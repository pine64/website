---
title: "SD MCUBoot"
draft: false
menu:
  docs:
    title:
    parent: "PineTime/Flashing"
    identifier: "PineTime/Flashing/SD_MCUBoot"
    weight: 
---

## The Problem

* PineTime ships with the MCUBoot bootloader which boots to the [InfiniTime](/documentation/PineTime/Software/InfiniTime) Firmware
* This assumes that the firmware ([InfiniTime](/documentation/PineTime/Software/InfiniTime), Mynewt, Zephyr, ...) has its own Bluetooth LE (BLE) stack and can handle firmware updates (DFU)
* But some firmware (wasp-os, ATCwatch) require Nordic SoftDevice to be installed to support the BLE and DFU functions
* [InfiniTime](/documentation/PineTime/Software/InfiniTime) Firmware does not support flashing of SoftDevice as firmware update, because SoftDevice is usually flashed at address 0x1000 (plus a 4k MBR at 0 to switch between the bootloader and the softdevice), which is used by the MCUBoot Bootloader

## How do we allow SoftDevice-based firmware to be flashed to PineTime via DFU?

### Dual Bootloader Modes

#### Process

* PineTime will support 2 Bootloader Modes: [MCUBoot](https://github.com/JuulLabs-OSS/mcuboot/wiki) and SoftDevice. Default is MCUBoot Mode.
* The two bootloaders will not coexist, they will be mutually exclusive. This allows a different flash ROM map for each bootloader.

To switch from MCUBoot Mode to SoftDevice Mode:

* We will use DFU to flash a SoftDevice Loader Firmware, which will boot and replace MCUBoot by SoftDevice
* Thereafter, when PineTime boots, it will start SoftDevice and will be ready to accept SoftDevice-based firmware for DFU: wasp-os, ATCWatch

To switch from SoftDevice Mode to MCUBoot Mode:

* When we need to switch back to MCUBoot-based firmware (InfiniTime, Mynewt, Zephyr, ...), we will run an MCUBoot Loader (based on https://github.com/daniel-thompson/wasp-reloader
) to replace SoftDevice by MCUBoot plus a Minimal DFU Firmware that accepts DFU commands
* After rebooting, MCUBoot starts the Minimal DFU Firmware, which will accept MCUBoot-based firmware for flashing
* The MCUBoot-based firmware replaces the Minimal DFU Firmware

#### Switching modes with Companion App

* The PineTime Companion App (e.g. Gadgetbridge) will switch modes automatically depending on the firmware to be flashed. So PineTime Owners will never have to switch modes themselves.
* For SoftDevice-based firmware, the Companion App will also know which SoftDevice version is needed by the firmware, and load the right SoftDevice version.

### Custom MBR

It’s possible to customise (SoftDevice’s) MBR so that it can coexist with MCUBoot.

**Pros:**

* Seamless switching between the two different boot modes. Both MCUBoot and SD can be used.

**Cons:**

* Technically more complex - documentation isn’t the best, SoftDevice’s future support for custom MBR might be unknown

Should be explored further.

#### External resources about custom MBR

* https://devzone.nordicsemi.com/f/nordic-q-a/27599/boot-sequence-for-nrf52832
* https://aykevl.nl/2018/01/mbr-softdevice-internals
* https://forum.pine64.org/showthread.php?tid=9779&pid=65203#pid65203

#### wasp-reloader

wasp-reloader is a simple bare-metal C program that, in a fairly brutal fashion, can rewrite critical parts of the internal flash. It has fairly robust checksumming to avoid flashing problems and verifies that what it written is what is supposed to be written. Having said that more checks (no self-overwrite, battery level) would be nice. When complete it stops updating the watchdog in order to provoke get a clean reset. As a standalone app it can be loaded into the secondary slot using Infinitime DFU upgrade.

Currently it has linker scripts for SD132 V6.1.1 and can flash any payload smaller than SD132.

To be used to install SoftDevice from mcuboot it would need linker scripts for mcuboot (to ensure the reloader sits high enough in flash to avoid a self-overwrite). To install mcuboot we need an Intel HEX file of the mcuboot payload **and** InfiniTime (we have to write it in one shot to keep BLE updates working after switching bootloaders). This may need custom linker scripts depending on how big the Infinitime binaries are.
