---
title: "Specifications"
draft: false
menu:
  docs:
    title:
    parent: "Clusterboard/Further_information"
    identifier: "Clusterboard/Further_information/Specifications"
    weight: 3
---

These are the Clusterboard specifications:

* Standard mITX form-factor (167&nbsp;mm&nbsp;x 170&nbsp;mm)
* Built-in eight-port Gigabit Ethernet switch, using RTL8370N ASIC; the switch is unmanaged although the ASIC provides management functions, see [this forum thread](https://forum.pine64.org/showthread.php?tid=13181) for further information
* Seven internal Gigabit Ethernet ports, one for each SOPINE module, connected to the built-in switch using [RTL8211E](https://datasheet.lcsc.com/szlcsc/Realtek-Semicon-RTL8211EG-VB-CG_C69264.pdf) PHYs
* One connector for an eMMC module, for the first SOPINE module
* Seven USB 2.0 ports, one for each SOPINE module
* GPIO pins exposed for each SOPINE module, including the UARTs
* Gigabit Ethernet port activity LEDs, one for each SOPINE module
* Battery holder for two standard non-rechargeable AA-size 1.5&nbsp;V batteries, for the real time clock (RTC) backup on all SOPINE modules
* Barrel-style jack as a power input, 6.3&nbsp;mm outer diameter and 3.0&nbsp;mm inner diameter, for a 5&nbsp;V, 15&nbsp;A DC power supply
* Standard 24-pin ATX header as a power input, for an ATX power supply capable of providing at least 15&nbsp;A at its 5&nbsp;V output

Please note than only one power input may be used at once. The barrel-style jack is additionally protected by a built-in 15&nbsp;A polyfuse.

**📌 NOTE**\
No batteries for RTC backup should be installed unless certain hardware modifications are applied to the Clusterboard. Internal circuitry of the Clusterboard and SOPINE modules will eventually attempt to charge the batteries, which will result in damage to the batteries and the Clusterboard. Keep in mind that rechargeable batteries cannot be used because there is no charging circuitry for them on the Clusterboard. Please see [this forum thread](https://forum.pine64.org/showthread.php?tid=5849&page=2) and [this article](https://ericdraken.com/a64-reset-problem/) for further information.
