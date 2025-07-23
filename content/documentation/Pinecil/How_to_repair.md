---
title: "How to Repair"
draft: false
menu:
  docs:
    title:
    parent: "Pinecil"
    identifier: "Pinecil/How_to_repair"
    weight:
#aliases:
#  - '/wiki/Pinecil\:_Test,_Repair,_Issues'
#  - '/wiki/Pinecil\:_How_to_Repair'
---

This article explains how dismantle, test, and repair the [Pinecil](/documentation/Pinecil).

## Cautions

{{< admonition type="warning" >}}
 while opening your Pinecil will not necessarily void your warranty, all self-repairs are **done at your own risk**. Read everything in this section and related or linked articles to get a good idea of the procedure, and go to the Pinecil community chat if you desire advice/support from experienced volunteers. Self-repairs or modifications might void your warranty so proceed if this is not a concern. This information is for educational purposes only.
{{< /admonition >}}

Pinecil V1 and V2 have slightly different schematics and have different MCU chips. Doing repairs often requires referencing the correct schematics or photos. The datasheets are also important to get information about the chips, and to order replacement parts. The schematics and known datasheets are all at the bottom of this article and linked in the contents table at the top. Chatting with other owners of Pinecil is encouraged as they have experience - already broke things so you don’t have to (see Pinecil volunteer [chat link here](/community/#chat-platforms)).

{{< admonition type="note" >}}
 This is a new work in progress (WIP) started Feb. 18, 2023 which may be updated over time as volunteers have time to write up information. For sections that are missing, try asking in the live chat as a volunteer may have some clues to get you headed in the right path.
{{< /admonition >}}

## Tools needed

1. Digital multimeter (DMM)
2. Philips screwdriver
3. All schematics, datasheets for known common parts, and links to where to buy replacement parts are all in this article under [Schematics and board data](/documentation/Pinecil/Further_information/Schematics_and_datasheets/).
   * Refer to the correct section for V1 or V2 parts.
   * Which model do I have? The older V1 model has an all black handle with a blue silicone grip and was discontinued in July 2022. The new V2 model has a black handle with a green thumb grip and is the only model PINE64 and authorized resellers started selling after August 1, 2022.
4. Magnifying lamp or jeweler’s glasses with led light and good room light.
5. Photos/videos will help to chat with volunteers in the [live Pinecil chat channel](/community/#chat-platforms) if getting clarification or troubleshooting.
6. Optional: mobile phone to take macro photos or video. A macro lens to take phone photos is helpful; there are cheap ones that simply clip on.
7. Possibly another soldering iron to do the repair, some flux, solder, and isopropyl alcohol (IPA) for cleaning the PCB. See [[Pinecil_Cases,_Stands,_Supplies#Soldering_supplies| this guide]] for some basic supply options.
8. Optional: better needle size probe leads for DMM makes things easier and are nice for electronic work.
9. Reference photos are in the images section.

## Dismantle steps

### Easy trick to open Pinecil

* Video of easy trick: https://www.youtube.com/watch?v=aK01V5DrrVk
* Handle replacement [graphic](https://wiki.pine64.org/wiki/File:Pinecil_Shell_Replacement_Guide.pdf)
* Step-by-step
  1. It is recommended to take photos to help with reassembly.
  2. Loosen the top tip screw (PH1) (top is the side with the screen).
  3. Gently pull the tip out and set aside (let the tip cool down first or use protection to prevent burns).
  4. Slide the rubber thumb grip off the front.
  5. Remove the bottom-front screw (between the bottom feet (PH1)).
  6. Remove the ground screw (longer m2x4mm screw next to the screen near the (-) button (PH1)).
  7. Slightly pull the two halves of the case apart at the tip front end first, enough to get a fingernail or guitar pick between 2 parts.
  8. Move the pick down the length of the split to loosen the bottom half’s clips from the top half of the case.
  9. Once loose, remove the bottom half by sliding it a little forward (it is retained by the top half at the DC barrel side).
  10. Remove the screws retaining the copper tip contacts (PH000, M1.4 x 5).
  11. Remove the copper tip contacts (note the orientation of the contacts & tiny tab hole).
  12. Lift the PCB gently up from Tip end.
  13. Remove the round copper ring contact from under the PCB, near the tip end of the handle (this is installed first before the PCB because it provides ground contact from the front of the Pinecil to the rear ground screw).
  14. Remove the two small round buttons so they do not get lost.

## Assembly steps

1. Place the two round buttons into the two holes in the top half of the case.
2. Install the round copper ground ring at the tip end **before installing the PCB**.
3. Place the PCB board into handle at an angle, DC barrel end goes in first.
   1. Lower the rest of the board into the case and align the PCB with the 2 contact screw holes.
4. Install the two copper tip contacts (note the small tab on the contact and the small hole in the PCB for it).
   1. Orient the contact to align the alignment pin with the alignment hole next to the big hole on one of the big gold pads.
   2. Install and gently tighten the PH000 screw until the clip is no longer loose.
5. Place the bottom half of the case into the top half by sliding the lip on the port side (side without the feet) of the bottom half under the arch of the port side of the top half.
6. Gently close the case by bringing the two halves together, paying attention to each clip’s alignment and ensuring the case edges align.
7. Install the short PH1 screw at the bottom of the tip side of the case.
8. Install the longer PH1 screw at the ground connection point at the top side of the case (between the display and the ports).
9. Slide the rubber sleeve on (larger ridge first).
10. Gently insert tip.
11. Gently tighten the top PH1 screw to retain the tip.

{{< admonition type="note" >}}
 For normal operation of the iron, omission of the copper ring in step #2 does not impact operation. If you are working with ESD components, you need it in order to ground the iron tip via the earth screw at the back of the iron. It is recommended to keep this installed.
{{< /admonition >}}

## FAQ

### Common Fixes

1. Sometimes, just updating to the newest firmware fixes issues as Ralim and team are very active in adding features and enhancements (see [Firmware](/documentation/Pinecil/Firmware/)).
2. Some [Troubleshooting information](https://ralim.github.io/IronOS/Troubleshooting/) is also on GitHub Ralim’s IronOS (which is the firmware that is on the Pinecil). There are several hidden Debug tools in the firmware that also help with diagnosis.
3. Clean all new Tips (Cartridges) with 90%-99% IPA (Isopropyl Alcohol) especially the white end with the 2 silver contacts.
4. If you can’t find the information here or it hasn’t been written yet; simply join the volunteer run [live Pinecil chat channel](/community/#chat-platforms). Sometimes you can get a clue to the right path.

### Common Questions

1. **Temperature is flickering wildly**: 
   * Most likely just need to clean whole cartridge/tip with IPA ([reference issue](https://github.com/Ralim/IronOS/issues/1601)). See [Poor Contact Fix here](/documentation/Pinecil/How_to_repair/#poor_contact_fix)]. 
   * If it’s jumping wildly after reaching set temperature, this is also caused by using a low amp/volt charger that is below the 3amp minimum required for Pinecil (per manufacturer rating), upgrading to a 3.25amp/20V USB-C charger often fixes this ([reference issue](https://github.com/Ralim/IronOS/issues/1644)).
   * Some people might see a random spike while idle. Solution: update firmware, there are some ADC timing adjustments in IronOS 2.21+; it’s a good idea to keep your firmware updated to newest stable release ([reference issue](https://github.com/Ralim/IronOS/issues/1485)). This fix is included in 2.21+ release.
2. **I see No Tip connected symbol randomly on new Pinecil**: tip is installed and it heats up, but randomly I get no tip symbol. See #1 above, it is most likely the same reason, dirty contacts on the back of the cartridge/tip. follow the same instructions for [Poor Contact Fix here](/documentation/Pinecil/How_to_repair/#poor_contact_fix). [Reference ticket on Github](https://github.com/Ralim/IronOS/issues/1601).
3. **How do I install the optional Hall Effect Sensor?** See the Hall Effect Sensor article for installation; location is U14 on the PCB & in the Schematics. Reference schematics section also.
4. **Help, I think I bricked Pinecil doing an update**: no worries, it’s very hard to brick a Pinecil because of the way the firmware is loaded in ROM. Usually just flashing again with a newer or different version brings it back to life ([see Firmware](/documentation/Pinecil/Firmware/)). This can be done even if you can’t see your screen anymore.
5. **My Pinecil keeps rebooting**: change to a different charger or add a ground wire to your Pinecil ground screw (search for _ts100 ground wire_ on a search engine). Also see the [Power Supplies article](/documentation/Pinecil/Power_supplies/). This could happen because of the way 2-prong no-ground chargers are made with no ground path for small current leakage. Also try to plug the charger into a surge protector strip (type that have 3-prong ground and plug the surge protector into a 3-prong grounded wall outlet). Try a different cable or flipping the cable over also.
6. **Tip is glowing red hot**. Unplug immediately, you have most likely a blown MOSFET, check that out, replacement parts in Datasheets below. Tip is probably damaged too.
7. **My temperature display is way off and Pinecil is at room temerature**: first, check the poor contact fix. Then enter the hidden debug menu and look for HAN C which is the internal handle temperature. This should normally be close to or slightly higher than the room temperature if the Pinecil tip is also at room temperature. Under load, the HAN C can go up a bit, otherwise when the tip is cold, the HAN C should be close to ambient. Check the hidden debug menu for HAN C or C Han depending on your version of IronOS. See IronOS [Troubleshooting here](https://ralim.github.io/IronOS/Troubleshooting/), esp. about CHan and the Temperature sensor. If the reading is out of spec (very low/high), and reflowing/resoldering the Temperature sensor does not work, replacement might be needed.
8. **Screen shows X symbol** (no tip installed) and I have a tip installed. Remove the Tip screw, seat the tip all the way back, reinstalled the screw. See [Tips](/documentation/Pinecil/Tips/) and [Poor Contact repair](/documentation/Pinecil/How_to_repair/#poor_contact_fix).
9. **I see `Thermal Runaway` or `Undervoltage` messages on the screen**. This is often caused by using a weak power supply that does not have a minimum of 12V-3amps and is not rated to work with Pinecil. Pinecil will stop heat to the tip and display `Thermal Runaway`.
   * TL;DR get a USB-C charger 20V 3.25 amps, PD 65W (best bang for the buck for good Pinecil performance) many available between $15-$25.
   * Detailed information on chargers can be found under [Power supplies](/documentation/Pinecil/Power_supplies/Power_supplies).
10. **I plugged in the wrong kind of DC barrel charger, it was a not Center-positive pin and now the Pinecil won’t turn on**: see [Reverse polarity damage](#reverse_polarity_damage). Usually requires replacing the MOSFET (U13) and Buck Converter/Step-down (U8). See the datasheets for links to parts.
11. **I hear a sizzling/crackle sound from my new Pinecil**: this is usually fine and may disappear after a few days of use, see [Hissing Crackle Sound](#hissing_crackle_sound).
12. **Screen is black**: first try to update firmware. Check out the IronOS troubleshooting [guide here](https://ralim.github.io/IronOS/Troubleshooting/#no-display-or-dots-on-the-display) for possible issues. See the [datasheets here](/documentation/Pinecil/Further_information/Schematics_and_datasheets/) at the bottom of this article for links to replacement parts. Repair method would be similar to ts100 screens of which there are many guides like [this video](https://www.youtube.com/watch?v=HlWAY0oYPFI). If the tip heats up, but screen is black, the OLED may have failed/burned out. If tip does not heat up, it may be something else. Sometimes just reflow/reheat the solder for the OLED screen fixes issues. Using OLED screen at lower brightness extends the life.

## Solutions

### Hissing Crackle Sound

1. The sizzle sound will usually go away after a few days of use and heating up the iron. After wiping the tip contacts with IPA, heat it up a few times to 350 °C.
2. Ralim said, "there is usually a bit of noise when you first use it, and a slight hiss/pop noise from the handle and that is normal. depends a bit on exactly what batch of caps are in your unit. The Tip drive signal is AC coupled through a capacitor for safety, downside is that it means the firmware is hitting that cap with a square wave the whole time the tip is on. Once you have heated up the duty cycle, it drops off so it’s not as noticeable."
3. Some members reported that after they opened their new Pinecil, wiped the PCB and tips gently with IPA, let it dry, all the sizzling noise went away. They also did a break-in of the new tips, bringing the temperature to 350 C a few times.
4. Video of similar [crackle sound](https://www.reddit.com/r/soldering/comments/qv66a6/weird_crackling_noise_from_ts100_not_from_the_hot/) on the ts100 iron (don’t have example of Pinecil, but it’s similar sound).

### Cartridge/Tip Problems

1. Wipe entire tip (cartridge) clean, details in [Poor Contact](/documentation/Pinecil/How_to_repair/#poor_contact_fix) section
2. Using a multimeter, switch it to ohms to measure resistance. Measure the two silver bands at the rear end (white).
3. If it measures OL or infinity, or extremely out of the spec range below, it might be bad.
   * Normal ts100 style tips should measure ~7.8 ohms - 8.3 ohms.
   * PINE64 brand Short tips should measure ~6.1-6.5 ohms.
   * See the [Tips](/documentation/Pinecil/Tips) for more details.

### Poor Contact Fix

1. Most likely the tip (cartridge) is not making good contact (at the silver bands on the rear white end). Usually this issue goes away after a few days of use as the cartridge rubs against the internal contacts more. New cartridges could have factory residue on them that interferes with the R-tip reading.
2. To fix this issue quicker, wipe all new tips (cartridges) with a dry towel or 90-99% IPA (isopropyl alcohol) especially the two silver contacts at the white end (do not use water to wipe as it could get into the seam line on the white end).
3. With the Pinecil unplugged, remove and reinsert the tip a couple times and spin it a little inside against the contacts. Then plug it in and heat it up to 350 °C a few times for a couple minutes. These steps tend to resolve most new Pinecil or new cartridges causing flickering temperatures or "no-tip" icon displays randomly.
4. Always unplug Pinecil before swapping tips. Hot swapping is not a good idea, and for the V2 this could cause strange behavior as the V2 auto-detects tip resistance only on power-up or reboot.
5. Sometimes just disassembling and reassembling all parts back correctly and installing the 2 internal contacts with screws correctly also helps.
6. Poor contact could happen if the tips are not clean or brand new with factory residue or not making good contact with the internal clips inside the Pinecil. The two contacts inside might need to also be removed, wiped and reinstalled with the two screws (ensure the small metal tab on the clip sits into the small hole in the PCB).
7. See [Pinecil Tips](/documentation/Pinecil/Tips#how_to_check_new_tips?) article for more details on testing.

### Reverse Polarity Damage

Pinecil requires a center-positive DC power supply which most are, but some are reverse polarity and will destroy the electronics if used. If you plugged in a "center-negative" DC power supply, most likely the MOSFET and the buck converter are broken. This usually requires replacing the MOSFET (U13) and buck converter / step-down (U8). See the datasheets for links to replacement parts which is at the bottom of this article [[#Datasheets_for_Components| here]].

{{< admonition type="important" >}}
 **Check the polarity** of the DC barrel plug before plugging in a random charger. Incorrect polarity will break the Pinecil. The [video here](https://www.youtube.com/watch?v=5DBTNplNTfA) shows how to check.
{{< /admonition >}}

{{< figure src="/documentation/images/AC_adaptor_polarity.png" width="400" >}}

{{< figure src="/documentation/images/Nintendo-center-negative.png" width="300" >}}

Reference the article on [[Pinecil_Power_Supplies#DC_Barrel_Power| DC barrel chargers here]], (i.e., laptop bricks) for appropriate USB-C and DC chargers that will work with the Pinecil.

## Images

{{< figure src="/documentation/images/PCP-Top-side-screen.jpg" caption="Screen side: V2 on top, V1 below" >}}
{{< figure src="/documentation/images/PCP-Bottom-Side.jpg" caption="Pinecone side: V2 on top, V1 below" >}}
{{< figure src="/documentation/images/Pinecil_v2_MOSFET.JPG" caption="MOSFET V2" >}}
{{< figure src="/documentation/images/FUSB302-V2-02.JPG" width="302" >}}
{{< figure src="/documentation/images/Pinecil_LDOandOP-Amp.png" caption="_LDO_and_OP-Amp" >}}
{{< figure src="/documentation/images/Under_OLED_screen01.png" caption=" Under the OLED screen, V2" >}}

## Pinecil V1, 24V Mod

{{< admonition type="warning" >}}
 Do this at your own risk, read everything in this section and related/linked articles, and go to the Pinecil community chat if you desire advice. An incorrect cut of the trace could render the Pinecil non-working.
{{< /admonition >}}

{{< figure src="/documentation/images/Pinecil-V1andV2.png" caption="Pinecil V1 has blue rubber. Newer Pinecil V2 has green rubber & Bluetooth LE chip" >}}

1. This modification is not for the V2 (sold after Aug 1, 2022 with green thumb grip) as the V2 already has 24V DC barrel charger capability.
2. If you have an older V1 model, then first upgrade to the newest [firmware here](/documentation/Pinecil/Firmware/) before starting this modification. The PD debug menu was added to the firmware in 2.17 and other important fixes came later. Access to the hidden PD debug menu is necessary to assist with this mod.
3. See Ralim’s IronOS for how to use the hidden [PD Debug here](https://ralim.github.io/IronOS/DebugMenu/#pd-debug-menu) and check if your version of Pinecil V1 could benefit from the modification.
4. If PD-Debug menu says "No VBUS", then stop here, you do not need the modification or any cut of the trace line, it will not benefit you because there is no connection to the VBUS already. If it says "w. Vbus" then continue. If you don’t have a PD-Debug menu, then upgrade to the newest firmware first, see instructions above.
5. Some models of V1 came with the PCB already capable of 24V as the Pine Store made modifications to the PCB (not all batches of V1 were the same). Do the PD debug test first to see if the mod is not required.
6. See the February 2022 [Community update here](https://www.pine64.org/2022/02/15/february-update-chat-with-the-machine/). The photo is incorrect in the article. It is _not_ a before and after photo.
   * Photo shows two separate PCBs of Pinecil V1 made at different times; therefore, the trace is cut in a slightly different location depending on which one it looks like.
   * The PCB with 2 small via holes and is harder to cut in the correct location to avoid damaging the holes. This is called the "whalecil" in community chat (looks like a whale).
   {{< figure src="/documentation/images/Pinecil_V1_24V_Mod.png" width="400" >}}
    PCB 1 style (left photo) is easier to cut the trace. Cut all the way across the trace and deep enough to cut the copper contact. PCB 2 style (right photo) is harder because the trace has to be cut without damaging the 2 via holes.
7. Don’t plug in 24V until you first check with a USB-C PD charger that PD debug says **No VBUS** which means the mod is complete. If it still says **W. Vbus**, then the connection still exist. Cut a little deeper and clean the cut with some IPA (isopropyl alcohol) to remove any copper dust, dry it and check again. Taking a macro photo with a phone helps to examine the cut.
If a USB-C charger is not available, often a phone with a USB-C port is a PD type, and can be used like a charger to plug in and check the PD debug messages (unfortunately, a PC port is not normally "PD" and won’t give proper PD Debug).
8. If you want another set of eyes on it before you cut, post a photo of your PCB (near the Pinecone) on the [Pinecil chat channel](/community/#chat-platforms). Ask for a volunteer who has _completed_ the 24V mod on a Pinecil V1 to assist. Not all chat people own a Pinecil even if they are in the Pinecil channel.
