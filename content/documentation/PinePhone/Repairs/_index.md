---
title: "Repairs"
draft: false
toc: true
menu:
  docs:
    title:
    parent: "PinePhone"
    identifier: "PinePhone/Repairs"
    weight: 96
aliases:
  - /documentation/PinePhone/Hardware_fixes_and_mods/
  - /documentation/PinePhone/Hardware_fixes_and_mods/Hardware_issues/
  - /documentation/PinePhone/Hardware_fixes_and_mods/Modifications_and_repairs/
  - /documentation/PinePhone/Hardware_fixes_and_mods/Mods/
  - /documentation/PinePhone/Hardware_fixes_and_mods/Replacement_earpieces/
---

## Spare parts not available in the Pine Store

The following parts are not available for purchase in the Pine Store, however compatible parts can be sourced from other shops:

* Earpiece speaker dimensions: 12x6x2 mm. Compatible with Xiaomi Mi2 / Mi3 (but not Mi4!) and others, see [here](https://forum.pine64.org/showthread.php?tid=12046&pid=85698#pid85698)
* Loudspeaker dimensions: 15x11x3 mm. Compatible with Nokia N91, Lenovo A536 (requires soldering) and others, see [here](https://forum.pine64.org/showthread.php?tid=12046&pid=85698#pid85698)
* Proximity sensor rubber isolator

### Earpiece speaker

The earpiece speaker refers to the small speaker at the top of the ***PinePhone*** and ***PinePhone Pro***.

This part is not available to purchase from the PINE64 Store. However, it is possible to buy a replacement earpiece for another device, and install it in a PinePhone or PinePhone Pro. This documents earpieces that have been tested by the community, and verified to work.

Note that the earpiece dimensions for both the PinePhone and PinePhone Pro are 12x6x2 mm. When looking into earpieces not found in this list, aim for these dimensions.

#### Compatible earpiece speaker

| Model | PinePhone | PinePhone Pro | Example shop |
| --- | --- | --- | --- |
| LG K8 2017 M200N | Kind of ¹ | Broken | [Replace Base](https://www.replacebase.co.uk/for-lg-k8-2017-m200n-replacement-ear-piece-speaker-oem) |
| Nokia 5 | Works | Works | [Replace Base](https://www.replacebase.co.uk/for-nokia-5-replacement-ear-piece-speaker-with-adhesive-oem) |
| Nokia 7 | Works ² | Works ² | [Replace Base](https://www.replacebase.co.uk/for-nokia-7-replacement-ear-piece-speaker-unit-module-oem) |
| Nokia X5 | Works | Works | [Replace Base](https://www.replacebase.co.uk/for-nokia-x5-replacement-earpiece-speaker-unit-oem) |
| OnePlus One | Works | Works | [iFixit](https://www.ifixit.com/products/oneplus-one-earpiece-speaker), [Replace Base](https://www.replacebase.co.uk/oneplus-one-replacement-earpiece-speaker-original) |
| OnePlus X | Works | Works | [Replace Base](https://www.replacebase.co.uk/oneplus-x-replacement-earpiece-speaker-original) |
| PinePhone | Works | Works |  |
| Xiaomi Mi A1 | Works | Works | [Replace Base](https://www.replacebase.co.uk/for-xiaomi-mi-a1-replacement-ear-piece-speaker-oem) |
| Xiaomi Redmi Note 4 | Works | Works | [Replace Base](https://www.replacebase.co.uk/for-xiaomi-redmi-note-4-replacement-ear-piece-speaker-oem) |

Notes:

¹ The earpiece is too thin, it can work with padding to keep the contacts together.

² Audio playback is very low quality.

#### Incompatible earpiece speakers

The following devices are known to have replacement earpiece speakers with dimensions too large to fit inside the PinePhone or PinePhone Pro.

* Blackberry Classic Q20
* HTC Desire 500
* HTC M10
* Huawei Honor 7A
* Huawei Mate 10 Pro
* Huawei Y7 Prime 2018
* OnePlus 2
* Oppo Reno 5 4G
* Sony Xperia X Compact
* Sony Xperia XA1 Ultra
* Sony Xperia XP X Performance
* Sony Xperia XZ

## Replacing the mainboard

The mainboard can be replaced if it is faulty. The replacement board does not have an operating system pre-installed, to test if everything is working after swapping the mainboard a flashed microSD card is required.

{{< admonition type="tip" >}}
Replacement boards come with an empty eMMC, which means that trying to boot from them looks like the board is faulty (no LEDs, no screen, no reaction of the phone). Please boot an operating System from a microSD card.
{{< /admonition >}}

Prior to replacing your PinePhone’s mainboard please read the steps outlined in bullet points below and watch the attached video.

1. You’ll need a small Phillips screwdriver and a prying tool to swap out the mainboard.
2. Remove the PinePhone’s back cover. See your quick start guide for details.
3. Remove the battery as well as any inserted SD and SIM cards.
4. Unscrew all 15 Phillips head screws around the midframe of the phone.
5. Gently pry up the midframe using a guitar pick or credit card corner. It is easiest to separate the midframe at one of the bottom edges. Work your way around all the sides of the phone until the midframe separates from the phone’s body.
6. Detach all ribbon cables and "Lego" connectors. List of things to detach: 1) two "Lego" connects at the bottom of the mainboard. 2) u.FL antenna connect and touchscreen digitizer on PCD left side. 3) LCD ribbon cable top of mainboard, next to audio and UART jack.
7. Pry the mainboard up gently from the left-hand side.
8. Remove front and main cameras and reset them into the new mainboard.
9. Check that the rubber proximity sensor housing is in the chassis, not stuck to the removed mainboard.
10. Place the new mainboard in the chassis, hooking in on the plastic tabs on left side and pressing down firmly on opposite side, and follow the steps (7-2) in reverse. When reattaching the midframe take care that no cables are out of place or trapped, as they may be damaged when tightening screws.

After swapping the mainboard the phone won’t boot as there is no OS on the replacement board’s eMMC preinstalled. To boot an OS insert a flashed SD card.

A video tutorial by _Martijn Braam_ can be found here (or alternatively a video tutorial by user _brigadan_ with additional notes about the camera swap and proximity sensor isolator [here](https://www.youtube.com/watch?v=J3AJEF7akkw)):

{{< figure src="/documentation/images/Pinephone_martijn_pcb_replacement.png" width="600" >}}

### Flashing the ANX firmware

#### Method 1

After swapping the mainboard the ANX7688 chip has to be flashed for full USB functionality.

Under GNU/Linux this can be done by downloading the latest ANX7688 firmware image on the phone:

    wget https://xff.cz/git/linux-firmware/plain/anx7688-fw.bin

and executing as root ("sudo su") on the phone:

    cp anx7688-fw.bin /lib/firmware/
    echo 1 > /sys/class/typec/port0/device/flash_eeprom

#### Method 2

Booting a factory test image will automatically flash the ANX7688 chip. See [Factory Test OS](/documentation/PinePhone/Software/Releases/#hardware_test_build) for such an image.

## Replacing the screen

Before attempting to replace the screen be sure to review the section on [replacing the mainboard](#replacing_the_mainboard) since that will get you most of the way there. Be aware that the replacement screen is actually the entire front frame of the phone and there are components that will need to be swapped from your old screen.

* Make sure you have a precision screwdriver set that has the correct size Philips tip. The screws are very small and the heads can easily be stripped if the screwdriver is not correct - if you feel your screwdriver slipping, stop what you are doing and try one that is a better fit. A magnetized screwdriver will help in not losing screws, as will a magnetic parts holder to keep them in while working.
* There are a number of components and cables as well as the insulator sheet under the battery that are glued in place. A hair dryer will loosen the glue and make them much easier to remove. You may want to order extra cables along with the screen just in case.
* The vibration motor, which is part of the USB-C board assembly and glued into place, will come apart easily and be damaged if you pry it up in the wrong place. Make sure you pry from underneath the complete part, not midway on its housing. The ribbon cable attaching this to the USB-C board is small, thin, and fragile so be careful with that as well.
* The new screen comes with new side switches and insulator sheet but there are a number of parts that need to be transferred from the old screen, like the thin coax cable running up the side, the phone ear speaker, proximity sensor gasket, and a gold-colored mesh glued in place that needs to be transferred to a flexible circuit included on the new screen. If you don’t swap over the proximity sensor rubber gasket the screen will immediately turn off after logging in. Be careful when routing the coax cable that it goes around the screw holes or you may drive a screw right through the cable.

Take your time, use the right tools, be careful and you should be rewarded with success.

## Hardware issues

### SIM reader

The SIM reader may fail to read a SIM card (reporting 'sim-missing' in mmcli), possibly due to deformed pins (if you put your SIM adapter in without a SIM), or due to a warped SIM card adapter.

A possible solution is to bend the pins back (using a plastic spudger), and/or use a different SIM card adapter (which your carrier may provide to you).

### USB-C side board

Many issues with the USB-C side board can be fixed by replacing the [USB-C side noard](https://pine64.com/product/pinephone-usb-c-side-board/)

#### Internal microphone

The microphone may stop working or occasionally stop working or give off static when power is plugged in.

One possible fix is to User:Earboxer/Shim_U101|shim U101 (as seen on the [back side of the USB-C side board](https://files.pine64.org/doc/PinePhone/PinePhone%20USB-C%20small%20board%20bottom%20placement%20v1.0%2020190730.pdf)) with a piece of paper or cardboard.

#### Bottom speaker

The bottom speaker may stop working, especially if you have recently mishandled the USB-C side board, stressing the point of connection between the circuit board and the circuit flex. This can be fixed by touching up the solder between the two.


## Mods

There are a number of options to hardware mod the PinePhone.

Some are upgrades to fix issues that were not done optimally in the production of that version of the electronics, and some are to add options that were not part of the phone spec.

### General

Make pictures of the situation before and after your mods, so you can compare the change, and don’t need to disassemble the device to get the right pics later.

### Laser-cut parts

User _Mcyam2_ has created some laser-cut templates for the rear facing components here:

https://imgur.com/a/LAUatOa

https://anonfiles.com/L0BeK5L5oe/ppsvg-backplate-CUTOUT_svg

Originally based on silver’s work on a 3d printed rear frame

### 3D-printed parts

Silver has created a 3D-printable rear frame for the PinePhone and used it to create a folding keyboard design (work in progress), User:Silver/3d printed a folding keyboard mostly.

https://ibb.co/album/ScDttH

https://www.youmagine.com/designs/pinephone-folding-keyboard-mockup

### PCBs

https://github.com/SMR404/PinephonePogoBreakout

https://github.com/jnavarro7/pinephone_flex_breakout_board_grove

### Braveheart Edition

{{< admonition type="warning" >}}
 These are fixes for hardware bugs for old revisions of the PinePhone (from 2019 and early 2020). They do not apply to current revisions.
{{< /admonition >}}

* PMIC mod - Stops the battery drain from a shutdown phone, draining the battery to 0V.
* VCONN mod - Unblocks the USB-C power negotiation rail, so convergence functions are unlocked.

#### PMIC mod

[PinePhone 1.1 VBUS power usage hardware fix](/documentation/PinePhone/Repairs/PinePhone_1.1_VBUS_power_usage_Hardware_Fix)

The original description of this fix is given on megi’s pager here https://xnux.eu/devices/pp-pmic-fix.jpg

#### VCONN mod

See below.

### Braveheart Edition and UBPorts Community Edition

{{< admonition type="warning" >}}
 These are fixes for hardware bugs for old revisions of the PinePhone (from 2019 and early 2020). They do not apply to current revisions.
{{< /admonition >}}

* VCONN mod - Unblocks the USB-C power negotiation rail, so convergence functions are unlocked.

There are also a number of mods that can be done adding more functions by adding extra hardware to the pogo pins, and a number of options to change the screen protector.

At this moment there are not many pogo addons, and most are just connector boards. Likely the makers will add links to these projects to this page. Pine is looking into adding a N900 style keyboard attached to these pins.

#### VCONN mod

The original description of this fix is given on megi’s pager here https://xnux.eu/devices/pp-usbc-fix.jpg
There is a discussion on the merits of the different ways to do the fix.

##### VCONN mod, Removal only

[PinePhone 1.2 VCONN hardware fix](/documentation/PinePhone/Repairs/PinePhone_1.2_VCONN_Hardware_Fix)

There are now a few documented ways,

* Removal only, the tweezer "stupid" way: https://www.youtube.com/watch?v=j3jc7Mvn9Eo
* Removal only, the soldering iron "less stupid" way: https://www.youtube.com/watch?v=ZqOb45N2sMc

There are hopefully videos coming doing it the proper way, and so they can be linked here.

After this the firmware for the power negotiation chip needs to be upgraded, this can be done by running the factory test image, version http://images.postmarketos.org/pinephone/pine64-pinephone-20200724-factorytest55.img.xz or higher. This will do the firmware flashing and respond with a message indicating the state. After this the phone is ready for its added functions.
ANX states:

* No CC Fix - Fix not applied
* No USB Cable - No USB-C connection, cannot upgrade firmware
* OK - Firmware Applied, you are all set

##### VCONN mod, Replacement

Using 2x NCP334FCT2G you could do the full fix, making VCONN powered devices able to negotiate power. IT needs the parts to be removed first without damaging the pads, and then replacing the parts.


## Further mods

{{< children >}}