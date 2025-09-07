---
title: "Tutorials and FAQ"
draft: false
menu:
  docs:
    title:
    parent: "PineTab2/Software"
    identifier: "PineTab2/Software/Tutorials_and_FAQ"
    weight: 3
aliases:
  - /wiki/PineTab2_FAQ
---

This is a collection of tutorials and frequently asked questions for the PineTab2.

## Tutorials

### Putting the Device into Maskrom Mode

To recover from a bad eMMC/SPI flash, plug the included debug adapter into the charging USB-C port and switch the white switch to its "ON" position to bypass eMMC/SPI boot. This tries to boot from SD, and if no SD is inserted, enters Maskrom mode.

### Recovery from non-booting device
{{< admonition type="warning" >}}
You cannot use a virtual machine for this tutorial as rkdeveloptool does not function as intended.
{{</ admonition >}}

{{< admonition type="note" >}}
Before trying this, try the Maskrom instructions above by changing the debug adapter switch to "ON" to bypass the internal storage to boot the factory image off an SD Card. If this doesn't work you may proceed with this tutorial. 
{{</ admonition >}}

There may be situations where the device refuses to turn on and you cannot see anything coming up through UART. This may indicate that your device is bricked. The PineTab2 includes a debug adapter which allows the user to access Maskrom mode. On it's own this mode is useless as the user requires a miniloader from Rockchip to access any rkdeveloptool commands. 

**Install rkdeveloptool**

First you must install rkdeveloptool if you haven't already. You can find instructions on the [Rockchip wiki](https://opensource.rock-chips.com/wiki_Rkdeveloptool).

**Clone**

`git clone https://github.com/rockchip-linux/rkdeveloptool.git`

**Install dependencies**

`sudo apt-get install libudev-dev libusb-1.0-0-dev dh-autoreconf pkg-config libusb-1.0`

**Compile**
```
autoreconf -i
./configure
make
make install
```

**Put device into Maskrom mode**

{{< figure src="/documentation/PineTab2/images/PineTab2_USB_UARTv2.jpg" caption="The debug adapter, bottom port is for UART and the top one is for maskrom" width="450" >}}

Turn off your PineTab2 by holding the power button for around five seconds. Then grab your debug adapter, make sure the Maskrom switch is in the "ON" position, plug it into your PineTab2 and plug a USB-C cable into the top port and into your computer.  

Check that your device is in Maskrom mode by typing `lsusb` into a terminal. If it displays `Fuzhou Rockchip Electronics Company Device` then it has successfully entered Maskrom mode. 

**Troubleshooting**
* If you only see `QinHeng Electronics USB Serial` (UART) either try switching USB-C ports on the adapter or plugging in both adapter ports into your computer. 

**Boot miniloader using Maskrom**

To issue any commands using `rkdeveloptool` you must first load a Rockchip miniloader through Maskrom.

{{< admonition type="note" >}}
The zip is hosted directly on this website.
{{</ admonition >}}

**[Download MiniLoaderAll.bin.zip](/documentation/PineTab2/files/MiniLoaderAll.bin.zip)** 

Once you download and unzip the miniloader, issue this command using `rkdeveloptool`.

`rkdeveloptool db MiniLoaderAll.bin`

{{< admonition type="note" >}}
This command downloads the loader to the device temporarily. If you powered off the device and wish to enter Maskrom and issue `rkdeveloptool` commands you must follow the above instructions again. 
{{</ admonition >}}  

Once the command completes, wait for the device to reappear in `lsusb`. Make sure it has a different name than before. **Be patient as it can take ~20 seconds**.

`Fuzhou Rockchip Electronics Company Device USB-MSC`

**Recovery to factory firmware**

To make sure the only boot option for the device is via SD Card, erase the internal storage. 

`rkdeveloptool ef`

You will have to wait for a while until it has finished. Once the command has completed, force power off the device and place an SD Card with the DanctNix factory firmware into the card slot.

**Download factory image**

https://echo.danctnix.org:7269/factory_images/pinetab2/

{{< admonition type="note" >}}
The factory image is flashed to a microSD card and it will overwrite the eMMC installation after booting.
{{</ admonition >}}

{{< admonition type="info" >}}
Newer images use the **volume and power button for selection** at boot instead of the keyboard.
{{</ admonition >}}

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
