---
title: "Loading code"
draft: false
menu:
  docs:
    title:
    parent: "PineCone"
    identifier: "PineCone/Loading_code"
    weight: 4
---

To load code, you must move the jumper to the position closest to the edge, press reset, load the code, move the jumper back toward the center of the board, and press reset again.

There are currently a number of loaders in progress, each with differing degrees of completeness and success on various operating systems.

* In the build tree, there is BLFlashCube for Windows, which is a proprietary GUI for flashing images. Linux and macOS binaries are available via [Bouffalo Lab’s developer portal](https://dev.bouffalolab.com/download).
* [bl60x-flash](https://github.com/stschake/bl60x-flash) is in Python and has been reported successful on MacOS catalina (10.15.6) by Punnerud and madushan1000.
* [BLOpenFlasher](https://github.com/bouffalolab/BLOpenFlasher) is a WIP, written in go, by Bouffalo Labs to provide source for a flash utility.
* [bl602tool](https://github.com/renzenicolai/bl602tool) is a Python utility in development.
* [Bouffalo’s MCU tool](https://pypi.org/project/bflb-mcu-tool/) (Mar 2021) Python image tool replaced both of the above. Now combined with eflash loader, deals with partitions, DTS, signing, fuses etc.
* [blflash serial flasher](https://github.com/spacemeowx2/blflash) BL602 serial flasher, inspired by BLOpenFlasher
