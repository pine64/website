---
title: "Specifications"
draft: false
menu:
  docs:
    title:
    parent: "PineTab2/Further_information"
    identifier: "PineTab2/Further_information/Specifications"
    weight: 
---

* **SoC:** Rockchip RK3566
* **CPU:** 4x ARM Cortex-A55 @ 1.8 GHz
  * 32KB L1 Instruction Cache and 32KB L1 Data Cache per core
  * 512KB unified system L3 cache
  * ARMv8 Cryptography Extensions
* **GPU:** Mali-G52 MP2 @ 800 MHz
  * Supported by the open source 'Panfrost' driver in Linux and Mesa
  * Supports OpenGL 3.1 and OpenGL ES 3.1 with many newer extensions
* **NPU:** 0.8 TOPS Neural Processing Unit
* **RAM:** 4GB or 8GB LPDDR4
* **Storage:**
  * 64GB or 128GB internal eMMC ([https://www.szyuda88.com/product-77313-276594.html SiliconGo SGM8 100C-S36BCG]; eMMC 5.1, up o 400MB/s)
  * 1x MicroSD slot
* **Display:** 10.1" IPS LCD Resolution 1280x800
* **Cameras:**
  * Front: 2Mpx, chipset: Galaxycore GC02M2
  * Rear: 5Mpx, chipset: Omnivision OV5648
* **Battery:** 6000 mAh (22.2Wh)
* **Buttons:** Power, volume up, volume down
* **Network:**
  * Wi-Fi: BES2600
    * Driver under development, use a USB wifi dongle for now
  * Bluetooth: BES2600
* **I/O:**
  * 1x USB-C 3.0 (top, host mode only; power output up to 680mA)
  * 1x USB-C 2.0 + PD (bottom, device mode by default; power input)
  * 1x MicroHDMI
  * 1x 4 pole 3.5mm audio jack (microphone right) and headphone detection
  * 2x speakers + microphone (microphone left)
  * 1x 5 pin (USB 2.0; &lt;=680mA) Pogo connector for keyboard
  * (PCIe on PCB as a flat flex ribbon connector, no room for M.2 NVMe drives in case)
* **Sensors:**
  * Accelerometer: Silan SC7A20
  * Ambient Light & Proximity Sensor
* **Multimedia:**
  * rkdjpeg: 1080p120 JPEG decode
  * hantro: JPEG/VP8/H.264 encode, 1080p MPEG-2/H.263/VP8/H.264 AVC decode
  * rkvdec2: 4K H.264 AVC Main10 L5.1/H.265 HEVC Main10 L5.1/VP9 Profile 0 and 2 L5.1 decode
  * rkvenc2: 4K H.264 AVC/H.265 HEVC encode
* **Build:** Metal and Plastic
* **Dimensions:** 242x161x9mm
* **Weight:** 538g
* **Misc:**
  * Protective cover with keyboard
