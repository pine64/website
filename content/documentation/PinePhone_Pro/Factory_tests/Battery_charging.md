---
title: "Battery charging"
draft: false
menu:
  docs:
    title:
    parent: "PinePhone_Pro/Factory_tests"
    identifier: "PinePhone_Pro/Factory_tests/Factory_test_battery_charging"
    weight:
---

{{< figure src="/documentation/images/PPP_Abdroid_Test_Utility-1.jpg" width="300" >}}

{{< admonition type="note" >}}
Please note that this Android build solely for PinePhone Pro hardware checking purpose and solely used by support team. This is NOT a general release build.
{{</ admonition >}}

Download:

* [Direct download](https://files.pine64.org/os/PinePhonePro/pinephone_pro_dd_android9_QC_Test_SDboot_20220215-8GB.img.gz) from _pine64.org_ (722MB, for 8GB microSD cards or bigger, MD5 of the GZip file _214e063c8205c1a98d44b2015a21bb5d_)

Instructions:

* Download the build, extract the image and dd it to a 8 GB or larger microSD card, takes out the PinePhone Pro Explorer Edition then insert it into microSD slot (upper slot).
* Insert battery, press RE button (bypass SPI and eMMC boot)  while plug in USB-C power. After 3 seconds release RE button.
* When power up, below battery icon screen show up and battery will start charging.
* The battery icon display for few seconds and then LCD panel turn off while charging. To check charging status, just quick press power button (about 0.5 second) and battery icon will display progress.
