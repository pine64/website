---
title: "Reprogramming the PineTime"
draft: false
menu:
  docs:
    title:
    parent: "PineTime/Software"
    identifier: "PineTime/Software/Reprogramming"
    weight:
---

## Introduction

The PineTime Dev Kit comes with the back not glued down to allow it to be easily reprogrammed, however the kit does not include an hardware programmer/debugger.

Before you can use your debugger/programmer, you probably have to [wire up your pinetime](/documentation/PineTime/Further_information/Devkit_wiring). Heavily recommended you read this first.

There is a bewildering variety of different hardware programmers available but whatever programmer you have there are only a few tasks you will have to learn about:

* Unlocking the device **Note: PineTime watches shipped after 20 Sep 2020 do not require unlocking. They are shipped unlocked.**
* Uploading new software
* Running a debugger

All of these are described in this article.

Unlocking the device is a one-time action that is needed to enable the debug port and provide full access to the device. Unlocking the device will erase all existing software from the internal flash.

## SWD Pinout

See [Devkit wiring](/documentation/PineTime/Further_information/Devkit_wiring)

## nrfjprog (for Segger JLink)

The following steps have been tested with the Segger JLink embedded in the [NRF52-DK development board](https://www.nordicsemi.com/Software-and-Tools/Development-Kits/nRF52-DK).

### Hookup

Connect the Pinetime SWD pins to the debugger (P20 on NRF52-DK)

|     |     |
| --- | --- |
| Pinetime | JLink |
| GND | GND |
| SWDCLK | SWDCLK |
| SWDIO | SWDIO |
| VCC (3.3V) | VTG (target detect) |

### Unlocking the FLASH

Unlocking the device and erase the memory.

**You need to execute this step only once, to remove the read protection on the memory. Note that it will erase the whole flash memory of the MCU|** :

    nrfjprog -f NRF52 --recover

### Uploading new software

1. Program the BLE softdevice (if needed by the firmware). Replace PATH_TO_NRF_SDK by the path where you unzipped the [NRF52 SDK](https://www.nordicsemi.com/Software-and-Tools/Software/nRF5-SDK) :

       nrfjprog -f NRF52 --program /PATH_TO_NRF_SDK/components/softdevice/s132/hex/s132_nrf52_6.1.1_softdevice.hex --sectorerase
2. Program the firmware (replace firmware.hex by the actual filename of the firmware):

       nrfjprog -f NRF52 --program firmware.hex --sectorerase
3. Reset and run the new firmware:

       nrfjprog -f NRF52 --reset

## OpenOCD

OpenOCD, the Open On-Chip Debugger supports multiple different adapters. You can read more about it here: https://openocd.org/

### Adapters

These examples allow you to use telnet to issue futher commands to the devkit. Using them you can connect to _127.0.0.1_ (_localhost_) port _4444_ using telnet and invoke OpenOCD commands. GDB should also be available on port _3333_.

You can simplify your life by creating a configuration file that contains the interface, transport, target and speed configuration. Things like CLion also need one to work properly.

If you aren’t using the latest version of OpenOCD, you might need to substitute things in these examples with older syntax (e.g. instead of _adapter speed_ it’s _adapter_khz_).

#### CMSIS-DAP

This is a generic specification that is supported by a bunch of different hardware, things such as DAPLink also use it.

Issue this command to initialize a connection to the devkit:

    openocd \
       -c 'source [find interface/cmsis-dap.cfg]' \
       -c 'transport select swd' \
       -c 'source [find target/nrf52.cfg]' \
       -c 'adapter speed 8000' \
       -c 'init'

#### JLink

Start OpenOCD:

    openocd \
       -c 'source [find interface/jlink.cfg]' \
       -c 'transport select swd' \
       -c 'source [find target/nrf52.cfg]' \
       -c 'adapter speed 8000' \
       -c 'init'

#### Raspberry Pi

    openocd \
       -c 'source bcm2835spi' \
       -c 'bcm2835spi_speed 31200' \
       -c 'source [find target/nrf52.cfg]' \
       -c 'init'

#### STLink

Connect PineTime SWD Pins to ST-Link v2 as follows:

|     |     |
| --- | --- |
| PineTime | ST-Link |
| GND | GND |
| SWDCLK | SWDCLK |
| SWDIO | SWDIO |
| VCC (3.3V) | 3.3V |

{{< figure src="/documentation/images/pinetime-stlink.jpg" width="400" >}}

Note that only the bottom row of pins on ST-Link are used.

To flash PineTime with ST-Link on Linux and macOS, use [PineTime Updater](https://github.com/lupyuen/pinetime-updater/blob/master/README.md)

[**ST-Link can’t be used to remove nRF52 flash protection**](/documentation/PineTime/FAQ)

### Unlocking the device

If you need to disable access port protection then you can do this using the following commands below.

This can be done in two ways:

Appending this to OpenOCD command line:

    -c 'nrf52.dap apreg 1 0x04' -c 'nrf52.dap apreg 1 0x04 0x01' -c 'nrf52.dap apreg 1 0x04'

Or by using the telnet connection, just type in _telnet localhost 4444_ and then you can issue commands to OpenOCD:

Note: _Unlocking the device to remove access port protection will erase the contents of flash._

    telnet localhost 4444
      Trying 127.0.0.1...
      Connected to localhost.
      Escape character is '^]'.
      Open On-Chip Debugger
      > nrf52.dap apreg 1 0x04
      0x00000000
      > nrf52.dap apreg 1 0x04 0x01
      > nrf52.dap apreg 1 0x04
      0x00000001

(If the _nrf52.dap_ command cannot be found, try just _dap_ instead.)

### Uploading new software

Just issue this command, replace _code.hex_ with your own (and cmsis-dap.cfg with an appropriate adapter).

    openocd \
        -c 'source [find interface/cmsis-dap.cfg]' \
        -c 'transport select swd' \
        -c 'source [find target/nrf52.cfg]' \
        -c 'init' \
        -c 'halt' \
        -c 'nrf5 mass_erase' \
        -c 'program code.hex verify' \
        -c 'reset' \
        -c 'exit'

## Black Magic Probe

BlackMagic Probe is an JTAG/SWD adapter with open-source firmware, allowing for it to be ported to a multitude of different boards. One of it’s defining features is lack of need for intermediate software such as OpenOCD - one would just need to connect to the GDB server running on the chip and proceed with debugging. For more information, refer to [wiki](https://github.com/blacksphere/blackmagic/wiki).

### Native adapters

The native adapters are the official Black Magic family of debug adapters, including the original Black Magic Probe and the Black Magic Probe Mini. By buying the official hardware you are supporting the continued development of the Black Magic Probe software.

Providing your native adapter is running up-to-date firmware then it can be used to program your PineTime.

### STM32 (Blue Pill)

It is possible to flash a popular development board based on STM32F103C8T6 microcontroller, known as Blue Pill, to make a BlackMagic Probe device. For example, one may follow instructions in [forum post](https://forum.pine64.org/showthread.php?tid=8816&pid=57095#pid57095) or [gist](https://gist.github.com/darnel/dac1370d057e176386ca4026418abc2b) (mac os). Also, it is possible to use SWD pins on the board to flash other devices, instead using arbitrary pins on the board itself. See [this link](https://buger.dread.cz/black-magic-probe-bmp-on-bluepill-stm32f103c8-minimum-system-development-board.html) for more detals.

### Other hardware

The Black Magic Probe firmware can be run on a variety of host devices. See [BMP Debugger Hardware](https://github.com/blacksphere/blackmagic/wiki/Debugger-Hardware) for more information.

### Using the BMP to flash the PineTime

Refer to the BMP [wiki](https://github.com/blacksphere/blackmagic/wiki/Useful-GDB-commands) for the full description of commands.
Overall, the process on Linux is like following. (/dev/ttyBmpGdb is a symlink created by the udev rule). It’s useful to create a gdb script file (or .gdbinit) with following commands:

    target extended-remote /dev/ttyBmpGdb
    monitor swdp_scan
    attach 1
    file %firmware file%

Then one may use **load** command to flash the firmware, **compare-sections** to verify the upload, or **monitor erase_mass** to erase the firmware.

Then, proceed with debugging as normal.

## External links and additional tutorials

* https://github.com/jlukanc1/pinetime-boot-flasher
* https://blog.aegrel.ee/absniffer-cmsis-dap-sniffer.html
* https://blog.dbrgn.ch/2020/5/16/nrf52-unprotect-flash-jlink-openocd/
* https://medium.com/@ly.lee/openocd-on-raspberry-pi-better-with-swd-on-spi-7dea9caeb590
* https://medium.com/@ly.lee/build-and-flash-rust-mynewt-firmware-for-pinetime-smart-watch-5e14259c55
