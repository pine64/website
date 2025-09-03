---
title: "Flashing"
draft: false
menu:
  docs:
    title:
    parent: "PineNote/Development"
    identifier: "PineNote/Development/Flashing"
    weight: 2
aliases:
  - /wiki/PineNote_Development/Flashing
---

{{% docs/construction %}}

{{< admonition type="note" >}}
These instructions are directed towards experienced developers only!
{{</ admonition >}}

This page contains information on flashing software to the PineNote.

The general process is as follows:

1. Take a backup of all important data on the PineNote
2. Modify the partition layout to make space for your desired Linux distribution
3. Instantiate a root filesystem (rootfs) in the new partition space
4. Install your Linux distribution to the boot partition
5. Modify the boot process to boot the Linux distribution by default

There are multiple possible methods of executing these steps, and this page attempts to document all of them.

You can use:

1. `rkdeveloptool`, a command line utility for modifying [Rockchip](https://en.wikipedia.org/wiki/Rockchip) devices over USB
2. The [UART](/documentation/PineNote/Development/UART) shell
3. [Android Debug Bridge](https://en.wikipedia.org/wiki/Android_Debug_Bridge)
4. [Fastboot](https://en.wikipedia.org/wiki/Fastboot)

## Getting rkdeveloptool

Most flashing operations on the PineNote are done through `rkdeveloptool`, a command line utility built on libusb. PINE64 maintains its own fork [here](https://gitlab.com/pine64-org/quartz-bsp/rkdeveloptool) that you will need to get. The repo’s README contains a list of dependencies (libusb 1.0) and instructions for building the tool.

Installing (not just building) `rkdeveloptool` will configure PAM to elevate privileges where necessary on your system; you can configure this manually as follows:

```
sudo cp 99-rk-rockusb.rules /etc/udev/rules.d/
sudo udevadm control --reload
```

## Entering Maskrom/Rockusb mode

Interfacing with the PineNote over USB using `rkdeveloptool` requires first booting the PineNote into [an alternative operating mode](https://opensource.rock-chips.com/wiki_Rockusb) called Maskrom or Rockusb mode.

### Possible methods

There are three possible methods of entering Maskrom/Rockusb mode:

#### Hardware magnet switch

##### Developer Edition
1. Connect the PineNote to your computer via USB and boot the PineNote into Android
2. Locate & identify the small circular marking on the back of the PineNote, in the top right quadrant; have the PineNote pen close at hand, or any other small magnet
3. Hold the PineNote power button to bring up the reboot/shutdown menu; select reboot, then place the PineNote face down with the "eraser" end of the pen (or your magnet) resting on the small circular marking

##### Community Edition
The community edition is shipped with Debian and a passive pen without a magnet, therefore you will need to source your own magnet. 

1. Make sure you have flashed the new U-Boot image after receiving your community edition PineNote. You can do this if you haven't already by running:

    ```console
    $ cd /root/uboot
    ...
    $ bash install_stable_1056mhz_uboot.sh
    ```
2. Power off the PineNote from the Gnome quick settings menu in the top right.
3. Place the PineNote display side facing down and place the magnet on the small circle in the top right quadrant of the device. 
4. Plug the PineNote into your computer (you do not need to press the power button).

#### U-Boot terminal

This method requires a [UART dongle with passthrough](/documentation/PineNote/Development/UART#usb_passthrough) allowing simultaneous UART & USB connections.

It is nice because you can easily switch back & forth between U-Boot and Rockusb without having to physically manipulate the PineNote or its connectors; this is especially helpful when trying to develop U-Boot.

1. Connect to the PineNote via UART and USB simultaneously
2. Interrupt the U-Boot startup using `ctrl+c` sent over UART
3. In the U-Boot terminal over UART, run `rockusb 0 mmc 0`

The UART terminal should print `RKUSB` then a spinner will appear. You can exit back to the U-Boot terminal by sending `ctrl+c` again.

#### Shorting test points

If the bootloader is broken/corrupted, you cannot get to Maskrom without opening up the device (it can be opened using spudger and a bit of patience).

Once inside, short TP1301 (GND) and TP1302 (eMMC_D0/FLASH_D0) with a small tweezers, this is how it looks on board view (credit to Caleb):

{{< figure src="/documentation/PineNote/images/PineNote_Maskrom_TP.png" width="500px" >}}

### Success

No matter what approach you take, you can tell whether you succeeded by running the `lsusb` command on your computer:

* If you find the entry `2207:0018 Fuzhou Rockchip Electronics Company rk3566_eink` in the list, the process did not succeed; reboot and retry
* The entry `2207:350a Fuzhou Rockchip Electronics Company` will occur if you detach then reattach the USB-C cable while the PineNote is in Maskrom/Rockusb mode; `rkdeveloptool` won’t work and you will have to do a hard reboot (hold down power button for 30 seconds to shutdown)
* If you find the entry `2207:350a Fuzhou Rockchip Electronics Company USB download gadget` then the process succeeded

You can also look at the output of the `rkdeveloptool list` command:

* If this prints out `No devices in rockusb mode found` the process did not succeed; reboot and retry
* If this prints out `DevNo=1 Vid=0x2207,Pid=0x350a,LocationID=305 Maskrom` then you probably detached/reattached the USB-C cable while in Maskrom/Rockusb mode and `rkdeveloptool` won’t work; perform a hard reboot to fix
* If this prints out `DevNo=1 Vid=0x2207,Pid=0x350a,LocationID=303 Loader` then the process succeeded

### Exiting

You can boot the PineNote back into its normal mode of operation by powercycling the PineNote with its hardware power switch, or running the `rkdeveloptool reboot` command. If you used the magnetic switch method be sure to remove the pen/magnet before rebooting.

## Backup

A backup of the content of the internal eMMC before anything gets messed up is ***mandatory***.

Especially the _waveform_ partition contains data ***unique*** to your PineNote and is a prime candidate for backup.

Other partitions like U-Boot (need for any operation of the device) or the un-partitioned space at the beginning containing the GPT partition table (and presumably the VCOM setting for the e-ink display and maybe device mac addresses) contain data you may also wish to backup.

Depending of your personal level of data hoarder you may want to backup more than this or even just everything (the large _userdata_ partition is supposed to be able to be repopulated as empty space by Android)

In any case it is easier to restore/extract data from a backup than not having one if you need one.

This process was developed by Dorian Rudolph, originally described [here](https://github.com/DorianRudolph/pinenotes).

### List partitions

First, run `rkdeveloptool list-partitions` to print out your PineNote’s partitions to get an idea of what you’re dealing with.

#### Community Edition

Stock partition layout of the **Community Edition**:

| Number | Name | Size | Purpose |
| --- | --- | --- | --- |
| 0 |  uboot |  64 MB |  The [U-Boot](https://en.wikipedia.org/wiki/Das_U-Boot) embedded systems bootloader |
| 1 |  waveform |  2 MB |  Important files controlling the e-ink screen’s state changes |
| 2 |  uboot_env |  1 MB |  U-Boot environment partition |
| 3 |  logo |  64 MB |  Splash image displayed during boot |
| 4 |  os1 |  14.65 GB | Default OS slot where Debian is stored |
| 5 |  os2 |  14.65 GB |  An alternative operating system can be flashed here such as PostmarketOS or Arch Linux |
| 6 |  data |  85.82 GB | /home partition for user files |

#### Developer Edition

The stock **Developer Edition** has a fairly standard [Android partition setup](https://source.android.com/docs/core/architecture/partitions):

| Number | Name | Size | Purpose |
| --- | --- | --- | --- |
| 0 |  uboot |  4 MB |  The [U-Boot](https://en.wikipedia.org/wiki/Das_U-Boot) embedded systems bootloader |
| 1 |  trust |  4 MB |  Secrets that can be encrypted with a key stored in the [TPM](https://en.wikipedia.org/wiki/Trusted_Platform_Module) |
| 2 |  waveform |  2 MB |  Important files controlling the e-ink screen’s state changes |
| 3 |  misc |  4 MB |  Data used by the recovery partition |
| 4 |  dtbo |  4 MB |  [Device Tree Blob for Overlay](https://en.wikipedia.org/wiki/Devicetree), files describing the PineNote’s hardware configuration |
| 5 |  vbmeta |  1 MB |  Data required for [verified boot](https://android.googlesource.com/platform/external/avb/+/master/README.md) |
| 6 |  boot |  42 MB |  The kernel image & ramdisk to boot |
| 7 |  security |  4 MB |   |
| 8 |  recovery |  134 MB |  The recovery image, booted during Android updates |
| 9 |  backup |  400 MB |   |
| 10 |  cache |  1 GB |  Stores temporary data; can be used to install a minimal Linux distribution! |
| 11 |  metadata |  17 MB |  Used for disk encryption |
| 12 |  super |  3.25 GB |  Android itself is installed here |
| 13 |  logo |  17 MB |  Splash image displayed during boot |
| 14 |  device |  67 MB |   |
| 15 |  userdata |  119 GB |  The big one; user-installed Android apps and files live here |


### Patch U-Boot

{{< admonition type="note" >}}
This applies only to Developer Edition. Community Edition devices are shipped with fixed U-Boot. Do not flash the `uboot_patched.img` if the output of `rkdeveloptool list-partitions` doesn't match Developer Edition above.
{{</ admonition >}}

Before we can back up our partitions, we have a problem to solve. The version of U-Boot installed on the stock PineNote contains a bug where it can’t dump partitions beyond 32 MB (above that limit all bytes in the dump are just `0xCC`), meaning the PineNote must be flashed with a fixed version of U-Boot before it is possible to take a backup of the larger partitions. It is possible to extract and modify the U-Boot image from your PineNote if you’re interested in some light reverse-engineering (following Dorian’s notes), or you can simply download a patched U-Boot image directly [here](https://github.com/DorianRudolph/pinenotes/blob/main/static/uboot_patched.img).

Once you’ve acquired a patched U-Boot image, run:

1. `rkdeveloptool read-partition uboot uboot_backup.img`
2. `rkdeveloptool write-partition uboot uboot_patched.img`
3. `rkdeveloptool reboot`

### Taking the backup

With U-Boot patched, you can back up every partition except for super and userdata; run:

`rkdeveloptool read-partition partition_name partition_name_backup.img`

Unfortunately the super and userdata partitions run into a second limitation preventing dumping partitions larger than 2 GB, this time originating in `rkdeveloptool` itself. This means if you have a large number of documents in the Android userdata partition they might not all make it into the backup. If you don’t have many documents (or don’t care about losing them) this should not be a problem. If you do have a lot of documents, workarounds include:

* A possible patch written by Thomas exists [here](https://github.com/tpwrules/nixos-pinenote/blob/96d2c9158edb9da59afcb952cc864fada18382f9/nix/rkdeveloptool/0001-fix-large-dumps.patch) but has not yet been upstreamed; consider investigating how to get the patch tested & upstreamed, or just apply it to your own local copy of `rkdeveloptool`
* Use [this](https://github.com/talpadk/pinenote-backup) Python script written by Visti Andresen (talpadk) to automatically backup your entire partition by splitting reads into 2 GB chunks

See [instructions on this artifact](https://github.com/m-weigand/pinenote-debian-recipes/releases/tag/v0.1). It will instruct you on extracting the rootfs into an empty ext4 partition. This can be done from Linux or Android. Further instructions on building your own rootfs [can be found here](https://github.com/m-weigand/pinenote-debian-recipes).

### Using a user installed Linux

A Linux installed to the cache partition should be able to easily backup everything over WiFi or to a USB stick/disk using _dd_.

However the user would need to backup the cache partition (if they want that).

And more importantly they would only be getting the backup _after_ they started playing with the content of the eMMC.

## Side-by-side setup

It is possible to set up a partition for mainline development without disturbing the factory Android installation. This allows updating a mainline kernel, DTB, and initramfs over Wi-Fi until WiFi or USB OTG is working in mainline Linux.

### Without Repartitioning

The recommended partition for this is _mmcblk0p11_ aka _/cache_. It is large and already formatted as _ext4_, so it is readable from U-Boot. Here are some general steps:

1. From the UART or adb shell, set up your chroot in _/cache_. I used the Alpine Linux rootfs tarball.
2. Copy in your kernel and DTB, using for example _scp_ or _wget_ inside the chroot.
3. Finally, create and boot an `extlinux.conf` as described below.

### With Repartitioning

It is possible to shrink the _userdata_ partition, and create a new partition at the end for use with mainline Linux. This provides much more space than _cache_. However, because _userdata_ is formatted with _f2fs_, and that filesystem cannot be shrunk, resizing the partition requires wiping _userdata_.

1. Back up any necessary files from userdata
2. Boot to a mainline kernel from _mmcblk0p11_, either using that partition as rootfs (see above), or using an initramfs with repartitioning tools
3. Modify the partition table with your favorite tool, e.g. _fdisk_, _gdisk_, or _parted_
4. Reboot into _fastboot_ and wipe _userdata_.
5. Reboot into Android, where you can now chroot in and install your favorite distribution to the new partition.

## Using rkdeveloptool

### Building Downstream U-Boot

While in maskrom mode, we need to have a u-boot to download onto the device for any of the other commands to work. To build you’ll also need to install device-tree-compiler.

You also need to install Python and pyelftools.

{{< admonition type="note" >}}
 The rkbin is a >5GB download! This will take some time to clone and process the deltas.
{{</ admonition >}}

```
git clone -b quartz64 https://gitlab.com/pgwipeout/u-boot-rockchip.git
git clone -b rkbin https://github.com/JeffyCN/rockchip_mirrors.git rkbin
cd u-boot-rockchip
# If using Arch Linux, export CROSS_COMPILE=aarch64-linux-gnu-
export CROSS_COMPILE=aarch64-none-linux-gnu-
make rk3566-quartz64_defconfig
./make.sh
```

> In the current version (current as of 2022-01-02), there might have to be made a change to one line to get a clean compilation:
>
> ```
> diff --git a/lib/avb/libavb/avb_slot_verify.c b/lib/avb/libavb/avb_slot_verify.c
> index 123701fc3b..64a1ce6450 100644
> --- a/lib/avb/libavb/avb_slot_verify.c
> +++ b/lib/avb/libavb/avb_slot_verify.c
> @@ -296,7 +296,7 @@ static AvbSlotVerifyResult load_and_verify_hash_partition(
>    bool image_preloaded = false;
>    uint8_t* digest;
>    size_t digest_len;
> -  const char* found;
> +  const char* found = NULL;
>    uint64_t image_size;
>    size_t expected_digest_len = 0;
>    uint8_t expected_digest_buf[AVB_SHA512_DIGEST_SIZE];
> ```
>
> For systems where the global python executable points to python2, compilation fails with an error related to pyelftools not being installed (even if it is). To fix this:
>
> ```
> diff --git a/make.sh b/make.sh
> index 2bba05b4e4..cfe5b0afd5 100755
> --- a/make.sh
> +++ b/make.sh
> @@ -758,7 +758,7 @@ function pack_fit_image()
>         fi
>  
>         if [ "${ARM64_TRUSTZONE}" == "y" ]; then
> -               if ! python -c "import elftools" ; then
> +               if ! python3 -c "import elftools" ; then
>                         echo "ERROR: No python 'pyelftools', please: pip install pyelftools"
>                         exit 1
>                 fi
> ```

You can now download u-boot onto the PineNote:

    ./rkdeveloptool boot ../u-boot-rockchip/rk356x_spl_loader_v1.08.111.bin

This should output "_Downloading bootloader succeeded_".

We can now verify that this worked using e.g. the "read flash info" command:

    ./rkdeveloptool read-flash-info

{{< admonition type="note" >}}
 Section needs to be finished
{{</ admonition >}}

### Creating a mainline boot image

You can create a filesystem image that replaces the Android boot or recovery partition by doing roughly the following:

1. Erase boot and dtbo with rkdeveloptool or fastboot (back them up first!!!)
2. Create an ext2 partition image and mount it (fallocate, mkfs.ext2)
3. Build your mainline kernel
4. Copy the kernel, dtb and an initramfs to the root of the mounted image (use any old postmarketOS initramfs)
5. Create a file in the root of the mounted image called `extlinux.conf` as described below
6. Unmount the image and then use rkdeveloptool to flash it to the "recovery" partition on the pinenote (it’s about the right size until we get around to replacing the partition layout).

## Using fastboot

Follow the steps for [Creating a mainline boot image](#creating_a_mainline_boot_image), but instead of flashing it with _rkdeveloptool_, use _fastboot_. You can enter fastboot in either of two ways:

* Use "reboot bootloader" from adb or a UART console or
* get a U-Boot prompt and run `fastboot usb 0`.
