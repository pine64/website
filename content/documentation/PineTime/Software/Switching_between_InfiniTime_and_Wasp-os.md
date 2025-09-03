---
title: "Switching your PineTime between InfiniTime and Wasp-os"
draft: false
menu:
  docs:
    title: "Switching InfiniTime and Wasp-os"
    parent: "PineTime/Software"
    identifier: "PineTime/Software/Switching_between_InfiniTime_and_Wasp-os"
    weight:
aliases:
  - /wiki/Switching_your_PineTime_between_InfiniTime_and_Wasp-os
---

{{< admonition type="warning" >}}
**Do not attempt to change between infinitime and wasp-os on watches shipped with bootloader v1.0.1.** Your device may be **bricked** and **will require unsealing** to revive it!

This issue should be resolved soon, and this warning will be removed when all guides have been updated.
{{</ admonition >}}

## Introduction

Both Infinitime and Wasp-os are very cool OS’es for the [PineTime](/documentation/PineTime) and many people will want to try both. This is possible, even with a sealed device!

Both devices use the same Nordic (legacy) DFU protocol for updating firmware over the air. But the BLE stack and the bootloaders for both are different. That’s why we need to use the [reloader](https://github.com/daniel-thompson/wasp-reloader). However, instructions you find elsewhere (including [Daniel Thompsons video](https://www.youtube.com/watch?v=lPasAt1LJmo)) are somewhat outdated.

Flashing can be done with any of

* [Gadgetbridge](https://www.gadgetbridge.org) (Android >= 4.4)
* [Amazfish](https://github.com/piggz/harbour-amazfish) (SailfishOS and Linux)
* [Siglo](https://github.com/alexr4535/siglo) (Linux desktop and Pinephone) (Use the 'Manual OTA File' option)
* [PinetimeFlasher](https://github.com/ZephyrLabs/PinetimeFlasher) (Windows)
* ota-dfu-python (Linux CLI) which is included in sources of both Infinitime and Wasp-os
  * `InfiniTime/bootloader/ota-dfu-python/dfu.py`
  * `wasp-os/tools/ota-dfu-python/dfu.py`

{{< admonition type="note" >}}
 We removed mentions to NRFConnect as this app is closed source and recent versions do not work anymore with InfiniTime (the last version known to work is 4.24.3). If you used NRFConnect in the past, we recommend you switch to Gadgetbridge.
{{</ admonition >}}

This guide has been last updated for Infinitime 1.1.0 and Wasp-os 0.4.1.

{{< figure src="/documentation/images/Flash-reloader-mcuboot.jpg" caption="Flashing reloader-mcuboot.zip" width="600" >}}
{{< figure src="/documentation/images/Flash-micropython.jpg" caption="Flashing micropython.zip" width="400" >}}

## InfiniTime to Wasp-os

All the zips you need can be found from the [wasp-os installation guide](https://wasp-os.readthedocs.io/en/latest/install.html#binary-downloads).

* Make sure the watch is running Infinitime and can be found by your companion device (PC, phone, etc).
* First we need to flash the reloader, with the wasp-os bootloader as payload. To do this, flash: `wasp-os-0.4/build-pinetime/reloader-mcuboot.zip`
* After flashing, it will boot using the Infinitime bootloader (green large pine cone), then it’ll hang for a few seconds, then it’ll show the reloader animation (blue smaller pine cone), and then it’ll boot the wasp-os bootloader.
* Make sure the watch is on the screen with the pine cone and arrow. If it is in a bootloop instead, then reboot the watch by holding the button until the arrow appears.
* Now you can flash micropython with wasp-os: `wasp-os-0.4/build-pinetime/micropython.zip`
* Wasp-os should now boot. Enjoy!

## Wasp-os to InfiniTime

{{< figure src="/documentation/images/Flash-reloader-infinitime-recovery.jpg" caption="Flashing reloader-infinitime-recovery-0.14.1.zip" width="500" >}}
{{< figure src="/documentation/images/Flash-infinitime.jpg" caption="Flashing pinetime-mcuboot-app-dfu-1.1.0.zip" width="600" >}}

The `reloader-factory.zip` was broken in the original wasp-os 0.4 but was fixed in wasp-os 0.4.1. However the Infinitime binaries are outdated the 0.4 release and I do not recommend flashing these. Older InfiniTime versions have flaky BLE which makes upgrading from there very unreliable.

You can get newer binaries from the wasp-os projects CI system (see the [wasp-os installation guide](https://wasp-os.readthedocs.io/en/latest/install.html#binary-downloads)) or alternatively, I made my own containing just the [InfiniTime 0.14.1](https://github.com/JF002/InfiniTime/releases/tag/0.14.1) [recovery firmware](https://github.com/JF002/pinetime-mcuboot-bootloader/blob/develop/README.md#recovery-firmware). This allows you to flash any future release of InfiniTime without having to find a new reloader zip. Get the [reloader zip here](https://github.com/Peetz0r/wasp-reloader/releases/tag/infinitime-0.14.1-recovery) and the [latest Infinitime here](https://github.com/JF002/InfiniTime/releases).

* Reboot the watch by holding the button until the pine cone arrow appears.
* Flash the reloader zip: `reloader-infinitime-recovery-0.14.1.zip`
* After flashing, the reloader will run (blue smaller pine cone), then it’ll boot the InfiniTime bootloader (large pine cone) will run.
* Boot the watch into recovery mode by holding the button until the pine cone turns red. It’ll boot again (large pine cone will turn green) and then the InfiniTime logo will appear.
* You can now flash InfiniTime 1.1.0 (or any other version): `pinetime-mcuboot-app-dfu-1.1.0.zip`
* InfiniTime should now boot. Enjoy!
