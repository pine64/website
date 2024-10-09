---
title: "PinePhone v1.2b"
draft: false
hidden: true
menu:
  docs:
    title:
    parent: "PinePhone/Revisions"
    identifier: "PinePhone/Revisions/PinePhone_v1.2b"
    weight: 
---

The PinePhone v1.2b is a hardware revision of the [PinePhone](/documentation/PinePhone) that started shipping in Q4 2020.

This page contains information and resources which are specific to the v1.2b revision of the PinePhone. For other revisions or for resources related to all PinePhone revisions, see [PinePhone](/documentation/PinePhone/Revisions/).

## Schematics

* [Hardware schematic v1.2b](https://files.pine64.org/doc/PinePhone/PinePhone%20v1.2b%20Released%20Schematic.pdf) (for the Manjaro Community Edition)

## Changes from v1.2a

* A bug was fixed, where connecting a VBUS powered device lowered the screen brightness (resistor R1318 changed to NC).

## Changes with the Beta Edition

* Due to the global pandemic early 2021 and the component shortage as a result, the magnetometer in the Beta Edition had to be replaced from an LIS3MDL to an AF8133J.

## Known issues

* HDMI hotplug detection is not reliable due to a HW bug in level shifting circuitry for the hot plug detect (HPD) signal between HDMI bridge and A64 SoC, see [megi’s blog post](https://xnux.eu/log/#045).
* It is not known if three issues of previous revisions are still present and if yes to which degree, or if they have been fixed by removing resistor R1318, see [PinePhone v1.2](/documentation/PinePhone/Revisions/PinePhone_v1.2#backlight) for some details. Please edit this page once this has been confirmed. Mind that there is currently a likely software-related bug present, which also causes the screen to flicker. The bug usually happens after abruptly shutting down the phone previously (for example by forcing it off), in contrast to powering it off.
