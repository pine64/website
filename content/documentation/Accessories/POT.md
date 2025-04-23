---
title: "POT"
draft: false
menu:
  docs:
    title:
    parent: "Unsorted"
    identifier: "Unsorted/POT"
    weight:
---

Peripheral On Top (POT)

## POT Board Recommended PCB Dimension

* [POT board dimension for Pine A64 in DXF format](https://files.pine64.org/doc/Pine%20A64%20Schematic/PineA64%20POT%20Board.rar)
* [POT board dimension for Pine A64 in PDF format](https://files.pine64.org/doc/Pine%20A64%20Schematic/PineA64%20POT%20Board.pdf)

## USB/UART Programming/Console Adapter (PMPROG01)

{{< figure src="/documentation/images/USB_Prog.JPG" >}}

### Feature

```
Base on Silicon Libs CP2102
Support Virtual COM Port Device Drivers
Support USBXpress™ Direct Driver Support
With XH 5 pin 2.54mm pitch connector for UART connection
Voltage Output on the connection is selectable to either 5V,3.3V or off
On board USB-B Connector Receptor
Connector J3 can direct insert into Pine A64 Exp-Bus to provide console access to Pine A64 board
I/O pin are protected with ESD protector IC.
On board 5x2pin connector can direct insert into Pine A64 Exp Bus for UART0 Console access
Can use for programming and debugging for Wifi Remote I/O board
```

### Related Specification and Document

[CP2102 Datasheet](https://www.silabs.com/Support%20Documents/TechnicalDocs/CP2102-9.pdf)

[Virtual COM Port Driver](https://www.silabs.com/products/mcu/Pages/USBtoUARTBridgeVCPDrivers.aspx)

[USBXpress Driver](https://www.silabs.com/products/mcu/Pages/USBXpress.aspx)

{{< figure src="/documentation/images/PMPROG01_Rev2_USB_Serial_Programmer-4.jpg" >}}

{{< figure src="/documentation/images/PMPROG01_Rev2_USB_Serial_Programmer-1.jpg" >}}

{{< figure src="/documentation/images/PMPROG01_Rev2_USB_Serial_Programmer-3.jpg" >}}

{{< figure src="/documentation/images/PMWF01A_Wifi_Remote_IO_Rev3-1.jpg" >}}

## POT: Veroboard (PMVRB01)

{{< figure src="/documentation/images/PMVRB01_board_layout.JPG" >}}

### Feature

```
Sit on top of Pine A64 board
All the header receptor will have extended length pin to allow other POT board to insert on top of it
Allow easy access to all the I/O pin on the Pine A64 header
On board 4pcs of LED with current limiting resistor all direct connect to I/O pin for status indicator
On board 4pcs of Tact switch
On board XH5 2.54mm pitch connector for UART0 allow easy connection to USB/UART adapter for console access
```

{{< figure src="/documentation/images/PMVRB01_POT_Veroboard_Rev1-5.jpg" >}}

{{< figure src="/documentation/images/PMVRB01_POT_Veroboard_Rev1-3B.png" >}}

{{< figure src="/documentation/images/PMVRB01_POT_Veroboard_Rev1-2B.png" >}} POT Veroboard on Pine A64

{{< figure src="/documentation/images/PMVRB01_POT_Veroboard_Rev1-1B.png" >}} POT Veroboard 2 board stack on top of Pine A64

## POT: Multi I2C Bus (PMI2C01)

{{< figure src="/documentation/images/PMI2C01_Board_Layout.JPG" >}}

### Feature

```
Sit on top of Pine A64 board
All the header receptor will have extended length pin to allow other POT board to insert on top of it
Allow easy access to all the I/O pin on the Pine A64 header
2 channel of I2C bus is wire out for easy access
I2C bus repeater IC (PCA9517A) are included in each I2C bus to allow connection of more devices on each bus
Support 3.3V and 5V I2C bus for each channel separately
On Board separated 3.3V supply regulator for 3.3V I2C Bus
Each I2C bus pin are protected with ESD protector devices
Each channel consist of 4 pcs of XH 4 pin 2.54mm pitch connector and 2 pcs of XH 5 pin 2.54mm pitch connector
For the XH 4 pin connector, will consist of GND,SCL,SDA,5V pin
For the XH 5 pin connector, will consist of GND,nINT,SCL,SDA,5V pin
5V supplier is direct connect from Pine A64 adapter’s supply thus prevent over loading Pine A64 board
The nINT pin will allow peripheral with interrupt pin link back to the Pine A64 I/O pin
```

### Related Specification and Document

[NXP PCA9517A Datasheet](https://www.nxp.com/documents/data_sheet/PCA9517A.pdf)

[NXP AN10658 Sending I2C-bus signal via long communication cables](https://www.nxp.com/documents/application_note/AN10658.pdf)

[NXP AN11075 Driving I2C-bus signals over twisted pair cables with PCA9605](https://www.nxp.com/documents/application_note/AN11075.pdf)

[Program to Enable I2c Port internal pull with full source code](https://wiki.pine64.org/images/d/d8/EnableI2cPullup.tar.gz)

[Multi I2c Bus Schematic](https://pine.myggns.com/bozon/index.php?f=157836a20d7b7e)

{{< figure src="/documentation/images/PMI2C01_I2C_Board_Rev1-1.jpg" >}}

{{< figure src="/documentation/images/PMI2C01_I2C_Board_Rev1-2.jpg" >}}

{{< figure src="/documentation/images/PMI2C01_I2C_Board_Rev1-3.jpg" >}}

{{< figure src="/documentation/images/PMVRB01_POT_Veroboard_Rev1-4.jpg" >}}

## POT: Shield Adapter (PMARD01)

{{< figure src="/documentation/images/PMARD01_Shield_Adpater_POT.JPG" >}}

{{< figure src="/documentation/images/PMARD01_Arduino_Pin_Mapping.JPG" >}}

```
Adapter for Arduino Shield
Separate on board LM1117 3.3V LDO for the Shield
Base on Maxim MAX11609 on ADC input. Allow up to 5V analog signal
Extra 5V input DC jack socket (suitable for 4.0mm X 1.7mm DC Jack) for extra input power
```

### Related Specification and Document

https:/ / [MAX11609 10bit I2C ADC](https://www.maximintegrated.com/en/products/analog/data-converters/analog-to-digital-converters/MAX11609.html)

## I2C Device: Humidity and Temperature Sensor (PMSDP01)

{{< figure src="/documentation/images/PMSDO01_Dew_Point_Sensor.JPG" >}}

### Feature

```
Base on Silicon Labs Si7021 I2C Humidity and Temperature Sensor
High Accuracy Temperature Sensor ±0.4 °C (max), –10 to 85 °C
0 to 100% RH operating range
Up to –40 to +125 °C operating range
On board 3.3V regulator
2pcs of XH 4pin 2.54 mm pitch connector to allow daisy chain of multiple I2C sensor
```

### Related Specification and Document

[Si7021-A20 Datasheet](https://www.silabs.com/Support%20Documents/TechnicalDocs/Si7021-A20.pdf)

{{< figure src="/documentation/images/PMSDO01_Dew_Point_Sensor_Rev1-1.jpg" >}}

## I2C Device: Ambient Light Sensor (PMSAL01)

{{< figure src="/documentation/images/PMSAL01_Light_Sensor.JPG" >}}

### Feature

```
Base on TAOS/AMS TSL2561T I2C Light Sensor
Approximates Human Eye Response
Programmable Interrupt Function allow user defined upper/lower limit trigger threshold
Automatically rejects 50/60Hz lighting ripple
Build with 2 channel of photodiode/ADC to allow more accurate calculation of light intensity (in Lux)
Can support up to 3pcs of sensor in the same I2C channel
On board 3.3V regulator
2pcs of XH 5pin 2.54 mm pitch connector to allow daisy chain of multiple I2C sensor
```

### Related Specification and Document

[TSL2561T Datasheet](https://ams.com/eng/content/download/250094/975485/file/TSL2560_Datasheet_EN_v1.pdf)

{{< figure src="/documentation/images/PMSAL01_Light_Sensor_Rev1-1.jpg" >}}

{{< figure src="/documentation/images/PMSAL01_Light_Sensor_Rev1-2.jpg" >}}

## WiFi Remote I2C (PMWF01A)

{{< figure src="/documentation/images/PMWF01A.JPG" >}}

### Feature

```
Base on ESP8266 Wifi Chipset
Connect to Wifi AP
On board chip antenna or U-FL connector for external antenna
On board relay contact (TE PCJ-105D3M with 3A 275Vac Contact) with screw type terminal contact to support AC Line On/Off
On board 1pc Tact-switch
XH 5 2.54mm pitch connector connecting I2C device
XH 6 2.54mm pitch connector for GPIO/SPI/PWM output
XH 2 2.54mm pitch connector for system power 5V input or output
DC Jack socket (suitable for 4.0mm X 1.7mm DC Jack) for system power input
UART Port connector ready for on chip programming using USB/UART Programming/Console Adapter (PMPROG01)
2pcs of XH 5pin 2.54 mm pitch connector to allow daisy chain of multiple I2C sensor
```
Further Detail info on the module can be found at [WiFi Remote I2c Quick Start Guide](/documentation/Accessories/Wifi_remote_i2c) wiki page

### Related Specification and Document

[TE PCJ-105D3M Relay Datasheet](https://www.te.com/commerce/DocumentDelivery/DDEController?Action=srchrtrv&DocNm=PCJ_series_relay_data_sheet_E&DocType=DS&DocLang=EN)

[ESP8266 Datasheet](https://drive.google.com/file/d/0B0cEs0lxTtL3SDdCcWd0LVI2bk0/view?usp=sharing)

[ESP8266 forum](https://bbs.espressif.com/)

{{< figure src="/documentation/images/PMWF01A_Wifi_Remote_IO_Rev3-2.jpg" >}}

{{< figure src="/documentation/images/PMWF01A_Wifi_Remote_IO_Rev3-3.jpg" >}}

{{< figure src="/documentation/images/PMWF01A_Wifi_Remote_IO_Rev3-4.jpg" >}}

{{< figure src="/documentation/images/PMWF01A_Wifi_Remote_IO_Rev3-5.jpg" >}}

## Inter Connection Wire

{{< figure src="/documentation/images/I2c_Cable_Connection.JPG" >}}

{{< figure src="/documentation/images/W5T4-01-15_UART_Programming_Console_Cable.JPG" >}}

{{< figure src="/documentation/images/W5T4-02-15_5Way_to_4Way_I2C_Cable.JPG" >}}

{{< figure src="/documentation/images/W4T4-03-15_4Way_I2C_Cable.JPG" >}}

{{< figure src="/documentation/images/W5T5-04-15_5Way_I2C_Cable.JPG" >}}
