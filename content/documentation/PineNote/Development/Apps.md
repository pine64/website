---
title: "Apps"
draft: false
menu:
  docs:
    title:
    parent: "PineNote/Development"
    identifier: "PineNote/Development/Apps"
    weight: 6
---

This page lists applications and tweaks for the [PineNote](/documentation/PineNote).

## Development

Here are some resources you may find helpful in learning to develop on embedded Linux devices:

* Great YouTube series introducing you to the kernel and lower-level components of Linux: https://www.youtube.com/watch?v=WiZ05pnHZqM
* https://embetronicx.com/
* https://bootlin.com/training/
* https://www.nand2tetris.org

Emulator recommendation for developing and testing PineNote apps: https://github.com/michaelshiel/picom-epaper

The PineNote is a specialized device, mainly due to the eink display having unique display and refresh characteristics.
Finding and configuring apps that work well sometimes requires a lot of tweaking and a lot exploring, especially for
applications containing fast screen updates and animations, as well as depend on a lot of colors.

[Here is a video](https://www.youtube.com/watch?v=ZCLyJfbzbrU) showing the performance of a few applications.

## Desktop Environments

### Sway

* [WinkShell](https://github.com/hmpthcs/WinkShell) "Collected applications, configurations and scripts for using a wlroots-based compositor with an EPD (aka e-ink display). Currently supports Sway only."
* [0cc4m’s config](https://github.com/0cc4m/pinenote-misc/blob/main/sway/config/sway/config)

#### Getting touch + pen working on sway

If you notice that touching the screen works, but when you use the pen the mouse coordinates are inverted, don’t worry! We can fix it! Set `rockchip_ebc.panel_reflection=0` on boot (see [this page](/documentation/PineNote/Development/Building_kernel#configuring_the_driver) for more info). Add the following line to your sway config:

    # This line rotates the mouse input by 180 degrees. See https://wayland.freedesktop.org/libinput/doc/1.11.3/absolute_axes.html
    input "type:table_tool" calibration_matrix -1 0 1 0 -1 1

### Gnome

Gnome on wayland runs nicely on the PineNote. However, a slightly patched version of mutter is required at the moment.

* See this repository for .deb packages and patch/compile files: [Patched Debian Mutter for Bookworm](https://github.com/m-weigand/pinenote_debian_mutter)
* The ready-to-use [Debian image](https://github.com/m-weigand/pinenote-debian-recipes/releases) provides a pre-configured GNOME environment], with specific GNOME configurations found [here](https://github.com/m-weigand/pinenote-debian-recipes/blob/main/overlays/gnome_config/01-pinenote-settings)
* A GNOME extension is being [developed](https://github.com/m-weigand/mw_pinenote_misc/tree/main/gnome_extension) that provides access to some of the ebc-specific driver options.
* [PNEink](https://github.com/MichiMolle/PNEink) is a GNOME Theme for use with the PineNote

#### GTK3

High contrast style for eink-devices can be found [here](https://github.com/MichiMolle/gtk3-eink).

#### GTK4

High contrast style for eink-devices can be found [here](https://github.com/MichiMolle/gtk4-eink).

## Application support on the PineNote

### System-Control

A rust-based dbus service is being [developed](https://github.com/m-weigand/pinenote_dbus_service) to enable easy, system-wide control over some of the PineNote-specific settings by users and programs (e.g., triggering global screen refreshes, changing waveforms, enabling/disabling dithering). Requires [this kernel](https://github.com/m-weigand/linux/releases).

### Notetaking

#### Xournal++

Works well. Version 1.2 version offers repainting-related optimisations and supports PDF highlighting as well as links. To remove artefacts from the eraser set the eraser cursor’s visibility to Never via Preferences -> Stylus -> Eraser Visibility. Also, disable GTK3 intertial scroll via Preferences -> Touchscreen -> Touch Scrolling -> Disable GTK’s built-in intertial scroll, as this interferes with Xournal++'s internal touch event handling.

Xournal++ uses anti-aliasing and interpolation, which do not work well for the A1 waveform. Mitigations include using either dithering or black-and-white mode in the ebc driver. https://gitlab.com/hrdl/pinenote-shared/-/blob/main/patches/xournalpp/0001-Disable-anti-aliasing-and-use-NEAREST-interpolation-.patch is an outdated patch that used to work well without changing the bw mode.

Pre-compiled Debian packages with some of the PineNote-related modifications and support for triggering global refreshes after scrolling using the dbus service (see above) can be found [here](https://github.com/m-weigand/xournalpp_pn/releases)

#### Obsidian

Works well, EInk-Theme can be found [here](https://github.com/MichiMolle/obsidian-eink).

### Web Browsing

#### Firefox

Pretty good experience! Enabling GPU acceleration is helpful.

##### GPU Acceleration in Firefox

See [0ccam’s notes here](https://github.com/0cc4m/pinenote-misc#firefox-hardware-acceleration).

### Cloud

#### syncthing
High contrast theme can be found [here](https://github.com/MichiMolle/syncthing-eink).

### Games
	
==== Generating crosswords 
	
There are some scripts [here](https://git.sr.ht/~scott__/pinenote_crossword_utilities) for generating crosswords for the Pinenote from IPUZ files.
