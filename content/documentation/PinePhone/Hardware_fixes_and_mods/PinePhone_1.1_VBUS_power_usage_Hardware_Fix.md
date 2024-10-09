---
title: "PinePhone 1.1 VBUS power usage Hardware Fix"
draft: false
hidden: true
menu:
  docs:
    title:
    parent: "PinePhone/Hardware_fixes_and_mods"
    identifier: "PinePhone/Hardware_fixes_and_mods/PinePhone_1.1_VBUS_power_usage_Hardware_Fix"
    weight: 
---

This page details a hardware fix for an issue that affects some early [v1.1 Braveheart](/documentation/PinePhone/Revisions) units (fixed since [1.2 community edition](/documentation/PinePhone/Revisions/PinePhone_v1.2) included).

The issue was _PinePhone_v1.1_-_Braveheart#Excess_power_usage_while_driving_VBUS_ by megi.

TODO: Add more pictures and schematics, better reference the fix origin and tradeofs, remove TODOs/FIXMEs.

## Affected Units

1. [PinePhone v1.1 - Braveheart](/documentation/PinePhone/Revisions/PinePhone_v1.1_-_Braveheart)

FIXME: confirm ["Project Don’t Be Evil" devkit](/documentation/PinePhone/Revisions/Project_Dont_be_evil) and [PinePhone v1.0 - Developer batch](/documentation/PinePhone/Revisions/PinePhone_v1.0_-Dev) are unaffected.

## Disclaimer

Though easier to perform than the [PinePhone 1.2 VCONN hardware fix](/documentation/PinePhone/Hardware_fixes_and_mods/PinePhone_1.2_VCONN_Hardware_Fix), this fix requires desoldering relatively small Surface Mount Technology (SMT) components, therefore some experience with soldering is recommended.

## Issue description

TODO: pictures

The AXP803 cannot detect when the USB port is powered by the battery. Therefore, the Power Management IC (PMIC) continues draining current from it. This is especially problematic since this USB port is powered from the battery with the USB OTG boost regulator. One of the symptoms is the battery discharging rather quickly even when the phone is powered off.

## Workaround

HW workaround is desoldering the U1301 regulator (TODO: describe its role) and shorting pads for R1309 on the PCB (this is a "0 ohm" resistor on the schematic, so it’s completely fine).

Shorting the pads is easy to do with some solder (while carefully avoiding to short it with nearby resistors).

Desoldering the regulator is harder to do, since its large pads are designed to use the PCB as a heatsink and will happily cool down while you are trying to melt it. It should be possible to use properly sized pliers to cut the pins first, please edit if you attempt this.

Please be careful not to overheat nearby components trough the PCB traces when applying heat to the regulator. It can be helpful to start the operation with melting some leaded solder tin together with the pads, and lifting the regulator while applying heat also helps. Start with the side that has only one pad: though it is bigger, it should be easier to lift up. It might be useful to apply a relatively large quantity of molten solder tin to each pin, in turn, while lifting the regulator, to reduce the PCB heatsink effectiveness.

Feel free to add your experiences and tips here.

### Tradeoffs

TODO: Unknown to the author

## Proper fix

TODO

## Sources and tutorials

* [Tutorial from megi](https://xnux.eu/devices/pp-pmic-fix.jpg)
* [Description from megi](https://xnux.eu/devices/feature/anx7688.html) at the end of the page
