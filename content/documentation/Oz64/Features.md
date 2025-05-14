---
title: "Features"
draft: false
menu:
  docs:
    title:
    parent: "Oz64"
    identifier: "Oz64/Features"
    weight: 1
---

## Board dimension

Board Dimensions: 85mm x 56mm x 18.8mm, see the [model-B board dimension drawing](https://files.pine64.org/doc/rock64/rock64%20board%20dimension.pdf)

{{< figure src="/documentation/Oz64/images/Oz64_3D_model.png" caption="The Oz64 3D model" width="300" >}}

## Network

* 2.4 GHz 1T1R Wi-Fi 6
* Bluetooth 5.2
* 10/100 Mbit/s Ethernet with optional PoE capability

## Storage

* On-board eMMC module socket
* MicroSD, supports SDHC and SDXC

## Expansion ports

* USB 2.0 Host port
* 26 GPIO pins, including SPI, I^2^C and UART functionality
* 2x Dual-lane MiPi CSI port
* Optional dual-lane MiPi DSI port

## Input power

Input Power: +5V @2A with 3.5mm/1.35mm Type H Barrel type DC connector (@1.5A will work if there is no heavy load on the USB 2.0 port)

## SoC and Memory Specification

Based on the [Sophgo SG-200x](https://en.sophgo.com/sophon-u/product/introduce/sg200x.html)

{{< figure src="/documentation/Oz64/images/SG2000_Block_Diagram.png" caption="SG2000 block diagram" width="300" >}}

### CPU Architecture

T-Head C906 1GHz MHz 64-bit RISC-V CPU:

* Supports RISC-V RV64IMAFCV instruction architecture
* Five-stage single-issue sequentially executed pipeline
* Level-1 instruction and data cache of Harvard architecture, with a size of 32 KB and a cache line of 64KB
* Level-2 128KB cache
* Sv39 memory management unit, realizing the conversion of virtual and real addresses and memory management
* jTLB that supports 128 entries
* Supports AXI 4.0 128-bit master interface
* Supports core local interrupt (CLINT) and platform-level interrupt controller (PLIC)
* With 80 external interrupt sources, 3 bits for configuring interrupt priority
* Supports BHT (8K) and BTB
* Compatible with RISC-V PMP, 8 configurable areas
* Supports hardware performance monitor (HPM) units
* See [here](https://www.t-head.cn/product/c906?lang=en)

T-Head C906 700Mhz MHz 64-bit RISC-V CPU:

* Supports RISC-V RV64IMAFCV instruction architecture
* Five-stage single-issue sequentially executed pipeline
* Level-1 instruction and data cache of Harvard architecture, with a size of 16 KB and a cache line of 16KB
* Sv39 memory management unit, realizing the conversion of virtual and real addresses and memory management
* jTLB that supports 128 entries
* Supports AXI 4.0 128-bit master interface
* Supports core local interrupt (CLINT) and platform-level interrupt controller (PLIC)
* With 80 external interrupt sources, 3 bits for configuring interrupt priority
* Supports BHT (8K) and BTB
* Compatible with RISC-V PMP, 8 configurable areas
* Supports hardware performance monitor (HPM) units
* See [here](https://www.t-head.cn/product/c906?lang=en)

ARM Cortex-A53 1GHz 64-bit RISC CPU:

* [Quad-core Cortex-A53 up to 1.0GHz CPU](https://www.arm.com/products/processors/cortex-a/cortex-a53-processor.php)
* Full implementation of the ARM architecture v8-A instruction set
* ARM Neon Advanced SIMD (single instruction, multiple data) support for accelerated media and signal processing computation
* ARMv8 Cryptography Extensions
* In-order pipeline with symmetric dual-issue of most instructions
* Unified system L2 128KB cache
* Includes VFP v3 hardware to support single and double-precision operations
* Integrated 32KB L1 instruction cache, 32KB 4-way set associative L1 data cache
* TrustZone technology support
* PD_A53: Cortex-A53 + Neon + FPU + L1 I/D Cache of core 2/3

8051 25-300MHz 8-bit CPU:

* Integrated 8K SRAM

### System Memory
* SIP DRAM 512MB
