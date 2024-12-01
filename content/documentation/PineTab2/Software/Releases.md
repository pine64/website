---
title: "Releases"
draft: false
toc: true
menu:
  docs:
    title:
    parent: "PineTab2/Software"
    identifier: "PineTab2/Software/Releases"
    weight: 2
---

This page contains a list of all available releases and tools for the PineTab2 in alphabetical order. 

## Factory releases

The PineTab2 ships with _Danctnix Arch Linux ARM_. The latest factory image can be found here:

* https://echo.danctnix.org:7269/factory_images/pinetab2/20240625/danctnix-factory-image-20240625.img.xz (2.2 GB)

{{< admonition type="note" >}}
 The factory image is flashed to a microSD card and it will overwrite the eMMC installation after booting.
{{< /admonition >}}

{{< admonition type="note" >}}
 Notice that the last two images (20240307 and 20240625) don’t use the keyboard but the volume and power buttons for navigation
{{< /admonition >}}

### Older versions

* https://echo.danctnix.org:7269/factory_images/pinetab2/20240307/danctnix-factory-image-20240307.img.xz (2.1 GB)
* https://echo.danctnix.org:7269/factory_images/pinetab2/20230527/danctnix-factory-image-20230527.img.xz (1.5 GB)

{{< admonition type="note" >}}
 Older versions ship without Wi-Fi drivers. See below under Arch Linux ARM how to fix it
{{< /admonition >}}

## Linux

### Arch Linux ARM

(Unofficial) Arch Linux ARM maintained by the [DanctNIX](https://danctnix.org/) community (GitHub: [danctnix](https://github.com/DanctNIX/danctnix), [dreemurrs-embedded](https://github.com/dreemurrs-embedded)).

#### Download

* SD-card boot: https://github.com/dreemurrs-embedded/Pine64-Arch/releases
* Factory flash image: https://echo.danctnix.org:7269/factory_images/pinetab2/20240625/danctnix-factory-image-20240625.img.xz (2.2 GB)

| Default credentials | |
| -------- | ------- |
| `alarm` | `123456` |

#### Notes

* Currently ships without Bluetooth driver, and Wifi driver is unstable.
* Shutdown / Reboot sometimes hangs (but not always), this is caused by the Wifi driver.

### Buildroot

Buildroot is a simple, efficient and easy-to-use tool to generate embedded Linux systems through cross-compilation.

An external tree for the PINE64 PineTab2 is developed and maintained by _Danct12_ (same developer behind the PineTab2 port of _Arch Linux ARM_).

#### Download

* The repository and build instructions can be found [here](https://github.com/Danct12/buildroot_pinetab2).

### LuneOS

LuneOS is one of the original multi-tasking OS-es that runs on Linux. Based on HP/Palm’s webOS, merged with latest technology stack from LG called webOS OSE (a derivative of what LG uses on their Smart TV’s), software such as Qt6, Maliit, PulseAudio, Wayland and makes use of the Yocto build system.

#### Download

Stable: https://github.com/webOS-ports/luneos-releases/releases/

Testing: https://github.com/webOS-ports/luneos-testing/releases/

{{< admonition type="note" >}}
 U-Boot is required to boot the images. If you have the factory image installed and updated to the latest version, you can boot Mobian from an SD card without installing U-Boot.
{{< /admonition >}}

| Default credentials | |
| -------- | ------- |
| `root` | no password |

#### Notes
* The development is work in progress, but all hardware that’s supported by the kernel should work (WiFi/BT included). Camera’s aren’t working, similar to all other distros due to lack of drivers.
* In order to connect to the device using SSH/SCP, you simply can connect to the device’s IP address on port 5522. 
* Teams can be reached via [Telegram](https://t.me/luneos_dev) or [Libera IRC #webos-ports](http://web.libera.chat/#webos-ports)

### Mobian

An unofficial [Debian](https://www.debian.org) build for ARM64 running with Phosh. The current version of the base Debian system is Debian Bookworm. See the installation instructions [here](https://wiki.debian.org/InstallingDebianOn/PINE64/PineTab2). If you have questions about Mobian, please ask them in the [Mobian Matrix room](https://matrix.to/#/#mobian:matrix.org).

#### Download

* [Images](https://images.mobian.org/pinetab2/)

{{< admonition type="note" >}}
 U-Boot is required to boot the images. If you have the factory image installed and updated to the latest version, you can boot Mobian from an SD card without installing U-Boot.
{{< /admonition >}}

| Default credentials | |
| -------- | ------- |
| `mobian` | `1234` |

#### Notes

* The development is work in progress. Mobian’s support for the PineTab2 is maintained by [Julian](https://salsa.debian.org/julianfairfax). The Mobian wiki can be found [here](https://wiki.mobian-project.org/).
* In order to connect to the device using SSH/SCP, you need to install SSH on the device. You can do this by executing the following in a shell: "sudo apt-get install ssh", afterwards you can connect via SSH/SCP using the PineTab2’s IP address on port 22.
* When installing Mobian with full disk encryption and booting with the keyboard case connected, you will have to touch the screen or press a key to show the decryption screen. This is an [upstream issue](https://gitlab.com/postmarketOS/osk-sdl/-/issues/148).

### NixOS

NixOS is an immutable Linux distribution built around the Nix configuration language. The NixOS image for PineTab2 uses some downstream modifications to packages, such as an U-Boot package based on 2023.07-rc4 and a kernel also used by the Arch Linux Arm image.

This image is extremely basic and currently boots to a console. A NixOS configuration can be applied after booting to gain a full graphical system.

#### Download

* https://github.com/nabam/nixos-rockchip/releases

#### Notes

After booting, enable networking (with _wpa_supplicant_, see https://nixos.org/manual/nixos/unstable/#sec-installation-manual-networking) and download (for example by entering `nix-shell wget` to get access to wget) this flake to the pinetab and place it at /etc/nixos/flake.nix:

* https://git.asonix.dog/asonix/pinetab2-nixos/raw/branch/main/flake.nix

Run the following commands:

```console
$ sudo su
> cd
> nixos-rebuild switch
> nixos-rebuild switch # yes, do it two times
> reboot
```

After the first `nixos-rebuild`, you may need to reconnect to the network using `nmtui`.

After rebooting, there will be a new user account.

Note that booting can take a while, and does not show anything on the screen. After about 18 seconds the keyboard backlight turns on, then it’s about 30 seconds until the first text appears on the screen, and another 10 seconds before the session manager shows up.

| Default credentials | |
| -------- | ------- |
| `pinetab2` | `changeme` |

### Plasma Mobile on Debian

Images of Plasma Mobile on either Debian Bookworm or Debian Trixie created by dieselnutjob

The images include uboot, and are an SDcard installer (modified from the Danctnix OS Factory Tool).  Using the installer wipes the eMMC drive.

#### Download

https://sourceforge.net/projects/pinetab2debianplasmamobile/files/

| Default credentials | |
| -------- | ------- |
| `pt2` | `1234` |
| `root` | `1234` |

#### Notes

The image will not autoexpand to the fill the eMMC, however once booted it is easy to adjust the size of the rootfs using the included KDE Partition Manager.

The PineTab2 may be reluctant to shutdown, with several minutes delay whilst the BES2600 wifi driver unloads.  This can be avoided by turning off the wifi in the menu that can be pulled down from the top of the screen before shutting down or rebooting.

There is a video of the PineTab2 running one of these images here https://www.youtube.com/watch?v=9xpSuG63Rck

The author may be contacted via the pinetab discord channel on the Pine64 discord.

### postmarketOS

postmarketOS extends [Alpine Linux](https://www.alpinelinux.org/) to run on smartphones and other mobile devices.

It offers various user interfaces (Phosh, Plasma Mobile, Sxmo, Plasma Desktop, Gnome 3, Kodi, XFCE4 and more). As of writing, this distro is currently in testing and no official releases are available for download. Instead, users will need to create their own image with the distribution’s install and development tool `pmbootstrap`.

#### Download

* [Pinetab2 Device Page](https://wiki.postmarketos.org/wiki/PINE64_PineTab_2_(pine64-pinetab2))
* Build the image with [pmbootstrap](https://wiki.postmarketos.org/wiki/Pmbootstrap) and flash it to an SD.

### Rhino Linux

Rhino Linux is an Ubuntu-based distribution that uses the rolling-release model by tracking the `devel` branch of repositories. The port is currently maintained by Oren Klopfer (oklopfer).

The bootloader (u-boot) comes pre-flashed in the port. Installation just requires flashing the `.img.xz` to an SD or the eMMC.

#### Download
[Rhino Linux Downloads](https://rhinolinux.org/download.html) (select Pine64 on the dropdown)

| Default credentials | |
| -------- | ------- |
| `rhino` | `1234` |

#### Notes

Foundational to the distribution is [Pacstall](https://pacstall.dev), a Debian-based user repository inspired by the AUR. Additionally, RL comes with [Unicorn](https://rhinolinux.org/unicorn/), a custom modified version of XFCE with various modernizations and improvements, including auto-rotation for mobile devices.

[Discord](https://discord.gg/reSvc8Ztk3) - [Matrix](https://matrix.to/#/#rolling-rhino-remix:matrix.org) - [GitHub](https://github.com/rhino-linux) - [Wiki](https://rhinolinux.org/wiki.html)

### Ubuntu Touch

A Mobile Version of the Ubuntu Operating System made and maintained by the UBports Community. The port is currently maintained by Oren Klopfer (oklopfer).

The bootloader (u-boot) comes pre-flashed in the port. Installation just requires flashing the `.img.xz` to an SD or the eMMC.

#### Download

[UBports 20.04 PineTab2 Latest Releases](https://gitlab.com/ook37/pinephone-pro-debos/-/releases)

[UBports PineTab2 Device Info](https://devices.ubuntu-touch.io/device/pinetab2/release/focal)

| Default credentials | |
| -------- | ------- |
| Default user | Set during boot |
| root | `phablet`/`1234` |

#### Notes

Scroll down to the middle of [the GitLab project page](https://gitlab.com/ook37/pinephone-pro-debos/), or directly here [at the UBports website](https://devices.ubuntu-touch.io/device/pinetab2/release/focal/#deviceOverview) to see which features work.

Contributions and bug reports can be made at the [UBports PineTab2 GitLab page](https://gitlab.com/ook37/pinephone-pro-debos/). See [UBports website](https://ubports.com/foundation/sponsors) for how to donate.