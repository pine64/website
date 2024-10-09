---
title: "Updating instructions"
draft: false
menu:
  docs:
    title:
    parent: "PinePhone/Software"
    identifier: "PinePhone/Software/Updating_instructions"
    weight: 3
---

## Methods of updating
There is no need to regularly flash the newest images to your phone because the underlying system is built on pre-existing package managers for maintaining integrity. You can use the GUI applications (usually 'Software' or 'Discover') or because there is always a terminal nearby, these commands will help you stay updated with the latest available programs from your default selected repository.

## Mobian and other Debian-based distributions

To update all software, the following command will refresh the package cache, check for updates and install them:

```console
$ sudo apt-get update && sudo apt-get upgrade
```

If some packages were held back, you can update them with:

```console
$ sudo apt-get dist-upgrade
```

## Manjaro and other Arch-based distributions

To update all packages under Arch-based distributions, the package manager _pacman_ can be used:

```console
$ sudo pacman -Syu
```

Note: `sudo pacman -Syu --cachedir /path/to/external` can be used for a separate download location to improve installation speed, otherwise consider reading https://wiki.archlinux.org/index.php/Pacman#Configuration for further optimization.

If you encounter any errors during the update, you may have to update the Pacman mirrors. Under Manjaro this can be done using `sudo pacman-mirrors -f`
