---
title: "GPIO"
draft: false
menu:
  docs:
    title:
    parent: "PineCube"
    identifier: "PineCube/GPIO"
    weight: 4
---

GPIO header pin table:

| Pin | Name | Physical Pin (Designation) | Linux GPIO | Alternate Func 1 | Alternate Func 2 | Interrupt |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | 3V3 | DCDC3 |  |  |  |  |
| 2 | 5V | PS |  |  |  |  |
| 3 | TWI1_SDA | PB9 | 41 | TWI1_SDA | UART0_RX | PB_EINT9 |
| 4 | 5V | PS |  |  |  |  |
| 5 | TWI1_SCK | PB8 | 40 | TWI1_SCK | UART0_TX | PB_EINT8 |
| 6 | GND | GND |  |  |  |  |
| 7 | PWM1 | PB5 | 37 | PWM1 |  | PB_EINT5 |
| 8 | UART_TXD | PB0 | 32 | UART2_TXD |  | PB_EINT0 |
| 9 | GND | GND |  |  |  |  |
| 10 | UART_RXD | PB1 | 33 | UART2_RX |  | PB_EINT1 |
| 11 | GPIO17 | PC5 | 69 |  | SDC2_D2 |  |
| 12 | GPIO18 | PC6 | 70 |  | SDC2_D3 |  |
| 13 | GPIO27 | PC7 | 71 |  | SDC2_D4 |  |
| 14 | GND | GND |  |  |  |  |
| 15 | GPIO22 | PC8 | 72 |  | SDC2_D5 |  |
| 16 | GPIO23 | PC9 | 73 |  | SDC2_D6 |  |
| 17 | 3V3 | DCDC3 |  |  |  |  |
| 18 | GPIO24 | PC10 | 74 |  | SDC2_D7 |  |
| 19 | SPI-MOSI | PC3 | 67 | SPI0_MOSI | SDC2_D0 |  |
| 20 | GND | GND |  |  |  |  |
| 21 | SPI-MISO | PC0 | 64 | SPI0_MISO | SDC2_CLK |  |
| 22 | PWM0 | PB4 | 36 | PWM0 |  | PB_EINT4 |
| 23 | SPI-CLK | PC1 | 65 | SPI0_CLK | SDC2_CMD |  |
| 24 | SPI_CE0 | PC2 | 66 | SPI0_CS | SDC2_RST |  |
| 25 | GND | GND |  |  |  |  |
| 26 | SPI_CE1 | PC4 | 68 |  | SDC2_D1 |  |

Important notes:

* First ball is marked with white dot
* SPI is multiplexed also with SPI flash
* SPI_CE1 is normal GPIO pin"
