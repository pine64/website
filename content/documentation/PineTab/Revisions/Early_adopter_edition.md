---
title: "Early Adopter Edition"
draft: false
aliases:
  - Early_adopters
menu:
  docs:
    title:
    parent: "PineTab/Revisions"
    identifier: "PineTab/Revisions/Early_adopter_edition"
    weight: 
---

The _Early Adopter Edition_ was the first hardware revision of the PineTab which shipped to customers. Shipping began on September 6, 2020.

## Software

The device shipped with a beta build of Ubuntu Touch by UBports. This build is available to download at https://ci.ubports.com/job/rootfs/job/rootfs-pinetab-systemimage/18/. It has the following problems which are software, not hardware, issues:

* The mouse fails to move around the entire screen. It is stuck in an 800px horizontal box.
* It is not possible to enable Bluetooth
* Cameras do not function
* Portrait mode does not function
* The external keyboard is not always detected
* There is a faint crackling noise on startup
* Pasting an item on File Manager after Copy/Cut reboots the operating system
* GUI apps with Libertine are not working, because of missing bits between wayland and Libertine
* Cannot add accounts (Google, Evernote and other) in System Settings

The first-time setup wizard advises the user to unplug the keyboard dock (avoiding the mouse issues) and update the system. Unfortunately, as of this update to this page (September 8, 2020) this will not fix any of the issues above.

### 16GB/64GB storage software error

The image installed on the device was sized for a 16GB (~14GiB) eMMC, but the PineTab shipped with a 64GB (~58GiB) eMMC chip installed. This means that the "Storage" page in the "About" section of Ubuntu Touch System Settings will show total storage as 14.0GiB until the partition table on the device is edited.

This is fixed by an update to Ubuntu Touch released to the Stable channel on September 15, 2020. The image’s tag is "2020-09-12", visible in Settings -> About -> OS.

### Installing using apt

Installing software on the read-only root filesystem is unsupported on Ubuntu Touch. You should be able to find updates in System Settings -> Updates and new applications in the OpenStore. If you would like to install and use terminal software from the Ubuntu repositories, see [Run desktop applications in the UBports Documentation](https://docs.ubports.com/en/latest/userguide/dailyuse/libertine.html) to set up a Libertine container. Unfortunately, graphical software does not yet work through Libertine. This issue is tracked as [ubports/libertine#68](https://github.com/ubports/libertine/issues/68)

### Enabling ssh

Naturally, you should be wary of enabling ssh for security reasons but everything is there. Almost.

Edit **/etc/ssh/sshd_config** and change the following:

    PasswordAuthentication yes
    ChallengeResponseAuthentication yes

Then run:

    /etc/init.d/sshd start

Use user _phablet_ along with your password or PIN to log in.

## Wifi

### Wifi disappears

If wifi stopped working, first try usual means:

* switching wifi off and on again
* reboot PineTab

If it still doesn’t work, open terminal and type this:

    nmcli radio

If output is two lines with red word **disabled** under word **WIFI** - rejoice, since this issue is known (although it’s not yet investigated well enough to figure out when it happens, so clues to developers are likely welcome). To fix it, just type this in the terminal:

    nmcli radio wifi on

### Wi-Fi missing if started with keyboard attached

Operating system: Ubuntu Touch (OS version: RC#6 (2020-W37))

Symptom: if you started with keyboard attached wifi will not come up

Reason: the service urfkill is not running

Fix:

    sudo service urfkill restart

### Wifi radio reception is very weak

This needs a tweak! How to open the PineTab?

Tested with UT, Mobian and Archlinux: sitting right beside the router gives a connection (ca. 60% level). No reception in a distance of 7 meters, no wall, just an opened door, some edges, router not directly visible. Pinephone right beside the Pinetab has an absolutly stable wifi connection.

In the event that WiFi fails to connect using Ubuntu Touch, the USB port can be used with an appropriate dongle to connect for internet using ethernet cable.

## Keyboard

The keyboard attaches magnetically and will correctly link only one way: so screen faces the keyboard.

The keyboard backlight automatically comes on when keyboard is attached, but the light can be turned off/on by holding down the Pine (super) key and tapping the right CTRL key which also shows a bulb icon. The keyboard draws its power from the PineTab battery.

Holding down the Pine key for two seconds and holding it down reveals a popup window of keyboard shortcuts.

To access the icon features on the function keys, hold down the Fn key and tap the appropriate key. Ex: F5 and F6 activate volume control (which also has a rocker button on the tablet edge).
