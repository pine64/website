---
title: "SoC and memory specifications"
draft: false
menu:
  docs:
    title:
    parent: "PineNote/Further_information"
    identifier: "PineNote/Further_information/SoC_and_memory_specifications"
    weight: 2
---

The PineNote is based on the [Rockchip RK3566](https://www.rock-chips.com/a/en/products/RK35_Series/2021/0113/1274.html).

## CPU Architecture

* [Quad-core ARM Cortex-A55@1.8GHz](https://developer.arm.com/ip-products/processors/cortex-a/cortex-a55)
* AArch32 for full backwards compatibility with ARMv7
* ARM Neon Advanced SIMD (single instruction, multiple data) support for accelerated media and signal processing computation
* Includes VFP hardware to support single and double-precision operations
* ARMv8 Cryptography Extensions
* Integrated 32KB L1 instruction cache and 32KB L1 data cache per core
* 512KB unified system L3 cache
* [TrustZone](https://developer.arm.com/ip-products/security-ip/trustzone) technology support
* [22nm process, believed to be FD-SOI](https://www.cnx-software.com/2020/12/01/rockchip-rk3568-processor-to-power-edge-computing-and-nvr-applications)

## GPU (Graphics Processing Unit) Capabilities

* [Mali-G52 2EE Bifrost GPU@800MHz](https://developer.arm.com/ip-products/graphics-and-multimedia/mali-gpus/mali-g52-gpu)
* 4x Multi-Sampling Anti-Aliasing (MSAA) with minimal performance drop
* 128KB L2 Cache configurations
* Supports OpenGL ES 1.1, 2.0, and 3.2
* Supports Vulkan 1.0 and 1.1
* Supports OpenCL 2.0 Full Profile
* Supports 1600 Mpix/s fill rate when at 800MHz clock frequency
* Supports 38.4 GLOP/s when at 800MHz clock frequency

## NPU (Neural Processing Unit) Capabilities

* Neural network acceleration engine with processing performance of up to 0.8 TOPS
* Supports integer 8 and integer 16 convolution operations
* Supports the following deep learning frameworks: TensorFlow, TF-lite, Pytorch, Caffe, ONNX, MXNet, Keras, Darknet

## System Memory

* RAM Memory: 4GB LPDDR4.
* Flash Memory: 128GB eMMC
