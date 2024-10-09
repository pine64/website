---
title: "Checklist"
draft: false
menu:
  docs:
    title:
    parent: "Pinecil"
    identifier: "Pinecil/Checklist"
    weight: 
---

Prep tasks:

1. **Clean new cartridges/tips with 99% isopropyl alcohol (IPA)** to remove factory residue before installing (avoid strange behavior from poor electric contact). If you have none, try to at least wipe down the new cartridge with a clean towel especially the 2 contacts at the rear white end (do not use water, as it could get into the small white seam line).
2. Do not bend the two tiny [internal contacts](https://pine64.com/product/pinecil-copper-clips/), they are thin spring metal and may break.
3. Only use one port, USB-C or the DC barrel, but Never both at the same time. Damage will occur to PC/Laptop/Pinecil!
4. If using a DC barrel brick for power, do not use more than 24V for Pinecil V2 and not more than 21V for Pinecil V1 (a [special end-user modification](/documentation/Pinecil/How_to_repair/#pinecil_v1_24v_mod) is possible for V1 which allows it to use up to 24V safely).

Upon receipt, or buying a used Pinecil, one may want to check the following:

1. The display turns on when 5-21V is supplied (V2 models can do 24V).
   * Use a USB type C cable or a DC 5525 _center positive_ barrel [(how to check polarity)](https://www.youtube.com/watch?v=5DBTNplNTfA)
   * Use the video linked to make sure the DC barrel charger is _Center Positive_ before plugging it into Pinecil. Several users have accidentally plugged incorrect center-negative chargers into Pinecil which immediately breaks it because it is the wrong type of charger (this is sometimes repairable, see [live community chat](/documentation/#_community_and_support)).
   * Note that 5v shows _DC low_ and is not high enough to run Pinecil. 5V is only enough for firmware update and to see the menu.
2. It gets full power.
   * 20V from a 20V capable USB-C PD charger or power from DC barrel charger that is the appropriate specifications. The screen displays the voltage from the charger.
   * Check both orientations of the USB-C cable (try to flip it if one way doesn’t work).
3. Check for new firmware updates, see the firmware section.
   * Note: do not connect the DC barrel at the same time as a USB-C cable. Pinecil was designed to only have one cable plugged in at a time. You could damage/break the PC and Pinecil doing this.
   * V1 and V2 used different flasher apps to load firmware onto the Pinecil, see the [Firmware section](/documentation/Pinecil/Firmware/).
   * Updating firmware requires a _data_ capable USB cable connected to a PC/laptop.
4. Check that both buttons work
   * `[-]` to enter menu or decrease temperature, long press `[-]` to get the software version info or to turn off heating
   * `[+]` to turn on heating or select a menu item
5. The displayed text rotates according to gravity when orientation is set to _Automatic_
   * User interface -> Display orientation -> Automatic
   * [More menu options listed on IronOS documents](https://ralim.github.io/IronOS/Settings/)
6. Check that all 3 external screws are present
   1. One near the back of the screen (ground screw for optional ground wire)
   2. One at the front on top (to hold the tip in)
   3. One at the front on the bottom (to hold the case together, does not touch the tip)
7. Check that the tip is clean & wipe it down with a dry towel or IPA (uniformly silver at the front, with no pitting or texture).
   * Some tips come pre-dipped in solder for protection and may look odd. Heat them up then wipe clean on a soldering sponge or brass wool and inspect.
   * Heat up the tips a few times to 350°C for a couple minutes to check that they are working and melting solder.
   * See [Pinecil Tips](/documentation/Pinecil/Tips/) and [Guides to Soldering & Maintenance](/documentation/Pinecil/Guides_to_soldering/) for soldering advice.
   * Re-tin the tip before storing is advised to prevent oxidation.
8. Check that it heats up with an installed tip, and stops increasing when it reaches the set point.
   * This may draw up to ~3A, make sure the [power supply](/documentation/Pinecil/Power_supplies/Power_supplies) can provide a minimum of 3amps or more.
   * Minor overshoot may occur, but, disconnect power if the temperature keeps going up higher without user input and check with the [live volunteer Pinecil channel](/documentation/#_community_and_support).
9. Do a simple test is to see if the iron will melt solder at approximately the expected temperature for the alloy of solder being tested.
   * If no direct measurement is possible, set it to ~230°C and see if it just about melts SAC (lead-free) solder (~190°C for leaded). This may be more if the room is cold.
10. If there are multiple tips, wipe all of them with isopropyl alcohol (IPA) or a dry clean towel and check that they all heat up.
11. If the tip moves a little while using it, try to hold Pinecil with the screen facing the side or screen downwards. Members found that if the screen is up and the screw loosens during use, then the tip wobbles a little. Changing holding angles helps the tip press against the solid barrel instead of wobbling on the stub of the small screw.
