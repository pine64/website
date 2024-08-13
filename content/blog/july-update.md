---
title: "July update: community developers portal"
date: "2021-07-15"
authors: ["Lukasz Erecinski"]
categories:
  - "community"
  - "news"
  - "pinedio"
  - "pinephone"
  - "quartz64"
tags: 
  - "community"
  - "developers"
  - "pine64"
  - "pinedio"
  - "pinephone"
  - "quartz64"
cover: 
  image: "JulyHeader.jpg"
images:
  - "/blog/images/JulyHeader.jpg"
---

![](/blog/images/JulyHeader.jpg)

This month’s big news isn't a piece of hardware or software but rather an upcoming platform aimed at community developers called the PINE64 DevZone. But fret not, I also have a number of hardware news to report - including a new LoRa device called PineDio Stack - as well as an overview of the software progress on our flagship devices.   

Let’s get to it.  

You can watch the synopsis of this month’s community update on YouTube (embedded below) as well as on [Odysee](https://odysee.com/@PINE64:a) and [PeerTube](https://tilvids.com/accounts/pine64tilvids/video-channels). To stay up-to-date with PINE64 news make sure to subscribe to this blog (subscription widget at the bottom of the webpage), follow [PINE64 Telegram News channel,](https://t.me/PINE64_News) the [announcements channel in Discord](https://discord.gg/pine64) as well as our [Twitter](https://twitter.com/thepine64) and [Mastodon](https://fosstodon.org/@PINE64).

I’d like to thank [JF](https://twitter.com/codingfield), [Alex](https://twitter.com/AlexRob12252696) (clover), [Danct12](https://twitter.com/realdanct12), [Peter](https://twitter.com/pgwipeout) (pgwipeout), [Martijn Braam](https://twitter.com/braam_martijn), [Brian](https://mastodon.online/web/accounts/61817) (33YN2) and [PizzaLovingNerd](https://www.youtube.com/channel/UCmGcm7dhEjS9CIOsOOv8y6w) for their contributions to this community update.

**N.B.** Comments on the blog post need to be in English and follow our [Community Rules and Code of Conduct](https://forum.pine64.org/showthread.php?tid=13209).

{{< youtube id="SkuxIZ7H8N4" >}}

**Community update video summary by [PizzaLovingNerd](https://www.youtube.com/channel/UCmGcm7dhEjS9CIOsOOv8y6w)**

**TL;DR**

- Housekeeping: we’re creating a community developers portal called the PINE64 DevZone; [sign-ups are open](https://devzone.pine64.org)
- PineTime: sealed PineTime units with InfiniTime 1.2 & newest bootloader are now available in the PineStore for $26.99
- PineTime: InfniTime 1.2 brings new apps, improvements to RAM and ROM memory and various bug fixes; upcoming release will feature a new watchface
- PineTime: WaspOS gets a sports app, a watch face chooser and a visual overhaul
- PineTime: New firmware announced - Malila is based on RIOT and in early stages of development
- PinePhone Hardware: final keyboard pre-production units now being made, production to start immediately after final review if no issues are found
- PinePhone Hardware: wireless charging and fingerprint reader back cases being tested and reviewed in coming days; LoRa back case awaiting I2C driver 
- PinePhone Software: PinePhone now playing back accelerated video; app called Clapper made available
- PinePhone Software: Arch Linux with Plasma Mobile now available to download; a SXMO build coming later this month
- PinePhone Software: postmarketOS gets an update with quick suspend/resume support and number of other improvements in both stable and edge
- Quartz64: software progressing at a very rapid pace and upstreaming of patches is underway
- Quartz64: big missing functionality features include display output (worked on), audio out (worked on) and e-ink; latter will likely prove a challenge
- Quartz64: we now have buildroot, Debian and a plug-and-play Manjaro OS images available for the model-A 
- PineDio Stack: a LoRa and BL602/604 development platform; allows you to plug in peripherals, has a small LCD screen and can be powered from batteries
- PineDio Stack: can be used with solar power and fitted with batteries for a variety of implementations; we will likely offer voltaic panels for to fit the Stack PCB into

### Housekeeping: PINE64 development portal

This month’s housekeeping focuses on one sole topic - the PINE64 developers portal called PINE64 DevZone. In recent months the community of active developers has grown significantly; I suspect that the number of active community developers has more than quadrupled since 2019, which is obviously great. This growth has, however, resulted in a side-effect of sorts - we (I in particular) have lost track of who is working on what. Moreover, with development taking place across various communication protocols and platforms, newcomers to the community  willing to contribute code are forced to spend a long time looking through chat logs, finding relevant repositories, gathering resources and figuring out who-is-who in the community. We wish to help streamline this process, improve cooperation and build a system to disseminate development resources in an efficient way. 

Registration for the DevZone is [now open](https://devzone.pine64.org) and anyone with an interest and experience in software development is welcome to apply. The portal is primarily aimed at developers unassociated with our partner projects (partner project developers will be granted a developer’s status automatically) and industry partners who want to contribute code or share their insights, but we’ll happily review any submitted applications. 

![](/blog/images/devzone-1024x481.jpg)

**DevZone sign-ups are now live**

Let’s talk specifics. So then, what do we get out of it? We get an overview of active and prospectus community developers, their interests, experience and contribution history (to both PINE64 and other projects). This will help us better understand our community development pool and the available talent. We frequently find ourselves with a handful of early prototype devices and spend countless hours figuring out who would be the right fit for them. Development units sometimes end up in the hands of people who do not have the right skillset, are already working on a different device or are otherwise occupied. At the same time we overlook developers who would be an ideal fit. We have a backlog of ideas stalled due to the component shortages, and would like to get the show back on the road as soon as the world reverts to normal. We believe the DevZone will be principal in getting the wheels spinning once production of new devices is viable once again.    

And what do you get out of it? If you’re granted developer’s status you’ll receive access to a knowledge and information sharing platform with early prototype data, pre-release schematics, development resources and an overview of ongoing development. Information disseminated on the platform will include things we don’t usually share publicly (not because they are secret per se, but rather because prototype details can create disinformation or give false impressions of the end-product). The system will give an overview of who's working on what, provide a direct line to other developers and a guarantee that we see your feedback. You may also be invited to work closer with us on upcoming devices by reviewing prototypes; we’ll be choosing from this pool only. Lastly, we’ll label you as a developer on our platforms (where applicable), thereby making it easy for end-users and other developers to identify you. In time the DevZone will grow to encompass additional functionality, be it additional cooperation tools, an internal chat or something completely different. We’ll settle on what further features are needed together. 

As I already mentioned, the portal is currently under construction and we presently don’t have a timeframe for launch. But if you are interested in participating in development on PINE64 hardware then I encourage you to register today - we’ll get back to you once the system is live.

### PineTime \[by JF & 33Y2N\]

Let me start with really good news for those of you waiting (im)patiently to get their hands on a PineTime: I've just learned that the production of the new batch of PineTime is going well and, if everything goes according to plan, then single sealed [PineTime units should be available](https://pine64.com/product/pinetime-smartwatch-sealed/) when this post goes live! These PineTimes are flashed with the latest versions of the bootloader of and InfiniTime, so that you'll be able to get the most out of your watch the moment you receive it.

As we [announced last month](https://www.pine64.org/2021/06/15/june-update-new-hardware-and-more-on-the-way/), the factory was waiting for this release to start the production of the new batch of PineTimes. As a reminder: the ongoing component shortage forced PINE64 to use a slightly different accelerometer for this new batch, since the original one was not available anymore, and InfiniTime needed to add support for this new chip to ensure features like step counting and wake on wrist rotation would work as expected.

The [1.2.0 version of the firmware](https://github.com/JF002/InfiniTime/releases/tag/1.2.0) includes a new metronome application, improves the stopwatch app and brings about many improvements and bug fixes. We've also worked on memory optimizations which freed up quite a lot of space in both RAM and ROM memories. This will allow us to ensure that we'll be able to add more features to the firmware in the future. As always, InfiniTime developers didn't stop at this, and we are already working on the next release that will bring, among other things, a new stylish watchface!

![](/blog/images/infinitime1_2-metronome-1024x1024.jpg) ![](/blog/images/infinitime1_2-stopwatch-1024x1024.jpg)

**Left: metronome  // Right: stopwatch**

In other PineTime news, [WaspOS](https://github.com/daniel-thompson/wasp-os) has seen a few improvements merged recently in the form of an early sports app which currently lacks polish cosmetically, a watch face chooser which shows a full screen preview of various watch faces to let the user decide which one to use, new icons, and bug fixes. Further, of note recently a pull request has been created that aims to add an advanced alarm application (much more featureful than the existing alarm app).

This month, I'm really happy to highlight a newcomer to the world of PineTime firmwares: [Malila](https://github.com/arteeh/malila) by [Maarten de Jong (Arteeh)](https://github.com/arteeh). Maarten have previously been working on UI designs, a flasher app and a GTK companion app for WaspOS. His latest project, Malila, is no less than a fully-featured firmware for the PineTime based on [RIOT OS](https://www.riot-os.org/). Here's the announcement he made earlier in the chat rooms:

_Hi community, I wanted to share something I'm working on: [https://github.com/arteeh/malila](https://github.com/arteeh/malila)_

_It's a simple firmware for the Pinetime, based on RIOT. It doesn't have any functionality, and it doesn't support the bootloader yet, so as an end user don't expect anything from it just yet :)_

_I started working on this to experiment with ways to fight the 8hz refresh rate bottleneck on the display. What I have right now is the following: A grayscale (2 bits per pixel) graphics system with two buffers, which we can use to only send a color over SPI when the pixel we're writing to isn't already that color._

_It's grayscale because a full 16 bit (65536 colors) buffer would be 115kb of RAM, which won't fit. 8 bit (256 colors) using 57kb might theoretically fit, but would not leave room for any other software._

_Anyway, I just started doing some initial work on getting a font converter (.ttf file to c array) working, and next up I want to write the code that writes letters to the buffer._

_Long shot, but eventually I would like my project to have the following features:_

_\- A nice looking Gnome-style (Cantarell font, Gnome icons and symbols) UI_

_\- Micropython support_

_\- Support for all the hardware (touch, hearbeat, etc.) and a way for Python programs to interact with it_

_\- 6LoWPAN networking over BLE (RIOT seems to support this, and Linux has a kernel module for it)_

_Check out the repo if you want :-)_

The project is still in its early stages, but it looks really ambitious and promising. For now, Maarten is focusing on the display driver and font rendering. Ultimately, Malila should look like the designs Maarten is working on in his [PinetimeOS project](https://github.com/arteeh/pinetime):

![](/blog/images/PineTimeOS-UI.gif)

**Render of Malila PineTime firmware**

Let's wish Maarten best of luck!

### PinePhone: Hardware 

The first topic of the month’s agenda is the PinePhone keyboard, which I know many of you are eagerly awaiting. Those of you who read previous community update blog entries will already know that we created two prototype iterations and have been ironing out existing issues these past 3 months. We’re now at a stage where we incorporated most, if not all, developer feedback concerning the keyboard’s electronics, chassis (including fit and finish refinements) and fine-tuned the membrane responsible for the feel of keystrokes. There is now also a fully [open firmware for the keyboard thanks to Megi](https://xnux.eu/log/#041), which I am happy to report will ship with the keyboard by default. As you can probably tell from the above, we’re very close to being production-ready. However, since we recognize the importance of this peripheral, we therefore also want to get it right from the get-go, and have decided to create a final set of pre-production review units (they ought to ship out in less than 2 weeks time).This will allow for any last-minute tweaks ot the end product if need be. Granted everything goes according to plan and no issues are found with these final pre-production units, we will start production immediately after receiving a green light from developers. 

![](/blog/images/Keyboard-new-membrane-1024x722.jpg) https://youtu.be/Gnb8K80h9aU

**Left: final (hopefully) revision of the keyboard membrane // Right: keyboard testing at factory**

In other hardware news, final pre-production back cases for the PinePhone have just arrived from the factory. The fingerprint reader and wireless charging modules will be fitted into the cases and undergo functionality and physical endurance testing in the next few days. If it turns out that the cases fit well, function as expected and we can source the necessary components to produce them in scale, then you can expect production to commence shortly. The LoRa back case will have to wait a little longer as we still need a developer to bring up the LoRa chip’s functionality over the I2C protocol. If you’re someone who’s keen on having a go at it then make sure to reach out to us in the comments section. Given current progress, we may see the back cases introduced at the same time as the PinePhone keyboard. I’ll write a dedicated post about the back cases once production starts - stay tuned.

![](/blog/images/LoRa-back-case-PCB-1024x489.jpg) https://youtu.be/qEXv\_SrD0TA

**Left: LoRa back case electronics // Right: PinePhone unlocked using fingerprint reader**

### PinePhone: Software \[by 33Y2N, Danct12 & Martijn Braam\]

The big software news of this month is that the PinePhone is now capable of accelerated video playback. The device has, at least technically, long had the possibility of doing hardware accelerated video playback using the mainline Cedrus media driver ([demonstrated last year](https://xnux.eu/log/#016) by Megi) which renders video using the Allwinner A64’s onboard Video Processing Unit (not to be confused with the GPU). Shown once again this year by Brian Daniels, not only is it possible to get smooth hardware accelerated video playback using [gstreamer in the command line](https://briandaniels.me/2021/06/27/hardware-accelerated-video-playback-on-the-pinephone.html), but it is also possible to write applications that can utilize gstreamer and it’s hardware decoding, such as the case with the new [Clapper video player](https://briandaniels.me/2021/07/06/hardware-accelerated-video-playback-on-the-pinephone-with-clapper.html). The PinePhone can output 1080p at 30fps with ease using acceleration, exceeding the native resolution; this is, however, something that may prove useful for those seeking to dock their PinePhone for convergence. In order to get video decoding working, at least for now, you must build GStreamer manually; however once this work comes to stable releases of GStreamer you can expect distributions to start utilizing hardware video decoding out of the box.

https://www.youtube.com/watch?v=BvmRV6IIGGo

**Hardware accelerated video in Clapper - by [Brian Daniels](http://briandaniels.me/)**

In other news, there is now an Arch Linux ARM OS image featuring Plasma Mobile; this is something that many users have been interested in seeing for quite some time. The image features the newest Plasma Mobile UI (5.22) and joins the existing selection of Phosh and barebones installations - it can be downloaded from [here](https://github.com/dreemurrs-embedded/Pine64-Arch/releases)! 

The update schedule for the Plasma Mobile image is based on [Plasma 5's update schedule](https://community.kde.org/Schedules/Plasma_5#Final_version) set out by the KDE team, which means that aside from bug fixes, there won't be any new features added until the next major release is out. Aside from the addition of Plasma Mobile to the Arch roster, [dni](https://github.com/dni) has made a pull request to the repository which adds SXMO as a UI option. We hope to see SXMO up and running soon, and a new OS image featuring this UI will be released by the end of July. Lastly, the community build of Arch Linux Arm has fixed a high priority [security vulnerability](https://github.com/dreemurrs-embedded/Pine64-Arch/issues/186) last month - so make sure to update your installation if you have not done so recently. 

![](/blog/images/IMG_20210714_230643.jpg)

**Arch Linux with Plasma Mobile - by [Danct12](https://twitter.com/RealDanct12)**

Lastly, the postmarketOS build for the PinePhone has seen a number of improvements. The biggest one being the recent v21.06 stable release, which brought updated software for users on the stable branches of postmarketOS with Phosh 0.11 (and Phosh 0.12 in edge). The postmarketOS build also received quick suspend/resume support for the modem for those running the edge branch; this should increase the reliability of calls and mobile data on the phone. If you wish to give postmarketOS a go, the newest OS images can be [downloaded from their website](https://images.postmarketos.org/bpo/v21.06/pine64-pinephone/); you get a choice of three UI options: Phosh, Plasma Mobile and SXMO. 

### Quartz64

With Quartz64 now [available in the Pine Store](https://pine64.com/product-category/quartz64/) and shipping to early adopters, I will focus on the software progress this month. Those of you who wish to learn more about the hardware, please read [last month’s community update](https://www.pine64.org/2021/06/15/june-update-new-hardware-and-more-on-the-way/), in which I outlined, in considerable detail, the current and future Quartz-line offerings. Earlier this week I spoke with [pgwipeout](https://twitter.com/pgwipeout) who laid the foundations for mainline Linux on the RK3566 SoC used in Quartz64, and he briefed me on the progress made. The official device tree has now landed in mainline Linux alongside a number of nodes. Presently a method for handling the RK3566 and RK3568 split is being devised - once a solution is found, developers will be submitting a number of RK3566-specific patches upstream. Among them will be the basic device tree for the Quartz64 model-A as well as the supported, but missing in mainline, nodes enabling various additional functionality. One key bit presently missing, but in development, is the VOP-V2 display driver that will eventually allow for display output. 

![](/blog/images/Q64-received.png)

**One of the first Quartz64 model-A boards in the wild - also, we will hold you to your word [Chris](https://twitter.com/obbardc) ;)**

Other key missing components are: the audio driver, e-ink and battery charging support. The audio and battery charging functionality will take time but are likely to be incorporated into the Linux kernel in a timely fashion. E-ink display functionality, on the other hand, is likely to prove a major challenge. From an end-user’s perspective, the display and audio drivers are obviously the most important in terms of basic usability, and there is a good indication that both will be the first missing pieces to be added. Rockchip is also actively working on preparing u-boot support for the RK3566 and has pushed downstream patches to RAM init as well as added RK3566 support in mkimage program. A complete overview of the development status can be found on [Quartz64 Wiki page](https://wiki.pine64.org/wiki/Quartz64_Development#Upstreaming_Status). Given how young the SoC is, and the short amount of time the Quartz64 model-A has been available, I think it is fair to say that development is progressing at a blistering speed. 

![](/blog/images/manjaroonQ64.png)

**Manjaro running on the Quartz64 model-A - by [Spikerguy](https://twitter.com/fkardame)**

For those of you who wish to contribute to development at this early stage, there are now multiple operating systems to toy around with. Pgwipeout made a [buildroot recovery image and a Debian installer](https://gitlab.com/pgwipeout/quartz64_ci/-/jobs/1378934651/artifacts/browse/artifacts/), both of which pack all currently available functionality and the newest commits. Since earlier this month the Quartz64 is also able to boot [Manjaro Linux](https://github.com/manjaro-arm/quartz64-bsp-images/releases), which features the same kernel and patches as buildroot and Debian, and therefore also all currently available functionality. The Manjaro Linux OS image is plug-and-play, which means that you flash it to a SD card (or eMMC) and it’ll boot up just as you’d expect. Given current software maturity of the Quartz64, I suspect it may take a little longer to see other partner projects port their operating systems to the platform, but once baseline functionality is fleshed out I am sure we'll see wide-range support for the platform. 

### PineDio

We are happy to announce that another device will be joining the PineDio family on launch day: the PineDio Stack. The Stack is effectively an all-in-one development platform, featuring the Buffalo BL604 RISC-V SoC (which is effectively identical to the BL602 that is currently undergoing open-sourcing as part of the [nutcracker challenge](https://www.pine64.org/2020/10/28/nutcracker-challenge-blob-free-wifi-ble/), but with more available GPIO) and a SX1262 LoRa module by our friends at RAKWireless. The Stack will allow you to connect peripherals via exposed GPIO, will connect to a small LCD panel, and the entire PCB can be housed inside a small sleek plastic case. It will also be possible to operate the PineDio Stack solely from battery - it shares the PineTime’s battery charging circuit.

![](/blog/images/stackPCB-1024x576.jpg)

**PineDio Stack assembled PCBs**

While we envisioned the PineDio Stack as a development platform for the BL602/4 and SX1262, it can also be used for a variety of other purposes. It will obviously be up to developers’ and end-users’ imagination what the device is best suited for, but we have already started experimenting with a number of different applications that use the Stack as a LoRa end-node and use of voltaic solar panels in conjunction with batteries. We know that wireless solar-powered operation for LoRa end-nodes is a highly desirable feature and therefore also exploring an in-house solution for such a setup. I am including some of our tests below - please consider them very early tests; we will likely have a default voltaic solar panel available in the Pine Store for you to pick up once the Stack enters production. Developer units will be available late this month.

{{< youtube id="FIyzurH9z-g" >}}

![](/blog/images/stack-inside-solar-1-1024x576.jpg)

**Left: Stack powered by solar energy // Right: Stack inside voltaic panel case fitted with a 18650 battery**

In other LoRa news: the PineDio gateway is still awaiting certification as we’re missing a part, which we’re told will be delivered in 5 weeks time. As soon as the part (a crypto chip) is delivered we’ll move to certify the gateway and proceed with its production. As for the PinePhone LoRa back case - the electronics and the back case itself are completed and, at least in theory, ready to go. That said, we’re missing the I2C driver that would make the LoRa back case work with the PinePhone. We are currently talking to a handful of prospectus developers who could be up to the challenge to bring up the required driver - if you’re someone interested in this, make sure to let us know in the comments section below.   

That is it for this month. I hope you’re somewhere nice and warm and enjoying the weather!
