---
title: "Debian Installer"
draft: false
menu:
  docs:
    title:
    parent: "Pinebook_Pro/Software"
    identifier: "Pinebook_Pro/Software/Debian_installer"
    weight:
aliases:
  - /wiki/Pinebook_Pro_Debian_Installer
---

* This is an image creator and Debian installer that runs from an existing Linux OS and installs Debian Bullseye
  * Installer can configure an encrypted rootfs and provides a choice of desktops, including the default Debian desktop based on Gnome 3
  * Strict adoption of upstream Debian packages (with exception of kernel and bootloaders) in order to provide a clean upgrade path as Bullseye matures
* Download at: https://github.com/daniel-thompson/pinebook-pro-debian-installer/
* Pull requests welcome but for discussion and support please use [the forum topic](https://forum.pine64.org/showthread.php?tid=8487).

## Features

| Feature | Status | Notes |
| --- | --- | --- |
| Install to micro SD card | Works | Automatically expands to use all available space |
| Install to eMMC | Works | Automatically adapts for 64GB and 128GB models |
| Full disk encryption | Works | Run installer with `CRYPT=yes`. Requires kernel support and this support is missing in the original factory kernel so it it not possible to install a LUKS filesystem from the factory distro. You can make a temporary unencrypted install with this installer and then use the temporary OS to perform a full encypted install. |
| Wifi | Works | Issues have been reported with WPA2 networks [https://forum.pine64.org/showthread.php?tid=8822] |
| Firefox | Works |  |
| VLC | Works |  |
| Fn+ keys | Work | After updating mesa to  20.0.7-1 |

## Current issues

|Issue|Category|Status|Workaround|Notes|
| --- | --- | --- | --- | --- |
| `cdn-dp fec00000.dp: Direct firmware load for rockchip/dptx.bin failed with error -2` | Debian issue https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=857054 | If having FDE, it fails to load at boot as the firmware is not included in initramfs | Include the dptx.bin firmware in the initramfs | See https://forum.pine64.org/showthread.php?tid=8487&pid=57202#pid57202 |
| Bluetooth doesn’t work  bluetooth hci1: Direct firmware load for brcm/BCM4345C5.hcd failed with error -2 |  |  | Copy those firmware https://gitlab.manjaro.org/manjaro-arm/packages/community/ap6256-firmware to /lib/firmware/brcm/. After that, Bluetooth works fine. | It seems some firmware is missing. See https://forum.pine64.org/showthread.php?tid=8731&pid=57525#pid57525 |
| Suspend doesn’t work properly, when lid is closed, the laptops gets hot and dramatically dry the battery |  |  | Install is preconfigured to use suspend-to-idle instead. This offers some power savings compared to normal running but suspend should only be used for short periods. | `# echo deep > /sys/power/mem_sleep` PBP simply doesn’t wake up after 'deep' sleep. |
| Often very slow to wake from suspend: 30-60 seconds. | Forum thread https://forum.pine64.org/showthread.php?tid=8822 |  | Sometimes pressing the power key helps wake it up. Set this key to not trigger sleep/shutdown in the Desktop Environment config. |  |
