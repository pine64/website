---
title: "Software"
draft: false
menu:
  docs:
    title:
    parent: "STAR64"
    identifier: "STAR64/Software"
    weight: 1
---

The releases are still in **alpha** state and are only fit for testing purposes.

## Apache NuttX RTOS

[Apache NuttX RTOS](https://www.hackster.io/lupyuen/rtos-on-a-risc-v-sbc-star64-jh7110-apache-nuttx-2a7429)

## Armbian

[STAR64](https://www.armbian.com/star64/) on _armbian.com_. Read the [Armbian forum thread](https://forum.pine64.org/showthread.php?tid=18276) on _forum.pine64.org_.

## DietPi

[Star64 image](https://dietpi.com/#download) on _dietpi.com_, with Linux 6.1 based on [StarFive VisionFive 2 kernel sources](https://github.com/starfive-tech/linux/tree/JH7110_VisionFive2_6.1.y_devel), rebased on latest [mainline kernel](https://git.kernel.org/pub/scm/linux/kernel/git/stable/linux.git/?h=linux-6.1.y), with Star64 support from [Fishwaldo’s kernel sources](https://github.com/Fishwaldo/Star64_linux) and own configuration. The kernel sources can be found on the [DietPi Star64 repository on GitHub.com](https://github.com/MichaIng/linux/tree/6.1-star64).

Download:

* [Direct image download](https://dietpi.com/downloads/images/testing/DietPi_Star64-RISC-V-Sid.img.xz)

## Fishwaldo images

A Set of Images built with Yocto for commandline, weston and plasma, see the [project on GitHub.com](https://github.com/Fishwaldo/meta-pine64).

Notes:

* Where possible, GPU/VPU acceleration is enabled.

## NixOS

[NixOS](https://sr.ht/~fgaz/nixos-star64/), based on the [the nixos-hardware configuration](https://github.com/NixOS/nixos-hardware/tree/master/pine64/star64)
