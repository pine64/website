---
title: "Releases"
draft: false
menu:
  docs:
    title:
    parent: "PINE_H64_Model_B/Software"
    identifier: "PINE_H64_Model_B/Software/Releases"
    weight: 2
---

The following releases are for the PINE H64 Model B

## Linux

### Armbian

{{< figure src="/documentation/images/armbian.png" width="100" >}}

**Armbian** is a Linux distribution designed for ARM boards. They are usually Debian or Ubuntu flavored.

Download:

* https://www.armbian.com/pine-h64-b/

### Manjaro ARM

{{< figure src="/documentation/images/Manjaro-logo.svg" width="100" >}}

**Manjaro** is a user-friendly Linux distribution based on the independently developed Arch operating system. To learn more about Manjaro please visit the [Manjaro Forum](https://forum.manjaro.org/tags/manjaroarm).
Download:

* [Manjaro ARM PINE H64 GitHub](https://github.com/manjaro-arm/pine-h64-images/releases)

### DietPi

{{< figure src="/documentation/images/dietpi.png" width="100" >}}

**DietPi** is a lightweight yet easy to setup and feature-rich Linux distribution, based on Debian. To find out more about DietPi, please visit the [official documentation](https://dietpi.com/docs/). Discuss the PINE H64 build on the [PINE64 forum thread](https://forum.pine64.org/showthread.php?tid=12531).

Download:

* [Debian 11 Bullseye](https://dietpi.com/downloads/images/DietPi_PINEH64-ARMv8-Bullseye.img.xz) (supports the microSD card and eMMC, 4GB or more)
* [Debian 12 Bookworm](https://dietpi.com/downloads/images/DietPi_PINEH64-ARMv8-Bookworm.img.xz) (supports the microSD card and eMMC, 4GB or more)

| Default credentials | |
| -------- | ------- |
| `root` | `dietpi` |

### LibreELEC

{{< figure src="/documentation/images/libreelec.jpg" width="100" >}}

**LibreELEC** is a "Just enough OS" Linux distribution combining the Kodi media center with an operating system.

Download:

* [Daily builds](https://test.libreelec.tv/) (look for look for _LibreELEC-H6.arm-xxx-nightly-xxxxxxxx-xxxxxxx-pine-h64-model-b.img.gz_]

Notes:

* Supports microSD card and eMMC boot

## BSD

### FreeBSD

{{< figure src="/documentation/images/FreeBSD.jpeg" width="100" >}}

**FreeBSD** is an operating system used to power modern servers, desktops, and embedded platforms. To learn more about FreeBSD, please visit [FreeBSD main page](https://www.FreeBSD.org/).

Instructions:

* See general information about [FreeBSD on Allwinner ARM](https://wiki.freebsd.org/arm/Allwinner) and specific details about [creating a microSD card for the PINE H64](https://wiki.freebsd.org/arm/Allwinner/H6)

Notes:

* FreeBSD supports booting from the microSD card

### NetBSD

{{< figure src="/documentation/images/netbsd.png" width="100" >}}

**NetBSD** is a free, fast, secure, and highly portable Unix-like Open Source operating system. To learn more about NetBSD please visit [NetBSD main page](https://www.netbsd.org/).

Download:

* [Direct download latest release build from NetBSD by select PINE H64](http://www.armbsd.org/)

Notes:

* NetBSD supports booting from the microSD card
* Instructions concerning enabling SSH can be found [here](https://www.netbsd.org/docs/guide/en/chap-boot.html#chap-boot-ssh)

| Default credentials | |
| -------- | ------- |
| `root` (root user and SSH) | `[none]` |
