---
title: "Dock"
draft: false
menu:
  docs:
    title:
    parent: "Pinebook_Pro"
    identifier: "Pinebook_Pro/Dock"
    weight: 3
---

The **Pinebook Pro USB-C Docking Deck** can be used to extend the [Pinebook Pro](/documentation/Pinebook_Pro) with additional functionality. It is custom designed for both, physical dimensions and ports, to compliment the Pinebook Pro laptop. It has been tested on several disparate platforms and seems to be fully compatible with Android, Windows, ChromeOS, and GNU/Linux. It may be compatible with Apple systems, but this has yet to be documented.

## Ports

List of ports available on docking station:

* USB-C Charging Port x1
* USB 3.0 Ports x3
* USB-C 2.0 Ports x2
* 4K @ 30fps HDMI x1
* 1080P VGA x1
* Gigabit Ethernet networking port x 1
* Card readers: micro SD x 1 & SD x 1, supports: SD, SDHC and SDXC
* Audio Jack: 3.5mm Earphone Jack with mic x1

## Hardware Tests

**Acer Aspire e15**

Note that machine lacks USB-C video. Tested with both Windows 10 and Gentoo GNU/Linux. Every device functions properly with the exception of the microphone jack. In Linux, the jack will only function with its volume set at or above 98 in _alsamixer_. This is uncomfortably loud. 8/10 for compatibility.

**iPad Air (4th generation)**

USB dock functions for fast charging and input from USB keyboard and mouse peripherals. Audio jack does not function under any tested circumstances. Bluetooth audio disabled when dock in use. Other devices not tested. 8/10

**Samsung Chromebook Plus V2**

Everything functions perfectly, with the exception of Ethernet, which was not tested. 9/10.

**Google Pixel 4a**

Note that the machine lacks USB-C video. Using android version 11. Video and Ethernet were not tested. Everything else functioned properly. 8/10.

**PineBook Pro**

Using Manjaro ARM minimal with dwm. Video out, USB, and SD card readers all work. Did not test Ethernet or audio jack. 8/10.

Using devuan ARM & debian ARM, xfce4. Did not test Video out. USB and SD card readers work. Ethernet is working at full speed. The Docking Deck is able to negotiate USB-C 9V 1.6A and convert to 5V 2.5A for the PBP. No charging issues; the PBP makes some noise, but that isn’t the docking deck’s fault. Audio out is working. Note that adding another audio device obviates the need for the audio device default to be restored on reboot, which did not work on xfce4. 9/10.

**PinePhone Pro Explorer Edition**

With Mobian: jack, Ethernet, SD-card readers, USB-A and -C, VGA fully works, HDMI lacks sound output. Video-out works fully on Mobian. 9/10

## Known Bugs

### Audio Volume on Linux

Currently, the audio output from this dock

On some Linux systems, and possibly all of them, the volume range for headphones from audible to loud is from 64562-64575 to 65000. That’s absolute, not percentages. This is an extremely tiny range -- completely impossible to navigate with percentages, and dangerous as well. For the time being, this audio output should be treated as unsafe for human health, as well as the health of your speakers. To ensure safe audio levels, users can switch to the digital output to lower the volume to a safe level.

### Pinebook Pro does not charge when connected to USB-C dock

It has been observed in the past that the Pinebook Pro is somewhat temperamental when used with the USB-C dock. Sometimes it will not charge when connected to its dock, even if the dock is powered from the official Pinepower power supply (i.e., even when it is provided with sufficient power). The more astute may have surmised that the Pinebook Pro was powering the dock, rather than being powered itself. The solution, luckily, is quite simple. The following command should always work:

    echo "sink" | sudo tee /sys/class/typec/port0/power_role

Please note:

1. This command cannot be run with sudo, you must be the root user.
2. If this command still fails with the message "bash: /sys/class/typec/port0/power_role: No such file or directory" Please ensure that the file actually exists. The most likely cultprits are that either /sys/class/typec does not exist or /sys/class/typec/port0 has a different name on your machine.

### Unable to output to external display

Unplug the dock cable turn 180 degrees reinsert in new orientation. (Sometimes works for charging the laptop too.)

## Components

List of chips used in the docking station:

* PD Negotiation chip - PDFL7102
* HDMI/VGA chip - IT6564
* GbE Ethernet chip - RTL8153B
* USB 3.0 Hub chip - VL817
* SD card reader chip - GL823K
* Audio CODEC chip - HZD100

## External Links

* [The Pinebook Pro Docking Deck at the Pine64 store](https://pine64.com/product/pinebook-pro-usb-c-docking-deck/)
* [The "Pinebook Pro Hardware and Accessories" section of the Pine64 forum](https://forum.pine64.org/forumdisplay.php?fid=116)
