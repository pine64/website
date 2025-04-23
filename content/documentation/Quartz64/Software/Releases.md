---
title: "Releases"
draft: false
toc: true
menu:
  docs:
    title:
    parent: "Quartz64/Software"
    identifier: "Quartz64/Software/Releases"
    weight: 1
aliases:
  - /wiki/Quartz64_Software_Releases
---

This page contains a list of all available operating systems for the [Quartz64](/documentation/Quartz64) in alphabetical order, as well as links to other resources.

## Software releases

{{< admonition type="warning" >}}
 You are strongly encouraged to procure a 3.3V UART serial adapter capable of running at 1.5 mbauds, such as [the Woodpecker](https://pine64.com/product/serial-console-woodpecker-edition/) if you want to use a Quartz64, as some images' U-Boot may have no video output on this chip.
{{< /admonition >}}

{{< admonition type="important" >}}
 **Note:** The images are provided by the community, not by PINE64. Most community projects currently aim at getting mainline Linux running on the board, not some vendor provided kernel that will never be receiving updates. A mainline-first approach allows for the boards to continue receiving important updates, such as security updates, for years to come, as well as have higher quality code in the kernel as it underwent independent review, but does mean that not all aspects of the hardware work right out of the gate.
{{< /admonition >}}

### Armbian

{{< figure src="/documentation/images/armbian.png" width="100" >}}

**Armbian** is a base operating system platform for single board computers

* Lightweight Debian or Ubuntu based Linux distribution specialized for ARM development boards
* Each system is compiled, assembled and optimized by [Armbian Build Tools](https://github.com/armbian/build)
* It has powerful build and software development tools to make custom builds

Download:

{{< admonition type="note" >}}
 This image appears to have issues detecting more than 2GB of RAM. It is strongly recommended to use a different distribution.
{{< /admonition >}}

* [latest, as fresh as possible, upon code change, images](https://github.com/armbian/build/releases/)

Notes:

* Support on Armbian forums https://forum.armbian.com/forum/96-upcoming-hardware-wip/

### DietPi

{{< figure src="/documentation/images/dietpi.png" width="100" >}}

**DietPi** is a lightweight, yet easy to setup and feature-rich Linux distribution, based on _Debian_. To find out more about DietPi, please visit the [official documentation](https://dietpi.com/docs/). Discuss the Quartz64 builds on the [PINE64 forum thread](https://forum.pine64.org/showthread.php?tid=17601).

Download:

* Quartz64 Model A: [Direct download from dietpi.com](https://dietpi.com/downloads/images/DietPi_Quartz64A-ARMv8-Bookworm.img.xz)
* Quartz64 Model B: [Direct download from dietpi.com](https://dietpi.com/downloads/images/DietPi_Quartz64B-ARMv8-Bookworm.img.xz)
* SOQuartz: [Direct download from dietpi.com](https://dietpi.com/downloads/images/DietPi_SOQuartz-ARMv8-Bookworm.img.xz)

| Default credentials | |
| -------- | ------- |
| `root` | `dietpi` |

### Manjaro ARM

{{< figure src="/documentation/images/Manjaro-logo.svg" width="100" >}}

**Manjaro ARM** is a user friendly rolling release distribution, based on Arch Linux ARM.

Download:

* Quartz64 Model A: [Image on GitHub](https://github.com/manjaro-arm/quartz64-a-images/releases)
* Quartz64 Model B: [Image on GitHub](https://github.com/manjaro-arm/quartz64-b-images/releases)

Notes:

Most of the hardware support is already available in the mainline kernel. If some devices doesn’t work it is possible to swap to the linux-quartz64 kernel `pacman -S linux-quartz64`.

Following desktop options available:

* Gnome
* KDE Plasma
* Mate
* Sway
* XFCE
as well as minimal image without desktop.

### NetBSD

**NetBSD** is a free, fast, secure, and highly portable Unix-like Open Source operating system. It relies upon the UEFI support in Tianocore. Before NetBSD 10 is released, the latest version of NetBSD-current should be used.

Download:

* [NetBSD daily builds top level](https://nycdn.netbsd.org/pub/NetBSD-daily/HEAD/) from inside here, navigate to a date, and inside the images/ subdirectory are installable images. Use the one called "NetBSD-<version>-evbarm-aarch64-install.img.gz".

Notes:

* This image can be written to a supported device, such as the eMMC interface, any USB storage device, NVMe, and PCIe AHCI SATA are all supported with builds after 2022-01-15.
* Currently this can not be shared with the EDK2 port, ie, microSD for EDK2 and some other media for NetBSD.

### Plebian

Plebian stands for **P*INE64 *L*ive D*ebian** and aims to be a fairly vanilla live Debian image for Quartz64 and SOQuartz devices, based on Debian Bookworm.

* [Download Release Images](https://github.com/Plebian-Linux/quartz64-images/releases)
* [Read The Instructions](https://github.com/Plebian-Linux/quartz64-images/blob/main/RUNNING.md)
* [Visit plebian.org to learn more](https://plebian.org/)

To flash, run (replace _/dev/sdX_ with your target block device):

```console
$ xzcat imagename.img.xz | sudo dd of=/dev/sdX bs=4M oflag=dsync status=progress
```

Some quick notes:

* You will be asked to change your password on first login (for what the default login is, read the instructions)
* Root file system is grown to take up the entire space of your boot device
* NetworkManager is used instead of Debian’s interfaces config to be more flexible with what adapters are plugged in and working
* An sshd is started on port 22 with freshly generated keys

### Tianocore EDK II port by jmcneill

This (as of 2021-12-30) is a work in progress to enable UEFI enabled systems, and is able to bring up SD, eMMC, USB, PCIe with SATA and NVMe, HDMI, thermal sensors, TRNG, as well as general Cortex A-55 features. Known to work with NetBSD -current, and the ESXi Arm fling version 1.8.

Download:

* [jmcneill’s Quartz64 UEFI Github](https://github.com/jaredmcneill/quartz64_uefi)

Notes:

* The microSD card image should be written to an microSD card and installed. Currently, using the same card for the operating system as well may be problematic.

## BSP Linux SDK

The *BSP Linux SDK ver 4.19_ for the Quartz64 Model A.

Download:

* [Direct download](https://files.pine64.org/SDK/Quartz64/QUARTZ64-model-A_BSP%20Linux.tar.gz) from _pine64.org_ (32.67GB, MD5 of the TAR-GZip file _24554419aec29700add97167a3a4c9ed_)

## Android SDK

### Android 11 SDK

The **Android 11 SDK** for the Quartz64 Model A SBC.

Download:

* [Direct download](https://files.pine64.org/SDK/Quartz64/QUARTZ64_SDK_android11.tar.gz) from _pine64.org_ (79.00GB, MD5 of the TAR-GZip file _77c2ff57ea3372fb04da7fb49e17d12b_)
* Just the boot blobs (<1MB): https://wiki.pine64.org/wiki/File:Rk35-blobs.tar.gz

### Android 11 Production Test Builds

#### Android 11 Stock

The **Android 11 Stock** images for eMMC boot for the Quartz64 Model A. This is test build that was used during product testing.

Download:

* [Stock image for the 8GB eMMC module](https://files.pine64.org/os/Quartz64/android/Quartz64_model-A_dd_20210604_stock_android11_emmcboot-8GB.img.gz) from _pine64.org_ (819MB, MD5 of the Gzip file _e4365753e584d9fce1b8f10f095eede6_, build 20210604)
* [Stock image for the 16GB eMMC module](https://files.pine64.org/os/Quartz64/android/Quartz64_model-A_dd_20210604_stock_android11_emmcboot-16GB.img.gz) from _pine64.org_ (1.10GB, MD5 of the Gzip file _491c5f7744b0ca0b74ae76e607051836_, build 20210604)
* [Stock image for the 32GB eMMC module](https://files.pine64.org/os/Quartz64/android/Quartz64_model-A_dd_20210604_stock_android11_emmcboot-32GB.img.gz) from _pine64.org_ (846MB, MD5 of the Gzip file _47a6f0cdac8bad06cb920743849a8894_, build 20210604)
* [Stock image for the 64GB eMMC module](https://files.pine64.org/os/Quartz64/android/Quartz64_model-A_dd_20210604_stock_android11_emmcboot-64GB.img.gz) from _pine64.org_ (884MB, MD5 of the Gzip file _4e2fed6f5db0d55afdc8a142fc0c4fe1_, build 20210604)

Notes:

* Write the disk images to the eMMC modules using the USB adapter, for example using `dd`.
* Please allow 3-5 minutes boot up time on first time for initialization.

#### Android 11 Production Test Build

The **Android 11 Production Test Build** for the Quartz64 model A for eMMC boot using ROCKChip tools method. This is a test build that was used during product testing.

Download:

* [Direct download](https://files.pine64.org/os/Quartz64/android/Quartz64_model-A_20210604_stock_android11_emmcboot.img.gz) from _pine64.org_ (812MB, MD5 of the Gzip file _800f867fdd0d1b2bd7822c156b6067e3_, build 20210604)

Notes:

* Please unzip first and then using [Rockchip Android tool ver 2.84](https://files.pine64.org/os/Quartz64/android/RKDevTool_Release_v2.84.zip) to flash in
* For Windows OS environment please install the [DriverAssistant v5.11](https://files.pine64.org/os/Quartz64/android/DriverAssitant_v5.1.1.zip) driver first
* The OTG port located at top USB 2.0 port on top of USB 3.0 port, needs USB type A to type A cable.
* Please allow 3-5 minutes boot up time on first time for initialization

### Android 13 SDK

The ***Android 13 SDK*** for the Quartz64 Model "Zero" SBC.

Download:

* [Direct download](https://files.pine64.org/SDK/Quartz64/Quartz64-Zero_Android13_SDK.tar.gz) from _pine64.org_ (111GB, MD5 of the TAR-GZip file _0cd965cf68145cc62876d50f320a715a_)

#### Android 13 Stock

The ***Android 13 Stock*** images for eMMC boot for the Quartz64 Model Zero. This is test build.

Download:

* [Direct download](https://files.pine64.org/os/Quartz64/android/Quartz64-Zero_Android13_emmc_boot_20240606_v1.0.img.gz) from _pine64.org_ (765MB, MD5 of the Gzip file _00086005b07b23b8de06fd0c9f8c6816_, build 20240606)

Notes:

* Please unzip first and then using [Rockchip Android tool ver 3.13](https://files.pine64.org/os/Quartz64/android/RKDevTool_v3.13_for_window.zip) to flash in
* For Windows OS environment please install the [DriverAssistant v5.11](https://files.pine64.org/os/Quartz64/android/DriverAssitant_v5.1.1.zip) driver first 
* The OTG port located on USB 3.0 port, needs USB type A to type A cable.
* Please allow 3-5 minutes boot up time on first time for initialization

The ***Android 13 Stock*** images for SD boot for the Quartz64 Model Zero. This is test build.

Download:

* [Direct download](https://files.pine64.org/os/Quartz64/android/Quartz64-Zero_Android13_sd_boot_20240614_v1.0.img.gz) from _pine64.org_ (765MB, MD5 of the Gzip file _c80d48ba407533734fb6484c25d2a398_, build 20240614)

Notes:

* Please unzip first and then using [Rockchip SD card program tool ver 1.74](https://files.pine64.org/os/Quartz64/android/SDDiskTool_v1.74.zip) to program SD card
* Please allow 3-5 minutes boot up time on first time for initialization
