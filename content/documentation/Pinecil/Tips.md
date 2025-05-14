---
title: "Tips"
draft: false
menu:
  docs:
    title:
    parent: "Pinecil"
    identifier: "Pinecil/Tips"
    weight:
aliases:
  - /wiki/Pinecil_Tips
---

This article is about the available tips for the [Pinecil](/documentation/Pinecil) and how they work.

## Pinecil Tips

{{< admonition type="tip" >}}
Pay attention to the length! Pine Store sells two different lengths of tips.
{{< /admonition >}}

### What kind of tips work?

1. Pinecil V2 uses both Pine64 designed Short Tips (ST line, 6.2-6.5 Ω) and TS-100 Normal length compatible tips (TS line, ~8.0 Ω).
2. Presently, the V1 uses the normal length TS100 style tips (~8.0 ohms) until a firmware update enables manually switching the tip types. Check Github Ralim’s IronOS [here](https://github.com/Ralim/IronOS/issues/1558) for progress on this.
3. **Unplug before swapping** tips as the V2 automatically detects the tip resistance at boot-up and it is safer.

### How to increase tip life?

1. Typically, lead solder uses a working temperature of ~300°C-320°C and no-lead solder ~350°C-365°C (check the temperature charts in [the soldering guides](/documentation/Pinecil/Guides_to_soldering/#what_temperature_should_i_use) or google it for your specific solder type, it varies). Always start lower than needed and increase ~5°C at a time until you reach a good working temperature. If you want your tips to last longer, use the lowest temperatures you can comfortably work at. Thicker wires, etc., may need more (adjust).
2. The open source firmware may allow the use of temperatures past the manufacturer limit for tips, but that doesn’t mean you should. That said, people have reported using the boost feature at 5-15 second burst to >430°C and have been perfectly fine (TS100 and Pine64 tips are readily available at reasonable prices and some people prefer convenience of higher temperatures and accept they might replace tips more frequently as a trade-off).
3. If the tips are not too expensive, some keep spare tips and boost to high temperatures freely for convenience, and simply replace the tip when it loses the plating or the tip fails (common sign of tip failure is tip plating is gone, has pit holes, or a multimeter measures OL infinite ohms across the 2 silver contacts on the cold end of the tip).
4. Check out this [Soldering Guide article](/documentation/Pinecil/Guides_to_soldering) for more details on best practices for use and maintenance of tips.

### How to check new tips?

{{< figure src="/documentation/images/Multimeter_measuring_Short_Tip.png" caption=" Short Tip 6.2 Ω" width="200" >}}

1. Remove the screw on top, then remove the cartridge. Clean new cartridges/tips with isopropyl alcohol (IPA) to remove any factory residue before installing (avoid strange behavior). If you have no IPA, use a dry clean towel, especially the white end with the two silver contacts (do not use water; it could get into the seam line on the white end). This often resolves issues with glitchy temperatures or random no-tip symbol from poor or dirty electric contact [reference]https://github.com/Ralim/IronOS/issues/1601).

{{< figure src="/documentation/images/CleanTip-Cartridge-Contacts.jpg" caption="Clean contacts with IPA" >}}
	
. Then install the cartridge/tip, re-install the screw on top, and heat the tip a few times to 350 °C for a couple minutes.
. If you don’t have a multimeter, then after you initially heat the tips a few times to 350 °C. Then change the temperature to the [correct range](/documentation/Pinecil/Guides_to_soldering#what_temperature_should_i_use?) for the solder you purchased and check if it melts solder (add a little solder to the tip end also before storing it).
. If you have a multimeter (dmm) and have an issue with the cartridge/tip, then you can measure when the tip is cold (room temperature and unused a couple hours). Set dmm to ohms and the correct range, and measure the 2 silver contacts on the rear white end.
. Warning: warm tips change the measurements (measure only when cold and unused for a couple hours).
* Short tips could be ~6.2-6.5 ohms
* Normal length tips could be ~7.8-8.3 ohms
* If the tip measures OL (open loop) it is defective. Also a tip that is way off spec, e.g., 10 ohm will cause strange behavior on temperature readings.
* If you measure when it’s even a little warm, the ohms will be much higher; this is normal and how the cartridge/tip works.

### Why have different tips?

* See the [Soldering Guides](/documentation/Pinecil/Guides_to_soldering#general_soldering_guides) for usage of different tips and how to keep tips clean.

### How does the tip work?

1. A thermocouple is integrated into the end of the tip itself; advantage is every new tip includes a brand new thermocouple and it’s a more accurate measurement of the temperature.
2. Pinecil tips are considered [newer tech style](https://www.youtube.com/watch?v=kmq769_ed9w). This is more accurate compared to older style Irons where the thermocouple is in the handle and much farther from the end of the tip.
3. [Science: what is a thermocouple?](https://www.youtube.com/watch?v=v7NUi88Lxi8)
4. [How is Tip Temperature measured in Ralim’s IronOS firmware?](https://ralim.github.io/IronOS/Temperature/)
5. [What does the inside of a ts100 tip look like?](http://www.minidso.com/forum.php?mod=viewthread&tid=1110)

## Pine Store Tip Options

### I. Short tips

{{< admonition type="important" >}}
 **Pay attention to the length in your cart!** Pine Store sells two different lengths.
{{< /admonition >}}

1. All new Pinecil V2 soldering irons include a single Pine64 newly designed Short tip (ST-B2 conical).
2. The discontinued V1 came with a longer normal length TS-B2 conical tip.
3. Pine Store carries 4-Packs of Pine64 designed Short Tips (only Pine64 makes the short style presently)
   * Short tips [Fine link, white box](https://pine64.com/product/pinecil-soldering-short-tip-set-fine/) (~6.2-6.5 Ω)
   * Short tips [Gross link, white box](https://pine64.com/product/pinecil-soldering-short-tip-set-gross/) (~6.2-6.5 Ω)
4. Pine64 Short tip packs are lower resistance/ohms which means higher performance and better ergonomics. Many professional irons have shorter tips for more control while soldering.

{{< admonition type="note" >}}
 Older Pinecil V1 can not use the short tips until firmware code is written to enable manual selection of 6.2 Ω or 8.0 Ω tip. **Only the V2 model** has the hardware to auto-detect the two kinds of tips short 6.2 Ω or regular length 8.0 Ω. If you would like to help with the code, see [GitHub/IronOS](https://github.com/Ralim/IronOS).
{{< /admonition >}}

{{< figure src="/documentation/images/Pinecil-Short-Tip-SetGross-1.jpeg" caption="Short gross set, white box" >}}
{{< figure src="/documentation/images/Pinecil-Short-Tip-SetFine-1.jpeg" caption="Short fine set, white box" >}}
{{< figure src="/documentation/images/Pinecil-ST-B2.jpg" caption="ST-B2 conical short tip included with the V2 Pinecil" width="250" >}}

* The shorter tip is designed for higher performance and requires more power than longer traditional TS100 tips
* Recommend using minimum of usb-C PD65W-3.25A-20V or higher voltage charger when using Short tips (short tip draws more power than longer tips because of the lower ohms).
* For example with a PD65W-20V charger, the maximum watts with a standard 8 ohm tip is 50W, whereas the max watt with a 6.2 ohm tip is ~64 watts ([watts/volts calculator](https://www.rapidtables.com/calc/electric/watt-volt-amp-calculator.html)).
* Heating formula: P = IV = I^2 * R = V^2 / R (⇧ watts = ⇧ faster heating)

      20V @8Ω tip=50W; @6.2Ω tip=64.5W
      24V @8Ω tip=72W; @6.2Ω tip=92.9W

### II. Normal tips

{{< admonition type="important" >}}
 **Pay attention to the length!** Pine Store sells two different lengths.
{{< /admonition >}}

* Normal Length [Gross Set here](https://pine64.com/product/pinecil-soldering-tip-set-gross/) (~8.0 Ω)
* Normal Length [Fine Set here](https://pine64.com/product/pinecil-soldering-tip-set-fine/) (~8.0 Ω)

{{< figure src="/documentation/images/Pinecil-Tip-SetFine-1.jpg" caption=" Fine Set, Normal length" width="250" >}}

{{< figure src="/documentation/images/Pinecil-Tip-SetGross-1.jpg" caption=" Gross Set, Normal length" width="250" >}}

{{< figure src="/documentation/images/PinecilTipSets.jpg" caption=" Regular Length TS Tips: Left= Fine set, Right = Gross set. Both TS sets have ~8.0 ohm tips and are the standard length similar to other TS100 style tips." width="500" >}}

{{< admonition type="important" >}}
 Currently, Pinecil V1 original uses the normal length ts100 style tips and not the newer Short tips designed for V2. Ralim is working on adding a feature to the firmware to allow people with the older V1 Pinecil to manually switch a profile setting which allows toggling between Normal Tip and Short tip profiles (adequate power supply must also be used min. PD65w 3.25A, 20V recommended). Check Github Ralim’s IronOS for progress information. Always unplug when swapping tips.
{{< /admonition >}}

### Other compatible tips

{{< figure src="/documentation/images/TS100-Tip-Styles.png" caption=" BC3 and JL02 are not sold by Pine Store, ~8.0 Ω" width="300" >}}

**Common resistances for tips:**

{{< figure src="/documentation/images/TipResistance2.png" width="200" >}}

* PINE64 designed short tip 6.2 Ω, shorter length, only at pine64.com.
* no brand long tip 7.9 Ω, normal length ts100 style
* Miniware long tip 8.0 Ω, normal length ts100 style
* no brand long tip 8.3 Ω, normal length ts100 style

**Compare different soldering iron sizes:**

This photo shows common irons to compare the distance from the finger grip to the work surface.

{{< figure src="/documentation/images/Compare-iron-tip-sizes.jpg" width="500" >}}
{{< figure src="/documentation/images/Compare-PinecilV2-iron-sizes.png" width="500" >}}
