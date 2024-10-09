---
title: "PinePhone v1.2a"
draft: false
hidden: true
menu:
  docs:
    title:
    parent: "PinePhone/Revisions"
    identifier: "PinePhone/Revisions/PinePhone_v1.2a"
    weight: 
---

The PinePhone v1.2a is a hardware revision of the [PinePhone](/documentation/PinePhone) that started shipping in Q3 2020.

This page contains information and resources which are specific to the v1.2a revision of the PinePhone. For other revisions or for resources related to all PinePhone revisions, see [PinePhone](/documentation/PinePhone/Revisions).

## Schematics

* [Hardware schematic v1.2a](http://files.pine64.org/doc/PinePhone/PinePhone%20v1.2a%20Released%20Schematic.pdf) (2020-06-08, for the postmarketOS Community Edition)

## Changes from v1.2

* A thermal pad was added to the SoC alongside a graphene foil covering the metal shielding of the mainboard which is in direct contact with the LCD backplane to help dissipate heat. Another graphene foil sticker was added to the rear cover of the device to help disperse thermals from the back of the modem.
* Fixed a rectangular dead spot of the touchscreen under the speaker grill
* Antenna changes
* USB-C CC fix for video out and OTG functionality

## Known issues

The backlight issue of v1.2 is still present, see [PinePhone v1.2](/documentation/PinePhone/Revisions/PinePhone_v1.2#backlight). There is also another backlight issue, where the brightness is lower when connecting a VBUS powered device, https://xnux.eu/log/#022. See [PinePhone 1.2b R1318 backlight hardware fix](/documentation/PinePhone/Hardware_fixes_and_mods/PinePhone_1.2b_R1318_backlight_Hardware_Fix).
