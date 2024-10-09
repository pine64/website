---
title: "Notes"
draft: true # Page not published
menu:
  docs:
    title:
    parent: "Pinebook_Pro/Software"
    identifier: "Pinebook_Pro/Software/Notes"
    weight: 
---

## Linux, the kernel, downstream source

Although the current upstream version boots and works, the development of new features and other improvements is still ongoing. The results (including detailed changelogs) are published on [megi’s tree](https://github.com/megous/linux/tags).

## Hardware-accelerated video decoding

Drivers for accelerated video decoding are available in the current kernels but to use the ''v4l2-request'' API with ''FFmpeg'' (and the apps that depend on it) one needs to build [a fork](https://github.com/jernejsk/FFmpeg/branches). With ''mpv'' built against it and the integrated ''yt-dlp'' support watching YouTube and similar sources is possible without stressing the CPU.
