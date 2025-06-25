---
title: "PinePower"
draft: false
menu:
  docs:
    title:
    parent: "PinePower/Versions"
    identifier: "PinePower/Versions/PinePower"
    weight: 1
---

The PinePower is a small and compact palm size 65W wall socket power adapter. It features 2 USB-C ports and 1 USB-A port charger. [Gallium Nitride](https://en.wikipedia.org/wiki/Gallium_nitride) technology ensures a small and light charger with high charging efficiency. It has a retractable US plug.

{{< figure src="/documentation/PinePower/images/PinePower_Charger_65W.jpeg" caption="" width="400" >}}

## General specifications

Body:

* Dimensions: 74.8mm x 36.6mm x 32mm
* Weight: 130 grams
* Build: Plastic
* Color: Black

Power:

* Input: AC 100-240V 50/60Hz 1.5A Max
* Output: 65W
* Power switch

Connections:

* 240Vac input US plug, adapters for AU, EU, and UK,
* 1x USB-A
* 2x USB-C

## Power specifications

| Output | Max output power | Power ranges PD | Power ranges QC | Power ranges PPS |
| --- | --- | --- | --- | --- |
| Single USB-C1 or C2 | 65W | 5V3A, 9V3A, 12V3A, 15V3A, 20V3.5A | - | 3.3-11V5A |
| Single USB-A | 65W | - | QC3.0 4.5V5A, 5V4.5A, 9V3A, 12V3A, 20V3A | - |
| <ul><li>USB-C1 &</li><li>USB-C2 combined</li></ul> | <ul><li>45W</li><li>18W</li></ul> | <ul><li>5V3A, 9V3A, 12V3A, 15V3A</li><li>5V3A, 9V2A, 12V1.5A</li></ul> | - | - |
| <ul><li>USB-C1 &</li><li>USB-A combined</li></ul> | <ul><li>45W</li><li>18W</li></ul> | <ul></li>5V3A, 9V3A, 12V3A, 15V3A</li><li>-</li></ul> | <ul><li>-</li><li>5V3A, 9V2A, 12V1.5A</li></ul> | - |
| <ul><li>USB-C1 &</li><li>USB-C2 + USB-A combined</li></ul> | <ul><li>45W</li><li>15W</li></ul> | <ul><li>5V3A, 9V3A, 12V3A, 15V3A</li><li>5V3A</li></ul> | - | - |

## Internals

### Teardown

{{< admonition type="warning" >}}
Opening this device may expose you to high voltage components that can cause serious injury or death. **Do not attempt to open, repair or modify the device.** For safety, always consult a qualified technician for any issues.
{{< /admonition >}}

To open your Charger, you just have to Cut away the backplate with the USB-Ports, then you can pull out the PCB.

### Images

{{< figure src="/documentation/PinePower/images/PinePower_Charger_65W_teardown/PCB-Backside.jpg" caption="PCB Back" width="400" >}}

{{< figure src="/documentation/PinePower/images/PinePower_Charger_65W_teardown/PCB-top.jpg" caption="PCB Top" width="400" >}}

{{< figure src="/documentation/PinePower/images/PinePower_Charger_65W_teardown/Top-view-case.jpg" caption="Top view in case" width="400" >}}

{{< figure src="/documentation/PinePower/images/PinePower_Charger_65W_teardown/PCB-unsoldered.jpg" caption="PCB with unsoldered USB-C ports" width="400" >}}

{{< figure src="/documentation/PinePower/images/PinePower_Charger_65W_teardown/PCB-side.jpg" caption="PCB side view" width="400" >}}

## Certifications

* [65W PinePower GaN Charger FCC Certificate](https://files.pine64.org/doc/cert/65W%20PinePower%20FCC-SDO%20Certificate-LCSA110222005E.pdf)
* [65W PinePower GaN Charger CE EMC Certificate](https://files.pine64.org/doc/cert/65W%20PinePower%20GaN%20Charger%20CE%20EMC%20Certificate-LCSA110222003E.pdf)
* [65W PinePower GaN Charger CE LVD Certificate](https://files.pine64.org/doc/cert/65W%20PinePower%20GaN%20Charger%20CE%20LVD%20Certificate-LCSA110222004S.pdf)
