---
title: "PinePhone v1.1 - Braveheart"
draft: false
hidden: true
menu:
  docs:
    title:
    parent: "PinePhone/Revisions"
    identifier: "PinePhone/Revisions/PinePhone_v1.1_-_Braveheart"
    weight: 
---

The PinePhone v1.1 "Braveheart" is a hardware revision of the [PinePhone](/documentation/PinePhone) that shipped in January 2020.

This page contains resources which are exclusive to the 1.1 revision of the PinePhone. For newer revisions or for resources related to other PinePhone revisions see [PinePhone](/documentation/PinePhone/Revisions/).

## Schematic

[Hardware schematic](http://files.pine64.org/doc/PinePhone/PinePhone_Schematic_v1.1_20191031.pdf)

## Changes from 1.0

Braveheart is slightly different from the 1.0 revision of the Pinephone. These differences should not require creating different images.

1. Added CPU shielding and cover plate
2. Swap PC3 to FLASH_EN and PD24 to FLASH_TRIGOUT, where previously they were reversed
3. Add pulldown resistor on PD24 (FLASH_TRIGOUT) so the flash LED does not light on boot
4. Connect WiFi enable to VD33
5. Set the EG25G’s PWRKEY on by default (see resistor R1526)
6. Add R630 resistor location, populate with 0K by default. Allows adjusting to different battery thermistors in case this is not possible in software.
7. Add voltage shift to Pogo pins I2C-CLK, I2C-DATA, and INT. The Pogo Pin specified voltage is 3.3v while the A64’s I2C is 2.8V.
8. A64 LINEOUTN is disconnected from the speaker amplifier, making the speaker output single-ended instead of differential

## DIY Hardware fixes

Some of the known issues can be fixed with more or less involved hardware modifications:

* VCONN mod: USB-C CC pins are pulled to GND, [removing small switches](/documentation/PinePhone/Hardware_fixes_and_mods/PinePhone_1.2_VCONN_Hardware_Fix) can make USB-OTG work. A proper fix is to replace those with another component.
* PMIC mod / [PinePhone 1.1 VBUS power usage hardware fix](/documentation/PinePhone/Hardware_fixes_and_mods/PinePhone_1.1_VBUS_power_usage_Hardware_Fix) to lower power consumption, especially when the phone is powered off.

## Known issues

This section lists problems known on the 1.1 revision hardware, possibly because they carried over from the 1.0 revision. Most of these were fixed in the 1.2 revision mainboard.

### Need a way to distinguish v1.1 from v1.2 from U-Boot SPL

_Resolved in v1.2 by PL6 being connected directly to the modem, instead of through the level shifter, so it is pulled low at boot._

To load the correct device tree, there needs to be some hardware feature that can distinguish the two versions. This can be as simple as an I/O pin that is pulled differently by default between v1.1 and v1.2. Reading the pin in SPL will tell us which device tree to use.

### WiFi module cannot be disabled or reset in software

_Resolved in v1.2 by connecting PL2 to the WiFi module’s WiFi reset pin._

Neither the ***WL-REG-ON*** nor ***WL-PMU-EN*** signal is connected to anything, and the WiFi module’s ***CHIP_EN*** pin is connected (through the privacy switch) to a regulator that cannot be turned off (easily, if at all). So while the privacy switch works, there’s no way to disable the WiFi module in software. This will lead to excess power consumption when WiFi is turned off.

### Magnetometer's IRQ signal is routed to the wrong pin

_Resolved in v1.2 by connecting the magnetometer’s ***DRDY*** pin to PB1._

It needs to go to DRDY, not to INT. The kernel driver expects the trigger events to be fired when DRDY changes, and does not even configure the interrupts to be enabled on the INT pin.

Software workaround is to disable magnetometer interrupt in the devicetree, and use a hrtimer  or some other software triggering mechanism for IIO devices.

### Speaker output could be differential

_Resolved in v1.2 by connecting ***LINEOUTP*** to the speaker amplifier’s ***INP*** input._

Using a differential connection to the speaker amplifier would significantly lower the noise floor of the speaker, and would allow doubling the max volume.

### Modem AP_READY signal is not connected

_Resolved in v1.2 by connecting PH7 to ***AP_READY*** instead of ***WAKEUP_IN***._

The [modem’s power management documentation](https://www.quectel.com/UploadImage/Downlad/Quectel_EC2x&EG9x_Power_Management_Application_Note_V1.0.pdf) describes how to implement modem power saving. The modem can wake up the host using either the Ring Indicator pin (section 4.5) or USB remote wakeup (section 4.3). Either way, it suggests the ***AP_READY*** signal needs to be connected. The modem needs that signal to know when the host is asleep (and the modem needs to queue its messages and wake it up), and when the host has finished waking up (and is ready to receive the queued messages).

### Modem RI signal routing prevents wakeup

_Resolved in v1.2 by connecting ***RI*** to PL6._

The EG25G’s Ring Indicator (RI) pin is currently routed to GPIO pin PB2. The A64 needs to receive interrupts via this pin while suspended, so the modem can wake up the A64 (for incoming calls and text messages). The only GPIO bank that can receive interrupts while the A64 is suspended is Port L (on ***R_PIO***).

**Note**: Port L is powered by VCC-PL, and runs at 1v8, so it should _not_ have a level shift to DCDC1/3v3 between the AP and the modem, like DTR currently has. The way DTR is currently connected is a bug.

### Excess power usage while driving VBUS

_Resolved in v1.2 by connecting PL9 and ***VBUS_CTRL*** on the ANX7688 to ***N_VBUSEN*** on the PMIC._ A crude hardware workaround is also possible, see _PinePhone 1.1 VBUS power usage Hardware Fix_.

The ***N_VBUSEN/DRIVEVBUS*** input on the  AXP803 PMIC, labeled ***USB-DRVVBUS*** on the schematic, is not connected to the USB OTG boost regulator enable input, because R1300 is marked "NC". This prevents the AXP803 from automatically detecting when the USB port is being powered from the battery. Thus, the PMIC continues to draw power from the USB port, and this doubles the drain on the battery (since the whole phone is being powered by the USB OTG boost regulator). This could be fixed by populating R1300.

The ANX7688’s VBUS_CTRL pin should also be connected to the DRVVBUS signal to perform role switching in hardware without needing OS interaction. In that case PD6 becomes an input. Otherwise, we would need to hook up the VBUS status change interrupt from the ANX7688 to control the USB PHY driver.

### ANX7688 power supply situation is problematic

_Resolved in v1.2 by powering always-on 3v3 from DCDC1, video-related 3v3 from DLDO1, 1v8 from GPIO-LDO1, and 1v0 controlled by PD11._

ANX7688 has four power inputs: 3v3, 1v8, 1v0, and HDMI_VT (which is also 3v3).

* The main 3v3 input, to AVDD33, should always be on according to the datasheet. For this reason, it should be connected to an always-on regulator, such as DCDC1, so DLDO1 can be turned off when the screen is off. It has extremely low power consumption.
* HDMI_VT is only needed during video transmission, and should remain connected to DLDO1.
* The only other 3v3 consumer is the VCONN_EN pull-ups. These could be pulled to GPIO1-LDO (1.8V) instead; the pins are open drain.
* The DVDD18 input should also always be on according to the datasheet. It has extremely low power consumption. I recommend connecting it and the PL11 pull-up to VCC-PL, so GPIO1-LDO can be turned off.
* The remaining 1v8 inputs only need to be enabled when a USB cable is connected (supply or OTG). They are connected to their own regulator (GPIO1-LDO), so that is fine. (Note that the next issue suggests removing the pull-ups for POWER_EN and RESET_N.)
* The 1v0 input is only needed when a USB cable is connected (supply or OTG). It is currently controlled by DLDO1, but I think controlling it with GPIO1-LDO would be an improvement. That way DLDO1 only needs to be enabled when transmitting video, not always when a cable is connected.

### Modem PWR_KEY signal resistor population

_Resolved in v1.2 by separating the modem ***PWRKEY*** (PB3) and ***STATUS*** (PH9) signals._

On the dev phone (1.0) this signal was connected to PB3. This allows for turning on/off the modem via GPIO from a kernel driver. If proper power down is to be implemented in the kernel for the modem, to allow safe shutdown of the modem before turning off the 4g-pwr-bat, kernel has to be able to signal to the modem to shut down and wait 30s. This is not possible on braveheart. Without this signal, kernel can’t do anything to shut down the modem, and would have to rely on userspace to properly manage the modem power up/down sequence. Relying on userspace risks users shutting down the modem without proper wait time of 30s, risking modem damage (flash data corruption).

It would be nice to also have access to the STATUS signal from the modem, so that the driver can detect whether the modem is on or off (userspace might have turned modem off already via AT commands). Given that PWR_KEY pulse will either turn the modem on or off, based on the current status, it’s necessary to know the current status before sending the pulse.

There’s a STATUS signal routed to PWR_KEY on BraveHeart, that keeps the PWRKEY deasserted when the modem is on and it’s not possible to pull it up from PB3, even if R1516 would be optionally mounted.

So after powerup you can’t change PWR_KEY signal anymore from PB3 even if R1516 is mounted, and it’s not possible to turn off the modem via PB3.

### Modem has access to sensors on I2C1

_Resolved in v1.2 by disconnecting the modem’s I2C port._

The modem is a master on the I2C1 bus. A malicious firmware on the modem would be able to read the phone’s gravity/light/proximity sensors and prevent the main Linux OS from reading them. The [modem’s audio design note](https://www.quectel.com/UploadImage/Downlad/Quectel_WCDMA&LTE_Audio_Design_Note_V1.1.pdf) describes the ***AT+QIIC*** command which can be used to read and write registers on I2C devices.

According to the modem documentation, its I2C interface is only used for direct connection to a standalone audio codec. On the PinePhone, since the modem’s audio is routed through the A64 SoC, the modem’s I2C interface has no legitimate use.

The modem’s I2C interface should be left floating. U1503 pins A1, A2, B1, and B2 can be disconnected, and R1527/R1528 can be removed.

### Allow access the modem debug UART

_Not resolved in v1.2 -- would have required moving several other GPIOs._

Instead of the modem’s I2C pins, which aren’t very useful (see above), it would be great to have access to the modem’s debug UART, for debugging/updating the modem. This could be on UART3 (PD0-PD1, no flow control), while the main modem UART is on UART4 (PD2-PD5, with flow control).

### Modem UART flow control is broken

_Not resolved in v1.2 -- assumption is that USB will be used for high-bandwidth modem I/O._

BB-TX and BB-RX are connected to UART3 (PD0/PD1). BB-RTS and BB-CTS are connected to UART4 (PD4/PD5). To use hardware flow control, TX/RX would need to be connected to UART4, swapping PD0/PD1 with the motor control and rear camera reset GPIOs at PD2/PD3. This would need a device tree change.

Hardware flow control can be disabled with the ***AT+IFC*** command, and USB can also be used for commands instead of the UART. So the impact of this problem is unclear.

### ANX7688 power/reset control pulled the wrong way

_Not resolved in v1.2 -- this has minimal impact._

Both ***ANX_POWER_EN*** and ***ANX_RESET_N*** have pull-ups when they should not. Both signals need to be pulled low by default. They only need to be brought high (turning the chip on) when a USB cable is attached; and they should only be brought high after the 1v8 and 1v0 regulators are turned on. ***ANX_POWER_EN*** needs an external pull-down. ***ANX_RESET_N*** has an internal pull-down.

### VCONN_EN signals are possibly inverted

_Further investigation determined that the hardware is correct as-is in v1.1, so no change was made._

I don’t have a datasheet for the AW3512 chips, but I assume the enable input is active-high. VCONN1_EN and VCONN2_EN are open-drain. When they are open, it appears that VCONN should be enabled. But right now, when they are open, VCONN is disabled, because the AW3512 EN pin will be pulled low by the FET.

### Cameras have the same default I2C address

_Resolved in software by reprogramming the one of the cameras' I2C addresses at boot._

This makes it hard to keep both of them powered at the same time and switch quickly between them (on the per-frame basis) without having to re-initialize the sensors on each switch, which takes some time.

### USB-C CC pins are pulled to the GND by AW3512 (VCONN switches) when VCONN is off

This issue prevents cable plug/orientation detection and USB-PD communication. ANX always sees cable as plugged even if none is plugged. There’s no SW workaround for automatic detection of cable plug or power role.

In SW this can only be worked around by manual selection of PinePhone’s data and power role by the user.

HW workaround is desoldering U1305 and U1309 switches (BGA like packages). This will void the VCONN control, but it will release the CC pins for their proper connection detection and negotiation roles. I confirmed that desoldering fixes the issue. (Howto: https://megous.com/dl/tmp/pp-usbc-fix.jpg)

HW fix is to replace AW3512 with a variant of the chip that preserves the EN signal polarity and that doesn’t have the "quick discharge function" that ties the output to the GND via a 75 Ohm resistor when the switch is OFF. mozzwald used NCP334FCT2G as a replacement.

This issue is also present on the PinePhone 1.2 (CE) version and was fixed with revision 1.2a. See the [workaround](/documentation/PinePhone/Hardware_fixes_and_mods/PinePhone_1.2_VCONN_Hardware_Fix) for affected revisions.

### Pogo Pins supply 5v0, not 3v3

_No hardware change suggested, to maintain accessory compatibility._

This is possibly just a documentation issue. The wiki claimed they provide a "3.3v power source", and on this page, "The Pogo Pin specified voltage is 3.3v". But according to the schematic, they are connected to ***USB-5V***, the output of the 5V boost regulator.
