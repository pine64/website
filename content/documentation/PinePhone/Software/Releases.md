---
title: "Releases"
draft: false
toc: true
menu:
  docs:
    title:
    parent: "PinePhone/Software"
    identifier: "PinePhone/Software/Releases"
    weight: 1
---

This page contains a list of all available releases and tools for the [PinePhone](/documentation/PinePhone) in alphabetical order.

{{< admonition type="note" >}}
 Some releases may not have a good setup for the backlight at low brightness. If configured too low, the backlight shuts down completely, but the screen is still displayed and usable in bright front-light.
{{< /admonition >}}

See [Installation instructions](/documentation/PinePhone/Installation/) on how to install the operating systems. Please see [Update instructions](/documentation/PinePhone/Software/Updating_instructions) for how to update the phone.

## Software Releases

### Arch Linux ARM

{{< figure src="/documentation/images/Archlinux-logo.png" width="100" >}}

(Unofficial) Arch Linux ARM with choice of Phosh UI, Plasma Mobile, sxmo or barebones.

It is maintained by the [DanctNIX](https://danctnix.org/) community (GitHub: [danctnix](https://github.com/DanctNIX/danctnix), [dreemurrs-embedded](https://github.com/dreemurrs-embedded)).

#### Download

Get both stable and test builds at [GitHub releases](https://github.com/dreemurrs-embedded/Pine64-Arch/releases).

| Default credentials | |
| -------- | ------- |
| Default user | `alarm/123456` |
| root (barebone only) | `root/root` |

#### Notes

* There are _archmobile_ chat rooms on Matrix ([#archmobile:kde.org](https://matrix.to/#/#archmobile:kde.org)) and Telegram ([@archmobile](https://t.me/archmobile)).
* Feel free to send us [pull requests](https://github.com/dreemurrs-embedded/Pine64-Arch/pulls) and reports [issues](https://github.com/dreemurrs-embedded/Pine64-Arch/issues) on [GitHub](https://github.com/dreemurrs-embedded/Pine64-Arch).

### Fedora

{{< figure src="/documentation/images/fedora1.png" width="100" >}}

An (unofficial) vanilla Fedora rawhide build for aarch64 with megi's kernel and [some additional packages](https://copr.fedorainfracloud.org/coprs/njha/mobile/packages/) to tie it all together.
It aims to eventually be an upstream part of the Fedora project, rather than a phone-specific distribution.

* Forum discussion: [Fedora + Phosh for PinePhone](https://forum.pine64.org/showthread.php?tid=9347)
* GitLab: [Fedora Mobility SIG](https://gitlab.com/fedora/sigs/mobility)

#### Download

* [Build scripts](https://github.com/nikhiljha/pp-fedora-sdsetup)
* [Packages (Fedora COPR)](https://copr.fedorainfracloud.org/coprs/njha/mobile/)

There is also an FTP server with images build every night @ ftp://pine.warpspeed.dk/nightly/pinephone/ (Mount this with something like Nautilus)

| Default credentials | |
| -------- | ------- |
| Nightly images (via FTP) | `pine/1111` |

#### Notes

WiFi, Bluetooth, SMS, Data, Calls all work|There are still a few bugs though, and [some features don't have driver support yet](https://xnux.eu/devices/pine64-pinephone.html#toc-feature-driver-support-matrix) on any PinePhone distribution.

Please send your bug reports to [the project's issue tracker](https://github.com/nikhiljha/pp-fedora-sdsetup/issues). Be sure to include logs if applicable|Send us pull requests on [GitLab](https://gitlab.com/groups/fedora/sigs/mobility/-/issues).

### Gentoo

{{< figure src="/documentation/images/GentooLogo.png" width="100" >}}

There are unofficial Gentoo overlays with ebuilds for the PinePhone. There are no images - the image must be built manually, including picking the kernel, bootloader and the desired desktop environment. The ARM64 version of Gentoo has to be selected.

#### Download

Overlay locations:

* https://git.gjdwebserver.nl/gjdwebserver/gjdwebserver-overlay

#### Notes

The documentation can be found here:

* https://blog.gjdwebserver.nl/ords/f?p=107:HOME:::::ARTICLE:gentoo-on-a-pinephone
* https://blog.gjdwebserver.nl/ords/f?p=107:HOME:::::ARTICLE:gentoo-on-a-pinephone-making-it-a-usable-phone
* https://blog.gjdwebserver.nl/ords/f?p=107:HOME:::::ARTICLE:gentoo-on-a-pinephone-pro
* https://wiki.gentoo.org/wiki/User:Dr41nU/PinePhone
* https://wiki.gentoo.org/wiki/PinePhone (incomplete)

{{< admonition type="note" >}}
 Please consider cross-compiling the software on the computer. Long compilation times and heat production can lead to a reduced lifespan of the phone.
{{< /admonition >}}

### GloDroid

A fully open-source port of Android and LineageOS to the PinePhone.

GitHub: [GloDroid](https://github.com/GloDroidCommunity/pine64-pinephone)

#### Download

* Releases: [GloDroid](https://github.com/GloDroidCommunity/pine64-pinephone/releases)

#### Notes

Feature overview:

* Works: WiFi, screen dimming, sound, touchscreen, charging and telephony(partially) works.
* Doesn't work: Bluetooth and GPS
* See more at [project status page](https://github.com/GloDroidCommunity/pine64-pinephone/issues/2)

### Kali Linux

{{< figure src="/documentation/images/Kali-logo.png" width="200" >}}

The official Kali Nethunter images for PinePhone and PinePhone Pro have been released now. For older/unofficial releases, you can still download from the GitHub releases page. Get [Nethunter App](https://github.com/Shubhamvis98/nethunter-pinephone) for your PinePhone's Kali Linux. Packet Injection is working now, use iwconfig instead of airmon-ng.

#### Download

* [Kali Phosh Unofficial](https://github.com/Shubhamvis98/kali-pinephone/releases)
* [Kali Nethunter Pro Official](https://www.kali.org/get-kali/#kali-mobile)

| Default credentials | |
| -------- | ------- |
| Default user for Unofficial Releases | `kali/8888` |
| Default user for Nethunter Releases | `kali/1234` |



### LuneOS

{{< figure src="/documentation/images/Luneos-logo-256.png" width="100" >}}

LuneOS is one of the original multi-tasking OS-es that runs on Linux. Based on HP/Palm's webOS, merged with latest technology stack from LG called webOS OSE (a derivative of what LG uses on their Smart TV's), software such as Qt5 and makes use of the Yocto build system.

* [WebOS Ports Wiki](https://www.webos-ports.org/wiki/Main_Page)
* [WebOS-Ports Wiki's Pinephone page](https://webos-ports.org/wiki/Pinephone_Info)
* GitHub: [WebOS Ports](https://github.com/webOS-ports)

#### Download

* LuneOS Preview images: [Downloads](https://github.com/webOS-ports/meta-pine64-luneos/releases)

| Default credentials | |
| -------- | ------- |
|Default user | `root` |

#### Notes

In order to connect to the device using SSH/SCP via WiFi: You can simply connect via SSH/SCP via WiFi using the PinePhone's IP address on port 22.

### Maemo Leste

{{< figure src="/documentation/images/Maemoleste-logo.png" width="100" >}}

Maemo is a trimmed-down version of Debian for mobile devices, originally a collaboration between Nokia and many open source projects (the [Maemo community](http://maemo.org/intro/)) before Nokia abandoned it. The more well-known devices Maemo supports are the OpenMoko and N900. The community now takes full responsibility in developing fully open source Maemo for a variety of mobile devices. You may be interested to learn more about the features in their [Maemo Leste FAQ](https://leste.maemo.org/Leste_FAQ).

Maemo 8 "Leste" is an ARM64 port of [Devuan](https://devuan.org/) (Debian without systemd) and runs the mainline Linux kernel.
The default user interface stack is [Hildon](https://en.wikipedia.org/wiki/Hildon), [Xorg](https://en.wikipedia.org/wiki/X.Org_Server), [Matchbox WM](https://en.wikipedia.org/wiki/Matchbox_(window_manager)), and [GTK](https://en.wikipedia.org/wiki/GTK).

#### Download

* [Maemo Leste test builds](https://maedevu.maemo.org/images/pinephone/)

There is also an [image builder](https://github.com/maemo-leste/image-builder), see the wiki for instructions on how to [build a custom image](https://leste.maemo.org/Image_Builder). For current status and instructions, please read their [PinePhone wiki page](https://leste.maemo.org/PinePhone).

| Default credentials | |
| -------- | ------- |
| root | `toor` |
| user | `12345 (lockscreen)` |

#### Notes

Most discussion occurs at `#maemo-leste` on `irc.libera.chat` ([link](ircs://irc.libera.chat:6697/#maemo-leste)) and [this thread](https://talk.maemo.org/showthread.php?t=100192&page=60).

All other contact information is listed on the [main page](https://leste.maemo.org/Main_Page) of the Maemo wiki.

Submit [bug reports](https://github.com/maemo-leste/bugtracker/issues) on GitHub. To track known issues, you may use these search terms: [pinephone](https://github.com/maemo-leste/bugtracker/issues?utf8=%E2%9C%93&q=is%3Aissue+is%3Aopen+pinephone) and [pine64](https://github.com/maemo-leste/bugtracker/issues?utf8=%E2%9C%93&q=is%3Aissue+is%3Aopen+pine64).

### Manjaro ARM

{{< figure src="/documentation/images/Manjaro-logo.svg" width="100" >}}

Manjaro is a user-friendly Linux distribution based on the independently developed Arch operating system with the Plasma Mobile and Phosh desktop environment.

#### Download

* Phosh: [Dev](https://github.com/manjaro-pinephone/phosh-dev/releases) and [Stable](https://github.com/manjaro-pinephone/phosh/releases)
* Plasma Mobile: [Dev](https://github.com/manjaro-pinephone/plasma-mobile-dev/releases) and [Stable](https://github.com/manjaro-pinephone/plasma-mobile/releases)
* Lomiri: [Dev](https://github.com/manjaro-pinephone/lomiri-dev) (unmaintained)

| Default credentials (Only Phosh) | |
| -------- | ------- |
| Default user | `manjaro/123456` |
| root | `root/root` |

#### Notes

The installation of the stable images is strongly suggested. The dev images might break frequently.

### Mobian

{{< figure src="/documentation/images/Mobian-logo.png" width="100" >}}

A [Mobian](https://www.mobian.org) build for ARM64 running with Phosh (developed by Purism, uses Wayland instead of Xorg).
The current version of the base Debian system is Debian Bookworm. Only the GUI applications and a few others (ModemManager, WiFi chip firmware) are built from modified sources (as well as the kernel and u-boot).

#### Download

* [Images](https://images.mobian.org/pinephone/)

{{< admonition type="note" >}}
 Tow-Boot is required to be able to boot the images, see [here](https://wiki.mobian-project.org/doku.php?id&#61;install-linux)!
{{< /admonition >}}

| Default credentials | |
| -------- | ------- |
| Default user | `mobian/1234` |

#### Notes

The development is work in progress. See [pinephone-support](https://gitlab.com/mobian1/devices/pinephone-support) for further information. The Mobian wiki can be found [here](https://wiki.mobian-project.org/).

In order to connect to the device using SSH/SCP via WiFi, you need to install SSH on the device. You can do this by executing the following in a shell: "sudo apt-get install ssh", afterwards you can connect via SSH/SCP via WiFi using the PinePhone's IP address on port 22.

### Movuan

{{< figure src="/documentation/images/movuan-logo.png" width="100" >}}

Movuan is the incipient stage of a new distribution for the PinePhone. It is derived from Mobian, yet using Devuan instead of Debian. The image attempts to be as short lived as possible, hoping to get merged into mainline Devuan as soon as possible.

#### Download

* [Image](https://gitlab.com/l2385/movuan/movuan-recipes/-/releases)

This is a split zip file. To extract it, the following command can be used:

```shell
7z e movuan-pinephone-phosh-daedalus-20250224.img-split.zip
```

{{< admonition type="note" >}}
Tow-Boot is required to be able to boot, same as for Mobian
{{< /admonition >}}

| Default credentials | |
| -------- | ------- |
| Default user | `movuan/1234` |

#### Notes

* Current image version is based on Devuan Daedalus.
* [Source Code](https://gitlab.com/l2385/movuan)
* [Announcement/Discussion/Motivation](https://dev1galaxy.org/viewtopic.php?pid=54759#p54759)
* Further interest [Customizing Movuan under Host Mounting](https://gitlab.com/l2385/movuan/customizing-movuan-under-host-mounting)

At this time expecting feedback or offers to help with building/packing.

Anybody is welcome to fork this project, or use it in any GPL compliant way. Use a different name though and change the logo, and notify the author of the project to review if it can be incorporated back.

If you want to just mirror the code and provide additional pre-built images on a different server, there is no need to change the logo/name. Just make sure to prominently point to the original location.

### Multi-distro demo image

{{< admonition type="warning" >}}
 This is a demo image for testing different operating systems before installing a regular image. Attempting to use this image productively is highly discouraged. The kernel is shared across the different operating systems and is not updated.
{{< /admonition >}}

This image allow users to try many Linux distributions easily, without having to figure out how to flash them individually and juggle with many microSD cards. Also called megi's 15-in-1 multi boot image.

* Main page: https://xnux.eu/p-boot-demo/
* Git repo: https://megous.com/git/pinephone-multi-boot/
* Forum discussion: [15-distro multi-boot image for Pinephone](https://forum.pine64.org/showthread.php?tid=11347)

#### Download

*Update 2022-01-26, using megi's kernel 5.16.2*

DD image to SD card and boot. This image is for 16GiB or larger SD cards, also works if flashed to eMMC.

This is also a good build for charging depleted battery. Just boot up this build with power supply connected, keep the PinePhone charging for 3 hours at power down stage.

For more info on this build, please visit its entry the "News" section of its [web page](https://xnux.eu/p-boot-demo/).

* [Download torrent file from author's website](https://dl.xnux.eu/p-boot-multi-2022-01-26.torrent)
  * *File name:* multi.img.zst
  * *SHA-256:* 39915b9d2aa2f33fd78552ac9a0e665c4aef97dd68a9f9a6c76f9fa2f0ac049e
  * *File Size:* 6.9GiB

Due to its size, download though torrent is suggested by the author on its main page.

| Default credentials | |
| -------- | ------- |
| General | `1111` |
| sxmo | `user/1111` |
| Manjaro | seems to insist on `123456` |

#### Notes

[NOTE]

#### 

 Note about zstd) archive file (`.zst`):

On Linux, you may install or compile `zstd`, then write the image to SD card by piping `zstdcat` and `dd`. See the "Installation" section of its [web page](https://xnux.eu/p-boot-demo/) for command examples.

On Windows, instead of the offical [zstd](https://github.com/facebook/zstd) command line program, you may use [7-zip-zstd](https://github.com/mcmilk/7-Zip-zstd). Different installation method is provided in their README. Install 7-Zip-zstd / zstd, extract the disk image file (`.img`) from the zstd archive, and flash with tools like [Win32 Disk Imager](https://sourceforge.net/projects/win32diskimager/).

#### 

Also see [Installation instructions](/documentation/PinePhone/Installation_instructions).

### Nemo Mobile

{{< figure src="/documentation/images/nemo_mobile.png" width="100" >}}

Nemo Mobile is the open source build of Sailfish OS with a open source UI called [Glacier](https://nemomobile.net/glacier-home/), [based on Manjaro](https://nemomobile.net/pages/Hello_manjaro/).

#### Download

[Image](https://img.nemomobile.net/2022.05/Manjaro-ARM-nemomobile-pinephone-0.9.img.xz)

| Default credentials | |
| -------- | ------- |
| Default user | `manjaro/123456` |
| root | `root/root` |

#### Notes

The website of the Nemo Mobile UX Team can be found [here](https://nemomobile.net/). Please report bugs regarding the Nemo Mobile UI as [GitHub issue](https://github.com/nemomobile-ux/main/issues).

### NixOS

{{< figure src="/documentation/images/NixOS.webp" width="100" >}}

NixOS is a Linux distribution built on top of the Nix package manager using declarative configuration to allow reliable system upgrades.

#### Download

There is a guided installer by the [Mobile NixOS](https://mobile.nixos.org/devices/pine64-pinephone.html) project available. An installer image that can be flashed to a sdcard can be downloaded from the [Hydra build instance](https://hydra.nixos.org/job/mobile-nixos/unstable/installer.pine64-pinephone).

Users that want to build a local image, are expected to follow the instructions in the [Getting Started page](https://mobile.nixos.org/getting-started.html),
and [Project's device page](https://mobile.nixos.org/devices/pine64-pinephone.html).

#### Notes

Project home page: [Mobile NixOS](https://mobile.nixos.org/)

### OpenMandriva Lx

{{< figure src="/documentation/images/Oma-logo-22042013_300pp.png" width="100" >}}

OpenMandriva Lx with Plasma Mobile as UI.

#### Download

The official image can be found [at sourceforge.net](https://sourceforge.net/projects/openmandriva/files/release/4.2/RC/Pinephone/).
See [here](https://www.openmandriva.org/en/news/article/openmandriva-lx-4-3-rc-available-for-testing) for the offical announcement.

#### Notes

{{< admonition type="note" >}}
 This image is solely for testing purposes.
{{< /admonition >}}

### openSUSE

{{< figure src="/documentation/images/SLEM-OS-logo.png" width="100" >}}

Our images use the same [openSUSE Tumbleweed](https://en.opensuse.org/Portal:Tumbleweed) base as our desktop images,
except what needs to be changed for the PinePhone.
The images include _zypper_ (RPM) as the default package manager,
and have access to virtually the same (open source) software as our desktop repositories,
thanks to the [Factory](https://en.opensuse.org/Portal:Factory) ports.
Using [dnf](https://en.opensuse.org/SDB:DNF) is possible, if preferred.

#### Download

* [Phosh](https://download.opensuse.org/repositories/devel:/ARM:/Factory:/Contrib:/PinePhone/images/openSUSE-Tumbleweed-ARM-PHOSH-pinephone.aarch64.raw.xz) / [SHA-256](https://download.opensuse.org/repositories/devel:/ARM:/Factory:/Contrib:/PinePhone/images/openSUSE-Tumbleweed-ARM-PHOSH-pinephone.aarch64.raw.xz.sha256) / [SHA-256 Signature](https://download.opensuse.org/repositories/devel:/ARM:/Factory:/Contrib:/PinePhone/images/openSUSE-Tumbleweed-ARM-PHOSH-pinephone.aarch64.raw.xz.sha256.asc)
* [Plasma Mobile](https://download.opensuse.org/repositories/devel:/ARM:/Factory:/Contrib:/PinePhone/images/openSUSE-Tumbleweed-ARM-PLAMO-pinephone.aarch64.raw.xz) / [SHA-256](https://download.opensuse.org/repositories/devel:/ARM:/Factory:/Contrib:/PinePhone/images/openSUSE-Tumbleweed-ARM-PLAMO-pinephone.aarch64.raw.xz.sha256) / [SHA-256 Signature](https://download.opensuse.org/repositories/devel:/ARM:/Factory:/Contrib:/PinePhone/images/openSUSE-Tumbleweed-ARM-PLAMO-pinephone.aarch64.raw.xz.sha256.asc)

To verify the images you need to import [our GPG key](https://build.opensuse.org/projects/devel:ARM:Factory:Contrib:PinePhone/public_key).
Keep on mind that the first boot may stay on black screen for about a minute - consequent boots should be faster.

You can find install instructions at [this section](https://en.opensuse.org/HCL:PinePhone#Installing_openSUSE_in_a_Pinephone) in the openSUSE Wiki.

| Default credentials | |
| -------- | ------- |
| Default user | `pine/1234` |
| root | `root/linux` |

#### Notes

You can find all information about the releases of the project [here](https://gitlab.com/slem.os/slem.os/-/blob/master/CHANGELOG.md).
Detailed information, tips and troubleshooting suggestions are also provided at [the openSUSE Wiki](https://en.opensuse.org/HCL:PinePhone).
You will also find information in our wiki on how to report issues (Contributing section).

### postmarketOS

{{< figure src="/documentation/images/PostmarketOS_logo.png" width="100" >}}

postmarketOS extends [Alpine Linux](https://www.alpinelinux.org/) to run on smartphones and other mobile devices.
It offers various user interfaces (Phosh, Plasma Mobile, Sxmo, Plasma Desktop, Gnome 3, Kodi, XFCE4 and others).

#### Download

[Download page](https://postmarketos.org/download/)

| Default credentials | |
| -------- | ------- |
| Test images user | `user/147147` |

#### Notes

As of writing, official images are provided with Phosh, Plasma Mobile and Sxmo.
The official images come in two flavors, either as a test image to try out postmarketOS, or with the installer.

When using the installer images (recommended), it is possible to:

* encrypt the installation
* install from the SD card to eMMC

Power users may also create their own image with the distribution's install and development tool `pmbootstrap`.

See the [pine64-pinephone](https://wiki.postmarketos.org/wiki/PINE64_PinePhone_(pine64-pinephone)) page of the postmarketOS wiki for details.

	
### Rhino Linux

Rhino Linux is an Ubuntu-based distribution that uses the rolling-release model by tracking the devel` branch of repositories. The port is currently maintained by Oren Klopfer (oklopfer).
	
Tow-Boot is required for installing Rhino Linux. Instructions for installing Tow-Boot to the PinePhone can be found [here](https://tow-boot.org/devices/pine64-pinephoneA64.html). After Tow-Boot has been installed to your device, Rhino Linux installation just requires flashing the `.img.xz` to an SD or the eMMC.

#### Download

[Rhino Linux Downloads](https://rhinolinux.org/download.html) (select Pine64 on the dropdown)

| Default credentials | |
| -------- | ------- |	
| Default user | `rhino`/`1234` |
	
#### Notes
	
Foundational to the distribution is [Pacstall](https://pacstall.dev), a Debian-based user repository inspired by the AUR. Additionally, RL comes with [Unicorn](https://rhinolinux.org/unicorn/), a custom modified version of XFCE with various modernizations and improvements, including auto-rotation for mobile devices.
	
[Discord](https://discord.gg/reSvc8Ztk3) - [Matrix](https://matrix.to/#/#rolling-rhino-remix:matrix.org) - [GitHub](https://github.com/rhino-linux) - [Wiki](https://rhinolinux.org/wiki.html)

### Sailfish OS

{{< figure src="/documentation/images/SailfishOS_logo.png" width="100" >}}

[Sailfish OS](https://sailfishos.org/) is a Linux-based operating system based on open source projects such as [Mer](https://wiki.merproject.org/wiki/Main_Page), and a closed source UI based on [Lipstick](https://sailfishos.org/wiki/Lipstick).

* [PinePhone Wiki Page](https://wiki.merproject.org/wiki/Adaptations/PinePhone64) on Mer Wiki, for both Nemo Mobile and Sailfish OS.
* [Linux kernel config repo](https://gitlab.com/pinephone-sailfish-os/linux-kernel/)
* [Sailfish OS repo](https://gitlab.com/sailfishos-porters-ci/dont_be_evil-ci/)

#### Download

*Flashing script*

The Sailfish OS image is built on Gitlab CI. The latest image can be installed using the [flashing script](https://raw.githubusercontent.com/sailfish-on-dontbeevil/flash-it/master/flash-it.sh).

The script downloads the image and bootloader from the CI, extracts everything and burns it onto the SD card.

{{< admonition type="note" >}}
 The script will format and erase the SD card!
{{< /admonition >}}

Instructions:

1. Download the flashing script
2. Insert a microSD card in your device
3. Make the script executable: `chmod +x flash-it.sh`
4. Verify that you have the `bsdtar` package installed
5. Execute it: `./flash-it.sh`
6. Follow the instructions. Some commands in the script require root permissions (for example: mounting and flashing the SD card).

When asked where to flash, type 'raw' and it will build the image on your computer. Otherwise define the path */dev/[...]*. to flash to card or internal emmc.

*username/password*

Set PIN on initialization.

#### Notes

* Sometimes the first run stalls before the tutorial. Reboot and it will start from setting the security pin.
* The homescreen may be locked unless you boot with a sim card inserted. An old expired sim will do. *If you do not have a SIM card on hands, do NOT set a security code on first boot.*
* When a screen with a loading circle is displayed, just left/right swipe it away.
* If you're not familiar with Sailfish OS, pay attention to the tutorial - the interface works great, but is not immediately obvious. If you are familiar with it, you can skip the tutorial by touching all 4 corners starting top left.

*What works, what does not work*

See the [Hardware Support section](https://wiki.merproject.org/wiki/Adaptations/PinePhone64#Hardware_Support) on the Mer Wiki's PinePhone Page.

There is a limited selection of apps available from the Jolla store, the vast majority are hosted on openrepos.net. If the Storeman app for openrepos is not preinstalled, download the RPM and click to install.

*How to contribute and report defects*

See the documentation wiki at [the github project](https://github.com/sailfish-on-dontbeevil/documentation/wiki) for help and links.

See the [Installation section](https://wiki.merproject.org/wiki/Adaptations/PinePhone64#Installation) on the Mer Wiki's PinePhone Page for compile, build and development.

Git repo links are at the top of this OS section. other repos that may be helpful:

* [GitHub project page](https://github.com/sailfish-on-dontbeevil)
* [the repo of the flash-it.sh flashing script](https://github.com/sailfish-on-dontbeevil/flash-it)
* [Mer Open Build Service page](https://build.merproject.org/project/show/nemo:devel:hw:pine:dontbeevil) ([Mer is being assimilated into Sailfish OS](https://forum.sailfishos.org/t/changes-needed-to-merge-the-project-names-to-sailfish-os/1672) and [OBS is shutting down](https://forum.sailfishos.org/t/obs-shut-down-and-next-steps/1814), also see [OpenStack is replacing OBS with another build system based on Jenkins](https://specs.openstack.org/openstack/fuel-specs/specs/7.0/replace-obs.html), if it's related, even OBS come back under Sailfish OS, it will be different.)

See the [Sailfish OS wiki](https://sailfishos.org/wiki/Collaborative_Development#Reporting_issues) for links to their forum, as well as info required when reporting an issue. See the [Sailfish OS wiki main page](https://sailfishos.org/wiki/SailfishOS) for options to contribute to Sailfish OS.

*Notes*

OTA is supported: `zypper refresh && zypper update` as root (`devel-su` to get root access). Things that need reflash are bootloader specific at the moment. If improvements like [Crust](/documentation/PinePhone/Software/Crust) or changes of partition layout are added, then you need to reflash.

### SkiffOS

{{< figure src="/documentation/images/SkiffOS-Icon-1.png" width="100" >}}

Minimal in-memory cross-compiled OS optimized for hosting multiple in parallel Docker containers. Provides the reliability of firmware with the ease-of-use of package managers.

#### Download

The repository and instructions can be found [here](https://github.com/skiffos/SkiffOS/tree/master/configs/pine64/phone).

#### Notes

Upgrade over-the-air via a simple rsync script, or copying 3 files.

Uses the [Buildroot](http://buildroot.org) cross-compilation tool for support for all Pine64 boards.

Use configuration packages to configure distro:

| Package | Distro |
| -------- | ------- |
| core/pinephone_neon | KDE Neon via Ubuntu repositories |
| core/pinephone_nixos | Nixos Mobile |
| core/pinephone_gentoo | Gentoo with Link-time Optimization & KDE Mobile or Phosh |
| core/pinephone_ubports | Ubuntu Ports for PinePhone |
| core/pinephone_manjaro_kde | Manjaro for PinePhone: KDE variant |
| core/pinephone_manjaro_phosh | Manjaro for PinePhone: Phosh variant |
| core/pinephone_manjaro_lomiri | Manjaro for PinePhone: Lomiri variant |

The boot-up OS is upgraded independently from the containers.

### Slackware

[Slackware](https://arm.slackware.com/) is the world's oldest actively developed Linux distribution, providing a modern user land (applications) and Linux Kernel, within a more classic Unix Operating System environment.

#### Download

* https://dl.irradium.org//slackware/images/pinephone/

#### Notes

Discussion: [Thread](https://forum.pine64.org/showthread.php?tid=12181&highlight=slackware+pinephone)

### Ubuntu Touch

{{< figure src="/documentation/images/Ubports-logo.png" width="100" >}}

A Mobile Version of the Ubuntu Operating System made and maintained by the UBports Community. The port is currently maintained by Oren Klopfer (oklopfer).
	
{{< admonition type="note" >}}
 Tow-Boot is required for installing the latest version of Ubuntu Touch (20.04) on the PinePhone. Instructions for installing Tow-Boot to the PinePhone can be found [here](https://tow-boot.org/devices/pine64-pinephoneA64.html). 
{{< /admonition >}}
	
Installation instructions can be found at [this UBports post](https://ubports.com/en/blog/ubports-news-1/post/pinephone-and-pinephone-pro-3889). After Tow-Boot has been installed to your device, Ubuntu Touch installation just requires flashing the _.img.xz_ to an SD or the eMMC.

#### Download

* [UBports 20.04 PinePhone Latest Releases](https://gitlab.com/ook37/pinephone-pro-debos/-/releases)
* [UBports PinePhone Device Info](https://devices.ubuntu-touch.io/device/pinephone/release/focal)

| Default credentials | |
| -------- | ------- |
| Default user | Set during boot
| root | `phablet`/`1234` |

#### Notes

Scroll down to the middle of [the GitLab project page](https://gitlab.com/ook37/pinephone-pro-debos/), or directly here [at the UBports website](https://devices.ubuntu-touch.io/device/pinephone/release/focal/#deviceOverview) to see which features work.
	
Contributions and bug reports can be made at the [UBports PinePhone GitLab page](https://gitlab.com/ook37/pinephone-pro-debos/). See [UBports website](https://ubports.com/foundation/sponsors) for how to donate.

## Tools

There are software tools, that can be booted on the PinePhone.

### JumpDrive

JumpDrive can be used to flash the eMMC (and the microSD card), see [Installation instructions](/documentation/PinePhone/Installation/Installation_to_the_eMMC/#using_jumpdrive).

See https://github.com/dreemurrs-embedded/Jumpdrive/releases for the latest image.
Make sure to download the "PinePhone" image and to unpack the archive before flashing.

### Tow-Boot

Tow-Boot is a more user-friendly distribution of U-Boot. Can also mount internal storage as USB Mass Storage by holding the volume up button at startup before and during the second vibration and the LED will turn blue if done successfully.

See https://github.com/Tow-Boot/Tow-Boot/releases for the latest image.
Make sure to download the image with pinephoneA64 in the name.

## Hardware test build

{{< admonition type="warning" >}}
 The factorytest image for hardware testing appears to be no longer maintained.
{{< /admonition >}}

On the Braveheart model, there was a postmarketOS based basic Factory Test OS pre-installed on the eMMC. The developer Martijn Braam from postmarketOS has improved the functionality of the image considerably later. Since the 20200501 version, it is able to test all the hardware. It also includes functionality to install a new OS to the eMMC when using with an test image that includes that OS image. The downloadable image just does the hardware tests. Do not flash eMMC to test your device, just flash it to microSD and test from there. New versions are distributed as part of the postmarketOS distribution.

{{< admonition type="note" >}}
 The magnetometer test will fail on the new Beta Edition, as the factory image wasn't updated for it yet.
{{< /admonition >}}

Links:

* [Software Images](https://images.postmarketos.org/pinephone/) (*NOTE:* Link is is broken) (download the latest one named like pine-pinephone-yyyyMMdd-factorytestX.img.xz)
* [Git repo](https://gitlab.com/MartijnBraam/factorytest)
* [Documentation](https://gitlab.com/MartijnBraam/factorytest/-/blob/master/README.rst)

## Historic factory builds

These are different operating system builds that was preloaded in the factory with testing utility.

Download the build, extract the image and dd it to a 8 GB or larger microSD card, then insert it into the PinePhone.
After power up or reboot, you may perform and complete the test routine, or apply the build from microSD card to eMMC.

All the download links below are direct download from pine64.org.

{{< admonition type="warning" >}}
 These images are for testing purposes only. If you are looking for an up-to-date image please select one from the
{{< /admonition >}}
software releases section instead.

| Distribution | Download Link | File Size | MD5 |
| -------- | ------- | ------- | ------- |
| Beta Edition | [pine64-pinephone-plamo-beta-factorytest.img.xz](https://files.pine64.org/os/PinePhone/BetaEdition/pine64-pinephone-plamo-beta-factorytest.img.xz) | 1.78GB | `f16bce93504a52217540ac886863a418` |
| Mobian | [pine64-pinephone-20201207-factorytest-mobian.img.xz](https://files.pine64.org/os/PinePhone/Mobian/pine64-pinephone-20201207-factorytest-mobian.img.xz) | 1.41GB | `015be381ff4e650a7fca6d4eaa90d63d` |
| KDE | [pine64-pinephone-20201208-factorytest-kde.img.xz](https://files.pine64.org/os/PinePhone/KDE/pine64-pinephone-20201208-factorytest-kde.img.xz) | 2.28GB | `32979ff17b5ec4d358ce99f1aff0c77c` |
| Manjaro | [pine64-pinephone-20201013-manjaro-stable-20201018-factory56.img.xz](https://files.pine64.org/os/PinePhone/Manjaro/pine64-pinephone-20201013-manjaro-stable-20201018-factory56.img.xz) | 1.04GB | `4edfd4dceaefdd32a3417c1727161c29` |
| postmarketOS | [pine64-pinephone-20200726-phosh-v20.05-factory.img.xz](https://files.pine64.org/os/PinePhone/PostMarketOS/pine64-pinephone-20200726-phosh-v20.05-factory.img.xz) | 517MB | `244093be2f6d728fcbd1d29114607727` |
| Ubuntu Touch | [PinePhone-flasher-ubuntu-7b.img.gz](https://files.pine64.org/os/PinePhone/UBPorts/PinePhone-flasher-ubuntu-7b.img.gz) | 1.05GB | `2d7f5271e7a281db8f1b1219bedbe131` |

## Further Releases

### Apache NuttX RTOS

[Apache NuttX RTOS](https://nuttx.apache.org/docs/latest) is a Real-Time Operating System that supports PinePhone

* [Apache NuttX RTOS on PINE64 PinePhone](https://nuttx.apache.org/docs/latest/platforms/arm/a64/boards/pinephone/index.html)

### Sculpt Operating System (Genode OS Framework)

[Sculpt OS since version 23.04](https://genode.org/news/sculpt-os-release-23.04) supports PinePhone.

Ready-to-use system image available on the [download page](https://genode.org/download/sculpt).

## Installing other ARM64 distributions

Other ARM64 distributions might be installed as well, however this requires some tinkering and may not work well.

{{< admonition type="note" >}}
Distributions not on this page may not even boot after you follow this section. In the best case, they will be barely usable.
This is more for fun, or if you would like to port a new distribution to the PinePhone.
{{< /admonition >}}

General steps:

1. Create a boot partition (from 4 MB to about 252 MB) and a root partition (from the end of boot to the end of the card) filesystem on the SD card.
2. Format the boot partition with vfat, and the root partition with a supported filesystem like ext4 or f2fs.
3. Extract the root filesystem from your distribution's ARM image into the root filesystem on the SD card. Do not copy the partition, copy the files instead (in archive mode, like `rsync -ar`).
4. Edit `/etc/fstab` to match your partitions.
5. Grab megi's kernel from https://xff.cz/kernels/, Follow the instructions in the [README](https://xff.cz/kernels/README), which involves copying the kernel modules into the SD card rootfs, and writing u-boot and the bootloader.

If you would like to see examples or specific commands for how to complete these steps, see:

* [an example for Fedora](https://github.com/nikhiljha/pp-fedora-sdsetup), current unofficial [#Fedora] release
* [an example for Arch Linux](https://xnux.eu/howtos/install-arch-linux-arm.html) by megi

## Other Resources

Other software information

* [sunxi community wiki](https://linux-sunxi.org/Main_Page)
* [megi's feature/driver support matrix](https://xnux.eu/devices/pine64-pinephone.html)
* [megi bootUI notes (for dualbooting/multibooting)](https://megous.com/dl/tmp/README.bootui) see demonstration [on YouTube](https://www.youtube.com/watch?v=ZL1GREqoqx8)
* [ayufan boot tools](https://github.com/ayufan-pine64/boot-tools)

Other

* [Pine64 blog on blobs](https://www.pine64.org/2020/01/24/setting-the-record-straight-pinephone-misconceptions/)
* [Martijn Braam Librem 5 comparison, especially covering openness/blobs](https://tuxphones.com/yet-another-librem-5-and-pinephone-linux-smartphone-comparison/)
* [Bart Ribbers blog on Linux distributions and desktop environments on mobile devices](https://fam-ribbers.com/2019/12/28/State-of-Linux-on-mobile-and-common-misconceptions.html)
* [Jeff Geerling on testing microSD cards](https://www.jeffgeerling.com/blog/2019/a2-class-microsd-cards-offer-no-better-performance-raspberry-pi)

