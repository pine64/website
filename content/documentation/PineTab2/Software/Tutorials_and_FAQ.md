---
title: "Tutorials and FAQ"
draft: false
menu:
  docs:
    title:
    parent: "PineTab2/Software"
    identifier: "PineTab2/Software/Tutorials_and_FAQ"
    weight: 3
---

This is a collection of tutorials and frequently asked questions for the PineTab2.

## Tutorials

### Putting the Device into Maskrom Mode

To recover from a bad eMMC/SPI flash, plug the included debug adapter into the charging USB-C port and switch the white switch to its "ON" position to bypass eMMC/SPI boot. This tries to boot from SD, and if no SD is inserted, enters Maskrom mode.

### Networking using USB

Until the internal BES2600 WIFI has a stable driver, the community suggests that you connect using USB. This section summarizes the more detailed information in [File:PineTab2_USB_Guide.pdf](https://wiki.pine64.org/wiki/File:PineTab2_USB_Guide.pdf), which covers connecting via a tethered Android phone, a suitable USB WIFI adapter, a wired USB Ethernet adapter, and a tethered iOS device.

#### Selecting a USB WIFI Adapter

Insert a supported WIFI dongle in the upper USB port, using a USB-C to USB-A adapter as necessary. As a general rule, single state adapters are recommended. Even better, select one from this list: https://github.com/morrownr/USB-WiFi/blob/main/home/The_Short_List.md

If you must use a multi-state adapter and it isn’t recognized by the kernel, you can try ejecting the device. This _should_ force it back into adapter mode. If this does not work, you can try installing [usb_modeswitch](https://man.archlinux.org/man/usb_modeswitch.1.en) to troubleshoot. You will need to temporarily use another method to get internet (such as phone tethering below) or load the package on an SD card to install it.

#### Performing USB Tethering with an Android Phone

This guide simply describes HOW to undertake this option. The user is responsible for ensuring that their wireless plan permits such use, and for any fees incurred.

You can use an Android phone as a network adapter.

You’ll need:

* An Android phone
* A USB OTG adapter (or the USB-C to USB-C cable)
* Some knowledge of your variation of Android

Do the following in order:

* Plug in the device to the PineTab2 using the USB cable and a USB OTG adapter
* On your android phone, open the settings app (specifics from here may vary on version)
  * Navigate to "Network & Internet"
  * Navigate to "Hotspot & Tethering"
  * Tap on "USB Tethering"

You should now see a new network interface on the PineTab2.

#### Performing USB Tethering with an iPhone

Prerequisite:

On the iPhone make sure that Settings -> Personal Hotspot -> Allow others to join is turned on.

1. Use an Lightning (Apple) to USB-C (Pinetab2) cable to connect the devices.
2. In the Pinetab make sure to use the USB-C port next to the volume keys.
3. Once the cable is connected open your iPhone.
4. You will see a request to trust the new device. Trust it.
5. Confirm by typing in your Apple Device PIN

This should be it. The Pinetab2 will show you the new device and the network connects to `Wired connection 1`

Make sure to open the iPhone once you reconnect.

#### Performing USB Tethering with a KaiOS phone

This guide simply describes HOW to undertake this option. The user is responsible for ensuring that their wireless plan permits such use, and for any fees incurred.

You can use a KaiOS phone for mobile Internet use with your PineTab2.

You’ll need:

* A KaiOS phone
* A USB OTG adapter
* Your device’s charging cable
* Some knowledge of your KaiOS phone

Do the following in order:

* Plug the device into the PineTab2 using the USB cable and a USB OTG adapter
* On your KaiOS phone, open settings (specifics from here may vary on version)
* Navigate to "Network & Connectivity"
* Navigate to "Internet Sharing"
* Select "USB" and select On under USB tethering (Note: This option will be greyed out unless connected to the PineTab2)

You should now see a new network interface on the PineTab2 and it should show a wired connection icon.

### Screen Rotation
#### Auto-rotating the Screen
Auto-rotation is handled by your operating system. However, the following general steps should work on distributions that support iio-sensor-proxy:

* To enable auto-rotation, install the iio-sensor-proxy package: `sudo pacman -S iio-sensor-proxy` and reboot.
* Some desktop environments, such as KDE, default to only allowing screen rotation while in tablet mode (detached from the case.) To enable it with the keyboard attached, go to System Settings-->Display and Monitor -> Display Configuration -> Uncheck "Only when in tablet mode" and click "Apply."

#### Rotating the Login Screen
Login screen orientation is handled by your operating system. Below are the instructions for the SDDM login screen that ships with the factory image:

By default, the login screen is set to display in portrait mode. If you wish to change it to landscape mode to match the keyboard while in the case, use the following steps ([Credit to chzbacon](https://forum.pine64.org/showthread.php?tid=18313)) :

* Install necessary software: `sudo pacman -S xorg-xrandr xorg-xinput`
* Edit /usr/share/sddm/scripts/Xsetup. For example, using nano: `sudo nano /usr/share/sddm/scripts/Xsetup` and add the following two lines to the end of file:
  * `xrandr --output DSI-1 --mode 800x1280 --rate 60.00 --rotate right`
  * `xinput set-prop "pointer:Goodix Capacitive TouchScreen" --type=float "Coordinate Transformation Matrix" 0 1 0 -1 0 1 0 0 1`
* Now edit /etc/sddm.conf.d/sddm.conf, for example: `sudo nano /etc/sddm.conf.d/sddm.conf` and add the following two lines (case sensitive):
  * `[X11]`
  * `DisplayCommand=/usr/share/sddm/scripts/Xsetup`
* Reboot, and your login screen should now display in landscape mode.

## Frequently Asked Questions

### General

#### How does the PineTab2 compare to the Pinebook Pro?
It’s slower, as it is intended to be a successor to the PineTab1, not the Pinebook Pro. It’ll still handle web browsing, video playback and documents fine though.

#### What is the Performance of the PineTab2 compared to the PineTab-V?
The PineTab2 is notably faster than the PineTab-V. You can see this by [comparing the Quartz64 sbc-bench results to the Star64 ones](https://github.com/ThomasKaiser/sbc-bench/blob/master/Results.md). Performance should not be a factor of consideration when purchasing a PineTab-V.

#### I am a casual user with minimal Linux experience. Is this device for me?
The PineTab 2 is considered early release at this point, and the community is expected to develop support for it over time. For example, the [Known issues](/documentation/PineTab2/Development/Known_issues) page details several features that are not yet fully working. You may at times need to troubleshoot this device and some development experience is ideal if you want to realize the tablet’s full potential at this stage.

For these reasons, the PineTab2 may not be the ideal device for casual users. However, if you feel up to the challenge and want to learn while joining a great community, you are more than welcome! Please join one of our chat platforms: the community is always happy to help!

#### What works, what doesn't?

Please see [Known issues](/documentation/PineTab2/Development/Known_issues).

#### I only know Python, can I help with drivers?
Drivers are (at least typically) written in the C programming language. Unfortunately, there is no way to "code drivers in Python" because usually drivers need to access and process memory allocation directly. If you feel like this is interesting to you, we suggest you to spend some time learning the C programming language, maybe with an emphasis in device driver development. The good news is that, since you already know a programming language, you already know part of the skill.

In short, you can only help with drivers development if you learn the C programming language first.

### Hardware

#### Does the Tablet support a Pen?
No, adding a digitiser for pen inputs would make the price too high.

#### Is there SPI Flash?
Yes! A 128 Mbit flash chip (sk25lp128) is reportedly present on production devices.

### Software
#### What operating systems are currently available?
The PineTab2 uses ARM operating systems. Please see [Software](/documentation/PineTab2/Software/Releases) for a current list of software releases.

#### How can I install an operating system on the SD card / eMMC?

See the article [Software](/documentation/PineTab2/Software).

#### Can I run Android on it?

Theoretically yes, practically there’s little chance anyone wants to make a well-supported Android build for this device. If you’re looking for an Android tablet, buy any mainstream tablet, and you’ll get better value for your money.

However, if you just need to run a few simple android apps, you might want to have a look at [Waydroid](https://docs.waydro.id/usage/install-on-desktops) which can be installed on Arch Linux ARM using the following command: `sudo pacman -S waydroid`

### Booting

#### What's the boot order for SD cards and eMMC?

The SPI and the internal memory (eMMC) have a higher boot priority than the microSD card. Please see the [Software](/documentation/PineTab2/Software) for more detailed information.

#### Can I install a different OS on my PineTab2?

Yes! While all PineTab2 come with an OS preinstalled, you are free to use any OS on the integrated storage (the eMMC) or an SD card. See [Software](/documentation/PineTab2/Software) for how to install them.

### Bluetooth

#### The Bluetooth isn't working

The BES2600 Bluetooth driver still needs to be implemented. Please see the _Networking Using USB_ section above for a workaround.

### Wi-Fi

#### The Wi-Fi isn't working
The [BES2600 Wi-Fi driver](https://gitlab.com/TuxThePenguin0/bes2600) needs major cleanup and bugfixing: at the moment it causes system crashes. Please see the _Networking Using USB_ section for a workaround.

### Video

#### Can PineTab2 play back DRM content such as Netflix?

Yes, though the specific implementation depends on your installed operating system.

On the default Arch Linux Arm: Widevine, using the `widevine-aarch64` package in the AUR is working, and was demonstrated on the PineTab2 using Paramount+ and Disney+. Install it (`yay -S widevine-aarch64`), run the included register script to get Firefox to recognize it, and it should start working.
