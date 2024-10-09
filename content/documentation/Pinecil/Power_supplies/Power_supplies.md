---
title: "Power Supplies"
draft: false
menu:
  docs:
    title:
    parent: "Pinecil/Power_supplies"
    identifier: "Pinecil/Power_supplies/Power_supplies"
    weight: 
---

This article is about compatible power supplies for the [Pinecil](/documentation/Pinecil/).

## Power Options for Pinecil

### Overview

1. Using a power supply that is at the higher end of the Voltage/Amps requirements will give faster heating and performance.
2. Any USB-C power supply that supports PD (Power Delivery) and has at least the minimum Volt/amps listed should work. The USB-C PD65W, 3.25A, 20V is recommended, but a lower PD45W will also work on V1.
3. Also, any quality "center positive" DC barrel 12-21V battery or power supply using a DC 5525 jack (5.5mm outer diameter, 2.5mm post) see the video on [center-positive polarity](https://www.youtube.com/watch?v=5DBTNplNTfA). It is sometimes better to get a pre-used name brand laptop brick Dell/Lenovo/HP etc., over a cheap brick which could have voltage spikes that damage the Pinecil or other electronics.
4. V2 can handle a DC barrel supply up to 24V without modifying the PCB (always check polarity, must be a center-positive jack).
5. Any typical tool battery 18V-21V will work, see the tool battery section for details.
6. QC3.0 phone chargers: not recommended, it is weaker in power and does not auto-negotiate like USB-C PD does. QC3 requires manually setting the voltage in the Power settings. A minimum of 3 amps is needed and many QC phone chargers are only able to provide a low 12V 1.5amp, limiting Pinecil to about 17W of thermal capability which is weak and slow. It may not even start to heat, but if it does, it may get repeated `Thermal Runaway` message (this means the weak power causes Pinecil to auto-shutdown continuously).
7. QC is more problematic for V2 which comes with the Pine64 designed shorter 6.2 ohm resistance tip. This means the V2 needs more power than the V1. Switching to the longer tys100 style tip in V2 would reduce the power requirement a little, but then you lose a small amount of heat speed/performance.
8. Magnetic tip USB-C cables are not recommended, and are not USB compliant.

### Troubleshooting QC chargers

1. older QC2.0 chargers are not supported in IronOS firmware (only QC3.0 and PD type).
2. Some QC power adapters only allow a limited time for QC negotiation, otherwise voltage will fall back to 5V. To address this, starting from firmware v2.16+, there is a PD timeout setting (in 100ms steps) which allows QC negotiation to start earlier. Change this only if you are having issues with your QC charger (lower the PD timeout to see if that will help QC charger work). (Power Settings > PD timeout)
3. This enables some QC adapters to work (i.e., some Baseus QC chargers). Alternately, lowering the number may result in problems with PD negotiation on some PD type adapters that are slower to negotiate. If you switch between QC & PD adapters, you may have to change this setting.
4. For certain QC adapters, lowering the PD timeout value to 15 could help, and most PD adapters will also still work using 15. If a PD charger does not work at 15, then increase the timeout (PD default is 20 = 20x 100ms = 2 seconds).
5. Note that some QC chargers simply will not work, are too weak, or cheaply made (PD USB-C chargers are recommended over QC only type)

### How to Test if my charger will work?

As long as you do the following you should be fine:

1. Don’t plug in something that is higher voltage than the official ratings for V1 (21v limit) or V2 (24V limit).
2. If using a DC barrel charger, **check the Polarity first**, it must be center positive ([see Video](https://www.youtube.com/watch?v=5DBTNplNTfA))
3. Use a known good quality cable that will not short. There are low cost $3 cable testers that test for shorts.
4. If the Pinecil heats up very slowly or gets `Thermal Runaway` message, then the charger is too weak, get something else.
5. Phone chargers are too weak, most are only 12V 1.5 amps which is too low and prevent proper Pinecil operation.
6. QC 2.0 not supported by IronOS firmware (only QC 3.0 and PD type).
7. most PC & laptop ports don’t work as they are only 5V which is good enough for simple Firmware updates but not to provide the constant higher power a "resistance" type of soldering Iron needs to maintain heat.
8. Check the specs on your laptop/PC ports and charger ports, most of the time when it doesn’t work, it’s because the rating is very low on it and not designed to power an Iron (check specified Watts, Volts, Amps on the port and see if they meet the minimum needed by Pinecil).

## Cables, Chargers, Batteries

This is a very small list compared to all the possible chargers that work, and new chargers come on the market all the time.

### USB-C Cables

Silicone USB-C cables are recommended if possible, they are more flexible and heat resistance. They do not melt or smoke if touched briefly with an iron compared with most other cords.

### USB-C Charger

#### Should I get a GaN type Charger?

* Sure, if there are two PD65 20V chargers that are similar in price, and one is GaN, this is generally a good chioce.
* Older style chargers could become dangerously hot, whereas GaN can stay cooler, even in a smaller size.
* If the GaN charger senses a potentially dangerous condition, i.e., overcurrent spikes, the chips are designed to go into a cycle-by-cycle sleep state, protecting the device. [Over current protection in GAN](https://www.ti.com/lit/an/snoaa15/snoaa15.pdf).
* The [PinePower Portable PD65](https://pine64.com/product/pinepower-65w-gan-2c1a-charger-with-international-plugs/) is GAN II (2nd generation GaN).
* Will Pinecil work with regular USB-C PD 65w 20V-3.25A chargers also? Yes, as long as it supports PD (power delivery protocol).

#### EPR PD3.1, 140W Chargers

1. Voltme 140W, 28V max
2. Rocoren 140W, 28V max
3. Apple 140W 28V
4. Anker 737 Power Bank (only EPR battery on the market presently).

{{< admonition type="note" >}}
 a PD3.1 240W cable needs to be purchased if you want the full 28V performance. EPR PD3.1 chargers are backwards compatible and work for all USB-C devices. They do up to 28V on PD3.1 devices,e.g, Pinecil V2, and will do 20V and less for older USB-C devices that don’t need as much power. Lower cables will also work but then the charger will only deliver a max of 20V.
{{< /admonition >}}

#### PD3.0 65w 20V Chargers

{{< figure src="/documentation/images/USB_C_PD_shared_watts_charger.jpg" width="400" >}}

1. [PD120w PinePower Desktop w/Grounded 3-pin plug](https://pine64.com/product-category/pinepower/)
2. [PD65w GAN II Pinepower Portable Travel charger](https://pine64.com/product/pinepower-65w-gan-2c1a-charger-with-international-plugs/) (PD@20V)
3. Cirtek 65W charger 3-port
4. Etre Jeune 65W 3-port charger
5. EfaithFix PD65W, 3-port
6. TREBLEET Ultra-thin Portable PD65w
   * small flat, full 20V PD65W charger, works well with Pinecil
   * it may not as durable as bigger chargers as it has no thick insulation around it.
7. HTC PD65W, 3-port black
8. HTC PD65W, 3-port, white
9. Amazon Basics 65W One-Port GaN USB-C PD 3.0

### Battery Power bank

1. Anker 737 28V-140W EPR (must use EPR-PD 3.1 240W cable if you want the full 28V, otherwise it will provide a lower PD20V)
2. Blitzwolf BW-P1 10400mAh QC2
3. Insignia 80W 26,800mAh NS-PWLB80
4. Intenso 7332330 Powerbank PD 10000 - External Battery PowerDelivery & QuickCharge3 - 10000mAh Powerbank, the Pinecil shows 12V and about 17W when heating up, using USB C PD (Red Silicone Pinecil cable)
5. Marbero M87 30W PD 3.0
6. Charmast C2032 65W Power Bank, maximum power at 20V is only available from the IN/OUT USB-C port, the OUT USB-C port delivers only 12V.
7. Baseus BiPow 10000mAh 18W PD&QC3.0
8. INIU Power Bank 65 W 25000 mAh - Make sure to use the 65W port

### DC Barrel Power

{{< admonition type="important" >}}
 **Check the polarity** of the DC Barrel plug before plugging in a random charger or it could break the Pinecil.
{{< /admonition >}}

{{< figure src="/documentation/images/AC_adaptor_polarity.png" width="350" >}}

{{< figure src="/documentation/images/Nintendo-center-negative.png" width="350" >}}

### DC Laptop Brick

1. Generally a center-positive laptop charger with more than 3 Amps and 19V-24V will work on Pinecil V2 ([video to check polarity](https://www.youtube.com/watch?v=5DBTNplNTfA)). Plugging in a DC barrel charger with the wrong polarity symbol on the back will break the Pinecil.
2. **Avoid Universal power supplies and cheap off-brand ones** with low quality control. &lt;tl_lim> said "try to avoid such universal power. The output contains sharp voltage spike and can kill the Pinecil. There are already several cases reported by support team that Pinecils are damaged by such power supply."
3. Read the 2 answers in [this link](https://community.element14.com/products/manufacturers/keysight/f/forum/39013/what-is-the-effect-of-switching-noise) that give an idea of why using cheap DC power supplies could damage electronics due to switching noise/voltage spikes. Cheap DC bricks don’t have all the extra protections needed, go through little quality control, and most have no certification stamps related to industry testing.
4. DC5525 barrel plug will plug in directly (5.5mmm x 2.5mm) but if you have a different plug, there are many adapters to convert it to 5.5mm, 2.5mm (don’t force a different plug into Pinecil, [it will Break the barrel port](https://forum.pine64.org/showthread.php?tid=13237)), and possibly push back and break the positive pin connection inside Pinecil where the DC barrel attaches to the PCB.
5. DC barrel 24V is supported on V2 (most V1 can only do a max of 21V unless a modification is performed to cut the trace to the Vbus and enable 24V safely (see [Ralim’s IronOS DebugMenu for details](https://github.com/Ralim/IronOS/blob/dev/Documentation/DebugMenu.md#pd-debug-menu)))
6. It is recommended to use a quality brand DC barrel charger. Often a used name-brand laptop charger (Dell, HP, Toshiba, etc..) that gets some QC testing is a better option than a no-name cheap DC barrel charger. The cheap ones might have large voltage spikes that are out of the 21V range for Pinecil V1 and 24V range of Pinecil V2 causing the Mosfet and Buck regulator to break.
   * These two parts are low cost and not too hard to replace if your Pinecil breaks from a poor quality DC charger (see the datasheets section for links to get replacement chips).
   * Members have experienced broken Pinecils after using low quality off-brand DC barrel chargers and had to replace both the Mosfet and Buck Converter. Sometimes it’s just one part, but it’s best to order a couple of both as they are usually under $0.35 each.

### Tool Batteries 18V-21V

{{< figure src="/documentation/images/Power_Wheel_Adapters_for_18-21V_Tool_Batteries.png" width="475" >}}

[Power-Wheels adapter link](https://a.co/bo626Nk) with Ryobi battery

* Easy way: just get a Power Wheels adapter. They are made for different tool brands and get a DC5525 Pigtail wire.
* [DC5525 pigtail](https://www.amazon.com/Hobbypark-Connector-Soldering-Outdoor-Repairing/dp/B08LKY5DBX) (keep the XT60 connector or cut it off)
* Some people print their own 3D adapters for tool batteries.
  * Must use a 5.5mm x 2.5 mm DC barrel Plug. Forcing an an incorrect size, i.e., DC 5521 will break [the connector as seen here](https://forum.pine64.org/showthread.php?tid=13237) (if it doesn’t go in, it doesn’t fit).
* If you use a random DC barrel charger, first Check the Polarity of the plug to make sure it is Center Positive before using it. [(how to check polarity)](https://www.youtube.com/watch?v=5DBTNplNTfA). Using reverse polarity DC plug will destroy the Pinecil.
* Get a Power Wheels Adapter [like this for Ryobi](https://smile.amazon.com/gp/product/B09GXBJMNF), then splice/connect it to a DC5525 Pigtail to complete connection to Pinecil.
  * Other kinds of [Power-Wheels Adapters here](https://smile.amazon.com/stores/page/F3CF7FFA-3021-4014-AA81-E214F6F7CEDC?ingress=0&visitId=485f97ee-6a92-43e8-aaef-479873fccd6f) (Ridgid, Milwaukee, Makita, etc).
  * [Adapter for Ridgid batteries](https://www.amazon.com/Adapter-Battery-terminals-Connector-Robotics/dp/B09GY21VXL)
* To prevent battery overdrain, add this Pinecil setting which works for all the 18-21V tool batteries typical for Dewalt, etc.. Some tool brands have the overdrain protection already; it doesn’t hurt to also set this in Pinecil or in case you don’t know if your brand/type has it or not. ` Power source = 5S, Minimum Voltage = 3.3V `
* Hint: only if you change to a different size battery do you need to alter this. If you only ever switch between a USB-C charger and the tool battery, you could just leave the 5S/3.3V setting. Overdrain means using the battery past the point where you can charge it again. Many tool batteries have internal protection to prevents this, but some brands don’t have it (unfortunately, unlike most brands, Dewalt puts it into the tool & not the battery). Setting it in Pinecil is an extra safety setting in case you are not sure and want to preserve batteries.

**Limited usability:**

* Nintendo Switch AC Adapter (USB-C wall-wart) (PD@15V). Does not work well on V2 (needs 3+amps). Works on V1, but slower heat speed because it’s low amps and only 15V.
* Notebook Docking Station HP Thunderbolt Dock 230W G2 (PD@20V) (had problems with lower firmware versions, but works fine Pinecil firmware: 2.15 and DockingStation firmware: 1.0.69.1)
* Smartphone Charger Samsung EP-TA20EWE (QC2@9V)
* Smartphone Charger Google Pixel G1000-US (PD@9V)
* Notebook AC Adapter Delta Electronics ADP-65JH BB (DC@19V) and ADP-90CD DB (1.7x 4.8mm need adapter, tip is not DC5525)
* Notebook AC Adapter LITEON PA-1700-02 (DC@18.5V, 65W) (tip is 1.7mmx5.5mm would need adapter for DC5525)
* Nillkin 63W USB Car Charger Quick Charge 3.0 PD (Pinecil Firmware: 2.14.2425902)
  * QC3@9V/12V and PD@15V work, PD@20V doesn’t
  * PD@20V works fine when using PDC004-20V or ZY12PDN on dc jack (DC@20V, limit: 45W)

#### Not compatible

* Zendure Power bank like [this one](https://www.amazon.com/dp/B07P8NRNX7) does not work. It does not appear to be USB-C PD 3.0 compliant. Only the USB-A port seems to work at lower QC voltage. It does not deliver USB-C 20V-5amps or USB-C 20V -3amps.
* Smartphone Charger RAVpower 30W Dual USB Turbo Wall Charger (Should provide QC3@9V/12V, but only provides 5 V on both ports)
* Sabrent HB-B7C3 USB3 hub, 7 data ports, 3 charge ports, 60W supply -- does not negotiate higher voltages.
