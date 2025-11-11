---
title: "Development projects"
draft: false
menu:
  docs:
    title:
    parent: "Pinecil"
    identifier: "Pinecil/Development_projects"
    weight:
---

| Author | Project Homepage | Description | Supported |
| --- | --- | --- | --- |
| Ben Brown ([ralimtek](https://github.com/Ralim?tab=repositories)) | [Ralim’s IronOS](https://ralim.github.io/IronOS/) | Official Pinecil firmware | BL706, GD32VF103TB, Stm32f103 |
| Marek Kraus [gamiee/gamelaster](https://github.com/gamelaster) | [Blisp V2 Flasher](https://github.com/pine64/blisp) | CLI Updater for Pinecil V2, BL70x MCU | Windows, Linux, Mac |
| Marek Kraus [gamiee/gamelaster](https://github.com/gamelaster) | [Pinecil V1 Flasher](https://github.com/pine64/pine64_updater) | Pinecil V1 GUI Updater | Windows, Mac |
| Arkaitz Goni Hedger [spagett1](https://github.com/Spagett1?tab=repositories) | [PineFlash](https://github.com/Laar3/PineFlash) | Pinecil V1 GUI Updater | Linux, Mac |
| [Builder555](https://github.com/builder555) | [BLE PineSAM](https://github.com/builder555/PineSAM) | Bluetooth LE Settings & temperature control from any browser | Cross-platform, runs local script to control Pinecil from PC or phone. |
| [Joric](https://github.com/joric?tab=repositories) (iamjoric) | [BLE browser API](https://joric.github.io/pinecil/) | [Bluetooth LE Graph](https://github.com/joric/pinecil/wiki) | Windows, Linux, Android browsers that support BLE GATT |
| Tom W ([TomW1605](https://github.com/TomW1605)) & [ithinkido](https://github.com/ithinkido?tab=repositories) | [BLE V2 + ESP32](https://github.com/TomW1605/esphome_pinecilv2_ble) | Bluetooth LE V2 data => ESP32 BLE+Wifi => Home Assist display | Cross Platform |
| Bouffalo Lab | [B-Lab Dev Cube ](https://dev.bouffalolab.com/download) | MCU vendor GUI for Dev | BL70x, BL60x, others (does not work for Pinecil V2) |
| Alvin Wong | [Rust code on GD32VF103](https://github.com/alvinhochun/gd32vf103-pinecil-demo-rs) | Rust code demos for Pinecil V1 | GD32VF103TB |
| [tr4nt0r](https://github.com/tr4nt0r) | [pynecil](https://github.com/tr4nt0r/pynecil) | Python library to communicate with Pinecil V2 via Bluetooth | Cross-platform, Python >= 3.11 |
| [tr4nt0r](https://github.com/tr4nt0r) | [Home Assistant](https://www.home-assistant.io/integrations/iron_os/) | Monitor and control Pinecil V2 from Home Assistant | IronOS integration introduced in HA 2024.8 |


{{% admonition type="note" %}}
Bluetooth (BLE) apps require upgrading Pinecil V2 to IronOS **2.21** or newer [firmware here](https://github.com/Ralim/IronOS/releases/).
{{% /admonition %}}
