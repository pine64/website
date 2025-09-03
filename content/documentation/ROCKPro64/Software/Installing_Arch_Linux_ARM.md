---
title: "Installing Arch Linux ARM"
draft: false
menu:
  docs:
    title:
    parent: "ROCKPro64/Software"
    identifier: "ROCKPro64/Software/Installing_Arch_Linux_ARM"
    weight:
aliases:
  - /wiki/ROCKPro64_Installing_Arch_Linux_ARM
---

{{< admonition type="warning" >}}
 This page is a work in progress, use at your own risk
{{</ admonition >}}

Commands to be run as a normal user are prefixed with `$`, commands to be run as root are prefixed with `#`. We assume your target device is ***/dev/sdX***, adjust accordingly.

## Obtaining and Building U-Boot And TF-A

The first step is to compile the open firmware (TF-A) and the open bootloader (u-boot).

Clone u-boot git repository:

```console
$ git clone https://source.denx.de/u-boot/u-boot.git
```

Clone TF-A git repository:

```console
$ git clone https://github.com/ARM-software/arm-trusted-firmware.git
```

Build TF-A (you will need ***aarch64-linux-gnu-gcc*** and ***arm-none-eabi-gcc*** for this)

```console
$ cd arm-trusted-firmware
$ make realclean
$ make CROSS_COMPILE=aarch64-linux-gnu- PLAT=rk3399
```

Next, export the path to your compiled BL31 in the shell you’ll build u-boot in. Adjust the path as necessary.

```console
$ export BL3/path/to/arm-trusted-firmware/build/rk3399/release/bl31/bl31.elf
```

Build U-Boot (you may need to install additional packages to successfully compile, such as `bc`, `python-pyelftools`, or `swig`):

```console
$ make mrproper
$ make rockpro64-rk3399_defconfig
$ make CROSS_COMPILE=aarch64-linux-gnu- -j$(nproc)
```

## Preparing The Block Device

Here we assume your block device is ***/dev/sdX***, adjust as needed.

Create a new partition table:

```console
# parted -s /dev/sdX mklabel gpt
```

Create the partitions for loader and u-boot:

```console
# parted -s /dev/sdX mkpart loader 64s 8MiB
# parted -s /dev/sdX mkpart uboot 8MiB 16MiB
```

Create the partition for u-boot’s environment (optional, but you’ll have to adjust the following offsets if you don’t do it):

```console
# parted -s /dev/sdX mkpart env 16MiB 32MiB
```

Create the "efi" boot partition and mark it as bootable:

```console
# parted -s /dev/sdX mkpart efi fat32 32MiB 544MiB
# parted -s /dev/sdX set 4 boot on
```

Create the root partition:

```console
# parted -s /dev/sdX mkpart root ext4 544MiB 100%
```

### Creating The File Systems

Now create the file systems for boot and root:

```console
# mkfs.vfat -n "efi" /dev/sdX4
# mkfs.ext4 -L "rootfs" /dev/sdX5
```

### Flashing U-Boot

Flash idbloader.img and uboot.img:

```console
# dd if=idbloader.img of=/dev/sdX1
# dd if=u-boot.itb of=/dev/sdX2
```

## Fetching The Root File System Tarball

Fetch the root filesystem tarball and the PGP signature

```console
$ wget -N http://os.archlinuxarm.org/os/ArchLinuxARM-aarch64-latest.tar.gz{,.sig}
```

Fetch the gpg keys:

```console
$ curl 'https://keyserver.ubuntu.com/pks/lookup?op=get&search=0x68b3537f39a313b3e574d06777193f152bdbe6a6' | gpg --import=-
```

Compare the key ID provided in the above command with the one listed here: https://archlinuxarm.org/about/package-signing (Take good note of the domain and HTTPS)

Verify the tarball’s authenticity

```console
$ gpg --verify ArchLinuxARM-aarch64-latest.tar.gz.sig
```

{{< admonition type="important" >}}
 Do not skip verifying the authenticity. This is important. It also protects you from prematurely aborted transfers giving you a corrupt archive.
{{</ admonition >}}

## Installing The Root File System

```console
# mount /dev/sdX5 /mnt/alarm-root
# mkdir /mnt/alarm-root/boot
# mount /dev/sdX4 /mnt/alarm-root/boot
# bsdtar -xpf ArchLinuxARM-aarch64-latest.tar.gz -C /mnt/alarm-root
```

### Editing fstab

Find your partition UUIDs for both partitions using `lsblk`:

```console
$ lsblk -o NAME,SIZE,MOUNTPOINTS,PARTUUID
```

In ***/mnt/alarm-root/etc/fstab***, put the lines

```
PARTUUID=_root-uuid-here_  /       ext4    defaults        0       1
PARTUUID=_boot-uuid-here_  /boot   vfat    defaults        0       2
```

with your UUIDs in place of the placeholder.

### Writing extlinux.conf

Create a ***/mnt/alarm-root/boot/extlinux/extlinux.conf*** with these contents:

```
default l0
menu title ROCKPro64 Boot Menu
prompt 0
timeout 50

label l0
menu label Boot Arch Kernel
linux /Image
fdt /dtbs/rockchip/rk3399-rockpro64.dtb
append initrd=/initramfs-linux.img earlycon=uart8250,mmio32,0xff1a0000 console=ttyS2,1500000n8 root=LABEL=rootfs rw rootwait
```

Once done, unmount the partitions:

```console
# umount /mnt/alarm-root/boot
# umount /mnt/alarm-root
```

## Finishing Setup

SSH in as ***root*** with password ***root*** and run

```console
# pacman-key --init
# pacman-key --populate archlinuxarm
```