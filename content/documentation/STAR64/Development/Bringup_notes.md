---
title: "Bringup notes"
draft: false
menu:
  docs:
    title:
    parent: "STAR64/Development"
    identifier: "STAR64/Development/Bringup_notes"
    weight: 1
---

* The USB over-current protection is not wired up correctly to the USB ports on Star64. The default Starfive Kernel will disable USB on boot as it belives the ports are overcurrent. This ugly hack works around it: https://github.com/Fishwaldo/Star64_linux/commit/2634a13ecfa1fa5c232ec2b9f6a6b6b0d9d66898
* The Wifi Chip (RTL8852BU) is not supported in the kernel. There is a Vendor Driver that is imported in the kernel at https://github.com/Fishwaldo/Star64_linux/tree/Star64_devel/drivers/staging/rtl8852bu but it really needs a cleanup. It does BUG_ON at boot, but wifi is confirmed working. 
* HDMI can be finicky. 4K Monitors are known to have a issue. This is also relevant for VisionFive2
* Some kernels/distributions do not detect the total memory correctly. This is due to the way u-boot is configured. Currently, u-boot reads the memory from the eeprom on the Star64, and updates the dtb file before booting the kernel. Distributions that boot differently may not get the updated dtb file with the correct memory entry. You can work around this by recompiling the DTB with the correct memory for your board
* VisionFive2 Kernels will only offer limited functionality on the Star64 - Mainly USB, Wifi and PCI will not work.
* The 4-pin 12 volt JST-XH-4A connector found on the Star64 is incompatible with the dual SATA power adapter intended for the ROCKPro64. The connector on the Star64 is rotated 180 degrees to the one on the ROCKPro64, resulting in the cable receiving +12V where GND is expected and vice versa. The cable’s internal circuitry ends up shorting in this configuration.
* Booting from uSD: Component S1804 is adjacent to the 40pin GPIO Bus; ignore the printed text on S1804 that says "ON" or "ONKE". Do pay attention to the '1' and '2' printed on S1804. Also pay attention to the 'L' and 'H' text on the board next to S1804. The 'L' stand for '0' and the 'H' stands for '1'. You will need to flip switch '1' (GPIO_1) on S1804 to the 'L' position and switch '2' (GPIO_0) on S1804 to the 'H' position. S1804 maps to the table next to S1804 that has text [ [GPIO_1 | GPIO_0], [0|0] Flash, [0|1] SD, [1|0] EMMC, [1|1] UART ]; Helpful links: https://mrrcode979.github.io/blog/post/star64-guide/, https://www.bortzmeyer.org/star64-first-boot.html
* TTL use notes: Ground is on pin 6, RXD is on pin 8, and TXD is on pin 10.

## Prototype Bringup Notes

{{< admonition type="note" >}}
 This section is relevant to the original prototype (v1.0) that a few developers received. 
{{< /admonition >}}

* The [schematic](https://files.pine64.org/doc/star64/Star64_Schematic_V1.0_20220721.pdf) has several discrepancies with actual board labels.
* The serial console can be found with TXD on pin 8 and RXD on pin 10; a convention common to Pi-style boards. Use the 40pin header pinouts in color on page one and not the schematic prose.
* If you have only a single core running and no PCI card present, it appears to power up via the +5V/GND lines from the USB serial adapter pins.
* It will not boot from a VisionFive R1 uSD card.
* The boot device switch labels and the silk screen are inverted. "0" means "On".
* 2021.10-00001-gdbdaad919b will attempt to boot from SPI, but it appears blank. If you let it for many minutes, the device will eventually time out and boot OpenSBI v1.0  from (SPI?). This will fail, but only after self-identifying as a VisionFive R2, complete with five cores and 4 GB of RAM, before failing. A "press any key" timeout is offered, but I’ve been unable to make it stop. It will eventually crash with:

  ```
  Loading Environment from SPIFlash... SF: Detected gd25lq128 with page size 256 Bytes, erase size 4 KiB, total 16 MiB
  *** Warning - bad CRC, using default environment
   
  Not a StarFive EEPROM data format - magic error
  ```
