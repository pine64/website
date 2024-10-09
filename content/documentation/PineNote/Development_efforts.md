---
title: "Development efforts"
draft: false
menu:
  docs:
    title:
    parent: "PineNote"
    identifier: "PineNote/Development_efforts"
    weight: 3
---

The following page discusses the development efforts for the PineNote:

* [PineNote Development](/documentation/PineNote/Development) for general information regarding how to flash the device and other development information.

## Software

* [PineNote Development/Flashing](/documentation/PineNote/Development/Flashing) for general flashing instructions of data to the PineNote
* [PineNote Development/TODOs](/documentation/PineNote/Development/TODOs)

### Linux Kernel

* [RK3566 EBC Reverse-Engineering](/documentation/General/RK3566_EBC_reverse-engineering) for the EBC (eInk Panel) driver.
* [PineNote Development/Building Kernel](/documentation/PineNote/Development/Building_kernel)
* BSP Linux SDK version 4.19 for the PineNote and [Quartz64 Model A](/documentation/Quartz64):
  * [Direct download](http://files.pine64.org/SDK/Quartz64/QUARTZ64-model-A_BSP%20Linux.tar.gz) from _pine64.org_ (32.67GB, MD5 of the TAR-GZip file _24554419aec29700add97167a3a4c9ed_)
  * [Mirror by mwfc](https://tmp.mwfc.info/pinenote/QUARTZ64-model-A_BSP%20Linux.tar.gz)
  * An unofficial torrent download provided by a community member of the BSP Linux and Android SDKs can be found [here](https://cdn.discordapp.com/attachments/870707390998282292/907726420204208148/pinenote.torrent) (100GB).

### User Space

* [PineNote Development/Booting Linux](/documentation/PineNote/Development/Booting_Linux)

For tweaks and tricks see:

* [PineNote Development/Software Tweaks](/documentation/PineNote/Development/Software_tweaks)

For app development see:

* [PineNote Development/Apps](/documentation/PineNote/Development/Apps)

### Android

Android 11 e-ink SDK for the PineNote and Quartz64 Model A. This is the Android SDK build for 10.3" eink panels on Quartz64 Model A.

Download:

* [Direct download](http://files.pine64.org/SDK/Quartz64/QUARTZ64-model-A_eink.android11_SDK.tar.gz) from _pine64.org_ (72.88GB, MD5 of the TAR-GZip file _293a550584298de4fb95ceae18103672_)
* [Mirror by mwfc](https://tmp.mwfc.info/pinenote/QUARTZ64-model-A_eink.android11_SDK.tar.gz)
* An unofficial torrent download provided by a community member of the BSP Linux and Android SDKs can be found [here](https://cdn.discordapp.com/attachments/870707390998282292/907726420204208148/pinenote.torrent) (100GB).
* Just the boot blobs (&lt;1MB): https://wiki.pine64.org/wiki/File:Rk35-blobs.tar.gz

Notes:

* View [Android SDK for RK3566](/documentation/General/Android_SDK_for_RK3566) for more information how to compile an image for the PineNote using this SDK

### Related

* [Development](/documentation/Quartz64/Development) for the mainlining status of various functions on the Rockchip RK3566 SoC.

## Hardware

This section includes discussions and their results regarding hardware changes and debugging of the PineNote.

### Resolved issues

The following topics have resolved:

* [PineNote/Hardware Changes/Closed Case UART](/documentation/PineNote/Further_information/Closed_Case_UART)
* **Could the USB-C port support USB 3.1 5Gbps?** Yes and no. The RK3566 only has a host-mode 5Gbps controller, meaning it can only negotiate such a high data rate with a device such as a flash drive. When the RK3566 is acting as a device, it only supports 480Mbps transfer rates. The hardware required to switch between these modes would raise the PineNote’s price unreasonably. Therefore, the USB-C port will remain at USB 2.0 speeds for Host and Device mode.
* **Could the USB-C port output DisplayPort?** Yes and no. The hardware required to support such a feature would raise the PineNote’s price unreasonably. Therefore, DisplayPort output will not be possible through the USB-C port.
* **Where is the microSD card slot?** The case design of the PineNote is fixed, making physical changes like adding a microSD card slot would raise the cost unreasonably.
* **How will I install software to the PineNote?** This is a hardware and software question. If the software on your PineNote is completely broken and cannot boot to a recoverable state, a Hall (magnet) sensor was fitted to the PineTab motherboard as U9009. This sensor is attached to SARADC_VIN0_KEY/RECOVERY on the RK3566. With the device powered off, and screen face down, holding a magnet over U9009 and plugging in a USB-C cable causes the device to boot into ["rockusb"](http://opensource.rock-chips.com/wiki_Rockusb) flash mode. With proper flashing software and drivers, it should be possible to load a new operating system using rockusb if the system is soft-bricked. Of course, software vendors will need to be more careful with flashing firmware and providing useful "recovery" options on this device due to this process’s relative difficulty to other PINE64 devices.

### Unresolved issues

The following concerns have been brought up as open, unanswered topics:

* Does [Audio Adapter Accessory Mode](https://en.wikipedia.org/wiki/USB-C#Audio_Adapter_Accessory_Mode_2) work? It appears that the Headphone output of the audio codec was routed to the USB-C audio+USB switch, but it’s unclear whether CC lines are hooked up correctly for detection of such a device. The PineNote hardware team will be testing this functionality soon (as of August 19, 2021). Note that Audio Accessory mode is detectable by reading the I2C registers of the WUSB3801Q. So connecting ASEL to a GPIO would be enough to get this working if it is not working already.
* Why is the Headphone output of the audio codec routed to the speakers? HPL_OUT is routed from the RK817 PMIC and audio codec to U9010 (the USB-C switch) and U6 (the audio amplifier). SPK_OUT is unused. It seems like SPK_OUT should be routed to U6 and HPL_OUT to U9010.
* Nitpick: The cold white charging LED bleeds through the gap between the rear case and the device’s face. It does not bleed onto the screen, but it is jarring in low-light conditions or when the screen is amber. Could be resolved in software by turning off the charge LED when the screen is on.
* Is there any way to indicate when the device is in rockusb mode, such as connecting a certain magic pin to the power LED?
* The modem/4G connector (J6010) has its I2C and UART pins unconnected. Could those be connected to the SoC?

### UART Dongle

The USB UART dongle delivered with the PineNote allows you to have access to a serial port via USB-C Debug Accessory Mode (_DAM_) without having to open up the device.
The factory firmware runs at a baud rate of 1500000bps, 8 data bits 1 stop bit, no parity and no flow control. The USB-C male end should go into the PineNote and the female end can be connected with a standard USB-C cable to your computer.

It is relatively easy to build your own UART interface with a USB-C breakout board (for example https://www.ebay.com/itm/275407037613), two resistors and a 3.3V USB serial adapter. It is basically just two 1K pull up resistors (R3, R4), the data sheet values of 10K isn’t whats on the real hardware, see the [schematic](https://files.pine64.org/doc/PineNote/PineNote_USB-C_Console_UART_breakout_board_schematic_v1.0_20210903.pdf). The pull ups enable the serial output on SBU1 and SBU2 you can use with any 3.3V USB serial adapter.

The UART dongle is not necessary to flash the PineNote, but is essential if something goes wrong to fix it without having to open the case.

You can flash premade images with the following links:

* https://github.com/m-weigand/pinenote_uboot_patching_dorians_backup (Note: this creates a U-Boot image to flash, do not worry about idblock.bin on the instructions for the next link)
* https://github.com/m-weigand/pinenote-debian-recipes/releases/
