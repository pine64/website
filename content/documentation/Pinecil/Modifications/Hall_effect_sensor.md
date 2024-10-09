---
title: "Hall Effect Sensor"
draft: false
menu:
  docs:
    title:
    parent: "Pinecil/Modifications"
    identifier: "Pinecil/Modifications/Hall_effect_sensor"
    weight: 
---

Instructions to install a hall effect sensor (HES) on the [Pinecil](/documentation/Pinecil) V1 and V2.

The Hall Effect Sensor (HES) is an optional end user installed sensor that activates to put Pinecil to sleep when it enters a holder or stand. This requires a neodymium magnet attached to the stand. The closer the HES in the Pinecil is to the magnet, the more likely the HES will activate to enter sleep mode. This adds a feature to Pinecil that is often seen in high end pro irons.

## Tools and Supplies

1. Order a Hall Effect Sensor [(SI7210-B-00 here)](https://www.lcsc.com/product-detail/Position-Sensor_SILICON-LABS-SI7210-B-00-IVR_C2654956.html), also at Digikey and Mouser.
2. Ordering 2-3 might be a good idea in case the first one is damaged during install (if all goes well, one could mail the extras to a friend or another Pine64 member in the community chat ;).
3. Jeweler’s magnifying glasses or magnifying lamp or a microscope is recommended as the [SOT23](https://madpcb.com/glossary/sot-23/) chip is very small.
4. Borrow a second soldering iron (this is when 2x Pinecils is a good idea).
5. Get some [neodymium magnets](https://a.co/d/0jU8zic), just two 8x2.7mm at 8:00PM and 12:00PM on the stand could be enough. Experimentation is needed. Start with just one small magnet and increase the number placed around the stand until 360° sleep is activated when the Pinecil hits the stand.
6. Reference [[Pinecil:_How_to_Repair#Schematics_and_Board_Data | Schematics are here]] (search for U14).

## Videos

1. Easy trick to [Open Pinecil](https://www.youtube.com/watch?v=aK01V5DrrVk).
2. How to install [Hall Sensor video](https://www.youtube.com/watch?v=vU-fhELpI8Y).

## Installation

1. Updating to the newest firmware before installing is recommended, see the [Firmware article](/documentation/Pinecil#firmware_&_updates). These instructions are for 2.18 or newer firmware.
2. The HES is located at the very front of the Pinecil, tip end, see [PCB images here](#images).
3. Once it is soldered, cleaned, and assembled, check the sleep menu, a new hall sensitivity option appears.
4. See this article on how to set up the [sensitivity settings](https://github.com/Ralim/IronOS/blob/dev/Documentation/HallSensor.md) on the firmware menu (Ralim’s IronOS).
5. Once you change the Sleep menu > Hall sensitivity to what you like, then scroll back to the main screen in order for the setting to be saved and persist on reboot.
6. Note: IronOS firmware does not flash a setting change until one scrolls out of the sub-menu back to the main screen. This is to reduce the total number of flashes done as several settings might be changed in one section (number of flashes is not unlimited; most users will not encounter the maximum allowed flashes on normal use over years).

## Hints

1. Try not to overheat the sensor while soldering as that could damage it and even cause a leg to fall off.
2. This is a small SOT23 chip. Tacking one pin on the 2-pin side helps to hold it in place before soldering the rest of the sensor.
3. It is recommended to solder this with an iron with a small tip instead of using hot air (depends on your experience with hot air). See photos below, use kapton tape to protect nearby components: the 3 via holes above the 3-pin side, and the NTC temperature sensor on the other side. If too much heat is applied, it could damage the pcb, and/or affect the I2C and cause screen corruption.
4. Apply generous flux to the area. If lead solder is being used, it is recommended to remove some of the existing no-lead solder that is already on the U14 pads.
5. After the HES is soldered, clean the area completely with 99% isopropyl alcohol (IPA) and a soft toothbrush or small paint brush and dry before [assembly](/documentation/Pinecil/How_to_repair#assembly_steps). Air/hair dryer could be used to blow out some of the wet IPA. Not cleaning it well enough could cause some I2C noise on the screen. Try to keep IPA/alcohol away from OLED screens.
6. If the stand/holder is not metal, tape magnets near where the Pinecil enters the hole in the holder to test out good locations. Hot glue is another option.
7. When closing the handle, inspect that the the seam line is fully snaped closed; avoid pressing the screen.

## Images

Before installation, location at U14:
{{< figure src="/documentation/Pinecil/images/hall_effect_1.jpg" >}}

After installation:
{{< figure src="/documentation/Pinecil/images/hall_effect_2.jpg" >}}

Only needs small amount of solder:
{{< figure src="/documentation/Pinecil/images/hall_effect_3.jpg" >}}

Kapton tape/protect the 3 Via holes above 3-pin side,title="Kapton tape/protect the 3 Via holes above 3-pin side":
{{< figure src="/documentation/Pinecil/images/hall_effect_4.jpg" >}}

Kapton tape/protect the NTC sensor on opposite side of V2 (V1 does not have this):
{{< figure src="/documentation/Pinecil/images/NTC-temp-Sensor.jpg" >}}
