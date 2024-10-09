---
title: "Troubleshooting"
draft: false
menu:
  docs:
    title:
    parent: "SOPINE"
    identifier: "SOPINE/Troubleshooting"
    weight: 3
---

There is a number of things that can prevent the board from booting up properly. The most common culprits of a failed boot are:

* Subpar or counterfeit microSD card
* Subpar Power Supply
* High resistance (thin) or a very long microUSB cable
* Failed imaging of the microSD card

{{< admonition type="note" >}}
 Make sure to have the newest version of the operating system and the bootloader installed.
{{< /admonition >}}

To find out more, visit the [PINE64 forum thread](http://forum.pine64.org/showthread.php?tid=514).

## Supported screen resolutions

The board supports a number of video resolutions under Linux, however RemixOS and Android images currently only support 720p and 1080p. Linux supports a wider range of resolutions (see all resolutions supported on Linux [here](https://github.com/longsleep/sunxi-disp-tool#available-hdmi-output-names)). If the native resolution of your monitor or TV is not compatible with the board you will be unable to get video output working with your screen.

## Steps

Follow these steps to determine the cause of your problem:

* Check your PSU and barrel cable ratings
* Download and install a base image of Linux
* Plug in _power_ and _ethernet_ into your Board
* Confirm activity on the ethernet port LED
* Find out the IP of the SOPINE on the router interface
* Try to connect to the running SOPINE from your computer using SSH

## Notes

If neither of the above mentioned scenarios fits the problem you are facing, please consult the [PINE64 forum thread from user _Ghost_](http://forum.pine64.org/showthread.php?tid=680).
