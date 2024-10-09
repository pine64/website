---
title: "Features"
draft: false
menu:
  docs:
    title:
    parent: "Pinecil"
    identifier: "Pinecil/Features"
    weight: 2
---

* Portability and Temperature control
* Soldering tips:
  1. Replaceable and low cost
  2. Many styles: [currently sold](https://pine64.com/product-category/pinecil/) as 4-packs, one fine set, the other larger.
  3. Compatible with other ts100 tips.
* Multiple power sources will work for more flexibility:
  1. USB-C PD (power delivery), minimum 3 Amps, 12V.
  2. DC 5525 Barrel jack charger, minimum 3 Amps, 12V.
  3. Battery: connect to 18V-21V Lithium-ion tool batteries or 3S/4S/5S LiPo batteries.
* Pinecil V2 has a BL706 chip, see [history of changes below](/documentation/Pinecil/Further_information/History_of_hardware_changes/).
  * Board schematics are open. Software is open. Create your own!
  * [Pinecil breakout board](https://pine64.com/product/pinecil-break-out-board/) lets you use JTAG, GPIO, A2D, SPI, and more.

Additional features (useful for devkit):

* Programmable Risc-V BL706 embedded processor
* V2 model allows BLE Bluetooth control because of the switch to the Bouffalo BL706 MCU.
* 0.69" Monochrome Display that can render text or graphics
* Support for Idle detection, sleep mode of tip, automatic shut-down
* Programmable with [tools from Bouffalo Labs](https://github.com/bouffalolab/bl_mcu_sdk), [HomeBrew](https://github.com/riscv-software-src/homebrew-riscv) or [Linux RISC-V](https://wiki.debian.org/RISC-V#Cross_compilation).
