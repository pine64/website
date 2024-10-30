---
title: "Releases"
draft: false
toc: true
menu:
  docs:
    title:
    parent: "ROCKPro64/Software"
    identifier: "ROCKPro64/Software/Releases"
    weight: 1
---

This page contains a list of all available releases and tools for the [ROCKPro64](/documentation/ROCKPro64) in alphabetical order.

## Linux

### AOSC
{{< figure src="/documentation/images/aosc.png" width="100" >}}

**AOSC OS** is a general purpose Linux distribution that strives to simplify user experience and improve free and open source software for day-to-day productivity. Originally AnthonOS (an OpenSUSE derivative built with SUSE Studio), then remade as a Debian derivative with customized KDE 4 UI and CJK support. To learn more about AOSC, please visit the official [AOSC website](https://aosc.io/)

Download:

* https://aosc.io/downloads/ (supports the microSD card and eMMC, 8GB or more)

| Default credentials | |
| -------- | ------- |
| `aosc` | `anthon` |

### Armbian

{{< figure src="/documentation/images/armbian.png" width="100" >}}

**Armbian** is a Linux distribution designed for ARM boards. They are usually Debian or Ubuntu flavored. To find out more about Armbian and available options please visit their [site](https://www.armbian.com/rockpro64/). If you are booting from a Micro SD card, then both Linux kernel versions will work. If you are trying to boot from an eMMC module then the 4.4.y will work, but the newer 5.10.y will not.

Download:

* https://dl.armbian.com/rockpro64/archive/

### Batocera Linux

{{< figure src="/documentation/images/batocera.png" width="100" >}}

**Batocera Linux** is an open-source and completely free retro-gaming distribution that can be copied to a USB stick or an SD card with the aim of turning any computer/nano computer into a gaming console during a game or permanently. Visit the project’s website here (https://batocera.org/). You can follow the ongoing discussion about batocera.linux on the PINE64 forum (https://forum.pine64.org/showthread.php?tid=7084)

Download:

* https://batocera.org/download

### Debian

{{< figure src="/documentation/images/Debian-logo.png" width="100" >}}

**Debian** is an operating system and a distribution of free software. See the forum thread [here](https://forum.pine64.org/showthread.php?tid=9744).

Download:

* [Debian 11 Bullseye](https://deb.debian.org/debian/dists/bullseye/main/installer-arm64/current/images/netboot/SD-card-images/)
* [Debian 12 Bookworm](https://deb.debian.org/debian/dists/bookworm/main/installer-arm64/current/images/netboot/SD-card-images/) (recommended)
* [Daily netboot images](https://d-i.debian.org/daily-images/arm64/)

Instructions:

* Download: `firmware.rockpro64-rk3399.img.gz`
* Download: `partition.img.gz`
* Create the disk image:
  * For Linux: `zcat firmware.rockpro64-rk3399.img.gz partition.img.gz > complete_image.img`
  * For Mac: `gzcat firmware.rockpro64-rk3399.img.gz partition.img.gz > complete_image.img`
* Write the image to your boot device:
  * For Linux: `dd if=complete_image.img of=your_chosen_boot_device bs=4M`
  * For Mac: see [Getting started](/documentation/Introduction/Getting_started)

Notes:

* An Ethernet connection is required for the above installer
* Remember to leave some space before your first partition for u-boot! You can do this by creating a 32M size unused partition at the start of the device.
* See the [troubleshooting section](/documentation/ROCKPro64/Troubleshooting) if you encounter issues with GPU acceleration.

### DietPi

{{< figure src="/documentation/images/dietpi.png" width="100" >}}

**DietPi** is a lightweight, yet easy to setup and feature-rich Linux distribution, based on Debian. To find out more about DietPi, please visit the [official documentation](https://dietpi.com/docs/). Discuss the ROCKPro64 build on the [PINE64 forum thread](https://forum.pine64.org/showthread.php?tid=12532).

Download:

* [Direct download from dietpi.com](https://dietpi.com/downloads/images/DietPi_ROCKPro64-ARMv8-Bookworm.img.xz)

| Default credentials | |
| -------- | ------- |
| `root` | `dietpie` |

### LibreELEC

{{< figure src="/documentation/images/libreelec.jpg" width="100" >}}
**LibreELEC** is a lightweight 'Just enough OS' Linux distribution purpose-built for Kodi on current and popular mediacentre hardware.

Download:

* [Official LibreELEC build image](https://libreelec.tv/downloads/rockchip/) (look for PINE64 RockPro64-LibreELEC-RK3399.arm-x.x.x-rockpro64.img.gz, supports microSD card and the eMMC module of 8GB or more.)

{{< admonition type="note" >}}
 Unzip and flash the image to a microSD card or eMMC module, for example using _dd_.
{{< /admonition >}}

### Manjaro ARM

{{< figure src="/documentation/images/Manjaro-logo.svg" width="100" >}}

**Manjaro** is a user-friendly Linux distribution based on the independently developed Arch operating system. To learn more about Manjaro please visit [Manjaro forum](https://forum.manjaro.org/c/arm/releases/102).

Download:

* [from Github](https://github.com/manjaro-arm/rockpro64-images/releases)

Notes:

* Decompress the image (***unxz****) before flashing, or decompress on the fly while flashing (****xzcat*** in a root shell, Etcher, or others)
* A display and keyboard will be required for first boot.
* Initial setup includes: keyboard layout, locale, username, user password, and root password.
* The installer will expand the root partition to use the remaining space on the storage device you’ve flashed.

### Nems Linux

{{< figure src="/documentation/images/nems.jpg" width="100" >}}

**NEMS** stands for _Nagios Enterprise Monitoring Server_ and it is a modern pre-configured, customized and ready-to-deploy Nagios Core image designed to run on low-cost micro computers. To find out more about NEMS on the PINE64 and available tweaks to the installation please visit the [PINE64 forum thread](https://forum.pine64.org/showthread.php?tid=7306).

Download:

* [Download page](https://nemslinux.com/download/nagios-for-pine64.php) with torrent seed or direct download.

| Default credentials | |
| -------- | ------- |
| `nemsadmin` | `nemsadmin` |

### NixOS

{{< figure src="/documentation/images/NixOS.webp" width="100" >}}

**NixOS** is a Linux distribution built on top of the Nix package manager using declarative configuration to allow reliable system upgrades. More information can be found on the [NixOS wiki](https://wiki.nixos.org/wiki/NixOS_on_ARM/PINE64_ROCKPro64).

Download:

* [nixos-installer-rockpro64](https://github.com/AshyIsMe/nixos-installer-rockpro64)

### OpenMediaVault

{{< figure src="/documentation/images/omv.png" width="100" >}}

**OpenMediaVault** is the next generation network attached storage (NAS) solution, [click this link to OMV main page](https://www.openmediavault.org/) to learn more. Forum thread concerning this release can be found [here](https://forum.pine64.org/showthread.php?tid=6308)

Download:
{{< admonition type="warning" >}}
 Outdated release
{{< /admonition >}}
* Stretch 32bit (armhf): [Direct download from ayufan’s github](https://github.com/ayufan-rock64/linux-build/releases/download/0.8.3/stretch-openmediavault-rockpro64-0.8.3-1141-armhf.img.xz)
* Stretch 64bit (aarch64): [Direct download from ayufan’s github](https://github.com/ayufan-rock64/linux-build/releases/download/0.8.3/stretch-openmediavault-rockpro64-0.8.3-1141-arm64.img.xz)

Notes:

* You need to enable root login in OMV WebGUI
* [OpenMediaVault Plugins](http://omv-extras.org/joomla/index.php/omv-plugins-3/3-stable)

| Default credentials | |
| -------- | ------- |
| `rock64` (TTY and SSH, except OMV) | `rock64` |
| `admin` (WebGUI Login) | `openmediavault` |
| `root` (TTY and SSH) | `openmediavault` |

### OpenWrt

{{< figure src="/documentation/images/Openwrt_logo_square.png" width="100" >}}

**OpenWrt** ​is a highly extensible ​GNU/​Linux ​distribution for embedded devices ​(typically wireless routers). Unlike many other distributions for these routers, OpenWrt ​is built from the ground up to be a full-featured, easily modifiable operating system for your router. In practice, this means that you can have all the features you need with none of the bloat, powered by a Linux kernel ​that’s more recent than most other distributions.

Download:

* https://openwrt.org/toh/pine64/rockpro64_v2.1

### postmarketOS

{{< figure src="/documentation/images/PostmarketOS_logo.png" width="100" >}}

postmarketOS extends [Alpine Linux](https://www.alpinelinux.org/) to run on smartphones and other devices.
At the time of writing, the only user interface provided through prebuilt images for the ROCKPro64 is [Plasma Bigscreen](https://plasma-bigscreen.org/).

Download:

* https://postmarketos.org/download/

| Default credentials | |
| -------- | ------- |
| `user` | `147147` |

### R-Cade

{{< figure src="/documentation/images/RCadeLogo.jpg" width="100" >}}

Retro Center’s **R-Cade**, the 4K Media Center Arcade. [RCade](https://www.retro-center.com/about-r-cade/) Features 100+ retro-gaming systems, a lightweight web browser, and full 4K UHD media playback.

Download:

* [Direct download from Retro Center’s GitHub](https://github.com/retro-center/rcade_releases/releases) (USB, microSD and eMMC boot)

### Recalbox

{{< figure src="/documentation/images/RB.png" width="100" >}}

**Recalbox** allows you to re-play a variety of videogame consoles and platforms in your living room, with ease|Visit the project’s website here (https://www.recalbox.com/). You can follow the ongoing discussion about Recalbox on the PINE64 forum (https://forum.pine64.org/showthread.php?tid=7194)

Download:
{{Template:Outdated release}}
* [download](https://github.com/mrfixit2001/recalbox_rockpro64/releases) release from mrfixit2001 github.

### SkiffOS

{{< figure src="/documentation/images/SkiffOS-Icon-1.png" width="100]_Minimal_cross-compiled_OS_optimized_for_hosting_distributions_in_Docker_containers._Provides_the_reliability_of_firmware_with_the_ease-of-use of package managers. Uses the http://buildroot.org[Buildroot" >}} cross-compilation tool for support for all Pine64 boards.

Use configuration packages to configure the distribution:

* core/gentoo: Gentoo optimized for Rockpro64
* core/nixos: NixOS arm64

You can also configure the skiff core yaml file to configure multiple distributions to run in parallel.

The boot-up OS can be upgraded independently from the containers.

Download:

* The repository and instructions can be found [here](https://github.com/skiffos/SkiffOS/tree/master/configs/pine64).

### Slackware

{{< figure src="/documentation/images/slackware.jpg" width="100" >}}

**Slackware** is the world’s oldest actively developed Linux distribution, providing a modern user land (applications) and Linux Kernel, within a more classic Unix Operating System environment.

Resources:

* [Installation instructions](https://docs.slackware.com/slackwarearm:inst).
* [Installation video guide](https://www.youtube.com/watch?v=uXAL9jz-yaA&list=PL1XOSJnvang3VLmqke2QbRitKtOD6Rm3t)

### slarm64

**slarm64** is an unofficial aarch64 / riscv64 Slackware Linux port. You can follow the ongoing discussion about slarm64 on the RockPro64 on the PINE64 forum (https://forum.pine64.org/showthread.php?tid=6823) or this forum thread for more general slarm64 information: https://www.linuxquestions.org/questions/slackware-arm-108/slarm64-aarch64-unofficial-slackware-4175613287/.

Downloads:

* [download](http://dl.fail.pp.ua/slackware/images/rockpro64/) (supports microSD card, look for slarm64-current-aarch64-xfce-rockpro64-x.xx.x-build-xxxxxxxx.img.zst)

| Default credentials | |
| -------- | ------- |
| `root` | `password` |

Flashing the distribution to the eMMC:

* Flash the image to micro SD, power up the board with micro SD and login
* Copy the image file to micro SD by using SFTP. The image file must have the _.img_ file extension.
* After finish copy the file, power off the board and add eMMC module to the board
* Boot the board, run below command for flashing to eMMC module
* Run `dd if=[image file] of=/dev/mmcblkX bs=10M` (example: _sudo dd if=slack-current-aarch64-xfce_29Sep18-4.4.162-rockpro64-build-20181126.img of=/dev/mmcblkX bs=10M_)
* then edit these two files in eMMC module:
  * `mount /dev/mmcblk1p1 /media`
  * `echo "rootdev=/dev/mmcblk1p1" >> /media/boot/uEnv.txt`
  * `sed -i 's:mmcblk0p1:mmcblk1p1:' /media/etc/fstab`
* After that, power off the board and remove the microSD card. Then boot with only the eMMC module.

### Twister OS

{{< figure src="/documentation/images/Twister_OS.png" width="100" >}}

**Twister OS** brings a desktop computing experience for SBCs, right out-of-the-box. Including themes, applications, tools, and optimizations to get the most out of your SBC. For more information on Twister OS, please visit the [official site](https://twisteros.com/). You can follow the ongoing discussion about Twister OS on the PINE64 forum (https://forum.pine64.org/showthread.php?tid=12192).

Download:

* [Twister OS Armbian-Reforged XFCE Desktop image](https://twisteros.com/twisterarmbian.html) (2.8GB, supports the microSD card and eMMC modules with 16GB and more)

{{< admonition type="note" >}}
 After flashing image with Etcher, edit /boot/armbianEnv.txt, replace the dtb name with rk3399-rockpro64.dtb.
{{< /admonition >}}

| Default credentials | |
| -------- | ------- |
| `pi` | `raspberry` |

### Void Linux

**Void Linux** is a general purpose operating system, based on the monolithic Linux kernel. The official guide can be found at [Guide](https://docs.voidlinux.org/installation/guides/arm-devices/index.html). At this time there are no RockPro64 images available.

The following creates a bootable image from an existing Void Linux installation:

* `xbps-insall -Syu` to update the xbps installation of the installation
* create ROCKPro64 image with the _void-mklive_ software (from github.com):
  * create a rootfs via _mkrootfs.sh_: `sh mkrootfs.sh -o void-aarch64-muls-ROOTFS-yyyymmdd.tar.xz`
  * `sh mkplatformfs.sh rockpro64 void-aarch64-muls-ROOTFS-yyyymmdd.tar.xz`
  * `sh mkimage.sh -s 7GiB void-rockpro64-PLATFORMFS-yyyymmdd.tar.xz`
* write image to sdcard or eMMC: `dd if=IMAGE-FILENAME of=DEVICENAME bs=2M`
* If _mkplatformfs.sh_ errors with _ROCKPro64 not supported_, install _xbps-src_ from https://github.com/void-linux/void-packages and build the ROCKPro64 package.
* Tip:  write a new U-Boot to the image if you see on the serial console the boot-up stalls:
  * get the two U-Boot files from [pkgs.org](https://pkgs.org/download/u-boot-rockpro64), the aarch64 files:
  * `dd if=idbloader.img of=DEVICENAME seek=64`
  * `dd if=u-boot.itb of=DEVICENAME seek=16384`

| Default credentials | |
| -------- | ------- |
| `voidlinux` | `voidlinux` |

## BSD Images

### FreeBSD
{{< figure src="/documentation/images/Freebsd_Logo.png" width="100" >}}

**FreeBSD** is an operating system used to power modern servers, desktops, and embedded platforms. The [RockChip FreeBSD page](https://wiki.freebsd.org/arm/RockChip#RockPro64) has instructions for installing FreeBSD. Version 13.0 and greater include prebuilt images.

Download:

* Images for various FreeBSD releases can be found [here](https://www.freebsd.org/where/)

| Default credentials | |
| -------- | ------- |
| `freebsd` (SSH user, SSH enabled by default) | `freebsd` |
| `root` | `root` |

Notes:

* The wiki has instructions on [enabling the PWM cooling fan](https://wiki.freebsd.org/arm/RockChip#Fan_Control_on_RockPro64).

### NetBSD

{{< figure src="/documentation/images/netbsd.png" width="100]_*NetBSD*_is_a_free,_fast,_secure,_and_highly_portable_Unix-like_Open_Source_operating_system._To_learn_more_about NetBSD please visit https://www.netbsd.org/[NetBSD main page" >}}

Download:

* [download](https://armbsd.org/) latest release build from NetBSD by select 64bit - RockPro64 (size: 339 MB)

| Default credentials | |
| -------- | ------- |
| `root` (root user and SSH login) | `[none]` |

Notes:

* Instructions concerning enabling SSH can be found [here](https://www.netbsd.org/docs/guide/en/chap-boot.html#chap-boot-ssh) or the bootable image from armbsd.org can have the MSDOS partition modified to setup SSH using [this](https://man.netbsd.org/creds_msdos.8) method.

### OpenBSD

{{< figure src="/documentation/images/Puffy_mascot_openbsd.png" width="100" >}}

**OpenBSD** is a security-focused, free and open-source, Unix-like operating system based on the Berkeley Software Distribution. Official instruction to get OpenBSD on ROCKPro64 is [here](https://www.openbsd.org/arm64.html), and blogs on installation [is here](https://github.com/jasperla/openbsd-rockpro64) and [here](https://bsandro.tech/posts/openbsd-7.1-on-pine64-rockpro64/). Forum discussion is [here](https://forum.pine64.org/forumdisplay.php?fid=109).

## Chromium OS

{{< figure src="/documentation/images/chromium.jpg" width="100" >}}

The **Chromium OS** community build image for microSD card and eMMC module, version beta (R76). To learn more please visit the [forum](https://forum.pine64.org/showthread.php?tid=7659).

Download:
{{< admonition type="warning" >}}
 Outdated release
{{< /admonition >}}
* https://github.com/ayufan-rock64/chromiumos-build/releases/

{{< admonition type="note" >}}
 Flash the image to a microSD card or an eMMC module, for example using _dd_.
{{< /admonition >}}

## Android

{{< figure src="/documentation/images/Android_logo_2019_(stacked).svg" width="100" >}}

### Android 9.0.0

**Stock for DD method [eMMC Boot] [20200804]**
* Use 'dd' to write the image to the eMMC module using the USB-to-eMMC adapter module and boot. Using [Etcher](https://www.balena.io/etcher/) or another specialized SD writing tool is preferred.
* Please allow 3-5 minutes boot up time on first time for initialization
* Supports new RockPro64 AP6256 Wifi/BT module
* Support Sony IMX214 camera module and works on both MiPi-CSI ports
* This build supports PINE64 7" LCD panel with tablet UI (not Android TV)
* DD image for 8GB eMMC module
** [Direct download from pine64.org](http://files.pine64.org/os/ROCKPro64/android/ROCKPro64_dd_20200804_stock_android_9.0_emmcboot-8GB.img.gz)
***** MD5 (GZip file): 7287fd0846616354615c8d3eff6a2a92
***** File Size: 602MB
* DD image for 16GB eMMC module
** [Direct download from pine64.org](http://files.pine64.org/os/ROCKPro64/android/ROCKPro64_dd_20200804_stock_android_9.0_emmcboot-16GB.img.gz)
***** MD5 (GZip file): 78352bbf21198d062af8bab2217ee691
***** File Size: 611MB
* DD image for 32GB eMMC module
** [Direct download from pine64.org](http://files.pine64.org/os/ROCKPro64/android/ROCKPro64_dd_20200804_stock_android_9.0_emmcboot-32GB.img.gz)
***** MD5 (GZip file): c5c8dce419478f75f85f893ee4808dbd
***** File Size: 624MB
* DD image for 64GB eMMC module
** [Direct download from pine64.org](http://files.pine64.org/os/ROCKPro64/android/ROCKPro64_dd_20200804_stock_android_9.0_emmcboot-64GB.img.gz)
***** MD5 (GZip file): aab1cf4d30c4d16e6ce2672f3ecae935
***** File Size: 666MB

**Stock for RK Flash tool [eMMC Boot] [20200804]**
* Please unzip first and then using Android tool to flash in
* The OTG port located at USB type-C connector, needs USB type A to type C cable.
* [Direct download from pine64.org](http://files.pine64.org/os/ROCKPro64/android/ROCKPro64_20200708_stock_android_9.0_emmcboot.img.gz)
** MD5 (GZip file): 9ac830527814521e15b009fa2503c9e3
** File Size: 589MB

*Stock for DD method [eMMC Boot] [20200708]
* Use 'dd' to write the image to the eMMC module using the USB-to-eMMC adapter module and boot. Using [Etcher](https://www.balena.io/etcher/) or another specialized SD writing tool is preferred.
* Please allow 3-5 minutes boot up time on first time for initialization
* Supports new RockPro64 AP6256 Wifi/BT module
* This build supports PINE64 7" LCD panel with tablet UI (not Android TV)
* DD image for 8GB eMMC module
** [Direct download from pine64.org](http://files.pine64.org/os/ROCKPro64/android/ROCKPro64_dd_20200708_stock_android_9.0_emmcboot-8GB.img.gz)
***** MD5 (GZip file): ef5f5a890a9270734e0adee21f006837
***** File Size: 597MB
* DD image for 16GB eMMC module
** [Direct download from pine64.org](http://files.pine64.org/os/ROCKPro64/android/ROCKPro64_dd_20200708_stock_android_9.0_emmcboot-16GB.img.gz)
***** MD5 (GZip file): 179bd684a468f800a86f7c658a543bef
***** File Size: 606MB
* DD image for 32GB eMMC module
** [Direct download from pine64.org](http://files.pine64.org/os/ROCKPro64/android/ROCKPro64_dd_20200708_stock_android_9.0_emmcboot-32GB.img.gz)
***** MD5 (GZip file): d930b757c4427be07b83c37a9c8494a1
***** File Size: 630MB
* DD image for 64GB eMMC module
** [Direct download from pine64.org](http://files.pine64.org/os/ROCKPro64/android/ROCKPro64_dd_20200708_stock_android_9.0_emmcboot-64GB.img.gz)
***** MD5 (GZip file): 09a970d68a10bdb3d6495d55860940e6
***** File Size: 660MB

**Stock for RK Flash tool [eMMC Boot] [20200708]**
* Please unzip first and then using Android tool to flash in
* The OTG port located at USB type-C connector, needs USB type A to type C cable.
* [Direct download from pine64.org](http://files.pine64.org/os/ROCKPro64/android/ROCKPro64_20200708_stock_android_9.0_emmcboot.img.gz)
** MD5 (GZip file): 6d060ddd47ebcfd5cfcdbf90ec042c97
** File Size: 589MB

**Stock for DD method [eMMC Boot] [20190427]**
* Use 'dd' to write the image to the eMMC module using the USB-to-eMMC adapter module and boot. Using [Etcher](https://www.balena.io/etcher/) or another specialized SD writing tool is preferred.
* Please allow 3-5 minutes boot up time on first time for initialization
* Please ignore "internal problem with your device" popup message if appear on Android boot-up page.
* This build supports PINE64 7" LCD panel with tablet UI (not Android TV)
* DD image for 16GB eMMC module
** [Direct download from pine64.org](http://files.pine64.org/os/ROCKPro64/android/ROCKPro64_dd_20190417_stock_android_9.0_emmcboot-16GB.img.gz)
***** MD5 (GZip file): 3BA4C72D81BCFC4C21B3B5D2BCB4F9F7
***** File Size: 609MB
* DD image for 32GB eMMC module
** [Direct download from pine64.org](http://files.pine64.org/os/ROCKPro64/android/ROCKPro64_dd_20190417_stock_android_9.0_emmcboot-32GB.img.gz)
***** MD5 (GZip file): 4965CCF50A8F06CEB2E4A6828A21F31C
***** File Size: 627MB
* DD image for 64GB eMMC module
** [Direct download from pine64.org](http://files.pine64.org/os/ROCKPro64/android/ROCKPro64_dd_20190417_stock_android_9.0_emmcboot-64GB.img.gz)
***** MD5 (GZip file): 748EC28FE5D5395D33E858C913D744BF
***** File Size: 663MB

**Stock for DD method [microSD Boot] [20190506]**
* DD image to microSD card and boot.
* Use 'dd' to write the image to the eMMC module using the USB-to-eMMC adapter module and boot. Using [Etcher](https://www.balena.io/etcher/) or another specialized SD writing tool is preferred.
* Please allow 3-5 minutes boot up time on first time for initialization
* Please ignore "internal problem with your device" popup message if appear on Android boot-up page.
* This build supports PINE64 7" LCD panel with tablet UI (not Android TV)
* DD image for 8GB microSD card
** [Direct download from pine64.org](http://files.pine64.org/os/ROCKPro64/android/ROCKPro64_dd_20190506_stock_android_9.0_sdboot-8GB.img.gz)
***** MD5 (GZip file): E1C551E8106E178841E1C3F71432194A
***** File Size: 599MB
* DD image for 16GB microSD card
** [Direct download from pine64.org](http://files.pine64.org/os/ROCKPro64/android/ROCKPro64_dd_20190506_stock_android_9.0_sdboot-16GB.img.gz)
***** MD5 (GZip file): 73592FDD5A2F52F08020F16AD99E8C8C
***** File Size: 609MB
* DD image for 32GB microSD card
** [Direct download from pine64.org](http://files.pine64.org/os/ROCKPro64/android/ROCKPro64_dd_20190506_stock_android_9.0_sdboot-32GB.img.gz)
***** MD5 (GZip file): 74DE0FE528F210E4DD483B411A71904B
***** File Size: 627MB
* DD image for 64GB microSD card
** [Direct download from pine64.org](http://files.pine64.org/os/ROCKPro64/android/ROCKPro64_dd_20190506_stock_android_9.0_sdboot-64GB.img.gz)
***** MD5 (GZip file): D7626BD50443A88AEB9254C88C575284
***** File Size: 663MB

**Stock for RK Flash tool [eMMC Boot] [20190427]**
* Please unzip first and then using Android tool to flash in
* The OTG port located at USB type-C connector, needs USB type A to type C cable.
* Please allow 3-5 minutes boot up time on first time for initialization
* This build supports PINE64 7" LCD panel with tablet UI (not Android TV)
* [Direct download from pine64.org](http://files.pine64.org/os/ROCKPro64/android/ROCKPro64_20190417_stock_android_9.0_emmcboot.img.gz)
** MD5 (GZip file): 046BA4A07933120809FBE1B9577B7341
** File Size: 592MB

### Android 8.1.0

**Stock for DD method [eMMC Boot] [20180828]**
* Use 'dd' to write the image to the eMMC module using the USB-to-eMMC adapter module and boot. Using [Etcher](https://www.balena.io/etcher/) or another specialized SD writing tool is preferred.
* Please allow 3-5 minutes boot up time on first time for initialization
* This build supports PINE64 7" LCD panel with tablet UI (not Android TV)
* [Direct download from pine64.org](http://files.pine64.org/os/ROCKPro64/android/ROCKPro64_dd_20180828_stock_android_8.1_emmcboot.img.xz)
** MD5 (XZ file): 9AEE21BC1B9DE886DCB0E64FA123988A
** File Size: 414MB

**Stock for DD method [microSD Boot] [20181212]**
* Use 'dd' to write the image to the eMMC module using the USB-to-eMMC adapter module and boot. Using [Etcher](https://www.balena.io/etcher/) or another specialized SD writing tool is preferred.
* Please allow 3-5 minutes boot up time on first time for initialization
* This build supports PINE64 7" LCD panel with tablet UI (not Android TV)
* DD image (for 8GB microSD card and above)
* [Direct download from pine64.org](http://files.pine64.org/os/ROCKPro64/android/ROCKPro64_dd_20181212_stock_android_8.1_sdboot.img.xz)
** MD5 (XZ file): 5A6BB7FCD7B3F77FCEE99CE462AE7405
** File Size: 616MB

**Stock for RK Flash tool [eMMC Boot] [20180828]**
* Please unzip first and then using Android tool to flash in
* The OTG port located at USB type-C connector, needs USB type A to type C cable.
* Please allow 3-5 minutes boot up time on first time for initialization
* This build supports PINE64 7" LCD panel with tablet UI (not Android TV)
* [Direct download from pine64.org](http://files.pine64.org/os/ROCKPro64/android/ROCKPro64_20180828_stock_android_8.1_emmcboot.img.xz)
** MD5 (XZ file): 4DACFE927BB09EE9C56B5232A7F624EE
** File Size: 415MB

### Android 7.1.2

**Stock for DD method [eMMC Boot] [20180518]**
* Use 'dd' to write the image to the eMMC module using the USB-to-eMMC adapter module and boot. Using [Etcher](https://www.balena.io/etcher/) or another specialized SD writing tool is preferred.
* Please allow 3-5 minutes boot up time on first time for initialization
* This build supports PINE64 7" LCD panel with tablet UI (not Android TV)
* [Direct download from pine64.org](http://files.pine64.org/os/ROCKPro64/android/ROCKPro64_dd_20180518_stock_android_7.1_emmcboot.img.xz)
** MD5 (XZ file): 33622034ACDBC31A7D7BB01ED634E29B
** File Size: 345MB

**Stock for RK Flash tool [eMMC Boot] [20180518]**
* Please unzip first and then using Android tool to flash in
* The OTG port located at USB type-C connector, needs USB type A to type C cable.
* Please allow 3-5 minutes boot up time on first time for initialization
* This build supports PINE64 7" LCD panel with tablet UI (not Android TV)
* [Direct download from pine64.org](http://files.pine64.org/os/ROCKPro64/android/ROCKPro64_20180518_stock_android_7.1_emmcboot.img.xz)
** MD5 (XZ file): 90C1991DADAE13ADC94E927F171F8920
** File Size: 342MB

### Android SDK

**Android P SDK [v9.0]**
* [Direct Download from pine64.org](http://files.pine64.org/SDK/ROCKPro64/ROCKPro64_SDK_android9.0.tar.gz)
** MD5 (TAR-GZip file): 3CEBEEFD1A873BEEEC149148A785D92E
** File Size: 125.16GB

### Slash TV OS

Android 7 based system including Play Store, working only from SD card (does not boot when installed on eMMC)

* https://drive.google.com/drive/folders/1K5YhWaB7Xstuv2HCo1HkpglCEm9x-RIM

## Development resources

The Ayufan github page

* [github.com/ayufan-rock64/linux-build/](https://github.com/ayufan-rock64/linux-build/releases)

Below are the LPDDR4 driver for RK3399

* [rk3399_loader_v1.10.112_support_1CS.bin, this is 800Mhz version used in Android Build](http://files.pine64.org/os/ROCKPro64/driver/rk3399_loader_v1.10.112_support_1CS.bin)
* [rk3399_ddr_666MHz_v1.11.bin, this is alpha version](http://files.pine64.org/os/ROCKPro64/driver/rk3399_ddr_666MHz_v1.11.bin)
* [rk3399_ddr_933MHz_v1.11.bin, this is alpha version](http://files.pine64.org/os/ROCKPro64/driver/rk3399_ddr_933MHz_v1.11.bin)

ROCKPro64 related files

* [ROCKPro64 Kernel file](http://files.pine64.org/os/ROCKPro64/driver/kernel_rockpro64.tar.gz)
* [trust.img](http://files.pine64.org/os/ROCKPro64/driver/trust.img)

## Miscellaneous tools

* [Windows ADB driver package](http://files.pine64.org/doc/rock64/tools/DriverAssitant_v4.5.zip)
* [MAC address](/documentation/ROCK64/Software/MAC_address)
* [Guide to install stock Android build to eMMC module](http://files.pine64.org/doc/rock64/guide/ROCK64_Installing_Android_To_eMMC.pdf)
* [Tools to burn Android build into a bootable microSD card](http://files.pine64.org/doc/rock64/tools/SD_Firmware_Tool._v1.46.zip)
* [Tools that allows developer flash image into eMMC’s Loader/Parameter/Misc/Kernal/Boot/Recovery/System/Backup partition](http://files.pine64.org/doc/rock64/tools/AndroidTool_Release_v2.38.zip)
