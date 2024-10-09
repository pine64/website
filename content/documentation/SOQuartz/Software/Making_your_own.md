---
title: "Making your own"
draft: false
menu:
  docs:
    title:
    parent: "SOQuartz/Software"
    identifier: "SOQuartz/Software/Making_your_own"
    weight: 
---

Making your own image/installation of Linux for SOQuartz is relatively easy, as all major components are mainlined. You will need:

* A build of mainline U-Boot &ge; v2023.10. Flash this to sector 64 (sector size 512, so byte 32768) of your image for SD or eMMC. It’s prudent to "protect" it by making a small (~16MiB) partition at this offset.
* A [mainline Linux kernel](https://www.kernel.org/) &ge; v6.2. See [Quartz64/Development#Linux Kernel Config Options](/documentation/Quartz64/Development/#linux_kernel_config_options) for the device specific kernel configuration options.
* The root filesystem of the distribution of your choice. This can be on the same filesystem as your kernel and device tree if using _extlinux.conf_.

You can either boot the kernel through U-Boot’s EFI booting, in which case it gets its device tree from U-Boot, or mark the partition containing your kernel and device tree with the legacy bootable flag and write an _extlinux/extlinux.conf_ as explained in the [U-Boot documentation](https://u-boot.readthedocs.io/en/latest/develop/distro.html#boot-configuration-files).
