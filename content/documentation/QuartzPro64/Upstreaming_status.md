---
title: "Upstreaming status"
draft: false
menu:
  docs:
    title:
    parent: "QuartzPro64"
    identifier: "QuartzPro64/Upstreaming_status"
    weight: 2
---

* Upstream Linux kernel DT: https://github.com/torvalds/linux/blob/master/arch/arm64/boot/dts/rockchip/rk3588-quartzpro64.dts
* Upstream U-Boot DT: https://github.com/u-boot/u-boot/blob/master/arch/arm/dts/rk3588-quartzpro64-u-boot.dtsi

| Function | Status | | Component | Notes |
| --- | --- | --- | --- | --- |
| **Video Output** | Needs porting | | `VOP2` | Collabora said they’ll work on this. The video output IP on the RK3588 should mostly be the same as the one on the RK356x, but the chip specific stuff will need to be integrated into the vop2 driver. |
| **Video Input** | Needs porting | | `rk_hdmirx` | Huge 3600 line driver, but generally seems to be in good condition | 
| **3D Acceleration** | Needs writing | Needs writing | `panfrost` | Collabora said they’ll work on this. New architecture, reportedly needs many changes to the kernel component of Panfrost. |
| **Video Decode** | Needs writing | GStreamer only, no ffmpeg<sup>[Source](https://patchwork.ffmpeg.org/project/ffmpeg/list/?series=2898)</sup> | `hantro` using `v4l2-requests` | VDPU121 handling 1080p60 H.263/MPEG-4, MPEG-1 and MPEG-2 | 
| | Needs writing | | `rkvdec2` using `v4l2-requests` | Nobody is known to be working on this for now. VDPU346 handling 8K60 H.265, H.264, VP9 and AVS | 
| | Needs writing | | `rkdjpeg` using `v4l2-requests` | User:CounterPillow is doing a little work on this. VDPU720 handling JPEG | 
| | In review<sup>[Source](https://patchwork.kernel.org/project/linux-rockchip/list/?series=721724)</sup> | | `hantro` using `v4l2-requests` | Collabora is working on this. VDPU981 handling 4K60 AV1 |
| **Video Encode** | Needs writing | GStreamer only | JPEG on VEPU121 | Driver already exists, only minor changes needed. |
| | Needs writing | ? | H.264 on VEPU580 |  
| | Needs writing | ? | H.265 on VEPU580 |
| **Audio** | Linux Mainline | | `rockchip-i2s-tdm` | As of 6.2<sup>[Source](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=c619bd4268ff9895760dab303b4eb15ed3d0f7e9)</sup> | Linux Mainline | `es8388` CODEC |  |
| **CRU** | Linux Mainline | | `clk-rk3588` | As of 6.2<sup>[Source](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=f1c506d152ff235ad621d3c25d061cb16da67214)</sup> | 
| **MMC** | Linux Mainline | | `sdhci-of-dwcmshc` | As of 5.19<sup>[Source](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=bbbd8872825310b14bc6e04250d2cb5edcd55edb)</sup> | 
| **pinctrl** | Linux Mainline | | `pinctrl-rockchip` | As of 5.19<sup>[Source](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=fdc33eba11c5919199f3d13dc53571cc7bf19d7d)</sup> | 
| **GPIO** | Linux Mainline | | `rockchip-gpio` | As of 6.1<sup>[Source](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=cc165ba48aaf7d792e99d0c7e4b12e9625bc73e3)</sup> | 
| **I<sup>2</sup>C** | Linux Mainline | | `rk3x-i2c` | Should be the same as RK3399, just needs devicetree work |
| **SPI** | Linux Mainline | | `rockchip-spi` | Should be the same as previous SoCs, just needs devicetree work | 
| **PMU** | In review<sup>[Source](https://patchwork.kernel.org/project/linux-rockchip/list/?series=687286)</sup> | | `rk806` | Talks over SPI | 
| **Regulators** | Needs porting| | `rk860` | Talks over I<sup>2</sup>C | 
| **GMAC** | Linux Mainline | | `dwmac-rk` | As of 6.1<sup>[Source](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=2f2b60a0ec2826e5a2b2a1ddf68994a868dccbc1)</sup> |
| **Power Domains** | Linux Mainline | | `rockchip-pm-domain` | As of 6.1<sup>[Source](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=6541b424ce1dda616d3946e839f015c984df7a99)</sup> |
| **CAN** | Needs porting | | `rockchip_canfd` | Not broken out on the QuartzPro64, so we probably won’t be the ones porting it | 
| **SPDIF TX** | May need porting | | `rockchip-spdif` | Genuinely just needs the compatible string added, I think, otherwise we’re all good. Not broken out on QuartzPro64 dev board | 
| **SPDIF RX** | Needs porting | | `rockchip-spdifrx` | Not broken out on QuartzPro64 dev board | 
| **PCIe** | May need porting | | `rockchip-dw-pcie` | Downstream driver and upstream are quite different, look into how much work actually needs doing. Seems to be the same controller as rk3568 so maybe none? | 
| **NPU** | Needs porting/writing | ? | `rockchip-rknpu` | |
| **USB 2.0** | In review<sup>[Source](https://patchwork.kernel.org/project/linux-rockchip/list/?series=749871)</sup> | | `phy-rockchip-inno-usb2` | Might have more factors than just the PHY |
| **USB 3.0** | ? | | `?` | |
| **SATA** | Linux Mainline | | `ahci-dwc` | Just needs the compatible added to the bindings, done [here](https://patchwork.kernel.org/project/linux-rockchip/list/?series=749876) | Thermal | In review<sup>[Source](https://patchwork.kernel.org/project/linux-rockchip/list/?series=687619)</sup> |
| **Thermal** | In review<sup>[Source](https://patchwork.kernel.org/project/linux-rockchip/list/?series=687619)</sup> | | `rockchip-thermal` |  |
| **Wifi & Bluetooth** | ? | | `?` | |
| **HWRNG** | Needs porting | | `rockchip-rng` | The code & DT work is easy to port & working |
| **RTC** | Linux Mainline | | `hym8563` | Should only need DT work (see [here](https://patchwork.kernel.org/project/linux-rockchip/list/?series=736799) for an example) | 
| **OTP** | In review<sup>[Source](https://patchwork.kernel.org/project/linux-rockchip/list/?series=744118)</sup> | | `rockchip-otp` | | 
| **SARADC** | In review<sup>[Source](https://patchwork.kernel.org/project/linux-rockchip/list/?series=748188)</sup> | | `rockchip_saradc` | |
