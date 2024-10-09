---
title: "Building U-Boot"
draft: false
menu:
  docs:
    title:
    parent: "Quartz64/Software"
    identifier: "Quartz64/Software/Building_U-Boot"
    weight: 
---

This article guides you through compiling U-Boot for a ***Quartz64*** and ***SOQuartz*** device.

## Prerequisites

You will need either an x86 machine with an aarch64 cross-compiler installed, or an existing aarch64 system. You will also need the device tree compiler dtc, python3 (including setuptools and pyelftools), swig, GNU make and git.

### Arch Linux

On an x86_64 Arch Linux system, you can install the required dependencies with:

    pacman -S --needed base-devel aarch64-linux-gnu-gcc aarch64-linux-gnu-binutils git dtc python-setuptools swig python-pyelftools

### Debian

On an x86_64 Debian (or derivates such as Ubuntu) system, you can install the required dependencies with:

    apt install device-tree-compiler build-essential gcc-aarch64-linux-gnu binutils-aarch64-linux-gnu make python3 python3-dev libssl-dev python3-pyelftools python3-setuptools swig git

## Fetching the repositories

Use git to clone the mainline U-Boot repository into the directory _u-boot_:

    git clone https://source.denx.de/u-boot/u-boot.git

You can use `git checkout _tagname_` inside the _u-boot_ directory to check out a specific git tag (release), you can list all of them with `git tag -l` (but do keep in mind we only have device support since v2023.10).

Then, also use git to clone the rockchip firmware binaries repository into the directory _rkbin_:

    git clone https://github.com/rockchip-linux/rkbin.git

## Setting up your environment

Next, we need to set two environment variables: `ROCKCHIP_TPL` for the DRAM init binary, and `BL31` for the ARM Trusted Firmware binary.

    cd u-boot
    export ROCKCHIP_TPL="$(ls ../rkbin/bin/rk35/rk3566_ddr_1056MHz_v*.bin | sort | tail -n1)"
    export BL31="$(ls ../rkbin/bin/rk35/rk3568_bl31_v*.elf | sort | tail -n1)"

## Configuring U-Boot

First, we need to use the right default config for our device. Please choose _defconfig_ from the following table depending on your device:

| Board | defconfig |
| --- | --- |
| Quartz64 Model A | `quartz64-a-rk3566_defconfig` |
| Quartz64 Model B | `quartz64-b-rk3566_defconfig` |
| SOQuartz on Model A | `soquartz-model-a-rk3566_defconfig` |
| SOQuartz on Blade | `soquartz-blade-rk3566_defconfig` |
| SOQuartz on CM4 I/O Board | `soquartz-cm4-rk3566_defconfig` |

In the _u-boot_ directory with your environment variables set, run:

```
make CROSS_COMPILE=aarch64-linux-gnu- _defconfig_
```

with _defconfig_ being the value from the previous table.

## Building U-Boot

In the _u-boot_ directory, after configuring, and with your environment variables set, run:

    make CROSS_COMPILE=aarch64-linux-gnu- -j$(nproc)

This will output a _u-boot-rockchip.bin_, which is your freshly built SPL+U-Boot combined image.
