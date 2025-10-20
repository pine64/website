---
title: "FAQ"
draft: false
toc: false
menu:
  docs:
    title:
    parent: "PineTime"
    identifier: "PineTime/FAQ"
    weight: 6
aliases:
  - /wiki/PineTime_FAQ
---

## Does PineTime run Linux?

No. [Please read this forum article](https://forum.pine64.org/showthread.php?tid=8112) for information about Linux on PineTime. Also check out the article ["PineTime doesn’t run Linux... But that’s OK!"](https://lupyuen.github.io/pinetime-rust-mynewt/articles/pinetime)

## Why are there two versions of the PineTime in the store?

See the below question and answer.

## Why can I only buy the closed version in a 3-pack, and the open version per one?

TL:DR: The unsealed PineTime is for development, the sealed one is for production use, because of firmware uploads. That is also why they were initially sold three in a pack.

In the current situation in development there are some reasons to want to be sure you only experiment with an open device. If you install the wrong firmware, your device could be bricked, until you find a way to open it, which will likely damage the device.
The idea is that if you want to develop an application for the PineTime, you will be testing it out first, and only after you know for sure your new firmware is well tested, you will install it on sealed devices. If you are in the beta stage, having more than one PineTime is probably a good idea. So to prevent people from locking themselves out at the first test, it was decided to sell the closed version only as a pack of 3. Development can be done on an open device, so any issues can be easily handled.

## How long does it take to ship my PineTime?

That depends on whether you chose for Standard or Express shipping. Standard shipping for the dev kit may take up to a few weeks.

## How do I install new software on PineTime?

If you have a Sealed PineTime, flash only tested PineTime Firmware to your PineTime. If you flash unknown PineTime Firmware, your sealed PineTime may be bricked relatively permanently.

There is a lot of different software for flashing. Check out [Development](/documentation/PineTime/Development) page for a list of companion software.

Also see [this page to see various methods of reprogramming the devkit PineTime the wired way](/documentation/PineTime/Software/Reprogramming/).

Remember to validate the firmware after flashing: Swipe up to show the menu, tap the checkmark icon, tap "Validate".

## My PineTime arrived, now what?

You should start by testing out all the features of the watch, to make sure everything works. Power it on and check the display.

PineTime is shipped with InfiniTime firmware. Press the watch button to show the clock, then swipe up on the touchscreen to reveal the menu.

You probably now wish to update the bootloader and firmware.

## What's the OS that's preinstalled on the PineTime by default?

PineTime ships with the open source [InfiniTime firmware](https://github.com/JF002/InfiniTime).

To support firmware update and rollback, PineTime includes the open source [MCUBoot Bootloader](https://lupyuen.github.io/pinetime-rust-mynewt/articles/mcuboot).

## Can we use this OS or its source code?

Yes, [InfiniTime](https://github.com/JF002/InfiniTime) and the [MCUBoot Bootloader](https://lupyuen.github.io/pinetime-rust-mynewt/articles/mcuboot) are open source.

## Why is the back exposed? Is it supposed to snap on?

The back cover of the PineTime devkit is exposed so that you can flash and debug the device with the SWD pins. The main unit and cover does not snap (lock) together. If you want to attach the back cover anyway, you can use glue or tape.

## What hardware should I use to flash code to the PineTime?

There are several ways you can do this, check out [Reprogramming the PineTime](/documentation/PineTime/Software/Reprogramming/)

## How do I connect the PineTime to a programmer?

Here’s how: [Devkit wiring](/documentation/PineTime/Further_information/Devkit_wiring)

## How do I set the time on PineTime?

In recent versions of the firmware, you can set it directly from settings.

You can also use either GadgetBridge or the closed-source nRF Connect and Da Fit apps. See ["Set PineTime Date and Time with nRF Connect"](https://lupyuen.github.io/pinetime-rust-mynewt/articles/cloud#set-pinetime-date-and-time-with-nrf-connect)

You can also set the time using your PinePhone or other Linux-based Bluetooth LE capable device with the Bluez software installed. Install the bluez package and make sure your PineTime is running and awake with InfiniTime 0.7.1 or later.

```console
$ bluetoothctl
[ bluetooth ]# scan on
...
[NEW] Device D7:03:FB:6E:31:B2 Pinetime-JF
...
[bluetooth]# pair D7:03:FB:6E:31:B2
Attempting to pair with D7:03:FB:6E:31:B2
...
[NEW] Characteristic (Handle 0xfd80)
  /org/bluez/hci0/dev_D7_03_FB_6E_31_B2/service0015/char0016
  00002a2b-0000-1000-8000-00805f9b34fb
  Current Time
...
[Pinetime-JF]# menu gatt
...
[Pinetime-JF]# select-attribute /org/bluez/hci0/dev_D7_03_FB_6E_31_B2/service0015/char0016
[Pinetime-JF:/service0015/char0016]# read
Attempting to read /org/bluez/hci0/dev_D7_03_FB_6E_31_B2/service0015/char0016
[CHG] Attribute /org/bluez/hci0/dev_D7_03_FB_6E_31_B2/service0015/char0016 Value:
  b2 07 01 01 00 04 15 00 00                       .........    
  b2 07 01 01 00 04 15 00 00                       .........
[Pinetime-JF:/service0015/char0016]# write "0xe4 0x07 0x0c 0x1f 0x0e 0x02 0x00 0x00 0x00"
```

Use the list-attributes command to find the correct path. Look for the characteristic named 'Current Time'

This is the format for the current time as hex bytes:

    <lsb of year> <msb of year> <month (1-12)> <day (1-31)> <hour (0-23)> <minute (0-59)> <seconds (0-59)> <weekday (1-7 where Monday)> <fractions (1/256th of second)>

## Is there a standard agreed method of pushing OTA updates so that one could seal the PineTime dev kit nicely?

InfiniTime supports firmware updates over Bluetooth LE with the nRF Connect mobile app. See ["Download and Test Our PineTime Firmware"](https://lupyuen.github.io/pinetime-rust-mynewt/articles/cloud#download-and-test-our-pinetime-firmware)

## My PineTime's screen shows garbage, how do I fix it?

This is usually caused by unplugging the device after it has booted, it needs to be reinitialised. To do so just restart the watch by removing power to it.

## I have experience developing on Arduino. How does the PineTime compare?

To learn programming on PineTime, [check out this article](https://lupyuen.github.io/pinetime-rust-mynewt/articles/cloud)

Arduino provides the Arduino IDE (or you use the avr-gcc and avrdude command-line tools) which you can use to compile and upload code to an Arduino board. The PineTime and its ARM processor doesn’t have this, so you’ll have to familiarize yourself with tools like GCC for ARM, and OpenOCD. Some experience with Arduino does translate over to the PineTime, especially if you’ve worked with LCD’s, or SPI. The PineTime is at least four times faster than an Arduino Uno (even faster at certain specific workloads due to hardware acceleration), and it has 32 times more RAM and 16 times more flash storage.

[Lup Yuen Lee](https://github.com/lupyuen/) (just call him Lup, rhymes with "Up") has written many articles on PineTime programming. [Check out the articles here](https://lupyuen.github.io/)

## Can I code firmware for PineTime without an actual PineTime?

Yes, you may code PineTime Watch Faces and preview them in a web browser (thanks to WebAssembly).

[PineTime Simulator](https://lupyuen.github.io/pinetime-rust-mynewt/articles/simulator)

Then flash your firmware remotely to a real PineTime via Telegram, and watch your firmware run in a live video stream.

[Remote PineTime](https://github.com/lupyuen/remote-pinetime-bot/blob/master/README.md)

## What do I need for building PineTime firmware locally on my computer?

Most flavours of PineTime firmware (InfiniTime, Hypnos, Klok, wasp-os) will build fine on Linux (x64, Arm32, Arm64) and macOS. Just follow the instructions provided.

Download version 9-2020-q2-update of the [Arm Embedded Toolchain arm-none-eabi-gcc](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads). Other versions of gcc may have problems building the firmware correctly.

On Windows, install [Windows Subsystem for Linux (WSL)](https://docs.microsoft.com/en-us/windows/wsl/about) and execute the build steps inside the WSL Terminal (instead of the Windows Command Prompt). USB Programmers (like ST-Link and JLink) are not supported in WSL, so use the Windows Command Prompt to flash your built firmware to PineTime.

[pinetime-rust-mynewt](https://github.com/lupyuen/pinetime-rust-mynewt/blob/master/README.md) firmware for PineTime supports building and flashing via the Windows Command Prompt (no need for MinGW and Docker).

## Can I use Pinebook Pro for developing PineTime?

Yes, use version 9-2020-q2-update of the [Arm Embedded Toolchain arm-none-eabi-gcc](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads). Other versions of gcc may have problems building the firmware correctly.

## What is ARM Semihosting?

We use the SWD (Single Wire Debug) protocol created by ARM for flashing and debugging PineTime’s nRF52832 microcontroller, which contains an ARM CPU. (SWD is derived from standard JTAG, but with fewer wires) With ARM CPUs you can trigger a software breakpoint, and allow the debugger (OpenOCD) to do something really nifty: Display a message, read console input, dump out a file, even read a file. That’s called ARM Semihosting. [More about ARM Semihosting](https://developer.arm.com/documentation/dui0375/g/What-is-Semihosting-/What-is-semihosting-)

## What is OpenOCD?

OpenOCD is Open On-Chip Debugger. It’s the software that drives your microcontroller debugger/flasher. We need it for running any kind of flashing and debugging with Pi or ST-Link. gdb talks to OpenOCD for debugging firmware. gdb also works with VSCode for debugging firmware visually. [More about OpenOCD](https://openocd.org/doc-release/html/About.html#What-is-OpenOCD_003f)

Please use [xPack OpenOCD](https://xpack.github.io/openocd) with PineTime. Other versions of OpenOCD seem to have problems with PineTime.

## How do I remove flash protection?

PineTime watches shipped before 20 Sep 2020 have flash protection enabled.

The flash protection can be removed using multiple different methods. If you don’t have anything except the PineTime, not even a Raspberry Pi, then you have to order a programmer online: you can use a J-Link, CMSIS-DAP dongle and various other programmers. See [this page to see various methods of reprogramming the PineTime](/documentation/PineTime/Software/Reprogramming/).

If your PineTime was shipped after 20 Sep 2020, you don’t need to remove flash protection. They are shipped with flash protection disabled. You can flash and debug PineTime right away with ST-Link, JLink and Raspberry Pi.

## Why can't you use ST-Link to remove nRF52 Flash Protection?

Because ST-Link is a High Level Adapter. It doesn’t really implement all SWD functions, just a subset (probably to keep the price low). More details in the section "Why Visual Studio Code with ST-Link (instead of nRFgo Studio with J-LINK)" in the article ["Coding nRF52 with Rust and Apache Mynewt on Visual Studio Code"](https://medium.com/@ly.lee/coding-nrf52-with-rust-and-apache-mynewt-on-visual-studio-code-9521bcba6004?source=friends_link&sk=bb4e2523b922d0870259ab3fa696c7da).

## Since we need a low level SWD adapter like Raspberry Pi anyway, can we do everything on a Pi instead of ST-Link + Windows?

Yes, Raspberry Pi works for flashing and debugging PineTime, even for removing flash protection. We have a special version of OpenOCD called OpenOCD SPI that talks to PineTime’s SWD port over SPI (without bit-banging). See [PineTime Updater](https://github.com/lupyuen/pinetime-updater/blob/master/README.md)

## Is there a 3D model of PineTime available somewhere?

Not yet. Someone did design a cover you can snap on to keep the back shut. [More details](https://www.thingiverse.com/thing:4172849)

## Are there any alternatives to the wrist band provided with the PineTime?

No, but PineTime accepts standard 20mm wrist band that is widely available by a third party.

Note that some sellers have a different point of view on what standard is. So you should always check the fitting to make sure it looks like the one used by PineTime.

## Troubleshooting PineTime's Bluetooth (InfiniTime firmware)

Old (pre 1.4) InfiniTime firmware had an issue where Bluetooth connectivity sometimes gets lost/fails.

The fix was to soft-reset the watch, by holding the PineTime button for ~8 seconds until the PineCone logo appears.

## Does PineTime have an audible beeper or speaker?

No, but in practice the vibration component is a substitute for use with alerts.
