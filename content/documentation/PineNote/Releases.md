---
title: "Releases"
draft: false
menu:
  docs:
    title:
    parent: "PineNote"
    identifier: "PineNote/Releases"
    weight: 4
---

This page contains a list of all available operating systems for the [PineNote](/documentation/PineNote) in alphabetical order.

## Alpine

See https://github.com/DorianRudolph/pinenotes#alpine

## Arch Linux

See https://github.com/DorianRudolph/pinenotes#arch-linux

## Debian

* A full GNOME-enabled rootfs/disc image is provided under [m-weigand/pinenote-debian-recipes/releases](https://github.com/m-weigand/pinenote-debian-recipes/releases). This image can be flashed using rkdeveloptool.

{{< admonition type="note" >}}
 Check the [dev](https://github.com/m-weigand/pinenote-debian-recipes/tree/dev) branch and github actions artifacts (possibly requires github login) for builds newer than the latest release.
{{< /admonition >}}

* A Debian-based minimalistic rootfs/disc image can be built using `debos` using the work from  [Eugen Răhăian](https://salsa.debian.org/eugenrh). The GNOME image above is building on this work.

## postmarketOS

See https://wiki.postmarketos.org/wiki/PINE64_PineNote_(pine64-pinenote)


## Development

{{< admonition type="warning" >}}
The following releases are targeted towards experienced developers.
{{< /admonition >}}

### Linux Kernel

* [RK3566 EBC Reverse-Engineering](/documentation/General/RK3566_EBC_reverse-engineering) for the EBC (eInk Panel) driver.
* [PineNote Development/Building Kernel](/documentation/PineNote/Development/Building_kernel)
* BSP Linux SDK version 4.19 for the PineNote and [Quartz64 Model A](/documentation/Quartz64):
  * [Direct download](https://files.pine64.org/SDK/Quartz64/QUARTZ64-model-A_BSP%20Linux.tar.gz) from _pine64.org_ (32.67GB, MD5 of the TAR-GZip file _24554419aec29700add97167a3a4c9ed_)
  * [Mirror by mwfc](https://tmp.mwfc.info/pinenote/QUARTZ64-model-A_BSP%20Linux.tar.gz)
  * An unofficial torrent download provided by a community member of the BSP Linux and Android SDKs can be found [here](https://cdn.discordapp.com/attachments/870707390998282292/907726420204208148/pinenote.torrent) (100GB).

### Android

Android 11 e-ink SDK for the PineNote and Quartz64 Model A. This is the Android SDK build for 10.3" eink panels on Quartz64 Model A.

Download:

* [Direct download](https://files.pine64.org/SDK/Quartz64/QUARTZ64-model-A_eink.android11_SDK.tar.gz) from _pine64.org_ (72.88GB, MD5 of the TAR-GZip file _293a550584298de4fb95ceae18103672_)
* [Mirror by mwfc](https://tmp.mwfc.info/pinenote/QUARTZ64-model-A_eink.android11_SDK.tar.gz)
* An unofficial torrent download provided by a community member of the BSP Linux and Android SDKs can be found [here](https://cdn.discordapp.com/attachments/870707390998282292/907726420204208148/pinenote.torrent) (100GB).
* Just the boot blobs (<1MB): https://wiki.pine64.org/wiki/File:Rk35-blobs.tar.gz

Notes:

* View [Android SDK for RK3566](/documentation/General/Android_SDK_for_RK3566) for more information how to compile an image for the PineNote using this SDK