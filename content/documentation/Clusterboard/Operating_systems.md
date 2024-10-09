---
title: "Operating systems"
draft: false
menu:
  docs:
    title:
    parent: "Clusterboard"
    identifier: "Clusterboard/Operating_systems"
    weight: 2
---

## Armbian

To get the cluster running, start off with a basic [Armbian SOPINE](https://www.armbian.com/sopine-a64/) install on the first module or directly on all the modules. Armbian offers Debian and Ubuntu as options for download.

There is an issue recognizing the network that needs you to make a change to the base image described [here](https://forum.pine64.org/showthread.php?tid=10432), and a PXE issue. If you have a good description, please add it here. The network issue has been resolved in Armbian builds post December 2020 - [as described here](https://github.com/armbian/build/pull/2396).

As of February 2021 the current armbian image is not working (see the post on the [arbian forum](https://forum.armbian.com/topic/17333-unable-to-boot-focal-or-buster-images-on-sopine-clusterboard)). The latest working version is [21.02.1](https://armbian.systemonachip.net/archive/pine64so/archive/Armbian_21.02.1_Pine64so_buster_current_5.10.12.img.xz). To update the system, the package 'linux-dtb-current-sunxi64' needs to be held back by running

`echo "linux-dtb-current-sunxi64 hold" | sudo dpkg --set-selections`

There are a number of possible basic installation methods.

* Full install on each module’s mSD card.
* eMMC install on the first module.
* PXE boot for all modules, from the first module, or an external host.

## Others

The current version of NetBSD may have the networking issue solved in Armbian, as described above.
