---
title: "Model B Acrylic Open Enclosure"
draft: false
menu:
  docs:
    title:
    parent: "Accessories/Cases"
    identifier: "Accessories/Cases/Model_B_Acrylic_Open_Enclosure"
    weight:
aliases:
  - /wiki/"Model_B"_Acrylic_Open_Enclosure
  - /wiki/Model_B_Acrylic_Open_Enclosure
---

The **"Model B" Acrylic Open Enclosure** is a case for "Model B" sized single-board computers sold by PINE64, available from [the official store](https://pine64.com/product/model-b-acrylic-open-enclosure/).

{{< figure src="/documentation/ROCK64/images/ROCK64_acrylic_open_enclosure.jpg" title="A_ROCK64_mounted_in_the_case,_the_correct_way." >}}

## Installation

To install the SBC inside the case, stick the long screws into the SBC mounting holes from below, place the board such that the screws sit in its mounting holes, and screw on the brass fasteners on top of the SBC.

## Mods

### 3D-Printable Top With Fan Cutout

{{< figure src="/documentation/images/Model_b_open_enclosure_top_cad.png" title="Top_view_of_the_plate" >}}
{{< figure src="/documentation/images/Model_B_Open_Enclosure_Top_Fan_Mount.jpeg" title="The assembled modified case with a Noctua NF-A4x10 5V PWM mounted to it. The SBC is mounted in the enclosure upside-down." >}}

User:CounterPillow has created an alternate 3D-printable top plate which allows for the mounting of a 40mmx40mmx10mm fan. The STL and STEP files are available free of charge under [https://wiki.pine64.org/wiki/File:Model_B_acrylic_case_top_plate_with_fan_cutout.zip](https://wiki.pine64.org/wiki/File:Model_B_acrylic_case_top_plate_with_fan_cutout.zip), licensed as CC-BY 4.0.

A fan is mounted to it using self-tapping fan screws usually shipped with computer fans; put the fan on the underside of the plate, and screw in the self-tapping screws from the top side. You can either have the fan exhaust air through the top, or blow it onto the SoC’s heatsink. The latter configuration appears to work better, but precise measurements haven’t been made yet.

Recommended printing material is PETG for its structural rigidity. However, PLA will likely work fine as well, and is easier to print. A 0.6mm nozzle was used for test prints, but any nozzle should work. Depending on the layer height you choose, your print may come out slightly thicker or thinner; this is no problem though. It’s recommended to enable the advanced "Detect Thin Walls" option in slic3r to get a cleaner g-code result around the fan holes.

The print will take approximately 7.8 metres of filament, and take in the order of one hour, though this depends on slicer settings and printer model.

The cooling performance with a Noctua NF-A4x10 5V PWM is enough to no longer throttle after a few minutes of cpuburn, but comfortably sitting at below 75°C instead. The memory has no temperature sensor, but will likely be cooled quite a bit as well.

{{< figure src="/documentation/images/Arduino_pwm_thing.png" title="Rough wiring diagram of how to PWM control the fan from a ROCK64 with a helper Arduino" >}}

Since the [ROCK64](/documentation/ROCK64) has no PWM pins available to control the fan, a slight workaround can be done; with the `gpio-fan` device tree binding, an Arduino can be controlled to soft-PWM a suitable 25 kHz signal for the fan. The ROCK64 uses 3.3V on the GPIO pins, so you’ll need to logic level convert it to 5V if you’re using a 5V Arduino, and if you’re using a 3.3V microcontroller, you’ll need to logic level shift the output PWM signal as the 5V fan will be expecting 5V PWM on the PWM pin.

The [device tree changes and the Arduino sketch](https://gist.github.com/CounterPillow/34cd7355eb625093e4350c349d2618ea) which User:CounterPillow created for this can be used for any purpose by anyone. It is recommended to play around with the device tree though, to add more trip points for better control over when the fan actually ramps up, and adding more hysteresis as the temperature reading from the ROCK64 is quite jumpy.
