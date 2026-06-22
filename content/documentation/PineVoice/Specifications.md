---
title: "Specifications"
draft: false
menu:
  docs:
    title:
    parent: "PineVoice"
    identifier: "PineVoice/Specifications"
    weight: 1
---

The **PineVoice** is a compact smart speaker based on the Bouffalo Lab BL606P RISC-V SoC. It is designed as a local voice assistant satellite, with Wi-Fi, Bluetooth, a speaker, a dual microphone array, buttons, and a center ring LED.

## SoC and memory

PineVoice is based on the [Bouffalo Lab BL606P](https://bouffalolab.com/product/?type=detail&id=16).

### CPU architecture

T-Head C906 480 MHz 64-bit RISC-V CPU:

* Supports RISC-V RV64IMAFCV instruction architecture
* Five-stage single-issue sequentially executed pipeline
* Level-1 instruction and data cache of Harvard architecture, with a size of 32 KiB and a cache line of 64 bytes
* Sv39 memory management unit
* Supports AXI 4.0 128-bit master interface
* Supports core local interrupt (CLINT) and platform-level interrupt controller (PLIC)
* Compatible with RISC-V PMP

T-Head E907 320 MHz 32-bit RISC-V CPU:

* Supports RISC-V RV32IMAFCP instruction set
* Supports RISC-V 32-bit and 16-bit mixed instruction set
* Supports RISC-V machine mode and user mode
* Integer and floating-point pipelines
* Supports AXI 4.0 main device interface and AHB 5.0 peripheral interface
* 32 KiB instruction cache
* 16 KiB data cache

T-Head E902 150 MHz 32-bit RISC-V CPU

### Memory and storage

* 32 MiB pSRAM
* 788 KiB SRAM
* 16 MiB flash storage

## Hardware features

### Wireless

* Wi-Fi 802.11 b/g/n
* Bluetooth 5.2 Dual-mode (BT+BLE)

### Audio

* Built-in speaker (tuned for voice applications)
* Dual microphone array

### Controls and indicators

{{< figure src="/documentation/PineVoice/images/pinevoice-top-view-labels.png" caption="PineVoice buttons view" width="600" >}}

* Button controls
* Center LED ring and button
* Hardware mute button

See [Software](/documentation/PineVoice/Software/) for the current factory firmware button behavior and LED status colors.

### Power and connectivity

* USB-C power input and data channel
  * Debug UART is exposed on unused USB-C pins

### Package contents

* USB-A to USB-C power cable

## Board information, schematics and certifications

Module dimensions:

* 65 mm x 65 mm x 66 mm

Production version schematics:

* [PineVoice MainBoard Schematic with component placement 20260311](https://files.pine64.org/doc/PineVoice/PineVoice%20Main%20Board%20Schematics-20260311.PDF)
* [PineVoice Bottom Board Schematic 20250921](https://files.pine64.org/doc/PineVoice/PineVoice%20Bottom%20Board%20Schematics-20250921.PDF)

Certifications:

* [PineVoice CE Certificate](https://files.pine64.org/doc/cert/MTi260330019-0103E1C-Verification%20of%20Conformity.pdf)
* [PineVoice FCC Certificate](https://files.pine64.org/doc/cert/PineVoice%20Certificate%20LCSA070722057E.pdf)

## Datasheets

Bouffalo BL606P SoC information:

* [Bouffalo Lab BL606P SoC Datasheet](https://files.pine64.org/doc/datasheet/pinevoice/BL606P_DS_en_1.2.pdf)
* [Bouffalo Lab BL606P SoC Reference Manual](https://raw.githubusercontent.com/bouffalolab/bl_docs/main/BL808_RM/en/BL808_RM_en_1.3.pdf) (BL808 RM applies to BL606P as well)
* [Bouffalo Lab BL606P SoC Product Brief](https://files.pine64.org/doc/datasheet/pinevoice/BL606P_Product_Brief_v1.0.pdf)

SPI NOR flash information:

* [GigaDevice 128 Mb XSPI-Flash Datasheet](https://files.pine64.org/doc/datasheet/star64/gd25lq128e_rev1.0_20210513.pdf)
* [Winbond 128 Mb QSPI-Flash Datasheet](https://wiki.pine64.org/images/5/5d/W25Q128JW_RevB_11042019-1761358.pdf)
