---
title: "Software releases"
draft: false
menu:
  docs:
    title:
    parent: "Yuzuki_Avaota-A1/Software"
    identifier: "Yuzuki_Avaota-A1/Software/Releases"
    weight:
---

These releases are still in **beta** state and are only fit for development purposes. 


# OpenWrt Image Build
{{< figure src="/documentation/images/Openwrt_logo_square.png" width="100" >}}

* [OpenWrt Github Release](https://github.com/AvaotaSBC/openwrt/releases)

# Armbian Mainline Linux OS Image Build
{{< figure src="/documentation/images/armbian.png" width="100" >}}

* Source code available at https://github.com/pine64/build/releases, others are welcome to fork and enhance.
* Attach USB keyboard, then follow onboard small LCD screen message to complete first setup
* After the initial setup, please allow some time for the download of the HA (Home Assistant) image
* PineDio Zigbee dongle driver already included
* For the board with 2GB of memory, please only use OS build with Picoclaw version.

**The following are 2026.06.05 builds**
* [Direct Download Ubuntu 26.05 Noble with Home Assistance and Picoclaw build](http://files.pine64.org/os/Yuzuki/Armbian-unofficial_26.05.0-trunk_Avaota-a1_noble_legacy_5.15.154_xfce_desktop_picoclaw_cleanblz_20260605-162523.img.xz) from *pine64.org* (987MB, MD5  *777f08ad5d42f3e8c56aa242eff8f855*)
* [Direct Download Ubuntu 26.05 Noble with Home Assistance and openclaw build](http://files.pine64.org/os/Yuzuki/Armbian-unofficial_26.05.0-trunk_Avaota-a1_noble_legacy_5.15.154_xfce_desktop_openclaw_cleanblz_20260605-164956.img.xz) from *pine64.org* (988MB, MD5  *e40065560256718af2590f85137a55cc*)

**The following are 2026.05.21 builds**
* [Direct Download Ubuntu 26.05 Noble with Home Assistance and Picoclaw build](http://files.pine64.org/os/Yuzuki/Armbian-unofficial_26.05.0-trunk_Avaota-a1_noble_legacy_5.15.154_xfce_desktop_picoclaw_20260521.img.xz) from *pine64.org* (987MB, MD5  *4f60fdd168817b70f5b782f412009210*)
* [Direct Download Ubuntu 26.05 Noble with Home Assistance and openclaw build](http://files.pine64.org/os/Yuzuki/Armbian-unofficial_26.05.0-trunk_Avaota-a1_noble_legacy_5.15.154_xfce_desktop_openclaw.img_20260521.xz) from *pine64.org* (982MB, MD5  *bd6f6edb2a5733d79b0ea4bf3d867403*)

# Avaota OS Legacy Linux Image Build
{{< figure src="/documentation/images/Avaota-icon.png" width="100" >}}

**The following OS build is derived from the Allwinner BSP**

* [Direct Download Ubuntu 22.04.5 Jimmy CLI build](http://files.pine64.org/os/Yuzuki/AvaotaOS-jammy-cli-arm64-avaota-a1.img.xz) from *pine64.org* (480MB, MD5  *958dce883859ea7dae29ccd460a5996d*)
* [Direct Download Ubuntu 22.04.5 Jimmy Gnome build](http://files.pine64.org/os/Yuzuki/AvaotaOS-jammy-gnome-arm64-avaota-a1.img.xz) from *pine64.org* (1.09GB, MD5  *916a974dbdbcdc21f13860e597a44df2*)
* [Direct Download Ubuntu 22.04.5 Jimmy XFCE build](http://files.pine64.org/os/Yuzuki/AvaotaOS-jammy-xfce-arm64-avaota-a1.img.xz) from *pine64.org* (1.26GB, MD5  *7eac664789ad44b4db1241f6d7d15ffe*)
* [Direct Download Ubuntu 24.04 Noble CLI build](http://files.pine64.org/os/Yuzuki/AvaotaOS-noble-cli-arm64-avaota-a1.img.xz) from *pine64.org* (1.26GB, MD5  *8976d153484c6dfb14434f26c1a15e14*)

# Android 13 Image Build
{{< figure src="/documentation/images/Android_logo_2019_(stacked).svg" width="100" >}}

**Note: "eng" build enable root and log for development or hacking purpose, "user" build disable root and log as release version**

* [Direct Download Eng build](http://files.pine64.org/os/Yuzuki/t527_android13_avaota_a1_uart0_eng.zip ) from *pine64.org* (1.25GB, MD5  *6692b8cd14aeccfed4bbdc148f607135*)
* [Direct Download User build](http://files.pine64.org/os/Yuzuki/t527_android13_avaota_a1_uart0_user.zip) from *pine64.org* (1.22GB, MD5  *cc0227464c7a451b582aba1f3b1944ae*)

# Android 13 SDK

* [Direct Download](http://files.pine64.org/SDK/Yuzuki/android-avaota-a1-1.0.tar.gz) from *pine64.org* (62.28GB, MD5  *f565ff9d0f712ca9c8131c69011379cf*)

## Resources and Articles ##
* [Yuzuki github](https://github.com/YuzukiHD) for more information
* [Yuzuki's Avaota fun site](https://docs.avaota.fun/avaota-sbc/) dedicated to Avaota OS in Chinese