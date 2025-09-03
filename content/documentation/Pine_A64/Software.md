---
title: "Software Releases"
draft: false
menu:
  docs:
    title:
    parent: "Pine_A64"
    identifier: "Pine_A64/Software"
    weight: 2
aliases:
  - /wiki/Pine_A64_Software_Release
  - /wiki/Pine_A64_Software_Releases
  - /wiki/PINE_A64_Software_Releases
---

This page contains a list of all available software releases and other resources for the PINE A64 and PINE A64+.

{{< admonition type="note" >}}
 The images for the PINE A64 and PINE A64+ are *not compatible with the PINE A64-LTS* due to LPDDR3 memory configuration. For PINE A64-LTS releases, please see the [Software](/documentation/SOPINE/Software).
{{</ admonition >}}

## Linux

### AOSC

{{< figure src="/documentation/images/aosc.png" width="100" >}}

*AOSC OS* is a general purpose Linux distribution that strives to simplify user experience and improve free and open source software for day-to-day productivity. To learn more about AOSC, please visit the official [AOSC website](https://aosc.io/).

Download:

* https://aosc.io/downloads/ (supports the microSD card and eMMC, 8GB or more)

| Default credentials | |
| -------- | ------- |
| `aosc` | `anthon` |

### Arch Linux ARM
	
{{< figure src="/documentation/images/Archlinux-logo.png" width="100" >}}

*Arch Linux ARM* is a distribution of Linux for ARM computers.

Installation:

* https://archlinuxarm.org/platforms/armv8/allwinner/pine64

### Armbian

{{< figure src="/documentation/images/armbian.png" width="100" >}}

*Armbian* is a Linux distribution designed for ARM boards. They are usually Debian or Ubuntu flavored.

Download:

* https://www.armbian.com/pine64/

### Debian

{{< figure src="/documentation/images/Debian-logo.png" width="100" >}}

*Debian* is an operating system and a distribution of free software. See the forum thread [here](https://forum.pine64.org/showthread.php?tid=9744).

Download:

* [Debian 11 Bullseye](https://deb.debian.org/debian/dists/bullseye/main/installer-arm64/current/images/netboot/SD-card-images/) (recommended)
* [Debian 12 Bookworm](https://deb.debian.org/debian/dists/bookworm/main/installer-arm64/current/images/netboot/SD-card-images/)
* [Daily netboot images](https://d-i.debian.org/daily-images/arm64/)

Instructions:

* Download: `firmware.pine64_plus.img.gz`
* Download: `partition.img.gz`
* Create the disk image:
  * For Linux: `zcat firmware.pine64_plus.img.gz partition.img.gz > complete_image.img`
  * For Mac: `gzcat firmware.pine64_plus.img.gz partition.img.gz > complete_image.img`
* Write the image to your boot device:
  * For Linux: `dd if=complete_image.img of=your_chosen_boot_device bs=4M`
  * For Mac: see [Getting started](/documentation/Introduction/Getting_started)

Notes:

* An Ethernet connection is required for the above installer

### DietPi

{{< figure src="/documentation/images/dietpi.png" width="100" >}}

*DietPi* is a lightweight yet easy to setup and feature-rich Linux distribution, based on Debian. To find out more about DietPi, please visit the [official documentation](https://dietpi.com/docs/). Discuss the PINE A64 build on the [PINE64 forum thread](https://forum.pine64.org/showthread.php?tid=12513).

Download:

* [Debian 11 Bullseye](https://dietpi.com/downloads/images/DietPi_PINEA64-ARMv8-Bullseye.img.xz) (supports the microSD card and eMMC, 4GB or more)
* [Debian 12 Bookworm](https://dietpi.com/downloads/images/DietPi_PINEA64-ARMv8-Bookworm.img.xz) (supports the microSD card and eMMC, 4GB or more)

| Default credentials | |
| -------- | ------- |
| `root` | `dietpi` |

### FreedomBox

{{< figure src="/documentation/images/FreedomBox.jpg" width="100" >}}

*FreedomBox* is a private server for non-experts: it lets you install and configure server applications with only a few clicks. For more information about FreedomBox, please visit http://www.freedombox.org.

Download:

* [Release](https://ftp.freedombox.org/pub/freedombox/hardware/pine64-plus/stable/freedombox-bookworm_pine64-plus-arm64.img.xz)
* [Signature](https://ftp.freedombox.org/pub/freedombox/hardware/pine64-plus/stable/freedombox-bookworm_pine64-plus-arm64.img.xz.sig)
* [Torrent](https://ftp.freedombox.org/pub/freedombox/hardware/pine64-plus/stable/freedombox-bookworm_pine64-plus-arm64.img.xz.torrent)

Notes:

* This is a headless build, not HDMI output.
* Please plug-in Ethernet cable first before initial power up. After power up for 10 minutes, using browser and type in https://fredombox.local to setup. Browser may warms for unsecure site and please proceed with exception.
* Freedom Manual: https://wiki.debian.org/FreedomBox/Manual

### LibreELEC

{{< figure src="/documentation/images/libreelec.jpg" width="100" >}}

*LibreELEC* is a "Just enough OS" Linux distribution combining the Kodi media center with an operating system.

Download:

* 512MB PINE A64: [direct download](https://test.libreelec.tv/) from Libreelec nightly build site (look for _LibreELEC-A64.arm-...-nightly-xxxxxxxx-xxxxxxx-pine64.img.gz_)
* 1GB/2GB PINE A64+ Board: [direct download](https://test.libreelec.tv/) from Libreelec nightly build site (look for _LibreELEC-A64.arm-...-nightly-xxxxxxxx-xxxxxxx-pine64-plus.img.gz_)

Notes:

* Nightly build for microSD boot

### motionEyeOS

{{< figure src="/documentation/images/motioneyeos.png" width="100" >}}

*motionEyeOS* is a Linux distribution that turns a single-board computer into a video surveillance system. The OS is based on BuildRoot and uses motion as a backend and motionEye for the frontend. Visit the [motionEyeOS GitHub](https://github.com/ccrisan/motioneyeos/releases/) and its [GitHub Wiki](https://github.com/ccrisan/motioneyeos/wiki) for more information

Download:

* 1GB/2GB PINE A64(+): [Direct download from GitHub](https://github.com/ccrisan/motioneyeos/releases/latest) (look for _motioneyeos-pine64-xxxxxxxx.img.xz_)

Notes:

* Suitable for 1GB/2GB PINE A64(+) variants
* There are 2 ways to interact with the OS:
  * Scan for its IP with hostname MEYE-* and go to the admin web interface `https://[IP]` and after login, you should able to see the output of the CAMERA MODULE on the web interface
  * Use the PINE64 USB SERIAL CONSOLE/PROGRAMMER and login

| Default credentials | |
| -------- | ------- |
| `admin` | none |

### NEMS Linux

{{< figure src="/documentation/images/nems.jpg" width="100" >}}

*NEMS* stands for *Nagios Enterprise Monitoring Server* and it is a modern pre-configured, customized and ready-to-deploy Nagios Core image designed to run on low-cost micro computers. To find out more on NEMS Linux, please visit their [site](https://nemslinux.com/).

{{< admonition type="warning" >}}
 Outdated release
{{</ admonition >}}

Download:

* [Download torrent seed from NEMS Linux](https://nemslinux.com/download/nagios-for-pine64.php) (2.66GB, MD5 of the xz file is _ac508549a829021491cfa23aeb18a063_)
* [Direct download from pine64.org](https://files.pine64.org/os/pine-a64/nems/NEMS_v1.5-Pine64-Build1.zip) (2.66GB, MD5 of the xz file is _ac508549a829021491cfa23aeb18a063_)

Notes:

* Suitable for all 512MB/1GB/2GB PINE A64(+) variants

| Default credentials | |
| -------- | ------- |
| `nemsadmin` | `nemsadmin` |

### openSUSE

{{< figure src="/documentation/images/opensuse-distribution.png" width="100" >}}

*openSUSE* is a free and open source RPM-based Linux distribution developed by the openSUSE project. More details can be found under https://en.opensuse.org/HCL:Pine64.

Download:

* [Images](http://download.opensuse.org/repositories/devel:/ARM:/Factory:/Contrib:/Pine64/images/)
* Headless build: [Direct download](http://download.opensuse.org/repositories/devel:/ARM:/Factory:/Contrib:/Pine64/images/openSUSE-Tumbleweed-ARM-JeOS-pine64.aarch64.raw.xz)

### OpenWRT

{{< figure src="/documentation/images/Openwrt_logo_square.png" width="100" >}}

The *OpenWrt* Project is a Linux operating system targeting embedded devices.

Download:

* [Direct download](https://downloads.lede-project.org/snapshots/targets/sunxi/cortexa53/) (look for _pine64_pine64-baseboard-ext4-sdcard.img.gz_ and _pine64_pine64-baseboard-squashfs-sdcard.img.gz_)

Notes:

* OpenWRT community build for microSD boot.
* This is headless build, please use serial console to configure

| Default credentials | |
| -------- | ------- |
| Default user | Use the command `passwd` |

## BSD

### NetBSD

{{< figure src="/documentation/images/netbsd.png" width="100" >}}

*NetBSD* is a free, fast, secure, and highly portable Unix-like Open Source operating system. To learn more about NetBSD please visit [NetBSD main page](https://www.netbsd.org/).

Download:

* [Direct download](https://www.invisible.ca/arm/) (345MB, select _PINE A64 / PINE A64+_)

Notes:

* NetBSD community build for microSD boot
* Instructions concerning enabling SSH can be found [here](https://www.netbsd.org/docs/guide/en/chap-boot.html#chap-boot-ssh)

| Default credentials | |
| -------- | ------- |
| `root` and SSH | none |

## Windows 10 IoT

{{< figure src="/documentation/images/win10iot.png" width="100" >}}

Download:

* [Windows IoT direct download](https://files.pine64.org/os/pine-a64/win10-iot/PINE64_Win10IoT_TestOS_build_10.0.15063.0_20170602.ffu) from _pine64.org_ (957MB, MD5 of FFU file _ACA617C0C9CEDA705DD510BF041E79B4_)

Notes:

* PINE64 Win10 IoT build already passed the [Microsoft Azure certification](https://catalog.azureiotsuite.com/details?title=Allwinner_Technology_Pine64)
* For step by step installation process, please follow this [github link](https://github.com/Leeway213/Win10-IoT-for-A64-Release-Notes/blob/master/doc/How%20to%20flash%20ffu.md)
* For release note, please follow this [github link](https://github.com/Leeway213/Win10-IoT-for-A64-Release-Notes/blob/master/20160809/Pine64/ReleaseNotes.md)
* For Microsoft Azure IoT SDKs, please follow this [github link](https://github.com/Azure/azure-iot-sdks/)

Changelog for Win10 IoT 10.0.15063.0_20170602:

* Update Notes since 10.0.15063.0_20170524:
  * Fix the failure of default application installation caused by a app certification issue
  * Fix that the default application cannot start automatically after installation
  * Fix Ethernet initialization problem and now the Ethernet will start successfully every time
  * Enable the usermode access for all unusable GPIO pins in Pi-2 bus( later provide a UWP sample to show how to control these pins )
* Extra Notes:
  * If you want to connect a USB peripheral for extension, please connect a USB hub to the lower USB interface as the medium
  * Please refer to [Part 2 of chapter 3: Debug with a virtual net over USB](https://github.com/Leeway213/BSP-aw1689/blob/master/doc/Dev%20Guide.md) on how to use the upper USB interface

Changelog for Win10 IoT 10.0.15063.0_20170524:

* Some Updates:
  * Update the OS version to build v.10.0.15063.0 (Creators Update)
  * New page style of Device Portal, visit `https://deviceipaddr:8080` to check it
  * Built-in Cortana assistant, need to be enabled in settings page in default app and Device Portal
  * Support on-screen keyboard, need to be enabled in Device Portal
  * Enable 100M Ethernet and fix some bugs
  * Support built-in UART bus in A64 SoC(not built in the ffu, later provide driver binary and deployment helper)
  * Support built-in IR module in A64 SoC(not built in the ffu, later provide source code and dev doc for developers in community)
* Known Issues:
  * Kernel debug is enabled by default. This will slow the bring-up process. If a kernel debug is not necessary for you, visit Device Portal and navigate to Processes->Run Command page, run this command to disable: `Bcdedit /store C:\EFIESP\EFI\Microsoft\boot\BCD /set {default} debug off`
  * An PnP bug in audio device may cause a blue screen when acting software shutdown
  * Ethernet device may not start with problem code 12 at the first time to bring up

## Linux BSP SDK

Linux BSP Kernel 4.9

* [Direct Download](https://files.pine64.org/SDK/PINE-A64/PINE-A64_lichee_BSP4.9.tar.xz) from _pine64.org_ (5.4GB, MD5 of the TAR-GZip file _7736e3c4d50c021144d125cc4ee047a4_)

## Android SDK

Android Oreo (v8.1)

* [Direct Download](https://files.pine64.org/SDK/PINE-A64/PINE-A64_SDK_android8.1.tar.xz) from _pine64.org_ (24.94GB, MD5 of the TAR-GZip file _b0394af324c70ce28067e52cd7bc0c87_)

## Other resources

* [Allwinner PhoenixCard Bootable SD-Card Creator](https://files.pine64.org/tools/allwinner/PhoenixCard4_1_3.zip)
* [Allwinner DragonFace software that will let you edit and modify A64 Stock Android Build PhoenixCard image](https://files.pine64.org/tools/allwinner/DragonFace.zip)

Below you will find useful links to various resources and forum threads:

* [Sunxi PINE64 Page](https://linux-sunxi.org/Pine64)
* [Longsleep BSP Linux Builds Download Page](https://www.stdin.xyz/downloads/people/longsleep/tmp/pine64-images)
* [Longsleep BSP Linux Kernel Thread on PINE64 Forum](https://forum.pine64.org/showthread.php?tid=293)
* [Longsleep BSP Xenial Thread on PINE64 Forum](https://forum.pine64.org/showthread.php?tid=376)
* [Longsleep BSP Arch Linux Thread on PINE64 Forum](https://forum.pine64.org/showthread.php?tid=343)