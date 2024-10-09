---
title: "Features"
draft: false
menu:
  docs:
    title:
    parent: "ROCKPro64/Board"
    identifier: "ROCKPro64/Board/Features"
    weight: 
---

This section outlines the most important characteristics of the board and its components.

## SoC and Memory Specification

The ROCKPro64 is based on the Rockchip RK3399.

### CPU Architecture

* [Dual-core Cortex-A72 up to 2.0GHz CPU](https://developer.arm.com/products/processors/cortex-a/cortex-a72)
* [Quad-core Cortex-A53 up to 1.5GHz CPU](https://developer.arm.com/products/processors/cortex-a/cortex-a53)
* big.LITTLE architecture: Dual Cortex-A72 + Quad Cortex-A53, 64-bit CPU
* Cortex-A72:
  * 1-4x Symmetrical Multiprocessing (SMP) within a single processor cluster, and multiple coherent SMP processor clusters through AMBA 5 CHI or AMBA 4 ACE technology
  * AArch64 for 64-bit support and new architectural features
  * L1 cache 48KB Icache and 32KB Dcache for each A72
  * L2 cache 1024KB for big cluster
  * DSP & SIMD extensions
  * VFPv4 floating point
  * Hardware virtualization support
* Cortex-A53:
  * L1 cache 32KB Icache and 32KB Dcache for each A53
  * L2 cache 512KB for little cluster
* Full implementation of the ARM architecture v8-A instruction set
* ARM Neon Advanced SIMD (single instruction, multiple data) support for accelerated media and signal processing computation
* ARMv8 Cryptography Extensions
* In-order pipeline with symmetric dual-issue of most instructions
* Include VFP v3 hardware to support single and double-precision operations
* TrustZone technology support
* Full CoreSight debug solution
* One isolated voltage domain to support DVFS

### GPU Architecture

* [ARM Mali-T860MP4 Quad-core GPU](https://developer.arm.com/products/graphics-and-multimedia/mali-gpus/mali-t860-and-mali-t880-gpus)
* The highest performance GPUs built on Arm Mali’s famous Midgard architecture, the Mali-T860 GPU is designed for complex graphics use cases and provides stunning visuals for UHD content.
* Frequency: 650MHz
* Throughput: 1300Mtri/s, 10.4Gpix/s
* OpenGL® ES 1.1, 1.2, 2.0, 3.1, 3.2, Vulkan 1.0*, OpenCL™ 1.1, 1.2, DirectX® 11 FL11_1, RenderScript™.

### System Memory

* LPDDR4 RAM Memory Variants: Dual Channels 2GB and 4GB.
* Storage Memory: 128Mb built-in SPI Flash memory (as at August 2018 only support for USB boot).

## Display

* Dual VOP: one supports resolutions up to 4096x2160 and [AFBC](https://www.arm.com/why-arm/technologies/graphics-technologies/arm-frame-buffer-compression); the other supports resolutions up to 2560x1600
* Dual channel MIPI-DSI (4 lanes per channel)
* eDP 1.3 (4 lanes with 10.8Gbps) to support displays, with PSR
* Digital Video port up to 4Kp60
* DisplayPort 1.2 (4 lanes, up to 4K 60Hz)
* Supports Rec.2020 and conversion to Rec.709

## Video

* Digital Video output up to 4K@60Hz
* 4K HDR @ 30fps
* H.264/AVC Base/Main/High/High10 profile @ level 5.1; up to 4Kx2K @ 60fps
* H.265/HEVC Main/Main10 profile @ level 5.1 High-tier; up to 4Kx2K @ 60fps
* VP9, up to 4Kx2K @ 60fps
* MPEG-1, ISO/IEC 11172-2, up to 1080P @ 60fps
* MPEG-2, ISO/IEC 13818-2, SP@ML, MP@HL, up to 1080P @ 60fps
* MPEG-4, ISO/IEC 14496-2, SP@L0-3, ASP@L0-5, up to 1080P @ 60fps
* VC-1, SP@ML, MP@HL, AP@L0-3, up to 1080P @ 60fps
* MVC is supported based on H.264 or H.265, up to 1080P @ 60fps

## Audio

* 3.5mm Phone Jack
* 3-pin S/PDIF header
* Audio via Digital Video port

## Camera

* Dual MIPI CSI, dual ISP, maximum input resolution of 13M pixels

## Network

* 10/100/1000Mbps Ethernet - Capable of pushing 941 MBit/s in iperf3
* Wi-Fi 802.11 ac/a/b/g/n with Bluetooth 4.01 (old version with 2x2) / Bluetooth 5 (new version with 1x1) (optional)

## Storage

* microSD - bootable, supports SDHC and SDXC
* eMMC - bootable (optional eMMC module)
* 1x USB 3.0 host port
* 1x USB Type-C OTG port with alternate mode DP output  
* 2x USB 2.0 dedicated host port

## Expansion Ports

* 2x20 pins "Pi2" GPIO header
* PCI Express 2.1 x4 (four full-duplex lanes) open-ended port, [limited](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=712fa1777207) to the Gen1 speed

## Working Features

| Feature/Option | Android | Android Version | Linux | Linux Version | Test/Verify Steps | Notes | Product Link |
| --- | --- | --- | --- | --- | --- | --- | --- |
| PINE64 LCD Touchscreen (Screen/Touch) | Yes/Yes |  | No/No |  |  | Maybe [this](https://github.com/avafinger/pine64-touchscreen) will help get this working? | [7-inch LCD Touch Screen Panel](https://pine64.com/?product=7-lcd-touch-screen-panel) |
| Wireless ROCKPro64 2×2 MIMO Dual Band WiFi 802.11AC / Bluetooth 4.2 Module (old) ROCKPro64 1x1 Dual Band WiFi 802.11AC / Bluetooth 5.0 Module (new) | Yes/Yes |  | No/Yes* |  | For the "new" ROCKPro64 WIFI module: Verified with Manjaro ARM (kernel 6.2.5). A config file ("firmware file") is needed at `/lib/firmware/brcm/brcmfmac43455-sdio.txt`. | In 0.7.9 Ayufan linux releases this is deliberately disabled for stability reasons. On Manjaro ARM (kernel 6.2.5), WIFI seems to be stable with the firmware file. On a 5GHz network (802.11AC), it is possible to get about 120Mbps using the "new" ROCKPro64 WIFI module. | [ROCKPro64 1x1 Dual Band WiFi 802.11AC / Bluetooth 5.0 Module](https://pine64.com/product/rockpro64-1x1-dual-band-wifi-802-11ac-bluetooth-5-0-module/) |
| USB OTG |  |  |  |  | Configure ip on usb0: ifconfig usb0 169.169.222.222 and run iperf, you should likely see about 200-300MB/s | [ROCKPro64](/documentation/ROCKPro64/Getting_started/#otg_mode) |  |
| USB Mass Storage USB2/USB3 | Yes/yes |  | Yes/Yes |  |  |  |  |
| Dedicated Fan Power (pwm1) |  |  | Yes |  |  | You might want to use [ATS](https://github.com/tuxd3v/ats). |  |
| GPIO pins (raw or via RPI python scripts) |  |  |  |  |  | Check out [what Frank Mankel has done](https://forum.frank-mankel.org/topic/292/rockpro64-rp64-gpio/2). |  |
| MIPI CSI Camera 1 and 2 |  |  |  |  |  |  |  |
| eDP |  |  |  |  |  |  |  |
| HDMI Audio | Yes | 7.1.2 | Yes | 4.4.132-1083 - 4.4.138-1100 |  | Stopped working in 4.4.154.1105. Ayufan is looking into it. This is working in Manjaro ARM (kernel 6.2.5). Select the `Analog Output (Built-in Audio Stereo)` option in the audio output device selection window (either use `pavucontrol` or the volume button in the KDE desktop). Despite the slightly misleading name, audio does go through the HDMI port. See here for details: https://forum.manjaro.org/t/no-hdmi-audio-on-rockpro64/25595/2. |  |
| 3.5mm Audio/Mic |  |  |  |  |  |  |  |
| USB-C Host |  |  |  |  |  |  |  |
| Display via USB-C | Yes | 7.x and 8.x |  |  |  | eDP via USB-C per tillim. No sound on Android 7.x. Sound does work on Android 8.x |  |
| ROCKPro64 PLAYBOX ENCLOSURE | N/A |  | N/A |  | N/A | Ventilation does not exist, thus requires manual changes to add venting. Case should be modified to account power adapter not being centered in cut holes. Opening the case once close without modifying it first is nearly impossible without special tools. Graphene heatsink is included and does well for Linux but not Android. | [ROCKPro64 Playbox Enclosure](https://pine64.com/?product=rockpro64-playbox-enclosure) |
| ROCKPro64 30mm Tall Profile Heatsink | N/A |  | N/A |  | N/A |  | [ROCKPro64 30&nbsp;mm Tall-Profile Heatsink](https://pine64.com/product/rockpro64-30mm-tall-profile-heatsink/) |
| ROCKPro64 20mm Mid Profile Heatsink | N/A |  | N/A |  | N/A |  | [ROCKPro64 20&nbsp;mm Mid-Profile Heatsink](https://pine64.com/?product=rockpro64-20mm-mid-profile-heatsink) |
| Fan For ROCKPro64 20mm Mid Profile Heatsink | N/A |  | N/A |  | N/A | You might want to use [fanctl](https://github.com/tuxd3v/fanctl) to control the fan while keeping your CPU cool | [Fan For ROCKPro64 20&nbsp;mm Mid-Profile Heatsink](https://pine64.com/?product=fan-for-rockpro64-20mm-mid-profile-heatsink) |
| HDMI output 4K@60Hz |  |  |  |  |  |  |  |
| PCI Express 2.1 |  |  |  |  |  | The PCI Express interface of the RK3399 [is limited](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=712fa1777207) to the Gen1 speed. As a result, some installed PCI Express devices may operate with degraded performance, such as M.2 SSDs that support fewer than four PCI Express lanes, installed using an adapter like [this one](https://pine64.com/product/rockpro64-pci-e-x4-to-m-2-ngff-nvme-ssd-interface-card/). |  |
| Real Time Clock (RTC) battery backup |  |  |  |  |  |  | [RTC Backup Battery Holder CR2032](https://pine64.com/product/rtc-backup-battery-holder-cr-2032/) |
| Boot from USB/PXE |  |  |  |  |  |  |  |

RockChip themselves have tables of supported features at 4.4 and mainline kernel versions [in their wiki here](http://opensource.rock-chips.com/wiki_Status_Matrix).
