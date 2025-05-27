---
title: "Mainlining"
draft: false
menu:
  docs:
    title:
    parent: "PineCube/Software"
    identifier: "PineCube/Software/Mainlining"
    weight: 2
---

Please note:

* this list is most likely not complete
* no review of functionality is done here, it only serves as a collection of efforts

Linux kernel:

| Type                                | Link                                                                                              | Available in version |
| --------                            | -------                                                                                           | ------- |
| Devicetree Entry Pinecube           | https://lkml.org/lkml/2020/9/22/1241                                                              | 5.10
| Correction for AXP209 driver        | https://lkml.org/lkml/2020/9/22/1243                                                              | 5.9
| Additional Fixes for AXP209 driver  | https://lore.kernel.org/lkml/20201031182137.1879521-8-contact@paulk.fr/                           | 5.12
| Device Tree Fixes                   | https://lore.kernel.org/lkml/20201003234842.1121077-1-icenowy@aosc.io/                            | 5.10
| Audio Device and IR LED Fix         | https://github.com/danielfullmer/pinecube-nixos/blob/master/kernel/Pine64-PineCube-support.patch  | https://github.com/danielfullmer/pinecube-nixos/issues/2[TBD] |

U-boot:

| Type                                | Link                                                                | Available in version |
| --------                            | -------                                                             | ------- |
| PineCube Board Support              | https://patchwork.ozlabs.org/project/uboot/list/?series=210044      | v2021.04 |

Buildroot:

| Type                                | Link                                                                | Available in version |
| --------                            | -------                                                             | ------- |
| PineCube Board Support              | https://patchwork.ozlabs.org/project/buildroot/list/?series=314653  | 2023.11 |
