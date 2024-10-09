---
title: "Building"
draft: false
menu:
  docs:
    title:
    parent: "Ox64/Software"
    identifier: "Ox64/Software/Building"
    weight: 2
---

Start the building process cloning both the upstream Buildroot repository and the Buildroot Bouffalo overlay repository:

```console
 $ mkdir -p ~/ox64
 $ cd ~/ox64
 $ git clone https://github.com/buildroot/buildroot
 $ git clone https://github.com/openbouffalo/buildroot_bouffalo
```

Define an environment variable for the Buildroot Bouffalo overlay path:

```console
$ export BR_BOUFFALO_OVERLAY_PATH=$(pwd)/buildroot_bouffalo
```

Change directory into the cloned Buildroot folder:

```console
$ cd ~/ox64/buildroot
```

Apply the default configuration for Pine64 Ox64:

```console
$ make BR2_EXTERNAL=$BR_BOUFFALO_OVERLAY_PATH pine64_ox64_defconfig
```

Use the `menuconfig` tool to adjust the build settings:

```console
$ make menuconfig
```

Within `menuconfig`, configure the following:

* Select `Target Options`
* Enable `Integer Multiplication and Division (M)`
* Enable `Atomic Instructions (A)` using space key
* Enable `Single-precision Floating-point (F)`
* Enable `Double-precision Floating-point (D)`
* Select `Target ABI`, set it to `lp64d` and `press Exit`
* Select `Toolchain`, enable `Fortran support`, enable `OpenMP support`, and Save & Exit

Initiate the build process, but first make sure that your `PATH` variable contains no spaces. For Arch Linux distrubution you may also need to install extra-packages with `sudo pacman -S cpio rsync bc`.

```console
$ make
```

Buildroot will output the needed files to the `~/ox64/buildroot/output/images` directory in about 1 hour, according to your computer processing resources and internet connection speed.
