---
title: "U-Boot"
draft: false
menu:
  docs:
    title:
    parent: "General"
    identifier: "General/U-Boot"
    weight: 
---

**💡 TIP**\
It is helpful to have a debugging serial cable for this.

## Building U-Boot manually

### Prerequisites

These instructions are written with a host Arch Linux desktop system in mind.

This guide will be especially useful if you are looking to overclock the ram on your PinePhone following the information found [here](/documentation/General/Overclocking#dram).

You must have these packages installed: `dtc swig bc aarch64-linux-gnu-gcc`

If you are using a different system such as Ubuntu, there are plenty of cross compilation instructions available online with which you can grab the needed package names from, however you should be able to follow these instructions with these packages installed: `build-essential bison flex swig gcc-aarch64-linux-gnu`

### Compilation

**💡 TIP**\
This guide is written with the PinePhone in mind. On other devices you will need to set a different platform variable and likely use a different U-Boot source with patches oriented towards your device.

Note by default these instructions utilize all of your computers cores to compile thanks to the `-j` and `$(nproc)` parameters. If you wish to only use one core to compile, or change the number of cores used for example to only two cores, then you can either completely remove the `-j$(nproc)` parameter from the make commands, or just take off `$(nproc)` and add the number of threads you want used in it’s place: `-j4`

First, You need to compile the ATF (Arm Trusted Firmware):

    git clone https://github.com/crust-firmware/arm-trusted-firmware/
    cd arm-trusted-firmware
    export CROSS_COMPILE=aarch64-linux-gnu-
    export ARCH=arm64
    make PLAT=sun50i_a64 -j$(nproc) bl31
    cd ..

After the ATF is compiled clone u-boot and copy the bl31.bin file into the u-boot directory.

    git clone https://gitlab.com/pine64-org/u-boot.git
    cd arm-trusted-firmware
    cp build/sun50i_a64/release/bl31.bin ../u-boot/
    cd ..

**💡 TIP**\
You cannot build [Crust](/documentation/PinePhone/Software/Crust) if you do not have the or1k musl toolchain installed. This toolchain is not usually available in distribution repositories and will have to be manually installed to the system. The following text will show a simple way to install the toolchain.

Download the toolchain’s archive: https://musl.cc/or1k-linux-musl-cross.tgz

Extract the compressed archive: `tar zxvf or1k-linux-musl-cross.tgz`

Move the extracted archive to wherever you would like to install the toolchain to. In these instructions it will simply be installed to the users documents folder.

The final step is to edit your `.bashrc` and add the following to the end:

    # Path for or1k toolchain
    export PATH="$PATH:/home/USER/Documents/or1k-linux-musl-cross/bin/"

After you’ve completed that you can close out the terminal and reopen it and proceed to the following instructions.

    git clone https://github.com/crust-firmware/crust
    cd crust
    export CROSS_COMPILE=or1k-linux-musl-
    make pinephone_defconfig
    make -j$(nproc) scp
    cp build/scp/scp.bin ../u-boot/
    cd ..

**💡 TIP**\
If you do not wish to have [Crust](/documentation/PinePhone/Software/Crust) in your U-Boot build, then you can skip exporting SCP

    cd u-boot/
    git checkout crust
    export CROSS_COMPILE=aarch64-linux-gnu-
    export BL3bl31.bin
    export ARCH=arm64
    export SCP=scp.bin
    make distclean
    make pinephone_defconfig
    make all -j$(nproc)

### U-Boot installation

Once successfully compiled you can proceed to flash the device

{{< admonition type="warning" >}}
 Replace [CHANGE THIS] with the location of your SD card and make sure you are using the proper location. Failure to do so can result in data loss.
{{< /admonition >}}
```
sudo dd if=u-boot-sunxi-with-spl.bin of=/dev/[CHANGE THIS] bs=1024 seek=8
```

**💡 TIP**\
If you are compiling U-Boot in order to overclock your DRAM you can check if it was successful by reading the values of /sys/kernel/debug/clk/clk_summary

## p-boot multi-bootloader

One of the smallest and fastest PinePhone bootloaders, it was developed by Ondrej Jirman with the ability of booting multiple distributions on the PinePhone in mind.

More information can be found [here](https://xnux.eu/p-boot/)

## External Links

[Sunxi U-Boot Wiki](https://linux-sunxi.org/Mainline_U-Boot)

[U-Boot build instructions](https://raw.githubusercontent.com/u-boot/u-boot/master/board/sunxi/README.sunxi64)

[or1k toolchain download](https://musl.cc/or1k-linux-musl-cross.tgz)
