---
title: "Operating systems"
draft: false
menu:
  docs:
    title:
    parent: "PineTab"
    identifier: "PineTab/Operating_systems"
    weight: 1
---

The PineTab will automatically boot from microSD if a bootable card is inserted. Although it is technically possible to use any ARM distro (because the PineTab uses the mainline kernel), only few of them will actually be usable on Early Adopters PineTab, due to specifics of working with LCD panel. Among those listed all except for postmarketOS have working builds.

## Arch Linux ARM

{{< figure src="/documentation/images/Archlinux-logo.png" width="100" >}}

Unofficial **Arch Linux ARM** with Phosh as the UI selection, maintained by the DanctNIX community.

Download:

* The latest image can be downloaded [here](https://github.com/dreemurrs-embedded/Pine64-Arch/releases)

## Manjaro ARM

{{< figure src="/documentation/images/Manjaro-logo.svg" width="100" >}}

**Manjaro** is a Linux based alternative operating system with no adverts or licensing fees, it respects user privacy and gives them full control over their hardware. The PineTab "Early Adopter" edition is currently the only device supported by Manjaro ARM.

Download:

* Images with several different environments, including Phosh and Plasma, are available for the "Dev" pre-release can be downloaded [here](https://osdn.net/projects/manjaro-arm/storage/pinetab/)
* Images for the Early Adopter version can be downloaded [here](https://github.com/manjaro-arm/pinetab-images/releases).

Both Beta releases and weekly unstable builds for Phosh and Plasma Mobile can be found there.

## Mobian

{{< figure src="/documentation/images/Mobian-logo.png" width="100" >}}

A [Mobian](https://www.mobian.org) build for ARM64 running with Phosh. The current version of the base Debian system is Debian Bookworm. See the installation instructions [here](https://wiki.debian.org/InstallingDebianOn/PINE64/PineTab). If you have questions about Mobian, please ask them in the [Mobian Matrix room](https://matrix.to/#/#mobian:matrix.org).

Download:

* PineTab images can be downloaded [here](https://images.mobian.org/pinetab/). The password is **1234**

| Default credentials | |
| -------- | ------- |
| Default user | `mobian/1234` |

## postmarketOS

{{< figure src="/documentation/images/PostmarketOS_logo.png" width="100" >}}

**postmarketOS** extends [Alpine Linux](https://www.alpinelinux.org/) to run on smartphones and other mobile devices.

It offers various user interfaces (Phosh, Plasma Mobile, Sxmo, Plasma Desktop, Gnome 3, Kodi, XFCE4 and more). As of writing, official images are provided with Phosh and Plasma Mobile. The official images come in two flavors, either as demo image to try out postmarketOS, or with the installer.

When using the installer images (recommended), it is possible to:

* encrypt your installation
* install from the SD card to eMMC

Getting postmarketOS for the PineTab:

* [Download page](https://postmarketos.org/download/)
* [Flashing instructions](https://wiki.postmarketos.org/wiki/PINE64_PineTab_(pine64-pinetab)#Installation)
* Power users may also create their own image with the distribution’s install and development tool _pmbootstrap_

## Rhino Linux

{{< figure src="/documentation/images/Rhino-linux-logo.png" width="100" >}}

**Rhino Linux** is an Ubuntu-based distribution that uses the rolling-release model by tracking the `devel` branch of repositories. The port is currently maintained by Oren Klopfer (oklopfer).

The bootloader (U-Boot) comes pre-flashed in the port. Installation just requires flashing the `.img.xz` to an SD or the eMMC.

Download:

[Rhino Linux Downloads](https://rhinolinux.org/download.html) (select Pine64 on the dropdown)

| Default credentials | |
| -------- | ------- |
| Default user | `rhino/1234` |

Notes:

Foundational to the distribution is [Pacstall](https://pacstall.dev), a Debian-based user repository inspired by the AUR. Additionally, RL comes with [Unicorn](https://rhinolinux.org/unicorn/), a custom modified version of XFCE with various modernizations and improvements, including auto-rotation for mobile devices.

[Discord](https://discord.gg/reSvc8Ztk3) - [Matrix](https://matrix.to/#/#rolling-rhino-remix:matrix.org) - [GitHub](https://github.com/rhino-linux) - [Wiki](https://rhinolinux.org/wiki.html)

## Sailfish OS

{{< figure src="/documentation/images/SailfishOS_logo.png" width="100" >}}

You can get **SailfishOS** on your with the flash-it script, which will write an image on a SD card. https://github.com/sailfish-on-dontbeevil/flash-it

There is a forum discussion with further information.

https://forum.pine64.org/showthread.php?tid=11850

Many things are still broken but Bluetooth, Audio, Rotation and Keyboard are working.

## Ubuntu Touch

{{< figure src="/documentation/images/Ubports-logo.png" width="100" >}}

**Ubuntu Touch** is a mobile version of the Ubuntu distribution made and maintained by the UBports community. The port is currently maintained by Oren Klopfer (oklopfer).

The bootloader (U-Boot) comes pre-flashed in the port. Installation just requires flashing the the `.img.xz` file to an SD or the eMMC.

Download:

[UBports 20.04 PineTab Latest Releases](https://gitlab.com/ook37/pinephone-pro-debos/-/releases)
[UBports PineTab Device Info](https://devices.ubuntu-touch.io/device/pinetab/release/focal)

| Default credentials | |
| -------- | ------- |
| Default user  | Set during boot |
| root | `phablet/1234` |

Notes:

Scroll down to the middle of [the GitLab project page](https://gitlab.com/ook37/pinephone-pro-debos/), or directly here [at the UBports website](https://devices.ubuntu-touch.io/device/pinetab/release/focal/#deviceOverview) to see which features work.

Contributions and bug reports can be made at the [UBports PineTab GitLab page](https://gitlab.com/ook37/pinephone-pro-debos/). See [UBports website](https://ubports.com/foundation/sponsors) for how to donate.
