---
title: "Getting Started"
draft: false
menu:
  docs:
    title:
    parent: "PineNote"
    identifier: "PineNote/Getting_started"
    weight: 2
---

{{% docs/construction %}}

This page is a work in progress. Its goals are to help users get their devices up and running while minimizing redundancy with other pages (for example documentation, development), and to synthesize information provided in existing guides. Sections below represent a rough outline and will need to be expanded with details and further instructions.

## Who can contribute?

Anyone! Generally, the PineNote is in a very early state, and at least an intermediate level of linux knowledge is probably necessary to be able to do anything at this moment. That said, there are multiple efforts happening at once, and there are a number of ways a person of any skill level can help:

1. Join in the ongoing documentation effort
2. Help mainline the kernel by testing, fixing bugs.

## Out of the box

### Information on software shipped with the Pinenote
As of July 2022, the Pinenote ships with a modified version of android. Under this OS, users interested only in reading ebooks and possibly leaking data to unknown parties may find the device more than satisfactory (read: use caution when handling ultra personal or sensitive data). All hardware items are functional with this OS, though the ability to tune and tweak may be limited by the proprietary nature of some drivers (e.g., the driver for the e-ink display). Ongoing support for this OS is absent, though further community development is possible and hoped for by more than a few users already.

Apps preloaded with this OS include:

* Xphoto
* WPS Office Lite
* Browser from Tencent (would urge users to replace/remove)
* Core: Notes (stylus-driven note app), Local Storage (file browser), Task List (notes list with text and handwriting input)
* Application Management
* More Settings

Additional apps may be added via the included browser; for example, F-droid can be installed and then used to install further android apps.

The main bar drawn along the screen’s top edge features buttons for accessing the following, from left-to-right:

* Home (house icon; opens additional bar along the screen’s left edge for accessing notes and file management apps)
* Refresh screen
* Installed Apps (four squares)
* Active Apps (bulleted list of three lines)
* Settings (gear icon)
* Back
* Wifi Menu
* Bluetooth Stylus Menu (pairing included stylus allows use of hardware buttons on the stylus)

When hidden by an open app, this bar can be made to reappear by swiping downward anywhere along the screen’s top edge.

### Accessories included in the box

As of July 2022, the Pinenote ships with the following items in the box:

* Pinenote (duh)
* Stylus
* USB-c to USB-a cable
* USB-c to micro-b cable (for stylus)
* UART dongle

## Linux installation pages

### Building the Kernel

[PineNote Development/Building Kernel](/documentation/PineNote/Development/Building_kernel)

### Booting Linux

[PineNote Development/Booting Linux](/documentation/PineNote/Development/Booting_Linux)

Additional useful references:

* https://github.com/DorianRudolph/pinenotes
* https://musings.martyn.berlin/dual-booting-the-pinenote-with-android-and-debian

### OS installation

See [Releases](/documentation/PineNote/Releases)

### Configuring OS and apps

[PineNote Development/Apps](/documentation/PineNote/Development/Apps)

## Links to dotfiles, configuration examples, etc.

* Sway config, Mesa for hardware-acceleration using GPU, KO reader: https://github.com/0cc4m/pinenote-misc
* Setting up X: https://musings.martyn.berlin/setting-up-x-on-the-pinenote-in-debian-with-touchscreen-onboard-keyboard-and
* Gnome extension: https://github.com/m-weigand/mw_pinenote_misc/tree/main/gnome_extension
* Vim config: https://github.com/m-weigand/mw_pinenote_misc/tree/main/vim
* Xournal++, nwg and libinput tweaks: https://gitlab.com/hrdl/pinenote-shared/
