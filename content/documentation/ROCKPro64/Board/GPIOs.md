---
title: "GPIOs"
draft: false
menu:
  docs:
    title:
    parent: "ROCKPro64/Board"
    identifier: "ROCKPro64/Board/GPIOs"
    weight: 
---

## GPIO Pins

| Assigned To | Pin Nr. | Pin Nr. | Assigned To |
| --: | :-: | :-: | :-- |
| 3.3 V | 1 | 2 | 5 V |
| GPIO1_C4 (I2C8_SDA) ^a^ | 3 | 4 | 5 V |
| GPIO1_C5 (I2C8_SCL) ^a^ | 5 | 6 | GND |
| GPIO4_D0 (CPU_GPCLK) | 7 | 8 | GPIO4_C4 (UART2_TX) |
| GND | 9 | 10 | GPIO4_C3 (UART2_RX) |
| GPIO1_C6 | 11 | 12 | GPIO3_D0 (I2S0_CLK) |
| GPIO1_C2 | 13 | 14 | GND |
| GPIO1_A1 | 15 | 16 | GPIO1_A4 |
| 3.3 V | 17 | 18 | GPIO4_C5 [SPDIF] |
| [UART4_TX] GPIO1_B0 (SPI1_TXD) | 19 | 20 | GND |
| [UART4_RX] GPIO1_A7 (SPI1_RXD) | 21 | 22 | GPIO4_D1 |
| GPIO1_B1 (SPI1_CLK) | 23 | 24 | GPIO1_B2 (SPI1_CSN0) |
| GND | 25 | 26 | GPIO1_B5 |
| GPIO1_B3 (I2C4_SDA) | 27 | 28 | GPIO1_B4 (I2C4_SCL) |
| GPIO4_D3 | 29 | 30 | GND |
| GPIO4_D4 | 31 | 32 | GPIO3_D4 (I2S0_SDI1SDO3) |
| GPIO3_D5 (I2S0_SDI2SDO2) | 33 | 34 | GND |
| GPIO3_D2 (I2S0_LRCKTX) | 35 | 36 | GPIO3_D6 (I2S0_SDI3SDO1) |
| GPIO3_D1 (I2S0_LRCKRX) | 37 | 38 | GPIO3_D3 (I2S0_SDI0) |
| GND | 39 | 40 | GPIO3_D7 (I2S0_SDO0) |

Notes: 

* pulled high to 3.3V through 2.2kOhm resistor

## Linux /dev/gpiochip Assignments

| Pin Nr. | Chip | Line |
| --- | --- | --- |
| 3 | 1 | 20  |
| 5 | 1 | 21  |
| 7 | 4 | 24  |
| 8 | 4 | 20  |
| 10 | 4 | 19  |
| 11 | 1 | 22  |
| 12 | 3 | 24  |
| 13 | 1 | 18  |
| 15 | 1 | 1  |
| 16 | 1 | 4  |
| 18 | 4 | 21  |
| 19 | 1 | 8  |
| 21 | 1 | 7  |
| 22 | 4 | 25  |
| 23 | 1 | 9  |
| 24 | 1 | 10  |
| 26 | 1 | 13  |
| 27 | 1 | 11  |
| 28 | 1 | 12  |
| 29 | 4 | 27  |
| 31 | 4 | 28  |
| 32 | 3 | 28  |
| 33 | 3 | 29  |
| 35 | 3 | 26  |
| 36 | 3 | 30  |
| 37 | 3 | 25  |
| 38 | 3 | 27  |
| 40 | 3 | 31 |

On Linux, using the new `/dev/gpiochip` API, the `_n_` in `GPIO_n___XX_` appears to correlate to the number of the `/dev/gpiochip_n_`, and the `_XX_` to the definition `RK_P_XX_` of lines in `include/dt-bindings/pinctrl/rockchip.h` of the Linux kernel source. Having these named in the dts would be nice.

You can use [libgpiod](https://git.kernel.org/pub/scm/libs/libgpiod/libgpiod.git/) to drive them, and test them with the included tools (`gpioinfo`, `gpioset`, ...)

For example, `gpioset 4 25=1` (run as root) would turn pin 22 on. Do beware that poking the wrong GPIO pin can lock up your system.

The conversion table at right is also available as a [C header file](https://gist.github.com/CounterPillow/fe066655bf2d929148fe6eb3f15b1dd5).
