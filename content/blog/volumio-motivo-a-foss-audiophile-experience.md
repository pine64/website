---
title: "Volumio Motivo: a FOSS Audiophile Experience"
date: "2019-06-10"
categories: 
  - "entertainment"
  - "sopine"
tags: 
  - "audioplayer"
  - "motivo"
  - "volumio"
cover: 
  image: "Volumio-Motivo-Front-web.png"
images:
  - "/blog/images/Volumio-Motivo-Front-web.png"
---

![Volumio-Motivo-Front-web](/blog/images/Volumio-Motivo-Front-web.png "Volumio-Motivo-Front-web")

The higher end alternative to the PRIMO, the MOTIVO, will catch your eye and ear. It is powered by the FOSS audiophile Linux distribution - **[Volumio](https://volumio.org/)** \- that is aviable for many Single Board computers, including the PINE A64-LTS and the ROCK64.

From our point of view, the technology inside the MOTIVO is what makes it stand out, although, we can't argue with its great looks. Powered by a SOPine module, the Volumio Motivo is a true fusion of form and fucntion, and a brainchild of a Joint Venture between world-class industrial design firm Design Narratives and R&D and audio design Company Yottamusic.

Yottamusic has been working for 10 years on their the core-technology which is now in the Motivo: METACLOCK.

This Technology has 3 core principles:

- Do not use a generic SOC (which handles communication with the DAC)
- Use an interface that, other than USB and I2S allows faster data transfer
- Use a dedicated FPGA to handle communication with the DAC. Therefore emancipating the Audio Quality outcome from the OSCPU combination.

It works this way:

- The audio stream is sent from the A64 SOC via a high-speed BUS (SDIO) to a dedicated FPGA
- Here the stream is reclocked via a double buffer and stored on a high-speed memory
- It’s then sent, at the right moment to the DAC

The results that it brings:

- 104dB THD+N
- 110dB SNR
- Jitter: 200ps Maximum
- Network data correction

This means that with Metaclock technology, Volumio Motivo is able to achieve outstanding sound quality performances without the need of esoteric (and expensive) designs, following Volumio's core principle: the best possible sound quality with an unbeatable priceperformance ratio.

Integrating Metaclock technology is being probably the biggest challenge Volumio Team has faced so far: since this technology has never been done before, in this way, there is no standard to follow nor any HOWTO nor literature. Work is currently being done to implement the very complex software integration to take the most out of this technology, without compromising on usability.

![](/blog/images/SOPINE-A64-Audio-Streamer-Large.jpg)

**Back of the Motivo showcasing the wide IO array**

![](/blog/images/Volumio-Motivo-Large.jpg)

**Motivo front featuring an 8" EPS Touch Panel and control knob**

For those of you craving for technical specifications, here they are:

- 8” EPS touch panel allowing for great viewing angles without glare.
- Mounted digital volume control knob that also dubs as on/off.
- All Winner A64 chip optimized for audio with low noise carrier band.
- Wide bandwidth SDIO bus ideal for media transfer.  
- On board FPGA for noise and jitter elimination.
- On board ESS Sabre 9038Q2M DAC.
- Bluetooth 4.2
- PCM and DSP 1024 compatible.

Audio Outputs:

- RCA
- Balanced XLR
- Optical
- Coaxial
- HDMI I2S
- USB 2.0

Peripherals:

- Gigabit ethernet
- Dual USB 2.0 (input/output)
- HDMI 1.4 video for user interface display
- 9V/3A barrel power jack

**To learn more about Volumio Motivo make sure to** [**subscribe to the Volumio Blog**](https://volumio.org/)![volumio-motivo-high-end](/blog/images/volumio-motivo-high-end.jpg "volumio-motivo-high-end")

**Volumio Motivo was [unveiled at High-End](https://volumio.org/meet-us-in-munich-high-end-2019/) in Munich, Germany last month.**
