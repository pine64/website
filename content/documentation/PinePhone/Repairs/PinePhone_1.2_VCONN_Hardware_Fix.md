---
title: "PinePhone 1.2 VCONN Hardware Fix"
draft: false
hidden: true
menu:
  docs:
    title:
    parent: "PinePhone/Repairs"
    identifier: "PinePhone/Repairs/PinePhone_1.2_VCONN_Hardware_Fix"
    weight:
aliases:
  - /documentation/PinePhone/Hardware_fixes_and_mods/PinePhone_1.2_VCONN_Hardware_Fix/
  - /wiki/PinePhone_1.2_VCONN_Hardware_Fix
---

This page details a hardware fix for an issue that was found on early PinePhone hardware revisions (see [PinePhone](/documentation/PinePhone/Revisions/) for an overview of the different revisions) and has been fixed since the 1.2a hardware revision.

The issue was _PinePhone_v1.1_-_Braveheart#USB-C_CC_pins_are_pulled_to_the_GND_by_AW3512_.28VCONN_switches.29_when_VCONN_is_off_ by megi.

## Affected Units

1. Requires confirmation: ["Project Don’t Be Evil" devkit](/documentation/PinePhone/Revisions/Project_Dont_be_evil)
2. Requires confirmation: [PinePhone v1.0 - Developer batch](/documentation/PinePhone/Revisions/PinePhone_v1.0_-Dev)
3. [PinePhone v1.1 - Braveheart](/documentation/PinePhone/Revisions/PinePhone_v1.1_-_Braveheart)
4. [PinePhone v1.2 - UBports Community Edition](/documentation/PinePhone/Revisions/PinePhone_v1.2)

## Disclaimer

This fix requires desoldering tiny (1 mm per 1 mm, from the datasheet) BGA components, therefore some experience with soldering is highly recommended.

## Issue description

{{< figure src="/documentation/images/Martjin_VCONN_switches_1.1.jpg" title="Close-up picture of the two identical switches the issue originates from, with the ANX USB controller in the frame" >}}

{{< figure src="/documentation/images/Schematic_VCONN_switches.png" title="Excerpt from the PinePhone schematic showing the two components." >}}

The USB standard [specifies](https://microchipdeveloper.com/usb:tc-pins) that both halves (top and bottom) of the USB-C port contains one "CC" pin (CC1 and CC2, respectively). A regular cable will connect a CC pin from one end to the other end. This allows detecting which way the cable is plugged. Some active USB-C cables exist (both "e-marked" and "managed active cables"); they contain a chip, which needs to be powered. This is done by having one of the cable end connect its CC pins to 5V and VCONN, and requires switches to plug the right CC pin to the right voltage.

The issue arises due to the switches that were chosen up to v1.2a (the a revision excluded) of the PCB assembly: the [infamous AW3512](https://www.awinic.com/cn/index/pageview/catid/122/id/2.html), labelled U1305 and U1309 on the schematic. Instead of leaving the output pin "dangling" with a high impedance when disabled, the switch pull the output down. This feature is intended for discharging a capacitor, hence its "Quick output discharge" name. This is an excerpt from the datasheet:

"The AW3512/AW35122 includes the Quick Output Discharge (QOD) feature, in order to discharge the application capacitor connected on OUT pin. When EN pin is set to low level (disable state), a discharge resistance with a typical value of 276Ω (AW35122: 75Ω) is connected between the output and ground, pull down the output and prevent it from floating when the device is disabled."

This issue prevents cable plug/orientation detection and USB-PD communication. ANX always sees cable as plugged even if none is plugged. There’s no SW workaround for automatic detection of cable plug or power role.

In SW this could theoretically be worked around by manual selection of PinePhone’s data and power role by the user, but hasn’t been attempted, and might damage hardware if done incorrectly.

## Workaround

{{< figure src="/documentation/images/Pinephone_v1.1_VCONN_fix_diagram.svg" width="130])]" >}}

Hardware workaround is desoldering U1305 and U1309 switches (BGA like packages). This will void the VCONN control, but it will release the CC pins for their proper connection detection and negotiation roles.

### Tradeoffs

Voiding the VCONN control might (TODO: gather more data) prevent some accessories from working, notably those using an active cable.

## Proper fix

HW fix is to replace AW3512 with a variant of the chip that preserves the EN signal polarity and that doesn’t have the "quick discharge function" that ties the output to the GND via a 75 Ohm resistor when the switch is OFF. mozzwald used NCP334FCT2G as a replacement. PCBA revision 1.2a onwards incorporate that fix.

## Sources and tutorials

* [megi’s writeup](https://xnux.eu/devices/pp-usbc-fix.jpg)
* [another writeup from megi](https://xnux.eu/devices/feature/anx7688.html) with a few words on firmware
* [Video: "The right way"](https://www.youtube.com/watch?v=xf8OJtjNWUM) with a hot air gun/reflow station, by mozzwald
* [Video: "The equally stupid way"](https://www.youtube.com/watch?v=ZqOb45N2sMc), workaround video by Dalton, using a soldering iron. Less chances to permanently damage the board than the next if you are handy with a soldering iron, but still high.
* [Video: "The stupid way"](https://www.youtube.com/watch?v=j3jc7Mvn9Eo) workaround video by Lukasz, with pliers. Slightly damages the circuit board, preventing you from soldering the replacement chips at a later point. You might be fine with this.
