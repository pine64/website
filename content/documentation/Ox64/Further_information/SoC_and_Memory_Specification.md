---
title: "SoC and Memory Specification"
draft: false
menu:
  docs:
    title:
    parent: "Ox64/Further_information"
    identifier: "Ox64/Further_information/SoC_and_Memory_Specification"
    weight: 
---

Based on the [Bouffalo Lab BL808](https://en.bouffalolab.com/product/)

{{< figure src="/documentation/Ox64/images/BL808_Block_Diagram.jpg" width="500">}}

## CPU Architecture

XuanTie C906 480 MHz 64-bit RISC-V CPU:

* Supports RISC-V RV64IMAFCV instruction architecture
* Five-stage single-issue sequentially executed pipeline
* Level-1 instruction and data cache of Harvard architecture, with a size of 32 KB and a cache line of 64B
* Sv39 memory management unit, realizing the conversion of virtual and real addresses and memory management
* jTLB that supports 128 entries
* Supports AXI 4.0 128-bit master interface
* Supports core local interrupt (CLINT) and platform-level interrupt controller (PLIC)
* With 80 external interrupt sources, 3 bits for configuring interrupt priority
* Supports BHT (8K) and BTB
* Compatible with RISC-V PMP, 8 configurable areas
* Supports hardware performance monitor (HPM) units
* See [here](https://www.xrvm.com/product/xuantie/C906)

XuanTie E907 320 MHz 32-bit RISC-V CPU:

* Supports RISC-V RV32IMAFCP instruction set
* Supports RISC-V 32-bit/16-bit mixed instruction set
* Supports RISC-V machine mode and user mode
* Thirty-two 32-bit integer general purpose registers (GPR) and thirty-two 32-bit/64-bit floating-point GPRs
* Integer (5-stage)/floating-point (7-stage), single-issue, sequentially executed pipeline
* Supports AXI 4.0 main device interface and AHB 5.0 peripheral interface
* 32K instruction cache, two-way set associative structure
* 16K data cache, two-way set associative structure
* See [here](https://www.xrvm.com/product/xuantie/E907)

XuanTie E902 150 MHz 32-bit RISC-V CPU:

* See [here](https://www.xrvm.com/product/xuantie/E902)

## System Memory

* Embedded 64MB PSRAM
