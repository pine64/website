---
title: "Specifications"
draft: false
menu:
  docs:
    title:
    parent: "ROCK64/Further_information"
    identifier: "ROCK64/Further_information/Specifications"
    weight: 
---

Based on [Rockchip RK3328](https://www.rock-chips.com/a/en/products/RK33_Series/2017/0118/829.html)

## CPU Architecture

* [Quad-core Cortex-A53 up to 1.5GHz CPU](https://www.arm.com/products/processors/cortex-a/cortex-a53-processor.php)
* Full implementation of the ARM architecture v8-A instruction set
* ARM Neon Advanced SIMD (single instruction, multiple data) support for accelerated media and signal processing computation
* ARMv8 Cryptography Extensions
* In-order pipeline with symmetric dual-issue of most instructions
* Unified system L2 cache
* Includes VFP v3 hardware to support single and double-precision operations
* Integrated 32KB L1 instruction cache, 32KB 4-way set associative L1 data cache
* TrustZone technology support
* Full CoreSight debug solution
* One separate power domain for CPU core system to support internal power switch, and to externally turn on/off based on different application scenario
* PD_A53: Cortex-A53 + Neon + FPU + L1 I/D Cache of core 2/3
* One isolated voltage domain to support DVFS

### Frequencies & Voltages

|     |     |
| --- | --- |
| Frequency | Voltage   |
| 408 MHz | 0.950 V   |
| 600 MHz | 0.950 V   |
| 816 MHz | 1.000 V   |
| 1008 MHz | 1.100 V   |
| 1200 MHz | 1.225 V   |
| 1296 MHz | 1.300 V |

### Power Draw

These numbers for power draw have been measured through an USB power monitor (FNB38) while running the `stress` utility, whereby "cpu" stands for `stress --cpu 4` and "vm" stands for `stress --vm 4`. The former spins on the CPU, the latter stresses the memory. Real workloads are usually a mix of both. The tests were ran through ssh, with nothing besides power and ethernet plugged into the ROCK64

Please keep in mind that under real world usage, many other factors come into play. Having a display connected, running a graphical session, I/O and most importantly the connected USB peripherals can add a lot.

Helpful refresher on the formula for power (W) on DC: power = current &times; voltage, because the power factor is 1. The ROCK64 runs on 5V, so use that to calculate current if you need to.

|     |     |     |
| --- | --- | --- |
| Frequency | Power cpu | Power vm   |
| 1296 MHz | 2.64 W | 2.95 W   |
| 1200 MHz | 2.32 W | 2.69 W   |
| 1008 MHz | 1.90 W | 2.31 W   |
| 816 MHz | 1.62 W | 2.05 W   |
| 600 MHz | 1.45 W | 1.85 W   |
| 408 MHz | 1.33 W | 1.72 W   |

It appears a good upper bound for a headless setup is in the neighbourhood of 3 W, or the energy contained in 0.025 bananas per hour.

## GPU Architecture

* [ARM Mali-450MP2 Dual-core GPU](https://www.arm.com/products/multimedia/mali-gpu/ultra-low-power/mali-450.php)
* OpenGL ES 1.1 and 2.0, OpenVG1.1

## System Memory

* LPDDR3 RAM Memory Variants: 1GB, 2GB and 4GB.
