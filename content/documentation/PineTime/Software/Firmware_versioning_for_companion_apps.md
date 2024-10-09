---
title: "Firmware versioning for companion apps"
draft: false
menu:
  docs:
    title:
    parent: "PineTime/Software"
    identifier: "PineTime/Software/Firmware_versioning_for_companion_apps"
    weight: 
---

BLE defines a standard service (Device Information Service, DIS) that allows BLE devices to expose information about them: hardware version, software version.

Companion apps will use these information to detect which firmware (or fork of a firmware) is running on the Pinetime they are connected to.

## How to use the Device Information Service to differentiate firmwares?

We’ve briefly talked about this on the community chat and this proposal is the result of this discussion. This is a request for comments.

Fields from the Device Information Service:
|     |     |     |
| --- | --- | --- |
| Field | Description | Example value |
| Manufacturer name | Manufacturer | PINE64 |
| Model number | Name of the device | "PineTime", "P8" |
| Serial number | Not needed by companion apps as they can use the BLE MAC address | ? |
| Hardware revision | Version of the hardware | 1.0a |
| Software revision | Project name or fork name | "InfiniTime", "InfiniTime-forkname", "Hypnos" |
| Firmware revision | Version of the firmware | "0.7.1" |
