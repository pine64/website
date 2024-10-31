---
title: "Touchpad"
draft: false
menu:
  docs:
    title:
    parent: "Pinebook_Pro/Features"
    identifier: "Pinebook_Pro/Features/Touchpad"
    weight: 
---

Documentation for the touchpad can be found in [Datasheets for Components and Peripherals](/documentation/Pinebook_Pro/Further_information/Datasheets/). It is the only component of the Pinebook Pro held in place with strong adhesive tape. Here are some of its features:

* 2 actuating buttons.
* multi-touch functionality.
* A matte finish that your finger can slide along easily.
* A reasonable size (96 mm × 64 mm; diagonal: 115.378 mm or 4.542 inches).

## Troubleshooting

If you are having trouble using 2 fingers to scroll or emulate the click of a mouse’s right-button, then try these solutions:

* Update the firmware.
* Keep your 2 fingers spread apart rather than close together.
* Individual programs might need to be configured specially.
*. For smooth scrolling and gestures under X-Windows, _Firefox_ should be launched with with the following environment variable assignment:

`MOZ_USE_XINPUT2=1`

* Experiment with other settings, via X-Windows Configuration or some other system preferences. For example, you could disable double-finger scrolling, and instead enable scrolling by sliding one finger along the edge of the touchpad.

## Firmware

The touchpad controller is connected to the keyboard controller. All touchpad events go through the keyboard controller and its software, then to the keyboard controller’s USB port. Note that the touchpad does have separate firmware (which has to be written through the keyboard controller). The touchpad vendor’s firmware binary can be flashed from userspace using the following open source command-line utility:

* Kamil Trzciński’s [pinebook-pro-keyboard-updater](https://github.com/ayufan-rock64/pinebook-pro-keyboard-updater).

Naturally, forks have begun to appear:

* Jack Humbert’s [fork](https://github.com/jackhumbert/pinebook-pro-keyboard-updater)
* Dragan Simic’s [fork](https://github.com/dragan-simic/pinebook-pro-keyboard-updater). This one has recently delivered a much improved firmware from the vendor one, which greatly improves the control of the cursor (see this [thread](https://forum.pine64.org/showthread.php?tid=14531) for discussion). Before installing this update, consider resetting to the defaults any configuration of your touchpad.

**All Pinebook Pros shipped from the factory have the old buggy version installed so consider updating the keyboard and touchpad firmware with the latest fixes from Dragan.**

{{< admonition type="warning" >}}
 DO NOT update the touchpad firmware before checking which keyboard IC your Pinebook Pro has. Some Pinebook Pro were delivered with a _SH61F83_ instead of a _SH68F83_. The SH61F83 can only be written 8 times, this will render the keyboard and touchpad unusable if this limit is reached when step 1 (see below) is flashed. See [Reddit SH61F83 thread](https://reddit.com/r/PINE64official/comments/loq4db/very_disappointed/). The keyboard IC corresponds to _U23_ on the [top layer silkscreen of the main board](/documentation/Pinebook_Pro/Further_information/Schematics_and_certifications/). It is located under the keyboard flat flexible cable. All the PBPs from the post-pandemic batches have _SH61F83_ but TL Lim claimed they can be flashed just the same. No updated datasheet or a statement from the MCU vendor was provided though, so proceed at your own risk. Experience shows flashing those works for at least one time.
{{< /admonition >}}

Before updating _any_ firmware, your Pinebook Pro should be either fully charged or, preferably, running from mains. This utility will be writing data to chips on the keyboard and touchpad, so a loss of power during any stage of the update can result in irrecoverable damage to your touchpad or keyboard.

The scripts ought to work on all operating systems available for the Pinebook Pro. Some operating systems may however, require installation of relevant dependencies. The instructions below assume a Debian desktop. To install these dependencies, newer Pinebook Pro models that come with Manjaro will require a different command.

There are two keyboard versions of the Pinebook Pro: ISO (vertical Enter key) and ANSI (horizontal Enter key). You need to know which model you have prior to running the updater.

Firmware update steps for both models are listed below.

What you will need:

* Connection to internet for getting dependencies, either through Wi-Fi or wired ethernet (USB dongle).
* Your Pinebook Pro fully charged or running from mains power.
* An external USB keyboard and mouse (or access to the Pinebook Pro via SSH. Please note that for some configurations, the SSH service might not be available without first having logged in once. In this case, you will definitely want at least an external keyboard or UART serial console).

### ISO Model

From the terminal command line:

Debian-based distributions:

    git clone https://github.com/dragan-simic/pinebook-pro-keyboard-updater
    cd pinebook-pro-keyboard-updater
    sudo apt-get install build-essential libusb-1.0-0-dev xxd
    make

Arch-based distributions (note: [build-essential](https://www.garron.me/en/bits/build-essential-arch-linux.html), [xxd](https://aur.archlinux.org/packages/xxd-standalone) are named differently. Arch linux [does not split its packages](https://bbs.archlinux.org/viewtopic.php?id=44950) as foo and foo-dev):

    git clone https://github.com/dragan-simic/pinebook-pro-keyboard-updater
    cd pinebook-pro-keyboard-updater
    sudo pacman -Syu base-devel xxd-standalone libusb
    make

The next steps are identical for both Debian and Arch distros.

Step 1

    cd pinebook-pro-keyboard-updater
    sudo ./updater step-1
    sudo poweroff # do not use 'reboot'

Step 2 (after booting)

    cd pinebook-pro-keyboard-updater
    sudo ./updater step-2 iso
    sudo poweroff # do not use 'reboot'

### ANSI Model

{{< admonition type="note" >}}
 Running step 1 on the ANSI keyboard model will make the keyboard and touchpad inaccessible until step 2 is run, so an external keyboard must be connected to complete the update on this model!
{{< /admonition >}}

From the terminal command line:

Debian-based distributions:

    git clone https://github.com/dragan-simic/pinebook-pro-keyboard-updater
    cd pinebook-pro-keyboard-updater
    sudo apt-get install build-essential libusb-1.0-0-dev xxd
    make

Arch-based distributions (note: [build-essential](https://www.garron.me/en/bits/build-essential-arch-linux.html), [xxd](https://aur.archlinux.org/packages/xxd-standalone) are named differently. Arch linux [does not split its packages](https://bbs.archlinux.org/viewtopic.php?id=44950) as foo and foo-dev):

    git clone https://github.com/dragan-simic/pinebook-pro-keyboard-updater
    cd pinebook-pro-keyboard-updater
    sudo pacman -Syu base-devel xxd-standalone libusb
    make
	
The next steps are identical for both Debian and Arch distros.

Step 1

    cd pinebook-pro-keyboard-updater
    sudo ./updater step-1
    sudo poweroff # do not use 'reboot'

Step 2 (after booting)

    cd pinebook-pro-keyboard-updater
    sudo ./updater step-2 ansi
    sudo poweroff # do not use 'reboot'

When done, if some of the keys produce incorrect characters, please check your OS’s language settings. For ANSI users, the default OS may have shipped with English UK as the default language. You can change it to English US if desired.

### Revised Firmware

In addition, you might consider using revised firmware data. This is one final step that should not require a reboot:

Step 3: **ISO** (after booting)

    sudo ./updater flash-kb firmware/default_iso.hex

Step 3: **ANSI** (after booting)

    sudo ./updater flash-kb firmware/default_ansi.hex

## X Window System Configuration

{{< admonition type="note" >}}
 Before making adjustments, consider updating the firmware. Reset your adjustments before updating the firmware, so that your adjustments do not interfere with new functionality.
{{< /admonition >}}

When using X.Org display server the touchpad can be handled either by _libinput_ or _synaptic_ input drivers. The former allows to have shared configuration for both X.Org and Wayland but the latter provides more tunables (e.g. configurable edge scrolling, circular scrolling, mapping of multi-touch events to mouse buttons etc.).

Some forum members have found that an adjustment to X11 will allow finer motion in the touchpad. If you use the _synaptic_ mouse/touchpad driver, use this command to make the change live:

    synclient MinSpeed=0.2

You may experiment with different settings, but 0.25 was tested as helping noticeably.

To make the change persist across reboots, change the file **/etc/X11/xorg.conf** similar to below:

    Section "InputClass"
           Identifier "touchpad catchall"
           Driver "synaptics"
           MatchIsTouchpad "on"
           MatchDevicePath "/dev/input/event*"
           *Option "MinSpeed" "0.25"*
    EndSection

The line "Option "MinSpeed" "0.25"" is changed here.

Another forum user built on the above settings a little, and have found these to be very good:

    synclient MinSpeed=0.25
    synclient TapButton1
    synclient TapButton2=3
    synclient TapButton3=2
    synclient FingerLow=30
    synclient PalmDetect=1
    synclient VertScrollDelta=64
    synclient HorizScrollDelta=64

_FingerLow_ has the same value as 'FingerHigh' in one config (30). It is believed to help reduce mouse movement as you lift your finger, but it’s unknown whether synaptic works like this.
You may find this config to be comfortable for daily use.

_TabButton_ allows to just tab the touchpad instead of physically pressing it down (to get this click noise).

The right mouse click is emulated by tapping with two fingers on the touchpad. If you feel that this is not very responsive you can try this value:

    synclient MaxTapTime=250

Some users may encounter an issue with the mouse jumping when typing when using libinput driver due to their hand hitting the touchpad which can be fixed by updating the X.Org settings to disable it while typing. One can disable the touchpad while typing by setting the below option in the X.Org config simliar to the previous example.

    Option "DisableWhileTyping" "on"

The setting can be verified by using the xinput command to first list the devices and then listing the properties for the touchpad device. Exact commands to check this have been omitted for save of brevity. If DisableWhileTyping is shown enabled but does not appear to be working the issue may be due to the fact that the keyboard is connected to a USB bus which causes it to be seen as a external keyboard. Make sure you have libinput version 1.19.0 or later installed as it includes the necessary quirk.

Synaptic driver users can add _syndaemon_ to their X11 session for the same effect.
