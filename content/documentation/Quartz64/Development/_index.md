---
title: "Development"
draft: false
menu:
  docs:
    title:
    parent: "Quartz64"
    identifier: "Quartz64/Development"
    weight: 3
aliases:
  - /wiki/Quartz64_Development
---

This page documents the current status of software support for the [Quartz64](/documentation/Quartz64) single-board computer, and provides links to resources to help prospective contributors get started. Information is kept current on a best-effort basis as various patches get accepted into the kernel.

## Overview

### Upstreaming Status

| Function | Status | | Component | Notes | Applies To | 
| --- | --- | --- | --- | --- | --- |
| **Video Output** | Linux Mainline | | `rockchipdrm/VOP2` | As of 5.19-rc1<sup>[Source](https://git.kernel.org/linus/604be85547ce4d61b89292d2f9a78c721b778c16)</sup>,Also featured in Phoronix Article<sup>[Source](https://www.phoronix.com/scan.php?page=news_item&px=Rockchip-VOP2-Linux-5.19)</sup>, 4k@30 support and other improvements in 6.4-rc1<sup>[Source](https://git.kernel.org/linus/83b61f817f43ed67572d1e241c9f552e0a8bfff4)</sup> |
| | Needs porting | | `rockchip-edpphy-naneng` | Downstream: [Source](https://gitlab.com/pine64-org/quartz-bsp/rockchip-linux/-/blob/quartz64/drivers/phy/rockchip/phy-rockchip-naneng-edp.c) and [Source](https://gitlab.com/pine64-org/quartz-bsp/rockchip-linux/-/commit/d7ad116fb30d11d110aeb880754cf27f34c45c40#7e8e2ef87e479c54539dc519c0b92d6b31727f8d_671_681) Coordinate any porting with Rockchip first |
| | Linux Mainline | | `dw-mipi-dsi-rockchip` | As of 6.1<sup>[Source](https://git.kernel.org/linus/e18d9b093006d8abd53e1ce13c0d5a8d0fcd5f64)</sup> |
| **3D Acceleration** | Linux Mainline | Upstream Mesa | `panfrost` | As of 5.18<sup>[Source](https://git.kernel.org/linus/810028668c6d9da25664195d6b906c98a8169f72)</sup> |
| **Video Decode** | Linux Mainline | GStreamer only, no ffmpeg<sup>[Source](https://patchwork.ffmpeg.org/project/ffmpeg/list/?series=2898)</sup> | `hantro` using `v4l2-requests` | VDPU121 handling 1080p MPEG-2, VP8 and H.264. Mainline as of 5.19<sup>[Source](https://git.kernel.org/linus/5f6bfab6da6531238e899fdf29efd6d0185adc3e)</sup> |
| | Needs writing | | `rkvdec2` using `v4l2-requests` | VDPU346 handling 4K H.265, H.264 and VP9 |
| | Needs writing | | `rkdjpeg` using `v4l2-requests` | VDPU720 handling JPEG, User:CounterPillow is working on this |
| **Video Encode** | Linux Mainline | GStreamer only | JPEG on VEPU121 | Hantro-based. Mainline as of 6.1<sup>[Source](https://git.kernel.org/linus/6f1ae821a6c4aa9d5b8f437b27ec86fb569219fd)</sup> |
| | Needs writing | ? | H.264 on VEPU121 | Hantro-based |
| | Needs writing | ? | VP8 on VEPU121 | Hantro-based |
| | Needs writing | ? | H.264 on VEPU540 | rkvenc-based |
| | Needs writing | ? | H.265 on VEPU540 | rkvenc-based |
| **Audio** | Linux Mainline | | `rockchip-i2s-tdm` | As of 5.16<sup>[Source](https://git.kernel.org/linus/43b058698f723e3c2087af7069c0da082a3ecbe1)</sup> |
| | Linux Mainline | | `rockchip-spdif` | As of 5.15<sup>[Source](https://git.kernel.org/linus/dac825b6a6bdca41347e25f07354ad94fdc97445)</sup> |
| | Linux Mainline | | `rk817-codec` | As of 5.14<sup>[Source](https://git.kernel.org/linus/0d6a04da9b25b9a7cf2cac5f5079e3296d3bee0f)</sup>. | Quartz64 Model A/B |
| **Bootloader** | In review<sup>[Source](https://review.trustedfirmware.org/c/TF-A/trusted-firmware-a/+/16952)</sup> | | `TF-A` | |
| | Merged | | `U-Boot` | #mainline_u_boot_work[See below]. Quartz64 and SOQuartz as of v2023.10-rc2<sup>[Source](https://source.denx.de/u-boot/u-boot/-/commit/4e619e8d4fd68095bc665a78f2651d8e478a4534)</sup> |
| | In progress<sup>[Source](https://github.com/jaredmcneill/quartz64_uefi)</sup> | | `Tianocore EDK II` | |
| **Device Tree** | Linux Mainline | | Quartz64 Model A | As of 5.16<sup>[Source](https://git.kernel.org/linus/b33a22a1e7c4248608e533fc4fa524258b3fae84)</sup> | Quartz64 Model A |
| | Linux Mainline | | Quartz64 Model B | As of 5.19<sup>[Source](https://git.kernel.org/linus/c37415f55bdadffe5b4c0e7981e9fc7e8b96beea)</sup> | Quartz64 Model B |
| | Linux Mainline | | SOQuartz | As of 5.19<sup>[Source](https://git.kernel.org/linus/c466828fb3ba8cb7f5c3bf28766da9b70bf9745e)</sup> | SOQuartz |
| | Linux Mainline | | PineNote | As of 5.18<sup>[Source](https://git.kernel.org/linus/d449121e5e8addcee654250cec298c887ecafb32)</sup> | PineNote |
| **Gigabit Ethernet** | Linux Mainline | | `rk3566-gmac` | As of 5.14<sup>[Source](https://git.kernel.org/linus/3bb3d6b1c1957e88bfc5e77a4557f7e6ba761fe3)</sup> |
| | Linux Mainline | | `yt8511-phy` | As of 5.14<sup>[Source](https://git.kernel.org/linus/48e8c6f1612b3d2dccaea2285231def830cc5b8e)</sup> |
| **IOMMU** | Linux Mainline | | `rockchip-iommu` | As of 5.14<sup>[Source](https://git.kernel.org/linus/c55356c534aa651ccc3053ef2d5d8d810adacf5f)</sup> |
| **GPIO** | Linux Mainline | | `gpio-rockchip` | As of 5.15<sup>[Source](https://git.kernel.org/linus/936ee2675eee1faca0dcdfa79165c7990422e0fc)</sup> | 
| **pinctrl** | Linux Mainline | | | |
| **Thermal Regulation** | Linux Mainline | | `rockchip-thermal` | As of 5.14<sup>[Source](https://git.kernel.org/linus/4b14c055a6f644cbeb1156ba24647e92fe51ec69)</sup> |
| **PCIe** | Linux Mainline | | `pcie-dw-rockchip` | As of 5.15<sup>[Source](https://git.kernel.org/linus/0e898eb8df4e34c7b129452444eb7cef68a11f43)</sup> |
| **Power Management** | Linux Mainline | | `rockchip-pm-domains` | As of 5.14<sup>[Source](https://git.kernel.org/linus/1782c87b44a0b1a527f01a6a184677c58ccbf9c7)</sup> |
| **Voltage Control** | Linux Mainline | | `rk3568-pmu-io-voltage-domain` | As of 5.15<sup>[Source](https://git.kernel.org/linus/28b05a64e47cbceebb8a5f3f643033148d5c06c3)</sup> |
| **SPI** | Linux Mainline | | `spi-rockchip` | As of 5.14<sup>[Source](https://git.kernel.org/linus/d74d99229f4d48f42d674f7a8a1137179efd67ac)</sup>.Necessary device tree changes [in review](https://patchwork.kernel.org/project/linux-rockchip/list/?series=586691). |
| **Battery** | Linux Mainline | | `rk817-charger` | As of 6.1<sup>[Source](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/drivers/power/supply/rk817_charger.c?id=11cb8da0189b417392e2334ae967b0ba1f0d1be8)</sup> | Quartz64 Model A, PineNote |
| **Microphone** | Linux Mainline | | `rockchip-saradc` | As of 5.15<sup>[Source](https://git.kernel.org/linus/7786da3b5ae167c17f35e22ba35e06006338c2f6)</sup>. Headphone jack mic seems to connect to `SARADC_VIN2_HP_HOOK`, so I'm pretty sure that the dtsi and driver changes are needed for that mic to work |
| **USB 2.0** | Linux Mainline | | `rockchip-usb2phy` | As of 5.17<sup>[Source](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/drivers/phy/rockchip?h=v5.17-rc1&id=42b559727a45d79c811f493515eb9b7e56016421)</sup> |
| **e-Ink** | In review (RFC)<sup>[Source](https://lore.kernel.org/linux-rockchip/20220413221916.50995-1-samuel@sholland.org/T/)</sup> | | `rockchip-ebc` | A DRM driver is available [here](https://github.com/smaeul/linux/commits/rk35/ebc-drm-v5); See also [RK3566 EBC Reverse-Engineering](/documentation/General/RK3566_EBC_reverse-engineering) |
| **Combo PHY** | Linux Mainline | | `naneng-combphy` | As of 5.18<sup>[Source](https://git.kernel.org/linus/7160820d742a16313f7802e33c2956c19548e488)</sup>. Still requires DTS changes |
| **RGA** | Linux Mainline; Could be improved | | `rockchip-rga` | As of 6.5<sup>[Source](https://git.kernel.org/linus/0c3391f8bb06b744df521651534cd99e3d77e0a8)</sup>. Note that there's still a '4GB' problem and it's implementations has room for improvements (to put it midly <sup>[Source](https://lore.kernel.org/all/20230522102953.GB23678@pengutronix.de/)</sup> and <sup>[Source](https://lore.kernel.org/all/b404dc20-c460-ac3f-6659-8be7a7d32bfe@arm.com/)</sup>) |
| **Fan Controller** | Needs writing | | `gp7101` | Someone should write a pwm driver for it so we can then use pwm-fan | SOQuartz Blade |
| **CSI Camera** | Needs porting | | `rkisp` | Downstream: [Source](https://gitlab.com/pine64-org/quartz-bsp/rockchip-linux/-/tree/quartz64/drivers/media/platform/rockchip/isp) |
| | Linux Mainline | | `rockchip-inno-csidphy` | As of 6.1<sup>[Source](https://git.kernel.org/linus/29c99fb085ad53e6d5504d1f8d32e6673b9b3a2c)</sup> |
| **NPU** | Needs writing | | | Downstream version is a closed source SDK and [open source kernel module rknpu](https://github.com/dieselnutjob/kernel-rk3566/tree/linux-4.19.210/drivers/rknpu). Major undertaking to reimplement this as Linux does not (yet) appear to have a generic architecture for neural accelerators. |
| **Crypto** | Needs porting | | `rk-crypto` v2 | Downstream driver ([link](https://gitlab.com/pine64-org/quartz-bsp/rockchip-linux/-/tree/quartz64/drivers/crypto/rockchip)) doesn't include a rk3568 compatible either, but the TRM shows that it seemingly matches. |
| **TRNG** | In review<sup>[Source](https://patchwork.kernel.org/project/linux-rockchip/list/?series=699813&archive=both)</sup> | | `rockchip-rng` | |
| **Wi-Fi** | Needs porting | | `bes2600` | A downstream driver is available but it makes use of some custom Rockchip interfaces and is designed for older kernels, plans are being made to port it to DKMS. | PineTab 2 |
| | Linux Mainline | | `brcmfmac` | | Quartz64 Model B |

## Current Status

The following sections give an overview over the current status of different parts of the board. Some parts are waiting on a driver to be written or ported, others only need various adjustments.

According to pgwipeout, I/O device performance is within expected ranges now.

### Working

* eMMC
* SDMMC0 (SD cards)
* GMAC (Gigabit Ethernet)
* USB 2.0
* SATA 2
* SATA 3
* UART
  * UART 0 (Pi-bus)
  * UART 1 (Bluetooth)
  * UART 2 (Pi-bus, debug)
* Video Decode
  * VP8
  * H.264
* Video Encode
  * JPEG (it’s pretty bad)
* Battery
* GPU
* Video Output
  * HDMI
  * DSI
* Audio
  * Analog audio works
  * SPDIF works
  * HDMI works
* SPI &mdash; works, user needs to modify device tree to add devices
* I^2^C &mdash; works, user needs to modify device tree to add devices

### Partially Working

* PCI-Express Controller &mdash; everything but devices that need cache coherency (e.g. dGPUs) should work
  * User:CounterPillow noticed some weirdness with NVMe devices disconnecting during heavy write operations, likely down due to power draw on one of the rails as the same sustained bandwidth could be achieved with a different PCIe device with no issue.
* SDMMC1 (Wi-Fi) &mdash; AP6256 working, BL602 needs some work to make it flash firmware
* [GIC](https://developer.arm.com/architectures/system-architectures/system-components/arm-generic-interrupt-controller) &mdash; needs errata published by Rockchip to get upstream to add device-specific workarounds ^link:https://lore.kernel.org/linux-rockchip/CAMdYzYrQ5f-mv_VmTq_CRf9tR=\j3mwRpKHNLmPFgCF9whsGFRw@mail.gmail.com/[link]^

### Confirmed Broken

* ~~USB 3.0 (applies to Model A only) &mdash; only works with very short cables and depends on the device. This is due to a hardware design issue relating to the coupling capacitors needed for SATA, which shares the same lines as USB 3.0.~~
  * ~~Hardware design changes have been suggested to engineers, it’s in their hands now.~~
  * Fixed in newer revisions by leaving SATA unpopulated
* RGA &mdash; only works with memory &le; 4 GiB, because Rockchip didn’t make the address registers larger. Oopsie.

### Needs Testing

* E-Paper
* Microphone Input
* CSI &mdash; needs CIF driver
* eDP &mdash; needs PHY driver and controller driver

## TODO

### ebc-dev Reverse Engineering and Development

The [driver for the eInk panel](https://gitlab.com/pine64-org/quartz-bsp/linux-next/-/tree/rk356x-ebc-dev) needs to both be reverse engineered and then rewritten as C. In its current form, it is mostly an assembly dump produced by gcc with debug symbols. See [RK3566 EBC Reverse-Engineering](/documentation/General/RK3566_EBC_reverse-engineering) for details.

### Investigate MCU

The RK3566 comes with an integrated RISC-V microcontroller (MCU). It communicates with the A55 host through the Mailbox system driven by the rockchip-mailbox driver. Since this MCU would be quite useful for things such as low power standby mode, investigating how it can be turned on and have firmware flashed to it should greatly enhance the power saving features of the PineNote.

The user liamur [did some investigation](https://github.com/liamhays/rk3566-mcu) into the MCU and found that it is disabled by TF-A on suspend, and doesn’t reside in a low-power part of the RK3566 anyway. It does however have access to most of the chip and could be used as (for example) a real-time coprocessor.

### Mainline U-Boot Work

We currently use the "downstream" Rockchip U-Boot, which is based on an old version of U-Boot and contains vendor specific patches that have not undergone the same level of code review as they’d have done had they been submitted upstream.

While the lack of ATF sources means that using mainline U-Boot would still require the use of Rockchip provided binaries for the firmware, even with Rockchip blobs, a more modern version of U-Boot will be much nicer to use.

Mainline U-Boot contains good enough support for the RK3566 SoC used on the Quartz64 as of v2023.07 and have support for Quartz64 and SOQuartz as of v2023.10-rc2. Drivers for [ethernet GMAC](https://patchwork.ozlabs.org/cover/1841800/) and [Motorcomm PHY](https://patchwork.ozlabs.org/patch/1817295/) are supported as of v2024.01-rc1.

#### Things that could be done

This list is non-exhaustive as we don’t exactly know how much is missing

* Port a basic VOP2 driver to get a framebuffer from u-boot

#### List of Useful Resources for this Task

* Downstream Rockchip U-Boot repository with Quartz64 specific patches: https://gitlab.com/pgwipeout/u-boot-rockchip/-/tree/quartz64
* Mainline Rockchip custodian U-Boot repository: https://source.denx.de/u-boot/custodians/u-boot-rockchip
* U-Boot Mailing List: https://lists.denx.de/listinfo/u-boot

### eDP Driver Porting

The eDP PHY driver and controller driver needs to be ported, brought into shape and submitted with proper commit attribution to the Rockchip authors.

User:CounterPillow has experimentally ported stuff, but it’s currently not working.

## Linux Kernel Config Options

* `CONFIG_SND_SOC_ROCKCHIP_I2S_TDM`
  * for Analog and HDMI audio
* `CONFIG_SND_SOC_RK817`
  * for Analog audio on the Model A
* `CONFIG_STMMAC_ETH`
  * Ethernet
* `CONFIG_DWMAC_ROCKCHIP`
  * Ethernet
* `CONFIG_MOTORCOMM_PHY`
  * Ethernet PHY for Model A, set this one to Y, m won’t work out of the box if the generic PHY driver is y and binds first. Alternatively tell users in board-specific setup instructions to force including the `motorcomm` module in initramfs if you set it to m.
* `CONFIG_REALTEK_PHY`
  * Ethernet PHY for Model B
* `CONFIG_MMC_DW`
  * MMC/SD
* `CONFIG_MMC_DW_ROCKCHIP`
  * MMC/SD
* `CONFIG_MMC_SDHCI_OF_DWCMSHC`
  * MMC/SD
* `CONFIG_PCIE_ROCKCHIP_DW_HOST`
  * PCIe
* `CONFIG_PHY_ROCKCHIP_NANENG_COMBO_PHY`
  * PHY for PCIe/SATA/USB3
* `CONFIG_DRM_PANFROST`
  * GPU
* `CONFIG_SND_SOC_ROCKCHIP_SPDIF`
  * SPDIF audio
* `CONFIG_ROCKCHIP_DW_HDMI`
  * HDMI PHY
* `CONFIG_PHY_ROCKCHIP_INNO_DSIDPHY`
  * MIPI DSI DPHY
* `CONFIG_ROCKCHIP_VOP2`
  * Video output
* `CONFIG_ARCH_ROCKCHIP`
  * General SoC support
* `CONFIG_ROCKCHIP_PHY`
  * General SoC support
* `CONFIG_PHY_ROCKCHIP_INNO_USB2`
  * USB 2
* `CONFIG_RTC_DRV_RK808`
  * Real-time Clock
* `CONFIG_COMMON_CLK_RK808`
  * Real-time Clock
* `CONFIG_MFD_RK808`
  * Various things relating to the RK817 chip
* `CONFIG_CHARGER_RK817`
  * RK817 charger
* `CONFIG_REGULATOR_RK808`
  * Voltage regulators
* `CONFIG_ROCKCHIP_PM_DOMAINS`
  * Power management domains
* `CONFIG_GPIO_ROCKCHIP`
  * GPIO support
* `CONFIG_PINCTRL_ROCKCHIP`
  * GPIO and general SoC support
* `CONFIG_PWM_ROCKCHIP`
  * PWM support
* `CONFIG_ROCKCHIP_IOMMU`
  * IOMMU support
* `CONFIG_ROCKCHIP_MBOX`
  * Mailbox support (for communication with MCU)
* `CONFIG_ROCKCHIP_SARADC`
  * Analog-to-digital conversion support, for e.g. microphones
* `CONFIG_ROCKCHIP_THERMAL`
  * Temperature sensor and thermal throttling support
* `CONFIG_SPI_ROCKCHIP`
  * SPI support
* `CONFIG_VIDEO_HANTRO_ROCKCHIP`
  * Hardware video decoder support
* `CONFIG_ROCKCHIP_IODOMAIN`
  * General SoC support so your I/O pins have the right voltage
* `CONFIG_COMMON_CLK_ROCKCHIP`
  * Common clock support
* `CONFIG_PHY_ROCKCHIP_INNO_CSIDPHY`
  * MIPI CSI DPHY
* `CONFIG_I2C_RK3X`
  * I2C support

## Resources

### Repositories

* pgwipeout’s kernel tree
  * https://gitlab.com/pgwipeout/linux-next/-/tree/quartz64-v5.15-rc1
* BSP based development effort for SPL/U-Boot and Linux
  * https://gitlab.com/pine64-org/quartz-bsp
* Image CI pipeline aimed at developers
  * https://gitlab.com/pgwipeout/quartz64_ci/
* Rockchip U-Boot
  * https://github.com/rockchip-linux/u-boot
* Downstream rockchip-linux kernel tree
  * https://gitlab.com/pine64-org/quartz-bsp/rockchip-linux
* Tianocore EDK II port for UEFI on Quartz64
  * https://github.com/jaredmcneill/quartz64_uefi
* Mainline U-Boot Port by pgwipeout
  * https://gitlab.com/pgwipeout/u-boot-quartz64

### Other

* Rockchip-SoC Patchwork Page
  * https://patchwork.kernel.org/project/linux-rockchip/list/
* Rockchip Kernel Mailing List Archive
  * https://lore.kernel.org/linux-rockchip/

## Board/SoC Documentation

### Booting

#### Boot Order

The RK3566 boot ROM will search for a valid ID BLOCK in the following order on the support boot media:

* SPI NOR flash
* SPI NAND flash
* eMMC
* SD-Card

If this fails, the boot ROM will initialize the USB0 port and wait for a connection from the Rockchip
flash/boot tools.

#### Bootloader Flashing

As per pgwipeout’s [commit message](https://gitlab.com/pine64-org/quartz-bsp/u-boot/-/commit/12d102b86813378af08b086f3b9c13ed8010754c):

* Make a partition named `uboot` as partition number 1 at 8 MiB to 16 MiB
* `dd if=idblock.bin of=/dev/_<mmc/sd>_ seek=64`
* `dd if=uboot.img of=/dev/_<mmc/sd>_1`
