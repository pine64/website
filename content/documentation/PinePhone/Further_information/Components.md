---
title: "Components"
draft: false
menu:
  docs:
    title:
    parent: "PinePhone/Further_information"
    identifier: "PinePhone/Further_information/Components"
    weight: 
---

| Component | Model |
| --- | --- |
| Touchscreen | Goodix GT917S |
| Rear camera | OmniVision OV5640 |
| Camera flash | SGMICRO SGM3140 |
| Front camera | GalaxyCore GC2145 |
| LCD | Xingbangda XBD599 |
| WiFi | Realtek RTL8723CS |
| Bluetooth | Realtek RTL8723CS |
| Modem | [Quectel EG25-G](http://static.abstore.pl/design/accounts/soyter/img/dokumentacje/quectel_eg25-g.pdf) |
| GNSS/GPS | [Quectel EG25-G](http://static.abstore.pl/design/accounts/soyter/img/dokumentacje/quectel_eg25-g.pdf) |
| Magnetometer | ST LIS3MDL |
| Ambient light / Proximity | SensorTek STK3335 |
| Accelerometer / Gyroscope | InvenSense MPU-6050 |
| Vibration motor | Unknown model |
| Notification LED | LED0603RGB |
| Volume buttons | Buttons connected to the KEYADC |
| Power button | X-Powers AXP803 |
| Battery fuel gauge | X-Powers AXP803 |

## Components list

The following list of components are found in the [schematic](https://files.pine64.org/doc/PinePhone/PinePhone%20v1.2b%20Released%20Schematic.pdf) for the PinePhone 1.2b.

### Abreviations used in schematic

The following [abbreviations](https://www.electronics-notes.com/articles/analogue_circuits/circuits-symbols-diagrams/electronics-circuit-symbols-overview.php) are used as the starting letter(s) to identify the components in the PinePhone schematics:

* **ANT**: antenna
* **C**: [capacitor](https://www.electronics-notes.com/articles/analogue_circuits/circuits-symbols-diagrams/capacitors-polar-nonpolar-variable.php)
* **D**: [diode](https://www.electronics-notes.com/articles/analogue_circuits/circuits-symbols-diagrams/diode-semiconductor.php)
* **DU**: Only used in the "DU1", which is an integrated circuit for memory
* **ED**: Zener diode to protect against electrostatic discharge
* **FB**: [ferrite bead](https://en.wikipedia.org/wiki/Ferrite_bead)
* **J**: [wire link](https://www.electronics-notes.com/articles/analogue_circuits/circuits-symbols-diagrams/wires-switches-connectors.php) (i.e. a connector)
* **R**: [resistor](https://www.electronics-notes.com/articles/analogue_circuits/circuits-symbols-diagrams/resistors-fixed-variable.php)
* **L**: [inductor](https://www.electronics-notes.com/articles/analogue_circuits/circuits-symbols-diagrams/inductors-chokes-coils-transformers.php)
* **NC/**: not connected (i.e. the part probably isn’t placed on the board, but there are circuits in the PCB for it)
* **Q**: transistor
* **SW**: switch
* **T**: test point
* **U**: integrated circuit (i.e. a silicon chip)
* **X**: crystal oscillator (used for clocks)

### P.4 LPDDR3 FPGA178

Note: The title of this schematic page should be changed from "LPDDR3 FPGA178" to "LPDDR3 FBGA178", because the RAM chip is a 178-pin fine pitch ball grid array (FBGA), not a field-programmable gate array (FPGA).

DU1:

* Artmem [ATL3A1632H12A](http://files.pine64.org/doc/datasheet/pinephone/ATL3A1632H12A_mobile_lpddr3_11x11.5_v1.0_1600.pdf) 2GB 800MHz LPDDR3-1600 SDRAM, FBGA-178 11.0x11.5x0.93 mm
* Note: RAM will be clocked slower, since the Allwinner A64 only supports up to 3GB DDR3-1333 (666.5MHz) and doesn’t specify the top supported LPDDR3 speed.

### P.5 CPU

U1:

* Allwinner [A64](http://files.pine64.org/doc/datasheet/pine64/A64_Datasheet_V1.1.pdf) 1.2Ghz 4x Cortex-A53, 64-bit, superscalar, 32KB instruction & 32KB data L1 cache per core, 512KB L2 shared cache, ARM Mali-400 MP2 (Utgard) GPU, HDMI 1.4 (up to 4K@30), USB 2.0 with OTG, MIPI CSI, 4 channels in/out, 24-bit, 8-48 KHz audio, video encode: H.264 1080p@60, video decode: H.265 4K@30, H.265 1080p@120, H.264, MPEG1/2/4 / VP8 / AVS / AVS+ 1080p@60, FBGA-396 15x15 mm
* Note: Clocked at 1.152Ghz on the PinePhone.

X501:

* Axtal [AXX3225](https://pdf1.alldatasheet.com/datasheet-pdf/view/228815/AXTAL/AXX3225/+Q2J83JVYUyCLcEbcvvzE+/datasheet.pdf) 24MHz ±10ppm quartz crystal oscillator in SMD package, 3.2x2.5 mm

D500:

* Will Semiconductor [ESD5451X](https://pdf1.alldatasheet.com/datasheet-pdf/view/1136979/WILLSEMI/ESD5451X/+01_7-9BXuHlLuHRMflaL..hDk+/datasheet.pdf) 1-line, bi-directional, transient voltage suppressor, EDS protection up to ±30kV and 8A.

X500:

* Seiko Instruments Inc. (SII) [SC32S](https://www.sii.co.jp/en/quartz/files/2013/03/SC-32S_Leaflet_e20151217.pdf) 32.768KHz crystal oscillator
* Note: Not clear if using the [SC32S-12.5PF20PPM](https://www.mouser.com/ProductDetail/Seiko-Instruments-Micro-Energy/SC32S-125PF20PPM?qs=3CPZD7qAgihedyqH7awUjg%3D%3D) or the [SC32S-7PF20PPM](https://www.mouser.com/ProductDetail/Seiko-Semiconductors/SC32S-7PF20PPM?qs=3CPZD7qAgigZSR1ASVAS6w%3D%3D)

### P.6 POWER

ED600:

* Will Semiconductor (WILLSEMI) [ESD5451X](https://pdf1.alldatasheet.com/datasheet-pdf/view/1136979/WILLSEMI/ESD5451X/+01_7-9BXuHlLuHRMflaL..hDk+/datasheet.pdf) 1-line, bi-directional, transient voltage suppressor, EDS protection up to ±30kV and 8A.
* Note: This part is marked as optional in the schematic and may not be included.

U600:

* X-Powers [AXP803](https://raw.githubusercontent.com/OLIMEX/OLINUXINO/master/DOCUMENTS/A64-PDFs/AXP803_Datasheet_V1.0.pdf) power management integrated circuit (PMIC) optimized for multi-core systems, li-ion battery fuel gauge, USB charger (up to 2.8A), QFN 68-pin, 8x8 mm

Q600:

* Will Semiconductor [WPM1481](http://monitor.espec.ws/files/wpm1481_186.pdf) single P-channel, -12V, -5.5A, power MOSFET

J600:

* BA5924211-R battery connector
* Note: [Picture](http://biz.everychina.com/ddream-r/z2eb2904-lateralpressure_ba5924211_r.html) shows this part as having 8 pins, but the schematic shows 6 pins. [One page](http://biz.everychina.com/ddream-r/z2eb2904-lateralpressure_ba5924211_r.html) says that it is made by LateralPressure, but [another](https://www.worldwayelec.com/pro/rohm-semiconductor/ba5924211-r/3528348) says it is made by ROHM.

L606:

* IND_252010 2.2uH-2A inductor
* Note: Maybe this is the TDK [VLS252010HBU](https://product.tdk.com/info/en/catalog/datasheets/inductor_commercial_power_vls252010hbu_en.pdf).

U601:

* LowPowerSemi [LP6226CB6F](https://datasheet.lcsc.com/szlcsc/2004281203_LOWPOWER-LP6226CB6F_C517054.pdf) high efficiency boost DC/DC converter with 33V, 1.5A power MOSFET, SOT23-6 package

D600:

* On semiconductor [SS24](https://www.onsemi.com/pub/Collateral/SS24-D.PDF) Schottky power rectifier, [SOD123](https://www.nexperia.com/packages/SOD123.html) package

### P.7 NAND/eMMC

U700:

* Kimtigo [KM110SS0016GxA-DDD00WT](http://files.pine64.org/doc/datasheet/pinephone/Kimtigo_fbga153_16_32_64_eMMC_datasheet_v1.3.pdf) 16GB eMMC 5.1 TLC NAND Flash memory, FBGA-153 11.5×13.0×1.0 mm.
* Note 1: The schematic says the package is BGA-169, but the Kimtigo documentation says it is FBGA-153.
* Note 2: The A64 only supports up to eMMC 5.0.
* Note 3: The schematic lists the part as KM110SS0016GxA-DDD00WT, but [these photos](https://xnux.eu/devices/photos/pp-1.1.html) show that its variant, the KM111SS0016GxA-DDD00WT, is being used in the 16GB PinePhone.

### P.8 AUDIO

ED800, ED801, ED802, ED803, ED804, ED805, ED806:

* Will Semiconductor [ESD5451X](https://pdf1.alldatasheet.com/datasheet-pdf/view/1136979/WILLSEMI/ESD5451X/+01_7-9BXuHlLuHRMflaL..hDk+/datasheet.pdf) 1-line, bi-directional, transient voltage suppressor, EDS protection up to ±30kV and 8A.

U801:

* Broadchip [BCT4717ETB-TR](http://www.broadchip.com/upLoad/product/month_2003/202003191750413832.pdf) 4.0Ω, 300MHz bandwidth, dual bi-directional SPDT (single-pole/double-throw) analog switch

J800:

* EAROUTN-A64 receiver

J801:

* JA-3606-001AA 3.5mm audio jack

Q801:

* Toshiba [SSM3K35MFV](https://toshiba.semicon-storage.com/info/docget.jsp?did=10004&prodName=SSM3K35MFV) field-effect transistor, silicon N-channel MOS type

U800:

* Shanghai awinic technology [AW8737SCSR](https://www.awinic.com/Cn/Index/pageView/catid/107/id/45.html) high efficiency (80%), low noise (53μV), ultra-low distortion (0.008%), constant large volume, 7th generation class K audio amplifier, 1.6×1.68 mm CSP-14 package, 0.4mm pitch [datasheet](https://pdf1.alldatasheet.com/datasheet-pdf/view/1147555/AWINIC/AW8737SCSR/+014J7J8XvUpOKG+Gc..whdxee+/datasheet.pdf)

FB800, FB801:

* 600ohm at 100MHz ferrite bead in a [0402](https://www.electronics-notes.com/articles/electronic_components/surface-mount-technology-smd-smt/packages.php) package ([examples](https://uk.farnell.com/c/passive-components/emc-rfi-suppression/ferrites-ferrite-assortments/ferrite-beads?impedance-100mhz=600ohm))

### P.9 T-CADD/USB

Q901, Q902, Q903:

* Toshiba [SSM3K35MFV](https://toshiba.semicon-storage.com/info/docget.jsp?did=10004&prodName=SSM3K35MFV) field-effect transistor, silicon N-channel MOS type

ED900, ED901, ED902:

* Will Semiconductor [ESD5451X](https://pdf1.alldatasheet.com/datasheet-pdf/view/1136979/WILLSEMI/ESD5451X/+01_7-9BXuHlLuHRMflaL..hDk+/datasheet.pdf) 1-line, bi-directional, transient voltage suppressor, EDS protection up to ±30kV and 8A.

J901:

* SA-2202-112 25-pin Micro-SIM and TF slot

### P.10 CAMERA

J1000:

* T03-1025-FG01 27-pin connector to the rear camera.
* Note: The schematic says "GC2035-200W", which is a mistake because the rear camera is the OmniVision [OV6540](http://files.pine64.org/doc/datasheet/pinephone/OV5640_datasheet.pdf).

J1001:

* T03-1025-FG01 27-pin connector to the front camera.
* Note: The schematic says "GC2035-200W", which is a mistake because the rear camera is the GalaxyCore [GC2145](http://files.pine64.org/doc/datasheet/pinephone/GC2145%20CSP%20DataSheet%20release%20V1.0_20131201.pdf), not the GalaxyCore [GC2035](https://g2g9w6w7.stackpathcdn.com/pdf-down/G/C/2/GC2035-GalaxyCore.pdf).

U1000:

* Shanghai awinic technology [AW3641EDNR](https://pdf1.alldatasheet.com/datasheet-pdf/view/1147538/AWINIC/AW3641EDNR/+014J75AXvUpOKG+GczEDzOOae+/datasheet.pdf) flash LED driver with programmable timer and PWM dimming torch mode, 1A, 8 current levels.

### P.11 LCM/CTP

Note: "LCM/CTP" means "liquid crystal display monitor/capacitive touch panel". An LCM generally includes an LCD screen + LED backlight + PCB with the LCD controller + frame.

J1100:

* FPC24-PT05B, OK-24F-04 28-pin connector to the MIPI-DSI LCD

LED2:

* RGB LED

J1101:

* CON6-0.5, TP_6PIN-ZQ01 8-pin connector to the capacitive touch panel controller
* Note: The label says that the connector has 6-pins, but the schematic shows 8-pins.

ED1100, ED1101, ED1102, ED1103:

* Will Semiconductor [ESD5451X](https://pdf1.alldatasheet.com/datasheet-pdf/view/1136979/WILLSEMI/ESD5451X/+01_7-9BXuHlLuHRMflaL..hDk+/datasheet.pdf) 1-line, bi-directional, transient voltage suppressor, EDS protection up to ±30kV and 8A.

U1100:

* Chipown [AP3127B025](http://www.datasheet39.com/download.php?id=924200) step-up DC/DC converter series, white LED backlight driver, 6-pin SOT-23-6L package.

### P.12 SENSORS/MT/KEY

J1200:

* 8-pin connector to test points
ED1200, ED1201:
* Will Semiconductor [ESD5451X](https://pdf1.alldatasheet.com/datasheet-pdf/view/1136979/WILLSEMI/ESD5451X/+01_7-9BXuHlLuHRMflaL..hDk+/datasheet.pdf) 1-line, bi-directional, transient voltage suppressor, EDS protection up to ±30kV and 8A.

U1200:

* STmicroelectronics [LIS3MDL](https://www.st.com/en/mems-and-sensors/lis3mdl.html) ultra-low-power three-axis magnetometer, LGA-12 2.0x2.0x1.0 mm [datasheet](https://www.st.com/resource/en/datasheet/lis3mdl.pdf)
* Note: The LIS3MDL is currently unavailable, so it [has been replaced](https://www.pine64.org/2021/03/15/march-update/#comment-4273) in the PinePhone Beta Edition with the Voltafield AF8133L e-Compass, which is unlisted on the Voltafield web site, but the [AF8133J](http://www.voltafield.com/products01.html) is listed. Presumably U1200 will be unpopulated and U1203 will be populated in the Beta Edition, since they appear to be alternatives.

U1201:

* SensorTek https://web.archive.org/web/20190601120915 / [STK3311-A](http://www.sensortek.com.tw/en/product/Proximity_Sensor_with_ALS.html) proximity and ambient light sensor (large gap) with built-in infrared LED, DFN-8 3.94x2.36x1.35 mm [datasheet](https://cdn.datasheetspdf.com/pdf-down/S/T/K/STK3310-Sensortek.pdf)

U1202:

* TDK InvenSense [MPU6050](https://invensense.tdk.com/products/motion-tracking/6-axis/mpu-6050/) six-axis, low-power MEMS gyroscope and accelerometer, QFN-24 4x4x0.9 mm [datasheet](https://invensense.tdk.com/wp-content/uploads/2015/02/MPU-6000-Datasheet1.pdf)

U1203:

* Asahi Kasei Microdevices (AKM) [AK09911](https://static6.arrow.com/aropdfconversion/19f6bc6e0891877d596c7b1da69df3d2ea4388a5/31ak09911.pdf) 3-axis electronic compass IC with Hall sensor, 8-pin WL-CSP (BGA), 1.2×1.2×0.5 mm
* or Voltafield Technology Corp. (VTC) [AF8133J](http://www.winforcetek.com/pdf/PD-DST-0011-00%20AF8133J%20V03.pdf) 3-axis electronic compass with proprietary anisotropic magneto resistive (AMR) technology, 8-pin WLCSP 1.2x1.2x0.5 mm
* Note: These parts appear to be alternatives to be used if the LIS3MDL is unavailable, so U1203 was probably unpopulated in BraveHeart and the Community Editions, but will be populated in the Beta Edition.

U1204:

* Bosch Sensortek [BMI120](https://datasheet.lcsc.com/szlcsc/1912111437_Bosch-Sensortec-BMI120_C437657.pdf) 3-axis gyroscope and accelerometer, LGA-14 2.5x3.0x0.83 mm
* Note: Listed as "NC/BMI120", where "NC" probably means "not connected", so there may be circuits in the PCB for the part, but it is not placed on the board. This is probably an alternative to the TDK InvenSense MPU6050, in case it isn’t available or costs too much.

Q1200:

* Toshiba [SSM3K35MFV](https://toshiba.semicon-storage.com/info/docget.jsp?did=10004&prodName=SSM3K35MFV) field-effect transistor, silicon N-channel MOS type

D1200:

* Torex [XBS104S14](https://www.torexsemi.com/file/xbs104s14r/XBS104S14R.pdf) Schottky barrier diode, 1A, 40V, SOD-123A package

J1201:

* 2-pin connector to a motor, 1x1.8 mm
* Note: Presumably this is a vibration motor.

### P.13 DIGITAL VIDEO

J1300:

* OK-50F-04 40-pin connector
* Note: This part is probably produced by Shenzhen Yaqi Technology Co., which is part of OCN in Taiwan, and uses the Archie brand name.&lt;

U1304:

* Analogix [ANX7688](https://www.analogix.com/en/system/files/AA-002281-PB-6-ANX7688_Product_Brief_0.pdf) HDMI to USB-C bridge with MUX, converts HDMI 2.0 to DisplayPort Alternate Mode, USB-C Power Delivery (PD), BGA-64.
* Note 1: The schematic lists this part as "ANX7688S", but it is unclear what the "S" at the end stands for.
* Note 2: xnux.eu provides [more info](https://xnux.eu/devices/feature/anx7688.html) on the ANX7688, including flashing the firmware.

U1300:

* America Techcode Semiconductor [TD6817](http://techcodesemi.com/datasheet/TD6817.pdf) 1.5MHz 2A synchronous step-down regulator dropout, SOT23-5 package
* or Diodes Incorporated [AP3406K-ADJTRG1](https://media.digikey.com/pdf/Data%20Sheets/Diodes%20PDFs/AP3406.pdf) buck switching regulator IC positive adjustable 0.6V 650mA [datasheet](https://media.digikey.com/pdf/Data%20Sheets/Diodes%20PDFs/AP3406.pdf)

U1302:

* LowPowerSemi [LPW5206H](https://cdn.datasheetspdf.com/pdf-down/L/P/W/LPW5206-LowPowerSemi.pdf) USB power loading switch, N-channel MOSFET, SOT23-5 package

U1303:

* Texas Instruments [TXB0104YZT](https://www.ti.com/lit/ds/symlink/txb0104.pdf) 4-bit bidirectional voltage-level translator with automatic direction sensing and ±15-kV ESD protection, 12-pin DSBGA 1.40×1.90 mm

Q1300, Q1301, Q1302, Q1304, Q1305:

* Toshiba [SSM3K35MFV](https://toshiba.semicon-storage.com/info/docget.jsp?did=10004&prodName=SSM3K35MFV) field-effect transistor, silicon N-channel MOS type

U1305, U1309:

* Will Semiconductor [WS4621C-1X1](https://pdf1.alldatasheet.com/datasheet-pdf/view/1140651/WILLSEMI/WS4621C/+014QJJ4XuHlLuHRMfdaDGDwO+/datasheet.pdf) 2A, 38 mΩ, 290nA quiescent current and 70nA standby current load switch, CSP-4L 1x1 mm.

U1308:

* Shanghai awinic technology [AW3632](https://pdf1.alldatasheet.com/datasheet-pdf/view/1147535/AWINIC/AW3632/+014J758XvUpOKG+GczEww+/datasheet.pdf) high efficiency, low profile, fixed 5V output pump power supply, QFN-8 package

X1300:

* Mercury United Electronics [X3225](https://rf.cdiweb.com/products/detail/x322500018p3020207060r-mercury-united-electronics-inc/71942/) 27.000 MHz crystal oscillator

### P.14 WIFI+BT

U1400:

* Realtek [RTL8723CS](http://files.pine64.org/doc/datasheet/pine64/RTL8723BS.pdf) 802.11 b/g/n, single-band (2.4 GHz), Bluetooth 4.0, with SDIO for WiFi and UART for Bluetooth, LGA-40 12x12x1.6 mm.

X1400:

* 24Mhz ±10ppm crystal oscillator

D1400:

* SXSEMI [AU0511P1](http://sxsemi.com/upfile/AU0511P1.pdf) low capacitance ESD protection diode, SOD-882

ANT1400

* Antenna

### P.15 MODEM-4G

U1500:

* [Quectel EG25-G](https://www.quectel.com/product/lte-eg25-g/) https://wiki.pine64.org/wiki/File:Quectel_EG25-G_LTE_Standard_Specification_V1.3.pdf GSM/UMTS/LTE cellular modem and GNSS (GPS/Galileo/GLONASS/BeiDou/QZSS, with A-GPS), LGA-144 9.0x32.0x2.4 mm

U1502, 1503, 1504:

* Texas Instruments [TXB0104YZT](https://www.ti.com/lit/ds/symlink/txb0104.pdf) 4-bit bidirectional voltage-level translator with automatic direction sensing and ±15-kV ESD protection, 12-pin DSBGA 1.40×1.90 mm

Q1501, Q1503, Q1504, Q1505:

* Toshiba [SSM3K35MFV](https://toshiba.semicon-storage.com/info/docget.jsp?did=10004&prodName=SSM3K35MFV) field-effect transistor, silicon N-channel MOS type

J1500, J1502:

* MRF004-P01A 4-pin connector

Q1500:

* Will Semiconductor [WPM1481](http://monitor.espec.ws/files/wpm1481_186.pdf) single P-channel, -12V, -5.5A, power MOSFET
* Note: The documentation shows 6 pins, but the schematic shows 8 pins.

### Component Counts

| Type of component | Main PCB | USB PCB |
| --- | --- | --- |
| Antenna connectors (ANT_xxx_) | 6 | 4 |
| Capacitors (C_xxx_) | 296 | 16 |
| Diodes (D_xxx_) | 5 | 0 |
| Zener diodes (ED_xxx_) | 17 | 0 |
| Ferrite beads (FB_xxx_) | 6 | 0 |
| Wire links / connectors (J_xxx_) | 14 | 4 |
| Resistors (R_xxx_) | 222 | 0 |
| Inductors (L_xxx_) | 15 | 0 |
| Transistors (Q_xxx_) | 16 | 19* |
| Switches (SW_xxx_) | 1 | 0 |
| Test points (T_xxx_) | 27 | 3 |
| Integrated circuits (U/DU_xxx_) | 24† | 2 |
| Crystal oscillators (X_xxx_) | 5 | 0 |
| **Total without test points** | **627** | **45** |
| **Total with test points** | **654** | **48** |

Here is how the PinePhone compares with the Librem 5 in terms of components:

| Type of component | Librem 5 main | Librem 5 USB | PinePhone main | PinePhone USB |
| --- | --- | --- | --- | --- |
| Antenna connectors (ANT_xxx_) | 3 | 2 | 6 | 4 |
| Capacitors (C_xxx_) | 521 | 11 | 296 | 16 |
| Diodes (D/TVS/ED_xxx_) | 59 | 1 | 22 | 0 |
| Connectors (J/CON_xxx_) | 26 | 10 | 14 | 4 |
| Resistors (R/F_xxx_) | 348 | 8 | 222 | 0 |
| Inductors (L/FB_xxx_) | 79 | 7 | 21 | 0 |
| Transistors (Q_xxx_) | 17 | 0 | 16 | 19* |
| Switches (SW_xxx_) | 5 | 0 | 1 | 0 |
| Test points (T/TC/TP/TS/TV_xxx_) | 126 | 4 | 27 | 3 |
| Integrated circuits (U/DU_xxx_) | 65 | 2 | 24† | 2 |
| Crystal oscillators (Y/X_xxx_) | 10 | 0 | 5 | 0 |
| **Total without test points** | **1133** | **41** | **627** | **45** |
| **Total with test points** | **1259** | **45** | **654** | **48** |

* 18 parts for the PinePhone USB-C port are labeled as T_xxx_ in the schematic with the image of transistors, but it is possible that these are resistors and capacitors.

† There are 26 U/DU_xxx_ listed in the PinePhone schematic, but the two extra are for an alternative magnetometer (U1200 / U1203) and an alternative gyroscope and accelerometer (U1202 / U1204) which are unpopulated.

Source: [Amos Batto](https://forums.puri.sm/t/component-counts-in-the-librem-5-and-pinephone/11240)

### Other components not in the schematics

* SGMICRO [SGM3140](http://www.sg-micro.com/uploads/soft/20190829/1567071622.pdf) 500mA buck/boost charge pump LED driver for camera flash and torch, TDFN-10 3x3x0.75 mm
* Note: The [PinePhone page](/documentation/PinePhone/Further_information/Components/) lists the SGM3140, but the schematics contain the U1000: awinic AW3641EDNR, so it is unclear why the SGM3140 is needed.
* Goodix [GT917S](http://files.pine64.org/doc/datasheet/pinephone/GT917S-Datasheet.pdf) touch controller
* Sitronix [ST7703](http://files.pine64.org/doc/datasheet/pinephone/ST7703_DS_v01_20160128.pdf) MIPI LCD driver
* Xingbangda [XBD599](https://lkml.org/lkml/2020/6/16/1654) 5.99″ IPS LCD, 720x1440 pixels, 16.7M colors, hardened glass
