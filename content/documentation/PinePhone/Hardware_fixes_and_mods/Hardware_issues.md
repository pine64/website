---
title: "Hardware issues"
draft: false
hidden: true
menu:
  docs:
    title:
    parent: "PinePhone/Hardware_fixes_and_mods"
    identifier: "PinePhone/Hardware_fixes_and_mods/Hardware_issues"
    weight: 
---

{{% docs/construction %}}

## Main Board

### Sim Reader

The sim reader may fail to read a sim card (reporting 'sim-missing' in mmcli), possibly due to deformed pins (if you put your sim adapter in without a sim), or due to a warped sim card adapter.

A possible solution is to bend the pins back (using a plastic spudger), and/or use a different sim card adapter (which your carrier may provide to you).

## USB-C Side Board

All USB-C Side Board issues can be fixed by replacing the [USB-C Side Board](https://pine64.com/product/pinephone-usb-c-side-board/)

### Internal Microphone

The microphone may stop working or occasionally stop working or give off static when power is plugged in.

One possible fix is to User:Earboxer/Shim_U101|shim U101 (as seen on the [back side of the USB-C Side Board](https://files.pine64.org/doc/PinePhone/PinePhone%20USB-C%20small%20board%20bottom%20placement%20v1.0%2020190730.pdf)) with a piece of paper or cardboard.

### Bottom Speaker

The bottom speaker may stop working, especially if you have recently mishandled the USB-C Side Board, stressing the point of connection between the circuit board and the circuit flex. This can be fixed by touching up the solder between the two.

## Uncategorized Issues

Place new issues here.

## See Also

* [PinePhone](/documentation/PinePhone/Hardware_fixes_and_mods)
* [PinePhone v1.2](/documentation/PinePhone/Revisions/PinePhone_v1.2)
* [PinePhone v1.2a](/documentation/PinePhone/Revisions/PinePhone_v1.2a/#known_issues)
* [PinePhone v1.2b](/documentation/PinePhone/Revisions/PinePhone_v1.2b/#known_issues)
