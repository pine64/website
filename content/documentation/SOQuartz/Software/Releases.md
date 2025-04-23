---
title: "Releases"
draft: false
menu:
  docs:
    title:
    parent: "SOQuartz/Software"
    identifier: "SOQuartz/Software/Releases"
    weight: 1
aliases:
  - /wiki/SOQuartz_Software_Releases
---

{{< admonition type="note" >}}
 The images are provided by the PINE64 community, not by Pine Store Ltd. Most community projects currently aim at getting mainline Linux running on the board, not some vendor provided kernel that will never be receiving updates. A mainline-first approach allows for the boards to continue receiving important updates, such as security updates, for years to come, as well as have higher quality code in the kernel as it underwent independent review, but does mean that not all aspects of the hardware work right out of the gate.
{{< /admonition >}}

## DietPi

{{< figure src="/documentation/images/dietpi.png" width="100" >}}

***DietPi*** is a lightweight, yet easy to setup and feature-rich Linux distribution, based on _Debian_. To find out more about DietPi, please visit the [official documentation](https://dietpi.com/docs/). Discuss the Quartz64 builds on the [PINE64 forum thread](https://forum.pine64.org/showthread.php?tid=17601).

Download:

* [Direct download from dietpi.com](https://dietpi.com/downloads/images/DietPi_SOQuartz-ARMv8-Bookworm.img.xz)

| Default credentials | |
| -------- | ------- |
| Root user | `root/dietpi` |

## Manjaro ARM

{{< figure src="/documentation/images/Manjaro-logo.svg" width="100" >}}

Manjaro ARM is a user friendly rolling release distribution, based on Arch Linux ARM.

* [Images for SOQuartz on GitHub](https://github.com/manjaro-arm/soquartz-cm4-images/releases)

WiFI, Bluetooth, Ethernet, HDMI USB etc. works, others are not tested. 

Currently the image is built for Raspberry Pi CM4 - IO board, so to get it working with other base board like pine64 Soquartz model A base board then follow this steps:

* Flash the image to a SD card/ EMMC.
* Go to Boot partition.
* Then change the DTB listed in /boot/extlinux/extlinux.conf to -model-a.dtb instead of -cm4.dtb.
* Now put the SD card/ EMMC to the preferred base board and boot.
* First boot will take time as the user partition will resize to take whole storage size.

For headless installation, simply enter "root" at the login: prompt and complete setup.

## Plebian

{{< figure src="/documentation/images/Plebian-logo.svg" width="100" >}}

Plebian stands for ***P****INE64 **L****ive D****ebian*** and aims to be a fairly vanilla live Debian image for Quartz64 and SOQuartz devices, based on Debian Bookworm. It supports both of PINE64’s officially released SOQuartz base boards.

* [Download Release Images](https://github.com/Plebian-Linux/quartz64-images/releases)
* [Read The Instructions](https://github.com/Plebian-Linux/quartz64-images/blob/main/RUNNING.md)
* [Visit plebian.org to learn more](https://plebian.org/)

To flash, run (replace `/dev/sdX` with your target block device):

```console
$ xzcat imagename.img.xz | sudo dd of=/dev/sdX bs=4M oflag=dsync status=progress
```

Check [Plebian’s flashing instructions](https://plebian.org/flashing/) for instructions on how to flash from e.g. Windows.

Some quick notes:

* You will be asked to change your password on first login (for what the default login is, read the instructions!)
* Root file system is grown to take up the entire space of your boot device
* NetworkManager is used instead of Debian’s interfaces config to be more flexible with what adapters are plugged in and working
* An sshd is started on port 22 with freshly generated keys
* Please flash the correct image for your SOQuartz baseboard!
