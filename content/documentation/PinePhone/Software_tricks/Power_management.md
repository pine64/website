---
title: "Power Management"
draft: false
hidden: true
menu:
  docs:
    title:
    parent: "PinePhone/Software_tricks"
    identifier: "PinePhone/Software_tricks/Power_management"
    weight: 
---

The data on this page is based on the the [PinePhone v1.1 - Braveheart](/documentation/PinePhone/Revisions/PinePhone_v1.1_-_Braveheart).

## Regulators

### Current Assignments

| Name/GPIO | Output Voltage | Can disable at runtime? | Can disable in suspend? | Consumers (internal/external separated by semicolon) |
| --- | --- | --- | --- | --- |
| DCDC1 | 3.3V | No | No (VCC-IO) | VCC-EFUSE, VCC-IO, VCC-PC (VQMMC2), VCC-PD, VCC-USB; Modem [I2C, PCM, UART], Motor, Pogo I2C, UART0, VMMC0, VMMC2, WiFi CHIP_EN |
| DCDC2 | DVFS | No | Yes | VDD-CPUX |
| DCDC3 | DVFS | N/A | N/A | VDD-CPUX (polyphase with DCDC2) |
| DCDC4 | N/A | Yes | Yes | Not used |
| DCDC5 | 1.2V | No | Yes (future) | VCC-DRAM; DRAM |
| DCDC6 | 1.1V | No | Yes (future) | VDD-SYS |
| DC1SW | N/A | Yes | Yes | Not used |
| ALDO1 | 2.8V | Yes | Yes | VCC-PE; Camera AFVCC, Camera DOVDD, CSI I2C, Pogo I2C |
| ALDO2 | 1.8V | No | No (VCC-PL) | VCC-PL; Pogo INT |
| ALDO3 | 3.0V | No | No (KEYADC) | AVCC, KEYADC, VCC-PLL |
| DLDO1 | 3.3V | No | No (ANX7688 AVDD33) | HVCC, VCC-DSI; ANX7688 [AVDD33, HDMI_VT, I2C, ANX-V1.0 Enable, VCONN_EN Disable Pull-up], HDMI [DDC, HPD], Proximity LED, Sensor I2C, Sensor VDD |
| DLDO2 | 1.8V? 3.3V? | Yes | Yes | MIPI-DSI VIO |
| DLDO3 | 2.8V | Yes | Yes | Camera AVDD |
| DLDO4 | 1.8V-3.3V | Yes | Yes | VCC-PG; VQMMC1 |
| ELDO1 | 1.8V | No | No (DRAM) | CPVDD; DRAM |
| ELDO2 | N/A | Yes | Yes | Not used |
| ELDO3 | 1.8V | Yes | Yes | Camera DVDD |
| FLDO1 | 1.2V | Yes | Yes | HSIC-VCC (not used) |
| FLDO2 | 1.1V | No | No (VDD-CPUS) | VDD-CPUS |
| GPIO0-LDO | 3.3V | Yes | Yes | Backlight PWM, LCD, Proximity sensor VDD, Touchscreen [I2C, VCC] |
| GPIO1-LDO | 1.8V | No | No (ANX7688 DVDD1V8) | ANX7688 [AVDD1V8, DVDD1V8, CC, HDMI DDC, I2C, Power/Reset pull-up] |
| PD6 | 5.0V | Yes | Yes | USB OTG |
| PD8 | 5.0V | Yes | Yes | Pogo supply, USB OTG via PD6 |
| PD9 | 5.0V | Yes | Yes | VCONN (USB Type C) |
| PH10 | PWM | Yes | Yes | Backlight |
| PL7 | VBAT | Yes | Yes | Modem |
| ANX-V1.0 | 1.0V | Yes | Yes | ANX7688 [AVDD1V0, DVDD1V0] |

### Suggested Regulator Hardware Changes

#### ANX7688

1. Move ANX7688 AVDD33 (the chip input only, not the other things connected to 3v3) and ANX7688 I2C Level Shift (3.3V side) from DLD01 to DCDC1, and ANX7688 VCONN_EN Disable Pull-up (R1355 and R1366) from DLDO1 to ANX1.8V
2. ~~Move ANX7688 ANX1.8V from GPIO1-LDO to ALDO2~~
3. Move ANX7688 ANX-V1.0 Regulator Enable (R1352) from DLDO1 to a GPIO

These are all medium priority.

The result of these changes would be that:

1. The always-on part of the ANX7688 chip (AVDD33, DVDD1V8) will always be powered
2. GPIO1-LDO only needs to be powered when a USB cable is detected, and is enough to power the rest of the chip (except HDMI)
3. DLDO1 only needs to be enabled if the display pipeline or sensors are active, even if a USB cable is plugged in

### Assignments after Suggested Changes

Note: Only regulators that were modified are included here.

| Name/GPIO | Output Voltage | Can disable at runtime? | Can disable in suspend? | Consumers (internal/external separated by semicolon) |
| --- | --- | --- | --- | --- |
| DCDC1 | 3.3V | No | No (VCC-IO) | VCC-EFUSE, VCC-IO, VCC-PC (VQMMC2), VCC-PD, VCC-USB; ANX7688 [AVDD33, I2C], Modem [I2C, PCM, UART], Motor, Pogo I2C, UART0, VMMC0, VMMC2, WiFi CHIP_EN |
| ALDO2 | 1.8V | No | No (VCC-PL) | VCC-PL; ANX7688 [DVDD1V8], Pogo INT |
| DLDO1 | 3.3V | Yes | Yes | HVCC, VCC-DSI; ANX7688 [HDMI_VT], HDMI [DDC, HPD], Proximity sensor VDD, Sensor I2C, Sensor VDD |
| GPIO0-LDO | 3.3V | Yes | Yes | Backlight PWM, LCD, Proximity LED, Touchscreen [I2C, VCC] |
| GPIO1-LDO | 1.8V | Yes | Yes | ANX7688 [ANX-V1.0 Enable, AVDD1V8, CC, HDMI DDC, I2C, Power/Reset pull-up, VCONN_EN Disable Pull-up] |

### Open Questions

* How is ANX1.8V actually powered? from GPIO1-LDO (R1309) or PS (U1301) or both?
* Is DLDO2 supposed to be 1.8V or 3.3V? The schematic says both in different places.
  * From LCD and LCD controller datasheets, this should be 1.8V.
* If DLDO2 is 3.3V, can we spread the HDMI/DSI/Sensors better across DLDO1 and DLDO2 so they can be more independent?
  * Looks like this is N/A, because DLDO2 should be 1.8V.

## GPIO

### Current Modem Pin Assignments

Note: only pins relevant to power management are included in this table.

| Pin | Signal Name | Description | Direction (as modem) | Needed in suspend? | Connected to |
| --- | --- | --- | --- | --- | --- |
| 1 | ***WAKEUP_IN*** | Drive low to wake up the modem | I | No | PH7 (active high) |
| 2 | ***AP_READY*** | Drive high/low to signal the A64 is ready to receive URCs | I | No (if held) | NC |
| 4 | ***W_DISABLE#*** | Drive low to enter Airplane Mode | I | No (if held/tristate) | PH8 (active high) |
| 20 | ***RESET_N*** | Drive low to reset the modem | I | No (if held/tristate) | PC4 (active high) |
| 21 | ***PWRKEY*** | Drive low to turn the modem on/off | I | No (if held/tristate) | PB3 (active high) |
| 61 | ***STATUS*** | Open drain output, pulled low when the modem is on | O | No | PB3 |
| 62 | ***RI*** | Pulled low to request host wakeup | O | Yes | PB2 |
| 66 | ***DTR*** | Drive low to wake up the modem | I | No | PL6 (active low) |

### Current Port L Pin Assignments

| Pin | Signal Name | Description | Direction | Needed in suspend? |
| --- | --- | --- | --- | --- |
| PL0 | ***PMU-SCK*** | AXP803 I2C/RSB Clock | O | Yes |
| PL1 | ***PMU-SDA*** | AXP803 I2C/RSB Data | I/O | Yes |
| PL2 | ***WL-REG-ON*** | Not Connected | N/A | N/A |
| PL3 | ***WL-WAKE-AP*** | Wake-on-WLAN Interrupt | I | Yes |
| PL4 | ***BT-RST-N*** | Bluetooth Reset Control | O | No (if held) |
| PL5 | ***BT-WAKE-AP*** | Wake-on-BT Interrupt | I | Yes |
| PL6 | ***DTR*** | Modem DTR (Wakeup Request) | O | No |
| PL7 | ***4G-PWR-BAT*** | Modem Power Supply Control | O | No (if held) |
| PL8 | ***ANX7688-CABLE_DET*** | ANX7688 Cable Detection Interrupt | I | Yes |
| PL9 | ***ANX_RESET*** | ANX7688 Reset Control | O | No (if held) |
| PL10 | ***LCD-PWM*** | LCD Backlight PWM Brightness Control | O | No |
| PL11 | ***ANX7688-INT*** | ANX7688 Alert Interrupt | I | Yes |
| PL12 | ***POGO-INT*** | Pogo Pin Interrupt | I | Yes |

### Pins Held During Suspend

### Pins Active During Suspend

### Suggested GPIO Hardware Changes

1. Connect ***WL-REG-ON*** (PL2) to ***WL-PMU-EN*** (WiFi). _bugfix_
2. Connect the LIS3MDL ***DRDY*** pin, not ***INT*** pin, to PB1. _bugfix_
3. Reconnect ***LINEOUTN*** to make the line output differential.
4. Connect PH7 to ***AP_READY*** instead of ***WAKEUP_IN***. Since the A64 needs to drive this pin high (no pull-up on the modem side), this uses the level shifter channel previously used by RI (U1503 channel 4).
5. Swap ***DTR*** (was at PL6, now at PB2 with U1503 channel 3 level shift) and ***RI*** (was at PB2, now at PL6 with **no level shift**, but a pull-up to ALDO2 on the A64 side*). _partly a bugfix_
6. Connect the modem ***PWRKEY*** to PB3 only, not ***STATUS*** or DCDC1 (depopulate R1526). _bugfix_
7. Connect the modem ***STATUS*** to PH9. This is an open-drain signal, so it needs a pull-up on the A64 side. _bugfix_
8. Disconnect the modem I2C. The level shifter can be repurposed for the next change (modem debug UART).
9. ~~Connect the modem debug UART TX/RX to PD0-1.~~
10. ~~Move the modem main UART TX/RX to PD2-3. Motor and CSI reset that are currently at PD2-3 would need to be moved elsewhere.~~
11. Connect both AXP803 ***USB-DRVVBUS*** (populate R1300) and ANX7688 ***VBUS_CTRL*** to ***DRVVBUS*** (in addition to PD6).
   1. ~~Connecting to ANX7688 ***VBUS_CTRL*** would need a level shift to 1.8V.~~
   2. Alternatively, swap PL9 and PD6, so the level shift is not necessary, since PL9 is already a 1.8V logic level.
   3. ~~Alternatively, do not connect ANX7688 ***VBUS_CTRL****, and at least populate R1300 to connect AXP803 **USB-DRVVBUS***.~~
12. Reorient the transistors for ***ANX_POWER*** (PD10) and ***ANX_RESET*** (PL9) so they do not invert their input, and (more importantly) produce a low-level output by default. (Since PL9 is already at 1.8V, it may no longer need a transistor.)
13. ~~Remove the transistors inverting ***VCONN1_EN*** and ***VCONN2_EN****, and use a pull-up to **DVDD1V8*** (that is really already present) instead of the pull-up to ***3V3***.~~

**Note:**
Changes 1-7 and 11 are high priority.
Changes 12-13 are medium priority.
Changes 8-10 are low priority.

&#42; There should be at least one pin where the default value at boot changes, due to being pulled differently, for use in distinguishing the hardware revisions. In v1.1, PL6 reads 0 at boot. Since RI is an active-low interrupt, it needs a pull up. And it doesn’t need any level translation. So that’s our perfect opportunity. If PL6 reads low at boot, it’s a v1.1 device; if PL6 reads high at boot, it’s a v1.2 device.

### Open Questions

* What exactly is the modem PWRKEY currently connected to? PB3? STATUS? DCDC1?
* Currently STATUS pin is connected to PWRKEY and to PB3. STATUS can’t be read reliably since voltage divider from R1526 and R1517 places the STATUS signal at 0V or 0.5*Vcc-IO, which is unspecified input value according to A64 datasheet (Vih is 0.7*Vcc-IO, Vil is 0.3*Vcc-IO, the range in between is unspecified).
