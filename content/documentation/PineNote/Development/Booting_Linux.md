---
title: "Booting Linux"
draft: false
menu:
  docs:
    title:
    parent: "PineNote/Development"
    identifier: "PineNote/Development/Booting_Linux"
    weight: 3
aliases:
  - /wiki/PineNote_Development/Booting_Linux
---

{{< admonition type="warning" >}}
This page is only relevant for the first batch of PineNotes (December 2021)! The second batch of PineNotes (October 2024) come with Linux pre-installed!
{{< /admonition >}}

To boot Linux, the stock U-Boot has to be patched.

Here the method from [charasyn](https://gist.github.com/charasyn/206b2537534b6679b0961be64cf9c35f) is used, based of work from Dorian as credited in the script. We’ll use the script to pull the U-Boot environment out of the stock U-Boot partition. We’ll then apply the patch, recreate the image, add a configuration file, and flash the new image to the PineNote.

## Steps to patch U-Boot

* Get the [patch and the Python tool](https://gist.github.com/charasyn/206b2537534b6679b0961be64cf9c35f):

  ```console
  $ mkdir pinenote-uboot && cd pinenote-uboot
  $ curl https://gist.githubusercontent.com/charasyn/206b2537534b6679b0961be64cf9c35f/raw/cc513998a36fac0cea266260e3ca3e64abfe3696/boot-menu.patch -o boot-menu.patch
  $ curl https://gist.githubusercontent.com/charasyn/206b2537534b6679b0961be64cf9c35f/raw/cc513998a36fac0cea266260e3ca3e64abfe3696/pinenote-uboot-envtool.py -o pinenote-uboot-envtool.py
  $ chmod o+x pinenote-uboot-envtool.py
  ```
* Write your U-Boot partition to an image file: `dd if=/dev/mmcblk0p1 of=~/uboot.img`
* Extract the environment: `./pinenote-uboot-envtool.py extract uboot.img uboot.env`
* Poke around the files (or skip this if you don’t like to learn):
* Open `uboot.env` -- see, it’s just text at this point! 
* Open `boot-menu.patch` to get a feel for how that works
* The boot-menu.patch makes assumptions about where your Linux partition lives. Specifically, it will look at partition 0x11 (which is 17 in decimal). Change this in boot-menu.patch to reflect where your Linux boot partition lives.
* Apply boot-menu.patch: `patch uboot.env boot-menu.patch`

{{< admonition type="note" >}}
 Note: Might fail with the following error: "_patch: \****** unexpected end of file in patch at line 27_". In that case applying the patch manually is the solution.
{{< /admonition >}}

* Rewrite the new environment to the image: `./pinenote-uboot-envtool.py insert uboot.img uboot.env uboot-patched.img`
* Write the image to the boot partition from the PineNote: `dd if=~/uboot-patched.img of=/dev/mmcblk0p1`
* At this point, restarting your system will boot into Android -- this is because the patched U-Boot we’ve just created looks for `/boot/which_os.txt` to determine whether to boot Android or Linux, and since it can’t find this file (we haven’t made it yet), the bootloader defaults to Android. Create that file on the same boot partition you specified in the boot-menu.patch file, placing an `l` in the file for Linux.
* Reboot into Linux

## Sources and further reading

1. [U-boot with rockchip docs](https://u-boot.readthedocs.io/en/latest/board/rockchip/rockchip.html)
2. [Helpful stack overflow to learn a bit about the boot process/terminology](https://stackoverflow.com/questions/31244862/what-is-the-use-of-spl-secondary-program-loader)
3. [This conversation in matrix between pgwipeout, vveapon, and pinenewb about flashing U-Boot.](https://matrix.to/#/!QtTzSRYMuozjbOQkzJ:matrix.org/$bVBxdD3E01da7w4LRm45-mwbw_jPk6CrJTQWGMG3B2I?via=matrix.org&via=kde.org&via=tchncs.de)
