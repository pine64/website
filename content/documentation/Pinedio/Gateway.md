---
title: "Gateway"
draft: false
menu:
  docs:
    title:
    parent: "Pinedio"
    identifier: "Pinedio/Gateway"
    weight: 1
---

The gateway will be available in two variants - indoor and outdoor. All that is known about the outdoor unit is that it will have "an aluminum, rugged and water resistant case".
The indoor unit consists of a PINE A64-LTS, fitted with a purpose built hat (adapter) which uses a LoRa module by RakWireless. The chipset used is the SX1303, and the module via the SPI interface. There are two external connections on the enclosure for the GPS and loRa antenna.

## Connections

* GPS is connected to UART2 on the A64 board
* SX1303 on SPI0

| RAK5146 module | PI-2 connector | PINE A64-LTS |
| --- | --- | --- |
| SX1303 SPI | Pin 19 = MOSI / PC0<br> Pin 21 = MISO/PC1<br> Pin23 = CLK/PC2<br> Pin24 = CS/PC3 | SPI0 (/dev/spidev0.0) |
| SX1303 RESET | Pin 11 = GPIO17/PC7 | GPIO71 (/sys/class/gpio/gpio71) |
| GPS UART | Pin 8 = TX/<br> Pin 10 = RX | UART2 (/dev/ttyS2) |
| GPS RESET | Pin 33 = GPIO13/PC5 | GPIO69 (/sys/class/gpio/gpio69) |
| GPS Standby | Pin 35 = GPIO19/PC9 | GPIO73 (/sys/class/gpio/gpio73) |

## Pictures

{{< figure src="/documentation/images/Blog-april-InsideLoRaGateway.jpg" >}}
{{< figure src="/documentation/images/Blog-april-InsideLoRaGateway2.jpeg" >}}
{{< figure src="/documentation/images/Discord-lora-gateway-20210413_143615.jpg" >}}
{{< figure src="/documentation/images/Discord-lora-gateway-20210413_1435271.jpg" >}}

## Operating systems

The Pinedio Gateway carries the A64-LTS board. The [SOPINE releases](/documentation/SOPINE/Software) are also compatible based on the RAM specifications.
