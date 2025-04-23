---
title: "Releases"
draft: false
menu:
  docs:
    title:
    parent: "Pinebook_Pro/Software"
    identifier: "Pinebook_Pro/Software/Releases"
    weight: 1
aliases:
  - /wiki/Pinebook_Pro_Software_Release
  - /wiki/Pinebook_Pro_Software_Releases
---

This page contains a list of all available releases and tools for the [Pinebook Pro](/documentation/Pinebook_Pro).

## Linux OS Image Releases

For information on how to install these images onto your device, please see the [Getting started](/documentation/Introduction/Getting_started) Page, which includes information on writing images to the device eMMC or an SD card

### Manjaro ARM

{{< figure src="/documentation/images/Manjaro-logo.svg" width="100" >}}

The Manjaro project offers a mainline kernel with patches and modules to support the Pinebook Pro hardware. To learn more about Manjaro please visit [Manjaro Forum](https://forum.manjaro.org/c/arm/). You can follow the ongoing discussion about Manjaro on the [PINE64 forum](https://forum.pine64.org/showthread.php?tid=8207).
All images boot from both SD card and the internal eMMC module.

Download:

* [Direct download from Manjaro](https://manjaro.org/download/): You have to navigate to the Manjaro ARM section and select "Generic" as the device in the drop-down list (the Pinebook Pro image has been removed and it’s now included in the generic one since version 22.08. Then you can choose Gnome, KDE Plasma, Mate, Minimal, Sway or Xfce.
* Old factory release: [Manjaro/Plasma 22.06 factory loaded build](https://files.pine64.org/os/PinebookPro/manjaro/Manjaro-ARM-kde-plasma-pbpro-bsp-22.06%20(2).img.xz) (June 2022) from _pine64.org_ (1.04GB, MD5 of the XZ file _d78031a4bed3eeb4f2001f3c89b9ed5a_)

### Armbian

{{< figure src="/documentation/images/armbian.png" width="100" >}}

Armbian is a base operating system platform for single board computers (_SBCs_) that other projects can trust to build upon. It is a lightweight Debian or Ubuntu based Linux distribution specialized for ARM development boards. Each system is compiled, assembled and optimized by the Armbian Build Tools. It has powerful build and software development tools to make custom builds and a vibrant community.

Download:

* [The Pinebook Pro Download Page](https://www.armbian.com/pinebook-pro/)

Notes:

* If you have any difficulties please visit our [forum](https://forum.armbian.com) or come chat with us on [IRC / Discord](https://docs.armbian.com/Community_IRC/)
* As of April 2023, Armbian only has Ubuntu images pre-made. However, using their tools to create a Debian image from scratch takes little expertise and results in an image that can be burned onto a USB stick or SD card. Their installer can then install it onto internal eMMC, including a working bootloader.

### Twister OS

{{< figure src="/documentation/images/Twister_OS.png" width="100" >}}

Twister OS Armbian-Reforged with Xfce. It boots from microSD card and from eMMC. For more information on Twister OS, please visit this [official site](https://twisteros.com/). You can follow the ongoing discussion about Twister OS on the [PINE64 forum](https://forum.pine64.org/showthread.php?tid=12192).

**Installation**

* After flashing image, edit /boot/armbianEnv.txt, replace the dtb name with `rk3399-pinebook-pro.dtb`

**Download location**

Get the latest image here: [Direct download latest images from Twister OS’s website](https://twisteros.com/twisterarmbian.html) (size: 2.8GB)

**Password**

| Default credentials | |
| --- | --- |
| `root` | `asdasd` |

### Fedora

{{< figure src="/documentation/images/fedora1.png" width="100" >}}

Fedora Linux is a Linux distribution developed by the Fedora Project. It creates an innovative, free, and open source platform for hardware, clouds, and containers that enables software developers and community members to build tailored solutions for their users.

Installation:

* Using this [blog post](https://nullr0ute.com/2021/05/fedora-on-the-pinebook-pro/) it is possible to run Official Fedora on the Pinebook Pro

Notes:

* Upstream Fedora uses the SPI flash on the Pinebook Pro to manage U-Boot.

### Arch Linux ARM

{{< figure src="/documentation/images/Archlinux-logo.png" width="100" >}}

#### Official Installation

See [Installing Arch Linux ARM](/documentation/Pinebook_Pro/Software/Installing_Arch_Linux_ARM) for instructions on how to install the official Arch Linux ARM.

#### Customized Premade Root Filesystem

An Arch Linux ARM root filesystem customized for the Pinebook Pro using Manjaro’s kernel is available. Instructions are included for installation on microSD card, eMMC module and NVME SSD.

**Download location**

[Get the latest root filesystem from GitHub](https://github.com/SvenKiljan/archlinuxarm-pbp/releases/latest) (size: 500-600 MB).

**Installation**

Make sure to thoroughly read the [readme](https://github.com/SvenKiljan/archlinuxarm-pbp/blob/main/README.md), [installation instructions](https://github.com/SvenKiljan/archlinuxarm-pbp/blob/main/INSTALL.md) and [FAQ](https://github.com/SvenKiljan/archlinuxarm-pbp/blob/main/FAQ.md).

**Username and password**

The default Arch Linux ARM user credentials.

| Default credentials | |
| --- | --- |
| `alarm` | `alarm` |
| `root` | `root` |

### postmarketOS

{{< figure src="/documentation/images/PostmarketOS_logo.png" width="100" >}}

Official postmarketOS stable builds are available for the Pinebook Pro with the following interfaces:

* console
* GNOME
* KDE Plasma Desktop
* Phosh
* Sway

It boots from microSD card and from eMMC.

**Download location**

Get the stable image here: https://postmarketos.org/download/ (size: 103 MB to 775 MB)

The installer images allows setting up an encrypted installation on SD or eMMC.

**Username and password**

| Default credentials | |
| --- | --- |
| `user` | `147147` |

### Kali Linux

{{< figure src="/documentation/images/Kali-logo.png" width="100" >}}

Official pre-built OS images of Kali Linux for the Pinebook Pro featuring all tools you’d expect from the distribution. It boots from microSD card and from eMMC.

**Download location**

Get the latest image here: [Direct download latest images from Offensive Security’s website](https://www.offensive-security.com/kali-linux-arm-images/) (size: 2.0 GB)

**Username and password**

| Default credentials | |
| --- | --- |
| `kali` | `kali` |

### R-Cade

{{< figure src="/documentation/images/RCadeLogo.jpg" width="100" >}}

Retro Center’s R-Cade [USB / microSD / eMMC Boot]

* The 4K Media Center Arcade
* [RCade](https://www.retro-center.com/about-r-cade/) Features 100+ retro-gaming systems, a lightweight web browser, and full 4K UHD media playback
* DD image to USB, microSD, or eMMC and boot. Highly recommend using [Etcher](https://etcher.io/)
  * [Direct download from Retro Center’s GitHub](https://github.com/retro-center/rcade_releases/releases)

**Username and password**

| Default credentials | |
| --- | --- |
| `root` | `retro` |

### Q4OS

{{< figure src="/documentation/images/q4os.png" width="100" >}}

Q4OS is advertised as a 'fast and powerful operating system based on the latest technologies while offering highly productive desktop environment'. It boots from microSD card and from eMMC. To learn more please visit the [PINE64 forum](https://forum.pine64.org/showthread.php?tid=8385) or official [Q4OS website](https://q4os.org/index.html).

**Download location**

Get the latest image here: [Direct download latest release build from SourceForge](https://sourceforge.net/projects/q4os/files/stable/)

**Username and password**

User account and password are created on first run.

### DietPi

{{< figure src="/documentation/images/dietpi.png" width="100" >}}

DietPi is a lightweight, yet easy to setup and feature-rich Linux distribution, based on Debian. To find out more about DietPi, please visit the [official documentation](https://dietpi.com/docs/). Discuss the Pinebook Pro build on the [PINE64 forum thread](https://forum.pine64.org/showthread.php?tid=14061).

Download:

* [Direct download from dietpi.com](https://dietpi.com/downloads/images/DietPi_PinebookPro-ARMv8-Bookworm.img.xz)

| Default credentials | |
| --- | --- |
| `root` | `dietpi` |

### openSUSE

{{< figure src="/documentation/images/opensuse-distribution.png" width="100" >}}

**Download location**

Get the latest openSUSE Tumbleweed images for Pinebook Pro here: https://en.opensuse.org/HCL:Pinebook-Pro-RK3399. Credits to https://bugzilla.opensuse.org/show_bug.cgi?id=1194491.

* Step 1. Flash [Tow-Boot](https://github.com/Tow-Boot/Tow-Boot) to SPI
* Step 2. Flash openSUSE image to sd card & insert it
* Step 3. When it loads grub, press e and add the following line:

devicetree /boot/dtb/rockchip/rk3399-pinebook-pro.dtb

Press ctrl + x to boot

Works: display, WiFi
Not tested: bluetooth
Doesn’t work: audio

You may build rpms and see if it fix issues from this repository: https://github.com/bengtfredh/pinebook-pro-copr

Default password for root is "linux"

### FydeOS

An operating system based on the Chromium Project

https://fydeos.io/download/device/pinebook-pro

### Void Linux

{{< figure src="/documentation/images/void_bg.png" width="100" >}}

#### Images

[Void Linux](https://voidlinux.org/) packages U-Boot and a kernel for the Pinebook Pro, but does not distribute any images for the device.

Cameron Nemo (User:CameronNemo) distributes unofficial Void Linux images for the Pinebook Pro:

* [glibc download](https://repo.nohom.org/void/images/void-pinebookpro-20220530.img.xz)
* [musl download](https://repo.nohom.org/void/images/void-pinebookpro-musl-20220610.img.xz)

Some notes about the images:

* They were released on 2022-05-30 (glibc) and 2022-06-10 (musl)
* They ship U-Boot 2022.04 and Linux 5.15 (with minimal patches)
* Meant to be uncompressed then flashed to either an SD card or the internal eMMC module
* The root partition is ~1.7GB, and must be expanded manually
* There are very few services enabled on the images by default: udev and some getty’s

| Default credentials | |
| --- | --- |
| `root` | `voidlinux` |

#### Do It Yourself

{{< admonition type="warning" >}}
 This is not an official, nor supported way of using Void Linux on the Pinebook Pro.
{{< /admonition >}}

You can also manually install Void from a rootfs tarball: [see instructions here](/documentation/Pinebook_Pro/Software/Installing_Void_Linux_ARM).

## BSD

### NetBSD

{{< figure src="/documentation/images/netbsd.png" width="100" >}}

The image boots from microSD card and from eMMC. To learn more about NetBSD please visit [NetBSD main page](https://www.netbsd.org/)

**Download location**

Get the latest image here: [Direct download from NetBSD](http://www.armbsd.org/arm/)

**Installation**

Instructions concerning enabling SSH can be found [here](https://www.netbsd.org/docs/guide/en/chap-boot.html#chap-boot-ssh).

**Username and password**
| Default credentials | |
| --- | --- |
| `root` | none |

### OpenBSD

{{< figure src="/documentation/images/Puffy_mascot_openbsd.png" width="100" >}}

The image boots from microSD card and from eMMC. To learn more about OpenBSD, please visit [OpenBSD main page](https://www.openbsd.org/)

**Download location**

ARM64 images, (including support for Pinebook Pro), can be found here [OpenBSD arm64](https://www.openbsd.org/arm64.html)

## Linux Installer Releases

### Manjaro ARM

{{< figure src="/documentation/images/Manjaro-logo.svg" width="100" >}}

The [manjaro-arm-installer](https://gitlab.manjaro.org/manjaro-arm/applications/manjaro-arm-installer) script is intended to install Manjaro ARM directly to SD/eMMC cards without the need for images (including LXQT, Mate & CuboCore editions, as well as full disk encryption).

Running on a Linux x86 computer, it can install Manjaro ARM directly to an empty eMMC using an eMMC to USB adapter. The script can also be run from SD to install an image to the eMMC.

### Armbian

{{< figure src="/documentation/images/armbian.png" width="100" >}}

You can use the [Armbian Builder](https://github.com/armbian/build) to generate your own Armbian images of various types.

The builder supports building any version of Debian and any version of Ubuntu with various desktop options:

* Budgie
* Cinnamon
* Deepin
* Enlightenment
* Gnome
* I3-wm
* Kde-plasma
* Mate
* Xfce
* Xmonad

### Debian

{{< figure src="/documentation/images/Debian-logo.png" width="100" >}}

* Uses only the upstream kernel and firmware without special patches
* Display doesn’t always work properly on first boot of installer, usually fixed after a couple tries
* Requires adding the non-free component to your /etc/apt/sources.list file and installing the "firmware-linux" package for Wi-Fi and Bluetooth support. If your Pinebook Pro was part of the June/July 2022 batch, then you will need the "firmware-brcm80211" to accommodate the changed networking hardware. You will also need "brcmfmac43455-sdio.txt" in /lib/firmware/brcm, at least until it is included within firmware-brcm80211 upstream.
* Installer is loaded into RAM, can install onto the same media from which it’s booted
* Supports automatic partitioning and full disk encryption through LVM
* Installer currently doesn’t install a functional bootloader, leaving the installed system in an unbootable state until it’s manually added (if installed to eMMC, the system cannot be booted even to an SD card unless the eMMC is physically switched off or there is U-Boot in the SPI)

[The relevant files are built daily here](https://d-i.debian.org/daily-images/arm64/daily/netboot/SD-card-images/) and may sometimes be unavailable if the build system is having issues. The "README.concatenateable_images" file provides instructions on how to combine the partition.img.gz file with the firmware.pinebook-pro.rk3399.img.gz file in order to create a DD-able image.

The official images are **not** recommended yet until the display begins working consistently and the installer properly installs the bootloader. Building a Debian-based image via the Armbian builder on the other hand seems to work with no changes. Previously the best tool was [Daniel Thompson’s Debian Installer](/documentation/Pinebook_Pro/Software/Debian_installer), but unfortunately as of April 2023 some of the upstream kernel sources this tool used seem to no longer exist.

### Gentoo

{{< figure src="/documentation/images/GentooLogo.png" width="100" >}}

There is a script that prepares a Gentoo arm64 stage 3 tarball for the Pinebook Pro. Unfortunately, this script is not currently functional, and requires extensive troubleshooting to make work. New instructions are currently being created and will be available here.

**Word to the wise**

Currently, following the instructions on the Pinebook pro gentoo github page will **not** result in a functional system. Therefore it is neccesary to follow the instructions given here. Please bear in mind that the Pinebook pro’s six arm cores and 4gb of ram are extremely anemic. For example, emerging the package net-libs/webkit-gtk in order to build the minimalist web-browser "surf", a process which takes eighty minutes on an intel core i5-8250U with 8gb of ram, required eight hours of compile time, Basic installation alone can take 24 hours of compillation, dozens of reboots, and hours of troubleshooting. After that, even installing firefox would take 17 hours. Now that that’s out of the way, we may begin the installation.

**Preparing the bootloader**

Installing a functional bootloader can be difficult. Luckily, the tow-boot project provides a UEFI-like experience for some arm-based devices. Furthermore, it is not neccesary install this bootloader manually, as it will continue to be useable even after the disk has been reformatted, as long as the bootloader remains unscathed.

https://manjaro.org/downloads/arm/pinebook-pro/arm8-pinebook-pro-minimal/

No-matter where you intend to install gentoo, the bootloader should always be installed on the eMMC flash, although technically the SD card slot could also be used. Either way, install any of the official Manjaro arm disk images to the internal eMMC (there’s no reason not to use the minimal image, as you will not be using this OS for anything). You may use a second operating system installed on an SD-card, or the official Pine64 eMMC USB adapter. Boot into this operating system to ensure that the bootloader functions, but after that you have no further need of it.

Next, if you already have an OS on an SD card, you can use that for installing gentoo. If you don’t, you may be pleasantly suprised to find that tow-boot is cabable of booting from a USB drive. Therefore, you may install the same Manjaro image to your USB drive or SD card, and select it from the boot menu. You should now have an unused but bootable OS on the eMMC, and another bootable, usable OS on your external storage.

**Preparing the Disks**

Log into your host device as root with the following command:

`sudo su`

Enter your password.

Let the device on which you intend to install gentoo be refered to hereafter as /dev/<gentoo>. Use the following command to prepare this disk for installation:

`fdisk -B /dev/<gentoo>`

{{< admonition type="note" >}}
Don’t just copy these commands! You should substitute <gentoo> for mmcblk2 for the internal eMMC flash storage.
{{< /admonition >}}

Note that the first block of the boot partition is block 62500. Delete all partitions, but **do not** re-format the disk. Create a new boot partition starting at 62500, and as it’s size select "+1GB". Create a new swap partition. fdisk will try to start it at the beginning of the volume (before the boot partition) Instead, when it prompts you for the starting position, enter in the end sector of the boot partition. It should then tell you that this is within an existing partition, and recommend a slightly higher value. Press enter, and give for the size of the partition any value greater than "+4gb". You need this much ram to be able to suspend your system, and emerge large packages. Don’t be stingey - you still have SD cards. I reccomend "+8gb".

Finally, add a root partition starting at the end sector of the swap partition, and use the rest of the disk for it. That should be 50-60 GB depending on the size of your swap and boot partitions.

Lastly, press "t" to set the type of each partition. You may set partition 1 to type 6, 2 to type 82, and 3 to type 83.

to set the partition types of the three partitions.

`lsblk`

to remind yourself which disk is /dev/<gentoo>
Write the filesystems to these three partitions with the commands:

```
mkfs.vfat /dev/<gentoo>p1

mkswap /dev/<gentoo>p2

mkfs.ext4 /dev/<gentoo>p3
```

This may be a slightly different format if you’re installing to an USB stick.

**Installation**

make the directory for mounting the filesystem you just created. These should be made on the external OS.

```
mkdir /mnt/gentoo

mount /dev/<gentoo>p3 /mnt/gentoo
```

cd into this directory and fire up links. Navigate to gentoo.org/downloads and select the stage 3 minimal stage 3 tarball. Download it to your current directory, or move it to that directory from wherever it has been downloaded to. Once you are in the correct directory, unpack the tarball.

`tar xpvf stage3-arm64-<blah blah blah>`

Mount the boot partition.

`mount /dev/<gentoo>p1 /mnt/gentoo/boot`

Chroot into the mounted directory and Install the operating system as per the AMD64 manual [https://wiki.gentoo.org/wiki/Handbook:AMD64]. Before you emerge anything, however, be sure to set your use flags as follows:

```
nano /etc/portage/make.conf

MAKEOPTS="-j4 -l4"

ACCEPT_KEYWORDS="* **"

ACCEPT_LICENSE="*"

USE="X gtk bluetooth pulseaudio"
```

You can use your own options instead of these if you know what you’re doing. It’s not super difficult.

Continue installing the operating system, but stop just before emerging the @world set. I don’t know if this is necessary, but I haven’t had the time to try without doing this. Clone Janikk2099’s github repo. It doesn’t matter where, and run the script. If it fails run it a couple more times.

`git clone https://github.com/Jannik2099/gentoo-pinebookpro

Don’t follow any of Janikk’s other instructions. They appear to be out of date (no offense bro). Let me be clear: DO NOT INSTALL U-BOOT. I don’t know what will happen, but it won’t be an improvement over the existing boot-loader so don’t worry about it.

Finish installing your system until you come to the kernel.

**Custom Kernel**

Use sys-kernel/gentoo-kernel-bin as your kernel. You will need to manually edit the kernel configuration. First, select it as your kernel.

`eselect kernel list`

This should list only one option. Otherwise, select the number matching `linux-5.<whatever is latest>-gentoo-dist`, and cd into the kernel source directory.

```
eselect kernel set <number>

cd /usr/src/linux
```

Begin the kernel configuration

`make menuconfig`

At this point, you’re almost on your own. I don’t know a strict cause-and-effect relationship between my kernel config and the behavior of my system. For starters, just go into platform selection and deselect everything except rockchip platforms. Once you’re done save your configuration and exit. Make sure boot is mounted, and your fstab is set up with your swap mounted. Make sure dracut is installed.

```
make

make modules

make dtbs

make install

make modules install

make dtbs_install

ls /lib/modules

dracut -f --kver <name of directory in /lib/modules matching your kernel, **not** the kernel name from eselect>
```

emerge the package extlinux and run `u-boot-update`. Open the extlinux configuration file.

`nano /boot/extlinux/extlinux.conf`

And configure it as follows:

```
LABEL <label of your choice, for example GENTOO ARM>

KERNEL /<name of your vmlinuz kernel image. Include the slash, but be relative to boot, not root.>

FDT /dtbs/<kernel-version>/rockchip/rk3399-pinebook-pro.dtb

APPEND initrd=/<name of initramfs image> root=PARTUUID-<nboot partition’s PARTUUID, no quotes> rw rootwait
```

You can use the blkid command to find the PARTUUID of every partition on the machine. None of this configuration is guaranteed to work, but it worked for me, and given enough fiddling you can get it to work as well.

Now you should reboot the machine and see if it boots into gentoo. If it does: congratulations|If not, too bad. Try again.

### Kali Linux

{{< figure src="/documentation/images/Kali-logo.png" width="100" >}}

There is a script to create official Kali Linux OS images for the Pinebook Pro. The script carries out the build process in entirety and is Pinebook Pro specific.

**Installation**

* Please pull the latest [Kali Linux install script](https://gitlab.com/kalilinux/build-scripts/kali-arm/blob/master/pinebook-pro.sh) from the project’s GitLab.
* For more information regarding building the OS image please read the README instruction at https://gitlab.com/kalilinux/build-scripts/kali-arm/blob/master/README.md

### NixOS

{{< figure src="/documentation/images/NixOS.webp" width="100" >}}

You can follow the ongoing discussion about NixOS on the [PINE64 forum](https://forum.pine64.org/showthread.php?tid=10524). There is a good chance we will see Tier 1 support for aarch64, including the Pinebook Pro, in 2021 (see https://github.com/NixOS/rfcs/pull/87).

**Installation**

* This is instructions to install NixOS on the Pinebook Pro: https://wiki.nixos.org/wiki/NixOS_on_ARM/PINE64_Pinebook_Pro
* Please pull the latest [samueldr’s repository ](https://github.com/samueldr/wip-pinebook-pro) from the project’s GitHub.

### SkiffOS

{{< figure src="/documentation/images/SkiffOS-Icon-1.png" width="100" >}}

**Installation**

* Instructions to build/install on the Pinebook Pro: https://github.com/skiffos/SkiffOS/tree/master/configs/pine64/book
* Please pull the latest version from the project’s GitHub.
* Compiling the boot image takes approximately 30 minutes.
* Easily configure the kernel, compiler, etc with Buildroot.
* Pre-built ISOs will be available with the upcoming 2021.02 release.

### Slackware

{{< figure src="/documentation/images/slackware.jpg" width="100" >}}

[Slackware](https://arm.slackware.com/) is the world’s oldest actively developed Linux distribution, providing a modern user land (applications) and Linux Kernel, within a more classic Unix Operating System environment.

More information can be found about Slackware in this [20 minute video](https://www.youtube.com/watch?v=A5PFYUttsWA&list=PL1XOSJnvang3IbwySOf6m3PK1gm13hS5s).

[Installation instructions](https://docs.slackware.com/slackwarearm:inst).

[Installation guide video](https://www.youtube.com/watch?v=QKs_RnFqLO8&list=PL1XOSJnvang3VLmqke2QbRitKtOD6Rm3t)

### Ubuntu

If you install Tow-Boot to the SPI, you may then be able to use generic arm64 install disks, such as those for Ubuntu. This is because Tow-Boot can use UEFI boot partitions. The arm64 builds of the Ubuntu installer "ISOs" can be [found here](http://cdimage.ubuntu.com/ubuntu/releases/22.04/release/). These can then be converted to UEFI bootable USB drives using a tool such as unetbootin or the Ubuntu "Startup Disk Creator".

Ubuntu 22.04 does install and boot on a Pinebook Pro, however the speakers and wifi are non-functional. A USB wifi adapter can get you online.

Upgrading such an install to 22.10 fixes the wifi. The graphics are broken in an odd way on first boot, but then functional after that. The speakers are still non-functional.

A fresh install of 22.10 would presumably produce a similar result.
