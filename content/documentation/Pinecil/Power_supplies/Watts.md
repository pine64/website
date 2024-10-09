---
title: "Watts"
draft: false
menu:
  docs:
    title:
    parent: "Pinecil/Power_supplies"
    identifier: "Pinecil/Power_supplies/Watts"
    weight: 
---

Generally, a higher power charger is better; a 20V power supply will give better performance than a 15V charger. The Pinecil needs a minimum of 3 amps and will work with higher amps charger. However, do not exceed the volts rating for V1 and V2 models or damage to components could occur (see the side of the Pinecil handle for the maximum volts).

## Power Chart

| Type | Volts | / | Tip Ω | = | Amps | * | Volts | = | Watts |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| USB-C PD3.0 | 20V | / | 8.0 Ω | = | 2.5A | * | 20V | = | **50W** |
| USB-C PD3.0 | 20V | / | 6.2 Ω | = | 3.2A | * | 20V | = | **64W** |
| DC Barrel | 24V | / | 8.0 Ω | = | 3.0A | * | 24V | = | **72W** |
| DC Barrel | 24V | / | 6.2 Ω | = | 3.8A | * | 24V | = | **92W** |
| **EPR PD3.1 | 28V | / | 8.0 Ω | = | 3.5A | * | 28V | = | *98W** |
| **EPR PD3.1 | 28V | / | 6.2 Ω | = | 4.5A | * | 28V | = | *126W** |

## Power Notes

* PINE64 officially states the Pinecil V2 will support up to 24V-88W. Tentatively, the V2 also _unofficially_ supports 28V-140W EPR/PD3.1 USB-C chargers with certified EPR 240W USB-C cables.
* DC barrel power is 24V-5A maximum on V2. This allows headroom for higher spikes that happen in DC bricks or off-brand bench supplies. It is _not a smart charger_ like a USB-C charger which uses chips to negotiate with devices like the Pinecil.
* [Ralim’s IronOS firmware](https://ralim.github.io/IronOS/#getting-started) works with the PD3.1 protocol (EPR 28V-140W chargers) on Pinecil V2.
* EPR USB-C is new to the market in 2022. The first wave of these smart chargers are 28V/140W, are more expensive, and require a PD 3.1/240W cable to fully allow the 28V power to V2.
* EPR is backwards compatible for all USB-C devices. EPR chargers/cables can be used for everything else USB-C as well.
* Pinecil is not a USB-C tester: when the _detailed screen_ is enabled on Pinecil, note it shows estimates and are at best +-10%. The watts shown on _detailed_ mode are a big picture number for convenience and debugging various chargers used. It is not going to be as accurate as an external tester. Use external metering for comparisons or testing (external testers also cause a small reduction in Watts).

## QC Chargers

Many Quick Charge or QC3 phone chargers are **not recommended** as Pinecil V2 is rated for a _minimum of 3 Amps_ or more to work properly (see [Pine Store Official rating](https://pine64.com/product/pinecil-smart-mini-portable-soldering-iron/) on power ports). Most QC 12V phone chargers are only 1.5 Amps, this will lead to `Thermal Runaway` or `Undervoltage` messages because of weak power (older QC2 type is not supported in the IronOS firmware at all).
