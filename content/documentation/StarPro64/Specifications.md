---
title: "Specifications"
draft: false
menu:
  docs:
    title:
    parent: "StarPro64"
    identifier: "StarPro64/Specifications"
    weight: 2
---

{{< figure src="/documentation/StarPro64/images/starpro64_front.jpg" title="The StarPro64" width="400" >}}

{{< figure src="/documentation/StarPro64/images/starpro64_back.jpg" title="The StarPro64 backside" width="400" >}}

## SoC and Memory Specification

* Based on [ESWIN EIC7700X](https://www.eswincomputing.com/en/products/index/36/10.html)

{{< figure src="/documentation/StarPro64/images/EIC7700X_Block_Diagram.png" title="EIC7700X block diagram" width="800" >}}

### CPU Architecture

* [Quad-core P550 up to 1.8GHz CPU](https://www.sifive.com/cores/performance-p500)
* Fully compliant with the RISC-V RV64GBC ISA specification
* 64-bit RISC-V Application Core
* Features 13-stage, triple-issue, out-of-order pipeline
* 32KB L1 I-cache with ECC
* 32KB L1 D-cache with ECC
* Private 256KB L2 Cache
* Shared 4MB L3 Cache

### GPU Architecture

* [Imagination Technology AXM-8-256 up to 600Mhz GPU](https://www.imaginationtech.com/product/img-axm-8-256/)
* Support OpenCL 3.0
* Support OpenGL ES 3.x
* Support Vulkan 1.3
* 128-wide arithmetic logic unit (ALU) design
* Visually Lossless image compression – frame buffer compression and decompression (FBCDC) algorithm
* Lossless data compression – geometry compression, which is performed in the Geometry Processing phase of the 3D graphics workload
* Performance: 256 FP32 FLOPs/Clock, 1024 AI  INT8/Clock

### NPU Architecture

* 19.95 TOPS(INT8), 9.975TOPS(FP16 or INT16)

### System Memory

* 32GB 64bits LPDDR5@6400MHz RAM Memory.

## Board Features

### Video

* Digital Video output up to 4K@60Hz
* H.264/AVC Base/Main/High/High10 profile @ level 5.1; up to 4K&times;2K @ 60fps
* H.265/HEVC Main/Main10 profile @ level 5.1 High-tier; up to 4K&times;2K @ 60fps

### Audio

* 3.5mm audio Jack

### Network

* Dual 10/100/1000Mbps Ethernet 
* 2.4GHz/5Ghz MIMO WiFi 802.11 b/g/n/ac/ax with Bluetooth 5.3

### Storage

* on-board 128Mbit (16MByte) XSPI NOR flash memory - bootable
* microSD - bootable, supports SDHC and SDXC and storage up to 256GB
* eMMC - bootable (optional eMMC Module)
* 2&times; USB3.0 Dedicated Host port
* 2&times; USB2.0 Shared Host port

### Expansion Ports

* PCIe Gen3 &times;4 lane
* 2&times;20 pins "Pi2" GPIO Header
* 4 lane MiPi DSI port for LCD panel
* 4 lane MiPi CSI port for camera module

## Board Information, Schematics and Certifications

Model "A" Baseboard Dimensions: 133mm&times;80mm&times;19mm

Input Power: DC 12V @ 3-5A 5.5mmOD/2.1mmID center-positive Barrel DC Jack connector

Schematic:

* [StarPro64 Schematic 20250310 v2.0 (Production Released version)](https://files.pine64.org/doc/starpro64/StarPro64_schematic_v2.0-20250310.pdf)
* [StarPro64 Component Reference location v2.0 (top layer)](https://files.pine64.org/doc/starpro64/StarPro64_v2.0_Component_Placement_Top-20250310.pdf)
* [StarPro64 Component Reference location v2.0 (bottom layer)](https://files.pine64.org/doc/starpro64/StarPro64_v2.0_Component_Placement_Bottom-20250310.pdf)


Certifications:

* Disclaimer: Please note that PINE64 SBC is not a "final" product and in general certification is not necessary. However, PINE64 still submits the SBC for FCC, CE, and ROHS certifications and obtain the certificates to prove that the SBC board can pass the testing. Please note, a final commercial product needs to perform its own testing and obtain its own certificate.
* Not yet available

## Datasheets for Components and Peripherals 

ESWIN EIC7700X SoC information:
* [ESWIN EIC7700X SoC Product Brief](https://www.eswincomputing.com/en/bocupload/2024/06/19/17187920991529ene8q.pdf)
* [ESWIN EIC7700X SoC Datasheet](https://www.sifive.com/document-file/eic7700x-datasheet)

LPDDR5 (315 Balls) SDRAM:
* [Rayson LPDDR5 Datasheet](https://files.pine64.org/doc/datasheet/starpro64/RS4G32LO5D8FDB-31BT.V1.0.pdf)

eMMC information:
* [PINE64 eMMC module schematic](https://files.pine64.org/doc/rock64/PINE64_eMMC_Module_20170719.pdf)
* [PINE64 USB adapter for eMMC module V2 schematic](https://files.pine64.org/doc/rock64/usb%20emmc%20module%20adapter%20v2.pdf)
* [PINE64 USB adapter for eMMC module PCB in JPEG](https://files.pine64.org/doc/rock64/USB%20adapter%20for%20eMMC%20module%20PCB.tar)
* [16GB Foresee eMMC Datasheet](https://files.pine64.org/doc/datasheet/pine64/E-00517%20FORESEE_eMMC_NCEMAM8B-16G%20SPEC.pdf)
* [32GB/64GB/128GB SanDisk eMMC Datasheet](https://files.pine64.org/doc/datasheet/pine64/SDINADF4-16-128GB-H%20data%20sheet%20v1.13.pdf)

SPI NOR Flash information:
* [GigaDevice 128Mb XSPI-Flash Datasheet](https://files.pine64.org/doc/datasheet/star64/gd25lq128e_rev1.0_20210513.pdf)

Ethernet related info:
* TBA

WiFi/BT module info:
* [AIC AIC8800D80 11AX Dual Band WiFi + Bluetooth5.3 Datasheet](https://files.pine64.org/doc/datasheet/starpro64/AIC8800D80_DataSheet_v0.1.pdf)

## Bringup Notes

* [Lup Yuen's StarPro64 bring up article section 1-7](https://lupyuen.org/articles/starpro64.html)