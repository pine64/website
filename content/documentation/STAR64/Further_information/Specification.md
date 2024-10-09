---
title: "Specification"
draft: false
menu:
  docs:
    title:
    parent: "STAR64/Further_information"
    identifier: "STAR64/Further_information/Specification"
    weight: 
---

* Based on [StarFive JH7110](https://www.starfivetech.com/en/site/soc)

{{< figure src="/documentation/images/StarFive.jpg" >}}
{{< figure src="/documentation/images/JH7110_Block_Diagram.png" width="800" >}}

## CPU Architecture
{{< figure src="/documentation/images/SiFive.jpg" width="200" >}}

* [Quad-core U74 up to 1.5GHz CPU](https://www.sifive.com/cores/u74)
* Fully compliant with the RISC-V ISA specification
* 64-bit RISC-V Application Core
* 32KB L1 I-cache with ECC
* 32KB L1 D-cache with ECC
* 8 Region Physical Memory Protection
* Virtual Memory support with up to 47 Physical Address bits
* Integrated up to 2MB L2 Cache with ECC
* includes RV64IMAC S7 monitor core, 16 KB L1 I-Cache with ECC, 8 KB DTIM with ECC
* 32-bit RISC-V CPU core (E24) for real time control, support RV32IMFC RISC-V ISA

## GPU Architecture
{{< figure src="/documentation/images/imgtech.png" width="200" >}}

* [Imagination Technology BXE-4-32 up to 600Mhz GPU](https://www.imaginationtech.com/product/img-bxe-4-32-mc4/)
* Support OpenCL 3.0
* Support OpenGL ES 3.2
* Support Vulkan 1.2
* Tile-based deferred rendering architecture for 3D graphics workloads, with concurrent processing of multiple tiles
* Support for GPU visualization, up to 8 virtual GPUs
* On fly frame buffer compression and decompression (TFBC) algorithm
* Performance: 128 FP32 FLOPs/Clock, 256 FP16 FLOPs/Clock

## System Memory

* LPDDR4 RAM Memory Variants: 2GB, 4GB and 8GB.
