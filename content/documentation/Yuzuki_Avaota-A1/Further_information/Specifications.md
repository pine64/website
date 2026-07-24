---
title: "Specifications"
draft: false
menu:
  docs:
    title:
    parent: "Yuzuki_Avaota-A1/Further_information"
    identifier: "Yuzuki_Avaota-A1/Further_information/Specifications"
    weight:
---


## SoC and Memory Specification
* Based on [Allwinner A527](https://www.allwinnertech.com/index.php?c=product&a=index&id=109)

{{< figure src="/documentation/Yuzuki_Avaota-A1/images/Allwinner-T527-A527-block-diagram.jpg" caption="Allwinner T527 A527 block diagram" >}}

### CPU Architecture
* [Quad-core ARM Cortex-A55](https://developer.arm.com/ip-products/processors/cortex-a/cortex-a55) at 2.0&nbsp;GHz
* AArch32 for full backwards compatibility with ARMv7
* ARM Neon Advanced SIMD (single instruction, multiple data) support for accelerated media and signal processing computation
* Includes VFP hardware to support single and double-precision operations
* ARMv8 Cryptography Extensions
* Integrated 32KB L1 instruction cache and 32KB L1 data cache per core
* Integrated 64KB L2 instruction cache and 128KB L2 data cache per cluster
* 1MB unified system L3 cache

### GPU Architecture
* [Mali-G57 Valhall GPU@850MHz](https://www.arm.com/products/silicon-ip-multimedia/gpu/mali-g57)
* 4x Multi-Sampling Anti-Aliasing (MSAA) with minimal performance drop 
* 128KB L2 Cache configurations
* Supports OpenGL ES 1.1, 2.0, and 3.2
* Supports Vulkan 1.1
* Supports OpenCL 1.1, 1.2, 2.0 Full Profile
* Supports Renderscript
* L2 Cache 	Configurable 64KB – 512KB
** 64KB-128KB for 1-Core
** 128KB-256KB for 2-Core
** 256KB for 3-Core
** 1x256KB-2x256KB for 4-Core
** 2x256KB-2x512KB for 5-Core and 6-Core configurations
* Supports 3400 Mpix/s fill rate when at 850MHz clock frequency
* Supports 243.2 GLOP/s when at 850MHz clock frequency for peak single precision (FP32) performance


### System Memory
* LPDDR4 RAM Memory Variants: 2GB and 4GB.

## Board Features

### Video
* Digital Video output up to 4K@60Hz
* H.264/AVC Base/Main/High/High10 profile @ level 5.1; up to 4K&times;2K @ 30fps
* H.265/HEVC Main/Main10 profile @ level 5.1 High-tier; up to 4K&times;2K @ 60fps

### Audio
* 3.5mm audio Jack

### Network
* Dual 10/100/1000Mbps Ethernet 
* 2.4GHz/5Ghz MIMO WiFi 802.11 b/g/n/ac with Bluetooth 5.2

### Storage
* on-board 128Mbit (16MByte) XSPI NOR flash memory - bootable
* microSD - bootable, supports SDHC and SDXC and storage up to 256GB
* eMMC - bootable on-board 16GB or 32GB


### Expansion Ports

* 2&times;20 pins "Pi2" GPIO Header

{{< figure src="/documentation/Yuzuki_Avaota-A1/images/Avaota-A1_40_pin_connector.jpg" caption="Avaota-A1 40 pin connector diagram" >}}
* 4 lane MiPi DSI port for LCD panel
* 4 lane MiPi CSI port for camera module
* 1&times; USB3.0 OTG port
* 1&times; USB2.0 Host port
* 1&times; USB2.0 OTG port
* 1&times; CAN port