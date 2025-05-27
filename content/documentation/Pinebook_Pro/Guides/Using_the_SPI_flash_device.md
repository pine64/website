---
title: "Using the SPI flash device"
draft: false
menu:
  docs:
    title:
    parent: "Pinebook_Pro/Guides"
    identifier: "Pinebook_Pro/Guides/Using_the_SPI_flash_device"
    weight:
---

{{< admonition type="warning" >}}
 When removing the large RF shield found on the mainboard, to be able to short the pins on the SPI chip, make absolutely sure to align it correctly while putting it back. Failing to do so can result in shorting the battery to the ground, due to the close proximity of the solder pads for the bypass cables, which would prevent the normal operation and effectively cause a fire hazard. It is highly recommended to disconnect the battery before removing the RF shield, and before putting it back.
{{< /admonition >}}

See [SPI](/documentation/Pinebook_Pro/Features/SPI) for details.

The Pinebook Pro comes with a 128 Mbit, (16MByte), flash device suitable for initial boot target, to store the bootloader. The SoC used on the Pinebook Pro boots from this SPI flash device first, before eMMC or SD card. At present, April 19, 2020, the Pinebook Pros ship without anything programmed in the SPI flash device. So the SoC moves on to the next potential boot device, the eMMC. ARM/ARM64 computers do not have a standardized BIOS, yet.

Here is some information on using the SPI flash device:

* You need the kernel built with SPI flash device support, which will supply a device similar to: **/dev/mtd0**
* The Linux package below, will need to be available: _mtd-utils_
* You can then use this program from the package to write the SPI device: `flashcp <filename> /dev/mtd0`

Even if you need to recover from a defective bootloader written to the SPI flash, you can simply short pin 6 of the SPI flash to GND and boot. This will render the SoC bootrom unable to read from the SPI flash and have it fall back to reading the bootloader from other boot media like the eMMC or Micro SD card.

The procedures described above are a lot less risky than attaching an external SPI flasher and do not require any additional hardware. At present, April 19th, 2020, there is no good bootloader image to flash into the SPI flash device. This is expected to change, as there are people working on issue.
