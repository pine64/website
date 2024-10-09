---
title: "Connecting a MIPI-DSI display"
draft: false
menu:
  docs:
    title:
    parent: "Quartz64/How-Tos"
    identifier: "Quartz64/How-Tos/Connecting_a_MIPI-DSI_display"
    weight: 
---

The [Quartz64](/documentation/Quartz64) single-board computers (both Model A and Model B) come with MIPI-DSI ports for connecting a MIPI-DSI compatible display.

This article will go into how to connect the official [PINE64 7" LCD Touch Screen Panel](https://pine64.com/product/7-lcd-touch-screen-panel/) and setting up the software. Since this requires a panel driver for each panel, other displays generally are **not** interchangeable, as they won’t use the same driver compatible (or even have a mainline driver at all!)

## Connecting the hardware

When connecting the display, please make sure the board is powered off and unplugged. Failure to do so could make you short out the pins while connecting it!

### Model A

{{< figure src="/documentation/images/Quartz64-model-a-dsi.jpg" >}}

To connect the hardware, lift up the dark flap of the part marked with "DSI" in red in the above picture. Then, insert the flat flex cable with the contacts pointing down (and the blue backing pointing up). In the same fashion, connect the thinner touch panel controller cable to the port marked with "TP" in blue.

For the DSI cable, connect the other end to the small green joiner/adapter board, which you can first connect to the display’s DSI connector, again with the contacts facing down.

For the touch cable, connect the other end to the small green PCB attached to the back of the panel, again paying attention to have the contacts facing downwards (and the blue backing facing upwards).

### Model B

{{< admonition type="important" >}}
 **Note:** There’s no port for the touch panel input on Model B.
{{< /admonition >}}

**TODO:** Write this section. Adapter cable is needed.

## Setting up the software

For the display to be used, you need to tell the kernel about it by modifying the device tree. The easiest way to go about this is to use device tree overlays.

The kernel needs to be built with `CONFIG_DRM_PANEL_FEIYANG_FY07024DI26A30D` turned on (either as module or built-in), as that is the driver for this panel.

### On Plebian

{{< admonition type="important" >}}
 **Note:** Currently Debian’s kernel doesn’t have the panel driver built as part of its configuration. We’ll get that sorted soon.
{{< /admonition >}}

Use `git clone` to clone the [overlay-examples](https://github.com/CounterPillow/overlay-examples) repository by CounterPillow. Then, grab a copy of the Linux kernel source from [kernel.org](https://kernel.org) if you don’t already have one. To build the device tree overlays, run `make INCLUDE_DIR=path/to/linux/include` in the overlay-examples directory, substituting _path/to/linux/include_ with your path of course.

For Quartz64 Model A, copy _build/quartz64a/pine64-lcd-panel.dtbo_ into your _/boot/dtbo/_ directory (create it if it doesn’t already exist) and run `sudo u-boot-update`.

That’s all there is to it, the panel should light up on your next reboot.
