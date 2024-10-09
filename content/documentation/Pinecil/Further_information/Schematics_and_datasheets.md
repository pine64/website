---
title: "Schematics and datasheets"
draft: false
menu:
  docs:
    title:
    parent: "Pinecil/Further_information"
    identifier: "Pinecil/Further_information/Schematics_and_datasheets"
    weight: 
---

## Schematics and Board Data

### Pinecil V2 mainboard schematic

* [Pinecil mainboard schematic ver 2.0 20220608, this is production version schematic](https://files.pine64.org/doc/Pinecil/Pinecil_schematic_v2.0_20220608.pdf)
* [Pinecil mainboard ver 2.0 PCB Component Placement PDF file](https://files.pine64.org/doc/Pinecil/Pinecil_PCB_placement_v2.0_20220608.pdf)

### Pinecil V1 mainboard schematic

V1 was only sold until July 2022, and then discontinued for newer V2 model

* [Pinecil mainboard schematic ver 1.0 20201120, this is production version schematic](https://files.pine64.org/doc/Pinecil/Pinecil_schematic_v1.0a_20201120.pdf)
* [Pinecil mainboard ver 1.0 PCB Component Placement Top PDF file](https://files.pine64.org/doc/Pinecil/Pinecil-PCB-placement-v1.0-topplace.pdf)
* [Pinecil mainboard ver 1.0 PCB Component Placement Bottom PDF file](https://files.pine64.org/doc/Pinecil/Pinecil-PCB-placement-v1.0-bottomplace.pdf)
* [Pinecil mainboard ver 1.0 PCB Component Placement Top Drawing file](https://files.pine64.org/doc/Pinecil/Pinecil-PCB-placement-v1.0-topplace.dxf)
* [Pinecil mainboard ver 1.0 PCB Component Placement Bottom Drawing file](https://files.pine64.org/doc/Pinecil/Pinecil-PCB-placement-v1.0-bottomplace.dxf)

## Datasheets for Components

### Pinecil V2 datasheets

* Power MOSFET Switch: [HSM4313](https://datasheet.lcsc.com/lcsc/2105241831_HUASHUO-HSM4313_C2828487.pdf), location U13 ([Replacement HSM4313](https://lcsc.com/product-detail/MOSFETs_HUASHUO-HSM4313_C2828487.html)).
* LDO Regulator: [LP 3986-33](https://datasheet.lcsc.com/lcsc/1912111437_LOWPOWER-LP3986-33B3F_C387689.pdf), Ultra-low noise, location U5 (Replacement [LP 3986-33](https://www.lcsc.com/product-detail/Linear-Voltage-Regulators-LDO_LOWPOWER-LP3986-33B3F_C387689.html)).
* Buck Converter: [TP6841S6 40V](https://datasheet.lcsc.com/lcsc/2108072230_TECH-PUBLIC-TP6841S6_C2844736.pdf), Step-Down, location U8, (Replacement [TP6841S6-A](https://www.lcsc.com/product-detail/DC-DC-Converters_TECH-PUBLIC-TP6841S6-A_C2844924.html)).
* USB-C PD Controller: [FUSB302MPX](https://rocelec.widen.net/view/pdf/0av2cqef3a/FAIR-S-A0001311862-1.pdf?t.download=true&u=5oefqw), location U1, (Replacement [FUSB302MPX](https://www.lcsc.com/product-detail/span-style-background-color-ff0-USB-span-ICs_onsemi-Fusb302mpx_C442699.html))
* Acceleration/Gyroscope: [SC7A20 sensor](https://lcsc.com/product-detail/Attitude-Sensor-Gyroscope_Hangzhou-Silan-Microelectronics-SC7A20TR_C5126709.html), Silan, location U9 (replacement unknown).
* NTC Temperature Sensor: [NTCG163JF103FTDS](https://media.digikey.com/pdf/Data%20Sheets/TDK%20PDFs/NTCG163JF103FTDS_Spec.pdf), location NTC1 (Replacement [NTC here](https://lcsc.com/product-detail/span-style-background-color-ff0-NTC-span-Thermistors_TDK-NTCG163JF103FTDS_C435270.html)). Note that U10 is empty if NTC type thermistor is used.
* Optional Hall Effect Sensor: [ Si7210-B-00-IV(R) ](https://files.pine64.org/doc/datasheet/pinecil/si7210-datasheet.pdf)by Silicon Labs, location U14. This is a user add-on and does not come installed on the pcb.
  * ([How magnets work near Hall Sensor Si7210](https://www.silabs.com/documents/public/application-notes/an1018-si72xx-sensors.pdf))
  * ([Replacement Si7210-B-00-IV](https://lcsc.com/product-detail/Position-Sensor_SILICON-LABS-SI7210-B-00-IVR_C2654956.html), also at Digikey and Mouser)
* Operational Amplifier [SGM8557-1AXN5G](https://files.pine64.org/doc/datasheet/pinecil/SGM8557.pdf), SGMicro, Low Noise OP Amp Datasheet, location U11 (replacement unknown).
* Display Screen OLED [QUG-9616TSWCG02](https://files.pine64.org/doc/datasheet/pinecil/1810010328_UG-Univision-Semicon-UG-9616TSWCG02_C88335.pdf) datasheet (Replacement [QUG-9616TSWCG02](https://www.lcsc.com/product-detail/OLED-Displays-Modules_UG-Univision-Semicon-UG-9616TSWCG02_C88335.html) OLED Display).

MCU: Bouffalo Labs, BL-706_QFN48, RISC-V + 2.4 GHz RF SoC

* [BL706 Analysis](https://lupyuen.github.io/articles/bl706), by Lupyuen, includes datasheet, location U15.
* [BL706 datasheet](https://dev.bouffalolab.com/media/doc/702/open/datasheet/en/html/index.html)
* [BL706 Reference Manual](https://dev.bouffalolab.com/media/doc/702/open/reference_manual/en/html/index.html)
* [SDK and Bouffalo documents](https://github.com/bouffalolab/bl_mcu_sdk)
* [SMD Resonator](https://datasheet.lcsc.com/lcsc/1912111437_TAE-Zhejiang-Abel-Elec-TAXM32M4ZFBCCT2T_C388797.pdf) for Bluetooth BLE,  32MHZ/12PF-10PPM, SMD2016-4P, location UX1 (Replacement [SMD Resonator](https://lcsc.com/product-detail/Crystals_TAE-Zhejiang-Abel-Elec-TAXM32M4ZFBCCT2T_C388797.html)).

USB-C port:

* possible part, has not been verified: [Replacement USB-C port](https://www.lcsc.com/product-detail/span-style-background-color-ff0-USB-span-Connectors_SHOU-HAN-TYPE-C-24P-QT_C2681555.html)

### Pinecil V1 datasheets

* Buck converter: [RT7272B 3A Datasheet](https://files.pine64.org/doc/datasheet/pinecil/RT7272B-05.pdf), Ricktek, Step-Down converter, location U8
* LDO Regulator: [LP 3986-33](https://datasheet.lcsc.com/lcsc/1912111437_LOWPOWER-LP3986-33B3F_C387689.pdf), location U5, ([Replacement here](https://www.lcsc.com/product-detail/Linear-Voltage-Regulators-LDO_LOWPOWER-LP3986-33B3F_C387689.html)).
* MOSFET Switch: [CJQ7328 8A datasheet](https://files.pine64.org/doc/datasheet/pinecil/Changjiang-Electronics-Tech-CJ-CJQ7328.pdf), Chang Jiang.
  * Hint: people have replaced V1 mosfet using the better rated one from the newer V2 datasheets (HSM4313 has same footprint and higher rating), see V2 section for MOSFET.
* Acceleration [Bosch BMA223 Sensor Datasheet](https://files.pine64.org/doc/datasheet/pinecil/BMA223-Bosch.pdf)
* Temperature Sensor: [Analog Device TMP36 Datasheet](https://files.pine64.org/doc/datasheet/pinecil/TMP35_36_37.pdf), location U10, (possible [replacement here](https://www.lcsc.com/product-detail/Temperature-Sensors_Analog-Devices-TMP36GRTZ-REEL7_C129489.html)).
* Optional Hall Effect Sensor: [ Si7210-B-00-IV(R) by Silicon Labs, location U14](https://files.pine64.org/doc/datasheet/pinecil/si7210-datasheet.pdf). This is a user add-on and does not come installed on the pcb.
  * ([How magnets work near Hall Sensor Si7210](https://www.silabs.com/documents/public/application-notes/an1018-si72xx-sensors.pdf))
  * ([One place to buy it](https://lcsc.com/product-detail/Position-Sensor_SILICON-LABS-SI7210-B-00-IVR_C2654956.html), also at Digikey and Mouser)
* OLED Display screen: [QUG 9616TSWCG02 Display Module Datasheet](https://files.pine64.org/doc/datasheet/pinecil/1810010328_UG-Univision-Semicon-UG-9616TSWCG02_C88335.pdf)
* USB Type-C PD Controller: [FUSB302 USB PD Datasheet](https://files.pine64.org/doc/datasheet/pinecil/FUSB302-D.PDF)
* OP Amp information: [SGMicro SGM8557-1 Low Noise OP Amp Datasheet (U11)](https://files.pine64.org/doc/datasheet/pinecil/SGM8557.pdf)
* Capacitors: [possible replacement part for C5, 1uF/50V](https://lcsc.com/product-detail/Multilayer-Ceramic-Capacitors-MLCC-SMD-SMT_YAGEO-CC0603KRX7R9BB105_C559769.html)
* USB-C port: possible part, has not been verified: [Replacement](https://www.lcsc.com/product-detail/span-style-background-color-ff0-USB-span-Connectors_SHOU-HAN-TYPE-C-24P-QT_C2681555.html)

GigaDevice RISC-V SoC data:

* [GigaDevice RISC-V GD32VF103TB SoC Datasheet V1.1](https://files.pine64.org/doc/datasheet/pinecil/GD32VF103_Datasheet_Rev%201.1.pdf)
* [GigaDevice RISC-V GD32VF103TB SoC Usermanual V1.2](https://files.pine64.org/doc/datasheet/pinecil/GD32VF103_User_Manual_EN_V1.2.pdf)

Breakout Board Datasheet: [LP6498B6F 1.2A Switching Power Regulator](https://files.pine64.org/doc/datasheet/pinecil/LP6498B6F.pdf)
