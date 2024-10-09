---
title: "Software tweaks"
draft: false
menu:
  docs:
    title:
    parent: "PineNote/Development"
    identifier: "PineNote/Development/Software_tweaks"
    weight: 99
---

## Fixing Bluetooth
Some users have noticed instability with their wireless driver. Upgrading the driver to the version provided by LibreELEC may help! To do this, download the BCM4345C0.hcd, brcmfmac43455-sdio.bin, and brcmfmac43455-sdio.txt from the [libreELEC repositories](https://github.com/LibreELEC/brcmfmac_sdio-firmware/tree/master) and place them in the same location as your previous firmware (`/lib/firmware/brmc/`). Then rename brcmfmac43455-sdio.{txt,bin} as `brcmfmac43455-sdio.pine64,pinenote-v1.2.{txt,bin}`. If this doesn’t help, ask about it in the matrix chat!

### Preliminary fix for stuttering bluetooth audio

Following a fix used for the Quartz Model A (which uses the same SoC as the Pinenote), we can modify the device tree prior to building the kernel to try to mitigate poor Bluetooth audio streaming. (reference: see https://lore.kernel.org/linux-arm-kernel/20220926055435.31284-1-leo@nabam.net/T/)

**Steps:**

* Open `arch/arm64/boot/dts/rockchip/rk3566-pinenote.dtsi`
* Go to line 939, "bluetooth", under the "uart1" section
* Edit the two lines that read "device-wake-gpios" and "host-wake-gpios"; you want them to read "device-wakeup-gpios" and "host-wakeup-gpios" respectively
* Add the following line to the end of the bluetooth section (under the vddio-supply line in my .dtsi): "max-speed = &lt;3000000>;"
* Count your zeros, don’t forget your punctuation..

**Caveats:**

This will improve BT audio quality at least when using the AAC codec. In my experience, the quality is more than acceptable, but there are still issues apparent: occasional isolated stutters even on AAC; prohibitively frequent stutters on SBC-XQ remain. Fully resolving BT audio issues might require further changes similar to the one described above, or may alternatively be a matter of audio software settings (e. g., process priority, audio server buffer settings). Investigation ongoing.

## libinput Palm Detection

See https://gitlab.com/hrdl/pinenote-shared/-/blob/main/etc/libinput/local-overrides.quirks.

## libinput Touch Arbitration

Prerequisites: `libinput>1.22.1` and setup touch arbitration via udev: https://gitlab.com/hrdl/pinenote-shared/-/blob/main/etc/udev/rules.d/81-libinput-pinenote.rules

### Issues and workarounds

* No resolution reported by touchscreen driver. Workaround: patch `cyttsp5.c` and device tree: https://gitlab.com/hrdl/linux/-/commit/f1f9eb197d3bd88c9189ab9d8fba2d03d2e13960 or set device quirk `AttrSizeHint=210x157`.
* Touch screen arbitration is independent of the screen’s rotation. Workaround: use `AttrEventCode=-ABS_TILT_X` (on older version: `AttrEventCodeDisable=ABS_TILT_X`) in a libinput quirk matching `w9013 2D1F:0095 Stylus`. This makes touch arbitration independent of the pen’s location.
