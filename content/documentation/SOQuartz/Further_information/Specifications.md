---
title: "Specifications"
draft: false
menu:
  docs:
    title:
    parent: "SOQuartz/Further_information"
    identifier: "SOQuartz/Further_information/Specifications"
    weight: 
---

The SOQuartz is based on the [Rockchip RK3566](https://www.rock-chips.com/a/en/products/RK35_Series/2021/0113/1274.html).

## CPU Architecture

* [Quad-core ARM Cortex-A55@1.8GHz](https://developer.arm.com/ip-products/processors/cortex-a/cortex-a55)
* AArch32 for full backwards compatibility with ARMv7
* ARM Neon Advanced SIMD (single instruction, multiple data) support for accelerated media and signal processing computation
* Includes VFP hardware to support single and double-precision operations
* ARMv8 Cryptography Extensions
* Integrated 32KB L1 instruction cache and 32KB L1 data cache per core
* 512KB unified system L3 cache

## GPU (Graphics Processing Unit) Capabilities

* [Mali-G52 2EE Bifrost GPU@800MHz](https://developer.arm.com/ip-products/graphics-and-multimedia/mali-gpus/mali-g52-gpu)
* 4x Multi-Sampling Anti-Aliasing (MSAA) with minimal performance drop
* 128KB L2 Cache configurations
* Supports OpenGL ES 1.1, 2.0, and 3.2
* Supports Vulkan 1.0 and 1.1
* Supports OpenCL 2.0 Full Profile
* Supports 1600 Mpix/s fill rate when at 800MHz clock frequency
* Supports 38.4 GLOP/s when at 800MHz clock frequency

## Neural Process Unit NPU Capability

* Neural network acceleration engine with processing performance of up to 0.8 TOPS
* Supports integer 8 and integer 16 convolution operations
* Supports the following deep learning frameworks: TensorFlow, TF-lite, Pytorch, Caffe, ONNX, MXNet, Keras, Darknet

## System Memory

* RAM Memory Variants: 2GB, 4GB, 8GB LPDDR4.
* Storage Memory: optional 128Mb SPI Flash and optional eMMC module from 8GB up to 128GB

## Network

* 10/100/1000Mbps Ethernet
* WiFi 802.11 b/g/n/ac with Bluetooth 5.0

## Displays / Cameras

* 1x HDMI
* 2x DSI
* 1x eDP (Instead of HDMI1)
* 1x LVDS (not available when dual-mode DSI)
* 1x CSI 4-line

## Connectivity

* 1x Ethernet (1Gbit)
* 1x USB 2.0 OTG
* 1x SD Card (SD)
* 1x PCIe 1-Line
* 28x GPIO (TBD)
