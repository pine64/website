---
title: "Developer Edition"
draft: false
hidden: true
menu:
  docs:
    title:
    parent: "PinePhone_Pro/Revisions"
    identifier: "PinePhone_Pro/Revisions/Developer_Edition"
    weight: 
---

The Developer Edition was the first edition of the [PinePhone Pro](/documentation/PinePhone_Pro), shipped to developers in December 2021. The aim of the the Developer Edition was to give development community access to the hardware prior to end-users, boost development efforts and allow for porting of existing mobile Linux operating systems to the new hardware. It featured a factory test installation of AOSP as pre-installed operating system and was shipped with the packaging and manual of the succeeding Explorer Edition.

## Getting started

This documentation page is strictly aimed at developers receiving their PinePhone Pro dev units. Please note that the following instructions do not apply to Explorer Edition or other future editions of the PinePhone Pro - everything below is only pertinent to the dev phones.

Consider this a crash course rather than a comprehensive overview; you are also welcome to participate in documenting the process (and everything else related to the PinePhone Pro) on the documentation.

### Getting the hardware ready

After unpacking the PinePhone Pro from its box, detach the back cover (looking at the back of the phone, there is a fingernail notch on the left leading edge) and remove the plastic tab between the battery and mainboard. You can also flip the headphone jack privacy switch at this point - this enables UART output via the headphone jack. Serial console works the same way as on the original PinePhone.

## Factory hardware test image

The PinePhone Pro developer edition ships with a BSP AOSP factory image flashed to the eMMC. This image includes a number of factory applications meant to validate operation of the sensors, the modem, cameras, LCD & touch panel, etc. You’ll have to nuke the AOSP build to run a Linux installation on the PinePhone Pro. Booting from SD with the AOSP factory build present on eMMC is not possible due to the SoCs native boot order.

### Changing the language of factory AOSP

This is optional and only if you want to test out the AOSP test image.

1. Swipe up from the bottom of the screen.
2. Tap on the Gear icon.
3. Tap on the 2nd from last option that has an i inside of a circle icon.
4. Tap on the first choice with the globe icon.
5. Tap on the first choice with the language icon.
6. Tap on the second choice to add another language.
7. Tap on your language in the list.
8. If there is a secondary choice required, tap on the preferred country.
9. Tap the four horizontal bars icon to the right of the new second language and drag to the top of the list to set the new language as the default.

### Backing up the factory AOSP

It may be a good idea to create an image of the eMMC in case you want to flash it back. Free up at least 117GB of disk space. Install `adb`.

`adb root && adb pull /dev/block/mmcblk1 ~/pinephonepro-factory-AOSP.img`

### Nuking the factory AOSP installation

To be able to boot from the microSD card easily it is recommend to wipe the bootloader from the pre-installed operating system on the eMMC due to the eMMC being higher in the boot priority than the microSD card.

#### Method 1: Via ADB

In the factory test image, navigate to setting (gear icon) > at the very bottom of the settings list you will find a phone icon with rk3999mid written underneath it > tap the last (bottom) setting 7 times in quick succession. Following this, you **may** need to do the following: open the Settings application and enable USB debugging in Settings > System > Developer Options > USB debugging. Then connect the PinePhone Pro to your PC with the supplied USB-C cable.

Please note: It is recommended to charge the device to at least 50% before proceeding with wiping the eMMC.

**💡 TIP**\
Note: You may have gotten a Chinese factory image; in the settings menu you can change the language to English by selecting the gray info icon (系统, one from bottom), then the first option (语言..), and again the first option (also 语言), then press +, English and drag it to the top of the list).

Connect the phone to your computer and check `adb devices` in the terminal. The phone should be registered as attached. If the device doesn’t show you may want to try a different port or cable. Then enter `adb shell` followed by `su` to gain root access. At this point you can erase the eMMC installation:

`cat /dev/zero > /dev/block/mmcblk1`

The phone will freeze and then the screen will go blank. Let it sit for no less than 10 minutes and then power it off by holding down the power button. You’ll know the phone is powered down when the notification LED turns off.

#### Method 2: Via serial cable

Another method of erasing the image is to connect serial console, break into U-Boot when it says to press Ctrl-C, and then the "mmc erase" command can be used to zero blocks on the eMMC. For example, "mmc erase 0 16384" will zero the first 8MB, and is enough to stop it from being bootable. The baud rate for the serial console is 1500000.

### Flashing Linux

You will want to do all your testing and development on a SD card; you DO NOT want to flash an OS to eMMC at this time. Builds frequently break at this early development stage and recovering from a corrupted eMMC installation is presently time consuming and tedious. A fast 16-64GB micro SD card for $15 will work just fine.

There are a handful of OS builds available for the PinePhone Pro already. These can be found under the [Software Releases](/documentation/PinePhone_Pro/Software/Releases) section.

If you are a developer porting your own distribution to the PinePhone Pro, please make sure to make an entry for it in the Software Releases section on the documentation. If you want / need help with entering your build onto the documentation please ping one of the mods or admins in the chats (see Forums and Chats drop-down menu).

## Resources

Aside from the PINE64 documentation there are also other useful resources scattered across different Wikis, repositories and blogs. In time these will be gathered into one place - the [DevZone](https://gitlab.com/mobian1/devices/eg25-manager/-/merge_requests/41#note_744117720) - which will help to streamline the development process.

At the time of publishing, these are some of the notable resource, listed in no particular order:

* [postmarketOS Wiki](https://wiki.postmarketos.org/wiki/PINE64_PinePhone_Pro_(pine64-pinephonepro))
* [Megi’s (b)log](https://xnux.eu/log/)
* [DanctNIX repository](https://github.com/dreemurrs-embedded/Pine64-Arch/)
* [Manjaro repository](https://github.com/manjaro-pinephone)
* [Development](/documentation/PinePhone_Pro/Various/Development)
