---
title: "Additional hardware"
draft: false
menu:
  docs:
    title:
    parent: "Pinebook_Pro/Features"
    identifier: "Pinebook_Pro/Features/Additional_hardware"
    weight: 
---

Hardware that is not part of the SoC.

## Battery

* Lithium Polymer Battery (10,000 mAh; 9,600 mAh in later batches)
* Monitored by CW2015 which only measures the current voltage; reported state (charging/discharging), capacity (State-Of-Charge), remaining runtime and current are (poor) estimates

## Display

* 14.0" 1920x1080 IPS LCD panel

## Lid closed magnet

There is a magnet to detect when the laptop lid is closed, so action can be taken like sleep. This meets up with the Hall sensor on the daughter / small board to detect lid closed.

* The magnet is located on the LCD panel right side, around 1.5 inches up measure from bottom edge.

## Webcam

* Internal USB attached Webcam

## Audio

* 3.5mm stereo earphone/microphone plug
* Built-in microphone
* Built-in stereo speakers:
  * Oval in design
  * 3 mm high x 20 mm x 30 mm

## Network

* WiFi:
  * 802.11 b/g/n/ac
  * Dual band: 2.4Ghz & 5Ghz
  * Single antenna
* Bluetooth 5.0

## Optional NVMe adapter

* PCIe 1.1, 2.5 GT/s per lane
  * Note that due to errata, PCIe is limited to Gen1. See [this commit](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/arch/arm64/boot/dts/rockchip/rk3399.dtsi?id=712fa1777207c2f2703a6eb618a9699099cbe37b).
* Four PCIe lanes, which can not be bifurcated, but can be used with one- or two-lane NVMe cards
* **M** keyed, though **M**+**B** keyed devices will work too
* Maximum length for M.2 card is 80mm (M.2 2280). The following sizes will also work: 2230, 2242, 2260
* Power: 2.5 W (continuous)
* Does not support SATA M.2 cards
* Does not support USB M.2 cards
