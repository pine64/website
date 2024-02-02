---
title: "Setting the Record Straight:  PinePhone Misconceptions"
date: "2020-01-24"
categories: 
  - "pinephone"
tags: 
  - "pinephone"
cover: 
  image: "PinePhone.jpeg"
images:
  - "PinePhone.jpeg"
---

![](/blog/images/PinePhone.jpeg)

I take no pleasure in writing this blog post. In fact, even as I am writing these words I am internally torn on whether this is the right approach to addressing the problem on hand. Whether I’ve chosen the right approach remains to be seen, but regardless, I now feel it’s time to confront misconceptions about the PinePhone. 

#### What’s the misconception?

The misconception concerns the openness of the PinePhone. On numerous occasions I've seen the PinePhone being refereed to as closed-source on one level or another.  I don’t know the origin of this misconception nor do I understand the reason why it has become propagated throughout the internet. What I do know, however, is that it has been repeatedly quoted in online articles covering the PinePhone or other Linux devices for over a year now.

So let's set the record straight: the PinePhone is not ‘full of closed-source firmware’ and, moreover, is one of the most open devices out there. 

#### Here’s what’s open

Let's start with the Allwinner A64 SoC, which is the brains of the PinePhone; it runs mainline Linux, uses [mainline ATF](https://developer.trustedfirmware.org/dashboard/view/6/) and u-boot and there are open source drivers for all main SoC components. This openness extends to the [Lima GPU driver introduced in kernel 5.2](https://cgit.freedesktop.org/drm/drm/commit/?id=a1d2a6339961efc078208dc3b2f006e9e9a8e119).

Linux 5.6 will contain drivers for all major components of the SoC. The parts which still need to be upstreamed to mainline are HDMI audio and msgbox - both drivers are in the works. For more information on mainlining efforts, please refer to the A64 column at [https://linux-sunxi.org/Linux\_mainlining\_effort#Status\_Matrix](https://linux-sunxi.org/Linux_mainlining_effort#Status_Matrix)

It’s worth mentioning that LPDDR3 initialization is done by u-boot SPL, which is also open source. There are no blobs in there either.

Needless to say, the PinePhone itself is an open platform for any OS to run on. The grand majority of the OSes developed for the PinePhone are, in and of themselves, completely open too.

#### So, where are the blobs?

The non-FOSS parts of the phone are as follows: WiFi and Bluetooth firmware must be uploaded to the Realtek RTL8723cs on initialization, an optional auto-focus firmware (currently not used in any PinePhone OSes) can be uploaded to the rear OmniVision OV5640 camera, and the Quectel EG25-G LTE modem runs its own closed-source OS.

The WiFi module communicates with the CPU over SDIO and BT is over UART - neither of these connections provide direct access to CPU memory.

The LTE modem on the PinePhone is a ‘black box’, and runs its own Linux system internally. This includes all the proprietary modules (blobs) needed to run the actual cellular radios. However, this system is almost entirely isolated from the main system running on the A64 SoC. The only data contacts between A64 and modem are USB connection for data and I2S connection for audio. All data going in or out of the modem must go over these connections. 

There is no RAM or flash storage shared between the systems. In short, unless you explicitly send data to the modem, it is never in contact with the blobs running inside it. The modem cannot send any data to the phone unless phone is willing to receive it (that’s the basics of USB).

#### Closing statement

I do not think that this misconception arose online as a result of someone's ill intention or a conspiracy. I really don’t. I do, however, feel that if I were to leave this unanswered for much longer then this misconception would be further propagated.
