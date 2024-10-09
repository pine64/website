---
title: "120W Desktop Power Supply"
draft: false
menu:
  docs:
    title:
    parent: "PinePower/Versions"
    identifier: "PinePower/Versions/120W_Desktop_Power_Supply"
    weight: 2
---

{{< figure src="/documentation/images/PinePower-Desktop-2.jpg" title="PinePower Desktop 120W render" width="400" >}}

A 120W desktop power adapter. It features 1 USB-C port and 4 USB-A port. The 120W output is not per port, but total output power. This is calculated by combining the 65W USB-C, 3x15W USB-A and the 18W USB-A QC, making a total of 128W. The only difference between the US and EU edition is the supplied power cable. Every port, with exception of the wireless Q-charger, has a display, portraying the output voltage and amps. The display back light can be turned on and off by capacitive touch button, located on the top left side of the unit.

## General specifications

Body:

* Dimensions: 123mm x 115mm x 48mm
* Weight: 543 grams
* Build: Plastic
* Color: Black

Display:

* Individual port voltage status display
* Individual port current status display

Controls:

* Mains power toggle switch
* Capacitive power output display switch

Power:

* Input: AC 100-240V 50/60Hz ?A Max
* Output: 120w

Connections:

* 110/240VAC input (either US/EU/UK figure of 8 plug is supplied)
* 4x USB-A
* 1x USB-C

## Power specifications

|     |     |     |     |     |
| --- | --- | --- | --- | --- |
| Output | Protocol | Version | Max output power | Power ranges |
| USB-C | [PD](https://en.wikipedia.org/wiki/USB_hardware#USB_Power_Delivery_(USB_PD)) | ? | 65W | 5V3A, 9V3A, 12V3A, 15V3A, 20V3.25A |
| USB-A | [QC](https://en.wikipedia.org/wiki/Quick_Charge) | 3.1 | 18W | 5V3A, 9V2A, 12V1.5A |
| USB-A | USB | ? | 15W | 5V3A |
| Wireless charger | [Qi](https://en.wikipedia.org/wiki/Qi_(standard)) | 1.2 | 10W | - |

## Internals

The power unit is not made to be disassembled, do so at your own risk. The front plate is secured with 4 tabs, that can be disengaged with a screwdriver. The complete assembly can be slid out, but do mind the same tab in the casing. The power button at the back of the case has a plug that can be disconnected from the main PCB. The wireless charging PCB has to be de-soldered, or forcefully removed from the inner casing, as it is glued to the top of the case.

{{< figure src="/documentation/images/PinPower-Desktop-front-plate-removal.jpg" title="(Removal_of_the_front_plate)" >}}
{{< figure src="/documentation/images/PinPower-Desktop-Display-front.jpg" title="(Front_view_display_PCB)" >}}
{{< figure src="/documentation/images/PinPower-Desktop-Display-back.jpg" title="(Back_side_display_PCB)" >}}
{{< figure src="/documentation/images/PinPower-Desktop-PCB-top.jpg" title="(Top_side_main_PCB)" >}}
{{< figure src="/documentation/images/PinPower-Desktop-PCB-bottom.jpg" title="(Bottom_view_main_PCB)" >}}
{{< figure src="/documentation/images/PinPower-Desktop-wireless-charger.jpg" title="(Wireless charger)" >}}

Some remarks:

* This main PCB is marked as XR SEMI v1.1
* Two unmarked packages, control the display.
* An antenna is connected on the display PCB, lining up with the 'lamp' symbol. This is the capacitive touch button to control the display back light.
* The 65W PD USB-C port is controlled by a [HUSB339](http://www.hynetek.com/product/pdController/HUSB339/document/HUSB339_DS_EN_V1.2.pdf) controller, paired with a GOFORD G16 MOSFET.
* The other ports have a [NDP1360KC](http://www.lshchip.com/pdf/Deep-pool/NDP1360KC_EN_Rev1.1.pdf) as final power converter.

## Certifications

* [120W PinePower Desktop Power Supply FCC Certificate](https://files.pine64.org/doc/cert/120W%20Desktop%20PinePower%20FCC%20Certificate-DL-20221129012C.pdf)
* [120W PinePower Desktop Power Supply CE EMC Certificate](https://files.pine64.org/doc/cert/120W%20Desktop%20PinePower%20CE%20EMC%20Certificate-DL-20221129011C.pdf)
