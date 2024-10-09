---
title: "Getting started"
draft: false
menu:
  docs:
    title:
    parent: "Quartz64"
    identifier: "Quartz64/Getting_started"
    weight: 1
---

## Flashing the device

Natively the board only supports booting the platform firmware from SPI, the eMMC or a microSD card, see [boot order](#boot_order). The platform firmware loaded from there (U-Boot, EDK2, ...) may then allow loading kernels from additional storage mediums or even the network, and they will have their own boot order.

The board can be booted by flashing your chosen operating system to a microSD card using another device and inserting the microSD card into the Quartz64, see the article [Getting started](/documentation/Introduction/Getting_started). Flashing the eMMC is possible by booting an operating system from the microSD card and overwriting the eMMC from within the booted operating system, or by using [the USB eMMC adapter](https://pine64.com/product/usb-adapter-for-emmc-module/).

## Boot order

The hardware boot order of the Quartz64 is:

1. SPI NOR flash
2. SPI NAND flash
3. eMMC
4. microSD card
