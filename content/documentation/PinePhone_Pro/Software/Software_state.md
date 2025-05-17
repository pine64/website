---
title: "Software State"
draft: false
menu:
  docs:
    title:
    parent: "PinePhone_Pro/Software"
    identifier: "PinePhone_Pro/Software/Software_state"
    weight: 4
aliases:
  - /wiki/PinePhone_Pro_Software_State
---

Presently the PinePhone Pro Explorer Edition is aimed at **Linux developers with an extensive knowledge of embedded systems and/or experience with mobile Linux**. It will take time for all the PinePhone Pro’s functionality to reach software parity with the original PinePhone and for mobile operating systems, in more general, to reach a higher degree of maturity.

Bear in mind that the software for these smartphones is still in a very early stage, with most of the software being in alpha or beta state. That's especially also the case for scalability of applications, their availability and practicability, any hardware function implementations and the firmware. The software is provided as is. There is no warranty for the software, not even for merchantability or fitness for a particular purpose.

The following table lists the feature functionality status of the unaltered pre-installed factory image of the current shipping batch and as comparison an up-to-date reference image (no responsibility is accepted for the accuracy of this information, the list is provided and updated by the community). If you have any questions regarding the current state of the software or of specific features working, please don't hesitate to ask in the [community chat](/documentation#Community_and_Support) **before buying the device**:

* Discord: _#pinephone_ under [https://discord.gg/pine64](https://discord.gg/pine64)
* IRC: _#pinephone_ on _irc.pine64.org_. Note: please consider Matrix, Discord or Telegram due to the volatile nature of IRC
* Matrix: [https://app.element.io/#/room/#pinephone:matrix.org](https://app.element.io/#/room/#pinephone:matrix.org)
* Telegram: [https://t.me/pinephone](https://t.me/pinephone)

{{< admonition type="note" >}}
The software is *written by the community*, any contributions towards the community projects are greatly appreciated! Please see "[How to Contribute](/documentation/Introduction/How_to_contribute)" to learn about how to contribute to the software projects and "[Where to Report Bugs](/documentation/Introduction/Where_to_report_bugs)" to learn about where to report bugs.
{{< /admonition >}}


Bootloader:

| Component | Status | Notes |
| -------- | ------- | ------- |
| `Bootloader` | Working |  |
| `SPI` | Working |  |
| `Boot GUI` | Working | Devices bought after July 2022 come with Tow-Boot or rk2aw flashed to the SPI memory |


Operating System:

| Component | Status | Notes |
| -------- | ------- | ------- |
| `Stability` | WIP |  |
| `Suspend` | Experimental | Audio is often higher pitched after waking up from suspend due to a bug, make sure to update your system<sup>[Report](https://github.com/dreemurrs-embedded/Pine64-Arch/issues/381);</sup> <sup>[Report](https://gitlab.manjaro.org/manjaro-arm/packages/core/linux-pinephonepro/-/issues/3)</sup> |
| `Updates` | WIP | The pre-flashed and outdated operating system on the eMMC often gets corrupted after updating<sup>[Example](https://forum.pine64.org/showthread.php?tid=15950)</sup>; Pacman database lock preventing updates<sup>[Solution](https://wiki.archlinux.org/title/pacman#%22Failed_to_init_transaction_(unable_to_lock_database)%22_error)</sup>; Keyring bug (solution is to run "pinephonepro-post-install" script as root). |

Modem:

| Component | Status | Notes |
| -------- | ------- | ------- |
| `General` | WIP | [Alternative firmware](https://github.com/Biktorgj/pinephone_modem_sdk); Slow wakeup<sup>[Report](https://gitlab.com/mobian1/devices/eg25-manager/-/issues/34)</sup>; Some carriers blocking specific TANs in their network; *Note:* Proprietary firmware |
| `Phone` | WIP | The modem connection crashes frequently, which can lead to missed calls<sup>[Report](https://gitlab.com/mobian1/devices/eg25-manager/-/issues/34#note_984212350);</sup> <sup>[Alternative firmware](https://github.com/Biktorgj/pinephone_modem_sdk)</sup>; Slow wakeup<sup>[Report](https://gitlab.com/mobian1/devices/eg25-manager/-/issues/34)</sup>; bad call audio quality<sup>[Report](https://gitlab.manjaro.org/manjaro-arm/issues/pinephone/phosh/-/issues/249)</sup>; Audio is often higher pitched after waking up from suspend due to a bug<sup>[Report](https://github.com/dreemurrs-embedded/Pine64-Arch/issues/381);</sup> <sup>[Report](https://gitlab.manjaro.org/manjaro-arm/packages/core/linux-pinephonepro/-/issues/3)</sup> |
| `SMS` | Working | SMS functionality is expected to work. In certain cases the functionality might be blocked by a clogged modem<sup>[Report](https://gitlab.manjaro.org/manjaro-arm/issues/pinephone/phosh/-/issues/203)</sup>; Some bugs |
| `MMS` | WIP | MMS functionality is integrated into the application "Spacebar", some bugs remaining and expected |
| `Push notifications` | Not implemented | Receiving push notifications while the phone is suspended is not implemented |

Components:

| Component | Status | Notes |
| -------- | ------- | ------- |
| `LCD` | WIP | *Hardware issue*<sup>[Details](https://xnux.eu/log/#055)</sup> |
| `Touch` | Working |  |
| `Rear camera` | WIP | Camera work-in-progress with DTS fix<sup>[Citation]</sup>; userspace still needs to do some catching up; Green image tint<sup>[Citation]</sup> |
| `Front camera` | WIP | Camera work-in-progress with DTS fix<sup>[Citation]</sup>; userspace still needs to do some catching up; Green image tint<sup>[Citation]</sup> |
| `Camera flash` | Critical issues | *Hardware issue*<sup>[Details](https://xnux.eu/log/#069)</sup>; Note: `/sys/class/leds/white:flash` |
| `WiFi` | Working | WiFi is expected to work. The firmware does not support monitor mode and package injection. *Note:* Proprietary firmware |
| `Bluetooth` | WIP | Bluetooth not necessarily working for calls yet due to missing audio routing<sup>[Citation]</sup>; Bluetooth in general dodgy under Pulseaudio.<sup>[Info](https://wiki.archlinux.org/title/bluetooth_headset#Headset_via_Pipewire)</sup> *Note:* Proprietary firmware |
| `GNSS/GPS` | WIP | aGPS to be implemented; long loading times to get a GPS fix<sup>[Citation]</sup>; No preinstalled application<sup>[Citation]</sup> |
| `Sensors` | WIP | "Geo Magnetic Sensor" (`af8133j`): Status unknown (at `/sys/bus/i2c/devices/4-001c/iio:device1`) <br> "Accelerometer / Gyroscope" (`mpu6500`): Working (at `/sys/bus/i2c/devices/4-0068/iio:device2`) <br> "Ambient light / Proximity" (`stk3311`): Working after updating |
| `Vibration motor` | Working |  |
| `Notification LED` | Working |  |
| `Buttons` | Working | Power buttons and volume buttons are working. |

Accessory compatibility, spare parts:

| Component | Status | Notes |
| -------- | ------- | ------- |
| `Keyboard Add-on` | WIP | The keyboard add-on compatibility is work-in-progress. |
| `LoRa Add-on` | Not implemented | No software support implemented |
| `Qi Wireless Charging Add-on` | WIP | Wireless charging with the add-on case is expected to work to some degree. Certain software functionality and a driver is currently missing<sup>[Citation]</sup> |
| `Fingerprint Reader Add-on` | Not implemented | No software support implemented |
| `Spare parts` | Partial | Some spare parts now available in the store.<sup>[Store](https://pine64.com/product-category/pinephonepro-spare-parts/)</sup> |

Software notes:

| Component | Status | Notes |
| -------- | ------- | ------- |
| `Waydroid` | Working | Waydroid is an Android container used to run Android applications. |

¹ Status of the features at the time of the last factory installation without updates

² Status of the features with an up-to-date reference image
