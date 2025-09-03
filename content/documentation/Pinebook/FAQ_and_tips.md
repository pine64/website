---
title: "FAQ and tips"
draft: false
menu:
  docs:
    title:
    parent: "Pinebook"
    identifier: "Pinebook/FAQ_and_tips"
    weight: 4
---

## Key left of Z ( \ | )

How to map the key next to Z to the symbols on \ and | (rather than <>) ?

Choose the alternative international US keyboard layout and variant. The name will depend on you desktop environment:

* English (US, alt. intl.)
* English (US, international AltGr Unicode combining, alternative)
* English (US, alternative international)

{{< admonition type="note" >}}
 keyboard variants with similar names as the ones above change the upper left key for ` and ~. You have to press that key twice to get the desired char. This happens with the alt-intl variant. Choose the altgr-intl variant (or however it is called in your desktop environment) and it should work as expected.
{{</ admonition >}}

To set the keyboard layout and variant in the terminal for X-Windows use:

```
setxkbmap -layout us -variant altgr-intl
```

The Archlinux Wiki has some good help if you need to tweak your layout further [https://wiki.archlinux.org/index.php/Xorg/Keyboard_configuration#Setting_keyboard_layout]

## Key between Fn and Alt (Menu)

How to map the key between Fn and Alt to SUPER / META ?

The initial setup in many desktop environments maps the key between Fn and Alt to MENU. Although the menu key can be useful as well (e.g. spell correction in the browser) many desktop environments and window manager use the Super key for many other useful functions. And users are probably more used to have the META key near Ctrl and Alt.

In X-windows the following command maps the key between Fn and Alt to META and the Caps-Lock key to MENU.

```
setxkbmap -option caps:menu,altwin:alt_super_win
```

## Set display brightness in the terminal

To set the display brightness in the terminal use xbacklight (if available in your distro):

```
xbacklight -setXX
```

XX is the percentage (%) of brightness. E.g. for 70% brightness

```
xbacklight -set70
```

If you use LXQt you can also use:

```
pkexec lxqt-backlight_backend --inc
pkexec lxqt-backlight_backend --dec
```

For an alternative solution please see the scripts discussed in this thread: [https://forum.pine64.org/showthread.php?tid=5062]

## Get battery % in CLI

As ACPI is not compatible with ARM, to gather the % battery this can be used:

```
cat /sys/class/power_supply/battery/capacity
```

## Firefox font size

How to get a useful font size with firefox ?

To have every web page displayed in a larger more readable font size type about:config in the search bar and confirm on the first page that you want to make changes. Then search for this parameter:

```
layout.css.devPixelsPerPx
```

and modify the value (right click) to something between 1.2 to 1.5 depending on your preferences.

In addition to that you can set in Preferences -> General -> Fonts & Color -> Advanced Minimum font size to 16

## Disable wireless power management

If having issues with wifi connectivity, try to disable power management in the 8723cs module options, adding rtw_power_mgnt=0 in /etc/modprobe.d/8723cs.conf

```
options 8723cs rtw_initmac=00:ba:ch:16:85:46 rtw_power_mgnt=0
```

## Touchpad acceleration and scroll direction

To set touchpad parameters from the cli you can use the command _xinput_. To use it correctly you first need to determine the device id / name for your touchpad. To do so, use:

```
xinput list
```

You are looking for a line like this:

```
HAILUCK CO.,LTD USB KEYBOARD Mouse      	id=7	[slave  pointer  (2)]
```

With the device id = 7 found you can list the parameters that can be set with _xinput_.

```
xinput list-props 7
```

The result looks similar to this:

```
device 'HAILUCK CO.,LTD USB KEYBOARD Mouse':
...
libinput Natural Scrolling Enabled (256):	0
...
libinput Accel Speed (265):	0.000000
...
```

To change the parameter use _xinput set-prop_

To set reverse scrolling for the touchpad use this command

```
xinput set-prop 7 'libinput Natural Scrolling Enabled' 1
```

To set mouse speed

```
xinput set-prop 7 'libinput Accel Speed' 0.95
```

Check different numbers for 0.95 to meet your needs.

For more details on xinput and mouse speed also see the Archlinux Wiki [https://wiki.archlinux.org/index.php/Mouse_acceleration#Using_xinput]

## Prolong battery life

How to reduce the max voltage the battery is charged to:

```console
$ cd /sys/class/power_supply/axp20x-battery
```

{{< admonition type="note" >}}
 The voltage_max_design is writable by root, values are in microvolts. The factory value is 4200000 or 4.2V on my device. This charges to 100% capacity.
{{</ admonition >}}

```console
$ cat voltage_max_design 
4200000
```

Check the factory value on your device, and record it if it is different. The value depends on the battery installed. You can reduce it to 4.1 V by running the following Linux command as root:

```console
$ echo 4100000 > voltage_max_design
```

If you are fully charged and on AC, the battery will start discharging until it reaches 4.1 V. This will be about 98% capacity on my device. This prolongs the battery life when you don’t need the extra few minutes of offline power. The Linux driver will not let you set the maximum voltage to a value smaller than 4.1V (as of Linux kernel 6.3.8).

The setting seems to be retained across reboots.
