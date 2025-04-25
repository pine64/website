---
title: "Building Kernel"
draft: false
menu:
  docs:
    title:
    parent: "PineNote/Development"
    identifier: "PineNote/Development/Building_kernel"
    weight: 1
aliases:
  - /wiki/PineNote_Development/Building_Kernel
---

This page contains information on how to build a linux kernel for the PineNote.

## Available Kernel Repositories

The following PineNote-specific kernel repositories are available:

* https://github.com/m-weigand/linux/ (based mainly on the repository from smaeul, with additional patches pulled in from other sources, Debian packages available)
* https://git.sr.ht/~hrdl/linux (based on Maximilian's kernel tree, which improves display responsiveness with per pixel scheduling and the automatic redraw of pixels among other improvements)

## Building the kernel
There are currently a couple of up to date trees to choose from. 
* Maximilian's kernel is found on the default Debian based operating system shipped with the community edition devices. Currently the most stable option. 
* hrdl's tree is more experimental with new features such as per pixel scheduling and the automatic redrawing of pixels.

### Prerequisites
#### Building on Debian:
* Building on device (or another 64bit arm device) will require you to install `build-essential`. 
* If you are wanting to cross compile you are required to install `gcc-12-aarch64-linux-gnu-base` (or equivalent) and `build-essential`. 
  
### m-weigand kernel
Found at https://github.com/m-weigand/linux/

```console
# Clone the kernel repository and set up the working environment.
$ git clone --depth 1 --branch branch_pinenote_6-6-30 https://github.com/m-weigand/linux
$ cd linux

# Set the PineNote defconfig and compile the kernel. 
# Remember to pick the commands that reflect your compilation environment below. 

# For cross compilation
$ make ARCH=arm64 CROSS_COMPILE=aarch64-linux-gnu- pinenote_defconfig
$ make -j 2 ARCH=arm64 CROSS_COMPILE=aarch64-linux-gnu- LOCALVERSION=-pinenote-`date +%Y%m%d%H%M` KBUILD_IMAGE=arch/arm64/boot/Image

# For aarch64 host compilation
$ make pinenote_defconfig
$ make -j 2 LOCALVERSION=-pinenote-`date +%Y%m%d%H%M` KBUILD_IMAGE=arch/arm64/boot/Image

Once finished you will have your Image and vmlinux files.
``` 
To install your modules and dtbs:
```console
# Make a folder to store these files
$ mkdir pack

# For cross compilation
$ make ARCH=arm64 CROSS_COMPILE=aarch64-linux-gnu- INSTALL_MOD_PATH=${PWD}/pack modules_install
$ make ARCH=arm64 CROSS_COMPILE=aarch64-linux-gnu- INSTALL_PATH=${PWD}/pack dtbs_install

# For aarch64 host compilation
$ make INSTALL_MOD_PATH=${PWD}/pack modules_install
$ make INSTALL_PATH=${PWD}/pack dtbs_install

# Copy these to store them in our pack folder.
$ cp ./arch/arm64/boot/dts/rockchip/rk3566-pinenote-v1.2.dtb pack/
$ cp ./arch/arm64/boot/Image pack/
```
### hrdl kernel
Found at https://git.sr.ht/~hrdl/linux/

```console

# Clone the kernel repository
$ git clone --depth 1 https://git.sr.ht/~hrdl/linux hrdl-linux
$ cd hrdl-linux

# Set the PineNote defconfig and compile the kernel. 
# Remember to pick the commands that reflect your compilation environment below. 

# For cross compilation
$ make ARCH=arm64 pinenote_defconfig
$ make ARCH=arm64 -j$(($(nproc)-1))
$ make ARCH=arm64 INSTALL_PATH=pack INSTALL_MOD_PATH=pack modules_install dtbs_install

# For aarch64 host compilation
$ make pinenote_defconfig
$ make LLVM=1 -j$(($(nproc)-1))
$ make INSTALL_PATH=pack INSTALL_MOD_PATH=pack modules_install dtbs_install
```

## Next steps

### Configuring the driver
The driver has several options that can improve performance. These can be read about [here](https://github.com/m-weigand/mw_pinenote_misc/tree/main/rockchip_ebc/patches#new-features-as-of-2022august08).

Users should edit the `/etc/modprobe.d/rockchip_ebc.conf` to configure their driver.

#### For m-weigand kernel
`options rockchip_ebc direct_mode=0 auto_refresh=1 refresh_threshold=60 split_area_limit=0 panel_reflection=1 prepare_prev_before_a2=0 dclk_select=0`

#### For hrdl kernel 6.15rc3 
`options rockchip_ebc dithering_method=2 default_hint=0x80 early_cancellation_addition=2 redraw_delay=200`

### Fixing suspend

If you’re using a logind system, edit your **/etc/systemd/logind.conf** config. More information on what to do [in Arch’s documentation](https://wiki.archlinux.org/title/Power_management#ACPI_event).

### Configuring your apps

See [Apps](/documentation/PineNote/Development/Apps).

### Booting Linux instead of Android

[PineNote Development/Booting Linux](/documentation/PineNote/Development/Booting_Linux)

### Fixing Bluetooth

See [PineNote Development/Software Tweaks](/documentation/PineNote/Development/Software_tweaks)
