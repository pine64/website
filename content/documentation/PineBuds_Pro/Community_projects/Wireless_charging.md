---
title: "Wireless charging"
draft: false
menu:
  docs:
    title:
    parent: "PineBuds_Pro/Community_projects"
    identifier: "PineBuds_Pro/Community_projects/Wireless_charging"
    weight: 
---

This page is about the community project to bring wireless charging to the [PineBuds Pro](/documentation/PineBuds_Pro).

## Wireless charging

The PineBuds Pro don’t have wireless charging by default, but you can add it. However, you need to know how to disassemble the charging case and solder bunch of SMT components to the PCB.

Pine originally planned to have wireless charging for the PineBuds Pro, but apparently for cost reasons they decided to cancel it. However, they left footprints on the PCB for wireless charging component. They also designed COPO CP2021 component to be used. You also need a bunch of other components, such as resistors and of course [electromagnetic coil](https://en.wikipedia.org/wiki/Electromagnetic_coil). The places intended for the components, the footprints, are made for [SMT (also called SMD)](https://en.wikipedia.org/wiki/Surface-mount_technology) components. That means you need [a hot air soldering station](https://en.wikipedia.org/wiki/Soldering_station#Hot_air_soldering_stations) and experience.

## Required tools

* Picks/thin cards
* Screwdriver
* Hot air soldering station
* Tweezers
* Solder
* Flux
* Glue

## Required components

* COPO CP2021
* WIP

## Steps

1. First open the lid and then try to press the case from the front edge with a plectrum or a thin card. There are two clips on each side. Soon the case will snap open.
2. Carefully unscrew and remove the PCB from the case.
3. Solder the necessary components to their respective footprints, use the PineBuds Pro Charging Case Schematic/COPO CP2021 2.5W Qi Wire Power Receiver Datasheet (below).
4. Screw the PCB back into the place.
5. There is plenty of space, glue the coil to the bottom of the case.
6. Close the charging case.
