---
title: "LoRa Add-on"
draft: false
menu:
  docs:
    title:
    parent: "Phone_Accessories"
    identifier: "Phone_Accessories/LoRa"
    weight: 4
---

Store page: [pine64.com](https://pine64.com/product/pinephone-pinephone-pro-pindio-lora-add-on-case/)

{{< figure src="/documentation/images/PP_LoRa.jpg" width="250" >}}

Uses the pogo pins to interface a Semtech SX1262 LoRa module with the PinePhone (Pro).

{{< admonition type="important" >}}
Software for receiving and sending LoRa messages with this back cover does exist, however no PinePhone operating system has added support for it yet.
{{</ admonition >}}

## Schematics and Datasheet

Schematic:

* [PinePhone LoRa Back Cover Schematic ver 1.0 20210425](https://files.pine64.org/doc/PinePhone/Pinephone%20LoRa%20Back%20Cover%20Panel%20Schematic-v1.0-20210425.pdf)

Datasheet:

* [SX1262 Long Range, Low Power, sub-GHz RF Transceiver Datasheet](https://files.pine64.org/doc/datasheet/pinephone/DS_SX1261-2_V1.1-1307803.pdf)
* [ATmel ATtiny Microcontroller Datasheet](https://files.pine64.org/doc/datasheet/pinephone/ATmel%20ATTiny%20Microcontroller%20Datasheet.pdf)

I2C to SPI firmware:

* [zschroeder6212’s tiny-i2c-spi Github page](https://github.com/zschroeder6212/tiny-i2c-spi)
