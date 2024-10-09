---
title: "Troubleshooting"
draft: false
menu:
  docs:
    title:
    parent: "ROCKPro64"
    identifier: "ROCKPro64/Troubleshooting"
    weight: 4
---

## No Video or GPU Acceleration on Debian

If you can log in through serial but don’t get any video or GPU acceleration on Debian, this is likely due to Debian’s decision to compile the devfreq governors as loadable modules but not including them early enough for panfrost to be able to be provided with one of them.

The usual sign of this being the case is the following line in the kernel log: `[drm:panfrost_devfreq_init [panfrost]] **ERROR** Couldn’t initialize GPU devfreq`

To fix this issue, run the following as _root_ and reboot:

```
echo governor_simpleondemand >> /etc/initramfs-tools/modules
update-initramfs -u -k $(uname -r)
```

## PCIe probe failures on Linux kernel boot

While booting the Linux kernel, you might experience PCIe probe failures, which render the attached PCIe device inaccessible. The ["drivers: pci: introduce configurable delay for Rockchip PCIe bus scan"](https://lore.kernel.org/all/20230509153912.515218-1-vincenzopalazzodev@gmail.com/) thread on the Linux kernel mailing list (LKML) discusses this issue and proposes a fix.

Manjaro ARM applies the following patches to the kernel package, which fix the issue:

* [1005-rk3399-rp64-pcie-Reimplement-rockchip-PCIe-bus-scan-delay.patch](https://gitlab.manjaro.org/manjaro-arm/packages/core/linux/-/blob/44e81d83b7e002e9955ac3c54e276218dc9ac76d/1005-rk3399-rp64-pcie-Reimplement-rockchip-PCIe-bus-scan-delay.patch)
* [1007-arm64-dts-rockchip-Add-PCIe-bus-scan-delay-to-RockPr.patch](https://gitlab.manjaro.org/manjaro-arm/packages/core/linux/-/blob/44e81d83b7e002e9955ac3c54e276218dc9ac76d/1007-arm64-dts-rockchip-Add-PCIe-bus-scan-delay-to-RockPr.patch)
