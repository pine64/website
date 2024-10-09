---
title: "Pins and GPIOs"
draft: false
menu:
  docs:
    title:
    parent: "SOPINE"
    identifier: "SOPINE/Pins_and_GPIOs"
    weight: 2
---

## GPIO Alternate Functions Table

This is table of all available GPIOs on SOPine with their alternate functions. 

For more information about GPIOs, check the [Allwinner A64 Datasheet](http://files.pine64.org/doc/datasheet/pine64/A64_Datasheet_V1.1.pdf) section _4.2 GPIO Multiplexing Functions_ and section _4.3 Detailed Pin/Signal Description_

| Pin name | Linux | SOPine Pin | Direction | Default Function | Default Pull | Function 2 | Function 3 | Function 4 | Function 5 | Function 6 | SOPine Name |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| PB0 | GPIO32 | 35 | I/O | DIS | Z | UART2_TX |  | JTAG_MS0 |  | PB_EINT0 | PB0-UART2_TX |
| PB1 | GPIO33 | 75 | I/O | DIS | Z | UART2_RX |  | JTAG_CK0 | SIM_PWREN | PB_EINT1 | PB1-UART2_RX |
| PB2 | GPIO34 | 36 | I/O | DIS | Z | UART2_RTS |  | JTAG_DO0 | SIM_VPPEN | PB_EINT2 | PB2 |
| PB3 | GPIO35 | 30 | I/O | DIS | Z | UART2_CTS | I2S0_MCLK | JTAG_DI0 | SIM_VPPPP | PB_EINT3 | PB3-I3S_MCLK |
| PB4 | GPIO36 | 28 | I/O | DIS | Z | AIF2_SYNC | PCM0_SYNC |  | SIM_CLK | PB_EINT4 | PB4-I2S_SYNC |
| PB5 | GPIO37 | 27 | I/O | DIS | Z | AIF2_BCLK | PCM0_BCLK |  | SIM_DATA | PB_EINT5 | PB5-I2S_BCLK |
| PB6 | GPIO38 | 39 | I/O | DIS | Z | AIF2_DOUT | PCM0_DOUT |  | SIM_RST | PB_EINT6 | PB6-I2S_DOUT |
| PB7 | GPIO39 | 29 | I/O | DIS | Z | AIF2_DIN | PCM0_DIN |  | SIM_DET | PB_EINT7 | PB7-I2S_DIN |
| PB8 | GPIO40 | 34 | I/O | DIS | Z |  |  | UART0_TX |  | PB_EINT8 | PB8 |
| PB9 | GPIO41 | 33 | I/O | DIS | Z |  |  | UART0_RX |  | PB_EINT9 | PB9 |
| PC0 | GPIO64 | 134 | I/O | DIS | Z | NAND_WE |  | SPI0_MOSI |  |  | PC0-SPIO_MOSI |
| PC1 | GPIO65 | 150 | I/O | DIS | Z | NAND_ALE | SDC2_DS | SPI0_MISO |  |  | PC1-SPIO_MISO |
| PC2 | GPIO66 | 142 | I/O | DIS | Z | NAND_CLE |  | SPI0_CLK |  |  | PC2-SPIO_CLK |
| PC3 | GPIO67 | 148 | I/O | DIS | Pull-Up | NAND_CE1 |  | SPI0_CS |  |  | PC3-SPIO_CS |
| PC4 | GPIO68 | 135 | I/O | DIS | Pull-Up | NAND_CE0 |  |  |  |  | PC4 |
| PC5 | GPIO69 | 25 | I/O | DIS | Z | NAND_RE | SDC2_CLK |  |  |  | PC5 |
| PC6 | GPIO70 | 154 | I/O | DIS | Pull-Up | NAND_RB0 | SDC2_CMD |  |  |  | PC6 |
| PC7 | GPIO71 | 132 | I/O | DIS | Pull-Up | NAND_RB1 |  |  |  |  | PC7 |
| PC8 | GPIO72 | 130 | I/O | DIS | Z | NAND_DQ0 | SDC2_D0 |  |  |  | PC8 |
| PC9 | GPIO73 | 153 | I/O | DIS | Z | NAND_DQ1 | SDC2_D1 |  |  |  | PC9 |
| PC10 | GPIO74 | 156 | I/O | DIS | Z | NAND_DQ2 | SDC2_D2 |  |  |  | PC10 |
| PC11 | GPIO75 | 165 | I/O | DIS | Z | NAND_DQ3 | SDC2_D3 |  |  |  | PC11 |
| PC12 | GPIO76 | 146 | I/O | DIS | Z | NAND_DQ4 | SDC2_D4 |  |  |  | PC12 |
| PC13 | GPIO77 | 157 | I/O | DIS | Z | NAND_DQ5 | SDC2_D5 |  |  |  | PC13 |
| PC14 | GPIO78 | 155 | I/O | DIS | Z | NAND_DQ6 | SDC2_D6 |  |  |  | PC14 |
| PC15 | GPIO79 | 133 | I/O | DIS | Z | NAND_DQ7 | SDC2_D7 |  |  |  | PC15 |
| PC16 | GPIO80 | 144 | I/O | DIS | Z | NAND_DQS | SDC2_RST |  |  |  | PC16 |
| PD0 | GPIO96 | 60 | I/O | DIS | Z | LCD_D2 | UART3_TX | SPI1_CS | CCIR_CLK |  | PD0-SPI1_CS |
| PD1 | GPIO97 | 49 | I/O | DIS | Z | LCD_D3 | UART3_RX | SPI1_CLK | CCIR_DE |  | PD1-SPI1_CLK |
| PD2 | GPIO98 | 57 | I/O | DIS | Z | LCD_D4 | UART4_TX | SPI1_MOSI | CCIR_HSYNC |  | PD2-SPI1_MOSI |
| PD3 | GPIO99 | 61 | I/O | DIS | Z | LCD_D5 | UART4_RX | SPI1_MISO | CCIR_VSYNC |  | PD3-SPI1_MISO |
| PD4 | GPIO100 | 52 | I/O | DIS | Z | LCD_D6 | UART4_RTS |  | CCIR_D0 |  | PD4-UART4_RTS |
| PD5 | GPIO101 | 44 | I/O | DIS | Z | LCD_D7 | UART4_CTS |  | CCIR_D1 |  | PD5-UART4_CTS |
| PD6 | GPIO102 | 45 | I/O | DIS | Z | LCD_D10 |  |  | CCIR_D2 |  | PD6 |
| PD7 | GPIO103 | 40 | I/O | DIS | Z | LCD_D11 |  |  | CCIR_D3 |  | PD7 |
| PD8 | GPIO104 | 73 | I/O | DIS | Z | LCD_D12 |  | RGMII_RXD3/RMII_NULL | CCIR_D4 |  | GRXD3 |
| PD9 | GPIO105 | 83 | I/O | DIS | Z | LCD_D13 |  | RGMII_RXD2/RMII_NULL | CCIR_D5 |  | GRXD2 |
| PD10 | GPIO106 | 51 | I/O | DIS | Z | LCD_D14 |  | RGMII_RXD1/RMII_RXD1 |  |  | RMII-RXD1 |
| PD11 | GPIO107 | 48 | I/O | DIS | Z | LCD_D15 |  | RGMII_RXD0/RMII_RXD0 |  |  | RMII-RXD0 |
| PD12 | GPIO108 | 91 | I/O | DIS | Z | LCD_D18 | LVDS_VP0 | RGMII_RXCK/RMII_NULL |  |  | GRXCK |
| PD13 | GPIO109 | 89 | I/O | DIS | Z | LCD_D19 | LVDS_VN0 | RGMII_RXCT/RMII_CRS_DV |  |  | RMII-CRS-DV |
| PD14 | GPIO110 | 87 | I/O | DIS | Z | LCD_D20 | LVDS_VP1 | RGMII_NULL/RMII_RXER |  |  | RMII-RXER |
| PD15 | GPIO111 | 80 | I/O | DIS | Z | LCD_D21 | LVDS_VN1 | RGMII_TXD3/RMII_NULL | CCIR_D6 |  | GTXD3 |
| PD16 | GPIO112 | 82 | I/O | DIS | Z | LCD_D22 | LVDS_VP2 | RGMII_TXD2/RMII_NULL | CCIR_D7 |  | GTXD2 |
| PD17 | GPIO113 | 78 | I/O | DIS | Z | LCD_D23 | LVDS_VN2 | RGMII_TXD1/RMII_TXD1 |  |  | RMII-TXD1 |
| PD18 | GPIO114 | 85 | I/O | DIS | Z | LCD_CLK | LVDS_VPC | RGMII_TXD0/RMII_TXD0 |  |  | RMII-TXD0 |
| PD19 | GPIO115 | 79 | I/O | DIS | Z | LCD_DE | LVDS_VNC | RGMII_TXCK/RMII_TXCK |  |  | RMII-TXCK |
| PD20 | GPIO116 | 47 | I/O | DIS | Z | LCD_HSYNC | LVDS_VP3 | RGMII_TXCTL/RMII_TXEN |  |  | RMII-TXEN |
| PD21 | GPIO117 | 74 | I/O | DIS | Z | LCD_VSYNC | LVDS_VN3 | RGMII_CLKINRMII_NULL |  |  | GCLKIN |
| PD22 | GPIO118 | 53 | I/O | DIS | Z | PWM0 |  | MDC |  |  | RMII-MDC |
| PD23 | GPIO119 | 76 | I/O | DIS | Z |  |  | MDIO |  |  | RMII-MDIO |
| PD24 | GPIO120 | 50 | I/O | DIS | Z |  |  |  |  |  | LCD-RST |
| PE0 | GPIO128 | 58 | I/O | DIS | Z | CSI_PCLK |  | TS_CLK |  |  | CSI-PCLK |
| PE1 | GPIO129 | 102 | I/O | DIS | Z | CSI_MCLK |  | TS_ERR |  |  | CSI-MCLK |
| PE2 | GPIO130 | 100 | I/O | DIS | Z | CSI_HSYNC |  | TS_SYNC |  |  | CSI-HSYNC |
| PE3 | GPIO131 | 101 | I/O | DIS | Z | CSI_VSYNC |  | TS_DVLD |  |  | CSI-VSYNC |
| PE4 | GPIO132 | 95 | I/O | DIS | Z | CSI_D0 |  | TS_D0 |  |  | CSI-D0 |
| PE5 | GPIO133 | 54 | I/O | DIS | Z | CSI_D1 |  | TS_D1 |  |  | CSI-D1 |
| PE6 | GPIO134 | 96 | I/O | DIS | Z | CSI_D2 |  | TS_D2 |  |  | CSI-D2 |
| PE7 | GPIO135 | 65 | I/O | DIS | Z | CSI_D3 |  | TS_D3 |  |  | CSI-D3 |
| PE8 | GPIO136 | 105 | I/O | DIS | Z | CSI_D4 |  | TS_D4 |  |  | CSI-D4 |
| PE9 | GPIO137 | 59 | I/O | DIS | Z | CSI_D5 |  | TS_D5 |  |  | CSI-D5 |
| PE10 | GPIO138 | 107 | I/O | DIS | Z | CSI_D6 |  | TS_D6 |  |  | CSI-D6 |
| PE11 | GPIO139 | 111 | I/O | DIS | Z | CSI_D7 |  | TS_D7 |  |  | CSI-D7 |
| PE12 | GPIO140 | 98 | I/O | DIS | Z | CSI_SCK |  |  |  |  | CSI-SCK |
| PE13 | GPIO141 | 113 | I/O | DIS | Z | CSI_SDA |  |  |  |  | CSI-SDA |
| PE16 | GPIO144 | 92 | I/O | DIS | Z |  |  |  |  |  | CSI-RST-F |
| PE17 | GPIO145 | 109 | I/O | DIS | Z |  |  |  |  |  | CSI-STBY-F |
| PG0 | GPIO192 | 72 | I/O | DIS | Z | SDC1_CLK |  |  |  | PG_EINT0 | WL-SDIO-CLK |
| PG1 | GPIO193 | 108 | I/O | DIS | Z | SDC1_CMD |  |  |  | PG_EINT1 | WL-SDIO-CMD |
| PG2 | GPIO194 | 63 | I/O | DIS | Z | SDC1_D0 |  |  |  | PG_EINT2 | WL-SDIO-D0 |
| PG3 | GPIO195 | 110 | I/O | DIS | Z | SDC1_D1 |  |  |  | PG_EINT3 | WL-SDIO-D1 |
| PG4 | GPIO196 | 106 | I/O | DIS | Z | SDC1_D2 |  |  |  | PG_EINT4 | WL-SDIO-D2 |
| PG5 | GPIO197 | 112 | I/O | DIS | Z | SDC1_D3 |  |  |  | PG_EINT5 | WL-SDIO-D3 |
| PG6 | GPIO198 | 90 | I/O | DIS | Z | UART1_TX |  |  |  | PG_EINT6 | BT-UART-RX |
| PG7 | GPIO199 | 119 | I/O | DIS | Z | UART1_RX |  |  |  | PG_EINT7 | BT-UART-TX |
| PG8 | GPIO200 | 88 | I/O | DIS | Z | UART1_RTS |  |  |  | PG_EINT8 | BT-UART-CTS |
| PG9 | GPIO201 | 117 | I/O | DIS | Z | UART1_CTS |  |  |  | PG_EINT9 | BT-UART-RTS |
| PG10 | GPIO202 | 99 | I/O | DIS | Z | AIF3_SYNC | PCM1_SYNC |  |  | PG_EINT10 | BT-PCM-SYNC |
| PG11 | GPIO203 | 86 | I/O | DIS | Z | AIF3_BCLK | PCM1_BCLK |  |  | PG_EINT11 | BT-PCM-CLK |
| PG12 | GPIO204 | 120 | I/O | DIS | Z | AIF3_DOUT | PCM1_DOUT |  |  | PG_EINT12 | BT-PCM-DIN |
| PG13 | GPIO205 | 97 | I/O | DIS | Z | AIF3_DIN | PCM1_DIN |  |  | PG_EINT13 | BT-PCM-DOUT |
| PH0 | GPIO224 | 43 | I/O | DIS | Z | I2C0_SCL |  |  |  | PH_EINT0 | TP-SCK |
| PH1 | GPIO225 | 46 | I/O | DIS | Z | I2C0_SDA |  |  |  | PH_EINT1 | TP-SDA |
| PH2 | GPIO226 | 62 | I/O | DIS | Z | I2C1_SCL |  |  |  | PH_EINT2 | PH2-TW1_SCK |
| PH3 | GPIO227 | 37 | I/O | DIS | Z | I2C1_SDA |  |  |  | PH_EINT3 | PH3-TW1_SDA |
| PH4 | GPIO228 | 64 | I/O | DIS | Z | UART3_TX |  |  |  | PH_EINT4 | TP-INT |
| PH5 | GPIO229 | 68 | I/O | DIS | Z | UART3_RX |  |  |  | PH_EINT5 | PH5 |
| PH6 | GPIO230 | 66 | I/O | DIS | Z | UART3_RTS |  |  |  | PH_EINT6 | PH6 |
| PH7 | GPIO231 | 71 | I/O | DIS | Z | UART3_CTS |  |  |  | PH_EINT7 | PH7 |
| PH8 | GPIO232 | 38 | I/O | DIS | Z | OWA_OUT |  |  |  | PH_EINT8 | PH8-OWA_OUT |
| PH9 | GPIO233 | 77 | I/O | DIS | Z |  |  |  |  | PH_EINT9 | PH9 |
| PH10 | GPIO234 | 26 | I/O | DIS | Z | MIC_CLK |  |  |  | PH_EINT10 | LCD-BL-EN |
| PH11 | GPIO235 | 67 | I/O | DIS | Z | MIC_DATA |  |  |  | PH_EINT11 | CTP-RST |
| PL2 | GPIO354 | 21 | I/O | DIS | Z | S_UART_TX |  |  |  | S_PL_EINT2 | WL-REG-ON |
| PL3 | GPIO355 | 23 | I/O | DIS | Z | S_UART_RX |  |  |  | S_PL_EINT3 | WL-WAKE-AP |
| PL4 | GPIO356 | 14 | I/O | DIS | Z | S_JTAG_MS |  |  |  | S_PL_EINT4 | BT-RST-N |
| PL5 | GPIO357 | 18 | I/O | DIS | Z | S_JTAG_CK |  |  |  | S_PL_EINT5 | BT-WAKE-AP |
| PL6 | GPIO358 | 16 | I/O | DIS | Z | S_JTAG_DO |  |  |  | S_PL_EINT6 | AP-WAKE-BT |
| PL7 | GPIO359 | 24 | I/O | DIS | Z | S_JTAG_DI |  |  |  | S_PL_EINT7 | PL7 |
| PL8 | GPIO360 | 15 | I/O | DIS | Z | S_I2C_CLK |  |  |  | S_PL_EINT8 | PL8-S_TWI_SCK |
| PL9 | GPIO361 | 17 | I/O | DIS | Z | S_I2C_SDA |  |  |  | S_PL_EINT9 | PL9-S_TWI_SDA |
| PL10 | GPIO362 | 166 | I/O | DIS | Z | S_PWM |  |  |  | S_PL_EINT10 | PL10-S_PWM |
| PL11 | GPIO363 | 13 | I/O | DIS | Z | S_CIR_RX |  |  |  | S_PL_EINT11 | PL11-IR_RX |

## Pin Assignment Table

This table contains Pin Assignment of SOPine Edge Finger. For more information about peripherals, GPIOs, powering see:

* [Allwinner A64 Datasheet](https://files.pine64.org/doc/datasheet/pine64/A64_Datasheet_V1.1.pdf) section **4.2 GPIO Multiplexing Functions** and section **4.3 Detailed Pin/Signal Description**
* [Power Management Unit Datasheet](https://files.pine64.org/doc/datasheet/pine64/AXP803_Datasheet_V1.0.pdf|AXP803)

For Edge Finger view, see:

* [Edge Finger Pin Assignment Table](https://wiki.pine64.org/wiki/File:SOPine_Pin_Assigment_0.9.pdf)
* [forum.pine64.org: a PDF mapping the pins from the A64 chip itself, to the gold-fingers on the SO-DIMM edge, to the multiple connectors on the baseboard and on the clusterboard, attached to this forum post.](https://forum.pine64.org/showthread.php?tid=8058)

| SOPine Pin | SOPine Name | Allwinner name | Allwinner category | Ball | Type | Description |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | HBIAS | HBIAS | AUDIO_CODEC | D13 | AO | Master Analog Headphone Bias Voltage Output |
| 2 | EAROUT_P | EAROUTP | AUDIO_CODEC | B13 | AO | Earpiece Amplifier Positive Differential Output |
| 3 | HPOUTL | HPOUTL | AUDIO_CODEC | C13 | AO | Headphone Output Left Channel |
| 4 | EAROUT_N | EAROUTN | AUDIO_CODEC | A13 | AO | Earpiece Amplifier Negative Differential Output |
| 5 | HPOUTR | HPOUTR | AUDIO_CODEC | C12 | AO | Headphone Output Right Channel |
| 6 | HS-MIC | MIC-DET | AUDIO_CODEC | B10 | AI | Headphone MIC Detect |
| 7 | GND | GND | POWER | ? | G |  |
| 8 | GND | GND | POWER | ? | G |  |
| 9 | MIC2N | MICIN2N | AUDIO_CODEC | A17 | AI | Microphone Negative Input 2 |
| 10 | HPOUTFB | HP-FB | AUDIO_CODEC | C10 | AI | Headphone Common Reference Feedback Input |
| 11 | MIC2P | MICIN2P | AUDIO_CODEC | B17 | AI | Microphone Positive Input 2 |
| 12 | KEYADC | KEYADC | ADC | A16 | AI | ADC input for key |
| 13 | GPIO363 | PL11 | GPIO | PL11 | GPIO | General Purpose Input Output #363 |
| 14 | GPIO356 | PL4 | GPIO | PL4 | GPIO | General Purpose Input Output #356 |
| 15 | GPIO360 | PL8 | GPIO | PL8 | GPIO | General Purpose Input Output #360 |
| 16 | GPIO358 | PL6 | GPIO | PL6 | GPIO | General Purpose Input Output #358 |
| 17 | GPIO361 | PL9 | GPIO | PL9 | GPIO | General Purpose Input Output #361 |
| 18 | GPIO357 | PL5 | GPIO | PL5 | GPIO | General Purpose Input Output #357 |
| 19 | GND | GND | POWER | ? | G |  |
| 20 | GND | GND | POWER | ? | G |  |
| 21 | GPIO354 | PL2 | GPIO | PL2 | GPIO | General Purpose Input Output #354 |
| 22 | HP-DET | HP-DET | AUDIO_CODEC | D11 | AI | Headphone Detect |
| 23 | GPIO355 | PL3 | GPIO | PL3 | GPIO | General Purpose Input Output #355 |
| 24 | GPIO359 | PL7 | GPIO | PL7 | GPIO | General Purpose Input Output #359 |
| 25 | GPIO69 | PC5 | GPIO | PC5 | GPIO | General Purpose Input Output #69 |
| 26 | GPIO234 | PH10 | GPIO | PH10 | GPIO | General Purpose Input Output #234 |
| 27 | GPIO37 | PB5 | GPIO | PB5 | GPIO | General Purpose Input Output #37 |
| 28 | GPIO36 | PB4 | GPIO | PB4 | GPIO | General Purpose Input Output #36 |
| 29 | GPIO39 | PB7 | GPIO | PB7 | GPIO | General Purpose Input Output #39 |
| 30 | GPIO35 | PB3 | GPIO | PB3 | GPIO | General Purpose Input Output #35 |
| 31 | GND | GND | POWER | ? | G |  |
| 32 | GND | GND | POWER | ? | G |  |
| 33 | GPIO41 | PB9 | GPIO | PB9 | GPIO | General Purpose Input Output #41 |
| 34 | GPIO40 | PB8 | GPIO | PB8 | GPIO | General Purpose Input Output #40 |
| 35 | GPIO32 | PB0 | GPIO | PB0 | GPIO | General Purpose Input Output #32 |
| 36 | GPIO34 | PB2 | GPIO | PB2 | GPIO | General Purpose Input Output #34 |
| 37 | GPIO227 | PH3 | GPIO | PH3 | GPIO | General Purpose Input Output #227 |
| 38 | GPIO232 | PH8 | GPIO | PH8 | GPIO | General Purpose Input Output #232 |
| 39 | GPIO38 | PB6 | GPIO | PB6 | GPIO | General Purpose Input Output #38 |
| 40 | GPIO103 | PD7 | GPIO | PD7 | GPIO | General Purpose Input Output #103 |
| 41 | GND | GND | POWER | ? | G |  |
| 42 | GND | GND | POWER | ? | G |  |
| 43 | GPIO224 | PH0 | GPIO | PH0 | GPIO | General Purpose Input Output #224 |
| 44 | GPIO101 | PD5 | GPIO | PD5 | GPIO | General Purpose Input Output #101 |
| 45 | GPIO102 | PD6 | GPIO | PD6 | GPIO | General Purpose Input Output #102 |
| 46 | GPIO225 | PH1 | GPIO | PH1 | GPIO | General Purpose Input Output #225 |
| 47 | GPIO116 | PD20 | GPIO | PD20 | GPIO | General Purpose Input Output #116 |
| 48 | GPIO107 | PD11 | GPIO | PD11 | GPIO | General Purpose Input Output #107 |
| 49 | GPIO97 | PD1 | GPIO | PD1 | GPIO | General Purpose Input Output #97 |
| 50 | GPIO120 | PD24 | GPIO | PD24 | GPIO | General Purpose Input Output #120 |
| 51 | GPIO106 | PD10 | GPIO | PD10 | GPIO | General Purpose Input Output #106 |
| 52 | GPIO100 | PD4 | GPIO | PD4 | GPIO | General Purpose Input Output #100 |
| 53 | GPIO118 | PD22 | GPIO | PD22 | GPIO | General Purpose Input Output #118 |
| 54 | GPIO133 | PE5 | GPIO | PE5 | GPIO | General Purpose Input Output #133 |
| 55 | GND | GND | POWER | ? | G |  |
| 56 | GND | GND | POWER | ? | G |  |
| 57 | GPIO98 | PD2 | GPIO | PD2 | GPIO | General Purpose Input Output #98 |
| 58 | GPIO128 | PE0 | GPIO | PE0 | GPIO | General Purpose Input Output #128 |
| 59 | GPIO137 | PE9 | GPIO | PE9 | GPIO | General Purpose Input Output #137 |
| 60 | GPIO96 | PD0 | GPIO | PD0 | GPIO | General Purpose Input Output #96 |
| 61 | GPIO99 | PD3 | GPIO | PD3 | GPIO | General Purpose Input Output #99 |
| 62 | GPIO226 | PH2 | GPIO | PH2 | GPIO | General Purpose Input Output #226 |
| 63 | GPIO194 | PG2 | GPIO | PG2 | GPIO | General Purpose Input Output #194 |
| 64 | GPIO228 | PH4 | GPIO | PH4 | GPIO | General Purpose Input Output #228 |
| 65 | GPIO135 | PE7 | GPIO | PE7 | GPIO | General Purpose Input Output #135 |
| 66 | GPIO230 | PH6 | GPIO | PH6 | GPIO | General Purpose Input Output #230 |
| 67 | GPIO235 | PH11 | GPIO | PH11 | GPIO | General Purpose Input Output #235 |
| 68 | GPIO229 | PH5 | GPIO | PH5 | GPIO | General Purpose Input Output #229 |
| 69 | GND | GND | POWER | ? | G |  |
| 70 | GND | GND | POWER | ? | G |  |
| 71 | GPIO231 | PH7 | GPIO | PH7 | GPIO | General Purpose Input Output #231 |
| 72 | GPIO192 | PG0 | GPIO | PG0 | GPIO | General Purpose Input Output #192 |
| 73 | GPIO104 | PD8 | GPIO | PD8 | GPIO | General Purpose Input Output #104 |
| 74 | GPIO117 | PD21 | GPIO | PD21 | GPIO | General Purpose Input Output #117 |
| 75 | GPIO33 | PB1 | GPIO | PB1 | GPIO | General Purpose Input Output #33 |
| 76 | GPIO119 | PD23 | GPIO | PD23 | GPIO | General Purpose Input Output #119 |
| 77 | GPIO233 | PH9 | GPIO | PH9 | GPIO | General Purpose Input Output #233 |
| 78 | GPIO113 | PD17 | GPIO | PD17 | GPIO | General Purpose Input Output #113 |
| 79 | GPIO115 | PD19 | GPIO | PD19 | GPIO | General Purpose Input Output #115 |
| 80 | GPIO111 | PD15 | GPIO | PD15 | GPIO | General Purpose Input Output #111 |
| 81 | GND | GND | POWER | ? | G |  |
| 82 | GPIO112 | PD16 | GPIO | PD16 | GPIO | General Purpose Input Output #112 |
| 83 | GPIO105 | PD9 | GPIO | PD9 | GPIO | General Purpose Input Output #105 |
| 84 | GND | GND | POWER | ? | G |  |
| 85 | GPIO114 | PD18 | GPIO | PD18 | GPIO | General Purpose Input Output #114 |
| 86 | GPIO203 | PG11 | GPIO | PG11 | GPIO | General Purpose Input Output #203 |
| 87 | GPIO110 | PD14 | GPIO | PD14 | GPIO | General Purpose Input Output #110 |
| 88 | GPIO200 | PG8 | GPIO | PG8 | GPIO | General Purpose Input Output #200 |
| 89 | GPIO109 | PD13 | GPIO | PD13 | GPIO | General Purpose Input Output #109 |
| 90 | GPIO198 | PG6 | GPIO | PG6 | GPIO | General Purpose Input Output #198 |
| 91 | GPIO108 | PD12 | GPIO | PD12 | GPIO | General Purpose Input Output #108 |
| 92 | GPIO144 | PE16 | GPIO | PE16 | GPIO | General Purpose Input Output #144 |
| 93 | GND | GND | POWER | ? | G |  |
| 94 | GND | GND | POWER | ? | G |  |
| 95 | GPIO132 | PE4 | GPIO | PE4 | GPIO | General Purpose Input Output #132 |
| 96 | GPIO134 | PE6 | GPIO | PE6 | GPIO | General Purpose Input Output #134 |
| 97 | GPIO205 | PG13 | GPIO | PG13 | GPIO | General Purpose Input Output #205 |
| 98 | GPIO140 | PE12 | GPIO | PE12 | GPIO | General Purpose Input Output #140 |
| 99 | GPIO202 | PG10 | GPIO | PG10 | GPIO | General Purpose Input Output #202 |
| 100 | GPIO130 | PE2 | GPIO | PE2 | GPIO | General Purpose Input Output #130 |
| 101 | GPIO131 | PE3 | GPIO | PE3 | GPIO | General Purpose Input Output #131 |
| 102 | GPIO129 | PE1 | GPIO | PE1 | GPIO | General Purpose Input Output #129 |
| 103 | GND | GND | POWER | ? | G |  |
| 104 | GND | GND | POWER | ? | G |  |
| 105 | GPIO136 | PE8 | GPIO | PE8 | GPIO | General Purpose Input Output #136 |
| 106 | GPIO196 | PG4 | GPIO | PG4 | GPIO | General Purpose Input Output #196 |
| 107 | GPIO138 | PE10 | GPIO | PE10 | GPIO | General Purpose Input Output #138 |
| 108 | GPIO193 | PG1 | GPIO | PG1 | GPIO | General Purpose Input Output #193 |
| 109 | GPIO145 | PE17 | GPIO | PE17 | GPIO | General Purpose Input Output #145 |
| 110 | GPIO195 | PG3 | GPIO | PG3 | GPIO | General Purpose Input Output #195 |
| 111 | GPIO139 | PE11 | GPIO | PE11 | GPIO | General Purpose Input Output #139 |
| 112 | GPIO197 | PG5 | GPIO | PG5 | GPIO | General Purpose Input Output #197 |
| 113 | GPIO141 | PE13 | GPIO | PE13 | GPIO | General Purpose Input Output #141 |
| 114 | GND | GND | POWER | ? | G |  |
| 115 | GND | GND | POWER | ? | G |  |
| 116 | DSI-D1P | MDSI-D1P | MIPI_DSI | P22 | AO | MIPI DSI Positive Differential Data Line 1 |
| 117 | GPIO201 | PG9 | GPIO | PG9 | GPIO | General Purpose Input Output #201 |
| 118 | DSI-D1N | MDSI-D1N | MIPI_DSI | R22 | AO | MIPI DSI Negative Differential Data Line 1 |
| 119 | GPIO199 | PG7 | GPIO | PG7 | GPIO | General Purpose Input Output #199 |
| 120 | GPIO204 | PG12 | GPIO | PG12 | GPIO | General Purpose Input Output #204 |
| 121 | DSI-D0P | MDSI-D0P | MIPI_DSI | T22 | AO | MIPI DSI Positive Differential Data Line 0 |
| 122 | DSI-D3P | MDSI-D3P | MIPI_DSI | L23 | AO | MIPI DSI Positive Differential Data Line 3 |
| 123 | DSI-D0N | MDSI-D0N | MIPI_DSI | T23 | AO | MIPI DSI Negative Differential Data Line 0 |
| 124 | DSI-D3N | MDSI-D3N | MIPI_DSI | L22 | AO | MIPI DSI Negative Differential Data Line 3 |
| 125 | GND | GND | POWER | ? | G |  |
| 126 | DSI-D2P | MDSI-D2P | MIPI_DSI | M22 | AO | MIPI DSI Positive Differential Data Line 2 |
| 127 | DSI-CKP | MDSI-CKP | MIPI_DSI | N23 | AO | MIPI DSI Positive Differential Clock Line |
| 128 | DSI-D2N | MDSI-D2N | MIPI_DSI | N22 | AO | MIPI DSI Negative Differential Data Line 2 |
| 129 | DSI-CKN | MDSI-CKN | MIPI_DSI | P23 | AO | MIPI DSI Negative Differential Clock Line |
| 130 | GPIO72 | PC8 | GPIO | PC8 | GPIO | General Purpose Input Output #72 |
| 131 | GND | GND | POWER | ? | G |  |
| 132 | GPIO71 | PC7 | GPIO | PC7 | GPIO | General Purpose Input Output #71 |
| 133 | GPIO79 | PC15 | GPIO | PC15 | GPIO | General Purpose Input Output #79 |
| 134 | GPIO64 | PC0 | GPIO | PC0 | GPIO | General Purpose Input Output #64 |
| 135 | GPIO68 | PC4 | GPIO | PC4 | GPIO | General Purpose Input Output #68 |
| 136 | VIDEO-HTX0P | HTX0P | HDMI | G22 | AO | HDMI Positive Differential Data Line 0 |
| 137 | GND | GND | POWER | ? | G |  |
| 138 | VIDEO-HTX0N | HTX0N | HDMI | G23 | AO | HDMI Negative Differential Data Line 0 |
| 139 | VIDEO-HTX2N | HTX2N | HDMI | E22 | AO | HDMI Negative Differential Data Line 2 |
| 140 | GND | GND | POWER | ? | G |  |
| 141 | VIDEO-HTX2P | HTX2P | HDMI | D23 | AO | HDMI Positive Differential Data Line 2 |
| 142 | GPIO66 | PC2 | GPIO | PC2 | GPIO | General Purpose Input Output #66 |
| 143 | VIDEO-HTX1P | HTX1P | HDMI | E23 | AO | HDMI Positive Differential Data Line 1 |
| 144 | GPIO80 | PC16 | GPIO | PC16 | GPIO | General Purpose Input Output #80 |
| 145 | VIDEO-HTX1N | HTX1N | HDMI | F22 | AO | HDMI Negative Differential Data Line 1 |
| 146 | GPIO76 | PC12 | GPIO | PC12 | GPIO | General Purpose Input Output #76 |
| 147 | GND | GND | POWER | ? | G |  |
| 148 | GPIO67 | PC3 | GPIO | PC3 | GPIO | General Purpose Input Output #67 |
| 149 | VIDEO-TXCN | HTXCN | HDMI | H23 | AO | HDMI Negative Differential Clock Line |
| 150 | GPIO65 | PC1 | GPIO | PC1 | GPIO | General Purpose Input Output #65 |
| 151 | VIDEO-TXCP | HTXCP | HDMI | H22 | AO | HDMI Positive Differential Clock Line |
| 152 | GND | GND | POWER | ? | G |  |
| 153 | GPIO73 | PC9 | GPIO | PC9 | GPIO | General Purpose Input Output #73 |
| 154 | GPIO70 | PC6 | GPIO | PC6 | GPIO | General Purpose Input Output #70 |
| 155 | GPIO78 | PC14 | GPIO | PC14 | GPIO | General Purpose Input Output #78 |
| 156 | GPIO74 | PC10 | GPIO | PC10 | GPIO | General Purpose Input Output #74 |
| 157 | GPIO77 | PC13 | GPIO | PC13 | GPIO | General Purpose Input Output #77 |
| 158 | USB1-DP | USB1-DP | USB | B23 | A I/O | USB 1 Data Positive |
| 159 | GND | GND | POWER | ? | G |  |
| 160 | USB1-DM | USB1-DM | USB | C22 | A I/O | USB 1 Data Negative |
| 161 | VIDEO-SCL | HSCL | HDMI | G21 | I/O | HDMI DDC Clock |
| 162 | GND | GND | POWER | ? | G |  |
| 163 | VIDEO-SDA | HSDA | HDMI | E20 | I/O | HDMI DDC Data |
| 164 | VIDEO-HPD | HHPD | HDMI | E21 | I/O | HDMI Hot Plug Detection |
| 165 | GPIO75 | PC11 | GPIO | PC11 | GPIO | General Purpose Input Output #75 |
| 166 | GPIO362 | PL10 | GPIO | PL10 | GPIO | General Purpose Input Output #362 |
| 167 | VIDEO-CEC | HCEC | HDMI | F21 | I/O | HDMI CEC |
| 168 | PWR_ON | PWRON | PMU | 60 | I | Power On-Off key input |
| 169 | GND | GND | POWER | ? | G |  |
| 170 | NC |  |  |  |  |  |
| 171 | USB0-DP | USB0-DP | USB | A22 | A I/O | USB 0 Data Positive |
| 172 | DCDC1 | DCDC1 | POWER | ? | P | 3.3V from DCDC for eMMC, LEDs and other external devices with higher power consumption |
| 173 | USB0-DM | USB0-DM | USB | B22 | A I/O | USB 0 Data Negative |
| 174 | GPIO0-LDO | GPIO0 | POWER | ? | P | 3.3V@100mA from LDO for Capacitive Touch Screen I2C interface as pull-up and other purposes with low power consumption |
| 175 | CHG_LED | CHGLED | OTHER | 53 | O | Charger status indication |
| 176 | ALDO1 | ALDO1 | POWER | ? | P | 2.8V@500mA from LDO for CSI Camera and other 2.8V based devices with low power consumption |
| 177 | RESET | RESET | OTHER | ? | I | Pin for restarting of device, ground pin to perform device reset |
| 178 | NC |  |  |  |  |  |
| 179 | NC |  |  |  |  |  |
| 180 | DCIN | ACIN | POWER | ? | P | 5V input, but probably can be more, look at the AXP803 datasheet |
| 181 | ELDO3 | ELDO3 | POWER | ? | P | 1.8V@200mA from LDO for CSI Camera and other 1.8V based devices with low power consumption |
| 182 | DCIN | ACIN | POWER | ? | P | 5V input, but probably can be more, look at the AXP803 datasheet |
| 183 | DLDO3 | DLDO3 | POWER | ? | P | 2.8V@300mA from LDO for CSI Camera and other 2.8V based devices with low power consumption |
| 184 | DCIN | ACIN | POWER | ? | P | 5V input, but probably can be more, look at the AXP803 datasheet |
| 185 | VCC-WIFI | DLDO4 | POWER | ? | P | 3.3V@500mA from LDO for WiFi, Bluetooth and other 3.3V based devices |
| 186 | NC |  |  |  |  |  |
| 187 | DC1-SW | DC1-SW | POWER | ? | P | 3.3V from DCDC for LCD and Ethernet (RGMII, RMII so GMAC and EMAC) and other 3.3V based devices |
| 188 | USBVBUS | USBVBUS | POWER | ? | P | 5V for powering and charging PMU |
| 189 | DLDO2 | DLDO2 | POWER | ? | P | Probably 1.8V@400mA (some sources indicate 3.3V) from DCDC for MIPI and other 1.8V based devices |
| 190 | USBVBUS | USBVBUS | POWER | ? | P | 5V for powering and charging PMU |
| 191 | DLDO1 | DLDO1 | POWER | ? | P | 3.3V@500mA from LDO for HDMI, MIPI DSI and other 3.3V based devices |
| 192 | USBVBUS | USBVBUS | POWER | ? | P | 5V for powering and charging PMU |
| 193 | VCC-WIFI-IO | DLDO4 | POWER | ? | P | 3.3V@500mA from LDO for WiFi, Bluetooth and other 3.3V based devices |
| 194 | NC |  |  |  |  |  |
| 195 | NC |  |  |  |  |  |
| 196 | BATT_SENSOR | TS | PMU | ? | I | Battery Temperature Sensor Input |
| 197 | VRTC | VCC-RTC | PMU | ? | O | Output pin of RTLCDO (NOT SURE) |
| 198 | NC |  |  |  |  |  |
| 199 | PS | IPSOUT | POWER | 55 | P | 3.5V-5V@3A System power source |
| 200 | VBAT | VBAT | POWER | ? | P | 3.5-4.2V power input from battery |
| 201 | PS | IPSOUT | POWER | 55 | P | 3.5V-5V@3A System power source |
| 202 | VBAT | VBAT | POWER | ? | P | 3.5-4.2V power input from battery |
| 203 | PS | IPSOUT | POWER | 55 | P | 3.5V-5V@3A System power source |
| 204 | VBAT | VBAT | POWER | ? | P | 3.5-4.2V power input from battery |
