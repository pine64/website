---
title: "Development"
draft: false
menu:
  docs:
    title:
    parent: "PineNote"
    identifier: "PineNote/Development"
    weight: 5
aliases:
  - /wiki/PineNote_Development
  - /wiki/PineNote_Development/TODOs
---

## Sub pages

{{< children >}}

## Mainline development

### Status

The following table aims to provide a list of kernel modules required for running the PineNote. It also aims at listing repositories of work in progress. While some overlap with the Quartz64 module list ([Development](/documentation/Quartz64/Development#upstreaming_status)) is expected, only modules relevant to the PineNote hardware should be listed here.

| Function | Status | Module | Notes |
| --- | --- | --- | --- |
| Suspend mode driver | tbd | `rockchip-sip` | The rockchip-sip driver is not mainlineable; it is only needed [via a hack](https://github.com/smaeul/linux/commit/72127ca2806623a9de52cc1de39b06a38a22fe48) for suspend/resume to work when downstream TF-A is used. Suspend on upstream TF-A ([status](https://review.trustedfirmware.org/c/TF-A/trusted-firmware-a/+/16952)) should work without any special drivers. |
| Touchscreen | Implemented in Linux Mainline | `cyttsp5` | As of 6.2-rc1<sup>[[source](https://git.kernel.org/linus/5b0c03e24a061f9c9e8b28fa157b80990c559a37)]</sup> |
| Digitizer | Implemented in Linux Mainline | `i2c_hid_of` |  |
| Pen BLE Buttons | tbd | `ws8100-pen` | https://github.com/smaeul/linux/commit/46e87f1f9c7dd22af26d99f60eb83d2cace43cb5 |
| EBC Display controller | tbd | `rockchip-ebc` | [RFC PATCH 00/16 drm/rockchip: Rockchip EBC ("E-Book Controller") display driver](https://lore.kernel.org/all/20220413221916.50995-1-samuel@sholland.org/) |
| EBC PMic | tbd | `tps65185` | driver developed [here](https://github.com/smaeul/linux/tree/rk35/tps65185), small tweaks to resume behavior added on top [here](https://github.com/m-weigand/linux/commits/mw/rk35/tps65185) |
| LED backlight driver | Implemented in Linux Mainline | `lm3630a` |  |
| Accelerometer | Implemented in Linux Mainline | `st-accel-i2c` (silan,sc7a20) | As of 5.18-rc1 <sup>[[source](https://git.kernel.org/linus/c7a43b089826b17e46419d93c00c0d2f4b26735f)]</sup> |
| Rastergraphics unit RGA2e | tbd | `rga` (v4l2 mem2mem driver) | WIP patches for activation on the Pinenote/dithering/Y4-conversion can be found here: <sup>[[source](https://github.com/m-weigand/linux/commits/mw/rk35/rk356x-rga)]</sup>. Note that the rga2e in the rk3566 only works for RAM <= 4 G!). Simple demo program found here: <sup>[[source](https://github.com/m-weigand/rga-v4l2-demo)]</sup> |
| Mali GPU | Not in Linux Mainline<br> Implemented in upstream Mesa | `panfrost` | As of 5.18 <sup>[[source](https://git.kernel.org/linus/810028668c6d9da25664195d6b906c98a8169f72)]</sup> this got added to the `.dtsi` file, but it’s status is disabled. Enabling the `gpu` node upstream needs to wait till `rockchip-ebc` is upstreamed. |
| Wifi/BT | Implemented in Linux Mainline | `brcmfmac` |  |

### Mainlining notes

Some work happening here: https://gitlab.com/calebccff/linux, the idea is to import the parts of the eink/ebc drivers which are open source and use the downstream u-boot framebuffer driver as a reference to create a basic framebuffer driver.

Currently mainline struggles to boot due to weird issues while probing fixed regulators (?). It also fails to detect eMMC.

Further work is being done here: https://github.com/smaeul/linux/commits/rk356x-ebc-dev. This has a complete device tree, with working eMMC. Pen input also works out of the box. Wi-Fi and BT work with firmware copied from the factory Android image.

## How to boot mainline

UART is currently REQUIRED for this to work|We depend on u-boot falling back to console. Once we have a prebuilt u-boot which will use extlinux by default, UART won’t be needed anymore.

You can compile a u-boot that uses extlinux by default by following the instructions [here](https://github.com/JoshuaMulliken/pinenote_uboot/blob/aa9ecbd3d3e716f163f5a900824630f24e9f04ba/README.md#changing-default-boot-order).

### Getting to a U-Boot prompt

You can get to a U-Boot prompt by:

1. Holding Ctrl-C while the display panel initializes.
2. Wiping the "boot" partition.

### Using sysboot

The **extlinux.conf** should have the following contents:

    timeout 10
    default MAINLINE
    menu title boot prev kernel

    label MAINLINE
      kernel /vmlinuz
      fdt /rk3566-pinenote.dtb
      initrd /initramfs
      append earlycon console=tty0 console=ttyS2,1500000n8 fw_devlink=off PMOS_NO_OUTPUT_REDIRECT

At the U-Boot console, run the following command to boot your mainline kernel:

    sysboot ${devtype} ${devnum}:9 any ${scriptaddr} extlinux.conf

### Booting with individual commands

Booting with individual commands can be useful when you need to temporarily add some kernel command line arguments. Use these or similar commands at the U-Boot shell:

    load mmc 0:b ${kernel_addr_r} boot/Image
    load mmc 0:b ${fdt_addr_r} boot/rk3566-pinenote.dtb
    setenv bootargs ignore_loglevel root=/dev/mmcblk0p11 rootwait init=/bin/bash
    booti ${kernel_addr_r} - ${fdt_addr_r}

## Configuration

### Firmware for WiFi & Bluetooth and Waveform data

#### Using Maximilian's Debian image

If the Android partition (super) and waveform partition (waveform) is left intact the image extracts the WiFi, BT driver and waveform from the partitions on first run.

For instance if you repartitions the userdata partition and installs the image there.

#### Getting it from the Android install manually

Copy WiFi/BT firmware from Android:

    mkdir -p /cache/lib/firmware/brcm
    cp /vendor/etc/firmware/fw_bcm43455c0_ag_cy.bin /cache/lib/firmware/brcm/brcmfmac43455-sdio.bin
    cp /vendor/etc/firmware/nvram_ap6255_cy.txt /cache/lib/firmware/brcm/brcmfmac43455-sdio.txt
    cp /cache/lib/firmware/BCM4345C0.hcd /cache/lib/firmware/brcm/BCM4345C0.hcd

Copy waveform partition (via previously dumped file):

    adb root
    adb push waveform.img /cache/lib/firmware/waveform.bin

Or via dd within Linux:

    dd if=/dev/mmcblk0p3 of=/lib/firmware/waveform.bin bs=1k count=2048

#### Getting the Wifi and Bluetooth driver blobs from "other" sources

##### WiFi
The WiFi firmware .bin blob can be obtained by installing the Debian package firmware-brcm80211 (in the non-free section; in Bookworm and later it’s in the non-free-firmware section)

The WiFi brcmfmac43455-sdio.txt file can according to Eugen be sourced from https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/tree/brcm/brcmfmac43455-sdio.AW-CM256SM.txt needs a renaming when copying it to /lib/firmware/brcm/brcmfmac43455-sdio.txt). The content of the upstream .txt is different than the Android configuration, but is supposed to work.

As you don’t have WiFi yet you need to get the _firmware-brcm80211*.deb_ and _brcmfmac43455-sdio.txt_ file on the PineNote by other means, for instance using an USB stick

##### Bluetooth

Once you have WiFi working you can get BCM4345C0.hcd by installing the _bluez-firmware_:

    sudo apt install bluez-firmware

### Configuring the E-ink refresh mode

* https://github.com/m-weigand/mw_pinenote_misc/tree/main/rockchip_ebc/patches contains information on how/where to write in _/sys_ to alter the refresh mode
* https://github.com/m-weigand/mw_pinenote_misc/tree/main/gnome_extension contains the gnome extension used in Maximilian image

### Touchscreen and Pen In X.org

By default the pen config is flipped 180° (which makes it unusable) and the touchscreen doesn’t work. Placing the following config in `/etc/X11/xorg.conf.d/50-touchscreen.conf` will fix both problems:

    Section "InputClass"
        Identifier "evdev touchscreen"
        MatchProduct "tt21000"
        MatchIsTouchscreen "on"
        Driver        "evdev"
    EndSection
    Section "InputClass"
        Identifier    "RotateTouch"
        MatchProduct    "w9013"
        Option    "TransformationMatrix" "-1 0 1 0 -1 1 0 0 1"
    EndSection

## Further information

### Notes Written by Some Developers

* https://github.com/m-weigand/mw_pinenote_misc (Not super legible "notes", but very helpful repo with patches, videos, etc)
  * specifically see this section for helpful install/configure scripts: https://github.com/m-weigand/mw_pinenote_misc/tree/main/rockchip_ebc/patches#compiling.
* https://github.com/0cc4m/pinenote-misc
  * patch for enabling gpu: https://github.com/0cc4m/pinenote-misc/blob/main/mesa-archlinux-arm/mesa/rockchip-ebc.patch
  * prebuilt pkg’s: https://github.com/0cc4m/pinenote-misc/releases
* https://pwarren.id.au/pinenote/build_notes.txt
* https://github.com/DorianRudolph/pinenotes
* https://github.com/tpwrules/nixos-pinenote

### Alternative to patching of mesa

Mesa needs to be patched to add the driver entry point. The alternative to this, is the renaming of the ebc driver to an existing mesa driver entry point. A good existing name can be "repaper". To change the driver name, edit in the kernel tree the following files:

* replace "rockchip-ebc" with "repaper" in the two places in the file: drivers/gpu/drm/rockchip/rockchip_ebc.c
* preventive, replace "repaper" with "repaper-disabled" in the two places in the file: drivers/gpu/drm/tiny/repaper.c

### Video of Factory Android OS

[PineNote Developer Edition w/Tech Demo Android OS (Video Only)](https://www.youtube.com/watch?v=DWuTGgQHw98)

Informal walkthrough of the factory Android installation on the PineNote Developer Edition, recorded by a community member (Apr 2022). This is useful to look back at the original OS after erasing it from your device, or to get some additional detail before your device arrives.

The video also includes a chapter at the end showing [how to enable Android Debug Bridge ("adb") over USB](https://www.youtube.com/watch?v=DWuTGgQHw98&t=802s). Once enabled, keep the device powered and connect a USB cable directly to the PineNote (i. e. no UART breakout) to a computer running `adb`.

## Issues

### Resolved issues

The following topics have resolved:

* /documentation/PineNote/Further_information/Closed_Case_UART[PineNote/Hardware Changes/Closed Case UART]
* ***Could the USB-C port support USB 3.1 5Gbps?*** Yes and no. The RK3566 only has a host-mode 5Gbps controller, meaning it can only negotiate such a high data rate with a device such as a flash drive. When the RK3566 is acting as a device, it only supports 480Mbps transfer rates. The hardware required to switch between these modes would raise the PineNote’s price unreasonably. Therefore, the USB-C port will remain at USB 2.0 speeds for Host and Device mode.
* ***Could the USB-C port output DisplayPort?*** Yes and no. The hardware required to support such a feature would raise the PineNote’s price unreasonably. Therefore, DisplayPort output will not be possible through the USB-C port.
* ***Where is the microSD card slot?*** The case design of the PineNote is fixed, making physical changes like adding a microSD card slot would raise the cost unreasonably.
* ***How will I install software to the PineNote?*** This is a hardware and software question. If the software on your PineNote is completely broken and cannot boot to a recoverable state, a Hall (magnet) sensor was fitted to the PineTab motherboard as U9009. This sensor is attached to SARADC_VIN0_KEY/RECOVERY on the RK3566. With the device powered off, and screen face down, holding a magnet over U9009 and plugging in a USB-C cable causes the device to boot into ["rockusb"](https://opensource.rock-chips.com/wiki_Rockusb) flash mode. With proper flashing software and drivers, it should be possible to load a new operating system using rockusb if the system is soft-bricked. Of course, software vendors will need to be more careful with flashing firmware and providing useful "recovery" options on this device due to this process’s relative difficulty to other PINE64 devices.

### Unresolved issues

The following concerns have been brought up as open, unanswered topics:

* Does [Audio Adapter Accessory Mode](https://en.wikipedia.org/wiki/USB-C#Audio_Adapter_Accessory_Mode_2) work? It appears that the Headphone output of the audio codec was routed to the USB-C audio+USB switch, but it’s unclear whether CC lines are hooked up correctly for detection of such a device. The PineNote hardware team will be testing this functionality soon (as of August 19, 2021). Note that Audio Accessory mode is detectable by reading the I2C registers of the WUSB3801Q. So connecting ASEL to a GPIO would be enough to get this working if it is not working already.
* Why is the Headphone output of the audio codec routed to the speakers? HPL_OUT is routed from the RK817 PMIC and audio codec to U9010 (the USB-C switch) and U6 (the audio amplifier). SPK_OUT is unused. It seems like SPK_OUT should be routed to U6 and HPL_OUT to U9010.
* Nitpick: The cold white charging LED bleeds through the gap between the rear case and the device’s face. It does not bleed onto the screen, but it is jarring in low-light conditions or when the screen is amber. Could be resolved in software by turning off the charge LED when the screen is on.
* Is there any way to indicate when the device is in rockusb mode, such as connecting a certain magic pin to the power LED?
* The modem/4G connector (J6010) has its I2C and UART pins unconnected. Could those be connected to the SoC?
