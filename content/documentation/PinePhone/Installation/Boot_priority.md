---
title: "Boot priority"
draft: false
weight: 
menu:
  docs:
    title:
    parent: "PinePhone/Installation"
    identifier: "PinePhone/Installation/Boot_priority"
    weight: 1
---

The PinePhone always boots from the microSD card first. It is therefore recommended to have a microSD card handy. It is **not** possible to lock themself out of the phone when the installation on the internal storage (the eMMC) fails, as a correctly flashed microSD card will always boot. Note: Booting from USB is not supported by the hardware, a live USB stick will not boot.

The phone will also try to boot from microSD cards, which were previously flashed with an OS and formatted later, causing the phone to fail to boot. See [reuse microSD card](/documentation/PinePhone/Installation/Reuse_microSD_card) on how to format the microSD card properly, including wiping the residues of u-boot.
