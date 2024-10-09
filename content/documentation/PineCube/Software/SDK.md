---
title: "SDK"
draft: false
menu:
  docs:
    title:
    parent: "PineCube/Software"
    identifier: "PineCube/Software/SDK"
    weight: 
---

Stock Linux:

* [Direct Download from pine64.org](https://files.pine64.org/SDK/PineCube/PineCube%20Stock%20BSP-SDK%20ver1.0.7z) (MD5 (7zip file): efac108dc98efa0a1f5e77660ba375f8, file size: 3.50GB)

Compilation:

You can either setup a machine for the build environment, or use a Vagrant virtual machine provided by [Elimo Engineering](https://elimo.io)

## Compile on a dedicated machine

Recommended system requirements:

* OS: (L)Ubuntu 16.04
* CPU: 64-bit based
* Memory: 8 GB or higher
* Disk: 15 GB free hard disk space

Install required packages:

    sudo apt-get install p7zip-full git make u-boot-tools libxml2-utils bison build-essential gcc-arm-linux-gnueabi g++-arm-linux-gnueabi zlib1g-dev gcc-multilib g++-multilib libc6-dev-i386 lib32z1-dev

Install older Make 3.82 and Java JDK 6:

    pushd /tmp
    wget https://ftp.gnu.org/gnu/make/make-3.82.tar.gz
    tar xfv make-3.82.tar.gz
    cd make-3.82
    ./configure
    make
    sudo apt purge -y make
    sudo ./make install
    cd ..
    # Please, download jdk-6u45-linux-x64.bin from https://www.oracle.com/java/technologies/javase-java-archive-javase6-downloads.html (requires free login)
    chmod +x jdk-6u45-linux-x64.bin
    ./jdk-6u45-linux-x64.bin
    sudo mkdir /opt/java/
    sudo mv jdk1.6.0_45/ /opt/java/
    sudo update-alternatives --install /usr/bin/javac javac /opt/java/jdk1.6.0_45/bin/javac 1
    sudo update-alternatives --install /usr/bin/java java /opt/java/jdk1.6.0_45/bin/java 1
    sudo update-alternatives --install /usr/bin/javaws javaws /opt/java/jdk1.6.0_45/bin/javaws 1
    sudo update-alternatives --config javac
    sudo update-alternatives --config java
    sudo update-alternatives --config javaws
    popd

PineCubes SPI Flash support patch:

    From 9316112c37ee86645fd691c6d3352183b95177d8 Mon Sep 17 00:00:00 2001
    From: Marek Kraus <gamelaster@outlook.com>
    Date: Fri, 8 Jul 2022 21:01:47 +0200
    Subject: [PATCH] Add support for xt25f128 SPI Flash

    ---
    drivers/mtd/devices/m25p80.c | 1 +
    1 file changed, 1 insertion(+)

    diff --git a/drivers/mtd/devices/m25p80.c b/drivers/mtd/devices/m25p80.c
    index 31e5795..0f46a4c 100755
    --- a/drivers/mtd/devices/m25p80.c
    +++ b/drivers/mtd/devices/m25p80.c
    @@ -803,6 +803,7 @@ static const struct spi_device_id m25p_ids[] = {
     	{ "w25x64", INFO(0xef3017, 0, 64 * 1024, 128, SECT_4K) },
     	{ "w25q64", INFO(0xef4017, 0, 64 * 1024, 128, SECT_4K) },
     	{ "W25q128", INFO(0xef4018, 0, 64 * 1024, 256, 0) },
    +	{ "xt25f128", INFO(0x0b4018, 0, 64 * 1024, 256, SECT_4K) },
     	

    /* Catalyst / On Semiconductor -- non-JEDEC */

    7.4

Unpack SDK and then compile and pack the image:

    7z x 'PineCube Stock BSP-SDK ver1.0.7z'
    mv 'PineCube Stock BSP-SDK ver1.0' pinecube-sdk
    cd pinecube-sdk/camdroid
    # apply SPI Flash patch above or edit m25p80.c file
    source build/envsetup.sh
    lunch # select [1] here
    mklichee
    extract-bsp
    make -j3
    pack

## Compile using Vagrant

You can avoid setting up your machine and just use Vagrant to spin up a development environment in a VM.

Just clone the [Elimo Engineering repo](https://github.com/elimo-engineering/pinecube-sdk-vagrant) and follow the instructions in the [readme file](https://github.com/elimo-engineering/pinecube-sdk-vagrant/blob/main/README.md)

After spinning up the VM, you just need to run the build:

    cd pinecube-sdk/camdroid
    # apply SPI Flash patch above or edit m25p80.c file
    source build/envsetup.sh
    lunch # select [1] here
    mklichee
    extract-bsp
    make -j3
    pack

## Flashing the image

See [PhoenixCard](/documentation/Unsorted/PhoenixCard) for a manual on how to flash Allwinners BSP images.
