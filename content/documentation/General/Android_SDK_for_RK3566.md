---
title: "Android SDK for RK3566"
draft: false
menu:
  docs:
    title:
    parent: "General"
    identifier: "General/Android_SDK_for_RK3566"
    weight: 
---

Two Android SDKs are available from Pine64 for RK3566 devices:

## QUARTZ64_SDK_android11

### Android 11 SDK

For Quartz64 model A SBC and SOQuartz

* [Direct Download from pine64.org](http://files.pine64.org/SDK/Quartz64/QUARTZ64_SDK_android11.tar.gz)
  * MD5 (TAR-GZip file): 77c2ff57ea3372fb04da7fb49e17d12b
  * File Size: 79.00GB
  * Just the boot blobs (&lt;1MB): https://wiki.pine64.org/wiki/File:Rk35-blobs.tar.gz
  * Android build version:

## QUARTZ64-model-A_eink.android11_SDK

### Android 11 eink SDK

For PineNote and Quart64 model A SBC

* [Direct Download from pine64.org](http://files.pine64.org/SDK/Quartz64/QUARTZ64-model-A_eink.android11_SDK.tar.gz)
  * MD5 (TAR-GZip file): 293a550584298de4fb95ceae18103672
  * File Size: 72.88GB
  * Just the boot blobs (&lt;1MB): https://wiki.pine64.org/wiki/File:Rk35-blobs.tar.gz
  * Android build version:

## Compiling

### Build machine

* 64 bit Linux (Manjaro tested)
* At least 16G RAM
* At least 250G free storage, preferably SSD based
* Use a POSIX compliant shell such as bash, not zsh (in Manjaro "chsh -s /bin/bash username")

#### Manjaro packages

The following packages are needed (install with "sudo pacman -S packagename"):-

* make
* gcc
* python-pip
* dtc
* bison
* flex
* cpio
* unzip
* zip

Once this is done run

* pip install pyelftools
  * sudo isn’t needed

You will also need libncurses.so.5. The easiest way to install this appears to be using an Arch AUR package.

* Enable AUR
* pamac install ncurses5-compat-libs
  * don’t use sudo

### Patches

#### QUARTZ64-model-A_eink.android11_SDK

For QUARTZ64-model-A_eink.android11_SDK the following files will need to be updated:-

* rk3566_ebook/u-boot/arch/arm/mach-rockchip/decode_bl31.py                                                                                 
* rk3566_ebook/u-boot/arch/arm/dts/Makefile
* rk3566_ebook/u-boot/scripts/dtc/dtc-lexer.l
* rk3566_ebook/u-boot/scripts/dtc/dtc-lexer.lex.c
* rk3566_ebook/u-boot/scripts/dtc/dtc-lexer.lex.c_shipped
* Download link [QUARTZ64-model-A_eink.android11_SDK.patches.04112021.tar](https://wiki.pine64.org/images/c/ca/QUARTZ64-model-A_eink.android11_SDK.patches.04112021.tar)
* Only the PineNote target has been tested at this time.

### Compilation process

* cd rk3566 (for non eink)
* cd rk3566_ebook (for eink)
* source build/envsetup.sh
* lunch
* ./build.sh -UCKAu
