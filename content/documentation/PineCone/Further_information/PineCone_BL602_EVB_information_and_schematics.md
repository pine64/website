---
title: "PineCone BL602 EVB information and schematics"
draft: false
menu:
  docs:
    title:
    parent: "PineCone/Further_information"
    identifier: "PineCone/Further_information/PineCone_BL602_EVB_information_and_schematics"
    weight: 
---

![width=120](/documentation/images/PADI-II_EVB.png)

The approximate dimensions are 26mm x 43mm.

Schematics: [PineCone BL602 EVB schematic ver 1.1](https://files.pine64.org/doc/Pinenut/Pine64%20BL602%20EVB%20Schematic%20ver%201.1.pdf)

Note: In the PineCone revision 1.1 ("BL62B_EVB V1.1" silkscreened on back of board), CC1 and CC2 share one 5.1KΩ resistor. This means the board will fail to power when you use an e-marked USB-C cable like the one that comes with Apple chargers. See [this article](https://medium.com/@leung.benson/how-to-design-a-proper-usb-c-power-sink-hint-not-the-way-raspberry-pi-4-did-it-f470d7a5910) for details of why this happens. The next schematic design will give each line its own 5.1KΩ resistor as per the USB-C specification.

The board uses a CH340 Serial/USB adapter. This chip is commonly used in Arduino-class development boards. It is a full speed (12Mbps) USB interface and has vendor ID 0x1a86 with product ID 0x7523.

The GPIO pins (11, 12, 14, 17) plus the nearby RESET, POWER, and GND pins are all located on one side of the board, on J1 to provide JTAG connection.
