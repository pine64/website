---
title: "Internal layout"
draft: false
menu:
  docs:
    title:
    parent: "Pinebook_Pro/Features"
    identifier: "Pinebook_Pro/Features/Internal_layout"
    weight: 
---

## Main chips

* RK3399 system-on-chip (1)
* LPDDR4 SDRAM (21)
* SPI NOR flash memory (29)
* eMMC flash memory module (26; Note: Some datasheets indicate a low supported number of mating cycles.)
* WiFi/BT module (27)

## Mainboard Switches and Buttons

There are two switches on the main board: disabling the eMMC module (24), and enabling serial console UART (9) via headphone jack.

The Reset and Recovery buttons (28): the reset button performs an immediate reset of the laptop. The Recovery button is used to place the device in maskrom mode. This mode allows flashing eMMC using Rockchip tools (e.g. rkflashtools).

{{< figure src="/documentation/images/PBPL_S.jpg" width="500" >}}

## Key Internal Parts

| Number | Type | Descriptor |
| --- | --- | --- |
| 1 | Component  | RK3399 System-On-Chip |
| 2 | Socket | PCIe x4 slot for optional NVMe adapter |
| 3 | Socket | Speakers socket |
| 4 | Socket | Touchpad socket |
| 5 | Component | Left speaker |
| 6 | Connector | Power bridge connector |
| 7 | Socket | Keyboard Socket |
| 8 | Component | Optional NVMe SSD adapter |
| 9 | Switch | UART/Audio switch - enables serial console UART via headphone jack |
| 10 | Socket | Power bridge socket |
| 11 | Socket | Battery socket |
| 12 | Component | Touchpad |
| 13 | Component | Battery |
| 14 | Component | Right speaker |
| 15 | Socket | MicroSD card slot |
| 16 | Socket | Headphone / serial console UART jack |
| 17 | Socket | USB 2.0 Type A |
| 18 | Socket | Daughterboard-to-mainboard ribbon cable socket |
| 19 | Cable | Daughterboard-to-mainboard ribbon cable |
| 20 | Component | microphone |
| 21 | Component | LPDDR4 RAM |
| 22 | Socket | Mainboard-to-daughterboard ribbon cable socket |
| 23 | Socket | Microphone socket |
| 24 | Switch | Switch to hardware disable eMMC |
| 25 | Antenna | BT/WiFI antenna |
| 26 | Component | eMMC flash memory module |
| 27 | Component | BT/WiFi module chip |
| 28 | Buttons | Reset and recovery buttons |
| 29 | Component | SPI flash storage |
| 30 | Socket | eDP LCD socket |
| 31 | Socket | Power in barrel socket |
| 32 | Socket | USB 3.0 Type A |
| 33 | Socket | USB 3.0 Type C |

## Smallboard detailed picture

{{< figure src="/documentation/images/Pinebook_pro_smallboard.jpg" width="600" >}}
