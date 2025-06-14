---
title: "Project Don’t be evil"
draft: false
menu:
  docs:
    title:
    parent: "PinePhone/Revisions"
    identifier: "PinePhone/Revisions/Project_Dont_be_evil"
    weight:
aliases:
  - /wiki/Project_Don't_be_evil
---

{{< figure src="/documentation/images/Qee3ovj.jpg" >}}

The Project **Don’t be evil** is the phase two of _PINE64’s_ smartphone, the [PinePhone](/documentation/PinePhone) Development Kit. Project Don’t be evil is an actual smartphone developer kit for the PINE64 Smartphone dubbed "PinePhone". It is used in the early stages of development as a starting point for affiliated projects.

The PinePhone development has been broken down into three distinct phases:

* First phase - Project Anakin
* Second phase - purpose-built development kit code named "Don’t be evil" and introduced at FOSDEM 2019
* Lastly, the third phase which is the PinePhone itself - scheduled to be prototype released in Q3 2019 and BTO batch released with mobile OS parents in Q4 2019 (pending on software development).

{{< figure src="/documentation/images/Qsud2Gt.jpg" >}}
{{< figure src="/documentation/images/Martijnpocket.jpg" >}}

## Baseboard and SOPine Module Information, and Schematics

* Baseboard Dimensions: 165mm x 76mm x 19.5mm
* Input Power: DC 5V @ 2A, 3.7V Li-Ion battery connector, USB type-C connector

Baseboard Schematic:

* ["Don’t Be Evil" PinePhone Dev kit Baseboard Structure](https://files.pine64.org/doc/PinePhone/Pinephone-devkit%20Board%20Structure.pdf)
* ["Don’t Be Evil" PinePhone Dev kit Baseboard Ver 1.1 Schematic](https://files.pine64.org/doc/PinePhone/Pinephone-devkit-SCH%20Ver%201.1.pdf)
* ["Don’t Be Evil" PinePhone Dev kit Baseboard Ver 1.1 PCB Artwork](https://files.pine64.org/doc/PinePhone/Pinephone%20Dev%20Kit%20Ver%201.1_PCB.pdf)
* ["Don’t Be Evil" PinePhone Dev kit Baseboard Ver 1.2 Schematic](https://files.pine64.org/doc/PinePhone/Pinephone-devkit-SCH%20Ver%201.2.pdf)
* ["Don’t Be Evil" PinePhone Dev kit Baseboard Ver 1.2 PCB Artwork](https://files.pine64.org/doc/PinePhone/Pinephone%20Dev%20Kit%20Ver%201.2_PCB.pdf)

SOPine Module Schematic:

* [SOPine Module Schematic](https://files.pine64.org/doc/SOPINE-A64/SOPINE-A64-Schematic-ver-0.9.pdf)
* [SOPine Module Pin Assignment ver 1.0](https://files.pine64.org/doc/SOPINE-A64/SOPINE-A64-Pin-Assignments-ver-1.0.pdf)

Wifi/BT module information:

* [PINE A64 Wifi/BT Module Schematic](https://files.pine64.org/doc/Pine%20A64%20Schematic/A64-DB-WIFI-BT-REV%20B.pdf)

Pin assignment:

* [PINE A64 Pi-2/Eular/Ext Bus/Wifi Bus Connector Pin Assignment (Updated 15/Feb/2016)](https://files.pine64.org/doc/Pine%20A64%20Schematic/Pine%20A64%20Pin%20Assignment%20160119.pdf)

### SoC and Memory Specification

Based on the Allwinner A64/R18. The R18 and A64 are identical SoC but R18 committed for 10 years supply by vendor.

### CPU Architecture

* [Quad-core ARM Cortex-A53 Processor@1152Mhz](https://www.arm.com/products/processors/cortex-a/cortex-a53-processor.php)
* A power-efficient ARM v8 architecture
* 64 and 32bit execution states for scalable high performance
* Support NEON Advanced SIMD (Single Instruction Multiple Data) instruction for acceleration of media and signal processing function
* Support Large Physical Address Extensions(LPAE)
* VFPv4 Floating Point Unit
* 32KB L1 Instruction cache and 32KB L1 Data cache
* 512KB L2 cache

### GPU Architecture

* [ARM Mali400MP2 Dual-core GPU](https://www.arm.com/products/multimedia/mali-gpu/ultra-low-power/mali-400.php)
* Support OpenGL ES 2.0 and OpenVG 1.1 standard

### System Memory

* RAM Memory Variants: 2GB LPDDR3.
* Storage Memory: SPI Flash and optional eMMC module from 16GB up to 64GB

### Datasheets for Components and Peripherals

Allwinner A64/R18 SoC information:

* Note: the R18 and A64 are identical SoC but the R18 is committed for a 10 years supply by the vendor.
* [Allwinner A64 SoC Brief Introduction](https://files.pine64.org/doc/datasheet/pine64/A64%20brief%20v1.0%2020150323.pdf)
* [Allwinner R18 SoC Brief Introduction](https://files.pine64.org/doc/datasheet/pine64/Allwinner-R18-Brief%20Sheet.pdf)
* [Allwinner A64/R18 SoC Data Sheet V1.1 (Official Released Version)](https://files.pine64.org/doc/datasheet/pine64/A64_Datasheet_V1.1.pdf)
* [Allwinner A64/R18 SoC User Manual V1.0 (Official Release Version)](https://files.pine64.org/doc/datasheet/pine64/Allwinner_A64_User_Manual_V1.0.pdf)

X-Powers AXP803 PMU (Power Management Unit) information:

* [AXP803 PMIC Datasheet](https://files.pine64.org/doc/datasheet/pine64/AXP803_Datasheet_V1.0.pdf)

LPDDR3 information:

* [Allwinner LPDDR3 Datasheet](https://files.pine64.org/doc/datasheet/pine64/AWL3A1632_mobile_lpddr3_1600Mbps.pdf)
* [Foresee LPDDR3 Datasheet](https://files.pine64.org/doc/datasheet/pine64/FORESEE%20178ball%2012x11.5%20LPDDR3%2016G%20Spec%20V1.0-1228.pdf)
* [Samsung LPDDR3 Datasheet](https://files.pine64.org/doc/datasheet/pine64/K4E6E304EE-EGCE.pdf)
* [Hynix LPDDR3 Datasheet](https://files.pine64.org/doc/datasheet/pine64/LPDDR3%20178ball%208Gb_H9CCNNN8JTALAR_Rev1.0.pdf)

eMMC information:

* [PINE64 eMMC module schematic](https://files.pine64.org/doc/rock64/PINE64_eMMC_Module_20170719.pdf)
* [PINE64 USB adapter for eMMC module V2 schematic](https://files.pine64.org/doc/rock64/usb%20emmc%20module%20adapter%20v2.pdf)
* [PINE64 USB adapter for eMMC module PCB in JPEG](https://files.pine64.org/doc/rock64/USB%20adapter%20for%20eMMC%20module%20PCB.tar)
* [SanDisk eMMC Datasheet](https://files.pine64.org/doc/datasheet/pine64/SDINADF4-16-128GB-H%20data%20sheet%20v1.13.pdf)
* [Hynix eMMC Datasheet](https://files.pine64.org/doc/datasheet/pine64/H26M64003DQR%20Datasheet.pdf)
* [Foresee eMMC Datasheet](https://files.pine64.org/doc/datasheet/pine64/FORESEE_eMMC_NCEMBSF9-xxG%20SPEC%20A0%2020150730.pdf)

SPI NOR Flash information:

* [WinBond 128Mb SPI Flash Datasheet](https://files.pine64.org/doc/datasheet/pine64/w25q128jv%20spi%20revc%2011162016.pdf)
* [GigaDevice 128Mb SPI Flash Datasheet](https://files.pine64.org/doc/datasheet/pine64/GD25Q128C-Rev2.5.pdf)

### Related datasheets

2MPixel front CMOS Camera module information:

* [2MP CMOS Image Sensor Module Drawing](https://files.pine64.org/doc/datasheet/pinephone/GC20355Mp-module_for_pinephone_devkit.pdf)
* [GalaxyCore GC2035 2MP CMOS Image Sensor Product Brief](https://files.pine64.org/doc/datasheet/pinephone/GC2035%20Product%20Brief.pdf)
* [GalaxyCore GC2035 2MP CMOS Image Sensor Datasheet](https://files.pine64.org/doc/datasheet/pinephone/GC2035%20DataSheet.pdf)

5MPixel Rear CMOS Camera module information:

* [5MP CMOS Image Sensor Module Drawing](https://files.pine64.org/doc/datasheet/pinephone/ATK-OV5640-5Mp-module_for_pinephone_devkit.pdf)
* [OmniVision OV5640 5MP CMOS Image Sensor Datasheet](https://files.pine64.org/doc/datasheet/pinephone/OV5640_datasheet.pdf)
* [OmniVision OV5640 5MP CMOS Image Sensor Software Application Note](https://www.arducam.com/downloads/modules/OV5640/OV5640_Software_app_note_parallel.pdf)

LCD Touch Screen Panel information:

* [5.7" 1440x720 IPS LCD Panel Specification](https://files.pine64.org/doc/datasheet/pinephone/XBD572-IPS-HI010A%20SPEC.pdf)
* [fiti JD9365D LCD Controller Datasheet](https://files.pine64.org/doc/datasheet/pinephone/JD9365D_DS_Preliminary_V0.01_20170427.pdf)
* [5.7" Front Panel Touch Screen Specification](https://files.pine64.org/doc/datasheet/pinephone/XBD572-IPS-HI010A%20SPEC.pdf)
* [FocalTech FT6336GU Front Panel Touch Screen Specification](https://files.pine64.org/doc/datasheet/pinephone/FT6336GU_Upgrade_Spec_Ver1.0.pdf)

Lithium Battery information:

* [Panasonic NCR18650B 3350mAH Lithium Ion Battery Specification](https://files.pine64.org/doc/datasheet/pinephone/ncr18650b.pdf)

Ethernet PHY information:

* [Realtek RTL8211 10/100/1000M Ethernet Transceiver](https://files.pine64.org/doc/datasheet/pine64/rtl8211e(g)-vb(vl)-cg_datasheet_1.6.pdf)

Wifi/BT module information:

* [Realtek RTL8723BS WiFi with BT SDIO](https://files.pine64.org/doc/datasheet/pine64/RTL8723BS.pdf)

LTE module information:

* [Quectel EC25 LTE Module Specification](https://files.pine64.org/doc/datasheet/project_anakin/LTE_module/Quectel_EC25_LTE_Specification_V1.4.pdf)
* [Quectel EG25-G LTE Module Specification](https://files.pine64.org/doc/datasheet/project_anakin/LTE_module/Quectel_EG25-G_LTE_Specification_V1.1_Preliminary_20180522%20(002).pdf)
* [Quectel EC25 LTE Module AT Cammands Set Manual](https://files.pine64.org/doc/datasheet/project_anakin/LTE_module/Quectel_EC25&EC21_QuecCell_AT_Commands_Manual_V1.1.pdf)
* [Quectel EC25 LTE Module Hardware Design Guide](https://files.pine64.org/doc/datasheet/project_anakin/LTE_module/Quectel_EC25_Hardware_Design_V1.3.pdf)
* [Quectel EC25 LTE Module Reference Design Guide](https://files.pine64.org/doc/datasheet/project_anakin/LTE_module/Quectel_EC25_Reference_Design_Rev.D_20161111.pdf)

Sensors:

* [ST LIS3MDL 3-axis Magnetomater Datasheet](https://www.st.com/en/mems-and-sensors/lis3mdl.html)
* [InvenSense MPU-6050 Six-Axis (Gyro + Accelerometer) MEMS Datasheet](https://www.invensense.com/products/motion-tracking/6-axis/mpu-6050/)
* [SensorTek STK3335 Ambient Light Sensor and Proximity Sensor](https://www.sensortek.com.tw/en/product/Proximity_Sensor_with_ALS.html)

## Software releases

* [A64 mainline status matrix chart](https://linux-sunxi.org/Linux_mainlining_effort#Status_Matrix)

Some these OS images labelled as **beta or nightly builds** which means they are only fit for testing purposes. These images should be used **at your own risk** and are not fit for normal use.

* [Arch Linux XFCE](https://github.com/anarsoul/linux-build/releases/latest)
* [longsleep BSP Linux](https://www.stdin.xyz/downloads/people/longsleep/pine64-images/)
* [ayufan Linux](https://github.com/ayufan-pine64/linux-build/releases/latest/)

### postmarketOS

{{< figure src="/documentation/images/PostmarketOS_logo.png" width="100" >}}

Download:

* [Direct download from postmarketOS image site](https://images.postmarketos.org/pinephone/)

Instructions:

* [postmarketOS PinePhone "Don’t Be Evil" dev kit wiki site](https://wiki.postmarketos.org/wiki/Pine_Don%27t_be_evil_devkit_(pine-dontbeevil))

Notes:

* postmarketOS early alpha test build for microSD boot
* for 8GB microSD cards and above
* Suitable for PinePhone "Don’t Be Evil" Dev Kit version 1.1 and version 1.2
* There are two type of LCD panels. For long touch screen cable, please use the build with inverted wording.

### Sailfish OS

{{< figure src="/documentation/images/SailfishOS_logo.png" width="100" >}}

The Sailfish OS image is build on Gitlab CI, the latest image can be installed using our [flashing script](https://raw.githubusercontent.com/sailfish-on-dontbeevil/flash-it/master/flash-it.sh) written in Bash.

The script downloads the image and bootloader from our CI, extracts everything and burns it onto the SD card.

Instructions:

1. Download the flashing script
2. Insert a microSD card in your device
3. Make the script executable: `chmod +x flash-it.sh`
4. Execute it: `./flash-it.sh`
5. Follow the instructions. Some commands in the script require root permissions (for example: mounting and flashing the SD card).

Notes:

* The script will format and flash the SD card, make sure that you don’t have any important data on the SD card!

### Maemo Leste

{{< figure src="/documentation/images/Maemoleste-logo.png" width="100" >}}

Download:

* [Maemo Leste test builds download](https://maedevu.maemo.org/images/pinephone-dontbeevil/)

Notes:

* Works on dev kit versions 1.1 and 1.2
* Write the image to a micro SD (8GB+) or eMMC

### LuneOS

{{< figure src="/documentation/images/Luneos-logo-256.png" width="100" >}}

Download:

* [LuneOS test image for PinePhone and thanks to Tofe](https://build.webos-ports.org/luneos-testing/images/pinephone/)

Notes:

* It is recommended to use bmaptool
* for example `bmaptool copy https://build.webos-ports.org/luneos-testing/images/pinephone/luneos-dev-image-pinephone-testing-0-15.rootfs.wic.gz /dev/mmcblk0`

## Mali Driver

For the Mali driver see [Mali Driver](/documentation/General/Mali_driver).

## Errata for ver1.1 and ver1.2 board

1. Please DON’T insert micro SIM card to dev kit board micro SIM card slot, the SIM data, VPP, and GND signal have been misplaced. A miciPCIe adapter with sim card holder 9shown as below photo) will be provide to developers to correct this mistake.

{{< figure src="/documentation/images/MiniPCIe_with_sim_slot_adapter.png" width="200" >}}

1. The PinePhone dev kit doesn’t charge due to VBUS on SOPine module is not connected. Please connect R9688 solder pads with 0 ohm resistor or using thin wire bridge up the solder pads. Location shows as below:

{{< figure src="/documentation/images/PinePhone_VBUS_charging_small.png" width="200" >}}

1. The SOPINE’s SPI NOR flash storage and the devkit’s camera flash (heh) share the same GPIO pins. The flash storage may not be used.

{{< figure src="/documentation/images/SOPINE-SPI-Flash.png" width="200" >}}

1. On the camera flash GPIO conflict, the new assignment of GPIO PB3 pin for SGM3140 FLASH_EN and GPIP PD7 for FLASH_TRIGOUT. Please note that PD7 is also LCD_ID pin which may not be used.

Images:

{{< figure src="/documentation/images/GPIO_PB3_location.jpg" caption="GPIO_PB3_location" >}}
{{< figure src="/documentation/images/U54_SGM3140_FLASH_EN_pin_location.jpg" width="314" >}}
{{< figure src="/documentation/images/Flash_GPIO_Reassigned.jpg" caption="Flash GPIOs Reassigned wiring" >}}

## Other Resources

* [Linux Sunxi Wiki page on PINE A64](https://linux-sunxi.org/Pine64#Manufacturer_images)
* [Linux Image created by Andre Przywara](https://github.com/apritzel/pine64)
* [PINE64 Linux build scripts, tools and instructions by Longsleep](https://github.com/longsleep/build-pine64-image)
* [PINE64 Linux image by Longsleep](https://www.stdin.xyz/downloads/people/longsleep/pine64-images/)
* [Shrinking images on Linux by FrozenCow](https://softwarebakery.com/shrinking-images-on-linux)
* [Quectel EC-25 LTE module open source information](https://osmocom.org/projects/quectel-modems/wiki/EC25/24)
