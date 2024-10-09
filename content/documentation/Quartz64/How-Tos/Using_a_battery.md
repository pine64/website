---
title: "Model A: Using a battery"
draft: false
menu:
  docs:
    title:
    parent: "Quartz64/How-Tos"
    identifier: "Quartz64/How-Tos/Using_a_battery"
    weight: 
---

The [Quartz64 Model A](/documentation/Quartz64) allows for it to be powered from a single-cell 3.7V lithium-polymer battery. Because of [unfortunate incidents](https://en.wikipedia.org/wiki/UPS_Airlines_Flight_6), batteries are not easy to ship internationally, so PINE Store does not sell a matching battery for the board.

## Pin-out

{{< figure src="/documentation/images/Quartz64_Model_A_VBAT_Connector_Pinout.png" title="right" >}}

The pins on the board are a JST PH-3 compatible header labelled _+VBAT-_. As one might guess, the positive wire should be towards the +, and the ground wire towards -. The center pin of the connector is for a temperature probe.

## Ways to get a battery

We will now go into various ways one might go about getting a working battery.

### Crimping one yourself

You will need:

* an Engineer PA-20 ([Amazon Search](https://www.amazon.com/s?k=Engineer+Pa-20), [eBay Search](https://www.ebay.com/sch/i.html?kw=Engineer%20PA-20)) or Hozan P-707 ([Amazon Search](https://www.amazon.com/s?k=Hozan+P-707), [eBay Search](https://www.ebay.com/sch/i.html?kw=Hozan%20P-707)) or similar crimp tool (&lt;$80, good to have around anyway)
  * The Hozan P-707 is also comparatively good at crimping "Dupont"-style terminals, in case you find yourself doing that a lot, because it provides round crimping holes in addition to rectangular ones.
* JST PHR-3 receptacles ([~$0.05 on digikey](https://www.digikey.com/en/products/detail/jst-sales-america-inc/PHR-3/527357))
* 3&times; JST SPH-002T-P0.5L crimp terminals ([~$0.03 on digikey per terminal](https://www.digikey.com/en/products/detail/jst-sales-america-inc/SPH-002T-P0-5L/1300246))
  * When ordering from digikey, try to hit the minimum order cost to qualify for free shipping; you’ll get free fast courier shipping with all customs and duties pre-paid.
* a single-cell 3.7V lithium-polymer battery, ideally with a temperature probe
  * 2800 mAh Renata ICP606168PRT on [Conrad Germany](https://www.conrad.de/de/p/renata-icp606168prt-spezial-akku-prismatisch-kabel-lipo-3-7-v-2800-mah-1214021.html), [Conrad Switzerland](https://www.conrad.ch/de/p/renata-icp606168prt-spezial-akku-prismatisch-kabel-lipo-3-7-v-2800-mah-1214021.html)
  * 2000 mAh Adafruit on [Adafruit US](https://www.adafruit.com/product/2011) (no temperature probe, pre-crimped with JST PHR-2; just lift up the plastic tabs and pull out the terminals and shove them back into a PHR-3 connector)
  * Aliexpress: try keywords "3.7v lithium battery temperature probe"

Crimp the terminals onto the wires, crimp the strain relief onto the insulation, slide them into the connector until they firmly click in place.

### PINE64 18650 battery case

You will need:

* [PINE64 Lithium Battery Casing](https://pine64.com/product/lithium-battery-casing/)
* an 18650 sized lithium battery (**not** LiFePo4!)

**TODO:** Get one of these and document how to use them

## Using the battery

### Hardware

1. Ensure the wires in the connector are in the right order.
2. Turn off your Quartz64 Model A.
3. Remove the BAT ON/OFF jumper.
4. Plug in your battery.
5. It is now ready to use if your device tree has been set up correctly.

### Caveats

Not all parts of the board can be supplied from the battery. When you use battery as backup power for the board keep in mind that following parts of Quartz64-A will lose power when DCIN loses power:

* 12V Fan connector
* EDP LCD backlight
* 5V power rails on the 20 pin GPIO header
* PCIe socket (both 12V and 3.3V supplies)
* All USB ports except for the black one
* Black USB port’s VBUS (the one above the USB 3.0 port) will go through a 22ms brownout to approximately VCC_SYS - 0.6V voltage, before the RK817 BOOST regulator kicks in. This will likely cause the connected USB device to reset or have its internal state corrupted.

{{< figure src="/documentation/images/Quartz_64_Model_A_VBUS_Brownout.png" width="640" >}}

### Software

For the battery to be correctly detected, you will need to edit the device tree to add the charger and battery nodes, like this:

```
	// add this to root node (you may need to modify the values to fit your chosen battery)
	battery: battery {
		compatible = "simple-battery";
		charge-full-design-microamp-hours = &lt;6400000>;
		charge-term-current-microamp = &lt;200000>;
		constant-charge-current-max-microamp = &lt;2000000>;
		constant-charge-voltage-max-microvolt = &lt;4200000>;
		factory-internal-resistance-micro-ohms = &lt;117000>;
		voltage-max-design-microvolt = &lt;4200000>;
		voltage-min-design-microvolt = &lt;3200000>;

		ocv-capacity-celsius = &lt;20>;
		ocv-capacity-table-0 =  &lt;4200000 100>, &lt;4054000 95>, &lt;3984000 90>, &lt;3926000 85>,
					&lt;3874000 80>, &lt;3826000 75>, &lt;3783000 70>, &lt;3746000 65>,
					&lt;3714000 60>, &lt;3683000 55>, &lt;3650000 50>, &lt;3628000 45>,
					&lt;3612000 40>, &lt;3600000 35>, &lt;3587000 30>, &lt;3571000 25>,
					&lt;3552000 20>, &lt;3525000 15>, &lt;3492000 10>, &lt;3446000 5>,
					&lt;3400000 0>;
	};

	// add this to &rk817 node
	rk817_charger: charger {
		monitored-battery = &lt;&battery>;
		rockchip,resistor-sense-micro-ohms = &lt;10000>;
		rockchip,sleep-enter-current-microamp = &lt;300000>;
		rockchip,sleep-filter-current-microamp = &lt;100000>;
	};
```

You will also need to make sure that CONFIG_CHARGER_RK817 is enabled in your kernel.
