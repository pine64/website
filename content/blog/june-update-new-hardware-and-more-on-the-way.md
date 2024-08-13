---
title: "June update: new hardware and more on the way"
date: "2021-06-15"
authors: ["Lukasz Erecinski"]
categories:
  - "community"
  - "lora"
  - "news"
  - "pinecil"
  - "pinedio"
  - "pinephone"
  - "pinetime"
  - "quartz64"
tags: 
  - "lora"
  - "pinecil"
  - "pinephone"
  - "quartz64"
cover: 
  image: "JuneUpdateBanner.jpg"
images:
  - "/blog/images/JuneUpdateBanner.jpg"
---

![](/blog/images/JuneUpdateBanner.jpg)

I’d like to start by giving you all a quick heads-up: next month I am away on vacation (first one since early 2020), which means that next month’s update will either be very short or split into multiple posts. If I write up a longer post then I may not publish it on the 15th but at some other point in time. I haven’t yet made up my mind how I’ll do this, so just keep an eye out. 

With that out of the way let us get into this month’s news - the biggest one of which is that Quartz64 model-A is now available for purchase!    

You can watch the synopsis of this month’s community update on YouTube (embedded below) as well as on [Odysee](https://odysee.com/@PINE64:a) and [Peertube](https://tilvids.com/accounts/pine64tilvids/video-channels). Stay up-to-date with PINE64 news and make sure to subscribe to this blog (subscription widget at the bottom of the webpage), follow [PINE64 Telegram News channel,](https://t.me/PINE64_News) the [announcements channel in Discord](https://discord.gg/pine64) as well as our [Twitter](https://twitter.com/thepine64) and [Mastodon](https://fosstodon.org/@PINE64).

I’d like to thank [JF](https://twitter.com/codingfield), [Alex](https://twitter.com/AlexRob12252696) (clover), Ondrej ([Megi](https://xnux.eu/)), Chris ([kop316](https://gitlab.com/kop316)), [Brian (](https://mastodon.online/web/accounts/61817)33YN2) and [PizzaLovingNerd](https://www.youtube.com/channel/UCmGcm7dhEjS9CIOsOOv8y6w) for their contributions to this community update.

**N.B.** Comments on the blog post need to be in English and follow our [Community Rules and Code of Conduct](https://forum.pine64.org/showthread.php?tid=13209).

{{< youtube id="mzCIhq17b78" >}}

**June community update video summary by [PizzaLovingNerd](https://www.youtube.com/channel/UCmGcm7dhEjS9CIOsOOv8y6w)**

**TL;DR for this month's communty update:**

- Housekeeping: improvements to product pages and getting started. A new shipping, stock and availability tracker added to website 
- Housekeeping: a quick notice regarding code of conduct, moderation and just being a decent person to others
- **Quartz64: the model-A is now [available in the Pine Store](https://pine64.com/product-category/quartz64/)! (4GB model - $59.99 // 8GB model - $79.99)**
- Quartz64: development is proceeding quickly, but for now this is a board for developers and enthusiasts capable of contributing
- Quartz64: model-B, with smaller footprint, available at a later date 
- Quartz64: introducing the SOQuartz compute module, featuring industry-standard 100 pin connectors
- PinePhone Hardware: keyboard coming along well, two iterations of prototypes built in past 30 days 
- PinePhone Hardware: the keyboard now runs open firmware thanks to Megi; keyboard battery levels now reported in Linux; review of second iteration reveals some minor remaining problems need to be worked out
- PinePhone Hardware: delay on Wireless charging back case because TI chip not available (silicon shortages)
- PinePhone Software: Plasma Mobile 5.22 released; many improvements and new apps
- PinePhone Software: even more improvements coming in Plasma Mobile 5.23
- PinePhone Software: MMS (mmsd-tng) functionality coming along; kop316 working towards a v1.0 release, already in Mobian and postmarketOS
- PineTime: availability of single sealed PineTime delayed due to component shortages: replacement part sourced, but needs to be verified, tested and potentially enabled in firmware
- PineTime: a lot of development taking place, including optimizations for RAM and flash storage; many new apps being developed, inc. weather forecast, likely to be included in InfiniTime 1.2 
- PineDio: It will take us a little longer to deliver PineDio gateways - component shortages, affecting Realtek PHY, forced us to create a V2 revision of PINE A64-LTS - used as based for PineDio gateways
- PineDio: Board bring-up takes time, but we’re committed to bringing the PineDio LoRa-range of devices to the market ASAP
- PineDio: work on outdoor gateway ongoing; antenna routing being done currently; outdoor gateway includes 3x18650 battery holder and PoE adapter
- **Pinecil: The Hammerhead kit is now available in the [PineStore](https://pine64.com/product-category/pinecil/) for $24.99!**
- Pinecil: Hammerhead kit features 2x heads, 1x custom threaded shaft/tip and a 500\*C resistant mat

### Housekeeping

A lot of work has gone into improving the Community website this past month. Product pages have been reworked to be more informative and to include additional resources. If you have any suggestions for further improvements to the product pages, make sure to leave them in the comments section. We also added a [shipment, stock and availability tracker](https://www.pine64.org/availability-and-shipping-status/) on the website, allowing users to check current stock levels, estimated availability dates for popular devices and shipping status information. The system will be further refined in the coming weeks, but I feel that this is a good starting point. If you’d like to see other devices on the webpage, leave your suggestion in the comments section. 

We also reworked the [_getting started_](https://www.pine64.org/documentation/Introduction/Getting_started/ page on the website. The new page is a significant improvement in every respect. It offers a quick overview of individual devices' software maturity, recommended operating systems, and links to further resources. We also included all the necessary links to join the community. Once again, if you have suggestions for further improvements, leave them in the comments section. I am really keen to hear your feedback. 

![](/blog/images/Stock-n-shipping-898x1024.jpg)

**You now can check stock levels, estimated availability and shipping on this site**

![](/blog/images/GettingStarted-913x1024.jpg)

**The _getting started_ page is now much better at actually getting you started**

Next, let me touch upon chat etiquette and moderation briefly. As you know, a part of what makes PINE64 special is the direct involvement of developers from partner projects (as well as community contributors) on our chats and forums. Having developers from the different projects participate, work together and communicate with users is a major boon for us all. It is therefore alarming that in recent months we’ve seen an increase in non-constructive dissent. I don't wish to dwell on this - but long story short, it is one thing to voice an opinion and offer feedback, and another to ridicule or be hostile towards partner project developers. Just because you don’t like a particular OS or UI doesn’t make it hate-worthy. After all, it is people’s hard work, and it is open software, so I’m sure there are other objects more deserving of contempt. Developers are people too and they have their individual sensitivities - how you communicate matters, please keep that in mind. 

To finish this section off on an uplifting note: I encourage everyone to listen to the [latest PineTalk episode](https://www.pine64.org/podcast/010-man-of-many-apps/), in which Ezra and Peter interview Martijn Braam from postmarketOS and talk about how he got started with smartphone development and much more. The episode is worth listening to for the intro alone.

Lastly, a quick reminder that [KDE Akademy](https://akademy.kde.org/2021) is taking place June 18-25. This is also the fourth year in a row that PINE64 is a sponsor of the event.

### Quartz64

After months of work, the Quartz64 is now available in the [Pine Store](https://pine64.com/product-category/quartz64/). Let me begin with a short recap: the Quartz64-line is a series of computers featuring the Rockchip RK3566 SoC. This SoC combines a quad-core, ARM Cortex-A55 CPU with a Mali-G52 2EE GPU. It is capable of driving a single 4K display at 60fps and the GPU uses the open source [Panfrost](https://docs.mesa3d.org/drivers/panfrost.html) driver. It also has the benefit of running very cool, even without a heatsink and under a sustained load. The Quartz64 is a powerful and versatile platform that will serve us for years to come, also as a basis for future non-Pro PINE64 devices. 

![](/blog/images/Q64A-1-1024x1024.jpg)

**Quartz64 model-A viewed from top**

![](/blog/images/Q64A-3-1024x1024.jpg)

**Quartz64 model-A front IO**

**Right now, Quartz64 is only suitable for developers and advanced Linux users wishing to contribute to early software development.** Both [mainline and Rockchip’s BSP fork of Linux have already been booted](https://www.pine64.org/2021/04/15/april-update-new-developments/) on the platform, and development is proceeding very quickly, but it will be months before end-users and industry partners can reliably deploy it. If you need a single board computer for a private or industrial application today, we encourage you to choose a different board from our existing lineup or wait a few months until Quartz64 software reaches a sufficient degree of maturity. A [matrix-style visual representation](https://wiki.pine64.org/wiki/Quartz64_Development) of the software development status is available on our Wiki. It will be updated as new milestones are reached. You can also follow, and contribute to, the ongoing development on [GitLab](https://gitlab.com/pine64-org/quartz-bsp/linux-next/-/tree/quartz64-next-20210603). You can learn more about the Quartz64 model-A from my previous community updates written in [February](https://www.pine64.org/2021/02/15/february-update-show-and-tell/), [March](https://www.pine64.org/2021/03/15/march-update/) and [May](https://www.pine64.org/2021/05/15/may-update-connection-established/). 

The model-A footprint matches our ROCKPro64 and PINE A64-LTS boards. It can be used as a stand-alone computer as well as a development platform for future PINE64 devices. 

The board features an extensive I/O configuration, including:

- Gigabit Ethernet
- Digital video and audio out 
- Three USB 2.0 ports
- One USB 3.0 port
- One SATA 3.0 (6Gbps) port
- One eMMC slot
- One microSD slot
- Embedded DisplayPort (eDP)
- E-ink display connector
- MiPi DSI 4 lanes
- MiPi CSI 4 lanes
- Touch Panel port
- Lithium-Ion Polymer battery charger and power supply
- 2x10 GPIO header pins
- PCIe ×1 open-ended slot

We are also providing an optional [WiFi 802.11 AC +Bluetooth 5.0 module](https://pine64.com/product/rockpro64-1x1-dual-band-wifi-802-11ac-bluetooth-5-0-module/?v=0446c16e2e66) which interfaces with the board via SDIO 3.0. An alternate module featuring the Bouffalo 602 RISC-V 802.11n + BLE 5.0 module, currently undergoing open-sourcing, will also be available for the board in the future.

The Quartz64 model-A is available in two RAM configurations at launch: 

- **4GB LPDDR4 RAM - $59.99**
- **8GB LPDDR4 RAM - $79.99**

As always, you’ll find complete specifications of the Quartz64 model-A, alongside relevant schematics and documentation on the [Quartz64 sub-section of the PINE64 Wiki](https://wiki.pine64.org/wiki/Quartz64). 

In the coming months you will also see us introduce the Quartz64 model-B, a physically smaller board, sharing the same footprint of our ROCK64 computer. The smaller size means this device is great for education, tinkering, personal projects, and similar applications. However, the smaller form factor limits the available IO. For this reason, the Quartz64 model-B will not be used as a development platform for our future devices in consumer form factors. WiFi and Bluetooth are integrated on the Quartz64 model-B. Users will be given a choice of either the BL-602 RISC-V 802.11n and BLE 5.0 module, currently undergoing open-sourcing, or an AP6256 802.11ac WiFi + Bluetooth 5.0 module. I wrote about the model-B at some length in the [April community update](https://www.pine64.org/2021/04/15/april-update-new-developments/), if you want to learn more. 

![](/blog/images/modelBbackandfront-1024x759.png)

**Quartz64 model-B top / bottom (prototype)**

Lastly, I am happy to introduce you to the newest member of the Quartz-line of products: the SOQuartz. The SOQuartz is a compute module that is software compatible and built on the same architecture as the Quartz64 single board computers. The module will share the Quartz64 RAM configuration and host onboard eMMC flash storage. Flash storage can be added via the eMMC socket (it accepts standard PINE64 eMMC modules) or by having it soldered on the back-side of the PCB. The option for a soldered-on eMMC adds a degree of flexibility for industry partners who may wish to standardise a hardware rollout. 

The SOQuartz comes equipped with an Azurewave AW-CM256SM WiFi 802.11ac Bluetooth and WiFi module with an U.FL antenna connector. On the bottom of the PCB you will find the now industry-standard 100-pin high density connectors. This means that it will be possible to use the SOQuartz as a drop-in replacement for the most popular solution on the market.

![](/blog/images/SOquartz-1-1024x746.jpg)

**SOQuartz top (prototype)**

![](/blog/images/SOQuartz-2-1024x837.jpg)

**SOQuartz bottom (prototype)**

I’d like to end by thanking everyone who has helped us create the Quartz64, in particular community developers who have been working on it for the past 3 months. Their feedback and insights made the Quartz64 model-A a much better device. We’re interested, what would you use Quartz64 to create? Are you getting in early to learn about the RK3566 and build the open-source drivers that will make it great? Or will it be exactly what you need to build the project you’ve always dreamed of, after some more hardware enablement? Let us know in the comments.

### PinePhone

**Hardware**

Since last month's update we’ve sent out two iterations of PinePhone keyboard prototypes to developers for the purpose of internal testing and review. I've received the first iteration myself and offered extensive feedback to the product team. As you'd expect from a prototype device, there were some issues. Aside from some relatively minor fit and finish problems, and a few oversights (e.g. the wrong number of holes for LED lights), the biggest problem I encountered was the keyboard’s stiffness. Our first pass at the keyboard membrane resulted in very stiff domes, which made it difficult to plunge the keys. There were also a handful of issues with the electronics, which is something Megi writes about in a post [on his blog](https://xnux.eu/log/). I highly encourage you to  read his blog posts.

![](/blog/images/nextto3ds-1024x768.jpg)

**Front view of PinePhone with keyboard next to a 3DS for scale**

![](/blog/images/nextto3ds2-1024x768.jpg)

**Side view of PinePhone with keyboard next to a 3DS for scale**

Based on feedback from the first prototypes, the second iteration included fixes to all listed issues and improved on the feature-set. New membranes were created and installed, the chassis was improved, and the electronics circuitry significantly reworked. We now also have the source code from the keyboard vendor and will be working with Megi, Samuel and others to make it flashable. Granted no further issues are found with the electronics in testing, we may be moving to production soon - stay tuned. 

Last minute edit and a follow-up to the above: Megi received his keyboard just the other day, and has already managed to get open firmware running on it. I spoke to him briefly in the chat yesterday, July 13th, about his initial impressions of the keyboard; he confirmed for me that the enter and space keys are now well stabilised (an issue on the first prototype) and that keys can be plunged with ease. Moreover, the keyboard’s internal battery can now be detected by Linux, and even display battery levels separately to the PinePhones battery. That said, some issues related to electronics still remain - a short somewhere in the electronics causes dual inputs and ghost inputs. There is also some work yet to be done on the feel of the keys, as there is a degree of inconsistency between rows. Megi is currently exploring the root cause of these problems - ghost-inputs in particular.

{{< youtube id="Kx6B_OL4OJ4" >}}

**PinePhone keyboard running open firmware - by [Megi](https://xnux.eu/)**

One last thing I want to mention with respect to this topic: early feedback from the community indicated that many people would be interested in incorporating additional functionality into the keyboard. As a result of this, there is now a breakout header on the keyboard’s PCB, which will allow you to add LoRa and Qi wireless charging, and potentially also other peripherals in the future. However, due to the limited internal space inside the chassis, this will require soldering and as such is more of a nod towards hardware hackers rather than an end-user feature. In other words, we're making it easy to add the functionality for those who are up-to-the-task.

Speaking of additional functionality, the PinePhone back-cases are coming along but it may take a bit longer than we initially anticipated. We’ve run into some issues, related to current component shortages - the TI wireless charging chip we settled on for the charging back case is currently very difficult to source, and we're not happy with the performance of alternative options. I know that they've been pushed back already a few times, but we really want for the back cases to turn out great. I am leaving you with a handful of pictures of the current progress. 

![](/blog/images/fingerprint-1-1-1-768x931.jpg)

**New prototype of back case for LoRa, fingerprint scanner and Wireless charging - electronics missing in picture**

Before we move onto the software section, I need to shoehorn a short hardware-related notice into this part of the post. A new and improved quick start guide that will ship with future BE PinePhones is now available and has been [uploaded online](https://files.pine64.org/doc/PinePhone/PinePhone_User_Manual.pdf). Credit for the new guide’s layout and illustrations goes to Chris (Funeral). I actually do not know with certainty if PinePhones shipping this month will include this or the older quick start guide version, so if you’re waiting for your PinePhone then please read the one linked above; it is significantly better.  [](https://files.pine64.org/doc/PinePhone/PinePhone)

**Software**

_New release of Plasma Mobile 5.22 \[by [Brian (33YN2)](https://mastodon.online/web/accounts/61817)\]_

Plasma Mobile has seen tremendous progress for the current 5.22 release, and there is a lot still yet to come in Plasma 5.23. As outlined by the [Plasma Mobile June blog post](https://www.plasma-mobile.org/2021/06/10/plasma-mobile-update-june/), a new audio overlay that allows fined tuned control of per-application audio (including the microphone input volume) has landed for next update in October, and there have also been lots of new homescreen improvements such as multiple home screen pages and the groundwork for customizable home screen support. Lots of bug fixes have also landed, with lots more to come in 5.23.

There has also been a lot of work that has gone into the growing list of applications for Plasma Mobile. Two new plasma mobile applications have arrived such as the Mastodon client app called Tokodon, and the new podcast app called Kasts. Also notable is that back in march a YouTube music app called AudioTube, and a YouTube app called Plasmatube were also created. Work is also being done on a Plasma Mobile email client, though that is still very early in development.

![](/blog/images/audio-osd-465x930.png)

**Volume & output control on newest Plasma Mobile is amazing - screenshot via [KDE](https://www.plasma-mobile.org/2021/06/10/plasma-mobile-update-june/)**

_MMS (mmsd-tng) functionality and development \[By Chris (_[_kop316_](https://gitlab.com/kop316)_)\]_

I want to update you all on the state of Multimedia Messaging Service (MMS) on the Pinephone. If you are in a few countries where MMS is frequently used, a lack of this functionality can be a major show stopper for using the Pinephone as a daily driver. I am the author of [mmsd-tng](https://gitlab.com/kop316/mmsd/); mmsd-tng is a backend daemon to support MMS in Linux. In its current state, it completely supports MMS and is currently found in Mobian (Unstable), PostmarketOS, and Fedora repositories! Since it is a backend, any chat application can work with it, or it can run in a stand alone mode, though it isn't terribly useful in this mode. The mmsd-tng front ends I am aware of are:

- [mms2file](https://gitlab.com/a-wai/mms2file),
- [mms2mail](https://gitea.geodock.egeo.net.eu.org/Public/mms2mail)
- [ofono-matrix-puppet](https://gitlab.com/untidylamp/ofono-matrix-puppet).

As for future work, I have been working towards integrating MMS support into [Chatty](https://source.puri.sm/kop316/chatty/-/tree/wip/sadiq/mm-account), to complete MMS support for the Phosh stack. Once MMS support in Chatty is integrated, I will release a _1.0~release_ of mmsd-tng. Modem Manager’s new release (1.18) should also allow mmsd-tng to completely support MMS on carriers that split their MMS and data APN. If you want to keep up with development (or help out), feel free to join the Matrix Room (#opensourcemms:matrix.org) or the IRC channel (#opensourcemms on OFTC), which is bridged to Matrix.

If you have been thinking of contributing to open source development, I highly encourage you to do it! This is my first open source contribution and my previous experience with C is minimal. I can personally attest to the inclusiveness, patience, and professionalism of the Mobian, PostmarketOS, and Purism development teams. At no point was my lack of experience/newness to open source a barrier to my contributions, as all of those development teams are fantastic mentors who want to see me succeed as an open source developer. If you want to contribute, you will find the same welcoming experience as I have.

### PineTime \[by [JF](https://twitter.com/codingfield)\]

Last month, we announced the availability of a new batch of PineTimes in the Store in June, but... that component shortage struck again! The production is currently stopped due to the vendor being unable to provide a part needed for the PineTime - more specifically, the acceleration sensor. This sensor enables features like step counting and wake on wrist rotation, for example. The factory couldn't find another source for this component and provided us with an alternative option - replace the BMA421 with the BMA425! Although the new component is very similar to the old one, we now need to ensure that InfiniTime is working properly with the replacement, and provide an update to support it if needed. This will unfortunately take a bit of time, but 2 units equipped with this new component have already been shipped to me and should have arrived by the time you read these lines.

{{< youtube id="CvT5D0kxoiQ" >}}

**Ezra ([Elatronion](https://youtu.be/CvT5D0kxoiQ)) took a close look at the PineTime earlier this month, check out his video.**

On the development side, a lot of work is happening behind the scenes, with many refactorings, bug fixes and optimizations, mainly related to RAM and flash memory usage. We are also working towards leveraging the external flash memory, which, with its huge size of 4MB, will allow us to store many more pictures, fonts and icons while leaving enough room to add a lot more features to the firmware down the line!

As the project grows, many new contributors have also joined the party - to this date, 58 contributors are working on the project. And, while I was busy debugging a nasty stack corruption issue, these contributors continued their work and created pull-requests with many interesting features: a new watchface, a metronome app, a weather app, UI improvements, and many bug fixes. InfiniTime v1.2, which we plan to release Soon(TM), is looking really good! Keep an eye out for when it drops. 

### PineDio

We are striving to bring our indoor and outdoor PineDio LoRa gateways, as well as the various end-nodes, to the Pine Store as soon as possible. I’ve devoted a lengthy section to all the PineDio gear in the works in [last month’s update](https://www.pine64.org/2021/05/15/may-update-connection-established/), so make sure to read that first in case you missed it. We initially hoped to make the hardware available this month, however it may take a little longer for us to bring the devices to the market. Let me give you a complete run-down of why it will take us a bit longer (if you’re not interested in the details, skip to the third paragraph). 

Just as we were preparing to submit the gateway for certification we learnt that the Realtek Gigabit PHY used on the PINE A64-LTS - that is the brains of the PineDio gateway - can no longer be sourced (if you’re unaware of ongoing global component shortages, please read the [February](https://www.pine64.org/2021/02/15/february-update-show-and-tell/) and [March](https://www.pine64.org/2021/03/15/march-update/) updates housekeeping sections). As a result of this, we had to introduce a new revision of the PINE A64-LTS (v2.0) with the same PHY used on Quartz64 model-A. This was not the only problem we found; the gateway also uses the BL602 WiFi/BLE chipset, for which we still need a working driver in Linux.

Because of these issues we were unable to submit the gateway for certification, but we hope to do so in the coming weeks. Meanwhile we’ve been working on our outdoor gateway. Given how the outdoor gateway chassis are made of aluminium, all the antenna signals - not only for LoRa but also WiFi and BLE - need to be routed to the outside. While it may seem a trivial task, it is not; antenna placement, I’m told, is crucial on these kinds of devices. We are working closely with an antenna vendor to offer an optimal layout within the constraints of the chassis, and I am looking forward to showing it off soon in its final configuration. 

![](/blog/images/LoRa-outdoor-gateway1-598x1024.jpg)

**A peak inside the PineDio gateway chassis - color wires attached to 3x18650 battery holder**

![](/blog/images/LoRa-battery-POE-render.jpg)

**3x 18650 pack (under green bracket) and PoE location (black rectangular box) on the underside**

Lastly, a decision was made to include a 3X 18650 battery holder, placed on the underside of the mainboard, and separated by a metal plate (part of the chassis construction) from the PINE A64-LTS and the LoRa RAK module. Three 18650 batteries will allow the gateway to operate for hours if direct supply of electricity is cut off from the unit. Speaking of power delivery, on the underside you will also find a power over ethernet (PoE) adapter, which I am sure many people will appreciate given the convenience of only running one cable outdoors. The outdoor gateway is shaping up to be a very robust and feature-rich unit.  

I will have more news and announcements concerning PineDio in the coming month, so stay tuned and make sure to subscribe to this blog. 

### Pinecil

It has been a couple of months since we had a section dedicated to the Pinecil in the community update. I now finally have great news to share, which warrants allocating some real estate to the Pinecil. Hackers and tinkerers rejoice - the Pinecil hammerhead set is now available for purchase in the [Pine Store](https://pine64.com/product-category/pinecil/?v=0446c16e2e66). For those who do not know, the hammerhead accessory provides a large surface area for desoldering surface mounted components. The set contains a special threaded tip allowing for securely mounting either a large (20mm x 15mm x 20mm) or small (15mm x 15mm x 15mm) hammerhead. The hammerheads are made out of chromium coater pure blocks of copper, and have excellent thermal conductivity. 

{{< youtube id="cc9V1ZzNZz8" >}}

**Hammerhead in action resting on thermal mat included in the kit**

The purpose of the hammerhead is to provide a sizable area for easily removing surface mounted components - it is effectively a heating surface that may be used in conjunction with or instead of a hot air gun. The set also includes a thermally resistant mat rated at 500\*C, which the hammerheads can be safely placed upon. I honestly feel like this is a great set for anyone who occasionally needs to remove more than a single component from a PCB and doesn’t have a hot air gun on hand. The set is available for $24.99 and if you’re interested I suggest you pick one straight away -  most Pinecil accessories tend to sell out quickly. I am leaving you with two videos of the Pinecil equipped with the hammerhead tip in action above.

![](/blog/images/Pinecil-Hammer-head-kit-768x768.jpg)

**Contents of the Hammerhead kit**

That is all for this month’s update, go forth and comment!
