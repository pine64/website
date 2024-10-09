---
title: "Getting started"
draft: false
menu:
  docs:
    title:
    parent: "Introduction"
    identifier: "Introduction/Getting_started"
    weight: 
---

This guide is for the PINE64 devices. For device-specific information please see the corresponding device pages listed on the [main page](/documentation#Devices).

## Requirements

You will need the following to get started with using your [PINE A64(+)](/documentation/Pine_A64), [PINE A64-LTS](/documentation/Pine_A64-LTS), [Pinebook](/documentation/Pinebook) or [ROCK64](/documentation/ROCK64) board:

* A Windows / Linux PC or Mac device with a MicroSD Card Reader
* Internet connection / pre-downloaded OS image files
* Power Supply:
  * **PINE A64(+)**: Power Supply (PSU) and a micro USB cable. Please make sure to use a PSU rated at +5V @2A and a micro USB cable that is at least 26 AWG thick.
  * **SOPine/PINE A64-LTS**: Power Supply (PSU) with 3.5mm OD/1.5mm ID barrel DC Jack. Please make sure to use a PSU rated at +5V @2A.
  * **Pinebook** and **ROCK64**: Power Supply (PSU) with 3.5mm OD/1.5mm ID barrel DC Jack. Please make sure to use a PSU rated at +5V @3A.
* MicroSD card (Recommend: 8GB or higher capacity, 10MB/s or faster speed)
* HDMI cable (unless you wish to run [headless](https://en.wikipedia.org/wiki/Headless_computer) / without a screen)
  * For, Android and Remix OS supports 720p and 1080p, while Linux supports a [wider range of resolutions](https://github.com/longsleep/sunxi-disp-tool#available-hdmi-output-names).
* Input device(s) such as: keyboard, mouse, remote, pointer, etc.

## Step-by-Step Instructions for Flashing MicroSD Cards

{{< admonition type="important" >}}
 **Caution!** Handle the Pine64 Single Board Computers' PCBs with care. Always hold bare boards by the edges and make sure to wear an anti-static wrist strap. Touching components on the front and back of the boards can result in an ESD discharge that may cause damage to the electronics. Avoid placing bare boards on materials such as carpets, plastics or other surfaces prone to electrostatic build-up
{{< /admonition >}}

**Begin by imaging the OS of your choice**

The process of flashing PINE64 OS images to micro SD on your Windows, Linux or OSX device is the same for all devices. You will require a quality microSD card (8GB or greater; class 10 or faster). There are many [substandard and counterfeit cards](https://forum.pine64.org/showthread.php?tid=681) in circulation and even reputable vendors may unknowingly sell counterfeit microSD cards. Cards that do not meet the criteria outlined above are known to cause a variety of issues including, but not limited to, complete boot failure. There are ways of testing microSD cards prior to installing the operating system to make sure they are appropriate for use with your board. The main utility for checking microSD cards is  [H2testw 1.4](https://www.softpedia.com/get/System/System-Miscellaneous/H2testw.shtml#download); yet another alternative is [F3](https://github.com/AltraMayor/f3/archive/v6.0.zip). Yet another overview of various options [Test and Detect Fake Cards](https://www.raymond.cc/blog/test-and-detect-fake-or-counterfeit-usb-flash-drives-bought-from-ebay-with-h2testw/)

Please refer to the relevant section below for instructions on how to image your microSD card:

* [Imaging microSD on Windows 7/8/8.1/10](#imaging_microsd_on_windows_788_110)
* [Imaging microSD on macOS](#imaging_microsd_on_macos)
* [Imaging microSD on Linux](#imaging_microsd_on_linux)

Having successfully imaged your microSD card, insert it into the microSD slot.

**Plug in the HDMI Cable, Ethernet Cable and Peripherals to your PINE64 SBC**

Unless you are planning on running your board headless (without a monitor / as a server) you should plug in all necessary peripherals, including the HDMI and Ethernet cable, prior to powering ON the board. Do note, depending on which OS image you are using, some peripherals may or may not work.

**Apply Power to Your Board**

Once you have imaged your microSD and plugged everything in, you are ready to apply power to the PINE64 Single Board Computer. You’ll need a good quality 5 Volt, 2 Amp PSU. Using a good quality PSU is very important as failing to meet the required specifications may prevent the board from booting correctly. A marginally higher PSU Voltage is acceptable (for instance, 5.1 volts - due to the nature of the micro USB connection, a 5.1v supply can help protect slightly against voltage drops which can cause undesirable results). However, a significantly higher voltage of 7 Volts or more will damage the PINE64 Single Board Computer and may render it inoperative.

For PINE A64(+) board, if you are using a separate micro USB cable with your PSU, make sure that the cable has a low resistance rating. Cables with high resistance will cause improper function and the unit may not boot at all or only partially. The thicker the internal cabling, the better [i.e. AWG (American Wire Gauge) 20 is better than AWG 28](https://voyager8.blogspot.co.uk/2013/04/how-to-choose-good-usb-data-and.html). In General, **power-only microUSB** cables come with red colour USB header.

Having completed the steps outlined above the PINE64 Single Board Computer will begin to boot. The onboard power-on LEDs will come on and Ethernet port LEDs will start to blink if you have an Ethernet cable plugged in.

### Imaging microSD on Windows 7/8/8.1/10

You will need the following utilities to get started with imaging the OS of your choice onto your microSD card:

* A compression utility (used to unarchive the OS image). We recommend you use [7zip](https://www.7-zip.org/download.html).
* A disk image utility (used to flash the .img to your SD card). We recommend you use either the [Etcher](https://etcher.io/) or [Win32Imager](https://sourceforge.net/projects/win32diskimager/) utility.

**Optional for Allwinner A64 SoC based boards**
* Phoenix Card image utility (used ONLY for phoenix card images).

**Downloading and extracting OS image(s)**

You can find OS images for the respective devices in the [device section](/documentation) on the main page.
Images designated ‘DD’ need to be flashed using Etcher or Win32imager, whilst images labelled ‘Phoenix Card Image’ require the Phoenix Card utility.

Having downloaded the required OS image proceed to use 7zip to unarchive it by right-clicking the archive, and selecting ‘Extract All’. Upon completion, note the destination of where the .img file was extracted (‘Downloads’ folder by default). Once the process has completed, you can proceed to imaging the .img file.

**Imaging the microSD card (DD)**

* Insert your microSD card into your laptop/USB card reader. You may require a SD → microSD converter, as most laptops and desktops only feature a full-size SD card reader. Once the microSD card is plugged into your computer, make sure to take note of the drive it has been assigned (the drive is assigned a letter, e.g. ‘F:’). You will need to remember the ‘letter’ it has been assigned when imaging the OS.
* Launch Win32diskImager.exe or etcher.exe. You will be presented with a field titled ‘path’ and a drop down menu labeled ‘device’. Click the ‘path’, navigate to and select the OS image you extracted from the archive earlier. Next, from the drop-down menu select the drive your microSD has been assigned. WARNING: Pay close attention to the selected drive (remember your letter) – the imaging process will permanently erase and format the selected drive. If you choose the wrong drive all your data will be lost.
* Having chosen the desired OS image and the correct driver press ‘write’. Once the image has been written to your microSD card you will receive a pop-up notification. Be sure to close the application and to eject/remove your SD card safely from Windows.

**Imaging using Phoenix Card (applicable only to Allwinner A64 SoC based boards)**

On Windows, you can also use Phoenix Card (for detailed instructions click [here](/documentation/Unsorted/PhoenixCard)). The Phoenix Card utility works ONLY with images designated as ‘Phoenix Card’ in the downloads section. To use Phoenix Card follow these steps:

* Insert your microSD card into your laptop/USB card reader. You may require a SD → microSD converter, as most laptops and desktops only feature a full-size SD card reader. Once the microSD card is plugged into your computer, make sure to take note of the drive it has been assigned (the drive is assigned a letter, e.g. ‘F:’). You will need to remember the ‘letter’ it has been assigned when imaging the OS.
* Launch phoenixcard.exe. You will be presented with a ‘disk’ drop-down menu and a field denoted as ‘.img File’. Click on ‘.img File’ and navigate to and select the OS image have downloaded and unarchived. Next, make sure to select the disk that your microSD card has been assigned. WARNING: Pay close attention to the selected drive (remember your letter) – the imaging process will permanently erase and format the selected drive. If you choose the wrong drive all your data will be lost.
* Make sure to select ‘Startup!’ from the ‘Write mode’ window and click Burn. Once the image has been written to your microSD card you will receive a confirmation in the ‘option’ window. Be sure to close the application and to eject/remove your SD card safely from Windows.

### Imaging microSD on macOS

You will need the following utilities to get started with imaging the OS of your choice onto your microSD card:

* A compression utility (used to unarchive the OS image). You may use [Keka](https://www.keka.io/en/).
* A disk image utility (used to flash the .img to your SD card in GUI). You may use [ApplePi Baker v2](https://www.tweaking4all.com/software/macosx-software/applepi-baker-v2/#DownloadApplePiBaker) or [Etcher](https://etcher.io/).

**💡 TIP**\
Phoenix Card utility and images are NOT available on macOS.

**Downloading and extracting OS image(s), insert the SD card**

You can find OS images for the respective devices in the [device section](/documentation#Devices) of the main page.

Having downloaded the required OS image, proceed to use the compression utility to unarchive it and get the .img file.
Once the process has completed, you can proceed to write it to your SD card.

Insert your microSD card into your Mac laptop/USB card reader.
You may require a SD → microSD converter, as Apple’s laptops and desktops only feature a full-size SD card reader.
Once the microSD card is plugged into your computer, it should appear in Finder / on your desktop.

**Imaging the microSD card (GUI)**

Launch the imaging utility. Upon startup, the application may ask for your password.
When the application launches, you will be presented with a field titled ‘IMG file’ and a path of the mounted microSD card
(it will look like this: ‘/dev/diskX 32.0Gb SD card’).

To choose the OS image file, click the ‘IMG file’ button, navigate to and select the .img file you extracted from the archive earlier.
Then select the microSD card you want to write into.

{{< admonition type="warning" >}}
 Pay close attention to the selected device, make sure it is the right SD card – the imaging process will permanently erase and format the selected storage device. If you choose the wrong device, all the data in it will be lost.
{{< /admonition >}}

Having chosen the desired OS image and the correct device, press ‘Restore Backup’ or ‘Flash’.
Once the image has been written to your microSD card, you will receive a pop-up notification.
Close the application, then eject/remove your SD card from your Mac.

**Imaging from Terminal**

{{< admonition type="important" >}}
 If you are not comfortable using the terminal, please use the GUI method outlined above instead.
{{< /admonition >}}

Open up your terminal and navigate to the directory where you unarchived your OS image.

Before you start writing to the card, you will have to identify your microSD card.
Type: `diskutil list` and note the output.
The disk number should match the size of your SD card, and will likely be using `Fdisk_partition_scheme`.

Having identified the disk number execute the following commands
(substitute diskX for your disk and name of image for pine64-image-name.img):

    diskutil unmountDisk /dev/diskX
    sudo dd if=pine64-image-name.img of=/dev/disk2 bs=1M

Wait patiently for the process to complete, then eject/remove your SD card from your Mac.

### Imaging microSD on Linux

You will need the following utilities to get started with imaging the OS of your choice onto your microSD card:

* A compression Utility (used to unarchive the OS image). We recommend you use [Ark](https://apps.kde.org/en/ark).
* A disk image utility (used to flash the .img to your SD card in GUI). We recommend you use [Etcher](https://etcher.io/) or the [GUI Disks utility](https://git.gnome.org/browse/gnome-disk-utility/) that ships with most popular distributions.

**💡 TIP**\
Phoenix Card utility and images are NOT available on Linux.

**Downloading and extracting OS image(s)**

You can find OS images for the respective devices in the [device section](/documentation) on the main page. On Linux you can only use images designated as ‘DD’.

Having downloaded the required OS image proceed to use 7zip to unarchive it by double clicking the archive, and selecting ‘Extract All’. Upon completion, note the destination where the .img file was extracted (‘Downloads’ folder by default). Once the process has completed, you can proceed to imaging the .img file.

**Imaging the microSD card (GUI)**

* Insert your microSD card into your Linux laptop/USB card reader. Once the microSD card is plugged into your computer it should appear in your File Manager / on your desktop.
* Launch Disks or the etcher utility (This tutorial outlines how to use Disks, if you wish to learn how to use Etcher please visit [their website](https://etcher.io/)).
* Upon launching Disks, you will be presented with all volumes visible to your computer. As a rule of thumb, your microSD card should be found at the bottom of listed volumes. Verify this by checking the size and mounting of the microSD card. WARNING: Pay close attention to the selected drive – the imaging process will permanently erase and format the selected drive. If you choose the wrong drive all your data will be lost.
* Having selected your microSD card, click the cog menu in top right corner and choose the ‘Restore Disk Image’ option from the drop-down list. Navigate to and select the OS image you extracted from the archive earlier. Once you select it, you will be asked to enter your password and to confirm writing to the chosen volume (microSD card).
* You will be given a predicted time, writing-speed and completion percentage. Once the image has been written to your microSD card you will receive a pop-up notification. Be sure to close the application and to eject/remove your SD card safely from your computer.

**Imaging from Terminal**

{{< admonition type="important" >}}
 If you are not comfortable using the terminal, please use the GUI method outlined above instead.
{{< /admonition >}}

* Insert your microSD card into your Linux laptop/USB card reader. Once the microSD card is plugged into your computer it should appear in Finder / on your desktop.
* Open up your terminal and navigate to the directory where you unarchived your OS image. e.g. `cd Download`
* Before you start writing to the card, you will have to identify your microSD card.
* Type: `lsblk` and pay attention to the listed disks. Disks will appear as _/dev/mmcblk0 /dev/mmcblk1_ etc.

{{< admonition type="important" >}}
 **Hint**: the drive you currently have booted from has the `/` at the end of the line. This is the wrong drive. Look at the drive that matches your microSD card’s size.
{{< /admonition >}}

* Now you are ready to write the image to the microSD card using this command: (replace the pine.img file with your image and mmcblkX with the correct device for the microSD card)

      sudo umount /dev/mmcblkX
      sudo dd if=pine.img of=/dev/mmcblkX bs=1M status=progress conv=fsync
* Wait patiently for the process to complete.
* use the command `sync` to ensure everything is written to the microSD card.
* The card is ready to boot

(sometimes this process fails and your microSD card can’t boot, one way of fixing this is just to repeat the same thing, you can also try a different microSD card)

## Instructions for Flashing Removable eMMC Modules

Many Pine64 devices support removable eMMC modules as an alternative boot and storage solution to micro SD cards.
These devices include SBCs such as the Pine A64-LTS, ROCK64, ROCKPro64, PINE H64, SOPINE Baseboard, SOPINE Clusterboard, and Quartz64, and devices such as the Pinebook and Pinebook Pro.

Please be aware that the Pine A64 (+) does not support an eMMC module, while the Pine A64-LTS does.

An eMMC module can be purchased for your device(s) from the [PINE64 store](https://pine64.com/?post_type=product). The Pinebook and Pinebook Pro both come with a removable eMMC module pre-installed.

The available modules come in four different capacities: 16Gb, 32Gb, 64Gb and 128Gb

There are a few ways to flash eMMC modules with the desired OS image. The following sections are a summary of the processes involved in flashing the OS image of your choice to an eMMC module once it has been removed.

### Flashing Using the USB-to-eMMC Adapter (Preferred Way)

A USB-to-eMMC adapter is available from purchase from the [PINE64 Store](https://pine64.com/product/usb-adapter-for-emmc-module/) making it easy to mount the eMMC module as a volume in your Windows, Mac OS or Linux computer. The eMMC can hence be flashed directly from your computer with any image similarly to a micro SD card.

**This installation method works for all devices that support eMMC modules regardless of the chipset** and it is therefore the preferred way of flashing OS images to eMMC. All available OS images for your device can be installed on the eMMC module this way.

**This process of flashing an OS image to eMMC is *completely identical to imaging micro SD cards**, so please read [Step-by-Step Instructions to Flashing Micro SD Cards](/documentation/Introduction/Getting_started#step_by_step_instructions_for_flashing_microsd_cards) before you begin.

For this method you will need the following:

* A Windows, Linux or Mac OS computer
* A PINE64 eMMC module
* The PINE64 USB-to-eMMC adapter

**Flashing eMMC using the adapter**

* Insert the the eMMC module into the USB adaptor and plug it into your Windows, Linux or Mac OS computer. It should mount as a regular USB drive and show up in your file manager.
* If you are using Linux or Mac OS you can either use the dd terminal command or a GUI utility such as [Etcher](https://etcher.io/) to flash the chosen OS Image to eMMC.
* If you are using a Windows machine use [Etcher](https://etcher.io/) or [Win32 Disk Imager](https://sourceforge.net/projects/win32diskimager/) to flash the OS Image to the eMMC module.

Once the image has been flashed using your preferred method safely dismount the USB adapter in your system and unplug it from your computer. Your eMMC is now ready to boot and can be inserted into the eMMC socket on your PINE64 device.

## Instructions for Flashing Integral eMMC

As an alternative to a removable eMMC module, some devices come with an integral chip that cannot feasibly be removed. These devices include the PinePhone, PinePhone Pro, PineTab, and PineNote. In addition, the following techniques can also be used to flash a removable eMMC when it is not desirable to open the device, when a eMMC to USB adapter is not available, when a second device is not available, or for some other reason.

### Flashing to eMMC from a SD Boot

Some of the available Linux images for Allwinner A64 devices recognise eMMC modules as mounted storage when the device is booted from a micro SD card. This is true for all recent releases of [ayufan’s Linux images](https://github.com/ayufan-pine64/linux-build/releases). In result it is possible to flash an OS image to eMMC using the DD command in terminal or the Disks GUI utility included with the Mate desktop.

There are **two ways** in which an OS image can be flashed from within a micro SD boot:

* Via a script called Pine64_install_to_eMMC.sh found in _/usr/local/sbin_. This script will install an Ubuntu Mate OS installation (identical to the on running on the SD) to the eMMC module. To execute the script navigate to its location in the terminal and type `sudo ./Pine64_install_to_eMMC.sh`. Follow the instructions.
* By manually downloading and flashing a OS image for your device using DD or the Disk GUI. This way of flashing an OS image to the eMMC is identical to that used on a Linux computer (e.g. for flashing an OS image to a SD card). For more information on how the process works please see the detailed guide on [imaging OS images to SD card on Linux](/documentation/Introduction/Getting_started#imaging_microsd_on_linux).

For the latter of the two methods here is a summary of the process:

* Flash an OS image which recognizes eMMC as mounted storage to a micro SD card. For details on how to flash a micro SD card see [section 3](/documentation/Introduction/Getting_started#step_by_step_instructions_for_flashing_microsd_cards)
* Insert both the micro SD and eMMC module into your device and power it on.
* Once the PINE64 device boots from micro SD, you cannot flash the contents of the micro SD card to the eMMC while you are running from the micro SD so you will actually use this session to download an OS image to flash to the eMMC. Depending on the distribution this may be the same image you just flashed to the micro SD card and booted from.
* Once the OS image downloads check in terminal or in Disks utility the eMMC’s mounting location and unmount all but "/". Example command to show disks and mounts:

`$ lsblk`

* Use the DD command or Disks utility to flash the downloaded image to the eMMC module. Note your output device may be mmcblk1 or mmcblk2, use the command above to verify the correct one. Example DD command:

`$ xzcat imagename.img.xz | sudo dd of=/dev/mmcblk1 bs=1M status=progress conv=fsync`

* Once the flashing process is completed power down your device and remove the micro SD card. You should now be able to power your device back up and it will boot the image flashed to the eMMC module.

### Flashing to eMMC using FEL (Allwinner A64 Devices Only)

Under particular circumstances it may prove difficult to rely on a SD card to flash an OS image to an Allwinner A64 device. In such instances OS images can be directly flashed by means of entering into FEL mode. FEL is a low-level subroutine in the BootROM, and the process of enabling FEL differs from one device to another. To learn more about FEL please refer to the [SUNXI Wiki section](https://linux-sunxi.org/FEL) dedicated to the subject.

The process of flashing via FEL is more complex than utilising a micro SD and is therefore **better suited for proficient and advanced users**.

For the process of flashing an image to the eMMC on a device in FEL mode you will need:

* A computer running Mac OS or Linux
* An OTG USB A-to-A cable

To enter FEL you will need to:

* On the Pinebook, power down the Pinebook and remove the PSU, unscrew the bottom of the case and press down the FEL button on the PCB (REF). Plug in the OTG USB A-to-A cord to your computer and the OTG USB port on the Pinebook (on the right facing an open case). Reinsert the PSU cord and press the power button with the FEL button pressed down. Release the FEL button after 3 seconds.
* On the Pine A64(+) power down the board and remove the micro SD card and power cord. Plug in the OTG USB A-to-A cord to your computer and the OTG USB port on the Pine A64 (+) and SoPine (top port). Power on the device and immediately after insert a micro SD card [with FEL code](https://app.box.com/s/s3m7rb5zfe0jkwqhaiy1zytqq3436fqs).

You can check if your device entered FEL mode using _lsusb_ command in terminal. It should be listed as a device on the USB Bus.

The next step is to mount your device so that your computer recognizes the eMMC as mass storage (UMS). A script called boot-tools streamlining this process is available **thanks to ayufan** on [his github](https://github.com/ayufan-pine64/boot-tools). Follow his instructions and in terminal perform the following steps:

`git clone https://github.com/ayufan-pine64/boot-tools.git`

`cd boot-tools`

`make pinebook_ums`

or

`make pine64_ums`

Once your device mounts as UMS it will appear in your file manager. In CLI you can check if the storage is listed using _fdisk -l_.

This process of flashing an OS image to eMMC with the device in FEL mode and mounted as UMS is  **literally identical to imaging micro SD cards**, so please read [Step-by-Step Instructions to Flashing Micro SD Cards](/documentation/Introduction/Getting_started#step_by_step_instructions_for_flashing_microsd_cards) and follow the procedure. You can use DD or Disks/ Disk Utility to flash the OS image directly to your device’s eMMC.

Once the flashing process is completed, power down your device, remove the A-to-A USB OTG cable and after reapply power to boot your device from eMMC.

### Flashing to eMMC using Rockchip Tools (Rock64 Only)

Rockchip has a different boot hierarchy to Allwinner’s devices making it much more difficult to flash OS images using the micro SD-to-eMMC scheme used on A64. There are, however, flashing tools that make it possible to flash directly to eMMC on a Rock64 in loader and MarkROM modes.

To flash to the eMMC module using these tools you will need the following:

* A Windows, Mac OS or Linux computer
* An A-to-A USB cable
* The Rock64 board with the eMMC module inserted into the socket

Using Windows 7/8.1/10:

You will need to download the [DriverAssistant aka Rockchip driver](https://github.com/rockchip-linux/tools/tree/master/windows) as well as the [AndroidTool_Release](https://github.com/rockchip-linux/tools/tree/master/windows) used for flashing OS images. Having completed the downloads extract both archives.The Rockchip driver needs to be installed prior to using the AndroidTool utility.

Having installed the driver and flashing utility, follow these steps:

* Make sure that eMMC is inserted into the slot on the Rock64
* Place a jumper / short out the eMMC pins on the board (consult [this PDF document](https://files.pine64.org/doc/rock64/guide/ROCK64_Installing_Android_To_eMMC.pdf) for more details.
* Insert one end of the A-to-A cable into your Windows PC and the other into your Rock64 OTG USB port (top)
* Inset the power cord into the Rock64
* Start AndroidTool; make sure that it reports 'Found One Maskrom Device' (if it does not recognise your device, please repeat previous steps)
* Select either the latest Stock Android build or ayufan’s Android TV build with the suffic -update. Download and the extract the chosen image.
* In AndroidTool press the firmware tab and navigate to where you extracted the OS image and select it.
* Press the upgrade tab. You will be prompted when the flashing process is completed.
* Remove the USB A-to-A cable, power off your board and power it on again to boot into eMMC.

Using Linux or Mac OS:

* Make sure that eMMC is inserted into the slot on the Rock64
* Download latest stable or pre-release (to be used at own risk) Android TV OS image from [ayufan’s github](https://github.com/ayufan-rock64/android-7.1/releases). The image you wish to download is the one **without a suffix**; without -update or -raw in the OS image title.
* In terminal, download rkflashtool following instructions on [ayufan’s github](https://github.com/ayufan-rock64/android-7.1/blob/master/README.md)
* Extract the folder containing partitions of the OS image and place the script listed on ayufan’s github in the folder
* Hold down the recovery button on the board
* Insert one end of the A-to-A cable into your Mac OS or Linux PC and the other into your Rock64 OTG USB port (top)
* Inset the power cord into the Rock64
* Check that your device is in loader mode by typing in the terminal `sudo rkflashtool n`. If rkflashtool doesn’t detect the Rock64 please repeat last 3 steps
* In terminal navigate to where you extracted the Android folder containing the OS partitions and the script and type `rkinstall`; this will install the community Android TV build to eMMC.
* Remove the USB A-to-A cable, power off your board and power it on again to boot into eMMC.

### Flashing to eMMC Android 'Update' OS Images on Linux (Rock64 Only)

It is possible to flash Android 'update' images to the Rock64 eMMC using a Linux PC. This process requires a tool called [Linux Upgrade Tool](https://www.haoyuelectronics.com/service/RK3066/tools/linux/Linux_Upgrade_Tool_v1.2.tar.gz) and the full documentation of its functions can be found [here](https://www.hotmcu.com/wiki/Flashing_Firmware_Image_Files_Using_The_Rockchip_Tool#Using_Linux_Upgrade_Tool_to_flash_update.img). Make sure that you download v1.2 or newer, as older tools do not support the RK3328 used on the Rock64.

To flash the eMMC module using this method you will need the following:

* A Linux computer
* An A-to-A USB cable
* The Rock64 board with the eMMC module inserted into the socket

Start by downloading an Android **update** image for the Rock64. Both PINE64 and Ayufan provide such images for the board - and they are clearly designated as such on both this WiKi’s download section and on ayufan’s github. For the purpose of this example, I’ll use the ayufan’s ATV community build:

* Download latest stable or pre-release (to be used at own risk) Android TV OS image from [ayufan’s github](https://github.com/ayufan-rock64/android-7.1/releases). The image you wish to download is the one **with update suffix**. You need to **rename the downloaded image to update.img**.
* Download the [Linux Upgrade Tool](https://www.haoyuelectronics.com/service/RK3066/tools/linux/Linux_Upgrade_Tool_v1.2.tar.gz) to your Linux PC and unarchived it.
* Extract the archived update Android OS image somewhere where you will remember its path
* Hold down the recovery button on the board
* Insert one end of the A-to-A cable into your Mac OS or Linux PC and the other into your Rock64 OTG USB port (top)
* Inset the power cord into the Rock64
* In terminal, navigate to where you extracted Rockchip Update Tool and issue the following command substituting the correct path for where the Android Update OS Image is located:

`sudo ./upgrade_tool uf /path/to/update.img`

* Wait as the utility installs Android to eMMC on your Rock64.
* Remove the USB A-to-A cable, power off your board and power it on again to boot into eMMC.

## Flashing u-boot to SPI Flash

Some of PINE64 devices, such as the Rock64 and SOPine, are equipped with SPI Flash. This allows users to flash u-boot onto the SPI and boot from an external USB 2.0 or USB 3.0 SSD/HDD/thumb-drive, thereby forgoing use of eMMC or microSD card.

To find out more about which images can used in conjunction for SPI booting please see [ayufan’s github](https://github.com/ayufan-rock64/).

Writing u-boot to SPI Flash can be achieved in two ways:

### Using a Stand-Alone Image to Write u-boot to SPI

This may be the simplest method of flashing u-boot to SPI. Download a dedicated image labelled **u-boot-flash-spi.img.xz** from [ayufan’s github](https://github.com/ayufan-rock64/linux-u-boot/releases) and flash it to a microSD card, the same as you would with any OS image (to learn how to flash OS images to microSD please follow steps outlined in [Section 3](/documentation/Introduction/Getting_started#step_by_step_instructions_for_flashing_microsd_cards).

**Having flashed the image follow these steps**:

* Insert the SD into the ROCK64
* Remove all other peripherals from the board
* **Make sure that the eMMC module is disconnected from the board**
* Apply power to the ROCK64
* Wait (few seconds) until the the LEDs on the board will blink continually
* Power off the board.

The board is now ready to boot from USB 2.0/3.0 storage.

### Using a Script on Linux OS Images

Most of recent (newer than 0.6.9) Linux OS images contain a script called **rock64_write_spi_flash.sh**, which is found in _/usr/local/sbin_ directory. To run the script you will first need to flash a Linux OS image to a micro SD card (to learn how to flash OS images to micro SD please following steps outlined in [Section 3](/documentation/Introduction/Getting_started#step_by_step_instructions_for_flashing_microsd_cards)). Before proceeding **make sure that the eMMC module is disconnected** from the board. Once you have booted into Linux on your PINE64 device all you have to do is run the aforementioned script using this command:

`sudo ./rock64_write_spi_flash.sh`

Once the script finishes its operation, power off your board and remove the microSD card.
The board is now ready to boot from USB 2.0/3.0 storage.

### Erasing and Rewriting SPI

There are two ways of removing u-boot from SPI. You can either download **u-boot-flash-spi.img.xz** from [ayufan’s github](https://github.com/ayufan-rock64/linux-u-boot/releases) or use a script found on Linux OS images titled:**rock64_erase_spi_flash.sh**. Follow the instructions in the previous sub-sections for the chosen method of removing u-boot from SPI; the instructions are are identical, as the process of erasing u-boot is the exact opposite of flashing it.

**💡 TIP**\
You can also erase SPI manually.
To do so, you need to download mtd-utils. on Debian or Ubuntu follow these instructions:

`sudo apt-get install mtd-utils`

`sudo flash_eraseall /dev/mtd0`

### Booting an OS image from USB 2.0/3.0 Storage

To boot an OS image from USB 2.0/3.0 Storage such as a SSD/HDD or a thumbdrive you first need to have u-boot written to your SPI flash. Please follow the instructions in the previous sub-sections to learn how to write u-boot to SPI on your PINE64 device.

Once you have u-boot on your SPI, the process of booting is very similar to booting from microSD or eMMC.

* Download one of the supported OS images for your PINE64 device
* Flash the OS image to your USB 2.0/USB 3.0 storage device (to learn how to flash OS images please following steps outlined in [Section 3](/documentation/Introduction/Getting_started#step_by_step_instructions_for_flashing_microsd_cards) The instructions are identical for all types of storage, including USB 2.0/USB 3.0 HDDs and thumb-drives.)
* Insert the USB storage device with the flashed OS image into one of the USB ports on your PINE64 device
* Apply power

If you have followed all the steps correctly, the board should boot from your USB 2.0/3.0 storage device.

## Troubleshooting

{{% docs/construction %}}

A number of things can prevent the PINE64 board from booting up properly. The most common culprits of a failed boot are: (to find out more click [here](https://forum.pine64.org/showthread.php?tid=514))

* Subpar or counterfeit microSD card
* Subpar Power Supply
* High resistance (thin) or a very long microUSB cable
* Failed imaging of the microSD card or eMMC module

Make sure to have the newest version of the OS image your are running. On Allwinner A64 devices running Linux you can update the kernel and U-Boot using scripts located in the following directory: /usr/local/sbin

* To navigate to the directory type (in terminal): `cd /usr/local/sbin`
* You list all the available scripts by typing (in terminal): `ls`
* To run the script required update script run the following command: `sudo ./update_script.sh` (substitute the relevant update script for `update_script`)

**Troubleshooting Step by Step**

Follow these steps to determine the cause of your problem:

* Check your PSU and microUSB cable ratings
* Download and image a base image of Linux
* Plug in power and Ethernet into your PINE64 device
* Watch Ethernet port LED activity
* Check your router for your device’s IP
* Attempt to ssh into your device’s from your computer

If your PSU and microUSB meet the criteria, and you have correctly followed the instructions to image your card and power on the board, but you are not seeing any LED activity and cannot ssh into your device then either the imaging process failed (possibly due to a subpar microSD) OR the PSU / microUSB cable is/are faulty.

If your PSU and microUSB meet the criteria, and you have correctly imaged the OS to your card and power on the board and your can ssh into your PINE A64(+) but get no video feed, then it’s likely that the native resolution of your monitor/TV is not supported.

If neither of the above mentioned scenarios fits the problem you are facing, please consult this thread (thanks to Ghost for compiling the list): https://forum.pine64.org/showthread.php?tid=680
