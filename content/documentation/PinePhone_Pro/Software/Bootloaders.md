---
title: "Bootloaders"
draft: false
menu:
  docs:
    title:
    parent: "PinePhone_Pro/Software"
    identifier: "PinePhone_Pro/Software/Bootloaders"
    weight: 5
---

The following section contains notes regarding compatible bootloaders with the PinePhone Pro.

## rk2aw

The rk2aw loader program is designed for modern Rockchip SoCs. It modifies the boot ROM bootloader load order from the original and rigid “SPI NOR flash -> eMMC -> SD card” to a more flexible “SD card -> eMMC -> SPI NOR flash”. Additionally, it enables robust A/B bootloader updates in SPI NOR flash, allowing users to choose fallback options via a pre-boot menu. For details see the [rk2aw page](https://xnux.eu/rk2aw/).

## U-Boot

U-Boot is an open-source bootloader commonly used in embedded operating systems and is often pre-installed on device images.

## Tow-Boot

_Tow-Boot_ is an opinionated distribution of _U-Boot_ and brings numerous advantages over stock _U-Boot_, such as the possibility to choose from booting the eMMC or microSD card using the volume buttons during boot, as well as a _USB Mass Storage mode_, where the device can be written to by connecting the device to a computer via USB.

The user can flash Tow-Boot to the PinePhone Pro using the [instructions on the Tow-Boot website](https://tow-boot.org/devices/pine64-pinephonePro.html).

## levinboot

The levinboot bootloader is another option for the PinePhone Pro. The project repository can be found [here](https://gitlab.com/DeltaGem/levinboot/-/tree/master/). (Pinephone Pro supporting fork is [here](https://xff.cz/git/levinboot/).)
