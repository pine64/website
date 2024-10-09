---
title: "Ways to do things"
draft: false
menu:
  docs:
    title:
    parent: "QuartzPro64"
    identifier: "QuartzPro64/Ways_to_do_things"
    weight: 6
---

## Using rkdeveloptool

Use the [PINE64 fork of rkdeveloptool](https://gitlab.com/pine64-org/quartz-bsp/rkdeveloptool).

Connect a USB-C cable to the "DEBUG PORT" USB-C port, and a second to the "DOWNLOAD" USB-C port. Cable direction for the latter matters, so if it doesn’t show up after entering download mode, try rotating the USB-C connector to the other side.

To enter rockusb mode, interrupt the boot by holding the "V+/REC" on-board button or mashing Ctrl+C very quickly on the serial comms, then type `download`.

```console
$ rkdeveloptool list
```

should now show you the device somewhat like this:

    *$ rkdeveloptool list*
    DevNo=1 Vid=0x2207,Pid=0x350b,LocationID=204    Loader

{{< admonition type="important" >}}
 **Note:** If you receive an error about being unable to create the comms object in the following steps, make sure you have the udev rules installed with [CounterPillow’s RK3588 device id patch](https://gitlab.com/pine64-org/quartz-bsp/rkdeveloptool/-/merge_requests/19), install them to `/etc/udev/rules.d/` and `udevadm control --reload`
{{< /admonition >}}

Now, we can e.g. show the partitions on the eMMC:

    *$ rkdeveloptool list-partitions*
    #   LBA start (sectors)  LBA end (sectors)  Size (bytes)       Name             
    00                 8192              16383       4194304       security
    01                16384              24575       4194304       uboot
    02                24576              32767       4194304       trust
    03                32768              40959       4194304       misc
    04                40960              49151       4194304       dtbo
    05                49152              51199       1048576       vbmeta
    06                51200             133119      41943040       boot
    07               133120             329727     100663296       recovery
    08               329728            1116159     402653184       backup
    09              1116160            1902591     402653184       cache
    10              1902592            1935359      16777216       metadata
    11              1935360            1937407       1048576       baseparameter
    12              1937408            8310783    3263168512       super
    13              8310784          120831935   57610829824       userdata

You can now use `rkdeveloptool write-partition partitionname yourfile` to overwrite one of the eMMC partitions.

## U-Boot and kernel on SD, RootFS on eMMC

This is the setup User:CounterPillow currently uses. In short, you’ll need a vendor U-Boot on your SD card, with a boot partition on it that contains your ***extlinux.conf***, device tree and kernel.

### Setting up the SD card

Assuming your SD card is ***/dev/sdX***, partition as e.g. follows:

    # parted -s /dev/sdX mklabel gpt
    # parted -s /dev/sdX mkpart loader 64s 8MiB
    # parted -s /dev/sdX mkpart uboot 8MiB 16MiB
    # parted -s /dev/sdX mkpart env 16MiB 32MiB
    # parted -s /dev/sdX mkpart efi fat32 32MiB 544MiB    # increase size as you wish
    # parted -s /dev/sdX set 4 boot on

Flash SPL and u-boot:

    # dd if=rk3588_spl_loader_v1.06.109.bin of=/dev/sdX1
    # dd if=uboot.img of=/dev/sdX2

Then make the filesystem:

    # mkfs.vfat -n "efi" /dev/sdX4

Mount it to e.g. ***/mnt/sdcardboot***:

    # mount /dev/sda4 /mnt/sdcardboot

Put the following in ***/mnt/sdcardboot/extlinux/extlinux.conf***:

    default l0
    menu title QuartzPro64 Boot Menu
    prompt 0
    timeout 50

    label l0
    menu label Boot Jank Kernel SDMMC
    linux /jank
    fdt /dtbs/rockchip/rk3588-evb1-v10.dtb
    append earlycon=uart8250,mmio32,0xfeb50000 console=ttyS2,1500000n8 root=/dev/mmcblk0p14 rw rootwait

Copy your kernel to ***/mnt/sdcardboot/jank*** and your DTB to ***/mnt/sdcardboot/dtbs/rockchip/rk3588-evb1-v10.dtb***.

Unmount it, we’re done with the SD card.

### Creating the root file system

First, allocate a file the size of your desired root partition (larger sizes will take longer to transfer, don’t make the same mistakes as CounterPillow did), here we choose 16G:

```console
$ fallocate -l 16G rootpart.bin
```

then, make the filesystem on it. CounterPillow went for ext4 because nobody has ever been fired for using ext4:

```console
$ mkfs.ext4 rootpart.bin
```

Cool, now mount it:

    # mount rootpart.bin /mnt/emmc-root

Now we’ll download the Arch Linux ARM generic rootfs tarball and go to town:

```console
$ wget -N http://os.archlinuxarm.org/os/ArchLinuxARM-aarch64-latest.tar.gz{,.sig}
$ curl 'https://keyserver.ubuntu.com/pks/lookup?op=get&search=0x68b3537f39a313b3e574d06777193f152bdbe6a6' | gpg --import=-    # in case you're lacking the key
$ gpg --verify ArchLinuxARM-aarch64-latest.tar.gz.sig    # don't you dare skip this
# bsdtar -xpf ArchLinuxARM-aarch64-latest.tar.gz -C /mnt/emmc-root    # notice that this is run as root
```

Then we just need to edit fstab. Get the UUID (not PARTUUID) from lsblk:

```console
$ lsblk -o NAME,SIZE,MOUNTPOINTS,UUID
```

and put it in ***/mnt/emmc-root/etc/fstab*** as follows:

    UUID=_root-uuid-here_  /       ext4    defaults        0       1

Unmount ***/mnt/emmc-root***, we’re done with it.

### Flashing the root file system with RockUSB

{{< admonition type="warning" >}}
 This **will** destroy whatever data is on that userdata partition. But you’re here to run Linux, not Android, right?
{{< /admonition >}}

Plug one USB-C cable into the debug UART port, the other into the download port. Yes you will need two USB-C cables (or A-to-C cables) for this, get over it.

Plug in your board, reset it while hammering Ctrl+c on the debug UART until you get into a u-boot command line. Now enter the `download` command.

If your device doesn’t show up in `lsusb` or `rkdeveloptool list` command, pull out the download USB-C plug, rotate it axially by 180 Euler degrees, and plug it back in.

Next, flash the partition. Depending on the size of it, this can take over an hour:
 $ rkdeveloptool write-partition userdata rootpart.bin

### Booting

Unplug the download USB-C cable once done.

Put the SD card in the board. Reset it. You can now boot and your rootfs on eMMC will be mounted and contains an ALARM userland.

To update kernels or the device tree, just shut down the board, take out the SD card, write a new kernel or dtb to it, and plug it back in. No more need for rkdeveloptool, yay.
