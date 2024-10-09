---
title: "Specifications"
draft: false
menu:
  docs:
    title:
    parent: "Pinebook_Pro/Further_information"
    identifier: "Pinebook_Pro/Further_information/Specifications"
    weight: 
---

Based on Rockchip RK3399

## CPU Architecture

big.LITTLE architecture: Dual Cortex-A72 + Quad Cortex-A53, 64-bit CPU

* Full implementation of the ARM architecture v8-A instruction set (both AArch64 and AArch32)
* ARM Neon Advanced SIMD (single instruction, multiple data) support for accelerated media and signal processing computation
* ARMv8 Cryptography Extensions
* VFPv4 floating point unit supporting single and double-precision operations
* Hardware virtualization support
* TrustZone technology support
* Full CoreSight debug solution
* One isolated voltage domain to support DVFS

Cortex-A72 (big cluster):

* [Dual-core Cortex-A72 up to 2.0GHz CPU](https://developer.arm.com/products/processors/cortex-a/cortex-a72)
* Superscalar, variable-length, out-of-order pipeline
* L1 cache 48KB Icache and 32KB Dcache for each A72
* L2 cache 1024KB for big cluster

Cortex-A53 (little cluster):

* [Quad-core Cortex-A53 up to 1.5GHz CPU](https://developer.arm.com/products/processors/cortex-a/cortex-a53)
* In-order pipeline with symmetric dual-issue of most instructions
* L1 cache 32KB Icache and 32KB Dcache for each A53
* L2 cache 512KB for little cluster

Cortex-M0 (control processors):

* [Cortex-M0 CPU](https://developer.arm.com/ip-products/processors/cortex-m/cortex-m0)
* Two Cortex-M0 cooperate with the central processors
* Architecture: Armv6-M
* Thumb/Thumb2 instruction set
* 32 bit only

## GPU Architecture

* [ARM Mali-T860MP4 Quad-core GPU](https://developer.arm.com/products/graphics-and-multimedia/mali-gpus/mali-t860-and-mali-t880-gpus)
* The highest performance GPUs built on Arm Mali’s famous Midgard architecture, the Mali-T860 GPU is designed for complex graphics use cases and provide stunning visuals for UHD content.
* Frequency 650MHz
* Throughput 1300Mtri/s, 10.4Gpix/s

Graphic interface standards:

* OpenGL® ES 1.1, 1.2, 2.0, 3.0, 3.1, 3.2. (Panfrost has initial support of 3.0 beginning 2020/02/27)
* Vulkan 1.0, using the Mali binary blob. (Panfrost does not support Vulkan as of 2020/06/24)
* OpenCL™ 1.1, 1.2
* DirectX® 11 FL11_1
* RenderScript™

## System Memory

RAM Memory:

* LPDDR4
* 800MHz, (limited by RK3399)
* Dual memory channels on the CPU, each 32 bits wide
* Quad memory channels on the RAM chip, each 16 bits wide, 2 bonded together for each CPU channel
* 4GB as a single 366 pin mobile RAM chip

Storage Memory:

* 64GB eMMC module, can be upgraded to an 128GB eMMC module. (The initial PINE64 community build version shipped with a 128GB eMMC.)
* eMMC version 5.1, HS400, 8 bit on RK3399 side
* Bootable

SPI flash:

* [SPI](/documentation/Pinebook_Pro/Features/SPI)
* 128Mbit / 16MByte
* 1 bit interface
* Bootable, (first boot device, ahead of eMMC & SD card)
* U-Boot images can be made to work, but as of 2020/06/24 there is no standardized image available.

## Video out

* USB-C Alt mode DP
* Up to 3840x2160 p60, dependant on adapter, (2 lanes verses 4 lanes)

## Expansion Ports

MicroSD card:

* Bootable
* Supports SD, SDHC and SDXC cards, up to 512GB tested. SDXC standard says 2TB is the maximum.
* Version SD3.0, (MMC 4.5), up to 50MB/s
* SD card Application Performance Class 1 (A1), (or better), recommended by some users, for better IOPS

USB ports:

* 1 x USB 2.0 Type-A Host Port, bootable
* 1 x USB 3.0 Type-A Host Port, 5Gbps, is not bootable
* 1 x USB 3.0 Type-C OTG Port, 5Gbps, (includes laptop charging function), is not bootable
* Note that high power USB devices may not work reliably on a PBP. Or they may draw enough power to drain the battery even when the PBP is plugged into A.C. One alternative is externally powered USB devices.

Headphone jack switchable to UART serial console mux circuit
