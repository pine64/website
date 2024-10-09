---
title: "Multi-distribution image"
draft: false
menu:
  docs:
    title:
    parent: "PinePhone_Pro/Software"
    identifier: "PinePhone_Pro/Software/Multi-distribution_image"
    weight: 99
---

This article explains how to install a multiple linux distribution environment on your PinePhone Pro. You can choose to install this environment to the phone’s internal eMMC memory or to a microSD card. These instructions also integrate with the [multi-distribution image](/documentation/PinePhone_Pro/Software/Releases/#multi_distribution_image) releases page section.

## Variables

During the processes of [partitioning](#partitioning) the target device, [building](#building) the image or installing the [bootloader](#u_boot), make sure the variables are properly defined. Each time you open a new terminal window, the values of the variables must be re-set.

<dl><dt><strong>💡 TIP</strong></dt><dd>

_BASE_ is the base directory path on your computer\
_DEV_ is the device name from the lsblk command\
_ATTR_ are the attributes of each partition/distribution\
_SIZE_ is the GiB capacity of each partition/distribution\
_NameUrl_ is the Key:Value of distribution name and relative URL download address
</dd></dl>

This guide has been tested with 6 Linux distributions on a 128 GiB microSD card, and following variables:

```console
$ BASE=ppp-multi-image
$ DEV=sdb # i.e. sdb or mmcblk0
$ ATTR=RequiredPartition,LegacyBIOSBootable
$ SIZE=11GiB

$ declare -A NameUrl
$ NameUrl[uboot]=https://xff.cz/kernels/bootloaders-2024.04/ppp.tar.gz
$ #NameUrl[uboot]=https://megous.com/dl/tmp/ppp.tar.gz # test build
$ NameUrl[arch]=https://github.com/dreemurrs-embedded/Pine64-Arch/releases/download/20240326/archlinux-pinephone-pro-phosh-20240326.img.xz
$ NameUrl[manjaro]=https://github.com/manjaro-pinephone/phosh/releases/download/beta37/Manjaro-ARM-phosh-pinephonepro-beta37.img.xz
$ NameUrl[mobian]=https://images.mobian.org/pinephonepro/weekly/mobian-rockchip-phosh-20240324.img.xz
$ NameUrl[pmos]=https://images.postmarketos.org/bpo/v23.12/pine64-pinephonepro/phosh/20240501-0425/20240501-0425-postmarketOS-v23.12-phosh-22.3-pine64-pinephonepro.img.xz
$ NameUrl[sailfish]=https://gitlab.com/sailfishos-porters-ci/dont_be_evil-ci/-/jobs/artifacts/master/download?job=pinephonepro-rootfs
$ NameUrl[ut]=https://ci.ubports.com/job/focal-hybris-rootfs-arm64/job/master/lastSuccessfulBuild/artifact/ubuntu-touch-pinephone-pro-img-arm64.raw.xz
$ NameUrl[extra]=
```

## Install rk2aw

Make sure your phone has the [rk2aw pre-loader](/documentation/PinePhone_Pro/Software/Bootloaders/#rk2aw) installed to its SPI flash memory. PinePhone Pro models ordered after November 2023 are shipped with rk2aw pre-installed. Otherwise, follow the instructions in this section to install it.

Boot up the PinePhone Pro’s stock operating system and start a shell session. You can do this either by opening the terminal emulator app, or by enabling the SSH service and logging in from a PC on the same network. Then execute the following commands (from the phone’s shell):

```console
$ curl -O https://xff.cz/kernels/bootloaders-2024.04/ppp.tar.gz
$ tar -xvzf ppp.tar.gz
$ cd ppp
$ sudo ./spinor-flash-initial-setup.sh
```

<dl><dt><strong>💡 TIP</strong></dt><dd>

The multi-boot image _can_ function without rk2aw, but you will need to make sure the correct [bootloader](#uboot) is started by your phone’s SoC.

If you are installing to a microSD card, then either:

1. Ensure that the phone’s SPI flash and eMMC are empty, or
2. Hold down the _RE_ button during boot to force the phone to boot from the microSD card by disabling the SPI flash and the eMMC.

If you are installing to the eMMC, make sure the SPI flash is empty.
</dd></dl>

Further instructions can be found on the [author’s website](https://xff.cz/kernels/bootloaders-2024.04/ppp/rk2aw/INSTALL).

## Expose the device

Connect your PinePhone Pro to a Linux computer, with the stock USB cable. Press power button on. From the graphical menu select _eMMC over USB_ or _SD over USB_ to expose the device to your computer. You can optionally flash microSD directly into your computer’s slot, if available.

## Erasing

Make sure there are no signatures or partitions left, and overwrite the first sectors with zeroes. You can find the target device under `lsblk` command.

```console
$ sudo wipefs /dev/$DEV
$ sudo wipefs --all --force /dev/$DEV*
$ sudo dd if=/dev/zero of=/dev/$DEV status=progress bs=32768 count=1
```

Optionally you can zeroes the whole device:

```console
$ sudo dd if=/dev/zero of=/dev/$DEV status=progress bs=32768 count=$(expr $(lsblk -bno SIZE /dev/$DEV | head -1) \/ 32768)
```

## Partitioning

Partition the device for the multiple distributions:

```shell
$ sudo sfdisk /dev/$DEV --wipe always <<EOF
label: gpt
first-lba: 64
table-length: 10
attrs=RequiredPartition, type=D7B1F817-AA75-2F4F-830D-84818A145370, start=64, size=32704 name="uboot_raw"
$(
for name in "${!NameUrl[@]}"; do
  case ${name} in (uboot|extra) continue ;; esac
  printf '%s\n' "attrs=\"$ATTR\", size=$SIZE, name=\"$BASE-${name}\""
done | sort
)
attrs="$ATTR", size=$SIZE, name="$BASE-ut-data"
attrs="$ATTR", size=+, name="extra"
EOF
```

Returned string:

```
sudo sfdisk /dev/$DEV --wipe always <<EOF
label: gpt
first-lba: 64
table-length: 10
attrs=RequiredPartition, type=D7B1F817-AA75-2F4F-830D-84818A145370, start=64, size=32704 name="uboot_raw"
attrs="RequiredPartition,LegacyBIOSBootable", size=11GiB, name="ppp-multi-image-arch"
attrs="RequiredPartition,LegacyBIOSBootable", size=11GiB, name="ppp-multi-image-manjaro"
attrs="RequiredPartition,LegacyBIOSBootable", size=11GiB, name="ppp-multi-image-mobian"
attrs="RequiredPartition,LegacyBIOSBootable", size=11GiB, name="ppp-multi-image-pmos"
attrs="RequiredPartition,LegacyBIOSBootable", size=11GiB, name="ppp-multi-image-sailfish"
attrs="RequiredPartition,LegacyBIOSBootable", size=11GiB, name="ppp-multi-image-ut"
attrs="RequiredPartition,LegacyBIOSBootable", size=11GiB, name="ppp-multi-image-ut-data"
attrs="RequiredPartition,LegacyBIOSBootable", size=+, name="extra"
EOF
```

Expected results:

```
Checking that no-one is using this disk right now ... OK
Disk /dev/sd[...]: 118.16 GiB, 126877696000 bytes, 247808000 sectors
Disk model: microSD card Reader  
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
>>> Script header accepted.
New situation:
Disklabel type: gpt
Disk identifier: A012E9D0-B4EB-4677-926F-D93AE4C696FA
 Device    Start       End  Sectors   Size Type
 sdb1         64     32767     32704   16M unknown
 sdb2      32768  23101439  23068672   11G Linux fs
 sdb3   23101440  46170111  23068672   11G Linux fs
 sdb4   46170112  69238783  23068672   11G Linux fs
 sdb5   69238784  92307455  23068672   11G Linux fs
 sdb6   92307456 115376127  23068672   11G Linux fs
 sdb7  115376128 138444799  23068672   11G Linux fs
 sdb8  138444800 161513471  23068672   11G Linux fs
 sdb9  161513472 247805951 86292480  41.1G Linux fs
The partition table has been altered.
Calling ioctl() to re-read partition table.
Syncing disks.
```

## Install U-Boot

In order to display the graphical distribution selector when the phone boots, we need to install a custom version of the U-Boot bootloader.

First, use the following commands to download the required U-Boot image. Note that we are downloading the same _ppp.tar.gz_ archive as we did in the [rk2aw section](#rk2aw); if you already have a copy of this archive on your computer, you may skip the download and simply extract its contents into `~/$BASE/downloads/`.

```console
$ NAME=uboot
$ mkdir -p ~/$BASE/downloads && cd ~/$BASE/downloads
$ wget ${NameUrl[$NAME]}
$ tar -xvzf $(basename "${NameUrl[$NAME]}")
```

Then, use the following command to install the U-Boot image to the correct location on the microSD/eMMC:

```console
$ sudo dd if=ppp/foss/u-boot-rockchip.bin of=/dev/$DEV bs=512 seek=64 status=progress conv=fsync
```

<dl><dt><strong>💡 TIP</strong></dt><dd>

If you are interested in building this U-Boot image yourself, you can download the source code from [xff.cz](https://xff.cz/git/u-boot/tree/?h=ppp-2023.07). However, you will still need a copy of _ppp.tar.gz_ since it contains the U-Boot build configuration file (`ppp/foss/.config`).

Copy this file to the root of your U-Boot source directory, keeping the name `.config`. You can then use `make` to initiate the build process.
</dd></dl>

## Build the partitions

Make sure you download an updated file from [relases page](/documentation/PinePhone_Pro/Software/Releases). You will need to build each partition one by one, setting properly the [variables](#variables) and using specific commands according the selected distribution. When you reach the [building repeat advice](#building_repeat), come back to this point and build the next distribution.

### Arch, Manjaro, Mobian, postmarketOS

For these distributions, download and decompress the image:

```console
$ NAME=arch # set distribution name, i.e. arch, manjaro, mobian, pmos
$ mkdir -p ~/$BASE/downloads && cd ~/$BASE/downloads
$ wget ${NameUrl[$NAME]}
$ xz -v -d -k $(basename "${NameUrl[$NAME]}")
$ mv $(basename -as .xz "${NameUrl[$NAME]}") $NAME.img
```

Mount the image:

```console
$ cd ~/$BASE/downloads
$ sudo losetup -P /dev/loop0 $NAME.img
$ sudo mkdir -p /mnt/$NAME/boot /mnt/$NAME/root /mnt/$NAME/dev
$ sudo mount /dev/loop0p1 /mnt/$NAME/boot/
$ sudo mount /dev/loop0p2 /mnt/$NAME/root/
```

Copy `root` and `boot` contents:

```console
$ sudo dd if=/dev/loop0p2 of=/dev/disk/by-partlabel/$BASE-$NAME bs=1M status=progress conv=fsync
$ sudo mount /dev/disk/by-partlabel/$BASE-$NAME /mnt/$NAME/dev/
$ sudo scp -r /mnt/$NAME/boot/* /mnt/$NAME/dev/boot
```

### SailfishOS

This distribution needs different commands. Download and decompress the image:

```console
$ NAME=sailfish
$ mkdir -p ~/$BASE/downloads && cd ~/$BASE/downloads
$ wget ${NameUrl[$NAME]} -O artifacts.zip
$ unzip artifacts.zip
$ mv pinephonepro/*/*.tar.bz2 sailfish.tar.bz2
$ mkdir -p ~/$BASE/downloads/sailfishos
$ sudo tar -xvf sailfish.tar.bz2 -C sailfishos/ > /dev/null
```

Format the partition and copy the extracted files directly onto the device:

```console
$ sudo mkfs.ext4 -F /dev/disk/by-partlabel/$BASE-$NAME
$ sudo mkdir -p /mnt/$NAME/dev
$ sudo mount /dev/disk/by-partlabel/$BASE-$NAME /mnt/$NAME/dev
$ sudo rsync -avz --progress ~/$BASE/downloads/sailfishos/ /mnt/$NAME/dev
$ sudo chmod a=rwx /mnt/$NAME/dev/boot/*
```

### Ubuntu Touch

For this distribution, download and decompress the image:

```console
$ NAME=ut
$ mkdir -p ~/$BASE/downloads && cd ~/$BASE/downloads
$ wget ${NameUrl[$NAME]}
$ xz -v -d -k $(basename "${NameUrl[$NAME]}")
$ mv $(basename -as .xz "${NameUrl[$NAME]}") $NAME.img
```

Mount the image:

```console
$ cd ~/$BASE/downloads
$ sudo losetup -P /dev/loop0 $NAME.img
$ sudo mkdir -p /mnt/$NAME/boot /mnt/$NAME/system /mnt/$NAME/userdata /mnt/$NAME/dev
$ sudo mount /dev/loop0p2 /mnt/$NAME/boot/
$ sudo mount /dev/loop0p3 /mnt/$NAME/system/
$ #sudo mount /dev/loop0p4 /mnt/$NAME/userdata/
```

Create the `userdata` partition and copy `system` and `boot` contents:

```console
$ sudo mkfs.ext4 -F /dev/disk/by-partlabel/$BASE-$NAME-data
$ sudo e2label /dev/disk/by-partlabel/$BASE-$NAME-data $NAME-data
$ sudo dd if=/dev/loop0p3 of=/dev/disk/by-partlabel/$BASE-$NAME bs=1M status=progress conv=fsync
$ sudo mount /dev/disk/by-partlabel/$BASE-$NAME /mnt/$NAME/dev/
$ sudo scp -r /mnt/$NAME/boot/* /mnt/$NAME/dev/boot
```

### All distributions

If present, you can optionally backup _boot.scr_, _extlinux.conf_ and _fstab_ files.

```console
$ sudo mkdir -p /mnt/$NAME/dev/boot/extlinux
$ [ ! -f /mnt/$NAME/dev/boot/extlinux/extlinux.conf ] || sudo mv /mnt/$NAME/dev/boot/extlinux/extlinux.conf /mnt/$NAME/dev/boot/extlinux/extlinux.conf.bk
$ [ ! -f /mnt/$NAME/dev/boot/boot.scr ] || sudo mv /mnt/$NAME/dev/boot/boot.scr /mnt/$NAME/dev/boot/boot.scr.bk
$ [ ! -f /mnt/$NAME/dev/boot/boot.pinephonepro.scr ] || sudo mv /mnt/$NAME/dev/boot/boot.pinephonepro.scr /mnt/$NAME/dev/boot/boot.pinephonepro.scr.bk
$ sudo mv /mnt/$NAME/dev/etc/fstab /mnt/$NAME/dev/etc/fstab.bk
```

Then write the new _/boot/extlinux/extlinux.conf_ file, making sure you remove `#` comment for the selected distributions:

```shell
$ sudo tee /mnt/$NAME/dev/boot/extlinux/extlinux.conf <<EOF
## /boot/extlinux/extlinux.conf
menu title Pinephone Pro Boot Menu

## uncomment next line for timed default-selected distro
#default $NAME

timeout 50
label $NAME
menu label $NAME

## uncomment next 3 lines for ARCH
#fdt    /boot/dtbs/rockchip/rk3399-pinephone-pro.dtb
#initrd /boot/initramfs-linux.img
#kernel /boot/Image.gz

## uncomment next 3 lines for MANJARO
#fdt    /boot/dtbs/rockchip/rk3399-pinephone-pro.dtb
#initrd /boot/initramfs-linux.img
#kernel /boot/Image

## uncomment next 3 lines for MOBIAN
#fdtdir /boot/dtb-6.6-rockchip/
#initrd /boot/initrd.img-6.6-rockchip
#linux  /boot/vmlinuz-6.6-rockchip

## uncomment next 3 lines for PMOS
#fdtdir /boot/dtbs-pine64-pinephonepro/
#initrd /boot/initramfs-extra
#linux  /boot/vmlinuz

## uncomment next 2 lines for SAILFISH
#fdt    /boot/rockchip/rk3399-pinephone-pro.dtb
#kernel /boot/Image

## uncomment next 3 lines for UT
#fdtdir /boot/dtb-6.5.0-okpine-ut/
#initrd /boot/initrd.img-6.5.0-okpine-ut
#linux  /boot/vmlinuz-6.5.0-okpine-ut

## uncomment next line for all distros, excluding UT
#append root=PARTLABEL=$BASE-$NAME console=ttyS2,115200 console=tty0 loglevel=7 rw rootwait

## uncomment next line for UT only
#append root=PARTLABEL=$BASE-$NAME console=ttyS2,115200 console=tty loglevel=7 systempart=/dev/disk/by-partlabel/$BASE-$NAME datapart=/dev/disk/by-partlabel/$BASE-$NAME-data security=apparmor rw rootwait

EOF
```

Then write the new _/etc/fstab_ file, making sure you remove `#` comment for selected distribution:

```shell
$ sudo tee /mnt/$NAME/dev/etc/fstab <<EOF
## <file system> <dir> <type> <options> <dump> <pass>

## uncomment next line for ARCH
#PARTLABEL=$NAME / ext4 rw,relatime 0 1

## uncomment next line for MANJARO
#PARTLABEL=$NAME / ext4 defaults 0 1

## uncomment next line for MOBIAN
#PARTLABEL=$NAME / ext4 defaults,x-systemd.growfs 0 1

## uncomment next line for PMOS
#PARTLABEL=$NAME / ext4 defaults 0 0

## uncomment next 7 lines for SAILFISH
#PARTLABEL=$NAME / ext4     rw,noatime          0 1
#devtmpfs /dev     devtmpfs nosuid              0 0
#devpts   /dev/pts devpts   gid=5,mode=620      0 0
#tmpfs    /dev/shm tmpfs    noexec,nosuid,nodev 0 0
#proc     /proc    proc     defaults            0 0
#sysfs    /sys     sysfs    defaults            0 0
#tmpfs    /tmp     tmpfs    nosuid,nodev        0 0

## uncomment next 3 lines for UT
#PARTLABEL=$NAME      /         ext4 defaults 0 1
#PARTLABEL=$NAME      /boot     ext4 defaults 0 2
#PARTLABEL=$NAME-data /userdata ext4 defaults 0 2

EOF
```

Close any mounted directory window.

### Unmount, detach and resize

To unmount and deatch all building images, run:

```console
$ sudo umount /mnt/$NAME/*
$ sudo rm -r /mnt/$NAME
$ sudo losetup -D
```

On the first boot, if it doesn’t happen automatically, you can manually resize each image to fill the entire partition using GParted GUI software or using the CLI. Please note that SailfishOS doesn’t need any resizing.

```console
$ sudo e2label /dev/disk/by-partlabel/$BASE-$NAME $NAME
$ sudo e2fsck -f /dev/disk/by-partlabel/$BASE-$NAME
$ sudo resize2fs /dev/disk/by-partlabel/$BASE-$NAME
```

<a name="building_repeat"></a>{{< admonition type="important" >}}
 Repeat the [building process](#building) for the next distribution, adapting [needed variables](#variables).
{{< /admonition >}}

## Follow-up notes

Any time a distribution update rebuilds the initramfs it is necessary to delete _/boot/boot.scr_ again to keep the rk2aw menu clean.

In case you want to reinstall only one distribution, the easy way is to delete and recreate the selected partition using the GParted GUI.

If the device doesn’t start, connect a compatible [serial cable](https://pine64.com/product/pinebook-pinephone-pinetab-serial-console) to the headphone jack and a computer, switch off microswitch 6 and start a serial console to investigate further. Find out the corresponding USB device using `ls /dev/ttyUSB*` and then connect to it with for example _minicom_ using the command `minicom -b 1500000 -D /dev/ttyUSB[...]`, where **[...]** is the number of the USB device.

To find the exact _LABEL_, _UUID_, _PARTLABEL_ and _PARTUUID_ names, open a terminal window on the phone and use the command `blkid`.

## Appendix

Build the postmarketOS image

You can optionally use [pmbootstrap](https://wiki.postmarketos.org/wiki/Pmbootstrap) to generate the distribution image on your Linux computer, instead of downloading a pre-made image. Make sure you install pmbootstrap before building the image.

Start creating 2 GB empty image file, format and mount it.

```console
$ sudo su
# dd if=/dev/zero of=postmarketos.img bs=1 count=0 seek=2G status=progress && sync
# mkfs.ext4 postmarketos.img
# losetup -P /dev/loop0 postmarketos.img
# exit
```

Then build the image using _pmbootstrap_

```console
$ pmbootstrap init
$ pmbootstrap status
$ pmbootstrap pull
$ pmbootstrap install --sdcard=/dev/[LOOP-DEVICE]
$ pmbootstrap shutdown
```
