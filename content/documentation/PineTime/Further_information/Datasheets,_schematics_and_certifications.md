---
title: "Datasheets, schematics and certifications"
draft: false
menu:
  docs:
    title:
    parent: "PineTime/Further_information"
    identifier: "PineTime/Further_information/Datasheets,_schematics_and_certifications"
    weight: 
---

## Schematics

* [PineTime Schematic ver1.0a](https://files.pine64.org/doc/PineTime/PineTime%20Schematic-V1.0a-20191103.pdf)
* [PineTime GPIO Port Assignment ver1.0](https://files.pine64.org/doc/PineTime/PineTime%20Port%20Assignment%20rev1.0.pdf)

**📌 NOTE**\
The part number for the SPI FLASH in the schematic diagram is not correct, the PineTime features a larger external FLASH device, see below.

## Chip Datasheets

NORDIC nRF52832 information:

* [nRF52832 Product Brief](https://files.pine64.org/doc/datasheet/pinetime/nRF52832%20product%20brief.pdf)
* [nRF52832 Product Specification v1.4](https://infocenter.nordicsemi.com/pdf/nRF52832_PS_v1.4.pdf)

ARMv7-M information:

* [ARMv7-M Architecture Reference Manual](https://developer.arm.com/documentation/ddi0403/ee/?lang=en)

## Component Datasheets

PMU (Power Management Unit) information:

* [SGMicro SGM40561 Single Cell Charger Datasheet](https://files.pine64.org/doc/datasheet/pinetime/SGM40561.pdf)
* [SGMicro SGM2036 3.3V Low Power Low Dropout RF Linear Regulator Datasheet](https://files.pine64.org/doc/datasheet/pinetime/SGMICRO-SGM2036.pdf)

SPI Flash information:

* [XTX XT25F32B 32Mb(4MB) SPI NOR Flash](https://www.elnec.com/en/device/XTX/XT25F32B+%28QuadSPI%29+%5BSOP8-200%5D/) (data sheets for this part are hard to find but it acts similar to other QuadSPI SPI NOR Flash such as [Macronix 32Mb(4MB) SPI NOR Flash](https://www.macronix.com/Lists/Datasheet/Attachments/7426/MX25L3233F,%203V,%2032Mb,%20v1.6.pdf))
* [XTX XT25F32B](https://datasheet.lcsc.com/szlcsc/2005251035_XTX-XT25F32BSOIGU-S_C558851.pdf)
* IDs for XT25F32B are: manufacturer (0x0b), device (0x15), memory type (0x40), density (0x16)

LCD Panel:

* [1.3" 240x240 IPS LCD Panel Specification for PineTime](https://files.pine64.org/doc/datasheet/pinetime/PineTime%20LCD%20Panel.jpg)
* [11.6" Sitronix LCD Driver/Controller Datasheet](https://wiki.pine64.org/images/5/54/ST7789V_v1.6.pdf)

Touchpad information:

* [Touchpad Specification for PineTimel](https://files.pine64.org/doc/datasheet/pinetime/PineTime%20Touch%20Panel.jpg)
* [11.6" Hynitron CST816S Capacitive Touch Controller Datasheet in Chinese](https://files.pine64.org/doc/datasheet/pinetime/CST816S数据手册V1.1.pdf)
* [Touch Controller Datasheet en](https://wiki.pine64.org/images/2/2f/CST816S.zip)

Sensor:

* [BOSCH BMA425 Triaxial Acceleration Sensor Datasheet on current PineTime device](https://datasheet.lcsc.com/lcsc/1912111437_Bosch-Sensortec-BMA425_C437656.pdf)
* [BOSCH BMA421 Triaxial Acceleration Sensor Product Brief on early PineTime device](https://files.pine64.org/doc/datasheet/pinetime/BST-BMA421-FL000.pdf)
* [TianYiHeXin HRS3300 PPG Heart Rate Sensor Data Sheet](https://files.pine64.org/doc/datasheet/pinetime/HRS3300%20Heart%20Rate%20Sensor.pdf)

## Certificates

* [PineTime FCC Certificate](https://files.pine64.org/doc/cert/FCC_Grant_PineTime_2AWAG-PINETIME_DTS.pdf)
* [PineTime CE Certificate](https://files.pine64.org/doc/cert/CTL2203033031-W%20RED%20Certificate.pdf)

## Manuals

* https://wiki.pine64.org/wiki/File:PineTime Quick Start Guide.pdf[PineTime Quick Start Guide]
