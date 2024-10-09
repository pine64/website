---
title: "Board Features"
draft: false
menu:
  docs:
    title:
    parent: "PINE_H64_Model_A"
    identifier: "PINE_H64_Model_A/Board_Features"
    weight: 1
---

## Dimensions

Board dimensions: 133mm x 80mm x 19mm

## Power

Input power: DC 5V @ 3A, 3.5mm OD/ 1.35mm ID DC jack connector, Euler connector

## Video

* Digital Video 4KP60 (Type A - full)

## Audio

* 3.5mm stereo earphone/microphone plug

## Network

* 10/100/1000Mbps Ethernet
* WiFi 802.11 b/g/n/ac with Bluetooth 4.0/4.1 (optional)

## Storage

* microSD - bootable, support SDHC and SDXC, storage up to 256GB
* USB -	1 USB3.0 Host port and 2 USB2.0 Host port

## Expansion Ports

* RTC - Real Time Clock Battery Connector
* Wifi/BT Module Header - SDIO 3.0 and UART
* 2x20 pins "Pi2" GPIO Header
* mini PCIe connector

## SoC and memory specifications

The PINE H64 Model A is based on the ***Allwinner H6***.

### CPU Architecture

* Quad-core ARM Cortex-A53 Processor@1488Mhz footnote:[see [Cortex-A53 on arm.com](https://www.arm.com/products/processors/cortex-a/cortex-a53-processor.php)]
* A power-efficient ARM v8 architecture
* 64 and 32bit execution states for scalable high performance
* Trustzone technology supported
* Support NEON Advanced SIMD (Single Instruction Multiple Data) instruction for acceleration of media and signal processing function
* Support Large Physical Address Extensions(LPAE)
* VFPv4 Floating Point Unit
* 32KB L1 Instruction cache and 32KB L1 Data cache
* 512KB L2 cache

### GPU Architecture

* ARM Mali T-720MP2 Dual-core GPU footnote:[see [Mali-T720 on arm.com](https://developer.arm.com/products/graphics-and-multimedia/mali-gpus/mali-t720-gpu)]
* Supports OpenGL ES 3.1/3.0/2.0/1.1, OpenCL 1.2/1.1
* Supports ATSC (Adaptive Scalable Texture Compression)
* Supports FAST(4x)FSAA, IO Coherency
* Floating point operation greater than 70 GFLOPS

### System Memory

* RAM Memory Variants: 1GB, 2GB, and 3GB LPDDR3.
* Storage Memory: PINE H64 boards have a built-in 128Mb SPI Flash memory and can use bootable eMMC modules, bootable microSD cards or USB-attached storage.
