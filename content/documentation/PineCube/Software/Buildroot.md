---
title: "Buildroot"
draft: false
menu:
  docs:
    title:
    parent: "PineCube/Software"
    identifier: "PineCube/Software/Buildroot"
    weight: 
---

	
PineCube is supported in Buildroot since version 2023.11. See the file [board/pine64/pinecube/readme.txt](https://git.busybox.net/buildroot/tree/board/pine64/pinecube/readme.txt?h=next) in the Buildroot repository for details how to build it.

There is also available Buildroot fork by [Elimo Engineering](https://elimo.io), you can find the repository on [Elimo’s GitHub account](https://github.com/elimo-engineering/buildroot) and build instructions in the [board support directory](https://github.com/elimo-engineering/buildroot/tree/pine64/pinecube/board/pine64/pinecube) readme.

The most important thing that this provides is support for the S3’s DDR3 in u-boot. Unfortunately mainline u-boot does not have that yet, but the u-boot patches from [Daniel Fullmer’s NixOS repo](https://github.com/danielfullmer/pinecube-nixos) were easy enough to use on buildroot.

This should get you a functional system that boots to a console on UART0. It’s pretty fast too, getting there in 1.5 seconds from u-boot to login prompt.
