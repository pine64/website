---
title: "Pinenut-01S Module information and schematics"
draft: false
menu:
  docs:
    title:
    parent: "PineCone/Further_information"
    identifier: "PineCone/Further_information/Pinenut-01S_Module_information_and_schematics"
    weight: 
---

![width=200](/documentation/images/Pinenut-01S_PCB-Front.png)
![width=200](/documentation/images/Pinenut-01S_PCB-Back.png)

Schematics and GPIO definitions:

* [Pinenut-01S schematic ver 1.01](https://files.pine64.org/doc/Pinenut/Pinenut-01S%20V1.01%20SCH.pdf)
* [PineNut-01S KiCad schematic ver 1.01](https://wiki.pine64.org/images/6/6b/PineNut-01S_v1.01_KiCad.zip)
* [Pinenut-01S GPIO Definition ver 1.0](https://files.pine64.org/doc/Pinenut/NUT-01S%20GPIO%20Definition%20ver%201.0.pdf)
* [USB Programmer adapter for Pinenut-01S schematic ver 1.0](https://files.pine64.org/doc/Pinenut/USB%20Adapter%20for%20Pinenut-01S%20Schematic%20V1.0.pdf)

The default firmware runs the UART at 2000000 bps. It will accept input whilst regularly outputting:

    proc_hellow_entry: RISC-V rv32imafc
    cur key status:1
