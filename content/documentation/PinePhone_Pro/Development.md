---
title: "Development"
draft: false
menu:
  docs:
    title:
    parent: "PinePhone_Pro"
    identifier: "PinePhone_Pro/Development"
    weight: 98
aliases:
  - /documentation/PinePhone_Pro/Various/Development/
---

This page documents development processes and provides links to resources to help prospective contributors get started. For an overview of the current software state see [software state](/documentation/PinePhone_Pro/Software/Software_state/).

## Upstreaming status

| Function | Status | Component | Notes |
| --- | --- | --- | --- |
| Bootloader (u-boot) | Working. Not upstreamed. |  | https://github.com/dreemurrs-embedded/Pine64-Arch/tree/master/PKGBUILDS/pine64/uboot-pinephonepro uses https://git.sr.ht/~martijnbraam/u-boot. |
| Modem | Working. Not upstreamed. |  | Support in https://gitlab.com/mobian1/devices/eg25-manager and Megi’s kernel. |

## Levinboot-based kernel development image

This guide will help you get a comfortable environment for testing your kernel builds on Pinephone Pro. It assumes you either already know how to build or cross-build a Linux kernel for arm64, or if you have a way to get a pre-built kernel from somewhere. For a quick test that your setup works, you can use [megi’s pre-built kernels](https://xff.cz/kernels/).

Quick and easy way to get started with kernel development and testing is to use CrystalGamma’s Levinboot patched with support for Pinephone Pro and 3-option boot selection using volume keys. [You will be able to switch between kernels quickly without swapping uSD cards, which is necessary for painless kernel development experience.](https://xnux.eu/log/#049)

1) Create a following partitioning scheme on a uSD card using `sfdisk`:

```
label: gpt
first-lba: 64
table-length: 8

start=64, size=8128, type=D7B1F817-AA75-2F4F-830D-84818A145370, name="sd-lboot"
size=60M, type=E5AB07A0-8E5E-46F6-9CE8-41A518929B7C, name="sd-lpayload1"
size=60M, type=5f04b556-c920-4b6d-bd77-804efe6fae01, name="sd-lpayload2"
size=60M, type=c195cc59-d766-4b78-813f-a0e1519099d8, name="sd-lpayload3"
size=14G name="sd-rootfs1"
name="sd-rootfs2"
```

This can either be done interactively, or by saving the above to a file, like `format.txt`, and running `sfdisk /dev/<sdcard> < format.txt`

2) Write Levinboot to `sd-lboot` partition using `dd`. You can get a pre-built and tested version [here](https://xff.cz/kernels/pinephone-pro/) There are two options `levinboot-sd.img` and `levinboot-emmc.img` you can use either one of them for your `sd-lboot` partition. They differ in where they load the payloads from (either from SD or eMMC) and not in where they can be flashed to. For uSD card only workflow, you’ll want `levinboot-sd.img`.

3) Prepare payloads for Levinboot and copy them to appropriate partitions. Partition `sd-lpayload1` is used by default, `sd-lpayload2` when you hold a volume down key during powerup, and `sd-lpayload3` when you hold the volume up key.

Preparing a payload involves getting a TF-A `bl31.elf` build, kernel `Image` build, `DTB` file for Pinephone Pro, and optionally an initramfs archive, modifying DTB to include kernel boot arguments, and compressing these using `lz4` in specific order, as shown below.

```
BOOTOPTS=(
        console=tty1

    earlycon=uart8250,mmio32,0xff1a0000
    console=ttyS2,1500000n8

    root=PARTLABEL=emmc-rootfs1
    rootfstype=f2fs
    rootflags=fastboot
    rootwait
    rw

    loglevel=7
)

BOOTOPTS="${BOOTOPTS[@]}"
ALGO="lz4 -zc"

cp -f rk3399-pinephone-pro.dtb board-cfg.dtb
fdtput -pt s board-cfg.dtb /chosen bootargs "$BOOTOPTS"

(
        $ALGO bl31.elf
        $ALGO board-cfg.dtb
        $ALGO Image
.       $ALGO initramfs.img
) > payload.img

dd if=payload.img of=/dev/disk/by-partlabel/sd-lpayload1 bs=4M oflag=direct
```

4) Prepare root filesystem. You can use any Linux distribution for aarch64 for development. For example if you want to use Arch Linux ARM, you would need to format the `sd-rootfs1` partition with `f2fs` filesystem and extract the Arch Linux ARM rootfs tarball there. That will give you a bootable SD card image for Pinephone Pro.

5) Repeat steps 3 and 4 if you want either more kernel payloads, or more Linux distributions on the same uSD card. I recommend having at least some module-less working kernel in `sd-payload3` and perhaps a small userspace in `sd-rootfs1` with a pre-configured WiFi connection, that will allow you to always quickly recover if your development kernel fails to boot, just by pressing volume up key during boot and updating the the kernel in one of the primary payload partitions over WiFi.

## Resources

* See [megi’s PinePhone Development Log](https://xnux.eu/log/)
