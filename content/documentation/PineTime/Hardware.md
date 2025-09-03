---
title: "Hardware"
draft: false
menu:
  docs:
    title:
    parent: "PineTime"
    identifier: "PineTime/Hardware"
    weight: 2
aliases:
  - /documentation/PineTime/Further_information/Hardware/
---

## Display

Note: The factory-default software on the PineTime does not auto-detect the display being disconnected when it has already booted. That can cause garbled output, to fix it just restart the PineTime.

The display is driven using the ST7789 display controller. Use the following pins to drive the screen:

| PineTime pin | ST7789 pin |
| --- | --- |
| LCD_SCK (P0.02) | SPI clock |
| LCD_SDI (P0.03) | SPI MOSI |
| LCD_RS (P0.18) | Command/Data pin (CD) |
| LCD_CS (P0.25) | Chip select |
| LCD_RESET (P0.26) | Display reset |
| LCD_BACKLIGHT_{LOW,MID,HIGH} | Backlight (active low) |

Notes:

* Chip select must be held low while driving the display. It must be high when using other SPI devices on the same bus (such as external flash storage) so that the display controller won’t respond to the wrong commands.
* SPI must be used in mode 3. Mode 0 (the default) won’t work.
* LCD_BACKLIGHT_* is used to enable the backlight. Set at least one to low to see anything on the screen.
* Use SPI at 8MHz (the fastest clock available on the nRF52832) because otherwise refreshing will be super slow.

**References**:

[Adafruit ST7789 driver in cpp](https://github.com/adafruit/Adafruit-ST7735-Library/)

## Battery measurement

Reading whether the PineTime has power attached is easy: simply read the charge indication pin (P0.12). When it is high it is running on battery, when it is low it is charging.

Reading the battery voltage is a bit harder. For that you can use the battery voltage pin on P0.31 (AIN7). The returned value is 12 bits, which means it is 0..4095. You can get the measured voltage with the following formula, assuming a reference voltage of 3.3V (this is configurable in the ADC):

    adcVoltage = adcValue / (4095 / 3.3)

The measured voltage is actually half of the actual battery voltage, because the ADC is connected between a voltage divider where both resistors are 1MΩ. This can be corrected by multiplying the value:

    batteryVoltage = adcValue * 2 / (4095 / 3.3)

It’s often better to avoid floating point values on embedded systems and in this case there is no reason to use float at all, we can just represent the value in millivolts. Therefore the formula can be simplified to:

    batteryVoltage = adcValue * 2000 / (4095 / 3.3)
    batteryVoltage = adcValue * 2000 / 1241

Converting this voltage to an estimated capacity in percent requires a more complicated algorithm, because Lithium-ion batteries have a non-linear discharge curve.

## Button

The button on the side of the PineTime is disabled by default. To enable it, drive the button out pin (P0.15) high.

While enabled, the button in pin (P0.13) will be high when the button is pressed, and low when it is not pressed.

{{< admonition type="note" >}}
 the button consumes around 34µA when P0.15 is left high. To reduce current consumption, set it to low most of the time and only set it to high shortly before reading it. The button needs a short time to give good outputs though, setting P0.15 high at least four times in a row seems to result in enough delay that P0.13 has a stable output.
{{</ admonition >}}

## Touch panel

The touch panel is controlled by a Hynitron CST816S chips. Unfortunately, there is not much information about this chip on the internet apart from the datasheet below and a [reference driver](https://github.com/lupyuen/hynitron_i2c_cst0xxse/). This is enough to implement a basic driver, but crucial information needed to implement advanced functionalities are missing (I²C protocol and registers, timings, power modes).

### Pins

* P0.10=== What do you need to know?

If you followed Dorian’s guide to get here and felt semi-comfortable, you’ll be fine. This is no more complicated than that. If you are intimidated, that’s okay! I’ll still encourage you to try. You will learn a lot, just be patient and don’t put any data on your PineNote that you wouldn’t be okay losing. If you run into trouble, ask for help in the [Discord](https://discord.com/invite/pine64) / [Matrix](https://matrix.to/#/#pinenote:matrix.org). Please try to solve problems on your own first, and then ask for help -- if nobody replies, please be patient and ask again soon.

Reset

* P0.28: Interrupt (signal to the CPU when a touch event is detected)
* P0.06: I²C SDA
* P0.07: I²C SCL

### I²C

* Device address: 0x15
* Frequency: from 10Khz to 400Khz

{{< admonition type="note" >}}
 The controller goes to sleep when no event is detected. In sleep mode, the controller does not communicate on the I²C bus (it appears disconnected). So, for the communication to work, you need to tap on the screen so that the chip wakes-up.
{{</ admonition >}}

{{< admonition type="note" >}}
 The I²C bus, also known as TWI bus has known issues, make sure to write your TWI driver with timeouts.
{{</ admonition >}}

### Touch events

Touch information is available from the 63 first registers of the controller. Remember: the device is in sleep mode when no touch event is detected. It means that you can read the register only when the touch controller detected an event. You can use the _Interrupt_ pin to detect such event in the software.

These 63 bytes contain up to 10 touch point (X, Y, event type, pressure,...) :

<table style="width: 100%">
  <tr>
      <th> Byte </th>
      <th> Bit7 </th>
      <th> Bit6 </th>
      <th> Bit5 </th>
      <th> Bit4 </th>
      <th> Bit3 </th>
      <th> Bit2 </th>
      <th> Bit1 </th>
      <th> Bit0 </th>
  </tr>
  <tr>
      <td> 0 </td>
      <td colspan="8"> ? </td>
  </tr>
  <tr>
      <td> 1 </td>
      <td colspan="8"> GestureID: (Gesture code ,<br> 0x00: no gesture,<br> 0x01: Slide down,<br>
0x02: Slide up,<br>
0x03: Slide left,<br>
0x04: Slide right,<br>
0x05: Single click,<br>
0x0B: Double click,<br>
0x0C: Long press)<br> </td>
  </tr>
  <tr>
      <td> 2 </td>
      <td colspan="4"> ? </td>
      <td colspan="4"> Number of touch points </td>
  </tr>
  <tr>
      <td> 3 </td>
      <td colspan="2"> Event (0 = Down, 1 = Up, 2 = Contact) </td>
      <td colspan="2"> ? </td>
      <td colspan="4"> X (MSB) coordinate </td>
  </tr>
  <tr>
      <td> 4 </td>
      <td colspan="8"> X (LSB) coordinate </td>
  </tr>
  <tr>
      <td> 5 </td>
      <td colspan="2"> ? </td>
      <td colspan="2"> Touch ID </td>
      <td colspan="4"> Y (MSB) coordinate </td>
  </tr>
  <tr>
      <td> 6 </td>
      <td colspan="8"> Y (LSB) coordinate </td>
  </tr>
  <tr>
      <td> 7 </td>
      <td colspan="8"> Pressure (?) </td>
  </tr>
  <tr>
      <td> 8 </td>
      <td colspan="8"> Miscellaneous (?) </td>
  </tr>
</table>

Bytes 3 to 8 are repeated 10 times (10*6 + 3 = 63 bytes).

**NOTES**

* The touch controller seems to report only 1 touch point
* Fields X, Y, Number of touch points and touch ID are updated. The others are always 0.

### Registers

The reference driver specifies some registers and value, but there is no information about them:

| Register | Address | Description |
| --- | --- | --- |
| HYN_REG_INT_CNT | 0x8F |  |
| HYN_REG_FLOW_WORK_CNT | 0x91 |  |
| HYN_REG_WORKMODE | 0x00 | 0 = WORK, 0x40 = FACTORY |
| HYN_REG_CHIP_ID | 0xA3 |  |
| HYN_REG_CHIP_ID2 | 0x9F |  |
| HYN_REG_POWER_MODE | 0xA5 | 0x03 = SLEEP (reset the touchpanel using the reset pin before using this register: pin_low, delay 5ms, pin_high, delay 50ms then write 3 to register 0xA5) |
| HYN_REG_FW_VER | 0xA6 |  |
| HYN_REG_VENDOR_ID | 0xA8 |  |
| HYN_REG_LCD_BUSY_NUM | 0xAB |  |
| HYN_REG_FACE_DEC_MODE_EN | 0xB0 |  |
| HYN_REG_GLOVE_MODE_EN | 0xC0 |  |
| HYN_REG_COVER_MODE_EN | 0xC1 |  |
| HYN_REG_CHARGER_MODE_EN | 0x8B |  |
| HYN_REG_GESTURE_EN | 0xD0 |  |
| HYN_REG_GESTURE_OUTPUT_ADDRESS | 0xD3 |  |
| HYN_REG_ESD_SATURATE 0xED | 0xED |  |

## Accelerometer

The on board accelerometer in devices shipped before July 2021 is a Bosch BMA421, connected to the I2C bus.
Devices shipped after July 2021 use a Bosch BMA425 accelerometer.

### Pins

* P0.06: I²C SDA
* P0.07: I²C SCL
* P0.08: Interrupt

I²C Device address: 0x18

## Reducing power consumption

The PineTime appears to be able to sleep with a current consumption of [only 66µA](https://github.com/InfiniTimeOrg/InfiniTime/issues/53#issuecomment-783654321).

To investigate current consumption, it’s a good idea to disable everything possible to get the lowest current consumption possible, and then re-enable things one by one. Here is one way to get a baseline current consumption of 0.60µA, as measured from the 3.3V pin with the battery disconnected:

* Enable the DC/DC regulator. This doesn’t affect the current consumption while sleeping, but almost halves the runtime current consumption.
* Use the low-frequency (32.768kHz) oscillator.
* Leave all pins in their default state, except for P0.05 (SPI CS) and P0.25 (LCD CS) which should be configured as an output and set to high.
* Put the heart rate sensor in sleep mode by setting the PDRIVER (0x0C) register to 0, see [the HRS3300 datasheet for details](https://files.pine64.org/doc/datasheet/pinetime/HRS3300%20Heart%20Rate%20Sensor.pdf#page=12).
* Put the SPI flash in [deep power-down mode](https://datasheet.lcsc.com/szlcsc/2005251035_XTX-XT25F32BSOIGU-S_C558851.pdf#page=38) by setting flash CS high, then low, then writing the byte 0xb9 on the SPI bus, and then setting flash CS high again.
* Sleep in a loop, using WFE or WFI (if you’re using the Nordic SoftDevice, call `sd_app_evt_wait` instead).

Here are some current consumption statistics (current consumed in addition to the baseline power), roughly ordered from large to small:

| Source | Current | Notes |
| --- | --- | --- |
| SWD | 3.05mA | Power cycle the chip after programming to avoid this, it can hide other inefficiencies. |
| LCD | 5.61mA | Set the LCD to sleep mode when not used, using SLPIN. |
| Backlight high  | 12.27mA | |
| Backlight mid | 5.51mA |  |
| Backlight low | 1.83mA | 
| ADC left enabled | 1.3mA | Stopping SAADC brings the current back to the baseline. It seems that it doesn’t need to be disabled entirely. | 
| Edge triggered pin interrupts | 0-0.47mA? | It appears that under some configurations, edge triggered interrupts result in a large power drain. One way to avoid this is by using the pin sense mechanism.
| BUTTON_OUT left high | 0.04mA | See [Button](#button) for how to avoid this. |
| SPI flash sleep mode | 0.014mA | Sleep mode still consumes power. Put it in [deep power down mode](https://datasheet.lcsc.com/szlcsc/2005251035_XTX-XT25F32BSOIGU-S_C558851.pdf#page=38) to avoid this. 
| SPI, I2C | (negligible) | SPI and I2C appear to consume very little power when idle, around 1µA or less. |
