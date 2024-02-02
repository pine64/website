---
title: "December Update: Merry Christmas and Happy New PineTab"
date: "2022-12-15"
categories: 
  - "community"
  - "news"
  - "ox64"
  - "pine64-community"
  - "pinephone"
  - "pinephone-pro"
  - "pinetab"
  - "quartz64"
  - "quartzpro64"
  - "risc-v"
  - "star64"
tags: 
  - "community"
  - "pinephone"
  - "pinephone-pro"
  - "pinetab"
  - "quartz64"
  - "quartzpro64"
cover: 
  image: "DecemberUpdate.jpg"
images:
  - "/blog/images/DecemberUpdate.jpg"
---

![](/blog/images/DecemberUpdate.jpg)

Merry Christmas, happy holidays and a Happy New Year to you all. This month’s update has a different formula from the usual - aside from the announcement of the PineTab2, most of this month’s content is dedicated to looking back at this year and taking a sneak peak at what's to come in 2023. I think that if you read between the lines, even poorly, you’ll get a good idea of what we’ll be up to next year.  

We have a lot of ground to cover in this update so let's get to it. 

You can watch the synopsis of this month’s community update on YouTube (embedded below) as well as on [Odysee](https://odysee.com/@PINE64:a) and [PeerTube](https://tilvids.com/accounts/pine64tilvids/video-channels). To stay up-to-date with PINE64 news make sure to subscribe to this blog (subscription widget at the bottom of the webpage), follow the [PINE64 Telegram News channel](https://t.me/PINE64_News), the [announcements channel in Discord](https://discord.gg/pine64) as well as our [Twitter](https://twitter.com/thepine64) and [Mastodon](https://fosstodon.org/@PINE64).

I’d like to thank [Alex](https://twitter.com/AlexRob12252696) (clover), [Gamiee](https://twitter.com/gamelaster), [Danct12](https://twitter.com/RealDanct12), [Pillow](https://github.com/CounterPillow), [Thanos](https://fosstodon.org/@thanosengine), [Immy](https://mastodon.social/@immychan@antabaka.me) and [PizzaLovingNerd](https://www.youtube.com/channel/UCmGcm7dhEjS9CIOsOOv8y6w) for their contributions to this community update.

N.B. Comments on the blog post need to be in English and follow our [Community Rules and Code of Conduct](https://forum.pine64.org/showthread.php?tid=13209).

{{< youtube id="WvG2jUS6n_s" >}}

**Video synopsis of the December community update**

**TL;DR**

- Housekeeping
    - Thank you for 2022 everyone!
    - November community Q&A is now on Youtube and Odysee if you missed it
    - We’ve got a FOSDEM 2023 stall - we’re on the floor both days, come and see us
    - Work on the new website is coming along
    - PINE64 EU store restock before Christmas 
    - We’ve had an incident in #off-topic channel - we’re on it and working towards better moderation of all chats
- Newsflash
    - Star64 launch delayed due to review; striving to make it available before CNY
    - Ox64 among the fastest selling PINE64 hardware
    - Pillow has done much work on the Quartz64, SOQuartz and QuartzPro64 in the past month; much work has gone into mainlining and critical bug fixes - significant progress 
    - Much Pinecil V2 news and showcases: new Pinecil V2’s ship with firmware v2.20, Bluetooth functionality casting telemetry to computer, transparent Pinecil mod with LEDs, a nice 3D printed carry case and more
    - New DietPi release brings many important improvements to the Quartz64 and SOQuartz
- A look back at 2022
    - A review of the year 2022 with an explanation of its significance moving forward: launch of the PinePhone Pro and keyboard case; introduction of the QuartzPro64 for devs; launch of Pinecil V2 and PineBuds Pro; and finally our first RISC-V SBCs
- 2023 sneak peek 
    - A look at where PINE64 and in the year 2023 and beyond: focus on RISC-V alongside Arm with potential RISC-V based hardware in the coming year
- PineTab2
    - An explanation of what happened with the original PineTab; in a nutshell, it fell victim to pandemic and post-pandemic production issues and other project priorities
    - Sports a metal case which is easy to disassemble for repair and hardware hacking
    - Features the RK3566 - a great SoC for a tablet due to low power consumption and low thermals 
    - Two USB-C ports - USB 3.0 other USB 2.0 speeds and dedicated for charging; micro HDMI port for video output; microSD slot & headphone jack; a 2MPx and 5MPx camera
    - Will be available in 2 configurations: 8GB RAM / 128GB flash & and 4GB RAM / 64GB flash storage
    - Launch and price point not known yet - expected sometime after CNY
    - Dev units available soon (prior to CNY)
- PinePhone (Pro)
    - Major SailfishOS developments; sensors now work properly as does audio and calls work
    - Expectation that receiving calls in suspend will be possible soon on SailfishOS
    - Megi’s newest kernel brings countless improvements; improvements includes 60hz refresh for PinePhone Pro, complete CSI driver rewrite and DRM improvements on OG PinePhone 
    - Better support for the PinePhone (Pro) keyboard case 
    - Kali Linux launches Nethunter Pro with official support for both the PinePhone and PinePhone Pro

# **Housekeeping** 

I’d like to start by thanking [Marek (Gamiee)](https://twitter.com/gamelaster) for his incredible work in the past year steering this project. Marek has done an incredible job taking over from me and I see how much thought and heart he puts into this community. We also need to thank [Matthew (fire219](https://twitter.com/fire219_SIMPL)) and all the moderators for maintaining our communications channels and keeping the community orderly. We all also much acknowledge the work by contributors and our partner projects - without them and their hard work there would be no PINE64. I also want to express gratitude to those working on the community update each month - in particular [PizzaLovingNerd](https://twitter.com/PizzaLovingNerd), [Alex (Clover](https://twitter.com/AlexRob12252696)) and [JF](https://twitter.com/codingfield). You’ve all done an amazing job this year. Last but certainly not least I also want to thank all of you who support us - your support for the project and, by extension, the Pine Store is what pushes us to explore new avenues, create new hardware and foster a great community. Thank you everyone for 2022.         

We had a great Q&A session in November with countless questions being asked and answered. Thank you to everyone who joined us in the chats, asked questions and listened-in on Youtube and the Discord stage. I think that the Q&A is a really great way for the community to come together and interact with people shaping the project. I am aware that we ran out of time and some questions remained unanswered at the end of the event. And I know this isn’t the first time it happened. This leads me to think that it may be a good idea to make the Q&A session a bit longer to accommodate more questions - although, there is a limit to how long Marek and I can talk aloud and provide focused answers. I am also considering allowing people to post questions in the chat a day or two prior to Q&A. Feedback regarding these ideas is welcome - after all, this session is meant to benefit you. So please leave your thoughts on the Q&A and how to make it a better event for the community in the comment section below. It is a bit early to plan the next Q&A right now but it will be held at some point either in late February or early March next year.

{{< youtube id="8yzfyjIz5g0" >}}

**November community Q&A live recording**

We got a stall at [FOSDEM](https://fosdem.org/2023/)! I cannot overstate how happy to once again attend the event in-person, meet members of our community and man the stall. We have a huge number of things prepared for the meetup and there is at least one important announcement we’ll be making on February 4th. Mark the date in your diary. If you are in Europe and able to travel then make sure to pop by our stall and say hello - there’ll be plenty of gear to check out and discuss. The exact location of the PINE64 stall hasn’t been made available yet on FOSDEM’s website but I suspect that by January 15th and the next community update. I have also been toying with the idea of live-streaming or recording videos from the stall so that people from the community who cannot travel can virtually ‘visit’ check out some of the things we’ll be showcasing. What do you make of this idea? - let me know in the comments. 

Work on the new PINE64 community website is ongoing and, while we don’t really have an ETA for the new page’s launch, it is shaping up really nicely thanks to the work by a handful of community contributors, including Vincent who’s in charge of layout and assets. I am including a few snapshots below so you get a general sense of where the redesign is heading; the new website will focus on the community, giving this blog more of an exposure and allowing quick and easy access to all available documentation as well as chats and forums. I also hope to have some sort of exposure of community projects - perhaps something to the effect of the #community-content channel or the _newsflash_ section in this blog. I really like the direction this website rework is heading and will be bringing you more updates on it in the near future.        

![](/blog/images/New-WebsiteOrg2-1021x1024.png)

**A peek at the new website (work in progress)**

PINE64 EU is receiving restock shipments soon. I am mentioning it in this month’s update for two reasons: i) it may take time for the shipments to clear customs due to the high volume of work at both the customs and the proxy customs agencies. It usually takes 7-9 days for a shipment to clear customs (following the mandatory harmonization process) but this time it may take much longer. Regardless, I hope stock will be received before the holidays ii) Shipments during the holiday season and in the weeks following it may take longer to arrive at their destinations - just a heads up. To stay up-to-date, follow the EU store’s [Mastodon](https://fosstodon.org/@pine64eu), [Twitter](https://twitter.com/pine64eu) and [Telegram](https://t.me/pine64eu) news channels. 

Lastly, I want to spend a few lines explaining the situation regarding a temporary closure of the #off-topic chat, the consequences of the closure and what steps we’ll be taking in the coming weeks to deal with the situation. The #off-topic chat was temporarily closed by Matthew (fire219) due to an - apparently on-going - clash between multiple members of the community. Let’s just say that some of the topics discussed in #off-topic (which should have never been discussed in the first place) led to very heated discourse. Internally this raised a question of whether the [current code of conduct](https://forum.pine64.org/showthread.php?tid=13209) is sufficient for consequential moderation and if we should create a moderation guideline for the mods. People from different walks of the internet and of various sensitivities have been employed to help craft better community guidelines and patch holes in the existing code of conduct. I want everyone to know that we’ll be taking steps to make the community free of unnecessary conflict by working towards a more active and balanced non-intrusive moderation. The #off-topic channel has now been reopened for everyone to enjoy non-PINE64 specific conversations.  

# **NewsFlash** **\[by Lukasz and Pillow\]**

Let me start by writing a few words about Star64. [Last month](https://www.pine64.org/2022/11/15/november-update-tuned-in/) I warned everyone that there is a very real possibility of delays in production of the PineBuds Pro, Ox64 and Star64. While the delays of the PineBuds Pro and Ox64 were relatively minor the delay of the Star64 may be considerably longer. To be clear, the Pine Store is still very intent on releasing the board prior to the Chinese New Year (which starts on January 22) but a firm release date isn’t known as of yet. At this point the board is undergoing an additional review process and, due to various external reasons, it is hard to predict with complete certainty when the review will be finished. I’ll update you on social media when more information is available. 

The Ox64 is now one of if not _the_ fastest selling PINE64 SBC. To be fair I don’t really remember nor have direct access to the data of other other popular SBC launches, but this is certainly a really good start with strong community interest in the device. The December batch sold out very fast but rest assured that more Ox64s are on the way and a restock is currently scheduled for January of next year, before CNY. I am looking forward to hearing people’s early impressions from the first Ox64 boards.  

The past month [Pillow](https://github.com/CounterPillow) has been busy mainlining some more SOQuartz devicetree bits. GPU, HDMI (including audio) and PCIe should work starting with kernel 6.2. Based on work [neggles](https://github.com/neggles/) has done, Pillow also mainlined the device trees for the "Blade" and "Model A" baseboards for the SOQuartz. This work should also be in kernel 6.2, which is currently in its merge window phase. wifasoi from the PINE64 chats is working on a driver for the GP7101 PWM controller that controls the fan speed on the SOQuartz Blade. Pillow is working on a set of automatically generated Debian-based live OS images for the Quartz64 range of devices including the SOQuartz. More information about these builds will be available when they're ready for public use. The goal is to provide a smooth out of the box experience for Quartz64 devices.

For the QuartzPro64's RK3588, Pillow’s work to make audio output work on it was merged for the 6.2 release cycle. The changes needed were minimal as the I2S controller hardware is mostly the same as the RK3566 one. Attempts to get USB 2.0 to work ran into weird issues with the SoC locking up when it touched the right registers at the wrong time. There's probably some power management or clock gating stuff missing from the mainline kernel at this stage, so it was put off for later. As for what other people have been doing, Collabora has been incredibly busy getting the mainline kernel into shape for RK3588. This includes basic SoC support, power regulators, and so forth. They're also working on Mali G610 GPU support both in the kernel and in upstream mesa. neggles has also written a basic mainline targeted QuartzPro64 device tree that hasn't been submitted upstream yet. As for u-boot, we're still relying on vendor u-boot and closed-source TF-A and ram init binaries there.

Some awesome initial work on Pinecil V2 Bluetooth has been showcased earlier this month by [Joric](https://www.youtube.com/watch?v=3dEI7Qim1t0). Joric’s video shows Pinecil V2 connecting via Bluetooth to a PC and projecting key stats in a browser. This is a much requested feature and one that holds a promise of much more functionality in the future. [River](https://github.com/River-b) has also [uploaded a video](https://www.youtube.com/watch?v=-2q1hxxIxI0) - of what I imagine is a newer build of the web app - which casts the temperature on a graph alongside Wattage, Voltage and even the handle’s temperature. At present this web application serves effectively as a large display for the Pinecil V2 projecting all the telemetry on a large screen, but it doesn’t allow for any control input. This, however, may be a feature in the future.

{{< youtube id="damRcWwXpbA" >}}

**Video showcasing the Pinecil V2 connected to a PC via BT - via [Joric](https://youtu.be/damRcWwXpbA)**

The newest batch of Pinecil V2 (now in production) will ship with firmware v2.20 and its numerous improvements. Aside from a fair collection of bug fixes it also includes Cold Junction Calibration which was reworked - it now takes place on each boot when the device is cold. Moreover, it also comes with a language pack, which covers most major European languages. If you already own a Pinecil V2 then this is a firmware to look forward to - you can read the complete release notes [here](https://github.com/Ralim/IronOS/releases). 

We’ll be staying on the subject of the Pinecil for just a second longer, since I want to highlight two more Pinecil-related user projects. The first of which is a highly modified Pinecil V2 - as you can tell from the attached picture, [u/malimaru](https://www.reddit.com/user/malimaru/) added two LEDs to the device - one in the front and one in the back of the transparent case. This obviously doesn’t really improve the iron’s usability - if anything, it may be quite distracting I imagine - but it sure does look pretty awesome.

![](/blog/images/Blinkblink-1024x768.jpg)

**Blink blink - [via reddit](https://www.reddit.com/r/PINE64official/comments/z489qt/customized_pinecil_v2/)  
**

The second Pinecil maker project that caught my attention is a carry case designed by a community member by going by the handle [u/Pegor](https://www.reddit.com/user/Pegor/). To date I’ve seen countless carry cases crafted for the Pinecil, many of which are 3D printed, but this particular design stood out to me from the crowd due to its elegant simplicity. Unlike many cases which aim to pack as much functionality as possible into a very confined space, this carry case is just and only that - a carry case. You can pack the iron and a tip of your choice and that's it (perhaps a cable would fit too - although I’m not sure). The lid is held in place with magnets and features a nifty PINE64 pine cone logo. I’d really like to have one to be honest - so if you have a 3D printer, some spare time and will be attending FOSDEM, then print it for me and I’ll trade you something cool in return for it. For those interested in this case, u/Pegor uploaded the STL files [here](https://thangs.com/mythangs/file/556703).  

![](/blog/images/Pinecil-cary-case.jpg)

**I really like the look of this Pinecil carry case - [via reddit](https://www.reddit.com/r/PINE64official/comments/zjeys5/pine64_pinecil_case/)  
**

DietPi now offers significantly improved support for Quartz64. The most recent release of the popular SBC OS ships with Linux 6.1.0-rc1 which features support for model-B onboard WiFI. Moreover, the build comes with mainline u-boot which resolves issues with certain types of SD cards as well as eMMC modules. An issue which caused Docker to fail to start has also been resolved - the issue was caused by missing support for a BPF cgroup. If you’re already running DietPi on your Quartz64 then this is a release well worth upgrading to; you can read the complete release notes for DietPi v8.11 [here](https://dietpi.com/docs/releases/v8_11/).  

# A look back at 2022

January saw the launch of both the [PinePhone Pro](https://www.pine64.org/2022/01/11/pinephone-pro-explorer-edition-pre-orders-open-january-11/) and the [PinePhone (Pro) keyboard case](https://www.pine64.org/2021/12/31/happy-new-year-the-keyboard-and-cases-are-here/). As far as PINE64 devices go, there haven’t been many hardware launches that drew this much attention from the press and the Linux community as that of the Pro version of our Linux smartphone and the accompanying keyboard case. I think it will go down as one of the biggest and most well-managed launches that the Pine Store and PINE64 community executed. The PinePhone Pro and the keyboard case have become very popular and, judging from community feedback and the ongoing development (see this month’s _PinePhone (Pro)_ section), these devices bring end-users and developers not only challenges but also joy of use. The PinePhone Pro will remain the flagship PINE64 mainline-based smartphone for a long time to come and I am thrilled to see so much work and development that gradually matures the software on the platform. I hope and trust that by the end of 2023 the PinePhone Pro will reach software parity with the original PinePhone.  

[March saw](https://www.pine64.org/2022/03/15/march-update-introducing-the-quartzpro64/) the introduction of the QuartzPro64 development board, the first board in our lineup to feature the RK3588 SoC. As a platform the RK3588 may prove to be an important Arm SoC for PINE64 and one that, in time, will find its way into our range of devices. At present, the decision was made to release the QuartzPro64 to developers only. The rationale behind this is to take it slow and explore the silicon and its possibilities. We wanted to get a sense of the SoC and its characteristics prior to settling on a future Pro-grade SoC; while the RK3588 may seem like a natural continuation from the RK3399 nothing is written in stone as of today. We’ll keep working on and with the RK3588 while keeping our options open.     

As I stated at the [end of last year](https://www.pine64.org/2021/12/15/december-update-a-year-in-review/), we wanted to make 2022 all about smaller and perhaps less ambitious undertakings than phones and laptops. As exciting as such flagship devices are, their development is a major undertaking, which in turn requires time, resources and complete commitment to this particular hardware. A major hardware project is, in a sense, all-consuming and frequently dominates the direction of the project for months or even an entire year. Therefore 2022 was meant as a way for us to reset our headspace and explore other fun side projects that have been shelved for some time. One such project are the PineBuds Pro, which were introduced as a part of this year’s April fools joke. The buds landed earlier this month and we hope to see much development around them in the coming months - as I mentioned in November we’re waiting for Ben (Ralim) to release his Linux firmware flashing tool. The PineBuds Pro holds the promise of a device similar to that of the PineTime and Pinecil - something that anyone can pick up and use while also providing tinkerers and developers with an open playground. 

In [July we launched the Pinecil V2](https://www.pine64.org/2022/07/28/july-update-a-pinecil-evolved/). In the spirit of ‘if it ain’t broke don’t fix it’ the Pinecil V2 is an iterative improvement over the original. The new silicon brings with it Bluetooth connectivity and improves the soldering iron’s performance, which has landed it the top spot on [Tom’s Hardware best soldering iron list](https://www.tomshardware.com/best-picks/best-soldering-irons). With recent developments enabling Pinecil’s connectivity (read the _Newsflash_ section if you haven’t done so yet), I can see the iron becoming an even better device than it already is. Pinecil’s success is also enticing us to probe what other maker devices we could create or make better versions of. I think there are many possibilities in this regard, but I’m genuinely interested in what device in the vein of the Pinecil you’d like to see us make; leave a comment under this blog - I’ll read it, I promise. 

[August](https://www.pine64.org/2022/08/28/august-update-risc-and-reward/) and [October](https://www.pine64.org/2022/10/15/october-update-an-ox-no-bull/) saw the introduction of the Star64 and Ox64 respectively - our first RISC-V Linux-capable boards. While these are our first RISC-V SBCs they certainly aren’t our last; to the contrary, they are just the beginning of a much bigger trend within the PINE64 project. I’ll write more about this in the _2023 sneak peek_ section of this update. As I already mentioned, the Star64 has been delayed due to a review process and is due to launch sometime in the coming weeks, but the Ox64 has been out for a few weeks now and has been met with much positivity. Indeed, the Ox64 is probably one of the fastest selling items in the Pine Store to date. This shows both an interest in RISC-V architecture and a need for inexpensive boards such as the Ox64 on the market. The SoCs powering the Star64 and Ox64 hold much potential and I would count on seeing them utilized in future PINE64 devices. 

As a whole, this year was dedicated to exploring and setting a course for the future. Within the PINE64 project’s structure SBCs and devices are a part of a larger whole and tightly intertwined. SBCs often act as the means for a selected SoCs initial bring up, making it accessible to the development community, to be later transformed into a development platform for future PINE64 devices. To be more precise, ideas for devices such as Pinebooks and PinePhones emerge once a SoC shows promise and core software support becomes firmly established. I think that we now have a handful of very interesting SoCs on our hands - the RK3566 and JH7110 in particular. The coming year will see much development of these platforms and I foresee great things built upon these two SoCs - the PineTab2 being one of them. 

# 2023 sneak peek

As I wrote at the end of last year, and as it should be evident from what I wrote in the previous section, we’re very interested in the RISC-V architecture. As such, the much anticipated Ox64 and Star64 are merely early manifestations of our overarching plan for years to come. I should at the same time reiterate what I wrote in December of last year; while we have a strong will to explore, innovate and drive the RISC-V hardware space, this doesn’t mean we’re saying farewell to Arm as a platform. All it means is that you can expect us paying more attention to RISC-V this coming year and in the years to follow. As we see it RISC-V holds a huge promise for the community and for the Pine Store as a hardware manufacturer - a win-win situation. We believe that a few years down the line RISC-V will be able to offer more versatility and raw power at a lower price-point than Arm counterparts. It is also likely to benefit from fewer manufacturing restrictions and a higher degree of general configuration options. 

But that’s the future. As things stand, Linux and other FOSS systems have much catching up to do on RISC-V. I recently spoke to an authority (who doesn’t wish to be named) in the field of benchmarking and Arm SoCs in more general. Said person benchmarked a Star64 against the Quartz64, which resulted in the Quartz64 scoring much higher than one would expect against the Star64 (approx 30% better or so). During our email exchange I was told that while the Star64’s CPU may indeed be slightly slower than the Quartz64 in certain computational tasks, the benchmarked gap in performance is due to Linux’s software (im)maturity on RISC-V and not the hardware per se. If anything, this acts as an incentive to us. To develop FOSS OSes on RISC-V we'll need inexpensive, well built and popular devices with an established community base. This means that some existing PINE64 Arm hardware will see RISC-V counterparts in the future. Indeed, future Arm devices will also, at least in some instances, be released alongside RISC-V counterparts moving forward.  

For now our plans concern non-Pro devices, in part because no Pro-grade RISC-V chip has been settled on yet. Before you get too excited - no, there are no plans for a RISC-V PinePhone at this time. We do, however, have some very exciting news in the pipeline that we’ll be sharing with you in a few weeks time. But as I already mentioned, we’re not in a rush. To the contrary, the primary goal at this point is to make sure that our first entry into the RISC-V device space is a solid offering. We’re working on something that developers and the core community will appreciate. If you happen to be at FOSDEM then make sure to stop by and say hi - we’ll show you what we’re working on and your socks will be blown off. 

# PineTab2

Before we get to discussing the new PineTab2 let me first explain what happened to its predecessor. The original PineTab was conceived alongside the PinePhone in early 2018 at a small pub in Brussels, and a little less than 2 years later the PinPhone and PineTab became available for order. At that time a global pandemic was something that could only be experienced through the medium of film. I think it is fair to say that none of us could have truly imagined what a global pandemic would entail for the entire world, let alone understood the consequences it would have for hardware production, electronics supply chains and global economics. There is no need for me to recap how the pandemic unfolded, what effect it had on production in mainland China or explain the hardships businesses had to endure as a consequence of this, but suffice to say that the original PineTab was a victim of COVID and its fallout. For those interested in the details, I encourage you to browse the blog’s [PineTab tag](https://www.pine64.org/tag/pinetab/)– I did my best to keep the community updated on the original device’s status throughout 2020-2021. In all fairness I should also make it clear that PineTab’s death was, in some part, a choice on our part as decisions were made to allocate resources to secure PinePhone’s availability throughout late 2020 and early 2021.

![](/blog/images/pPineTab2-pcb-1024x768.jpg)

**A look at PineTab2's PCB**

By the time production of the PineTab became viable again we felt that the original design could and indeed should be improved on. By late 2021 there was also a great candidate SoC for a second generation PineTab – the RK3566. I have written extensively about the RK3566 in recent months in the [context of the Quartz64](https://www.pine64.org/category/quartz64/), but in a nutshell, it is a modern mid-range quad-core Cortex-A55 processor that integrates a Mali-G52 MP2 GPU and supports up-to 8GB of RAM. It is a dream-of-a-soc for small form-factor devices with space-constrained chassis since it runs cool, offers a wide variety of modern and fast IO, has a solid price-to-performance ratio and is genuinely future-proof. The one thing that the SoC didn’t have for a time was mature Linux support – but this is no longer the case (see _Newsflash_ section). Software development for the RK3566 platform is booming and Linux has now reached a high level of maturity with both mainline and BSP Linux supporting nearly all core functionality of the chipset. I feel it is fair to say that it is now a prime candidate for porting mobile OSes to.

![](/blog/images/PineTab2-case-back-off-1024x768.jpg)

**PineTab2 prototype with metal back removed**

But the PineTab2 is much more than a spec-bumped version of the original (more on the specs later) – it is a complete physical redesign: you’re getting a metal chassis that is very sturdy while also being easy to disassemble for upgrades, maintenance and repair. Taking the PineTab2 apart is as simple as undoing a set of snap-tabs and removing the metal back chassis. As is the case with the Pinebook Pro, the PinePhone and the PinePhone Pro, we’ll be offering replacement parts for the PineTab2 down the road. To make the device end-user serviceable we’ve made the PineTab2’s guts modular. This extends to the tiniest of parts, including the eMMC which sits on its own little PCB, like on the Pinebook Pro or our SBCs. Indeed, most parts are easy to reach and replace in a matter of minutes – the camera modules, the daughter-board, the battery and USB keyboard connector can all be replaced in under 5 minutes. I’d also like to mention that the LCD can be replaced without any specialist tools, although it will require a bit more time and effort. If you are a Pinebook Pro owner and have ever taken it apart out of curiosity or for repair, then you’ll feel right at home with the PineTab2. Speaking of the display panel, we’re still evaluating our options, but it will feature a tempered glass 10’1 IPS screen with modern and reasonably thin bezels.

![](/blog/images/PT2-2-1024x1024.jpg) ![](/blog/images/PT2-1024x1024.jpg)

**It is looking pretty good, isn't it?**

Let’s talk about IO, components and connectivity. The PineTab2 has two USB-C ports, one of which is USB 3.0 and the other is intended for charging. The latter port features USB 2.0 speeds when it isn’t used for juicing up the PineTab2. There is also a dedicated micro HDMI port for video output and two cameras on the V2 – a front facing 2MPx camera and a rear facing 5MPx one. We haven’t settled on a WiFi/ Bluetooth module yet but two are being tested right now - I’ll let you know which one fared better in testing and was chosen for production. PCIe is exposed on the PCB but I wouldn’t expect most NVMe SSDs to fit inside the chassis. However other peripherals may fit the 9mm-thick envelope of the PineTab2. This won’t be an advertised feature – consider it a nod to hackers who may be able to make use of it. A micro SD slot and an audio jack port are also present and can be found on the leading edges of the chassis. The current prototype has been fitted with a 6000mAh battery but this may change in the future. Indeed, I should make it clear that we’re still at a prototyping phase and all spec’s I’ve listed above may change before the PineTab2 finds its way into the Pine Store.

One of the things that the original PineTab had people excited about was its keyboard, which doubled up as a protective carry cover. We know that a detachable keyboard is a feature most of you want, so it is making a return with the introduction of the V2. And yes, we’re making sure that it will double-up as a protective case too. Unlike the original, all SKU variants of the PineTab2 will include the keyboard by default. Including the keyboard by default opens up the possibility of running convergent and dedicated desktop OSes – and I know a subset of the community always prefers to use a traditional desktop UI over a mobile counterpart. It is a bit early to discuss the specifics of the keyboard at this time – as we’re still exploring what is possible and feasible – but we’ll do our best to meet, and hopefully exceed, the original PineTab keyboard’s design. What it will have, however, is the same chipset as the Pinebook Pro, which means that it will be flashable with open firmware. It also features a backlight and the vendor has worked with us to reduce the reference keyboard’s weight and make it slimmer; this was achieved by using fiberglass panels.

On launch day there will be two **PineTab2 variants available – with 8GB RAM / 128GB flash and 4GB RAM / 64GB flash storage**. We’re currently hoping to bring the PineTab2 to the market sometime after the Chinese New Year, but it is too early to offer a firm date yet. A price point for either of the variants hasn’t been settled on yet either but I can promise that it will be affordable regardless of which version you’ll settle on. Developer units have just come in the other day and will be distributing them in December and January. I hope that you’re as excited about the PineTab2 as I am and you too are looking forward to seeing the PineTab vision realized in its full potential. Those of you who will be attending FOSDEM early next year - make sure to come and see us to check out the prototypes. 

# PinePhone (Pro) \[By Thanos\]

In the past month, SailfishOS on the Pinephone and Pinephone Pro have improved significantly, and the operating system is actually getting very close to being in a daily-driver ready state on the original Pinephone. Affecting both devices are some backend improvements made in the driver for the Pinephone modem, which should significantly reduce issues with the modem not working properly after the device wakes up from deep sleep. This improvement has been merged into the Megi kernel, so it will apply to all distros for the Pinephone that use it. Both the Pinephone and Pinephone Pro ports of SailfishOS have been updated to the latest 6.0 version of Megi’s kernel. Sailfish has the device able to wake from deep sleep on an incoming call, however the driver still has an issue preventing the call from being received. This is being worked on, and is the last major barrier from SailfishOS working extremely well on the original pinephone.

{{< youtube id="dvA1nL9pt3w" >}}

**Keyboard working with SailfishOS - video via [Adam Pigg on Twitter](https://twitter.com/adampigg/status/1595361551501885441)**

As for the Pinephone Pro, all sensors are now working properly under Sailfish. An audio configuration is in progress, but not ready yet. The SailfishOS team does believe that the pinephone pro has potential to work extremely well with SailfishOS, but the port is not quite ready yet. Overall, the SailfishOS team has made some incredible progress, meaning we have another solid option for a potential daily driver OS for people wishing to make the switch to mobile linux. The SailfishOS project is looking for contributors right now, so check them out at [https://github.com/sailfish-on-dontbeevil/](https://github.com/sailfish-on-dontbeevil/), or in the SailfishOS porting groups on matrix and telegram.

**\[edit\]** Since the publication there have been further developments on the SailfishOS port. SailfishOS and ofono now work much better form suspend, and could be used as a reliable phone. Both call and sms are handled from deep sleep with work  done over the last week. Check out [Adam's post on Twitter](https://twitter.com/adampigg/status/1603132663220797440).

Megi has a new version of his Pinephone and Pinephone pro kernel coming soon, and there are some major improvements coming. The camera support patch for the original Pinephone was completely rewritten for the latest version of the CSI driver from mainline. A bug where sometimes the power button would appear to still be held down when waking up from deep sleep has been patched. The DRM driver was improved on the original Pinephone. The Pinephone Pro’s display driver has also been patched to support a full 60hz refresh rate instead of the 53 it was getting before.

There is some important information regarding the Pinephone keyboard accessory. For good news, the power management driver for the keyboard has been merged into the kernel and should work a lot better now. The improvements made should result in much better battery life as a result of it using an algorithm optimized for maximum efficiency using strategies that minimize charging of the pinephone’s internal battery. For the bad news, a firmware bug has been discovered on the Pinephone keyboard that causes it to draw more than twice the expected amount of power while in standby. This means that it can fully undercharge your Pinephone’s battery in about 3 weeks if left unattended. As a result of this issue, it is highly recommended that you store the phone and keyboard detached from each other if you do not plan on using the device for more than a week.

![](/blog/images/NetHunterPro-1024x771.jpg)

**Kali Nethunter Pro on the PinePhone Pro - via [Hackerfantastic on Twitter](https://twitter.com/hackerfantastic/status/1601251537388392450)**

Lastly Kali Linux released a custom build of their offsec distribution which officially supports the PinePhone and PinePhone Pro. This mobile-friendly version of Kali Linux is called Nethunter Pro - a bare metal installation of Kali Linux with Phosh desktop environment optimized for small-screen devices. As with any other PinePhone OS, you can boot it from a SD card to dual boot Kali alongside the main OS on the phone’s internal flash. This is obviously very useful in this particular case because Kali is a purpose built OS that isn’t meant to be your daily driver. That said, for those who only wish to use their PinePhone (Pro) for this one purpose, Kali Linux announced that they will soon release an alternative version with Plasma Mobile as well as installers allowing installation of Kali NetHunter Pro onto the internal flash memory. It is awesome to see non-mobile-Linux specific projects picking up the PinePhone and PinePhone Pro and using the devices in really exciting ways. You can download Kali NetHunter Pro [here](https://www.kali.org/get-kali/#kali-mobile).  

That's all for this month, I’ll catch you all in January.
