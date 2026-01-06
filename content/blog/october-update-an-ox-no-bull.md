---
title: "October update: An Ox, no bull"
date: "2022-10-15"
authors: ["Lukasz Erecinski"]
categories:
  - "community"
  - "news"
  - "ox64"
  - "pinephone"
  - "pinephone-pro"
  - "quartzpro64"
  - "star64"
tags: 
  - "ox64"
  - "pinephone-pro"
  - "quartzpro64"
  - "star64"
cover:
  image: "/blog/images/october-update-no-bull.jpg"
images:
  - "/blog/images/october-update-no-bull.jpg"
---

![](/blog/images/october-update-no-bull.jpg)

I hope that the good news and all the announcements of this month will make up for the much delayed publication date - which is something I sincerely apologize for. This month we’re announcing the Ox64 - a sub $10 Linux capable single board computer, we are bringing you news that both the Star64 and QuartzPro64 now boot Linux (and run it well too already!) and share all the latest PinePhone Pro development. 

Let's get to it.  

You can watch the synopsis of this month’s community update on YouTube (embedded below) as well as on [Odysee](https://odysee.com/@PINE64:a) and [PeerTube](https://tilvids.com/accounts/pine64tilvids/video-channels). To stay up-to-date with PINE64 news make sure to subscribe to this blog (subscription widget at the bottom of the webpage), follow the [PINE64 Telegram News channel](https://t.me/PINE64_News), the [announcements channel in Discord](https://discord.gg/pine64) as well as our [Twitter](https://twitter.com/thepine64) and [Mastodon](https://fosstodon.org/@PINE64).

I’d like to thank [Alex](https://twitter.com/AlexRob12252696) (clover), [Gamiee](https://twitter.com/gamelaster), [Danct12](https://twitter.com/RealDanct12), [mothenjoyer69](https://github.com/mothenjoyer69) and [PizzaLovingNerd](https://www.youtube.com/channel/UCmGcm7dhEjS9CIOsOOv8y6w) for their contributions to this community update.

N.B. Comments on the blog post need to be in English and follow our [Community Rules and Code of Conduct](https://forum.pine64.org/showthread.php?tid=13209).

{{< youtube id="4H3XmwdjK4g" >}}

**Community update video synopsis**

**TL;DR**

- Housekeeping
    - Apologies for the delayed release of the update; moving forward we’re reverting to 15th of the month for updates
    - PINE64 at KDE Akademy earlier this month - talks about Plasma Mobile and the PinePhone (Pro)
    - We’ve applied for a stall at FOSDEM 2023; we hope to be accepted and to see you there in February 2023
    - Community Q&A next month at 8PM UTC, November 25th    
- Star64
    - Star64 now boots Linux thanks to work by Icenowy
    - Most of Star64’s IO and core functionality already works including the GPU
    - Things to be ironed out include USB 3.0 and onboard WiFi not working, and issues with Gigabit Ethernet dropping packages
    - More developers getting their hands on with the Star64 now 
    - Expect to see wide OS support for Star64 once the Linux base is fledged out fully
    - Star64 will be available in November
- Ox64
    - The Ox64 is a RISC-V Linux-capable SBC for $8
    - Features BL808 from Bouffalo labs RISC-V SoC with 64MB RAM
    - 3 cores: 64-bit RISC-V core, 32-bit RISC-V core and low power RISC-V core
    - Two variants of Ox64 on day one: for RTOS and Linux development - $6 and $8 respectively
    - Expected availability in November
- PinePhone (Pro)
    - Reduced order-to-shipping times for both the PinePhone and PinePhone Pro worldwide; weekly dispatch
    - Starting with kernel 5.19 PinePhone Pro’s cameras will work with Megapixels 
    - Improvements to standby and suspend; bringing the PinePhone Pro closer to user-parity with original PinePhone 
    - Kernel 6.x brings number of improvements; if you’re using a distro on megi’s kernel an update is advisable
    - PinePhone Pro keyboard driver finds its way into kernel 6.1
    - Anbox support is getting dropped; it is suggested to migrate to Waydroid if you use Android application on the PinePhone (Pro)
- QuartzPro64
    - QuartzPro64 boots BSP Linux thanks to work by mothenjoyer69
    - Much of the core functionality is already available and we’re told that the board runs Debian with accelerated GNOME well 
    - QuartzPro64 was able to set the (current) world record result for an RK3588 in Geekbench 5
    - Outstanding issues to be ironed out include: SD card and PCIe functionality as well as WiFi, NPU, HDMI RX); getting SD booting working is priority
    - Debian testing images will be available once SD booting works
    - Mainline kernel boots; BSP and mainline development ongoing in parallel 
    - The board holds much potential also for prospectus future hardware 

## Housekeeping

Let me start by apologizing for missing the September update. This is, to my memory, the first time we’ve missed an update in the past 4 years. The fault is mine; life got in the way. I had a personal situation that I needed to attend to, and with Marek and TL away at KDE Akademy there wasn’t anyone to complete the writing in time. I then faced a backlog of work at the EU store, which effectively meant that we chose to skip writing the September update altogether. Again, I apologise for this situation. This also means that we’re reverting back to the 15th of the month for community updates. While publishing the community update at the end of the month is probably better for the community, the middle of the month works better for my schedule. Moving forward, please expect the updates to be shorter than in the past—unless more members of the community decide to contribute. I therefore urge you, more than ever before, to partake in writing the update. Anyone is welcome to contribute content, be it news concerning documentation, development, new findings, the community, or anything else related to PINE64. It doesn’t matter if you are a notable and long-time community member or a newcomer—we welcome contributions from anyone. All you need to do is ping a mod or admin in one of the chats to discuss your contribution.

Now let's get into housekeeping; as I already mentioned, TL and Marek attended [KDE Akademy](https://akademy.kde.org/2022) earlier this month. This marks the 5th time that [PINE64 co-sponsored](https://akademy.kde.org/2022/sponsors) the Akademy event and someone from our project attended the conference. I unfortunately didn’t get a chance to attend this year, but from what I hear the conference was a success. It was also an opportunity to meet friends, contributors and partners from various projects. I should also mention that there were multiple references and conversations related to PINE64 hardware, and the PinePhone (Pro) in more particular, including a [talk](https://conf.kde.org/event/4/contributions/96/) by [Devin Lin](https://ca.linkedin.com/in/espidev) and [Bhushan Shah](https://twitter.com/bhushannshah?lang=en) on [Plasma Mobile](https://plasma-mobile.org/). Indeed, there were multiple talks which included the subject of Plasma Mobile, one of which you can watch [here](https://tube.kockatoo.org/w/uw5V5fcm993LAvabR81W3i?start=1h34m11s). Needless to say, we’re looking forward to attending Akademy next year. 

![](/blog/images/AkademyPPP-768x1024.jpg)

**PinePhone (Pro) at KDE Akedemy - picture [via twitter](https://twitter.com/rohangarg/status/1576190685690355714/photo/1)**

On the subject of conferences and meetups—we’ve applied for a stall at [FOSDEM 2023](https://fosdem.org/2023/), which will be the first in-person FOSDEM meetup since 2021. FOSDEM has historically been a very important event for us and one which we’ve attended since 2017. This is the event where the PinePhone and other hallmark PINE64 devices were dreamt up and eventually announced. Granted we will be offered a stall at FOSDEM 2023, we’ll make sure to bring all the newest and greatest PINE64 hardware for you to check out. We’ll also bring with us unannounced hardware prototypes and concept devices to check out and offer feedback on. Needless to say, you should also expect some exciting announcements from us during FOSDEM; we intend on keeping with the tradition of announcing hardware at the conference. FOSDEM is also an opportunity for us to meet with the community, so if you’re in Europe and can fly to Brussels to attend the conference on February 4 and 5th, then make sure to come by and say hi. On the off chance that we won’t get a stall, we’ll arrange to host our own meetup somewhere in Brussels during the conference—we’ll make sure to let you know closer to the date.

![](/blog/images/see-though-pinebook-768x1024.jpg)

**Do you recognize this prototype from FOSDEM 2018? ;)**

Lastly, the final quarterly community Q&A of 2023 will be held on November 25th at 8:00PM UTC. In case you missed prior Q&A’s, this is an opportunity for you to ask Marek and I live questions. We sometimes also have community members and developers join in to answer particular questions. The questions are picked directly from the chat and we strive to answer all of them within the time-frame of one hour. You can ask us questions on IRC, Matrix, Telegram and Discord—a full list of Q&A channels can be found here. Just as last time, we’ll be streaming the Q&A session on Youtube, Peertube as well as on the Discord live stage. Following the Q&A we usually take an hour and hang out in the voice chat and continue answering questions and keep the discussion going. So make sure to mark this date in your diary and join us. In case you won’t be able to make it, the Q&A sessions are recorded and uploaded in an unedited state to [YouTube](https://www.youtube.com/c/PINE64inc), [Odysee](https://odysee.com/@PINE64:a) and [PeerTube](https://tilvids.com/accounts/pine64tilvids/video-channels). Hope to see you all there.

## Star64

In August I dedicated a significant portion of the update to the Star64—more specifically to the hardware configuration that will be entering production. Aside from the obvious reasons for describing the hardware and introducing it, the core reason for focusing solely on the hardware stemmed from the fact Linux did not run on it yet. At the time I wrote that ‘_efforts to support the SoC in Linux have already begun’_ and expressed hope to see the development progress quickly due to the high interest in the platform in general and the Star64 in particular. While my belief that we’d soon see support for the board was sincere, admittedly I didn’t expect this much progress to be achieved so quickly—in less than 30 days. Therefore, now I will focus on the board’s software support status. So, if you somehow missed last month’s update and want to learn about Star64’s hardware then I invite you to read the [August update](https://www.pine64.org/2022/08/28/august-update-risc-and-reward/) before reading this month’s section.

I should start by crediting [Icenowy Zheng](https://github.com/Icenowy) for getting Star64 up and running. Some of you will likely know Icenowy from her participation in the [Sunxi Community](https://linux-sunxi.org/Main_Page) and work on numerous single board computers. Notably she also worked on the original Pine A64 (+) and many of our A64 devices, such as the Pinebook and PinePhone. Earlier this month a photograph taken by Icenowy was sent to me showing the Star64 sporting a handful of peripherals running [AOSC Linux](https://aosc.io/). AOSC is a general-purpose Debian fork, which supports single board computers and embedded devices as well as the x86 platform. As you may have already guessed, Icenowy has been one of the developers behind AOSC. The photo shows a 4GB RAM Star64 board running a full XFCE desktop environment atop kernel 5.15. For those who are wondering, I have confirmed that the GPU works; the PowerVR GPU on this RISC-V SoC is fairly capable and I’m sure will do well accelerating desktops with compositors that can take advantage of OpenGL. Since someone will ask: I haven’t been able to confirm whether VPU works at this time, but the VPU blob should be a part of (and work with) the FOSS driver.

![](/blog/images/Star64-Linux-1024x461.jpg)

**Linux now boots on the Star64**

As far as the IO is concerned, it is my understanding that USB 2.0, PCIe, GPIO, SD card, eMMC and Gigabit Ethernet all already work. Things that do not work or work partly include: the USB 3.0 (development of which is being prioritized) which doesn’t work at all, the onboard WiFi, which appears to not work because of driver issues, and while the Gigabit Ethernet works it currently drops packages. I don’t know the status of MiPi and CSI ports – it may be the case that these simply haven’t been tested yet. I should also note that I am writing this section 10 days before the update goes live, so any or all of the points may have already changed. Ultimately, the goal of listing the board's enabled functionality is privately to illustrate how much development was achieved in just a few short weeks, and only by one (very dedicated and skilled) developer. This Linux build is very important however, since it will be used to test Star64 prototypes, which will be shipped to developers shortly.

![](/blog/images/Star64-Running-461x1024.jpg)

**Star64 in action with various IO being used - picture by Icenowy**

This is only the beginning. With a handful of key developers now receiving the Star64 boards we expect to see the outstanding functionality implemented and issues ironed out; once all functionality is enabled we’ll invite partner project developers and individual contributors to port their OSes to Star64. The idea is to have very good support for the platform upon launch and so that end-users have a choice of more server and desktop oriented OS options. With people such as Kamil Trzcinski ([Ayufan](https://twitter.com/ayufanpl)) and Samuel Holland ([smaeul](https://github.com/smaeul)) receiving hardware soon, I expect to see more exciting Star64 developments in the coming weeks, so stay tuned for more news. Finally, the Star64 will be available for purchase to anyone who wants a unit in November. Pricing is yet to be determined. 

## 0x64

**\[edit\]** _It looks like most of the information regarding the Ox64 has already found its way online. The good news is that the coverage has been very favorable. To this end, this announcement is therefore a confirmation of what has already been written and ‘leaked’ online, with some additional details including pricing and expected availability._  

At the start of the year I hinted at a few things coming in 2022—one of which was that we’ll be taking a plunge into the RISC-V this year. The Star64, and any PINE64 devices that may be built upon the StarFive JH7110 SoC in the future, represent just one strand of our exploration of RISC-V architecture. For some time now, ever since the Pinecil first released, we felt that having an entry-level RISC-V single board computer, which would lower the entry-point to the architecture, would be beneficial to the community. To this end and with no further ado, say hello to Star64’s little brother (well, sort of—in architecture only), the Ox64. 

The Ox64 is a small form-factor single board computer powered by the BL808 RISC-V SoC—a new chipset by [Bouffalo Labs](https://en.bouffalolab.com/). Some of you already know of this vendor, since one of their microcontrollers is used in the Pinecil V2 and PineCone. Surely you also immediately noticed that the board is named Ox64 (side note: Ox … Bouffalo … you get it right?) as opposed to PineOx which is used in the PineCone and based on the older BL602 microcontroller. This is because BL808 is not a usual microcontroller. It features three cores - a high performance 64-bit RISC-V core, a high performance 32-bit RISC-V core and low power RISC-V core. These cores are paired with 64 MiB of PSRAM, a SD card interface and MMU (Memory Management Unit), and make the SoC capable of running Linux as well as bare-metal firmware. We hence treat Ox64 as a Single Board Computer rather than a microcontroller, despite that it can be used as either.

![](/blog/images/Ox64-1024x447.jpg)

**Here it is in all its tiny beauty**

Here are some of Ox64’s key hardware details. The BL808 contains a wide variety of really neat onboard features, such as WiFi 4 and Bluetooth 5.0, Zigbee connectivity and MIPI-CSI/DSI interfaces. It also sports a H.264 encoder, MJPEG encoder, JPEG decoder, an audio subsystem, Ethernet, USB 2.0 OTG and Neural Network unit. The Ox64 PCB with two USB ports, at the far ends of the PCB. The USB-C port features OTG and MIPI CSI for the camera module as well as an audio out/in interface. The secondary USB port is for power only. The WiFi chip antenna is soldered onboard and features a u.FL connector. The castellated header pin holes break out GPIO, SPI, I2C, I2S and UART. In the future, we plan to have adapter boards for Ethernet (using GMII interface), audio (I2C interface) and a camera module (USB).

![](/blog/images/Ox64-slate-1024x688.jpg)

**The first sample units for developers and QA**

Before we wrap this announcement up with information about pricing and availability I want to briefly touch upon software, which is pertinent to the pricing structure of the two SKUs that will be on offer later this year. As things stand, we’re awaiting this RTOS SDK, which should be available sometime next week and will be uploaded to the [Ox64’s docs](/documentation/Ox64/Software/Releases/) (which should already be up by the time you’re reading it). Getting Linux to run on the Ox64 will be a community endeavour, but with good documentation and additional external resources we expect to see initial support for the board surface soon. I should also mention that development boards have already shipped to a select group of developers, some of whom are interested in Linux and others in RTOS. I’ll be bringing you news on the progress in the months to come.   

![](/blog/images/file-1024x797.png)

**Ox64 pin assignment**

Finally, the Ox64 board will be available in two configurations, one with 16Mb flash and no microSD socket, and another variant with 128Mb flash and a microSD socket. The prior configuration that is geared towards RTOS development will sell at $6, while the latter is intended for Linux development and will be available for $8. Both configurations are expected to be available at some point next month. You can find more information [on the docs](/documentation/Ox64/). Lastly, I’d like to remind you that the Wiki is editable by community members and we always welcome contributions, thank you.

## PinePhone (Pro)

Before I get into the phone-related news of the month, I just want to provide you with a short update regarding shipping and availability of the PinePhone and PinePhone Pro. As some of you may have already noticed, the Pine Store has begun shipping both phones on a weekly basis from Hong Kong. This means that the time it takes for your PinePhone (Pro) to arrive at your doorstep has now been drastically reduced. Both devices are in-stock and, with current production-runs being quite substantial, we expect stock to last for the foreseeable future. Since stock is located in Hong Kong, COVID-19 related restrictions in the region are also less likely to affect shipping. As for the availability of both devices in the EU store; the PinePhone remains in stock while more PinePhone Pros are expected to arrive any day now. Across the board we strive to improve the process of ordering and delivering hardware; the weekly world-wide dispatches are just one of the many steps we’re taking to increase logistics efficiency (some of you may remember that in the past you had to wait months to receive your PinePhone). I expect to have yet more logistics news for you the following month, now let’s move onto software news.

And for software news, I think this is something many of you have been waiting for: as things stand, two issues PinePhone Pro users face are battery drain in idle and a lack of camera support. There are obviously also other problems, the importance of which I do not diminish—for example voice call quality, which is something I addressed in the [August update](https://www.pine64.org/2022/08/28/august-update-risc-and-reward/). However, the PinePhone Pro’s short battery life and a lack of photo-taking abilities are two of the things I see mentioned most frequently in online discussion on the device’s daily-drivability. While a long, or at least reasonably long, battery life is fundamentally crucial to a phone’s daily usage, the ability to take photos is merely a feature—but one which we’ve come to expect from modern mobile devices. Regardless, both issues impede a sense of the device’s software completeness, especially when compared against the original PinePhone. This, however, is about to change.

![](/blog/images/Camera-on-PPP-megapixels-1024x575.png)

**Initial PinePhone Pro camera support has now been added to multiple OSes - Picture via Manjaro**

Starting with kernel 5.19 PinePhone Pro’s cameras will work with the [Megapixels application](https://git.sr.ht/~martijnbraam/megapixels), shipped with most available OSes. To be clear, I already reported on the PinePhone Pro taking photos and even streaming video a while back, but an implementation necessary to take pictures in Megapixels (or similar userland application) has only become available now. If you’re running Manjaro on your PinePhone Pro then you can already give this new functionality a spin by switching to the unstable software branch. This may be true for other OSes too but I haven’t had the time to check. In terms of the current functionality, the viewfinder works smoothly and switching between the front and back camera is seamless. However, the images that the cameras produce and viewfinder image still have a long way to go; there currently is no color correction nor any post-processing, causing the images to look muddy and green-tinted. As things stand, at the time of writing, the original PinePhone takes better photographs despite the much inferior sensors (a slight digression—it is crazy to think how much of the image quality depends on the software rather than hardware). But this is a first step in a much longer journey to flesh out this functionality.

{{< youtube id="y8zKux7vxCg" >}}

**Initial camera functionality showcased - video by [Wolf Fur](https://www.youtube.com/channel/UCzepblha09x_3Duz3VHSPWg?feature=emb_ch_name_ex)**

The other big news concerns improvements to the PinePhone Pro’s battery life when it suspends. This, in and of its own, is obviously very important but it has also further going consequences. Recent patches to uboot based on 2022.10rc4 not only allow the PinePhone Pro to remain in suspend for a longer time but also a faster wake up time and reliable recovery on phone calls. In my (admittedly limited) testing the phone woke up reliably on incoming calls even after a prolonged suspend-time. Over a day of testing, I didn’t experience a single dropped call—even when I left the phone suspended overnight (approx. 10 hours). This is a huge development brought to us thanks to work by [dsimic](https://github.com/dragan-simic/) and [megi](https://xnux.eu/) as well as other contributors, and one which I hope will find its way into uboot used by most OSes as well as Tow-Boot. I should also mention that I experienced audio-related problems upon waking up—namely, while the phone rang reliably the phone-call audio was gone. At times, the system audio seems to temporarily also vanish. It is clear that more work will be needed to get these features ship-shape but the ongoing progress shows much promise.

I also want to make it clear that while these steps towards software parity with the original PinePhone are very important, they are just that – steps towards parity, not parity itself. There is still a journey ahead of us before the PinePhone Pro and PinePhone’s functionality is identical or near-identical. At this point I want to acknowledge and help all those who are making this happen—the developers working on u-boot patches, the kernel as well as userspace applications. I am glad to see their work gradually coming together to make the PinePhone Pro the best possible device to experience mobile Linux.

![](/blog/images/PPkeyboard-phoronix-777x1024.png)

**PinePhone Pro keyboard drivers are finding their way into kernel 6.1 [Phoronix reports](https://www.phoronix.com/news/PinePhone-Keyboard-Linux-6.1)**

Since I originally wrote the section in September, four more important PinePhone-related things have transpired, which were pointed out to me by [Danct12](https://twitter.com/realdanct12). For starters, megi has updated his [mainline-based kernel to 6.0](https://github.com/megous/linux/commit/b16232c6156de17e1dfdb63fdaea8e317baa07a7). This is a major Linux release, which brings about a plethora of overall improvements and fixes, as well as additional functionality (more on this in a bit); so if your distro of choice uses megi’s kernel then I strongly suggest you run an update. It should be mentioned that among the many things that kernel 6.0 brings, the next release (kernel 6.1) will incorporate the PinePhone (Pro)’s keyboard driver - [Michael Larabel](https://www.michaellarabel.com/) from [Phoronix writes](https://www.phoronix.com/news/PinePhone-Keyboard-Linux-6.1): “_Queued via the Linux kernel input subsystem's "next" branch is_ [_this commit_](https://git.kernel.org/pub/scm/linux/kernel/git/dtor/input.git/commit/?h=next&id=0f8ef970940803bb5950e7baa27469a89b8c2e21) _introducing the PinePhone keyboard driver. An associated commit also adds the PinePhone keyboard driver for the DeviceTree. This new driver is for supporting the matrix keypad and MCU of the Pine64's PinePhone keyboard case (...)_”. We’ve also seen the community built [modem firmware receive a new release](https://github.com/the-modem-distro/pinephone_modem_sdk/releases/tag/0.7.0). This release brings an update to Yacto 4.0.4, support for GSM-7 / UCS-2 / 8-Bit data coding scheme identification in Cell Broadcast messages and raw relaying as a SMS to the host if the default coding scheme is not used, fixes a problem with emergency broadcast messages in non-latin characters (making it a very important release if you happen to live in countries that don’t use latin characters) and fixes HWIDs compatibility for PinePhone Pro (Tow-boot) and PinePhone (Tow-boot / u-boot).

Lastly, [Danct12](https://twitter.com/realdanct12) told me that _“If you're still using Anbox on DanctNIX's Arch Linux ARM fork, keep in mind that Anbox and the relevant packages will be removed at the beginning of 2023. It's recommended to migrate to Waydroid ASAP.”_ This obviously also applies to all other distributions, most of which, to the best of my knowledge, now offer a simplified way of installing Waydroid in both Phosh and Plasma Mobile user environments. 

## QuartzPro64

The last piece of news I come bearing this month concerns software developments on the QuartzPro64. In case you don’t know, the [QuartzPro64](https://www.pine64.org/2022/03/15/march-update-introducing-the-quartzpro64/) is a development board powered by the powerful RK3588 SOC from Rockchip. We shipped a number of QuartzPro64 boards to developers earlier this year and we’re finally starting to see some really exciting software developments on the platform. Earlier this week I had a chat with [mothenjoyer69](https://github.com/mothenjoyer69), a developer who has been working on QuartzPro64. This section will effectively be an overview of what I’ve learned from our conversation and the details mothenjoyer69 provided me with. For starters, perhaps the most important news is that Debian stable now boots on the QuartzPro64 using the BSP kernel. 

![](/blog/images/QuartzPro64-linux-2-768x1024.jpg)

**QuartzPro64 running Debian - picture via Mothenjoyer69**

Not only does it boot however, a lot of the core board functionality works too. When asked about it, Mothenjoyer69 wrote _“The QP64 was recently shown to boot a BSP kernel, with almost all critical hardware working without issue. GNOME 3.38 boots with full acceleration, and glmark2 ran to completion without issue, and YouTube playback functions fine. With CPU frequency scaling available, the QuartzPro64 was able to set the (current) world record result for an RK3588 in Geekbench 5.”_ It is notable that OpenGLES already works flawlessly, including in glmark2. While Vulkan support isn’t functional yet, you can already expect some really solid performance in 3D acceleration tests. Speaking of acceleration, I’m told that the GPU was able to match a dedicated Nvidia GT750m in glmark2. I’m not sure how well this will translate to real-world 3D performance, but I certainly hope to make the QuartzPro64 the brains of a dedicated retro-game emulation machine at some point in the future.

To be clear, there are still a handful of missing features and outstanding issues which need to be addressed. Mothenjoyer69 explains “_SD card and PCIe are currently the primary issues, with SD card fixes being worked on. WiFi and a few other parts (the NPU, HDMI RX) are also currently non-functional. SATA functions \[however\]. Realistically the fixes don't appear to be that massive so right now SD card is the primary focus.”_ Once booting from SD will be fixed OS images will be made available for testing purposes on github. The work done by mothenjoyer64 and other contributors will, in time, serve as a basis for distributions to build their OSes atop of. As always, I hope that the early progress made on the board is indicative of the community’s interest in this powerful SoC and that eventually it will find its way into consumer-focused SBCs and future devices.

![](/blog/images/Running-mainline.jpg)

**Mainline Linux booted on the QuartzPro64 - via [Furkan Kardame (Manjaro)](https://twitter.com/fkardame/status/1554928120473571328)**

I would be remiss not to mention that mainlining efforts are made in parallel to the work on BSP. Indeed, as Mothenjoyer69 explains, _“mainline development has been very active with some large steps being made already. With the efforts of the Pine community, and ARM SBC community at large, the QP64 can successfully boot a mainline kernel, albeit with limited hardware support. With the continuing efforts of the community, and with assistance from Collabora, this will only improve as we move into 2023 and beyond."_ While mainline Linux is, as it always is, an end goal in an ARM SoCs development cycle, I for one am very happy that BSP and mainline are being developed simultaneously. Good BSP support and multiple feature-rich BSP OS images will help the platform grow and make the RK3588 viable for more user-oriented devices.

I am currently awaiting mothenjoyer69’s test images to become available so I can give the board a spin, and I must admit that I am genuinely excited to see what the RK3588 chipset is capable of. In the future I can see the QuartzPro64 platform becoming the basis for an entire line of very cool, versatile and highly diverse devices. I think that the chipset has multiple and widely different applications, the range of which can equal or even surpass the A64 and RK3399. Of course, only time can tell how this chipset will pan out. Until then, I’ll make sure to keep you updated.

That's all for this month!
