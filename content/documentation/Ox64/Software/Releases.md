---
title: "Releases"
draft: false
menu:
  docs:
    title:
    parent: "Ox64/Software"
    identifier: "Ox64/Software/Releases"
    weight: 1
---

## Quick Links to the Source of OS Images Build

There is a community effort to bring updated kernels, peripherals and buildroot - Lots of communication happening in the #ox64-nutcracker channel.

* [buildroot](https://github.com/openbouffalo/buildroot_bouffalo) bringing all the work below together with a bootable kernel and updated filesystem images for SD cards
* [U-Boot](https://github.com/smaeul/u-boot/tree/bl808) and [OpenSBI](https://github.com/smaeul/opensbi/tree/bl808) work by Smauel
* [Kernel](https://github.com/arm000/linux-bl808/tree/linux-next/mboxic) IRQChip, SDCard, and (WIP) USB by arm000, Alexander Horner and others
* [OpenBouffalo Firmware](https://github.com/openbouffalo/OBLFR) low_load drivers by Fishwaldo and others

Original Linux Images provided by Bouffalo - Very basic **alpha build** which are only fit for board bring up and testing purposes.

* [Linux for BL808](https://github.com/bouffalolab/bl808_linux)
* [Installation Instructions for Linux on BL808 (Chinese)](https://wiki.pine64.org/wiki/File:Linux_BL808.pdf)
* [Installation Instructions for Linux on BL808 (machine-translated to English)](https://wiki.pine64.org/wiki/File:Linux_BL808_en.pdf)

Toolchain:

* elf_newlib_toolchain/bin/riscv64-unknown-elf-gcc (Xuantie-900 elf newlib gcc Toolchain V2.2.5 B-20220323) 10.2.0
* linux_toolchain/bin/riscv64-unknown-linux-gnu-gcc (Xuantie-900 linux-5.10.4 glibc gcc Toolchain V2.2.4 B-20211227) 10.2.0
* cmake version 3.19.3

## Software Development Kits

* [BL808 MCU SDK](https://github.com/bouffalolab/bl_mcu_sdk)
* [BLDevCube Flashing Tool for Windows, macOS and Ubuntu x64](https://dev.bouffalolab.com/download)
* [Ox64 UART Flashing Guide](https://wiki.pine64.org/wiki/File:Ox64_BL808UART_connect.pdf), see the [notes](https://gist.github.com/lupyuen/7a0c697b89abccda8e38b33dfe5ebaff)
* [BL808 Demo Firmware: bl808_demo_event.bin](https://github.com/lupyuen/lupyuen.github.io/releases/download/ox64/bl808_demo_event.bin), see the [notes](https://gist.github.com/lupyuen/7a0c697b89abccda8e38b33dfe5ebaff)
* [BL808 UART Log Firmware: whole_flash_data.bin](https://github.com/lupyuen/lupyuen.github.io/releases/download/ox64/whole_flash_data.bin), see the [notes](https://gist.github.com/lupyuen/7a0c697b89abccda8e38b33dfe5ebaff)
* [BL808 DVK Quick Start](https://github.com/lupyuen/lupyuen.github.io/releases/download/ox64/BL808.DVK.Quick.Start.pdf)
* [OpenSBI for BL808](https://github.com/bouffalolab/bl808_linux/tree/main/opensbi-0.6-808)
* [Rust Peripheral Access Crate (PAC) for BL808](https://github.com/bouffalolab/bl-pac/tree/main/bl808)
* [System View Description (SVD) for BL808](https://github.com/bouffalolab/bl-pac/blob/main/bl808/bl808.svd)
