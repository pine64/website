---
title: "November Update: KDE PinePhone CE And A Peek Into The Future"
date: "2020-11-15"
authors: ["Lukasz Erecinski"]
categories:
  - "community"
  - "cube"
  - "news"
  - "pinebook-pro"
  - "pinecil"
  - "pinephone"
  - "pinetab"
  - "pinetime"
  - "soedge"
tags: 
  - "kde"
  - "pinebook-pro"
  - "pinecube"
  - "pinephone"
  - "pinetime"
  - "rk3566"
  - "soedge"
cover: 
  image: "KDECommunityEdition.png"
images:
  - "/blog/images/KDECommunityEdition.png"
---

![](/blog/images/KDECommunityEdition.png)

Welcome to this month's community update! We’ve got exciting news to share, but before I proceed in doing so I’d like to thank Gamiee, JF, and PizzaLovingNerd for contributing to this blog entry and Clover for the final edits and proof-reading. As the PINE64 device-family grows larger and becomes more diverse, I find myself more reliant than ever on other people's insight and expertise when writing up these updates. To this end, I’d very much like to thank the aforementioned community members and, at the same time, invite others to take part in shaping future updates. If you’ve got something you would like to contribute to an upcoming community update, then please reach out to me in the chats. 

In this update we’re happy to announce the next Community Edition of the PinePhone, which will ship with KDE Plasma Mobile. We will also take a look at the Pinebook Pro dock and talk a bit about future hardware. 

For those of you who are averse to reading long blog entries or simply prefer receiving news in an audio-video format, then you’ll be glad to know that we now have a complimentary video edition of the monthly community update. **It can also be watched  [on LBRY](https://lbry.tv/@PINE64:a) if Youtube isn’t your thing.**

https://www.youtube.com/watch?v=4su-YdjTYtY&feature=youtu.be

**Video synopsis of the November Community Update**

**TL;DR for this month's update:**

- We’ve donated to postmarketOS; thank you to those who supported the pmOS CE!
- Sub-forums and Wiki entries for PineCube and SOEdge are now up
- Problems with chat protocol bridge to be addressed soon(TM)
- Notice re. Small number of Manjaro PinePhones with postmarketOS -sorry! 
- Nutcracker Challenge - working towards a blob-free WiFi and BT. Get your PineCone EVB now
- Let’s talk about the future; sneak peak at RK3566 SBCs in early 2021
- **Thrilled to announce PinePhone KDE Community Edition!**
- **PinePhone KDE CE pre-orders start December 1st.** 2GB RAM/ 16GB eMMC and 3GB RAM/ 32GB eMMC + USB-C dock (Convergence Package) will be available. 
- PinePhone 3GB RAM/ 32GB eMMC mainboards now available in the Pine Store; early adopters get a major discount
- PInePhone Qi wireless charging back case taking shape - available nearly next year
- Megi’s PinePhone kernel improvements are a big deal; we’re getting closer and closer to daily-driver readiness
- PinePhone convergence working well now
- Pinebook Pro ‘Docking Deck’ USB-C dock available later this month for $39.99
- Armbian on the Pinebook Pro is great; if you’re in need of Ubuntu on the PBP, then give it a spin - highly recommended 
- FydeOS for Pinebook Pro is a ChromiumOS fork capable of running Android and Linux applications; coming soon!
- PineTime InfiniTime updated to 0.9.0; fixes a major bug and brings new music player
- PineTime firmware can now be upgraded via Gadgetbridge! 
- PineTime reloader tool to switch bootloaders, and firmware, in the works
- Pinecil entered production and will be available later this month or late the next; a look at the packaging and extra tips
- PineCube running Debian and NixOS; software progress is coming along well 
- PineCube subforum, chat and Wiki now available - join in and contribute
- SOEdge will be available for “Developers only” to start with
- SOEdge Wiki and subforum is now live

##### Housekeeping

We have now made a donation to the postmarketOS team for their work on the Community Edition of the PinePhone. We firmly believe and trust that this sizable donation will be put to good use and benefit all Linux on mobile development to come. Working with the postmarketOS team has been nothing short of great and since their phones shipped we’ve seen significant improvements to the software. I’d like to once again thank those of you who chose to support them by purchasing a postmarketOS PinePhone.

In other community news, there are now PineCube and SOEDge sub-forums on the PINE64 forum. Both devices, which I’ll write about later in this month’s update, will benefit strongly from community engagement early on. A PineCube chat is also available on our Discord server, and will eventually end up bridged up to other protocols. On a similar note, the Nutcracker challenge which began this month has now also found its way onto our Discord and will, in all likelihood, also be bridged to other protocols. We’ll soon also be adding sub-forums and chats for the SOEdge and Pinecil - you can expect them to be available to the community sometime later this year, perhaps even this month. 

On the subject of chats, I’d quickly like to touch upon the situation with the chat-protocol bridge. For those who aren’t in the know, we currently have multiple chat protocols bridged with many thousands of users relying on it for cooperation, knowledge dissemination and software support. In recent months we’ve started to experience issues, which subsequently led to IRC being disconnected from current chat infrastructure. We have also experienced a significant increase in response delays across the bridge - likely due to the high volume of messages and people participating. In result, the entire bridge will have to be reworked in the coming months - as early as this month or as late as early January. This will obviously cause a disruption to chat communications for a day or two, so consider this a heads-up; a notice will be issued when work on the chats begins.  

In other community news, I am happy to report that the shipping progress for the Manjaro Community Edition PinePhones is proceeding well without any major hiccups. Indeed, Manjaro CE started shipping earlier than we anticipated, with thousands of people having already received their devices. For those of you still waiting for your unit to arrive, I encourage you to follow the [shipping thread](https://forum.pine64.org/showthread.php?tid=11959) over on our forum; we still expect to have a handful of shipping updates for the Manjaro CE between now and mid-December.  

Lastly, a few days ago it has come to our attention that a number of Manjaro CE PinePhones have shipped with postmarketOS preinstalled. Following a brief investigation, it turned out that one out of 100 SD cards used for testing and subsequent flashing at the factory did, indeed, contain the postmarketOS image. If you Manjaro CE shipped with postmarketOS, then please see this [blog post](https://forum.pine64.org/showthread.php?tid=12078) and please accept our apologies for this situation.

##### Nutcracker Challenge \[by** [**Marek “Gamiee” Kraus**](https://twitter.com/gamelaster)**\] 

![](/blog/images/DSC0018_01.jpg)

**The PineCone - by [Martijn Braam](https://twitter.com/braam_martijn)**

As many of you have probably already heard, we recently launched the _Nutcracker Challenge_ - a reverse-engineering effort of WiFi and Bluetooth on the BL602 chip with a RISC-V core. The intention of the effort is to eventually have a 100% open-source WiFi and Bluetooth chip for PINE64 devices including current and future single board computers, smartphones, tablets and laptops. This is an important project for us and one which we believe will directly benefit not only our user base but also others who care about privacy. 

Following the announcement of the Challenge we immediately received a lot of attention, and at the time of writing this article we have received 86 pull requests, out of which 49 have already been merged. All this effort was made by 37 contributors who will be rewarded with a free PineCone Evaluation Board for their work. The first very small batch of PineCone Evaluation Boards - or EVBs - has been already shipped, and the second batch is being manufactured. We expect to ship a total of 1000 PineCone EVBs over the duration of the challenge.  

Despite developers and contributors not having access to the hardware, they made great progress on analyzing the blobs, improving documentation or fixing bugs in the SDK. We are also happy that the company which designed the chip - Bouffalo - have promised more documentation and low-level code, which they already provided to us alongside an improved datasheet and reference manual. There is still much to do and a long road ahead of us, but we expect to see a tremendous contribution boost once the hardware reaches its new owners. For all of you interested in participating in the _Nutcracker Challenge_, I invite you to read about how you can [contribute and receive a free PineCone EVB](https://www.pine64.org/2020/10/28/nutcracker-challenge-blob-free-wifi-ble/). 

##### Let's talk about the future \[Part 1 of many to come\] 

Next month’s update will include a full review of the year 2020; we will look back at how far we’ve come since December 2019. Today, I will give you a sneak-peak at the future and what’s to come. Before I proceed, I’d like to make it clear: what I am about to share with you is just a small portion of our strategy for the months to come. Consider this the first of many steps which we will begin taking in the next 6-to-12 months to further PINE64’s cause. With that out of the way, let me introduce you to the next SoC to enter the PINE64 lineup at one point early next year, the RK3566. 

![](/blog/images/Screenshot_20201112_234559.png)

**Rockchip RK3566**

You can think of the RK3566 in terms of a spiritual successor to the RK3328 currently used in the ROCK64 single board computer - our most popular device to date, at least in terms of units sold. It is, however, not only more powerful than the RK3328, but also considerably more flexible in terms of potential use-cases and implementations. Featuring four fast A55 cores running at 2.0 GHz, a modern G52 GPU, fast I/O (including PCIe, USB3.0, GbE and SATA) and up-to 8GB of \[LP\]DDR4 RAM, it is our choice for NON-Pro PINE64 devices to come.  

Next year you will see us introduce two single board computers based on the RK3566 - they will be available in two configurations, more specifically in the model ‘A’ and the model ‘B’ form-factor. For those that do not know, ‘A’ -sized PINE64 SBCs are larger in size, sharing the ROCKPro64’s and PINE A64-LTS footprint, while the ‘B’ form-factor SBCs are smaller, such as the ROCK64 or PINE H64. It is noteworthy that the new generation SBCs will be a part of a new line of devices, and hence not share the ‘ROCK’ naming scheme of current Rockchip boards. More on this later. 

We envision the two boards to serve somewhat different purposes within the PINE64 eco-system. The ‘B’ board will be just that, a stand-alone single board computer, while the ‘A’-sized board may offer the opportunity to be used as a development platform for future non-pro devices due to all of the SoC’s I/O being exposed on the larger PCBA. Both the ‘A’ and ‘B’ form-factor RK3566 single board computers will, of course, be software compatible so you may choose either for your new project. As a fun fact I’ll add that the SoC has a dedicated e-ink protocol - so the possibility for creating the most outrageously overpowered e-reader is now upon us.

Finishing this section off, I’d like to make you aware that it will be a long time before the future RK3566-based SBCs will be useful to regular end-users or serve as a basis for next-gen PINE64 devices. Mainlining, patching, as well as exposing all interfaces (making them functional) in the Linux kernel takes time and a lot of work. In other words, don’t expect the A64 and RK3328 - both of which are well supported in Linux - to be phased out anytime soon. Indeed, I expect that this will be a long transition period, but at the same time I am excited to announce this new beginning.  

Later this month I'll release a riddle pertaining to the naming of this PINE64 product-line. The person to crack the riddle first will receive one of the first boards from the production line.

##### PinePhone

We are thrilled to announce that we’re teaming up with KDE to bring you the next _community edition (CE)_ of the PinePhone. We have a long-standing friendship with the KDE Community, going all the way back to the original Pinebook which shipped with KDE Neon as it’s default operating system. For more than a year now, the Pinebook Pro, which features Manjaro with KDE Plasma desktop, has been receiving widespread acclaim from the media and end-users alike. It is also because of this close relationship that the KDE team were among the very first we approached when envisioning the PinePhone. Fun Fact: during the initial conceptual stages of the PinePhone’s development, KDE were also the ones to [accidentally leak](https://itsfoss.com/pinebook-kde-smartphone/) that the PinePhone was in the works!)

![FinalKDEFront2](/blog/images/FinalKDEFront2.png "FinalKDEFront2")

**KDE Plasma Mobile on the PinePhone**

For the past year now, Plasma Mobile (which, for those who don’t know, is KDE’s mobile user interface) has made major strides and achieved a new level of polish. I believe that this is, at least in part, thanks to the broad adoption of the PinePhone as the default Linux-on-mobile development platform. Just in a [recent blog post](https://www.plasma-mobile.org/2020/11/12/plasma-mobile-update-october.html) on Plasma Mobile’s website, the development team mentioned major improvements to the overall user experience, ranging from significant shell and lockscreen improvements, to improved support for vital mobile apps. I strongly encourage you to read the linked blog post to learn more. 

We currently plan to have pre-orders for the **KDE CE to go live on December 1, 2020** - you can expect an announcement blog post once the phones become available. I also encourage you to subscribe to this blog, follow us on [Twitter](https://twitter.com/thepine64) and join the [PINE64 Telegram News Channel](https://t.co/0O6pZHnFRm?amp=1) so you do not miss the news. The PinePhone itself will be available in the same two HW configurations as the previous two editions: 

**$149** - 2GB RAM + 16GB eMMC

**$199** - 3GB RAM + 32GB eMMC Convergence Package with an included USB-C dock

Please head over to [**KDE's website and read the announcement**](https://kde.org/announcements/pinephone-plasma-mobile-edition/) to learn more about what the team got in store for this community edition of the PinePhone.

![](/blog/images/mainboards.jpg)

**3GB RAM / 32GB eMMC Flash PinePhone Mainboards**

We’re happy to let you know that stand-alone 3GB RAM / 32GB eMMC flash mainboards are now [available for purchase](https://pine64.com/product-category/smarphone-spare-parts/?v=0446c16e2e66) from the Pine Store. We made the decision to sell the mainboards at a significant discount to BraveHeart and UBPorts CE owners who wish to upgrade the device. Consider it a ‘thank you’ for being early adopters; we really appreciate you supporting us in our quest to bring Linux on mobile to a wider audience. For those who wish to learn more about this newest revision of the PinePhone mainboard, I point you to the [schematic](https://files.pine64.org/doc/PinePhone/PinePhone%20v1.2b%20Released%20Schematic.pdf) for details (no major change from 1.2a). 

Last on the PinePhone hardware discussion list for this month is the Qi wireless charging caseback for the PinePhone. The wireless charging back case is soon to enter production and we expect it to be available early next year. The Qi wireless implementation we’re using is pretty cutting edge; it incorporates all components, including the copper coil on the actual PCB itself - which, in turn, is incorporated into the back case. It is over my head, so I am including an engineering picture for you to take a look at.

![](/blog/images/photo_2020-11-13_13-48-44.jpg)

**Qi wireless charging coil and PCB for the PinePhone to be embedded in custom back case**

Software-wise, the last month has seen some of the most impressive improvements in months. [Ondrej (Megi) Jirman](https://xnux.eu/log/) has made substantial progress on his kernel and usability patches, which have now become adopted by the majority of PinePhone operating systems. Among other refinements and enhancements made, the PinePhone display now runs at 60Hz - 1/3x faster than before, resulting in an all-around much snappier experience. This is particularly noticeable when typing or otherwise interacting with the touchscreen. I consider this a major boon from an usability standpoint. 

{{< youtube id="5fqZRVb4V_s" >}}

**KDE Plasma Mobile with Megi's patches ~ via KDE and Manjaro dev teams**

Moreover, docking the PinePhone for desktop convergence - in OSes that support this feature and use the new kernel and relevant patches - now works like a charm. I’ve tested Manjaro with Phosh and Plasma Mobile, and both worked well in the docked mode. Docking the phone for a convergence experience now also works with just about any TV or display, and the phone will even output to a 4K@30FPS monitor (although, the convergence feature is not usable at this resolution). To be clear, when I say that ‘it works’ I mean that all of the dock’s features now work well, including power input, HDMI out, USB ports and the Ethernet connection. I found that I can genuinely be quite productive whilst using the PinePhone in this configuration - case in point, I am writing this section of the update on a docked PinePhone. But productivity obviously is just a portion of the potential - you can have some fun with this feature too, check out the video below.

{{< youtube id="Xy0WLAPMxrE" >}}

**Docking your phone can be used for so much more than productivity!**

Lastly, I also found that the PinePhone now resumes faster from suspend on incoming calls, and that the Bluetooth adapter functions reliably. Both of these features, while relatively minor when compared to the major strides made in the past month, are actually very significant in terms of making the PinePhone viable as a daily driver. This, combined with the much improved voice call audio quality in the newest kernel, means that my SIM card now resides exclusively in the PinePhone, while I keep my Android phone for auxiliary tasks. We’ve come a long way since January 2020 and at this pace I feel the PinePhone may become a viable daily driver for many users early next year - I truly believe this.

##### Pinebook Pro

I have some good Pinebook Pro hardware and software news to share with you this month. Let’s begin with hardware; the Pinebook Pro USB-C dock, which we have christened “_The Docking Deck_”, has now entered production and ought to be available in the Pine Store in a week’s time. It will be coming in at a price of $39.99. I’d like to thank ayufan for making The Docking Deck work with the mainline Linux kernel with patches - without his work we likely would have not decided to proceed with making the deck. The default Manjaro OS build that ships with the PBP will be updated to support The Docking Deck out-of-the-box in the future. 

![](/blog/images/photo_2020-10-27_16-32-11.jpg)

**Picture of Docking Deck from factory**

The deck features a wide array of I/O including: 1) a full sized SD card slot; 2) a mSD slot; 3) 2x USB-C ports; 4) 3x USB 3.0 ports; 5) a Gigabit Ethernet port; 6) VGA out socket; 7) as well as HDMI out. It uses USB-C for power and is capable of accommodating high Wattage power supply units capable of delivering power to the Pinebook Pro as well as all peripherals attached to The Docking Deck. The picture below shows the exact layout of the entire I/O. Mind you, the picture below is of a prototype sample we received from the factory; the final production version will be perfectly color matched the Pinebook Pro and even share a near identical metal feel of the laptop’s shell. There will be a small laser etched PINE64 logo at the bottom of the deck, alongside the required certification.

![](/blog/images/dockingdeck.jpg)

**A closer look at the Docking Deck's I/O - Picture of Prototype**

Software wise, there are two things I’d like to write about this month, the most recent Armbian build and FydeOS for the Pinebook Pro. Armbian now offers a well supported [Ubuntu Focal OS image for the Pinebook Pro,](https://redirect.armbian.com/pinebook-pro/Focal_current_desktop) based on a mainline kernel with patches and FOSS GPU drivers. I’ve recently spent some time with this operating system and I am happy to report that it is a phenomenal option for all those who want to run Ubuntu on their Pinebook Pro. Armbian is snappy, responsive and has a good selection of software to get you going. I had no issues with watching 1080p video content locally, playing retro games in retroarch or browsing the internet. 

If you’re not a fan of Manjaro and have a strong preference for Ubuntu over Debian, then I highly recommend this build - it's very good.     

![](/blog/images/FydeOS.jpg)

**FydeOS on the Pinebook Pro**

The other operating system I’ve been trying out on my Pinebook Pro is [FydeOS](https://github.com/FydeOS) - a ChromiumOS fork capable of running Linux and Android apps. I found the operating system to be very snappy and capable. Playing back Youtube movies, even at a 1440p, was a perfectly smooth experience and Android apps - including some popular games - ran exceedingly well. I am not suggesting it instead of Linux or BSD, but if you or your kids need a Chromebook then this OS may just be worthwhile looking into. I am presently not certain as to when a build will be publicly available, but the beta I had the privilege of trying out was already really polished, so I expect we’ll hear more news from the FydeOS development team soon. Stay tuned! 

##### PineTime \[by** [**JF**](https://twitter.com/codingfield)**\] 

These last few weeks, the InfiniTime project received a lot of feedback from users (in [Github](https://github.com/JF002/Pinetime/issues), Twitter and in the chat) and [contributions](https://github.com/JF002/Pinetime/pulls) from fellow developers. It's really amazing to see that people are actually using InfiniTime and even devoting their time to working on improving it!

[InfiniTime version 0.9.0](https://github.com/JF002/Pinetime/releases/tag/0.9.0) was released a few days ago. The new firmware version fixes some annoying bugs, including one that prevented the bootloader from running correctly after a reset. This bug would temporarily brick the device, and some people had to wait for the battery to drain completely before being able to get PineTime up and running again. It's not something I like to tell to the users, so I'm glad we've been able to identify the underlying cause of the bug and fix it.

Version 0.9 also brings a new Music app. This app allows you to control the music playback on your phone (play, pause, volume up and down,...). [Avamander](https://github.com/Avamander) improved the previous version of the app with a new UI with a nice animation, and even added new information on the display like the song progression. This app still works nicely with Gadgetbridge and Amazfish!

![](/blog/images/music1.jpg)

**Music app on the PineTime connected to Android smartphone**

Speaking of [Gadgetbridge](https://gadgetbridge.org/) - an Android companion app - has seen a release of version 0.48.0 just a few days after last month’s community update. With this version of the app, you can use InfiniTime to upgrade your PineTime over-the-air (OTA) from Gadgetbridge. To my knowledge, Gadgetbridge is the first open source companion app to provide this functionality!

![](/blog/images/ota1.jpg)

**PineTime OTA firmware update via Gadgetbridge** 

Another piece of great news in the PineTime ecosystem is that [Piggz](https://github.com/piggz) is working on porting [Amazfish](https://openrepos.net/content/piggz/amazfish) to Linux desktop. Amazfish is a companion app for several smartwatches and fitness trackers. It runs on SailfishOS and already supports InfiniTime.  Amazfish should eventually be easily portable to multiple Linux distros and UIs (like plasma-mobile and UBPorts), and run on many devices like the PinePhone and the PinebookPro!

Now, what's next? I'm working with Daniel from [wasp-os](https://wasp-os.readthedocs.io) on a tool that upgrades/switches the bootloader of the PineTime. The bootloader is a critical piece of code that initialises the device and starts the firmware. It can also provide interesting functionalities like firmware upgrade and OTA. Since the beginning of the PineTime project 2 bootloaders have coexisted - the one based on the NRF Softdevice (NRF is the manufacturer of the microcontroller at the heart of the PineTime, the NRF52832) and the one based on [MCUBoot](https://github.com/mcu-tools/mcuboot), mainly written by \[Lup Yuen Lee\](https://twitter.com/MisterTechBlog). Both bootloaders have their characteristics, their functionalities, pros and cons, and they are not compatible with each other. You cannot install a firmware built around the NRF SoftDevice on a PineTime running the MCUBoot bootloader, and vice-versa. [Wasp-os](https://wasp-os.readthedocs.io) and [ATCWatch](https://github.com/atc1441/ATCwatch) are running on the NRF bootloader while [InfiniTime](https://github.com/JF002/Pinetime), [Klok](https://gitlab.com/caspermeijn/klok), and [Hypnos](https://github.com/endian-albin/pinetime-hypnos) use the MCUBoot one.

This [reloader](https://github.com/daniel-thompson/wasp-reloader) tool Daniel and I are working on (and honestly, Daniel is doing most of the work :)) will allow users not only to upgrade the bootloader they are using, but also to switch from NRF to MCUBoot and from MCUBoot to NRF. This will give more choices to the users and allow both communities to work together, which is, in my opinion, a really great thing.

Daniel shot a video that demonstrates a complete OTA roundtrip (wasp-os -> InfiniTime -> wasp-os) that will give you a better understanding on the subject!

{{< youtube id="lPasAt1LJmo" >}}

**Installing Wasp-OS from InfiniTime ~ by Daniel Thompson**

For those who don't know it yet, [wasp-os](https://wasp-os.readthedocs.io) is a "_MicroPython based development environment for smart watches_". It provides many Python applications such as a clock, stopwatch, step counter and heart rate monitor. Anyone interested in extremely geeky timepieces should be sure to check out the [Fibonacci watch face](https://wasp-os.readthedocs.io/en/latest/apps.html#fibonacci-clock) that was recently [contributed to wasp-os](https://wasp-os.readthedocs.io) by Johannes Wache.

##### Pinecil

The Pinecil has entered production a couple of weeks ago and will be available for purchase late this month or early next month. Much work has gone into polishing the tooling for the soldering iron’s molding, and we trust that the final version of the Pinecil will not only function but also look great. Check out [last month's update](https://www.pine64.org/2020/10/15/update-new-hacktober-gear/), in which I shared a couple of prototype pictures as well as a render of the final device. 

Aside from getting the Pinecil into production, time has also been spent on getting relevant certifications, figuring the least intrusive way of branding it, and deciding on the device’s packaging. Below you’ll find renders of the Pinecil’s packaging and the 4 complementary soldering tips which will be sold separately in the [Pine Store](https://pine64.com/product-category/soldering-irons/?v=0446c16e2e66). As you’ll notice, we decided to place branding and all required certifications along one side of the device - I subjectively feel this looks quite nice.  

![](/blog/images/photo_2020-10-16_03-19-41.jpg) ![](/blog/images/photo_2020-10-16_03-19-55.jpg)

**Pincil presentation box (top) and 4-tip presentation box (bottom)**

As soon as the Pinecil starts rolling out of the factory we’ll make sure to let you know when it is available for purchase. I’ll make sure to post a blog post, tweet / toot it and share it on our Telegram News Channel. If you’re interested in picking up a Pinecil, then make sure to follow us on your platform of choice to be notified when sales go live.  

##### PineCube

I’m happy to report that PineCube’s early software efforts are progressing well. We already have an internal Debian build running mainline kernel with patches, which shows a lot of potential. This isn’t to say that it is ready for use - to the contrary, considerable effort on developers part will be required to get all core functionality working. It is my understanding that this build will be released soon; massive thanks to Gamiee for making strides on the PineCube.

There is now also a NixOS build available for the PineCube thanks to [Daniel Fullmer](https://github.com/danielfullmer/pinecube-nixos/commits?author=danielfullmer). A quick look at [his GitHub](https://github.com/danielfullmer/pinecube-nixos) reveals that this OS build is quite far along, with many core functions of the device already working. This includes: Booting from SPI, enabling the IR LEDs, Ethernet, WiFi as well as USB. Perhaps most importantly, it appears that video streaming and recording from the camera already works, and if I am reading the documentation correctly then even the microphone is already functional. 

![](/blog/images/NixOSboot.jpg)

**NixOS booted on the PineCube**

I am also told that [Elimo Engineering](https://elimo.io) has integrated support for the PineCube into Buildroot. Their [GitHub account](https://github.com/elimo-engineering/buildroot) contains build instructions in the [board support directory](https://github.com/elimo-engineering/buildroot/tree/pine64/pinecube/board/pine64/pinecube) readme if you’re interested. It provides support for the S3's DDR3 in u-boot, which is an important development for the device. This means that the system is capable of booting really fast - apparently in under 1.5 seconds from cold boot to login prompt.  

These are all very significant developments, and the software will take shape over the next few months until we have a handful of usable operating systems for the PineCube. As I already mentioned in the Housekeeping section, a [PineCube subforum](https://forum.pine64.org/forumdisplay.php?fid=149) has been created earlier this month, and development discussions are already taking place on the [PineCube Discord chat](https://discordapp.com/invite/DgB7kzr). So if you pick up an early unit, you know where to direct questions and contributions. Speaking of contributions, you are also encouraged to submit entries to the PineCube [Wiki page](https://wiki.pine64.org/wiki/PineCube); we’d appreciate that.  

##### SOEdge

We’ll soon be getting ready to make the SOEdge available in the Pine Store. When it launches, it will be advertised as “strictly for developers”, since the software has a very long way to go before it can be considered as viable for end-user’s implementations. To speed up the development process, we’ve now created an information-rich SOEdge [Wiki section](https://wiki.pine64.org/wiki/SOEdge), which includes not only the BSP Linux SDK alongside core software documentation, but also a complete datasheet of the SOM, the baseboard and other components. 

Late last month Gamiee managed to get the module up and running using the Rockchip-provided BSP kernel. It is my understanding that this is an internal build - meant as a tool to determine the SOM’s and baseboard’s functionality, rather than an OS that will be shared publicly. It is my experience that information-exchange at such an early stage of development is crucial to a project’s success; to this end, we now have a [SOEdge subforum](https://forum.pine64.org/forumdisplay.php?fid=154), a Wiki page (please contribute) and there will soon be dev-chats set up to accommodate participating devs.

I cannot wait to see what the community manages to do with the SOEdge SOM in the coming months. 

![](/blog/images/SOege.jpg)

**SOEdge slotted in it's baseboard**

That's all for this month. Make sure to subscribe to this blog (at the bottom of the page), follow us on [Twitter](https://twitter.com/thepine64) and [Mastodon](https://fosstodon.org/@PINE64) and stay up-to-date with PINE64 News on the [Telegram News Channel](https://t.me/PINE64_News).
