---
title: "Powering From An ATX Supply"
draft: false
menu:
  docs:
    title:
    parent: "ROCKPro64/Hardware"
    identifier: "ROCKPro64/Hardware/Powering_from_an_ATX_supply"
    weight:
aliases:
  - /wiki/ROCKPro64_Powering_From_An_ATX_Supply
---

Powering the [ROCKPro64](/documentation/ROCKPro64) single-board computer from an ATX power supply allows the board to be powered with more than just two disks, and is a reliable and safe way to power it from your household mains.

{{< admonition type="warning" >}}
 Please note that following these instructions comes at your own risk. While best efforts have been made to write reliable, safe instructions, the authors cannot be held liable for the quality of procured components or the assembly job of the person following the instructions, and the damages caused by either of these not being up to par.
{{</ admonition >}}

## Shopping List

### Components

* **An ATX breakout board**. Get one with fuses. For extra safety, replace the fuses with your own trusted ones once you get it.
* **Some 24 AWG or thicker copper wire**, 0.5m of length at most, go thicker if you want to use longer wire. Also go thicker if you’re using copper-coated aluminium.
* **A 2.1mm ID/5.5mm OD barrel jack connector**

### Tools

* **A soldering iron**, e.g. the [Pinecil](/documentation/Pinecil), with some solder
* **Some wirestrippers** suitable for the thickness of wire you chose

## Assembly

* Slide the stress relief over both the wires you will use
* Solder the positive side of the wire to the centre contact of the barrel connector
* Solder the negative side of the wire to the outside contact of the barrel connector
* Fasten the stress relief/barrel connector housing
* Connect the positive side to your ATX breakout board’s 12V terminal
* Connect the negative side to your ATX breakout board’s GND terminal
* Plug in the ATX power supply into the ATX breakout board, with the PSU turned **'off**' at the flip switch in the back
* Set the power switch on the ATX breakout board to the on position
* Stand out of reach of any glass fuse shrapnel (e.g. put the breakout board in a housing), plug in the ATX power supply and flip its switch on
* If it didn’t blow up, you did it right, and can now hopefully plug the ROCKPro64 into the ATX breakout board using the cable you’ve made

## Further Steps

If you got one of the green breakout boards with the glass fuses and the red LED, then User:CounterPillow made a 3d printable housing for it. It screws together with heat-set brass inserts. [Download .zip containing STEPs and STLs as well as the FreeCAD project file](https://overviewer.org/~pillow/up/b97c120da9/atxthing.zip)
