---
title: "IMX258 Camera Debugging"
draft: true # page seems to break rendering
menu:
  docs:
    title:
    parent: "PinePhone_Pro"
    identifier: "PinePhone_Pro/IMX258_camera_debugging"
    weight: 
---

{{% docs/construction %}}

## Background

The Pinephone Pro’s rear camera is a Sony IMX258. The camera driver is present upstream, and at least [Manjaro’s kernel](https://gitlab.manjaro.org/manjaro-arm/packages/core/linux-pinephonepro) (downstream of Megi’s) enables the driver. The camera does not seem to work; this page catalogs work on figuring out why.

## Initial status

What do we see in dmesg?

```
imx258 1-001a: supply vana not found, using dummy regulator
imx258 1-001a: supply vdig not found, using dummy regulator
```

This tells us the kernel loads the driver, which is something.

Are these errors bad/fatal? Inspecting the [source](https://github.com/megous/linux/blob/orange-pi-5.17/drivers/media/i2c/imx258.c) shows us that these supplies are defined in the `imx258_supply_names` array, and `imx258_probe` calls `devm_regulator_bulk_get` to set them up.

`imx258_probe` checks the return code from `devm_regulator_bulk_get`, emitting a fatal "Failed to get supplies" message if the return code is negative (indicating failure). Since we don’t see this message (or any others from the driver), it looks like it loads successfully!

### How can we test the camera?

#### Megapixels

[Megapixels](https://gitlab.com/postmarketOS/megapixels) requires a per-device file to configure cameras. This one isn’t complete (most of its numbers are complete nonsense), but it should let us see what happens when Megapixels tries to access the camera:
`pine64,pinephone-pro.ini`:

```
[device]
make=PINE64
model=PinePhone Pro

[rear]
driver=imx258
media-driver=rkisp1
capture-width=4208
capture-height=3118
capture-rate=60
capture-fmt=GRBG10P
preview-width=1280
preview-height=960
preview-rate=60
#preview-fmt=BGGR8
capture-fmt=GRBG10P
rotate=90
mirrored=true
focallength=2.6
cropfactor=12.7
fnumber=2.8
flash-display=true
```

This segfaulted Megapixels for me. After patching some trivial segfaults, I get fatal GTK4 issues and other tangential problems. Let’s try something else.

#### Manually setting up a camera pipeline

We can roughly follow [this guide](https://www.kernel.org/doc/html/latest/admin-guide/media/rkisp1.html). Doing so gives us the following commands:

```
"media-ctl" "-d" "platform:rkisp1" "-r"
"media-ctl" "-d" "platform:rkisp1" "-l" "'imx258 1-001a':0 -> 'rkisp1_isp':0 [1]"
"media-ctl" "-d" "platform:rkisp1" "-l" "'rkisp1_isp':2 -> 'rkisp1_resizer_selfpath':0 [1]"
"media-ctl" "-d" "platform:rkisp1" "--set-v4l2" '"rkisp1_isp":0 [fmt:SGRBG10_1X10/1048x780]'
"v4l2-ctl" "-z" "platform:rkisp1" "-d" "rkisp1_selfpath" "-v" "width=1048,height=780,"
"media-ctl" "-d" "platform:rkisp1" "--set-v4l2" '"rkisp1_resizer_selfpath":0 [fmt:SGRBG10_1X10/1048x780 crop:(0,0)/1048x780]'

"v4l2-ctl" "-z" "platform:rkisp1" "-d" "rkisp1_selfpath" "-v" "width=800,height=600,pixelformat=422P"
"v4l2-ctl" "-z" "platform:rkisp1" "-d" "rkisp1_selfpath" "--stream-mmap" "--stream-count" "1" "--verbose"
```

Careful readers will note that this is setting the camera up with a low resolution compared to what the sensor can do. For some reason I can’t get the rkisp1 node to configure its sink pad with the maximum resolution of the sensor (4208x3118). Instead, it sets itself to 4032x3024. This mismatch is forbidden and causes v4l2 to give us EPIPE when we try to enable the stream. Using the lower resolution gets us further--the last command (which attempts to save a single frame of video) gives output like this:

```
VIDIOC_QUERYCAP: ok
		VIDIOC_REQBUFS returned 0 (Success)
		VIDIOC_QUERYBUF returned 0 (Success)
		VIDIOC_QUERYBUF returned 0 (Success)
		VIDIOC_QUERYBUF returned 0 (Success)
		VIDIOC_QUERYBUF returned 0 (Success)
		VIDIOC_QBUF returned 0 (Success)
		VIDIOC_QBUF returned 0 (Success)
		VIDIOC_QBUF returned 0 (Success)
		VIDIOC_QBUF returned 0 (Success)
		VIDIOC_STREAMON returned 0 (Success)
```

But then it just hangs there indefinitely.

Running under strace, we see the program stuck in an ioctl:

```
ioctl(3, VIDIOC_DQBUF, {type=V4L2_BUF_TYPE_VIDEO_CAPTURE_MPLANE
```

[VIDIOC_DQBUF](https://www.kernel.org/doc/html/v4.13/media/uapi/v4l/vidioc-qbuf.html) corresponds to dequeuing a buffer once it has been filled with an image by the v4l2 device. Apparently, the device never gives us back a captured frame.

### Now what?

#### Does i2c work at all?

The camera driver uses i2c; we can see the camera [in the .dts](https://github.com/megous/linux/blob/c5af9f4f874a66b65c73c450b79f6a86b1b46332/arch/arm64/boot/dts/rockchip/rk3399-pinephone-pro.dts#L890-L914) to determine that it’s on i2c bus 1, address 0x1a.

The imx258 is controlled over i2c, and sends image data over MIPI. The first step is to see if the i2c control is working.

Looking back at the driver, it seems we should see errors in dmesg if i2c communication fails. The driver checks the chip id in its probe function, which uses i2c, so we can conclude that i2c gets set up properly initially. Does it keep working?

#### Does i2c keep working? (FTrace)

We can see if other functions that use i2c produce errors--for example, when we run our `"v4l2-ctl" ... "--stream-mmap"` command, we expect that `imx258_start_streaming` will get called, and this function also writes a load of registers over i2c.

Build and install a kernel with CONFIG_FTRACE (not hard, but outside the scope of this write-up) and enable function graph tracing:

```
$ sudo su
. cd /sys/kernel/debug/tracing
. echo function_graph > current_tracer
. cat available_filter_functions | grep -E 'rkisp|imx258|v4l2' | awk '{print $1}' > set_graph_function
. echo 'vm_map_pages,__iommu_map,iommu_map_sg_atomic,rk_iommu_map,__alloc_pages,dma_alloc_attrs,dma_mmap_attrs,__vm_map_pages,vb2_mmap,clk_e,able,schedule_timeout,clk_disable,regmap_write,schedule,__i2c_tra,sfer,i2c_tra,sfer_buffer_flags,dma_free_attrs' | tr , '\n' > set_graph_notrace
. tee trace_pipe > ~/function-trace.log
```

Now, in another terminal session, run the `"v4l2-ctl" ... "--stream-mmap"` command again. We end up with a bunch (but hopefully not **too** much) of output in our first terminal and the `~/function-trace.log` file.

A quick grep shows that `imx258_start_streaming` is indeed called, so **i2c is working properly**.

### If i2c works, what doesn't?

Our program that asks for a video frame is still hung|We ask the camera to start streaming frames, it presumably does, but the v4l2 stack never tells us a frame has finished. Doing some digging in the v4l2 stack (and the rkisp1 driver), we find out that rkisp1 is notified about frame status via interrupts. We figure this out by manually backtracking through the code to see when `vb2_buffer_done`, the function in the vb2 API to call when a frame is finished, would be called. In the rkisp1 code, `vb2_buffer_done` is only called from `rkisp1_handle_buffer` which is only called from `rkisp1_capture_isr`, which (for the PPP’s rk3399 SoC) is only called from `rkisp1_isr`, which is an interrupt handler. We know that it’s an interrupt handler from the name (`_isr`), but also because it gets passed (indirectly) to `devm_request_irq` by way of being the `.isr` field of `rk3399_isp_isrs`.

Perhaps the hardware is never actually emitting the interrupt that signals a frame being finished. Indeed, grepping our FTrace log shows that `rkisp1_isr` is never called. A quick look at `/proc/interrupts` shows that **the only interrupt associated with the isp has never triggered** (0 count on every CPU):

```
. head -n1 /proc/interrupts; grep isp /proc/interrupts
           CPU0       CPU1       CPU2       CPU3       CPU4       CPU5    
 57:          0          0          0          0          0          0     GICv3  75 Level     ff914000.iommu, rkisp1
```

### `rkisp1` debugfs info

The `rkisp1` driver keeps some [error/debug counters](https://github.com/megous/linux/blob/c5af9f4f874a66b65c73c450b79f6a86b1b46332/drivers/media/platform/rockchip/rkisp1/rkisp1-common.h#L335-L363) in debugfs, which can be viewed at `/sys/kernel/debug/ff910000.isp0`.

Sadly, the only one of these that comes up nonzero is `sp_stop_timeout` ("upon stream stop, the capture waits 1 second for the isr to stop the stream. This param is incremented in case of timeout"). I observe it to increment once per time I terminate the `"v4l2-ctl" ... "--stream-mmap"` command. This tells us what we already know: interrupts are not firing, but it also tells us that we aren’t hitting any other errors that rkisp1 knows about.

## Next steps

Where do we go from here? I don’t know--something may be wrong with the way the .dts specifies interrupts, some kind of firmware/GIC (the rk3399’s interrupt controller) configuration issue, or something else. It would be good to try to determine:

* Whether the MIPI lines actually show traffic, if someone has a logic analyzer and a dissected PPP.
* Whether the DMA of frames to memory actually happens, regardless of (lack of) emission of the interrupt that tells us when said DMA finishes a frame.
* Whether the regulator messages we see during boot are actually significant. I don’t know enough about the Linux regulator framework to say whether these being not-found means power is not correctly supplied, or if Linux just isn’t being properly informed of the power supply requirements for precise tracking/power-saving when the camera is off.

## Megi saves the day

```
[I] <megi> you might be interested in this https://megous.com/dl/tmp/0ae6ba03a17a3d53.png
[I] <megi> https://megous.com/git/linux/tag/?h=orange-pi-5.18-20220521-1759
```

Turns out, the .dts had the wrong ISP connected to the sensor|This is fixed in [this commit](https://github.com/megous/linux/commit/9afd884f8b36121fb6097e77b6d35fe46ab48ad9), which is included in kernel version 5.18 or newer.

With a sufficiently new kernel, the following should produce an image (`frame.jpg`):

```
"media-ctl" "-d" "platform:rkisp1" "-r"
"media-ctl" "-d" "platform:rkisp1" "--set-v4l2" '"imx258 1-001a":0 [fmt:SGRBG10_1X10/1048x780]'
"media-ctl" "-d" "platform:rkisp1" "-l" "'imx258 1-001a':0 -> 'rkisp1_isp':0 [1]"
"media-ctl" "-d" "platform:rkisp1" "-l" "'rkisp1_isp':2 -> 'rkisp1_resizer_selfpath':0 [1]"
"media-ctl" "-d" "platform:rkisp1" "--set-v4l2" '"rkisp1_isp":0 [fmt:SGRBG10_1X10/1048x780 crop:(0,0)/1048x780]'
"media-ctl" "-d" "platform:rkisp1" "--set-v4l2" '"rkisp1_isp":2 [fmt:YUYV8_2X8/1048x780 crop:(0,0)/1048x780]'
"v4l2-ctl" "-z" "platform:rkisp1" "-d" "rkisp1_selfpath" "-v" "width=1048,height=780,"
"media-ctl" "-d" "platform:rkisp1" "--set-v4l2" '"rkisp1_resizer_selfpath":0 [fmt:YUYV8_2X8/1048x780 crop:(0,0)/1048x780]'

"v4l2-ctl" "-z" "platform:rkisp1" "-d" "rkisp1_selfpath" "-v" "width=1048,height=780,pixelformat=422P"
"v4l2-ctl" "-z" "platform:rkisp1" "-d" "rkisp1_selfpath" "--stream-mmap" "--stream-count" "1" "--stream-to=frame.raw"

ffmpeg -y -s:v 1048x780 -pix_fmt yuv422p -i frame.raw frame.jpg
```

Similarly, you can take a photo from the front camera with the following:

```
"media-ctl" "-d" "platform:rkisp1" "-r"
"media-ctl" "-d" "platform:rkisp1" "--set-v4l2" "'m00_f_ov8858 1-0036':0 [fmt:SBGGR10_1X10/1632x1224]"
"media-ctl" "-d" "platform:rkisp1" "-l" "'m00_f_ov8858 1-0036':0 -> 'rkisp1_isp':0 [1]"
"media-ctl" "-d" "platform:rkisp1" "-l" "'rkisp1_isp':2 -> 'rkisp1_resizer_selfpath':0 [1]"
"media-ctl" "-d" "platform:rkisp1" "--set-v4l2" "'rkisp1_isp':0 [fmt:SBGGR10_1X10/1632x1224 crop:(0,0)/1632x1224]"
"media-ctl" "-d" "platform:rkisp1" "--set-v4l2" "'rkisp1_isp':2 [fmt:YUYV8_2X8/1632x1224 crop:(0,0)/1632x1224]"
"v4l2-ctl" "-z" "platform:rkisp1" "-d" "rkisp1_selfpath" "-v" "width=1632,height=1224,"
"media-ctl" "-d" "platform:rkisp1" "--set-v4l2" "'rkisp1_resizer_selfpath':0 [fmt:YUYV8_2X8/1632x1224 crop:(0,0)/1632x1224]"
"media-ctl" "-d" "platform:rkisp1" "--set-v4l2" "'rkisp1_resizer_selfpath':1 [fmt:YUYV8_2X8/1632x1224]"

"v4l2-ctl" "-z" "platform:rkisp1" "-d" "rkisp1_selfpath" "-v" "width=1632,height=1224,pixelformat=422P"
"v4l2-ctl" "-z" "platform:rkisp1" "-d" "rkisp1_selfpath" "--stream-mmap" "--stream-count" "1" "--stream-to=frame.raw"

ffmpeg -y -s:v 1632x1224 -pix_fmt yuv422p -i frame.raw frame.jpg
```

In some cases, the isp exposes 2 devices nodes, and the nodes have separate topologies with a different sensor attached to each. In this situation, you may need to reference the isp using the correct device node for the commands to work.

### What's left?

* libcamera and megapixels still don’t work. Megapixels appears to need support for debayering YUYV, and both appear to be configuring the rkisp1 pipeline wrong.
* The images captured are pretty green and seem to have two pixels of garbage at their bottom edge. rkisp1 supports auto white-balance (AWB) using the params/stats pads, and libcamera has some smarts that may hook these up properly. In the meantime, raw images can be postprocessed to improve white balance and exposure.

## Useful links

* [Pinephone Pro Schematic](https://files.pine64.org/doc/PinePhonePro/PinephonePro-Schematic-V1.0-20211127.pdf)
* [Background on the GIC](https://blog.krybot.com/a?ID=01650-cea27a80-a1ab-4da1-9cb5-3945be91e3e1)
* [Background on the rkisp1 ISP](https://elinux.org/images/9/94/ISP-presentation.pdf)
