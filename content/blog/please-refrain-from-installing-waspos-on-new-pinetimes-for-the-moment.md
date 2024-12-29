---
title: Please refrain from installing WASP-OS on new PineTimes for the moment"
date: "2024-12-29"
authors: ["JF002"]
cover: 
  image: "construction.jpg"
images:
  - "/blog/images/construction.jpg"
---

In July 2024, PineStore [notified the community](https://github.com/InfiniTimeOrg/InfiniTime/issues/2096) that a small hardware change was needed on the PineTime : the current flash chip was end of life (EoL) and needed to be replaced by a new one. From the software point of view, the new chip behaves exactly like the old on so very few code changes were required to support it.

The new chip exposes different identifiers (manufacturer ID, for example) than the previous one. Which means that if the software checks those IDs, it would need to be updated to take the new ones into account.

No change was needed in InfiniTime, but we however added a [new field in the SystemInfo app to display the IDs of the chip](https://github.com/InfiniTimeOrg/InfiniTime/releases/tag/1.14.1). We figure this could be useful in the future.

The [bootloader](https://github.com/InfiniTimeOrg/pinetime-mcuboot-bootloader) does check against those IDs so we released a [new version of the bootloader (v1.0.1) as well](https://github.com/InfiniTimeOrg/pinetime-mcuboot-bootloader/releases/tag/1.0.1).

We provided the new software to PineStore so they could test them and use them to flash the new batch of PineTimes at the factory.

Everything went well and PineTimes equipped with the new memory chip and software are being delivered to happy users.

Everything? Well, not really : a few users reported soft-bricked PineTimes after switching to WASP-OS and then reverting to InfiniTime again. This is a bummer : **the "reloader" tool that reinstalls the InfiniTime bootloader also needed to be upgraded to support the new memory chip!**

[An issue has already been opened on the WASP-OS GitHub repo](https://github.com/wasp-os/wasp-os/issues/519) and a new reloader tool will hopefully be released soon to tackle this issue. We also added a big red warning on the documentation page that [explains how to switch to and from InfiniTime and WASP-OS](https://pine64.org/documentation/PineTime/Software/Switching_between_InfiniTime_and_Wasp-os/) to ensure that users won't try to switch OS until the issue is fixed and the documentation updated.

In the meantime, **do not try to install WASP-OS on your PineTime if it's running bootloader v1.0.1 from the factory (unless you know exactly what you are doing), this WILL brick your PineTime!**

Be sure that the community will try to fix this as soon as possible, but please remember that developers, like mostly everyone, are a bit less available during this period of the year ;-)

We are really sorry for the inconvenience caused by this issue, and we wish everyone a happy holiday season!

![](/blog/images/pinetime-bootloader-1-0-1.jpg)