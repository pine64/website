---
title: "Compatibility"
draft: false
menu:
  docs:
    title:
    parent: "PineTime/Development"
    identifier: "PineTime/Development/Compatibility"
    weight: 
---

## Compatibility with other projects

Different firmware running using different bootloaders and Bluetooth stacks on the nRF52832 have different requirements on how they should be initialised and what should be placed where in the internal flash.

To keep track of what, how and why things work like they do across the different projects, check out the [PineTime SoftDevice and MCUBoot compatibility](/documentation/PineTime/Flashing/SD_MCUBoot) article.

## Compatibility with companions apps and Bluetooth communication

There are a lot of different firmware running on the Pinetime that implement different BLE APIs (for example for time synchronization and notifications). Companion apps must be able to differentiate between different firmware and forks of the same firmware. See [Bluetooth](/documentation/PineTime/Software/Bluetooth).
