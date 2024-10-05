---
title: "December update: a year in review"
date: "2021-12-15"
authors: ["Lukasz Erecinski"]
categories:
  - "cube"
  - "news"
  - "pine64-community"
  - "pinenote"
  - "pinephone-pro"
  - "quartz64"
  - "risc-v"
tags: 
  - "keyboard"
  - "pinecube"
  - "pinephone-pro"
  - "pinetime"
  - "risc-v"
cover: 
  image: "December-Update-Header.jpg"
images:
  - "/blog/images/December-Update-Header.jpg"
---

![](/blog/images/December-Update-Header.jpg)

Seasonal greetings from the PINE64 community team! In the last community update of 2021 we’ll take a look at progress made this year and discuss potential avenues to explore in 2022. 

As far as news is concerned, we are happy to let you know that the PinePhone Pro Explorer Edition and PinePhone Pro keyboard production is steaming ahead with units available soon. 

Let's get into it. 

You can watch the synopsis of this month’s community update on YouTube (embedded below) as well as on [Odysee](https://odysee.com/@PINE64:a) and [PeerTube](https://tilvids.com/accounts/pine64tilvids/video-channels). To stay up-to-date with PINE64 news make sure to subscribe to this blog (subscription widget at the bottom of the webpage), follow [PINE64 Telegram News channel](https://t.me/PINE64_News), the [announcements channel in Discord](https://discord.gg/pine64) as well as our [Twitter](https://twitter.com/thepine64) and [Mastodon](https://fosstodon.org/@PINE64).

I’d like to thank [JF](https://twitter.com/codingfield), [Alex](https://twitter.com/AlexRob12252696) (clover), [Brian](https://mastodon.online/web/accounts/61817) (33YN2), [PizzaLovingNerd](https://www.youtube.com/channel/UCmGcm7dhEjS9CIOsOOv8y6w), [CounterPillow](https://github.com/CounterPillow) and [Marek](https://twitter.com/gamelaster) (Gamiee) for their contributions to this community update.

N.B. Comments on the blog post need to be in English and follow our [Community Rules and Code of Conduct](https://forum.pine64.org/showthread.php?tid=13209).

{{< youtube id="Ftk7Wm3-_ug" >}}

**Video synopsis of this month's update**

**TL;DR**

- Housekeeping
    - Merry Christmas everyone!
    - PineTalk recorder live on December 15 - listen and join us after the show 
    - Serious incident with malware made for the PinePhone; a run-down of what happened and steps taken
- A look back at 2021
    - Component shortages, logistics hurdles and brown-outs; a difficult year to manufacture and introduce new hardware to the market
    - Introduction of Quartz64-line of devices, including the PineNote
    - Crucial year for laying foundations for PineDio LoRa devices and peripherals 
    - The introduction of the PinePhone Pro
    - High LCD prices stalled Pinebook Pro and PineTab production for much of the year
- A sneak peak at 2022
    - The RK3588 will be announced at Rockchip’s event tomorrow and it's looking great
    - We’re pushing to bring PineDio to the Market ASAP; this is our main goal for early 2022
    - A small, but super cool, mystery project will be announced in Q1
    - We are interesting in exploring RISC-V architecture; something we may tackle in 2022, if production / component availability permits
- PinePhone Pro 
    - Developers have been getting their PinePhone Pro (PPP) over the past 2 weeks; positive response and good software progress means we’re proceeding With PPP Explorer Edition 
    - Explorer Edition edition available soon for $399 
    - Great software progress: modem, voice calls, LTE data, audio output, torch and LED all work now
    - OS images available include: postmarketOS, Manjaro, DanctNIX (Arch), Mobian and NixOS 
    - Small spec-bump since announcement - production PPPs have a higher resolution 8MP front-facing camera  
- PinePhone (Pro) hardware
    - Keyboard is in production and should be available in a few weeks, likely in early January
    - PineDio LoRa back case will be in Pine Store soon; thanks to efforts from devs it now works 
    - Fingerprint back case progress made and QA OS image for factory delivered; likely release in Q1 2022
- PinePhone (Pro) software
    - KDE Plasma Mobile 21.12 release brings a change from Ofono to ModemManager
    - Plasma Mobile’s new release includes many new UI improvements and resolves some pesky bugs
- Quartz64 
    - Linux 5.15 brings Quartz64 device tree
    - Quartz64 now outputs video via HDMI at 1080p 60hz for now; audio out via SPDIF also works out of the box
    - GPU works using the Panforst open driver
    - Tianocore EDK II implemented and allows for full UEFI
- PineTime
    - Car game utilizes PineTime accelerometer for steering; awesome demo of the device’s hackability
    - Many features coming to InfiniTime: BLE bonding with a PIN code to establish encrypted secure communication with the smartphone (or computer)
    - BLE filesystem API allows access to the PineTime’s internal filesystem via BLE
- PineDio
    - PinePhone PineDio LoRa back case works and can receive messages from other devices
    - PineDio PinePhone back case is coming to the Pine Store soon
    - Work carried out on new PineDio STACK prototypes
- PineCube
    - Work on reverse engineering the H.264 encoder driver for the PineCube SoC underway
    - A new closed-source H.264 driver works with the mainline kernel; can be used in the meantime

## Housekeeping

Thank you to everyone who contributed to the projects in 2021. I particularly want to thank our admins, [Matthew (Fire219)](https://twitter.com/fire219_SIMPL) and [Marek (Gamiee)](https://twitter.com/gamelaster), for their work. For those who don’t know, they are the people who put out the occasional fires and make sure that the cogs of the project keep turning. And a big shout-out to the moderators, who are doing a great job keeping our communication protocols clutter-free and safe. I also want to thank all of our partner projects - [Manjaro](https://manjaro.org/) and [KDE](https://kde.org/) in particular - for their work on our devices and their commitment to our shared community. I cannot forget about all the contributors, whom there are too many to mention individually, that make projects such as the PinePhone (Pro), the PineTime, and PineDio possible. Lastly, I want to thank all of you in the community for actively supporting us - I hope we did right by you yet another year. My best wishes to everyone - have a great holiday season. 

This month’s [PineTalk](http://pine64.org/podcast/) will be recorded live on December 15th. Brian ([33YN2](https://mastodon.online/web/accounts/61817)) and Justin (Porky) will be using the ‘stage’ feature on [Discord](https://discord.gg/pine64), found at the bottom of the server’s channel list. I encourage you all to join in, ask questions and stick around afterwards for a chat with the hosts and other community members. In case you miss it, the episode will be available in an edited format a few days later on the podcast streaming platform of your choice, as per usual.

![](/blog/images/Malware-notification-Telegram.png) ![](/blog/images/Malware-notification-discord-1024x94.png)

**Notification about the malware was issued in the News channels and in the chat platform - top: Telegram // bottom: Discord**

Lastly, I want to address a serious issue that transpired last week. A malware was shared in the chats, with the perpetrator claiming that it is a snake-type game and asking people for feedback. The malware has been made specifically for the PinePhone, wiping the phone’s file system and targeting a known vulnerability of the vendor’s modem firmware. It is important for me to note that the malware requires you to manually download and install it using root privileges (sudo). Here is a short run-down of what we did to mitigate and investigate this situation:

- Removed malware from chat and banned offending account(s) on more than one occasion
- Carried out an internal investigation of the incident 
- Consulted [Hacker Fantastic](https://twitter.com/hackerfantastic) from [_Hacker House_](https://hacker.house/) and received further assistance as well as a suggested course of action
- Secured website(s), the forum and Wiki; this includes more stringent rules for file uploads and additional screening of packages
- Deployed mitigating countermeasures to the chats and other communication protocols
- Notified our user base
- Having gathered the necessary information, authorities were informed of the incident - a formal investigation is underway and involves two law enforcement agencies

I am not going to go into more detail at this time, but I will keep you informed once the case reaches an end. What I will say is that we have good reasons to believe we can bring this to a satisfying conclusion. Before I head onto the next section, let me state the obvious: be cautious when installing software from unknown repositories onto your device.

## A look back at 2021

This was a gratifying but difficult year. At the beginning of the year, we initially believed that the worst was already behind us. As it turned out, however, 2021 proved to be even more challenging than last year. Component shortages, price-hikes of electronic parts, shipping hurdles caused by ongoing pandemic mitigation strategies, and production difficulties caused by state-imposed power consumption limits; are just some of the things we had to tackle this year. The circumstances forced us to prioritize and focus on the things that we could actually deliver. Although this may seem like a straightforward strategy to adopt, in reality it wasn’t. Figuring out what will be available, how much it will cost, and where it can be manufactured, was a complex jigsaw to solve. Regardless of the circumstances, there was a sense that we need to press on rather than wait until things take a turn for the better. With the year 2022 looking only marginally better than 2021, I think this was a painful but good strategy, as waiting it out is clearly not an option.   

![](/blog/images/China_power_supply.png)

**As if component shortages and pandemic mitigation measures weren't enough to cripple production ...**

Three decisions were made early on in the year: to introduce single board computers and devices based on the RK3566, to start working on our own LoRa-based communication platform, and to bring a higher-end PinePhone to the market. The Quartz64 model-A was unveiled in [February](https://www.pine64.org/2021/02/15/february-update-show-and-tell/) and was made available two months later. In [June](https://www.pine64.org/2021/06/15/june-update-new-hardware-and-more-on-the-way/) we introduced the SOQuartz compute module, which started shipping to developers and early adopters just recently. Both devices were met with much interest (I’d go as far as to say that the SOQuartz is very popular) and software enablement for the platform is proceeding quickly. The promising pace of software development also convinced us that now is the right time to [introduce the PineNote](https://www.pine64.org/2021/08/15/introducing-the-pinenote/) - an e-ink device based on the Quartz64-line of single-board computers. PineNote’s announcement is something many in our community have waited years for and, with the RK3566 SoC being a perfect fit for the job, we launched production.   

![](/blog/images/MNT-Reform-SOQuartz-911x1024.jpg)

**An adapter for the MNT Reform laptop with SOQuartz installed (our best wishes to [Lukas](https://twitter.com/mntmn) and the team) - picture via [MNT Reform Twitter](https://twitter.com/mntmn/status/1469271526323245060/photo/1)**

This year we also announced our [plan for a LoRa-based](https://www.pine64.org/2021/05/06/lets-make-mirakles-happen/) communication platform called PineDio, which will allow all of our devices to communicate over vast distances without the need for a GSM/CDMA modem. We have a long-term commitment to the PineDio ecosystem, and I’ll talk more about it in the following section, but suffice to say I am very impressed by the progress made this year; I am looking forward to seeing PineDio deployed across the globe. 

![](/blog/images/PineDio-stack-Lup-Yuen-Lee-1024x1024.jpg)

**Lup Yuen Lee documents in detail PineDio development on [his blog](https://lupyuen.github.io/) - picture via [Lup's Twitter](https://twitter.com/MisterTechBlog/status/1469709861210320901/photo/1)**

Last, but certainly not least, we [announced the PinePhone Pro](https://www.pine64.org/2021/10/15/october-update-introducing-the-pinephone-pro/) in October this year. This is certainly one of the most anticipated devices we’ve created. We worked on the PinePhone Pro for over a year prior to making the announcement, and the process of bringing it to the market was no simple feat. We tried at least three different hardware configurations before settling on the final device design. Hardware development proved particularly difficult due to various components drifting in-and-out of availability - making it hard to determine production viability in 9 month’s time. Uncertainty was high throughout the process and the decision to proceed with production was made just a month prior to the announcement. Only once all components and factory floor-time were secured did we feel like it was safe to launch the PinePhone Pro. One benefit of these circumstances is that it has only been 2 months since the announcement, and we have already shipped units to developers, and will be shipping the Explorer Edition in just a few short weeks. 

  
  

![](/blog/images/PinePhonePro-in-the-wild.png)

**One out of many PinePhone Pros in the wild - [source on Twitter](https://twitter.com/JiiNissi/status/1469580653125591040)**

Concluding this section, and for the sake of diligence and fairness, it is also important to note that we didn’t manage to produce more than a single production run of the Pinebook Pro this year. The reason for the prolonged halt in Pinebook Pro and PineTab production is related to the elevated price-point of LCD panels. Even with the current price increase of the laptop, we could not cover the production and assembly costs with a good quality LCD (something that the Pinebook Pro is known for). The price of LCD panels has remained high throughout the year but recently we saw some indications that prices may gradually start coming down; this makes us cautiously hopeful that production can resume soon after the Chinese New Year. To this end I want to make it clear to everyone - the Pinebook Pro, in its current configuration, will keep on being produced, and production will start as soon as we can source panels at a reasonable price. I’ll write more about this in the next section.

## A sneak peek at 2022

The year 2022 will be, by and large, all about the PinePhone Pro and the Quartz-line of devices. By this time next year - granted no disaster strikes - there ought to be (tens of) thousands of active PinePhone Pro users worldwide as well as a significant number of PineNote testers and developers. We also hope to bring back the Pinebook Pro and PineTab after the Chinese New Year that is celebrated at the start of February 2022. LCD prices have been coming down in price steadily these past months and we expect to see broader availability of affordable panels soon. We are looking forward to having the Pinebook Pro and the PineTab in stock just as much as you do. Lastly, Rockchip will finally be introducing the RK3588 on December 16th (which means I can’t write about it on the day the update goes live - sorry), which will most certainly be of interest to us. What I will say is that it will bring entry-level desktop-class Arm CPU performance and plenty of IO options; keep a lookout for press coverage of Rockchip’s event.

![](/blog/images/Rockchip-newsroom-1024x548.png)

**keep an eye on [Rockchip's press release](https://www.rock-chips.com/a/en/News/Press_Releases/index.html) website**

While the prospect of a high-end computational device is certainly exciting, it also isn’t at the top of our to-do list. Something that is on our agenda  however, is launching our LoRa range of PineDio devices. [JF](https://twitter.com/codingfield) and [Lup](https://twitter.com/MisterTechBlog), as well as a handful of other developers, have been working on the PineDio gateway and device nodes for much of this year. Thanks to their efforts (most of which have been well documented in the community updates) the PineDio platform has now reached a significant degree of maturity. [RTP](https://www.youtube.com/c/RTPPrivacyTechTips) has recently contributed a dedicated Armbian-based build for the PineDio gateway, which makes the initial setup and operation simple. I don’t currently have any firm dates for the roll-out, but we should have a preliminary timeline established by the end of next month. 

https://www.youtube.com/watch?v=bustSeT2QEg

**A look at the PineDio gateway OS image - via [RTP Privacy Tech Tips on Youtube](https://www.youtube.com/c/RTPPrivacyTechTips)**

At the start of 2022, we will also be introducing a cool small project into our lineup. Let me first clarify what ‘small’ means in this context: a small project is limited in scope and completely community-driven. Examples of such existing PINE64 projects include the Pinecil and PineTime. Small projects benefit from two things: 1) software for them can be completed to a high degree of satisfaction in a short(er) period of time; 2) and we can do them better than big brands for less. The Pinecil, in particular, has shown that we can upset a stagnant market by introducing a better and open device for half the price of existing options. This time, however, we’re hoping to bring something that can be enjoyed by enthusiasts and mainstream customers alike. It will be the first open device of its kind (to my knowledge) and we’re making it from the ground up with the help of experts. There will also be a dev board for it, which will likely be released at the same time as the device itself. This is all I can say right now, but an announcement should follow in Q1 2022. 

Another area we wish to explore next year is RISC-V. It shouldn’t come as a surprise that RISC-V SoCs are of interest to us, as we have already spoken about plans for an [entry-level RISC-V SBC](https://www.pine64.org/2021/03/09/risc-v-sbc-riddle/) in the past. While our plans to use Allwinner’s RISC-V SoC stalled, our curiosity in the platform has not waned. We’re interested in both microcontrollers as well as much more powerful Linux-capable SoCs, and we are already drawing up plans on how each type can be used in novel and innovative ways. As is usually the case, the journey will likely begin with a development platform and eventually make its way into enthusiast-grade devices. These devices will likely not appear anytime soon, however, so don’t hold your breath. In any case, if the supply line and component shortages subside, we’ll surely be taking a close look at what RISC-V can offer the PINE64 community.

Lastly, we will be working towards improving the global shipping times of the most popular devices. I don’t want to make any promises at this point - I just wanted to let you know that we’re exploring an option that would potentially allow us to ship globally regularly. We’ll start slowly, probably with the PineNote, due to the relatively lower volume of sales compared to our smartphones and laptops. If the dispatch option turns out to work well, then we may start using it for other devices. We’ll also await your feedback. I’ll make sure to keep you posted.

## PinePhone Pro

By the time this update goes live, you will likely have already seen countless developers posting photographs and videos of their PinePhone Pro units. The task of sorting, issuing and shipping developer’s orders was carried out within the time frame we initially aimed for. I am happy to report that much of the early feedback has been very positive: developers find the unit fast, easy to work with, and well-executed. It also appears there are no major flaws in the design. We are, therefore (still) aiming to open PinePhone Pro sales late this month or early the next. The price of the Explorer Edition remains unchanged - $399. The exact availability date will depend on how quickly we can establish a viable QA testing methodology at the factory; QA testing hurdles make for a boring story so I’m not going to describe the ordeal, but if you want to learn more then leave a comment below and I’ll respond with the details. The take-away is that it shouldn’t be long now. I will publish a blog post when the PinePhone Pro becomes available for purchase. The Explorer Edition launch blog entry will include detailed information about the device and software maturity so that everyone ordering a unit will know exactly what they’re getting (into). I don’t want people expecting full functionality picking up a PinePhone Pro at this time, instead, I‘d like to see well-informed early adopters who are willing to engage with the community and contribute to the development process. 

![](/blog/images/OS-images-on-Wiki-1024x513.png)

**Porting of OSes has started -  screenshot of _[Software Releases section](https://wiki.pine64.org/wiki/PinePhone_Pro_Software_Releases)_ on Wiki**

If you fall into the category of a competent early adopter, then I am glad to say you’re in for a treat. [Last month](https://www.pine64.org/2021/11/15/november-update-first-impressions/) I listed 5 things needed to reach software parity with the original PinePhone - today we can already cross 3 of these off the list. The following are now functional: 1) USB for data and video, 2) sound output and, 3) modem including voice calls. Credit for these enablements go to [A-Wai](https://mastodon.online/@awai) from [Mobian](https://mobian-project.org/) and [Megi](https://xnux.eu/); obviously, neither of them develops in a vacuum, and input from other developers contributed to these features now being functional. Even little things, such as the torch or notification LED now work. Mind you, these implementations are in a preliminary enablement stage, and regressions are to be expected at this development stage. More importantly, however, this means that the main outstanding missing core features are the cameras and power management improvements. The latter also includes finding a solution for the smartphone’s failure to wake from suspend. There are other, smaller, issues that need to be addressed, but from an end-user perspective, these are the major two. 

{{< youtube id="vo49cEO0Lk4" >}}

**Audio now works on the PinePhone Pro - via [Manjaro](https://manjaro.org) dev team**

There are now postmarketOS, Mobian, Manjaro, DanctNIX (Arch) as well as NixOS OS images for the PinePhone Pro. Some of these can be found on the [PinePhone Pro Wiki](https://wiki.pine64.org/wiki/PinePhone_Pro_Software_Releases), whilst others - like [Mobian](https://images.mobian-project.org/pinephonepro/weekly/) - are yet to be added to the list (but can already be found on the project’s repositories). I am sure that more OSes will follow shortly - indeed, some may already be available by the time you’re reading this. As was, as still is to some degree, the case with the original PinePhone, there will initially be discrepancies between functionality across distributions. Things that work on one OS will not work on another and vice versa. These differences will eventually fade and a similar experience will be available across the board. But this will take time. I have been using my PinePhone Pro daily for over a month now, mostly running Manjaro with KDE Plasma Mobile, and I can see myself dumping my Android in the future (once resuming from suspend works). Needless to say, I am very pleased with the software progress and the hardware itself. My assessment is obviously biased, but thankfully there are already plenty of hands-on accounts available for you to make your own mind up whether this is your future daily driver or not. Some devs already do really fun things with the device to showcase its raw power, as illustrated by the emulation of GameCube. Honestly, this exceeded my expectations. 

{{< youtube id="RFUuhoZYAVw" >}}

**GameCube (Dolphin) emulation on the PinePhone Pro is pretty crazy - via** [**FOSSingularity on Twitter**](https://twitter.com/FOSSingularity/status/1470124088085602309)

There is one more thing I’d like to touch upon - the final design of the PinePhone will feature a higher-end (8MP) front-facing camera than originally (5MP) planned. The rest of the specs remain the same, just as they were [initially announced](https://www.pine64.org/pinephonepro/). This is a small and likely relatively insignificant spec bump, but it is also something I have to make you aware of. Information on the device page and Wiki should now also be updated to reflect the upgraded hardware. For those of you who want the specifics: the camera is an ov8858 8MP 1/4-inch sensor, known to produce good quality pictures. Anticipating the question: yes, the current dev units already have this camera module installed. I am told that it is a significant step-up from the sensor (OG PinePhone’s main camera) in every sense of the word - consider it a small bonus.

Lastly, I have put in some initial work to draft a [Wiki layout for the PinePhone Pro](https://wiki.pine64.org/wiki/PinePhone_Pro) (which I closely modeled after the original PinePhone’s Wiki), and I am happy to see people already contributing content. I would like to encourage all of you who have already received their PinePhone Pro and those who will soon be receiving one soon to fill in as many outstanding information knowledge blind spots as possible. Anyone can create a Wiki account and contribute content to any section, and if you are registered on the forum your existing credentials should work. The more of the basics we can collectively cover at this early stage, the better the experience Explorer Edition users will have with their devices. Thank you!

## PinePhone (Pro) hardware

The PinePhone keyboard and LoRa PineDio back case will be available in the Pine Store shortly - likely at the very beginning of January. I already described the reasons why the keyboard was delayed at the last moment in the [November update](https://www.pine64.org/2021/11/15/november-update-first-impressions/); long story short, both the developers and production team weren’t completely satisfied with the keyboard’s membrane. Consequently, the vendor was asked to improve the responsiveness and consistency of the key presses. Given how the keyboard has now already been in prototyping and testing for over 6 months, another few weeks to get it just right is a small price to pay to deliver a better piece of hardware. And we really want to get it right from the get-go rather than having to revisit design choices in the future. That said, I do apologize for the delay, and I am very aware that many of you are growing impatient. The good news is that we’re having many keyboard units manufactured, so the chance of us selling out in a very short amount of time is slim to none. In other words, everyone who wants one will be able to pick one up. DanctNIX (Arch), postmarketOS, Manjaro, and Megi’s multiboot OS images have all been updated to support the keyboard at this time - there may be others that I’m not aware of, please check with your OS maintainer.

{{< youtube id="ZaciUkMrXiY" >}}

**p-boot now has portrait mode - via [Megi](https://xnux.eu/)**

The PineDio back case is now functional thanks to work done by JF and Lup. It will be available in the Pine Store soon, as early as next week. I won’t be writing more about the PineDio back case in this section, since I am sure JF will cover the key developments further down in this community update (you may also want to read [last month’s update](https://www.pine64.org/2021/11/15/november-update-first-impressions/) for more PineDio news). I am super thrilled that the back case will be available by the time the PineDio gateway hits the store. Since we’re on the topic of back cases, then I am also happy to report we’ve also made progress on the fingerprint back case. [Zachary](https://www.reddit.com/user/zschroeder6212/), the community developer behind [the first fingerprint reader prototype](https://www.reddit.com/r/PINE64official/comments/jurehy/pinephone_fingerprint_scanner_update/), delivered a custom QA fingerprint sensor testing OS image to be used at the factory floor; if the factory finds this build sufficient for testing purposes then we may finally see the fingerprint reader back case launch in Q1, 2022. 

## PinePhone (Pro) Software \[by 33YN2\]

Plasma Mobile has seen some major changes that have now been released in the Plasma Mobile Gear 21.12 release. The biggest is that it now has fully switched over to using ModemManager for telephony functionality. It also now has support for MMS messages in its SMS app, and additionally the SMS application now automatically detects links and 2FA codes and gives a copy shortcut to quickly copy them to your clipboard. Aside from the telephony changes, the shell itself has seen lots of work. Not only will the buttons now move to the right-hand side of the display when the device is rotated into landscape mode, but it also now has the new list view app drawer layout. The task switcher has also seen a major redesign, with a more efficient card style similar to that which is used by Lomiri. This is far from the end, however, there are more improvements and fixes coming for the new task switcher, and more to be done to the shell too. Make sure to check out the [Plasma Mobile Gear 21.12 blog post](https://plasma-mobile.org/2021/12/07/plasma-mobile-gear-21-12/) for a more detailed look!

{{< youtube id="DBpRGmDkJ0o" >}}

**Showcasing performance of an early build of Manjaro with Plasma Mobile on PinePhone Pro**

## Quartz64 \[by** **CounterPillow****\]

A lot has happened this past month in terms of Quartz64 software. Linux 5.16 finally has the Quartz64 Model A device tree, which describes the Quartz64 Model A's hardware and allows the mainline kernel to actually boot on the board completely out of the box, without patching needed. But the biggest news is probably the VOP2 patch set, enabling video output on the RK356x family of SoCs, of which the Quartz64 uses the RK3566. It's in a very rough state; its internal state tracking logic is broken, the frame presentation is buggy, and it only supports 1080p monitors at 60 Hz at the moment, but it's great to finally see movement on this front.

![](/blog/images/Q64-Video.jpg)

**HDMI output on Quartz64 model-A**

The patch set comes courtesy of [Sascha Hauer](https://github.com/saschahauer), whose work is based on the downstream Rockchip BSP kernel's driver. A small follow-up patch by [Michael Riesch](https://github.com/mriesch-tum1) to enable it on the Quartz64 Model A has also been contributed. Both Manjaro and [pgwipeout](https://github.com/pgwipeout)'s CI Debian installer already have the patch set applied, which allows people who are interested in the board to have a go at it without having to patch their own kernel. We still recommend you have a UART adapter such as PINE's Woodpecker to troubleshoot any issues. It's only $1.99. Don't have regrets.

In terms of booting, [Jared McNeill](https://github.com/jaredmcneill) ported Tianocore EDK II to the Quartz64 Model A, which means that there is now full UEFI available. The port is still in an early stage, but it's an exciting move towards getting the board ARM SystemReady certified. The port still requires Rockchip's firmware blobs, however, as Rockchip has yet to release the ARM Trusted Firmware sources for the RK3566 and RK3568. At the same time, pgwipeout has begun tinkering with mainline u-boot. Albeit there is some manual hackery and binary blobs involved, he managed to get mainline u-boot running. This is another promising route towards a better booting experience on the board. He also experimentally ported the mkimage utility changes over to the mainline version.

![](/blog/images/VM-on-Quartz64-1024x576.jpg)

**VM on the Quartz64 - via [Jared McNeill on Twitter](https://twitter.com/jmcwhatever/status/1463703248162934788/photo/1)**

As for the Linux kernel, I have been doing a bunch of small work here and there. SPDIF audio works in kernel 5.16 right out of the box on the Quartz64, if you're into that. Analog audio works as well, thanks to the i2s-tdm audio controller driver I've ported. As soon as the VOP2 patch set dropped, I also got to work on HDMI audio, which works, but isn't merged yet because the VOP2 patches aren't merged either. We depend on the HDMI output and a video clock to get HDMI audio, so there's a dependency on that patch set. Additionally, I submitted the SPI nodes to the RK356x device tree, which means that starting with kernel 5.17, people will be able to simply enable the SPI node in the Quartz64 device tree and add their SPI device definitions to it.

Rockchip's engineers have been very busy with unspecified other projects, but they have submitted some patches to the Linux kernel as well. The naneng combo PHY, which handles the physical interface for SATA, USB 3, and PCIe, has been submitted for review by Yifeng Zhao and is currently in its third iteration. pgwipeout's Quartz64 CI kernel has this patch set applied too. Sugar Zhang of Rockchip has also contributed some SPDIF driver updates to make it work with the newer Rockchip SoCs.

{{< youtube id="B8tikV3tJuQ" >}}

**Slightly patched kmscube showing a shadertoy shader**

Oh, did I mention yet that the GPU works? Yes, the GPU works. [Alex Bee took over Ezequiel Garcia's GPU enabling patch set](https://lkml.org/lkml/2021/11/26/620), and with a recent enough version of Mesa, you'll have working 3D acceleration. It can even thermally throttle now, in theory, but in practice, the GPU doesn't really get hot enough. In my stress tests with a medium heatsink on the device, the GPU never got hotter than 45°C (around 25°C over ambient.) Thanks to the VOP2 patch set, a couple of bugs have been found in other drivers. Alex Bee discovered a bug in the IOMMU driver that made video output fail on 8GB boards. This was fixed during the Linux 5.16 bug fixing cycle, so now the video output will work on all Quartz64 boards, no matter the amount of RAM.

I've also discovered a bug while working on the VOP2-prompted HDMI audio patch set, namely that my i2s-tdm audio controller driver wasn't happy being loaded multiple times. Oops. I've fixed this in Linux 5.16. Many of these improvements will of course affect the PineNote, as it uses the same SoC: if somebody adds something to the RK356x device tree, it'll also be available to the PineNote device tree that smaeul wrote. 

As always, you can track our continued progress on the Quartz64 Development Wiki page which I try to keep as accurate and up to date as possible.

## PineTime \[by JF\]

Remember when [last month](https://www.pine64.org/2021/11/15/november-update-first-impressions/) I mentioned this nice [demo from Petterhs](https://www.youtube.com/watch?v=QR5NhzcqyKA), showing him controlling a 3D object using the motion sensor of the PineTime? Peter has now extended this demo which now allows him to control a car in a car racing game. I really enjoy such demos, since they showcase how hackable PineTime is and how endless the possibilities are!

{{< youtube id="Ciu_dMfYJtI" >}}

**PineTime as a game controller**

InfiniTime developers and contributors are working on a few great features for the project. I won’t go into the details right now since we are still working on them, but here is an overview of what you can expect in future releases of InfiniTime.

First, the secure [BLE bond](https://github.com/InfiniTimeOrg/InfiniTime/pull/796). This feature, contributed by [evergreen-22](https://github.com/evergreen22), enables BLE bonding with a PIN code that establishes a secured (encrypted) communication. I did check that the communication was actually encrypted using my [sniffer setup](https://infinitime.io/blog/2021-02/debug-ble/). The screenshot below on the left shows a "sniffing" session from a PineTime running InfiniTime 1.7.1. As you can see, everything is visible in plain text: BLE commands, characteristic handles and notification content ("Hello world"). The screenshot to the right shows the same scenario but running on a build which includes this new feature. Now we no longer can make out of the content of the BLE messages:

![](/blog/images/unencrypted-1024x471.png) ![](/blog/images/encrypted-1024x578.png)

**Left: unencrypted connection // Right: encrypted connection**

The next massive feature is the \*\*BLE filesystem API\*\*. [Geekbozu](https://github.com/InfiniTimeOrg/InfiniTime/pull/756) implemented this API which allows companion apps to access the internal filesystem of InfiniTime. For now, this filesystem is only used to store user settings, but the end goal is to also store pictures, logos, fonts, translations, and much more in the memory. This feature is a major step toward reaching this goal. As a demo, I sent multiple random pictures to my developer PineTime and used them in a custom build of InfiniTime as the background of my clock:

![](/blog/images/poster2.png)

**Background pictures set via BLE filesystem API**

Note that those features are not stable yet, and therefore we have not released them in a public version of InfiniTime. They are however available in [the develop branch of the project](https://github.com/InfiniTimeOrg/InfiniTime) and everyone is free (and welcome) to test them and provide feedback!

That's it for this month! I wish everyone a Merry Christmas, a happy new year, and happy unboxing for those of you who'll receive a PineTime as a Christmas gift!

## PineDio \[by JF\]

As you probably know, the [PineDio range of devices](https://wiki.pine64.org/wiki/Pinedio) aims to deploy LoRa (Long Range low-power wireless communication) everywhere and across all PINE64 hardware . We have already talked about the LoRa PineDio gateway, the USB adapter, and the PineDio STACK (development kit based on the BL604 microcontroller) in previous updates.

Did you know that Pine64 is also working on a LoRa backplate for the Pinephone? This backplate will allow the Pinephone to send and receive LoRa messages thanks to the integrated LoRa module and antenna.

![](/blog/images/antenna1-1024x768.jpg)

**PinePhone (Pro) PineDio back case disassembled - a close took at the LoRa antenna**

These last few weeks I worked on bringing this backplate up and running, and succeeded in receiving LoRa messages from other LoRa devices. This is still mostly a work in progress, but it clearly shows that the integration of LoRa in a mobile phone running Linux is possible and, indeed, already functional! For those interested in the technical details, I documented everything in this series of 3 articles: [_First look at the LoRa backplate_](https://codingfield.com/blog/2021-11/first-look-at-lora-pinephone-backplate/), [_Flashing the LoRa backplate_](https://codingfield.com/blog/2021-11/flash-the-lora-pinephone-backplate/) and [_A driver for the LoRa backplate_](https://codingfield.com/blog/2021-11/a-driver-for-the-pinephone-lora-backplate/).

See the [video here](https://video.codingfield.com/videos/embed/6d713488-5469-442c-a40e-961daa3d9636)

**Receiving LoRa messages on the PinePhone with PineDio back case**

Note that the LoRa backplate is not available yet in the store, but Pine64 is actively working on it and even requested software to test the board in production, so they will probably be available in the near future! **\[edit from Lukasz\]** _Indeed, with the software now in a functional state, we will be starting to sell the PineDio back case for the PinePhone and PinePhone Pro in the next few weeks._  

On a similar topic, [Lup Yuen Lee](https://twitter.com/MisterTechBlog) is currently working on bringing [NuttX to the PineDio STACK](https://twitter.com/MisterTechBlog/status/1469857569300566019?s=20). He also documented the testing of [the new prototype version of the STACK](https://twitter.com/MisterTechBlog/status/1469709861210320901?s=20) we received last month. This new prototype comes in an enclosure and is equipped with GPS and a motion sensor in addition to a display and a LoRa module.

## PineCube \[by Gamiee\]

As we have seen in previous community updates, the PineCube is already very usable with software MJPEG encoding. But it's still not perfect, since software MJPEG encoding uses a lot of CPU power and, but to the PineCube’s single ARM Cortex-A7 core, not much power is left to other things. Because of this, PineCube's SoC has a hardware H.264 encoder core, which can encode video with minimal impact on the CPU. But for this core to be functional we need a driver. The current driver is closed sourced and doesn't work with the mainline Linux kernel; it only works with ancient Linux 3.10 kernel. So I started to reverse-engineer this driver, and I'm creating an open-source implementation of it; you can track the progress of this project and learn more about it [here](https://github.com/gamelaster/pinecube/tree/main/software/recedar).

While I was working on this project I learned a lot about how the whole driver and encoding core works. But I also found newer drivers, which can work on the mainline kernel with some modifications. So I modified and built the latest Linux 5.15 kernel, prepared the Debian root filesystem, and tried to see if the drivers would work. And it did!

![](/blog/images/mainline-debian-on-pinecube.png)

**PineCube running mainline Linux kernel**

So in the meantime, while I work on an open-source re-implementation of the driver, the PineCube can have hardware accelerated H.264 encoder using a modified closed source driver. Since I didn't have enough time to test it fully it remains uncertain if popular libraries like FFmpeg or GStreamer will be capable of using this driver, but it should work and I will let you know in the next community update about the progress made.

That's it for this month, Happy Holidays everyone!
