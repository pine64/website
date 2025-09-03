---
title: "Camera"
draft: false
menu:
  docs:
    title:
    parent: "PinePhone_Pro"
    identifier: "PinePhone_Pro/Camera"
    weight:
---

The PinePhone Pro has two cameras, Sony IMX258 with 13MP as rear camera and OmniVision OV8858 with 8MP as front-facing camera.

{{< figure src="/documentation/images/Rose.jpg" caption="Example picture taken on the PinePhone’s rear camera by Martijn Braam using his app _Megapixels_." width="400" >}}


As mentioned in [Software State](/documentation/PinePhone_Pro/Software/Software_state/) cameras work-in-progress with DTS fix[Citation]; userspace still needs to do some catching up; Green image tint[Citation]. This article explains how to fix camera sofware on your PinePhone Pro. The work is on progress and will be available soon for different distributions. Make sure your PinePhone Pro is connected to the web to download needed software.


### Arch Linux ARM + Phosh Installation

Open terminal and update your system

```console
$ sudo pacman -Syyuu
```

Remove original Megapixels app

```console
$ sudo pacman -Rns megapixels
```

Install camera dependencies
```console
$ sudo pacman -Syu gst-plugin-libcamera libcamera-tools pipewire-libcamera
```

Install flatpak software manager

```console
$ sudo pacman -S flatpak
```

Install Megapixels2 app

```console
$ flatpak install https://flatpak.brixit.nl/megapixels2.flatpakref --user
```

You will be prompted to some options

* Should the remote be kept for future installations? [Y/n]: n
* Configure this as new remote 'flathub' [Y/n]: y
* Required runtime for me.gapixels.Megapixels/aarch64/master (runtime/org.gnome.Platform/aarch64/47) found in remote flathub. Do you want to install it? [Y/n]: y


To launch camera app you can both click on Megapixels icon on your desktop or enter into terminal following command

```console
$ flatpak run me.gapixels.Megapixels
```

In case you need to reinstall Megapixels2

```console
$ flatpak list
$ flatpak uninstall --delete-data me.gapixels.Megapixels
$ flatpak uninstall --unused
$ flatpak repair
```

Further details regarding the camera and the Megapixels camera app can be found on [Martijn’s blog](https://blog.brixit.nl/tag/phones/).
