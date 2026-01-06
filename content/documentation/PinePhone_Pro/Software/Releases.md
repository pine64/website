---
title: "Releases"
draft: false
toc: true
toc_depth: 1
menu:
  docs:
    title:
    parent: "PinePhone_Pro/Software"
    identifier: "PinePhone_Pro/Software/Releases"
    weight: 3
aliases:
  - /wiki/PinePhone_Pro_Software_Releases
---

This page contains a list of all available releases and tools for the [PinePhone Pro](/documentation/PinePhone_Pro).

## Factory builds

These are two operating system builds that was preloaded in the factory with testing utility.

Download the build, extract the image and dd it to a 8 GB or larger microSD card, then insert it into the PinePhonePro. Press "RE" button for two seconds when power up, follows on screen instruction and apply the build from microSD card to eMMC. 

| Distribution | Download Link | File Size | MD5 |
| --- | --- | --- | --- |
| Sailfish with RK2AW | [ppp-factory-image-20231118.img.gz](https://files.pine64.org/os/PinePhonePro/ppp-factory-image-20231118.img.gz) | 447MB | _4e31e0a6b0999e3e3df45f86a7dc9c33_ |
| Manjaro with Tow-Boot | [Manjaro-ARM-plasma-mobile-pinephonepro-factory-20211212.img.xz](https://files.pine64.org/os/PinePhonePro/Manjaro-ARM-plasma-mobile-pinephonepro-factory-20211212.img.xz) | 1.37GB | _b82ba02287c1699b14fed403ce485b44_ |

## Arch Linux ARM

{{< figure src="/documentation/images/Archlinux-logo.png" width="100" >}}

(Unofficial) Arch Linux ARM with choice of Phosh UI, Plasma Mobile, sxmo or barebones.
Currently being maintained by the [DanctNIX](https://danctnix.org/) community (GitHub: [danctnix](https://github.com/DanctNIX/danctnix), [dreemurrs-embedded](https://github.com/dreemurrs-embedded)).

### Download

Get both stable and test builds at [GitHub releases](https://github.com/dreemurrs-embedded/Pine64-Arch/releases).

| Default credentials | |
| -------- | ------- |
| `alarm` | `123456` |
| `root` (barebone only) | `root` |

### Notes

The GitHub page can be found here: [dreemurrs-embedded/Pine64-Arch](https://github.com/dreemurrs-embedded/Pine64-Arch/)

A re-image of the above Arch image providing a Btrfs root partitioning has been [made by user kaida](https://github.com/K-arch27/pinebtrfs/).

## Gentoo

{{< figure src="/documentation/images/GentooLogo.png" width="100" >}}

There are unofficial Gentoo overlays with ebuilds for the PinePhone Pro. There are no images - the image must be built manually, including picking the kernel, bootloader and the desired desktop environment. The ARM64 version of Gentoo has to be selected. The PinePhone Pro will not boot with P-Boot but will boot with U-Boot, there is an ebuild for it.

### Download

The overlay can be found under https://github.com/stealthgun/gjdwebserver-overlay

### Notes

See https://stealthgun.tweakblogs.net/blog/19830/gentoo-on-a-pinephone-pro for the documentation.

{{< admonition type="note" >}}
 Please consider cross-compiling the software on the computer. Long compilation times and heat production can lead to a reduced lifespan of the phone.
{{</ admonition >}}

## GloDroid

A fully open-source port of Android and LineageOS to the PinePhone Pro.

GitHub: [GloDroid](https://github.com/GloDroidCommunity/pine64-pinephonepro)

### Download

* Releases: [GloDroid](https://github.com/GloDroidCommunity/pine64-pinephonepro/releases)

### Notes

Project status [link](https://github.com/GloDroidCommunity/pine64-pinephonepro/issues/1)

## LuneOS

{{< figure src="/documentation/images/Luneos-logo-256.png" width="100" >}}

LuneOS is one of the original multi-tasking OS-es that runs on Linux. Based on HP/Palm’s webOS, merged with latest technology stack from LG called webOS OSE (a derivative of what LG uses on their Smart TV’s), software such as Qt5 and makes use of the Yocto build system.

### Download

* LuneOS (Initial preview): [Downloads](https://github.com/webOS-ports/meta-pine64-luneos/releases)

| Default credentials | |
| -------- | ------- |
| `root` | |

### Notes

In order to connect to the device using SSH/SCP via WiFi: You can simply connect via SSH/SCP via WiFi using the PinePhonePro’s IP address on port 22.

## Manjaro ARM

{{< figure src="/documentation/images/Manjaro-logo.svg" width="100" >}}

Manjaro is a user-friendly Linux distribution based on the independently developed Arch operating system with the Plasma Mobile and Phosh desktop environment.

### Download

* Phosh: [Dev](https://github.com/manjaro-pinephone/phosh-dev/releases) and [Stable](https://github.com/manjaro-pinephone/phosh/releases) (recommended)
* Plasma Mobile: [Dev](https://github.com/manjaro-pinephone/plasma-mobile-dev/releases) and [Stable](https://github.com/manjaro-pinephone/plasma-mobile/releases) (recommended)

| Default credentials | |
| -------- | ------- |
| `manjaro` | `123456` |
| `root` | `root` |

## Mobian

{{< figure src="/documentation/images/Mobian-logo.png" width="100" >}}

A [Mobian](https://www.mobian.org) build for ARM64 running with Phosh. The current version of the base Debian system is Debian Bookworm. See the installation instructions [here](https://wiki.debian.org/InstallingDebianOn/PINE64/PinePhonePro). If you have questions about Mobian, please ask them in the [Mobian Matrix room](https://matrix.to/#/#mobian:matrix.org).

### Download

[Images](https://images.mobian.org/pinephonepro/)

{{< admonition type="note" >}}
 Tow-Boot required to be able to boot the images, see [here](https://tow-boot.org/devices/pine64-pinephonePro.html)!
{{</ admonition >}}

| Default credentials | |
| -------- | ------- |
| `mobian` | `1234` |

### Notes

The development is work in progress. The Mobian wiki can be found [here](https://wiki.mobian-project.org/).

In order to connect to the device using SSH/SCP via WiFi, you need to install SSH on the device. You can do this by executing the following in a shell: "sudo apt-get install ssh", afterwards you can connect via SSH/SCP via WiFi using the PinePhonePro’s IP address on port 22.

## Kali Linux

{{< figure src="/documentation/images/Kali-logo.png" width="200" >}}

The official Kali Nethunter images for PinePhone and PinePhone Pro have been released now. Get [Nethunter App](https://github.com/Shubhamvis98/nethunter-pinephone) for your PinePhone’s Kali Linux.

### Download

* [Kali Phosh Unofficial](https://github.com/Shubhamvis98/kali-pinephone/releases)
* [Kali Nethunter Pro Official](https://www.kali.org/get-kali/#kali-mobile)

| Default user for Unofficial Releases | |
| -------- | ------- |
| `kali` | `8888` |

| Default user for Nethunter Releases | |
| -------- | ------- |
| `kali` | `1234` |

## Nemo Mobile

{{< figure src="/documentation/images/nemo_mobile.png" width="100" >}}

Nemo Mobile is the open source build of Sailfish OS with a open source UI called [Glacier](http://nemomobile.net/glacier-home/), [based on Manjaro](http://nemomobile.net/pages/Hello_manjaro/).

### Download

[Image](https://img.nemomobile.net/2024.10/Manjaro-ARM-nemomobile-pinephonepro-24.10.img.xz)

| Default credentials | |
| -------- | ------- |
| `manjaro` | `123456` |
| `root` | `root` |

### Notes

The website of the Nemo Mobile UX Team can be found [here](https://nemomobile.net/). Please report bugs regarding the Nemo Mobile UI as [GitHub issue](https://github.com/nemomobile-ux/main/issues).

## NixOS

{{< figure src="/documentation/images/NixOS.webp" width="100" >}}

NixOS is a Linux distribution built on top of the Nix package manager using declarative configuration to allow reliable system upgrades.

### Download

Not available yet.

### Notes

WIP. See https://github.com/NixOS/mobile-nixos/issues/440

## postmarketOS

{{< figure src="/documentation/images/PostmarketOS_logo.png" width="100" >}}

postmarketOS extends [Alpine Linux](https://www.alpinelinux.org/) to run on smartphones and other mobile devices.
It offers various user interfaces (Phosh, Plasma Mobile, Sxmo, Plasma Desktop, Gnome 3, Kodi, XFCE4, [...]).

### Download

[Download page](https://postmarketos.org/download/)

Note that images for the PinePhone Pro are in the "community" category of devices indicating some features may not work. You can also build your own image using [pmbootstrap](https://wiki.postmarketos.org/wiki/Installation_guide)

| Default credentials | |
| -------- | ------- |
| `user` | `147147` |

### Notes

See the [pine64-pinephonepro](https://wiki.postmarketos.org/wiki/PINE64_PinePhone_Pro_(pine64-pinephonepro)) page of the postmarketOS wiki for details.

## Rhino Linux

Rhino Linux is an Ubuntu-based distribution that uses the rolling-release model by tracking the `devel` branch of repositories. The port is currently maintained by Oren Klopfer (oklopfer).

Tow-Boot is required for installing Rhino Linux. Instructions for installing Tow-Boot to the PinePhone Pro can be found [here](https://tow-boot.org/devices/pine64-pinephonePro.html). After Tow-Boot has been installed to your device, Rhino Linux installation just requires flashing the `.img.xz` to an SD or the eMMC.
	
### Download
	
* [Rhino Linux Downloads](https://rhinolinux.org/download.html) (select Pine64 on the dropdown)
	
| Default credentials | |
| -------- | ------- |
| `rhino` | `1234` |
	
### Notes
	
Foundational to the distribution is [Pacstall](https://pacstall.dev), a Debian-based user repository inspired by the AUR. Additionally, RL comes with [Unicorn](https://rhinolinux.org/unicorn/), a custom modified version of XFCE with various modernizations and improvements, including auto-rotation for mobile devices.
	
[Discord](https://discord.gg/reSvc8Ztk3) - [Matrix](https://matrix.to/#/#rolling-rhino-remix:matrix.org) - [GitHub](https://github.com/rhino-linux) - [Wiki](https://rhinolinux.org/wiki.html)
	
## Ubuntu Touch

A Mobile Version of the Ubuntu Operating System made and maintained by the UBports Community. The port is currently maintained by Oren Klopfer (oklopfer).
	
Tow-Boot is required for installing the latest version of Ubuntu Touch (20.04) to the PinePhone Pro. Instructions for installing Tow-Boot to the PinePhone Pro can be found [here](https://tow-boot.org/devices/pine64-pinephonePro.html).
	
Installation instructions can be found at
	
[this UBports post](https://ubports.com/en/blog/ubports-news-1/post/pinephone-and-pinephone-pro-3889). After Tow-Boot has been installed to your device, Ubuntu Touch installation just requires flashing the _.img.xz_ to an SD or the eMMC.
	
### Download
	
* [UBports 20.04 PinePhone Pro Latest Releases](https://gitlab.com/ook37/pinephone-pro-debos/-/releases)
* [UBports PinePhone Pro Device Info](https://devices.ubuntu-touch.io/device/pinephone-pro/release/focal)
	
| Default credentials | |
| -------- | ------- |
| Regular user | Set during boot |
| `phablet` (root) | `1234` |

### Notes
	
Scroll down to the middle of [the GitLab project page](https://gitlab.com/ook37/pinephone-pro-debos/), or directly here [at the UBports website](https://devices.ubuntu-touch.io/device/pinephone-pro/release/focal/#deviceOverview) to see which features work.
	
Contributions and bug reports can be made at the [UBports PinePhone Pro GitLab page](https://gitlab.com/ook37/pinephone-pro-debos/). See [UBports website](https://ubports.com/foundation/sponsors) for how to donate.

## Multi-distribution image

{{< admonition type="warning" >}}
 Work in progress; updating the distributions via their respective package managers may break the system.
{{</ admonition >}}

A PinePhone Pro analogue of the [PinePhone multi-distro demo image](/documentation/PinePhone/Software/#multi_distro_demo_image). This image allows the user to switch between multiple Linux distributions without having to swap microSD cards.

### Download

Clone [this git repository](https://github.com/Pavlos1/ppp-multi-image) and follow the instructions in the README to create a bootable microSD card.

### Notes

The shell script in the repository above was derived from [these instructions](/documentation/PinePhone_Pro/Software/Multi-distribution_image/).

## Various DPA Images

Multiple versions of unofficial images of various Debian-based distributions by the user DPA. They also contain some of DPA’s own software.

### Download

The latest successful image builds can be found here: https://repo.dpa.li/apt/dpa-image-builder/images/?board=pinephone-pro

### Notes

Most of these images are still in development / incomplete and DPA doesn’t have time to test them all, but they can still be useful as a starting point to get distributions running for which no other images have been created yet. DPA made these images because they wanted to run their favorite distribution, Devuan, on their phone.

The build scripts can be found in various places: [GitLab](https://gitlab.com/DanielAbrecht/dpa-image-builder), [my server](https://projects.dpa.li/git/?p=dpa-image-builder.git;a=summary), [GitHub](https://github.com/Daniel-Abrecht/dpa-image-builder)

In theory, these build scripts can create images for any Debian-based distribution which supports ARM64 and can be bootstrapped using _debootstrap_.
