---
title: "JTAG"
draft: false
menu:
  docs:
    title:
    parent: "PineCone"
    identifier: "PineCone/JTAG"
    weight: 2
---

| Default JTAG pins | |
| -------- | ------- |
| GPIO Pin | JTAG Pin |
| GPIO17 | TDI |
| GPIO11 | TDO |
| GPIO12 | TMS |
| GPIO14 | TCK |

BL602 multiplexes four GPIO pins to provide the familiar JTAG lines. See the accompanying table for the default pin mappings.

These are the default JTAG pins in use after a cold boot. However, many pieces of software, including the demo that's installed by default on new PineCones, remap these pins to other functions. You cannot use the default wiring for JTAG while such software is running. This issue is especially prevalent on the PineCone because three of the default JTAG pins are connected to the onboard RGB LED. Nothing about the LED itself interferes with JTAG, but any program that uses the LED will necessarily remap some of the default JTAG pins to be GPIO.

The MaskROM download mode that the BL602 enters when you tie GPIO8 high does *not* remap the default JTAG pins, and so you can and should use that mode while checking basic functionality of your JTAG adapter.

Note that, just as software can remap the default JTAG pins to be something else, it can also remap other pins to be JTAG. Control over this is quite granular, with 5-6 candidate pins for each individual JTAG signal that can be mapped independently of one another. LEE Lup Yuen has written some [sample code](https://lupyuen.github.io/articles/openocd#free-the-led-from-jtag-port) showing how to remap the JTAG pins so that your software can use the LED without giving up support for debugging.

## USB JTAG Adapter

The **USB JTAG Adapter** is an adapter with openOCD for Pinecone and Pinenut development.

### Features

* Using FTDI FT232H chipset
* Aluminum housing
* Dimension: 56.8 x 20.2 x 8.6 mm
* Include 20cm length 5 wires female-to-female DuPont cable

### Information and schematics

* [PINE64 USB JTAG Adapter Schematic-20201215.pdf (pine64_ft232hl_board-2020-12-14)](https://files.pine64.org/doc/Pinenut/PINE64%20USB%20JTAG%20Adapter%20Schematic-20201215.pdf)
* [PINE64 USB JTAG Adapter schematic 20210109 1.0a](https://wiki.pine64.org/wiki/File:PINE64_USB_JTAG_Adapter_Schematic_ver_1.0a-20210109.pdf)
