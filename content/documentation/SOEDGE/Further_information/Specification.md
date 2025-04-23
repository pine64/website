---
title: "Specification"
draft: false
menu:
  docs:
    title:
    parent: "SOEDGE/Further_information"
    identifier: "SOEDGE/Further_information/Specification"
    weight:
---

Based on the [Rockchip RK1808](https://www.rock-chips.com/a/en/products/RK18_Series/2019/0529/989.html).

## CPU Architecture

* [Dual-core ARM Cortex-A35 Processor@1600-2000Mhz](https://developer.arm.com/ip-products/processors/cortex-a/cortex-a35)
* A power-efficient ARM 64-Bit Armv8-A architecture
* AArch32 for full backward compatibility with Armv7
* Support NEON Advanced SIMD (Single Instruction Multiple Data) instruction for acceleration of media and signal processing function
* Support Large Physical Address Extensions(LPAE)
* VFPv4 Floating Point Unit
* 32KB L1 Instruction cache and 32KB L1 Data cache
* AArch64 for 64-bit support and new architectural features
* TrustZone security technology
* Neon Advanced SIMD
* DSP and SIMD extensions
* VFPv4 Floating point
* Hardware virtualization support
* 128KB L2 cache

## Neural Process Unit NPU Capability

{{< figure src="/documentation/images/Vivante_Acuity_SDK.jpg" width="400" >}}

* [NPU IP from Verisilicon Vivante](https://www.verisilicon.com/en/IPPortfolio/VivanteNPUIP)
* Support max 1920 Int8 MAC operation per cycle
* Support max192 Int16 MAC operation per cycle
* Support max 64 FP16 MAC operation per cycle
* 512KB internal buffer
* One isolated voltage domain to support DVFS
* [Acuity models Github](https://github.com/VeriSilicon/acuity-models)

## System Memory

* RAM Memory Variants: 2GB DDR4.
* Storage Memory: 128Mb SPI Flash and optional eMMC module from 16GB up to 128GB
