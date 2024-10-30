---
title: "Bootable storage"
draft: false
menu:
  docs:
    title:
    parent: "Pinebook_Pro/Features"
    identifier: "Pinebook_Pro/Features/Bootable_storage"
    weight: 
---

{{< figure src="/documentation/images/Pbp_emmc_disable_sw.jpg" title="The PineBook Pro eMMC module and switch, shown in 'enabled' position" width="480" >}}

## Boot sequence details

The RK3399’s mask 32KB ROM boot code looks for the next stage of code at byte off-set 32768, (sector 64 if using 512 byte sectors). This is where U-Boot code would reside on any media that is bootable, [RK3399 boot sequence](/documentation/General/RK3399_boot_sequence)

## Boot devices

The Pinebook Pro is capable of booting from eMMC, USB 2.0, USB 3.0, or an SD card. It cannot boot from USB-C. The boot order of the hard-coded ROM of its RK3399 SoC is: SPI NOR, eMMC, SD, USB OTG.

At this time, the Pinebook Pro ships with a Manjaro + KDE build with [u-boot](https://www.denx.de/wiki/U-Boot/) on the eMMC. Its boot order is: SD, USB, then eMMC.

(An update has been pushed for the older Debian + MATE build that improves compatibility with booting other operating systems from an SD card. In order to update, fully charge the battery, establish an internet connection, click the update icon in the toolbar, and then reboot your Pinebook Pro. Please see [this log](https://forum.pine64.org/showthread.php?tid=7830) for details.)

Please note that PCIe, the interface used for NVMe SSD on the Pinebook Pro, is not bootable on the RK3399 and therefore is not a part of the boot hierarchy. It is possible to run the desired OS from NVMe by pointing extlinux on the eMMC to rootfs on the SSD. This requires uboot, the Kernel image, DTB, and extlinux.conf
in a /boot partition on the eMMC.

## eMMC information

The eMMC appears to be hot-pluggable. This can be useful if trying to recover data or a broken install. Best practice is probably to turn the eMMC switch to off position before changing modules. Note that the enable/disable label on the silkscreen is incorrect on some board revisions (known bad on v2.1).

The eMMC storage will show up as multiple block devices:
*mmcblk1boot0 - eMMC standard boot0 partition, may be 4MB
*mmcblk1boot1 - eMMC standard boot1 partition, may be 4MB
*mmcblk1rpmb - eMMC standard secure data partition, may be 16MB
*mmcblk1 - This block contains the user areas

Only the last is usable as regular storage device in the Pinebook Pro.
The device number of "1" shown above may vary, depending on kernel.

If the eMMC module is enabled after boot from an SD card, you can detect this change with the following commands as user "root":

    echo fe330000.mmc >/sys/bus/platform/drivers/sdhci-arasan/unbind
    echo fe330000.mmc >/sys/bus/platform/drivers/sdhci-arasan/bind

(Note: with the device trees coming with older kernels (Linux < 5.11), the device name may be fe330000.sdhci instead of fe330000.mmc)
