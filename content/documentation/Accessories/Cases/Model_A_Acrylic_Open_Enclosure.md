---
title: "Model A Acrylic Open Enclosure"
draft: false
menu:
  docs:
    title:
    parent: "Accessories/Cases"
    identifier: "Accessories/Cases/Model_A_Acrylic_Open_Enclosure"
    weight:
aliases:
  - /wiki/Model_A_Acrylic_Open_Enclosure
---

The **"Model A" Acrylic Open Enclosure** is a case for "Model A" sized single-board computers (Pine A64, ROCKPro64, Quartz64 Model A) sold by PINE64, available from [the official store](https://pine64.com/product/pine-a64-rockpro64-acrylic-open-enclosure/).

{{< figure src="/documentation/images/Model_a_acrylic_case_with_pine_a64.jpg" title="A Pine A64 mounted in the &quot;Model A&quot; Acrylic Open Enclosure. The text on the top is &quot;PINE64&quot; nowadays." >}}

## Installation

Please refer to [the official instructions](https://files.pine64.org/doc/guide/PINE64_Acrylic_Open_Enclosure_Installation_Guide.pdf) for assembling the case.

For the Quartz64 Model A, you may need to file down the inner corner of one of the mounting posts for the little mic connector on the bottom of the board to clear it.

## Mods

### 3D-Printable Top With Fan and PCIe Cutout

{{< figure src="/documentation/images/Model_a_top_render.png" title="Non-artist’s impression of the replacement top plate" >}}

User:CounterPillow has created an alternate 3D-printable top plate which allows for the mounting of a 40mmx40mmx10mm fan, as well as allowing for PCIe cards to be mounted while the case is assembled. The STL and STEP files are available under [https://wiki.pine64.org/wiki/File:Model_A_acrylic_case_top_plate_with_fan_cutout.zip](https://wiki.pine64.org/wiki/File:Model_A_acrylic_case_top_plate_with_fan_cutout.zip) free of charge, licensed as CC-BY 4.0.

A fan is mounted to it using self-tapping fan screws usually shipped with computer fans; put the fan on the underside of the plate, and screw in the self-tapping screws from the top side. You can either have the fan exhaust air through the top, or blow it onto the SoC’s heatsink. The latter configuration appears to work better, but precise measurements haven’t been made yet.

Recommended printing material is PETG for its structural rigidity. However, PLA will likely work fine as well, and is easier to print. A 0.6mm nozzle was used for test prints, but any nozzle should work. Depending on the layer height you choose, your print may come out slightly thicker or thinner; this is no problem though. It’s recommended to enable the advanced "Detect Thin Walls" option in slic3r to get a cleaner g-code result around the fan holes.
