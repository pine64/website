---
title: "Boot order"
draft: false
menu:
  docs:
    title:
    parent: "PinePhone_Pro/Software"
    identifier: "PinePhone_Pro/Software/Boot_order"
    weight: 1
---

The RK3399S processor in the PinePhone Pro searches for the bootloader (such as _U-Boot_ or _Tow-Boot_) in the following order:

1. SPI flash
2. eMMC (the internal memory)
3. MicroSD card

## Boot from microSD card temporarily

To temporarily boot from an inserted **microSD card** do the following:

* On the **Explorer Edition ordered after November 2023** the microSD card is first in boot order due to using _rk2aw_ instead of _Tow-Boot_, see [here](https://xnux.eu/rk2aw/). A boot menu can be opened by holding _power_ at boot for not too long.
* On the **Explorer Edition ordered after July 2022** hold the _volume down key_ while powering on the device. The batches bought after July 2022 come with _Tow-Boot_ flashed to the SPI, which offers additional functionality over _U-Boot_ as bootloader.
* On the **Explorer Edition ordered between January and July 2022** hold the _RE_ button underneath the cover for a few seconds, while powering on the device. If the button is labeled _RESET_ instead of _RE_ please verify if the device is a regular [PinePhone](/documentation/PinePhone) (or the Developer Edition). This is required because older batches don’t ship with _Tow-Boot_ on the SPI. Flashing _Tow-Boot_ can be caught up by following [this](https://tow-boot.org/devices/pine64-pinephonePro.html) instruction. Note: If _Tow-Boot_ is flashed later, the microSD card can be selected at boot with the volume down key as well.
* On the **Developer Edition (sold to selected developers only)** the SPI and the eMMC can be bypassed by shorting the bypass test points while booting. The process is explained in the article [PinePhone Pro Developer Edition](/documentation/PinePhone_Pro/Revisions/Developer_Edition). Please join the community chat for any questions regarding the process.

The RE button disables the SPI and the eMMC at the hardware level while the button is held and the PinePhone Pro will try to boot from the next available boot medium, which is the microSD card. Note: When holding the _RE_ button (or when shorting the contact points in case of the _Developer Edition_) for a longer time at boot the operating system will not initialize the SPI and eMMC and it will not be possible to write to these storage mediums until the next reboot.

{{< admonition type="note" >}}
 The bootloader uses its own boot order for loading the kernel and other core operating system components at boot, which for example may result in the boot loader residing on the eMMC loading and booting the kernel from a microSD card.
{{< /admonition >}}

## Boot from microSD card permanently

The bootloader (such as _U-Boot_) resides in the free space in front of the first partition. Wiping the bootloader from the eMMC to make the PinePhone Pro boot from microSD card can be done using `sudo dd if=/dev/zero of=/dev/mmcblk2 seek=64 count=400 conv=fsync`. Formatting the drive or deleting the partition table is not sufficient to wipe the bootloader.
