---
title: "PineVoice"
draft: false
fullnote: false
menu:
  docs:
    title:
    parent:
    identifier: "PineVoice"
    weight:
---

{{< figure src="/documentation/PineVoice/images/pinevoice.jpg" caption="The PineVoice" width="600" >}}

The **PineVoice** is a RISC-V based smart speaker based on the Bouffalo Lab BL606P RISC-V SoC with C906 64-bit and E907 32-bit CPU cores supported by 16 MB of embedded PSRAM memory, and with built-in Wi-Fi, Bluetooth and Zigbee radio interfaces.

## Software Releases

### Quick Links to the Source of OS Images Build

There is a community effort to bring updated kernels, peripherals and buildroot - Lots of communication happening in the #ox64-nutcracker channel. 

* [buildroot](https://github.com/openbouffalo/buildroot_bouffalo) bringing all the work below together with a bootable kernel and updated filesystem images for SD cards 
* [OpenBouffalo Firmware](https://github.com/openbouffalo/OBLFR) low_load drivers by Fishwaldo and others

Toolchain:

* elf_newlib_toolchain/bin/riscv64-unknown-elf-gcc (Xuantie-900 elf newlib gcc Toolchain V2.2.5 B-20220323) 10.2.0
* linux_toolchain/bin/riscv64-unknown-linux-gnu-gcc (Xuantie-900 linux-5.10.4 glibc gcc Toolchain V2.2.4 B-20211227) 10.2.0
* cmake version 3.19.3

### Software Development Kits
* [BL808 MCU SDK](https://github.com/bouffalolab/bl_mcu_sdk)
* [BLDevCube Flashing Tool for Windows, macOS and Ubuntu x64](https://dev.bouffalolab.com/download)
* [Ox64 UART Flashing Guide](https://wiki.pine64.org/wiki/File:Ox64_BL808UART_connect.pdf), see the [notes](https://gist.github.com/lupyuen/7a0c697b89abccda8e38b33dfe5ebaff)


## SoC and Memory Specification

Based on the [Bouffalo Lab BL606P](https://en.bouffalolab.com/product/)

### CPU Architecture

T-Head C906 480 MHz 64-bit RISC-V CPU:

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
* See [here](https://www.t-head.cn/product/c906?lang=en)

T-Head E907 320 MHz 32-bit RISC-V CPU:

* Supports RISC-V RV32IMAFCP instruction set
* Supports RISC-V 32-bit/16-bit mixed instruction set
* Supports RISC-V machine mode and user mode
* Thirty-two 32-bit integer general purpose registers (GPR) and thirty-two 32-bit/64-bit floating-point GPRs
* Integer (5-stage)/floating-point (7-stage), single-issue, sequentially executed pipeline
* Supports AXI 4.0 main device interface and AHB 5.0 peripheral interface
* 32K instruction cache, two-way set associative structure
* 16K data cache, two-way set associative structure
* See [here](https://www.t-head.cn/product/e907?lang=en)


### System Memory
* Embedded 16MB PSRAM

## Smart Speaker Module Features

### Network
* 2.4 GHz 1T1R WiFi 802.11 b/g/n
* Bluetooth 5.x Dual-mode (BT+BLE)
* Zigbee


### Storage
* On-board 128 Mbit (16 MB) XSPI NOR flash memory

### Expansion Ports
* USB 2.0 OTG port


### Audio
* Microphone
* Speaker

## Board Information, Schematics and Certifications


* Module dimensions: 65 mm x 65 mm x 66 mm
* Input power: 5 V, 2 A USB-C ports

Production version schematic:

* [PineVoice MainBoard Schematic with component placement 20260311](https://files.pine64.org/doc/PineVoice/PineVoice%20Main%20Board%20Schematics-20260311.PDF)
* [PineVoice Bottom Board Schematic 20250921](https://files.pine64.org/doc/PineVoice/PineVoice%20Bottom%20Board%20Schematics-20250921.PDF)


Certifications:

* [PineVoice CE Certificate](https://files.pine64.org/doc/cert/MTi260330019-0103E1C-Verification%20of%20Conformity.pdf)
* [PineVoice FCC Certificate](https://files.pine64.org/doc/cert/PineVoice%20Certificate%20LCSA070722057E.pdf)


## Datasheets for Components and Peripherals

Bouffalo BL606P SoC information:
* [Bouffalo Lab BL606P SoC Datasheet](https://files.pine64.org/doc/datasheet/pinevoice/BL606P_DS_en_1.2.pdf)
* [Bouffalo Lab BL606P SoC Reference Manual](https://files.pine64.org/doc/datasheet/pinevoice/BL606P_Product_Brief_v1.0.pdf)

SPI NOR Flash information:
* [GigaDevice 128Mb XSPI-Flash Datasheet](https://files.pine64.org/doc/datasheet/star64/gd25lq128e_rev1.0_20210513.pdf)
* [Winbond 128Mb QSPI-Flash Datasheet](https://wiki.pine64.org/images/5/5d/W25Q128JW_RevB_11042019-1761358.pdf) (W25Q128JWSQ)


## Compatible UARTs when in bootloader mode

When the PineVoice is in bootloader mode, some UARTs are unable to communicate with it. When this is the case, utilities such as BLDevCube are unable to actually program the device. If you see "Shake hand fail" and an empty ack, and your device is in bootloader mode, then it is likely an incompatible UART.

The below devices have been tested and verified as working:
* Raspberry Pi Pico - running the following [UART firmware](https://github.com/sanjay900/ox64-uart/releases/tag/v1.1) (GP4 and GP5 are used for port 0, GP12 and GP13 for port 1)
* Compiled binary for Pi Pico and connectivity diagram is [here](https://github.com/Kris-Sekula/Pine64_Ox64_SBC/tree/main/uart) 
* ESP32 with CP210x - bridge the EN pin to ground to disable the ESP32 itself, and then connect the TX on the esp32 to 14 on the Ox64 and RX to pin 15. Note that only baud rate 115200 works, and this doesn't seem to work for everyone
* Stand-alone CP2102 dongle works at 115200 baud. Brand used was HiLetgo.
* STM32F401 BlackPill - running the [Black Magic Debug](https://github.com/blackmagic-debug/blackmagic/tree/main/src/platforms/blackpillv2) firmware
* STM32F103C8T6 BluePill - running Black Magic Debug.
* Some UART adapters based on the FT232H (note that the FT232RL does not work, and neither does the Pine 64 JTAG)
* Some CH340G based adapters work and some don't.
* Flipper Zero UART-Bridge works with baud rate set to 230400.