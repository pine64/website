---
title: "Usage"
draft: false
menu:
  docs:
    title:
    parent: "Pinecil"
    identifier: "Pinecil/Usage"
    weight: 3
---

## Overview

**Prep Tasks**

**💡 TIP**\
Clean new cartridges/tips with isopropyl alcohol (IPA) to remove factory residue before installing (even if it looks clean). If you have no IPA, at least try a paper towel, especially clean the white end with the two silver electric contacts (do not use water; it could get into the seam line on the white end). This resolves issues with jumping temperatures or random no-tip symbol from poor electric contact.

Do not try to bend the two [internal contacts](https://pine64.com/product/pinecil-copper-clips/), they are made of a thin stiff spring metal and could break (not soft copper), but you could wipe them with IPA (including the small PCB pad below the contacts).

**1. Install the tip**: The Pinecil comes with a separate heating element, the tip.

1. Remove the screw from the front top-side of handle. Then, gently push the tip all the way back until the wide collar/guard is touching the front of the plastic (see link::File:Pinecilv2-1.jpg[photo]).
2. Gently tighten or loosen this screw to install or swap the tip. (careful, tiny screws break easy, if tip does not fall out, it’s tight enough)
3. The bottom front screw should not touch the tip, it only holds the handle together (see [Fasteners](#fasteners/screws)).
4. Always unplug before swapping tips if you have multiple tips.

**2. Supply power**: the USB-C port, connected to any supply, is enough power to show the display screen, but not necessarily enough to heat the tip.

1. USB port at 5 volts (i.e., laptop) shows _DC Low_, this is enough for [firmware updates](https://ralim.github.io/IronOS/#getting-started) and to view the menu, but not to run the soldering iron.
2. See [Power section](/documentation/Pinecil/Power_supplies/) for details on power options. QC 12V phone chargers will not work, as they are too weak.

**3. Heat the tip**: plug Pinecil into an appropriate [power supply](/documentation/Pinecil/Power_supplies/Power_supplies).

1. Clicking `**[+]**` starts the tip heating.
2. The detailed display option shows power draw, current temperature, supply voltage, and time until sleep mode starts.
3. Adjust the target temperature with further clicks of `**[+]**` and `**[-]**` buttons.
4. Wait a few seconds for the regular display to return, then hold down `**[-]**` for a moment to turn the heat off.
5. You can observe the temperature measurement go up and down. Certain settings involve holding down both buttons (see [GitHub IronOS for details on firmware](https://ralim.github.io/IronOS/) settings).

**4. Using the Settings Menu**:

1. To check the firmware version, hold down the `**[-]**` button. It will display something like "v2.19.A3BBABC 13-07-22". This is the firmware number and release date, the date is July 13, 2022 in the example.
2. Clicking `**[-]**` when heat is off steps through main categories menus to control a variety of settings, see [Getting started with menus section](/documentation/Pinecil/Usage/#getting_started_with_the_menu).
3. Clicking `**[-]**` also returns to the regular display of temperature and supply voltage (this view varies if you activate detailed idle). At other times it may show power draw.
4. Click `**[-]**` to scroll to the the main menu section desired (i.e., User Interface). Then click `**[+]**` button to change various internal settings. Then click `**[-]**` again to go to the next item in the sub-menu.

**5. Important notes**:

1. The iron will "sleep", switching to a lower temperature, after it has been put down for a short time, and heat up again when it is picked up.
2. Calibration of the Tip temperature is usually not necessary and should only be done if the tip is off by +/- 5 °C or temperature is behaving oddly. See instructions to [calibrate the tip in the firmware on GitHub IronOS.](https://ralim.github.io/IronOS/Menu/#calibrate-tip-cjc)
3. **For Safety**, unplug the soldering Iron when not in use or left unattended.
4. To heat up the tip, we need a [power supply](/documentation/Pinecil/Power_supplies/Power_supplies) that can provide at least 12V 3A to run. This is the bare minimum. Pinecil will heat slowly at only 12V/3A. To maximize performance, higher Volts/Amps/Watts is recommended (see [Power supplies](/documentation/Pinecil/Power_supplies/Power_supplies)).
   1. Option 1: a USB-C supply that can negotiate up to such a voltage. For good performance and soldering experience, a USB-C **PD65W, 20V, 3+ A** charger is recommended (suitable for most users).
   2. Option 2: a supply with a DC 5525 barrel connector [(+ pos center, - neg outside)](https://www.youtube.com/watch?v=5DBTNplNTfA) that supplies anywhere from 12V-21V, 3+ amps (V1 Pinecil) or 12V-24V, 3+ amps (V2 Pinecil).
   3. Option 3: use a battery, i.e., an 18V-21V tool Battery with a Power Wheels adapter, and a cable to plug into the Pinecil DC5525 barrel jack.
   4. You may have a suitable supply already that could be used, (see [Power supplies](/documentation/Pinecil/Power_supplies/Power_supplies)).
   5. While 12V-3A will work, it will not heat the tip as quickly and efficiently as a PD65W-20V USB-C charger or a higher rated DC barrel charger.
   6. See warnings about using random DC barrel chargers, not all of them have the correct polarity or DC 5525 style plug and some may be too high of voltage which could damage the Pinecil.

## Getting Started with the Menu

1. **Getting Started** Guide in [GitHub/IronOS](https://ralim.github.io/IronOS/GettingStarted/)
2. **Main Settings Menu**: updated list is found in the firmware repository [Settings Menu](https://ralim.github.io/IronOS/Settings/)
   * **Power settings**: settings related to power, battery cells, input voltage.
   * **Soldering settings**: settings for soldering such as, boost temps, increments for temperature change
   * **Sleep mode**: power & tip saving, such as sleep mode, sleep temperature, and shutdown modes, motion sensitivity
   * **User interface**: settings such as, units C/F, display orientation, button reversal, animation speed, brightness, boot logo duration
   * **Advanced settings**: assorted catchall for settings that don’t fit elsewhere or settings that require some thought before use. Restore default/factory settings is here. It will not change the firmware version, but rather resets the menu back to IronOS defaults. This is good to do after a major [firmware update](https://ralim.github.io/IronOS/GettingStarted/) as settings may have been altered and need to be re-selected/customized again to work as expected.
3. **Hidden Debug Menus**: also available, see [GitHub/IronOS](https://ralim.github.io/IronOS/DebugMenu/)
