---
title: "PinePhone v1.2"
draft: false
hidden: true
menu:
  docs:
    title:
    parent: "PinePhone/Revisions"
    identifier: "PinePhone/Revisions/PinePhone_v1.2"
    weight: 
---

The PinePhone v1.2 is a hardware revision of the [PinePhone](/documentation/PinePhone) that was shipped in 2020 as UBports Community Edition.

This page contains information and resources which are specific to the UBports Community Edition (v1.2 PCB) revision of the PinePhone. For other revisions or for resources related to all PinePhone revisions, see [PinePhone](/documentation/PinePhone/Revisions/).

## Schematics

* [Hardware schematic v1.2](http://files.pine64.org/doc/PinePhone/PinePhone%20v1.2%20Released%20Schematic.pdf) (2020-03-10, for the UBports Community Edition)

## Changes from v1.1

The v1.2 mainboard revision changes the routing of several GPIOs to fix bugs and to improve power management. Therefore, it needs an updated device tree. The state of PL6 at boot can be used to distinguish between v1.1 (it can be pulled high) and v1.2 (it will remain low).

1. The WiFi module’s ***CHIP_EN*** input (connected to the privacy switch) is now pulled down, so the WiFi will turn off reliably when the switch is off.
2. PL2 is now connected to the WiFi module’s reset pin, allowing the WiFi to be turned off or reset in software.
3. The magnetometer’s ***DRDY*** pin is now connected to PB1, allowing interrupt-driven periodic sensor readings.
4. ***LINEOUTP*** is again connected to the speaker amplifier’s INP input (like in v1.0), increasing the SNR of the rear speaker.
5. PH7 is now connected to the modem’s ***AP_READY*** input (instead of ***WAKEUP_IN***), allowing the modem to buffer URCs (interrupts) while the phone is asleep.
6. The modem’s ***RI*** output and ***DTR*** input had their GPIOs swapped between PL6 and PB2, so the ***RI*** signal can be detected without powering the main pin controller.
7. Both PL9 and ***VBUS_CTRL*** (from the ANX7688) are now connected to ***N_VBUSEN*** on the PMIC. This causes the PMIC to automatically stop drawing power from the USB port when supplying power to a USB-OTG peripheral. It also allows the ANX7688 to automatically control the direction of current flowing through the USB port.
8. As part of the previous change, the ANX7688’s reset input was moved to PD6; this pin previously controlled the USB OTG power.
9. Some of the regulators supplying the ANX7688 were rearranged, to reduce power consumption when the USB port is not connected and not being used to transmit video.
10. As part of the previous change, PD11 now controls the ANX7688’s 1v0 digital power domain.
11. The modem’s ***STATUS*** output is now connected to PH9, allowing the modem on/off state to be visible in software (note: this only works while the modem is powered). Since it is no longer connected to PB3, reading ***STATUS*** no longer turns the modem on.
12. The modem no longer has access to the I2C bus containing the sensors.
13. ***HBIAS*** is now connected to the headphone jack.

## Known issues

### Backlight

Backlight LED current regulation depends on gpio0-ldo voltage stability due to feedback voltage from current sensing resistor being modified via SoC’s PWM pin and pullup resistor to gpio0-ldo. gpio0-ldo also powers the CTP controller and light/proximity sensor, among other things. When backlight brightness is very low and the CTP controller actively communicates on the I2C bus the backlight blinks heavily. It’s not a very good idea to tie boost converter’s current regulating feedback circuit to the potential source of noise, especially since the noise will have much larger effect when the backlight LED current is low. It’s possible this can be mitigated if C1110 can be raised to 22-47uF range, or by changing the resistor values in the feedback circuit.

PWM duty cycle for the lowest brightness of the backlight is also not very predictable, varying from 7-20% (tested with a small sample size of 2 devices). Therefore it’s not possible to come up with a single device tree brightness settings that will work for everyone, requiring per-device calibration.

On PinePhone 1.0, this was not the case, PWM signal was directly fed to the CE pin of the regulator, and lowest brightness setting seems more stable. On the other hand, the lowest achievable brightness was brighter than on 1.1+.

Additionally there is also another backlight issue, where the brightness is lower when connecting a VBUS powered device, https://xnux.eu/log/#022. See [PinePhone 1.2b R1318 backlight hardware fix](/documentation/PinePhone/Hardware_fixes_and_mods/PinePhone_1.2b_R1318_backlight_Hardware_Fix).

### USB

The USB-C CC pins are pulled to the GND by AW3512 (VCONN switches) when VCONN is off. This issue prevents cable plug/orientation detection and USB-PD communication. ANX always sees cable as plugged even if none is plugged. There’s no SW workaround for automatic detection of cable plug or power role.

The issue was was fixed with revision 1.2a. See [PinePhone 1.2 VCONN hardware fix](/documentation/PinePhone/Hardware_fixes_and_mods/PinePhone_1.2_VCONN_Hardware_Fix) for details and an instruction about how to do the hardware fix.

In SW this can only be worked around by manual selection of PinePhone’s data and power role by the user.

Hardware workaround is to desolder U1305 and U1309 switches (BGA like packages). This will void the VCONN control, but it will release the CC pins for their proper connection detection and negotiation roles (see https://xnux.eu/devices/pp-usbc-fix.jpg).

Hardware fix is to replace AW3512 with a variant of the chip that preserves the EN signal polarity and that doesn’t have the "quick discharge function" that ties the output to the GND via a 75 Ohm resistor when the switch is OFF. User _mozzwald_ used NCP334FCT2G as a replacement.
