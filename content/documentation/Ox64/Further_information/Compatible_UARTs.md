---
title: "Compatible UARTs"
draft: false
menu:
  docs:
    title:
    parent: "Ox64/Further_information"
    identifier: "Ox64/Further_information/Compatible_UARTs"
    weight: 
---

When the Ox64 is in bootloader mode, some UARTs are unable to communicate with it. When this is the case, utilities such as BLDevCube are unable to actually program the device. If you see "Shake hand fail" and an empty ack, and your device is in bootloader mode, then it is likely an incompatible UART.

The below devices have been tested and verified as working:

* Raspberry Pi Pico - running the following [UART firmware](https://github.com/sanjay900/ox64-uart/releases/tag/v1.1) (GP4 and GP5 are used for port 0, GP12 and GP13 for port 1)
* Compiled binary for Pi Pico and connectivity diagram is [here](https://github.com/Kris-Sekula/Pine64_Ox64_SBC/tree/main/uart)
* ESP32 with CP210x - bridge the EN pin to ground to disable the ESP32 itself, and then connect the TX on the esp32 to 14 on the Ox64 and RX to pin 15. Note that only baud rate 115200 works, and this doesn’t seem to work for everyone)
* Stand-alone CP2102 dongle works at 115200 baud. Brand used was HiLetgo.
* STM32F401 BlackPill - running the Black Magic Debug firmware
* STM32F103C8T6 BluePill - running Black Magic Debug.
* STM32F103C8T6 BluePill - running [BluePill Serial Monster](/documentation/Ox64/Software/Flashing/#optional_preparing_serial_uart_adapter_stm32f103c8t6) 
* Some UART adapters based on the FT232H (note that the FT232RL does not work, and neither does the Pine 64 JTAG)
* Some CH340G based adapters work and some don’t.
