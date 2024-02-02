---
title: "February Update: Show and Tell"
date: "2021-02-15"
categories: 
  - "news"
  - "pinebook-pro"
  - "pinephone"
  - "quartz64"
  - "risc-v"
tags: 
  - "pine64"
  - "pinebook-pro"
  - "pinephone"
  - "quartz64"
  - "risc-v"
cover: 
  image: "FebruaryUpdateBanner2.jpg"
images:
  - "FebruaryUpdateBanner2.jpg"
---

![](/blog/images/FebruaryUpdateBanner2.jpg)

Welcome to this month's community update. As many of you know, we have now entered the Chinese New Year (CNY) period, which means that all manufacturing and related business activities have ground to a halt. It is always a mad rush to complete ongoing work prior to CNY, but now that the festive period is upon us we get a chance to catch our breath and evaluate the progress made.

In this month's update we're going to take a close look at the Quartz64 model-A, showcase headway made on the PinePhone keyboard, discuss our first RISC-V single board computer and introduce plans for making LoRaWAN a staple of the PINE64 ecosystem.

You can watch the synopsis of this month’s community update on Youtube (embedded below) as well as on [LBRY](https://lbry.tv/@PINE64:a) and [Peertube](https://tilvids.com/accounts/pine64tilvids/video-channels). Stay up-to-date with PINE64 news and make sure to subscribe to this blog (subscription widget at the bottom of the webpage), follow [PINE64 Telegram News channel](https://t.me/PINE64_News) as well as our [Twitter](https://twitter.com/thepine64) and [Mastodon](https://fosstodon.org/@PINE64).

I’d like to acknowledge [JF](https://twitter.com/codingfield), [Marek](https://twitter.com/gamelaster) (Gamiee), [Alex](https://twitter.com/AlexRob12252696) (clover), [PizzaLovingNerd](https://www.youtube.com/channel/UCmGcm7dhEjS9CIOsOOv8y6w), [Konrad](https://github.com/konradybcio), [Biktor](https://twitter.com/biktorgj) and [Dylan](https://twitter.com/DylanVanAssche) for their contributions to this community update. Thank you!

This may just be the most news-packed update since July last year, so strap in for some PINE64-goodness and let's get to it.

{{< youtube id="EEyBVvC3NJw" >}}

**Video Synopsis by [PizzaLovingNerd](https://www.youtube.com/channel/UCmGcm7dhEjS9CIOsOOv8y6w)**

**TL;DR** for this month’s update:

- Housekeeping: Two PineTalk episodes are out!
- Housekeeping: Pinecil back in stock late Feb/ early March
- Housekeeping: Shipping status of PinePhone Mobian CE
- Housekeeping: Manufacturing difficulties expected after CNY and for much of Q2/Q3 this year
- Quartz64: Detailed specs listed and pictures of the SBC shown
- Quartz64: Comparison to ROCKPro64 connectivity & performance 
- Quartz64: Generic benchmarks on par with most popular SBC on market
- Quartz64: More than a stand-alone SBC - a dev platform for future devices
- Pinebook Pro: Production resumes in March; pre-orders mid-March
- PinePhone pt.1: End of CEs; PinePhone to ship with Plasma Mobile on Manjaro from now on.
- PinePhone p.1: A close look at the PP keyboard; fitted with 6000mAh battery 
- PinePhone p.1: We decided on the keyboard layout with community - the keyboard will be programmable, for those who wish to alter keyboard functionality
- PinePhone p.2: Opensourcing the modem - a status report by Biktor, Konrad and Dylan
- PinePhone p.2: Modem - work done on kernel 5.11; running open userland on kernel 3.18; making phone calls from open firmware
- PinePhone p.2: Expected modem improvements using FOSS firmware 
- PineTime: 3 versions of InfiniTime released in short succession in last 30 days
- PineTime: Blob-less heart rate monitoring working on InfiniTime + improvements to OTA flashing
- PineTime: Navigation on PineTime synced to Linux or Android Phone
- RISC-V PINE64 SBC: We’re entering the RISC-V SBC game 
- RISC-V PINE64 SBC: Starting with an entry-level SoC combined with a RISC-V WiFi/BLE currently being opensourced (Nutcracker challenge) 
- RISC-V PINE64 SBC: Goal to make RISC-V accessible to all at a reasonable price; fun SBC with multiple potential applications; sub $15 SBC
- RISC-V PINE64 SBC: Stay tuned for a name reveal via riddle 
- LoRa & LoRaWAN PINE64 integration: we are doubling down on LoRa integration - coming to all PINE64 devices
- LoRa & LoRaWAN PINE64 integration: we will build our own base stations based on next gen technology with better range, lower power consumption & higher transfer-rates
- LoRa & LoRaWAN PINE64 integration: Novel use of technology - text-based communication without a middleman

### Housekeeping

I want to start by giving [Peter](https://twitter.com/linmobblog) and [Ezra](https://twitter.com/Elatronion) - our [PineTalk](https://www.pine64.org/pinetalk/) Podcast hosts - a huge shutout. They've worked really hard on the first two episodes of the podcast and, judging by the number of episode downloads, so far their style has resonated well with the community. In the last episode they spoke to [Dalton Durst](https://twitter.com/UnivrsalSuprBox) from UBports, discussed the recent announcement of [PinePhone Community Editions coming to a close](https://www.pine64.org/2021/02/02/the-end-of-community-editions/) and answered some questions from the community. PineTalk is now available on all major platforms, including Spotify and Apple's Podcast app, and I highly encourage you to subscribe to the [RSS feed](https://www.pine64.org/feed/mp3/). 

![](/blog/images/PineTalkPP-1024x768.jpg)

**Yes, of course, you can listen to PineTalk on your PinePhone too**

Over this past month we received a significant amount of feedback concerning the new PINE64 website. This included suggestions on improving the site’s responsiveness, functionality as well as a variety of various minor bugs encountered by community members. As a result, responsiveness has been significantly improved and sections of the site have been reworked to offer a better experience on mobile devices. There is now also a dedicated blog button (honestly, I was surprised to hear people had issues finding the blog on the new site) and the blog itself received some much needed tweaks to improve navigation. A number of fixes were also made to make the page less taxing. Thank you to Gamiee for his continued work on the community site and to all of you who submitted feedback and suggestions. 

As I mentioned in the opening bit of this blog entry, CNY is now upon us and there will be no manufacturing or shipping activity until late February. All Pine Store contractors in Malaysia, China and Hong Kong are now enjoying time off with their families and close ones (where permissible, of course, given COVID19 is still rampant). To those of you awaiting a response from the support or info teams, please be aware that you will not receive a reply until after CNY. If you have an urgent query concerning your shipping or order status, i.e., a query which cannot wait, then please reach out to me or one of the moderators in our chats.

I'd like to quickly touch upon the Pinecil's availability. I get bombarded with questions about when it will be back in stock, so I’m answering the query here: stock will be available again late this month or early the next. Don't expect it to show up in the store before the end of CNY.

![](/blog/images/RedPinecil-1024x768.jpg)

**I must say, the Pinecil looks good in red - picture via [Dan Lien on Twitter](https://twitter.com/danclien/status/1360394157798416384)**

Before proceeding to the main topic of this month’s housekeeping section, I want to write a few words about the Mobian Community Edition PinePhone shipping status. As some of you are aware, we ran [into issues with DHL](https://twitter.com/thepine64/status/1356426440938553344) shipments in late January and early February. Long story short, we effectively had to reship an entire palette of KDE CE PinePhones twice due to a DHL error. This threw a wrench into our schedule; the shipping team worked hard to dispatch as many phones as possible prior to CNY, but unfortunately most Mobian CE units ended up waiting at the warehouse to be shipped to their rightful owners. Only phones destined for Europe were successfully shipped before work ceased. Please follow the dedicated [forum thread](https://forum.pine64.org/showthread.php?tid=13007) to stay up to date on the shipment process.

I'd like to finish this housekeeping section by making you aware that difficult times are ahead of us manufacturing-wise. It was a [year ago to the day](https://www.pine64.org/2020/02/15/february-update-post-cny-and-fosdem-status-report/) when I first wrote about the impact the COVID19 pandemic would have on the supply chain and manufacturing process in China. I reported on the situation more than a month before any big brand even murmured a word about the severity of the electronics shortages, which we all witnessed mid-and-late last year. You see, big brands don't really want customers to know that their devices will not be available or in short supply. So here I am, a year later, once again being a bearer of bad news (edit: since originally writing this passage, 10 days ago or so, some [reporting of the issues](https://www.cnbc.com/2021/02/10/whats-causing-the-chip-shortage-affecting-ps5-cars-and-more.html) already begun in the media). We expect severe component shortages and major component price hikes after CNY. I am writing this to prepare you for what is to come. Production-wise, we're entering a difficult phase and compromises will be made - there is no doubt in our minds that the emerging market situation will have a significant negative impact on PINE64. However, the extent of the impact won't be known for at least an entire month, so let's not worry too much about the unavoidable and hope for the least disruptive outcome. Keep your fingers crossed! I will, of course, keep you up to date on how things pan out. 

### Quartz64

It is finally time for us to take a look at Quartz64 model-A, the first installment in our 'Quartz-line' of next generation single board computers (SBCs). The Wiki page for [Quartz64](https://wiki.pine64.org/wiki/Quartz64) is now available for those of you who wish to study the schematics and datasheets. Keep in mind that photos of the Quartz64 depict a prototype device and some modifications to the hardware may prove necessary prior to the SBC’s release. Any changes made, however, will be very minor at this point and only implemented to remedy issues identified by developers, if such arise. In other words, although this is an engineering sample, production units will look indistinguishable from it. With the board's layout now finalized, we're happy to share all the details you’ve been waiting for with you.

![](/blog/images/photo_2021-02-11_09-48-52-1024x633.jpg)

**Top view of Quartz64 model-A**

Many of you will immediately notice the close resemblance, in terms of both the available I/O and general layout, that this board shares with the ROCKPro64. Both boards feature USB 3.0, alongside 2xUSB 2.0 ports and have an open-ended 4xPCIe slot, which can be populated by a variety of peripherals. The similarities don't end here: the Quartz64 features un-populated IR and SDIO headers (current IR and WiFi/BT modules are compatible), has HDMI capable of 4K output at 60FPS as well as a DSI and CSI output and MiPi interface. There is also 128Mb of onboard SPI flash, just as on the ROCKPro64. The eMMC and mSD card slots too can be found in the exact same position on both boards. There are also FAN, VBAT and 12V power headers, situated in the same model-A layout locations. A RTC connector is also located on the PCB. The 12V header is capable of powering up-to two 2.5" SSDs or HDDs when using our 12v 5A [power supply](https://pine64.com/product/rockpro64-12v-5a-eu-power-supply/?v=0446c16e2e66), just as on the ROCKPRo64.

While the SBCs share many similarities, there are some significant differences between the two. For one, as you have likely already spotted, the Quartz64 has a native SATA 6.0 port located right behind the USB ports. The Quartz64 has one USB 3.0 port, while the ROCKPRo64 has one USB 3.0 and one USB-C port. The Quartz64 PCB also features an integrated battery charging circuitry. This means that, similarly to the PINEA64-LTS, the board can be completely battery operated. A unique feature of the Quartz64 is its native e-ink port; as I already mentioned in [last month's update](https://www.pine64.org/2021/01/15/january-update-happy-new-gear/), we hope to have a 10" e-ink panel available in the Pine Store when the SBC releases to the public. Perhaps most importantly of all, Quartz64 is capable of supporting up-to 8GB of LPDDR4 RAM.

![](/blog/images/photo_2021-02-11_09-48-521-768x1121.jpg)

**Front view of Quartz64 model-A**

![](/blog/images/photo_2021-02-11_09-48-51-768x906.jpg)

**Back view of Quartz64 model-A**

Performance-wise, early testing indicates that the Quartz64, with its 4 cortex A55 cores clocked at 1.8Ghz, is only 15-25% slower in computational tasks than the ROCKPro64. Do keep in mind, however, that the Quartz64 isn't a Pro-grade PINE64 single board computer. The intended purpose for it is to eventually supersede the PINE A64 and ROCK64, rather than the higher-end ROCKPro64. If anything, the fact that I am comparing a non-Pro next generation SBC to a Pro-grade current generation board should be rather exciting. Lastly, since I know that many of you are curious, the Quartz64 delivers computational performance that is very similar to the most popular single board computer on the market (based on generic benchmarks). Do keep in mind, however, that such benchmarks do not always translate well to real-life tasks, so one board may be superior to another depending on the nature of the scenario. I also ought to mention that from our initial testing, the RK3566 runs really cool - under load, without a heatsink, it rarely spiked above 60\*C.

![](/blog/images/RPIvsQ642-1024x418.jpg) ![](/blog/images/RPIvsQ64_1-1024x420.jpg)

**Don't read too much into these generic benchmarks**

Designing the Quartz64, we envisioned that it will serve an additional purpose in the future. Aside from being a stand-alone SBC, it will also be used as a development platform for future non-Pro devices. We have been thinking about democratizing development for some time now, and we intend to start the process with the Quartz64. Creating dedicated development platforms, such as the [Don't Be Evil](https://wiki.pine64.org/index.php/Project_Don%27t_be_evil) PinePhone kit, is expensive and time consuming. Such kits also limit the number of people who can participate in the bring-up process, as usually a very limited number of such devices are manufactured. The Quartz64, however, features all the necessary circuitry to start work on a next generation phone, tablet or laptop. Plug a display into the DSI port, a modem into the USB port and add a battery - _voila_, you've got yourself a next-gen phone dev kit. So to those who aren't usually interested in SBCs in general - it may be worthwhile picking one up and helping the Linux bringing-up process on the RK3566.

Speaking of the bringing-up process, a small number of Quartz64 boards have now been shipped to low-level developers. I am looking forward to seeing how Linux takes shape on this RK3566 platform in the coming months. A major encouraging factor in the bringing-up process is that the Panfrost open source GPU driver ought to 'just work' once Linux is brought-up and functional to a point where video output is possible. GPU drivers are always tricky and usually take a long time to open source, so the fact we already have a FOSS GPU for this SoC is a major boon.

![](/blog/images/underload.jpg)

**Under high load it manages to stay cool, even without a heatsink**

It is too early to talk about general availability at this point. A lot will depend on how quickly rudimentary Linux support can be brought to the Quartz64. That said, I place a lot of trust in the developer's abilities. You can expect an update on Quartz64 in the next community update.

### Pinebook Pro

I am happy to let you know that we will be resuming production of the Pinebook Pro shortly after CNY. We were fortunate enough to secure A-grade LCD panels and the necessary RAM (currently in short supply) for the production to begin, and we already have an allocated slot at the factory for the assembly process. I presently do not have a pre-order date for you - that will be announced at a later time. But if you're interested in picking up a unit then I strongly suggest you follow our Telegram news channel and/or social media for pre-order news  (links in the opening paragraph of this post). I know, however, that many of you would appreciate a ballpark idea of when stock will be available, so to this end: based on our current schedule, pre-orders are set to open sometime mid-March 2021.

![](/blog/images/lomirionPBP-1024x716.jpg)

**The Pinebook Pro is now a mature platform with a lot of fun development - image by [Clover](https://twitter.com/AlexRob12252696)**

### PinePhone Part 1

Earlier this month we announced the [end of the Community Editions](https://www.pine64.org/2021/02/02/the-end-of-community-editions). The Community Edition program was a vital step not only in bringing support to the PinePhone, but also in bringing attention to mobile Linux outside of our immediate bubble. Countless people worldwide were made aware of alternatives to the duopoly of Android and iOS, and I'm sure that we can all agree this is a good thing. This exposure is obviously good for PINE64, but I'd argue that it is equally good for the entire Linux community. Promotion of the Community Edition PinePhones propelled mobile Linux development like nothing else in recent years and gave birth to multiple new projects. With tens of thousands of PinePhones in people's hands, it is no longer an unlikely possibility that a mainline Linux smartphone will take hold, but rather an inevitable certainty. Before moving on, let me once again thank all the projects and their developers who participated in the Community Edition scheme. You all did a great job.

While the Community Edition program is now closed, we're working on a plan to actively support mobile Linux projects moving forward. Talks are held with all major projects and we already have some ideas on how to provide developers with ongoing support. Aside from projects which received a Community Edition, we are now also talking to Maemo Leste, LuneOS, openSUSE, DanctNIX and Fedora developers. While we haven't settled on a means to achieve this type of support just yet, I hope that a part of the strategy will be an introduction of branded back-covers to the Pine Store. In short, the idea is to sell back-covers with projects logos at approx. a $15 price-point, out of which $10 would go towards the donation. I think that this is a good and fun way of supporting development, which provides end-users with a tangible benefit for submitting their donation. It will take a couple of weeks for us to figure this out, or maybe even longer, but once we do arrive at a suitable arrangement I’ll write a dedicated blog entry about it. 

At this stage I know many of you are wondering what the future of the PinePhone holds. A question that I frequently receive concerns the default operating system and user interface that will ship on the PinePhone. Today we are very pleased to announce that the PinePhone will ship with [Plasma Mobile](https://www.plasma-mobile.org/) on a [Manjaro](https://manjaro.org/) ARM base from this point on. We have a long-standing relationship with Manjaro and KDE Community, and both projects have supported us and our efforts since the dawn of PINE64. I'm not sure if I wrote about this publicly in the past, but the promise that Plasma Mobile held in its early stages was the deciding factor for us to proceed with creating a Linux smartphone in the first place. Needless to say, we have been excited to see the UI environment mature and flourish on our platform over the past 12 months. Manjaro is our core partner, offering support for all our flagship Linux devices, including the ROCKPro64 and the Pinebook Pro. Their work on the PinePhone has been indispensable, and their current OS images are among the best and most fully-featured for the platform. Working with both projects on the PinePhone has been a pleasure and I am convinced that together we will reach new heights in the months to come.

![](/blog/images/PlamoKDE-1024x386.jpg)

**Manjaro and Plasma Mobile is just a great combination (picture of widget on main page)**

Earlier this month we also received the PinePhone keyboard, perhaps the most anticipated accessory of them all. It literally arrived a week ago from the factory. Looking at the pictures below, those eagle-eyed of you will probably notice the missing key caps. The key caps and the keyboard's PCB are the two outstanding parts we’re still waiting for - we expect both to be delivered shortly after CNY. The molding is completed however, and has now been submitted to us for review. I'm happy to let you know that our initial impressions are very positive and we're convinced that you'll be pleased with it too. Please keep in mind that the pictures are of an early preview unit, and everything you see is a subject to change before they keyboard becomes available in the Pine Store.

![](/blog/images/718491507195801866-1024x576.jpg)

**PinePhone in the keyboard chassis from the front and side**

![](/blog/images/photo_2021-02-04_17-24-43.jpg)

**PinePhone in the keyboard chassis from the side**

![](/blog/images/24374766084716176-576x1024.jpg)

**PinePhone in the keyboard chassis closed top**

![](/blog/images/photo_2021-02-04_17-24-45-1024x868.jpg)

**PinePhone in the keyboard chassis closed bottom**

From the very inception of the keyboard design we wanted to include a large battery in the base of the chassis. Aside from the obvious benefit of significantly extending the PinePhones operating time, a large battery also serves as a counter balance to the PinePhone placed in the top section of the keyboard’s body. We wanted to cram as much battery power as possible into the keyboard, and we were lucky to find a 22Wh 6000mAh battery which fits the bill perfectly. From my estimates, the PinePhone fitted with the keyboard will be able to remain in standby mode for nearly a week with the modem active. With the modem disabled, however, it will last you more than two weeks on a single charge when placed in deep-sleep. Due to the battery's size taking up the bulk of the space inside the keyboard’s bottom section, the charging circuitry had to be shrunk down to a tiny PCB. But don’t be deceived by it’s tiny size, this charging circuit can simultaneously charge the keyboard and the PinePhone via the keyboard’s USB-C port. Since I know someone will ask: the USB-C port on the keyboard can only be used charging, it doesn't support data or any alternate modes.

![](/blog/images/13956025106436045-768x1024.jpg)

**PinePhone keyboard charging PCB**

![](/blog/images/159224812259364083-576x1024.jpg)

**Look at the size of that battery!**

This effectively completely frees up the USB-C port on the PinePhone. You can plug a convergence dock into it or use it for any other common USB-C devices, e.g. thumbdrives. A quick web-search revealed to me that there are now a number of USB-C wireless mice available on the market (something I wasn't aware of!). So you can pick one up and plug it into the PinePhone, thereby transforming it into a pocketable Pinebook. Many GUI environments available for the PinePhone - including Phosh, Plasma Mobile and Lomiri - already work well in a desktop mode, but I am sure that the keyboard accessory will entice people to bring MATE, XFCE, GNOME and full-fledged Plasma to the device. And why not - after all the keyboard converts the PinePhone into a PDA capable of running full-blown Linux.

Before moving onto discussing software, I quickly wish to touch upon the keyboard’s layout. We spent a weekend in January ping-ponging ideas about the layout with the community. After some push and pull we finally arrived at a compromise that most end-users should be happy with, given the space and design constraints. The illustration attached below depicts the layout we arrived at and submitted to the vendor. I know that not everyone will agree with every design decision made; to those of you who would prefer a different layout, or really need a CAPS key (for whatever reason), rest assured that eventually you'll be able to flash your own firmwares to the keyboard via the i2c pins, and thereby change the keys functions. This will, however, require input from the development community - an effort similar to that [made on the Pinebook Pro](https://github.com/jackhumbert/pinebook-pro-keyboard-updater) will be needed. The time it took to get the community's approval of the design led to a delay in delivering the keycaps prior to CNY. But even without its keys, doesn’t it just look awesome?

![](/blog/images/photo_2021-01-19_07-26-14.jpg)

**Here is they keyboard layout we agreed on with the community**

### PinePhone Part 2 \[by Konrad, Biktor and Dylan\]

We are currently working on three different fronts modem-wise: 1) porting the mainline (kernel.org) kernel; 2) open-sourcing the userspace and; 3) improving the way incoming calls and texts are handled while the phone is suspended.

The modem can now boot version 5.11 of the Linux kernel with minimal functionality (serial, USB and NAND). Konrad has been working hard on all the low level drivers that are needed (PMIC, clocks etc) so the rest of the devices inside the SoC can start. There's still a lot of work to do, since the SoC has never seen an official release from Qualcomm ever since kernel 3.18.x, so even if some pieces can be adapted from other mainlined Qualcomm models, there's a lot of code that needs to be written from scratch. Work is being done by Konrad to send his existing patches upstream, so that they can get merged and so that he can further continue the work.

![](/blog/images/VOLTEblobles-768x986.jpg)

**VoLTE blobless audio calls will be possible in the future. [Original Twitter post By Biktor](https://twitter.com/biktorgj/status/1357217053745250304)**

On the present factory firmware, there are about 150 closed source binaries and libraries that make the modem work. Biktor is working on replacing all of them with 3 open source alternatives that will hopefully get 90% of the required functionality. At this point we can initialize the modem, establish data connections and make both CS (normal) and VoLTE calls without any binaries, although sometimes audio fails, and call reception doesn't work yet. Stay tuned for more information about the open sourced userspace in near future.

Dylan has been tackling one of the biggest complaints concerning the modem, namely the slow recovery from suspend and its USB resets, making the PinePhone lose incoming calls and texts when using ModemManager (since it cannot reconnect to the modem fast enough after suspend). These patches, currently in a testing stage, should make the PinePhone wake up and start ringing on the first dial tone when there's an incoming call or text, as well as fix intermittent USB resets that show up when resuming from suspend.

{{< youtube id="ZsmCpSyyE2g" >}}

We currently have: i) An open-source bootloader, allowing us to flash and boot custom software; ii) A temporary, open 3.18.140 kernel with minimal patches, that gives the same functionality as stock with less vulnerabilities and the chance of debugging drivers while moving to 5.x. iii) Open userspace options, with or without blobs, giving varying degrees of functionality, based on Yocto 3.2, or postmarketOS. iv) Modem SDK which serves as a playground for anyone who wants to build his or her own firmware based on Yocto. v) Initial support from the postmarketOS team that allows to create flashable pmOS images for the modem.

The end goal has always been the same, to have the modem as open source as possible. We aren't touching the modem's ADSP firmware, because in addition to the inherent difficulties that come with it, modifying the ADSP firmware could lead to problems with RF regulations or certifications.

### PineTime \[by JF\]

January was a prolific month for InfiniTime: we released no less than 3 versions of InfiniTime in this short period of time. The biggest release was InfiniTime 0.11, which came with 2 major features - the long awaited integration of the heart rate sensor and a brand new navigation application from [Adam](https://twitter.com/adampigg).

Why did it take so long to integrate the heart rate sensor in InfiniTime? Well, in fact, I implemented a working demo of the HR sensor more than 6 months ago but couldn't release it because it was based on a non-free/proprietary library. This library implements the algorithm that converts raw data coming from the sensor into human readable values (beat per minute).

From the beginning of the InfiniTime project, I always wanted it to be fully open-source. That's the reason why I chose the GPLv3 license for InfiniTime. One of the implications of this choice is that we cannot include non-free/closed source modules into the codebase. This heart rate processing library was then conflicting with the license of the project and one of its main values.

But still, many people were asking for the heart rate sensor in InfiniTime, and fortunately, [Daniel from WaspOS](https://github.com/daniel-thompson/wasp-os) implemented a brand new algorithm for WaspOS and released it under the LGPL license, which allowed me to port his code in C++ and integrate it into InfiniTime. Thanks again to Daniel for his amazing work!

![](/blog/images/HR2PT-768x1024.jpg) ![](/blog/images/hr1PT-768x1024.jpg)

**Heart rate measuring in-app (left) and displayed on watchface (right)**

I teased the Navigation app in the last community update. I'm happy to announce that it's now released! This app, written by [Adam](https://twitter.com/adampigg) works in conjunction with [Amazfish](https://github.com/piggz/harbour-amazfish) and [PureMaps](https://github.com/rinigus/pure-maps), and InfiniTime displays the navigation instructions from PureMaps when it's connected to Amazfish. Best of all, these apps run on many Linux devices, such as the Pinebook Pro and the Pinephone !

<iframe width="660" height="815" sandbox="allow-same-origin allow-scripts allow-popups" src="https://video.codingfield.com/videos/embed/1fd64ff8-5a5b-48d9-b7f8-298df0dc383e" frameborder="0" allowfullscreen></iframe>

**Navigation instructions displayed on the PineTime**

Speaking of Amazfish, Adam has also improved the integration in non-SailfishOS Linux distributions like ManjaroARM and Ubuntu.

The BLE connectivity has been greatly improved in InfiniTime 0.12 by updating NimBLE, the open source BLE stack integrated in InfiniTime. With this upgrade, you should expect less failed OTA and less unexpected disconnections from the companion app.

This month, I would also like to highlight [Nico's blog](https://www.ncartron.org/). In his blog, Nicolas writes about SailfishOS, smartwatches and... the PineTime! The [first article](https://www.ncartron.org/pinetime-on-sailfishos.html) is an overview of PineTime with SailfishOS. In a [second article](https://www.ncartron.org/upgrading-pinetimes-infinitime-firmware.html), Nico explains how to upgrade InfiniTime using Amazfish on SailfishOS. Finally, he reviewed InfiniTime 0.11 and 0.12 in this [3rd article](https://www.ncartron.org/pinetime---quick-review-of-infinitime-versions-0110-and-0120.html). I really appreciate these blog posts, they are short, easy to read and give honest and accurate opinions about the progress of the project.

### RISC-V PINE64 Single Board Computer(s)

It will probably come as no surprise to anyone following our project that we've been watching the RISC-V space very closely in the past 18 months. Many of you correctly concluded that the Pinecil, our recently released and very popular RISC-V soldering iron, was our first foray into the world of RISC-V SoCs. Indeed, the choice of the RISC-V SoC for the Pinecil was not mere coincidence. That said, Pincil’s SoC is rather rudimentary and incapable of running an advanced operating system such as Linux. We’re now at a point where we’re willing, and indeed keen, to dip our toes in the RISC-V pond and build our first single board computer capable of running full-blown Linux (and possibly also other FOSS operating systems). I’m not sure about you, but we’re rather excited about the prospect of this decision and its importance moving forward. 

While we’re not quite ready to talk about the specifics of the SBC at this point in time, in part because many PCB-design decisions haven’t been set in stone yet, I do nonetheless want to give you a general sense of the sort of hardware that we’ll be delivering. Our first SBC will feature two RISC-V CPUs, the main one being a C906 64-bit SoC coupled with an auxiliary 32bit BL602 SoC for WiFi and BLE. The C906 is already capable of running Linux and, from what I understand, is completely open while the BL602 is in the process of being open sourced (including firmware) in our [Nutcracker community challenge](https://www.pine64.org/2020/10/28/nutcracker-challenge-blob-free-wifi-ble/). The SoC has solid I/O, including USB 2.0 and Gigabit Ethernet, and I see it as a great entry-level Linux-capable RISC-V platform.

![](/blog/images/C906-RISC-V-Processor-1024x524.jpg)

**The C906 feature list for those very tech savvy of you**

I am making the specifications known well ahead of time to manage your expectations. The overarching idea behind this board is to make an inexpensive board, accessible to all who wish to explore the RISC-V architecture, and to get it into the hands of as many people as possible. We’re aiming at a sub-$15 price point. We also want it to become a gateway to more powerful RISC-V SoCs in the future. While it's our first entry into the world of this particular architecture, it most surely isn’t our last. The board will allow you to create fun IoT, learning and DIY projects, but I won’t be surprised to see someone make Doom, Sonic the Hedgehog or MarioKart run on it in a matter of weeks. In a month or two, I'll share more details concerning the board-design and the exposed IO. Lastly, as you noticed already I haven’t mentioned the name of the SBC - you can expect [a riddle](https://forum.pine64.org/showthread.php?tid=12585) in the coming weeks.

### LoRa and LoRaWAN PINE64 Ecosystem Integration

In the past 6 months I’ve mentioned LoRa and LoRaWAN on many occasions and in multiple posts. If it wasn’t clear until now, we have been quite interested in the technology and its potential for novel applications. After extensive internal considerations, we now feel ready to double-down and make LoRa an integral part of the PINE64 ecosystem. I’ll explain a bit more about the core premises of our vision further down in this section, but let me start by writing about the actual equipment we’re planning to deliver. For one, we will offer next generation modules for all our devices - this includes, but is not limited to, the PinePhone, the PineTab and Pinebook Pro. We will be using next generation LoRa chipsets in our expansion modules, which deliver better performance while consuming less power. We will simultaneously introduce LoRa modules for North America, Asia and Europe, that conform to the respective [regional regulations](https://en.wikipedia.org/wiki/LoRa#LoRaWAN). 

We will also build our own LoRaWAN base station, which too will utilize next generation LoRa technology. This chipset does not only allow for higher efficiency and lower power consumption, but also for an improved data-transfer rate when compared to presently available technology. We intend to introduce two versions of our base station, the first of which is intended for deployment indoors, while the second arrives enclosed inside an aluminum waterproof container for use outdoors. The theoretical range of the base station is measured in tens of km’s, at least in unobstructed line of sight. That said, a range of 5-6km is much more realistic in most scenarios due to terrain and other obstructions found in urban areas. As you have come to expect from us, the brains of the base-station will be running FOSS software atop of mainline Linux.

![](/blog/images/ACLoRaPaper-768x598.jpg)

**We aren't the first ones to think of using LoRa for communication - [source](http://wireless.ictp.it/Papers/lora-communications.pdf)**

So, then, why are we doubling-down on this? While LoRaWAN is usually used for a variety of IoT type deployments, we wish to use it for text-based communications. In its implementation we expect the functionality to be more akin to HAM radio rather than SMS or instant messaging. Most importantly of all, however, we see LoRaWAN as a means for communication without a middleman. To allow communication over vast distances, each base station can be connected to the internet. We hope that, in time, urban areas will see some degree of coverage and that people will be willing to join in on the fun. And yes, in the initial phase of this experiment, the purpose of LoRaWAN stations is to have a bit of fun, whilst simultaneously exploring the limits of the technology’s application for communication. Needless to say, getting developers onboard to support this novel implementation of the technology will prove crucial. Over the next months I’ll do my best to convince relevant parties that it makes sense to explore this LoRaWAN application and that it may be a first step in rethinking secure communication mediums.

That is all for now, I’ll catch you all in a month!
