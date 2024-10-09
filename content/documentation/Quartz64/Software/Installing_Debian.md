---
title: "Installing Debian"
draft: false
menu:
  docs:
    title:
    parent: "Quartz64/Software"
    identifier: "Quartz64/Software/Installing_Debian"
    weight: 
---

It is possible to install Debian onto eMMC of the [Quartz64](/documentation/Quartz64) from the pgewipout quartz64_ci imaged to a Micro SDcard, or vice versa.

This might be useful if you don’t have an eMMC to USB adapter or if the board is inside a case which doesn’t allow eMMC removal.

Download artifacts merge-job:archive from https://gitlab.com/pgwipeout/quartz64_ci/-/pipelines

Unpack zip file

Image to a Micro SDcard present in your PC as /dev/sdX:-

`sudo -i; xzcat images/rk3566-quartz64-a.dtb.img.xz > /dev/sdX`

`sudo sync`

Boot quartz64-a from microSD card

At boot menu select 1 (Buildroot-recovery)

```sh
parted -s /dev/mmcblk1 mklabel gpt

parted -s /dev/mmcblk1 mkpart loader 64s 8MiB

parted -s /dev/mmcblk1 mkpart uboot 8MiB 16MiB

parted -s /dev/mmcblk1 mkpart env 16MiB 32MiB

parted -s /dev/mmcblk1 mkpart efi fat32 32MiB 544MiB

parted -s /dev/mmcblk1 set 4 boot on

parted -s /dev/mmcblk1 mkpart root ext4 544MiB 100%

dd if=/dev/mmcblk0p1 of=/dev/mmcblk1p1

dd if=/dev/mmcblk0p2 of=/dev/mmcblk1p2

dd if=/dev/mmcblk0p3 of=/dev/mmcblk1p3

mkdosfs -F 32 -n "efi" /dev/mmcblk1p4

mke2fs -L "rootfs" /dev/mmcblk1p5

sync

reboot
```

At boot menu select 2 (Debian-Installer)

choose manual partitioning

set partition #5 of mmcbkl1 to be /, format to ext4 and complete the installation

reboot (installer will do this anyway)

```sh
mkdir /mnt/mmcblk0p5

mkdir /mnt/mmcblk1p4

mkdir /mnt/mmcblk1p5

mount /dev/mmcblk0p5 /mnt/mmcblk0p5

mount /dev/mmcblk1p4 /mnt/mmcblk1p4

mount /dev/mmcblk1p5 /mnt/mmcblk1p5

cp -a /mnt/mmcblk0p5/dtbs /mnt/mmcblk1p4/

cp /mnt/mmcblk0p5/vmlinuz /mnt/mmcblk1p4/

mkdir /mnt/mmcblk1p4/extlinux

touch /mnt/mmcblk1p4/extlinux/extlinux.conf

echo 'label Debian on eMMC' >> /mnt/mmcblk1p4/extlinux/extlinux.conf

echo 'linux /vmlinuz' >> /mnt/mmcblk1p4/extlinux/extlinux.conf

echo 'fdt /dtbs/rockchip/rk3566-quartz64-a.dtb' >> /mnt/mmcblk1p4/extlinux/extlinux.conf

echo 'append earlycon=uart8250,mmio32,0xfe660000 console=ttyS2,1500000n8 root=/dev/mmcblk1p5 rootwait' >> /mnt/mmcblk1p4/extlinux/extlinux.conf

cp /mnt/mmcblk0p5/kernel-modules.tar.gz /mnt/mmcblk1p5/root/
```

The following lines (upto adding the boot partition to fstab) are optional. Debian will boot just fine if the boot partition isn’t in fstab and you may prefer to manually mount it when you want to change the kernel:-

`blkid /dev/mmcblk1p4`

The output will show the UUID of your boot partition:-

/dev/mmcblk1p4: LABEL_FATBOOT="efi" LABEL="efi" UUID="5985-9C7B" BLOCK_SIZE="512" TYPE="vfat" PARTLABEL="efi" PARTUUID="93226dfa-53af-4400-8aab-239ff7900dd0"

```sh
echo 'UUID=UUID_from_above /boot    vfat    defaults        0       1' >> /mnt/mmcblk1p5/etc/fstab

chroot /mnt/mmcblk1p5

dpkg -l |grep image
```

To show which kernel images Debian has installed:-

ii  linux-base                    4.6                          all          Linux image base package

ii  linux-image-4.19.0-18-arm64   4.19.208-1                   arm64        Linux 4.19 for 64-bit ARMv8 machines (signed)

ii  linux-image-arm64             4.19+105+deb10u13            arm64        Linux for 64-bit ARMv8 machines (meta-package)

Uninstall them:-

```sh
dpkg -P linux-image-4.19.0-18-arm64 linux-image-arm64

cd /root

tar -xzvf kernel-modules.tar.gz

mv lib/modules /lib/

exit

halt
```

Remove MicroSD card and boot into eMMC.
