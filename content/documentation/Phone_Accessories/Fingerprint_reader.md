---
title: "Fingerprint Reader Add-on"
draft: false
menu:
  docs:
    title:
    parent: "Phone_Accessories"
    identifier: "Phone_Accessories/Fingerprint_reader"
    weight: 5
---

Store page: [pine64.com](https://pine64.com/product/pinephone-pinephone-pro-fingerprint-reader-add-on-case/)

{{< figure src="/documentation/images/PinePhone-FP-Addon.jpg" width="250" >}}

Uses the pogo pins to interface a high quality fingerprint sensor, which uses open firmware for it’s i2c bridge, and can also be used for gesture navigation thanks to it’s ability to detect directional swipes.

{{< admonition type="important" >}}
No PinePhone operating system has added support for the fingerprint reader yet.
{{< /admonition >}}

## Credits

Credit goes to the user _zschroeder6212_, who carried the PinePhone Fingerprint Cover project from an idea to a real product. Their progress can be followed on GitHub under https://github.com/zschroeder6212.

## Schematics and Datasheet

Schematic:

* [PinePhone Finger Print Back Cover Schematic ver 3.0 20210124](https://files.pine64.org/doc/PinePhone/Schematic_fingerprint%20driver%20board%20V3_2021-01-24.pdf)

Datasheet:

* [P2SD Personal Identity Authentication Module Datasheet](https://files.pine64.org/doc/datasheet/pinephone/Datasheet_PixelAuth_PIA_Module_P2SDS-NABL2-S05_V7.0.0.5.pdf)
* [ATmel ATtiny Microcontroller Datasheet](https://files.pine64.org/doc/datasheet/pinephone/ATmel%20ATTiny%20Microcontroller%20Datasheet.pdf)

I2C to SPI firmware:

* [zschroeder6212’s tiny-i2c-spi Github page](https://github.com/zschroeder6212/tiny-i2c-spi)
