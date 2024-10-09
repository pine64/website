---
title: "Reuse microSD card"
draft: false
weight: 
menu:
  docs:
    title:
    parent: "PinePhone/Installation"
    identifier: "PinePhone/Installation/Reuse_microSD_card"
    weight: 4
---

Once you have installed your release of choice to eMMC, you may wish to use an microSD card for data storage. If you choose to re-use a card you have previously used to boot from, you will find your phone might not boot if you just reformat the card and insert it. This is because the Allwinner firmware in the PinePhone uses some (normally) unused space at the front of the microSD card to store boot software, which you need to clear.

This can be done as follows on any Linux system:

    lsblk

to check the device of your microSD card – as an example lets assume it is /dev/mmcblk0
then

`sudo dd if=/dev/zero of=/dev/**[DEVICE]** bs=8k seek=1 count=4`

will clear the relevant sectors of your card.

Since Danctnix (arch) switched to a gpt partition table from mbr in May of 2022 it installs u-boot at an offset of 128k instead of 8k, which means this command must be used instead

`sudo dd if=/dev/zero of=/dev/**[DEVICE]** bs=32k seek=4 count=1`
