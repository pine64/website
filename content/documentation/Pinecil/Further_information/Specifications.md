---
title: "Specifications"
draft: false
menu:
  docs:
    title:
    parent: "Pinecil/Further_information"
    identifier: "Pinecil/Further_information/Specifications"
    weight: 
---

## Pinecil V2

* **Package:** 15cm x 9cm x 2.2cm, white box (released Aug 2, 2022)
* **Dimensions:** 155mm with solder tip or 103mm without solder tip x 12.8mm x 16.2mm
* **Weight:** 28g with solder tip, 18g without solder tip
* **Soldering Tip:** includes type ST-B2 (short tip), Length 86mm, weight 8.2g
* **Platform:** Ralim’s IronOS build
* **Display:** OLED White Color Monochrome Display 0.69" 96x16 pixels
* **Chipset:** Bouffalo BL-706
* **CPU:** 32-bit RV32IMAFC RISC-V "SiFive E24 Core" @ 144 MHz
* **Memory:**
  * 192KB Internal ROM
  * 132KB SRAM System
* **Power Ports (12V-24V, 88 Watts):**
  * Only use one power port at a time (USB or DC barrel)
  * USB type C: PD 12V-20V 3A and QC 3.0 12V-20V 3A (magnetic tip USB-C cables are not recommended, and not USB compliant)
  * Barrel Jack: DC5525, 12V-24V, minimum 3amps.
  * Trying to use an incorrect barrel jack, i.e., DC5521 will [BREAK the connector](https://forum.pine64.org/showthread.php?tid=13237) (if it doesn’t go in easy, it doesn’t fit).
  * Recommend operating voltage 12-24V, but a 12V USB-C charger will not perform as well or heat as fast as a USB-C PD65W/20V/3amp charger.
  * Tentative support: EPR 140W/28V PD3.1 chargers + EPR cables are theoretically supported in hardware and [IronOS firmware](https://ralim.github.io/IronOS/).
    * EPR is new technology in 2022. Theoretically Pinecil could get a max of 28V and 126W using EPR chargers & EPR cables (natural loss of 140W to 126W due to Tip ohms).
    * Bleeding edge users are using/testing this.
    * EPR is potentially the fastest/highest performance possible for V2; officially Pine Store states 12V-24V, 88W.

## Pinecil V1

* **Package:** 16.8cm x 11.8cm x 2.3cm, black box with clear plastic front (sold before Aug 2, 2022)
* **Dimensions:** 170mm with solder tip or 98mm without solder tip x 12.8mm x 16.2mm
* **Weight:** 30g with solder tip, 20g without solder tip
* **Display:** 0.67" QUG 9616TSWCG02 96x16 Monochrome Matrix display
* **CPU:** GD32VF103TB 32-bit RV32IMAC RISC-V "Bumblebee Core" @ 108 MHz
* **Memory:**
  * 128KB Flash
  * 32KB SRAM
* **Power supply (12V -21V, 65W):**
  * Only use one power port at a time (USB or DC barrel)
  * DC 12V-21V 5525 Barrel Jack. Do not try to use a larger 5521 (which requires excessive force). It will [BREAK the connector](https://forum.pine64.org/showthread.php?tid=13237).
  * USB-C 12-20V PD or QC3.0 (magnetic tip USB-C cables are not recommended, and not USB compliant)
  * Recommend operating voltage 12-21V, some components can tolerate higher voltages at "absolute maximum" but it’s very ill-advised

## Fasteners/Screws

![Thumb Screws](/documentation/images/Pinecil-Thumb-Screws-02.png)

* Originals screws are Phillips ([source](https://www.reddit.com/r/PINE64official/comments/tatf5l/comment/ig4r92v/?context=3)): two M2x3mm at the front, and one M2x4mm is the ground screw near the `**[-]**` minus button.
* The bottom-front screw only holds the handle together and does not touch the tip, hence is a shorter m2x 3mm.
* _Thumb screws_ are popular upgrades: an _M2 x 4mm_ thumb screw could replace both the front screen-side Tip holder screw and the ground screw in the rear of the handle.
* It was found that an M2x3mm thumb screw for the tip is a hair _too short_, and just grazes the Tip and the longer _m2 x 4mm is better on top_.

**📌 NOTE**\
If the screw is too long (for example with a length of 5mm) a metal file can be used lightly to shorten it a small amount. Stainless steel is recommended as the softer aluminum screws could mushroom as you tighten down the tip screw too much or over time.
