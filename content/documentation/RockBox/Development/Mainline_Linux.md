---
title: "Mainline Linux"
draft: false
menu:
  docs:
    title:
    parent: "RockBox/Development"
    identifier: "RockBox/Development/Mainline_Linux"
    weight: 1
---

Mainline Linux works on the RockBox without patches. To create a compatible u-boot image, https://github.com/mrfixit2001/uboot_builder may be used. The _dtb_ has to be compiled from a recent _dts_, such as [this](https://github.com/mrfixit2001/mainline-kernel/blob/master/arch/arm64/boot/dts/rockchip/rk3328-rockbox.dts), otherwise network and video won’t work.

## Building the dtb

The dtb can be compiled from a recent dts. To do that, download a kernel source and add a dts, or use a kernel source with an fitting dts. The second variant is showcased here:

    git clone https://github.com/mrfixit2001/mainline-kernel.git

Then change the directory to the kernel sources:

    cd mainline-kernel

Then create a config (defaults can be accepted):

    make ARCH=arm64 menuconfig

Now compile the dts files:

    make ARCH=arm64 CROSS_COMPILE=aarch64-linux-gnu- -j 12 dtbs

The compiled dtb file can now be copied from _/arch/arm64/boot/dts/rockchip/rk3328-rockbox.dtb_ into for example the EXTLINUX location.

## Configuring EXTLINUX

In the EXTLINUX location, the _/extlinux/extlinux.conf_ should be pointed to the correct kernel image and the correct dtb file. An example configuration (with serial output with 1500000 baud being enabled for the OS and with the root directory set to the second partition _mmcblk1p2_) can look like the following example:

```
default ROCKBOX

label ROCKBOX
kernel /Image
fdt /rk3328-rockbox.dtb
append console=tty0 console=ttyS2,1500000n8 rw root=/dev/mmcblk1p2 rootwait rootfstype=ext4 panic=10 init=/sbin/init coherent_pool=1M ethaddr=${ethaddr} eth1addr=${eth1addr} serial=${serial#} cgroup_enable=cpuset cgroup_memory=1 cgroup_enable=memory swapaccount=1 video=HDMI-A-1:1920x1080@60 loglevel=3
```
