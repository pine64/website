---
title: "May Update: PineTab pre-orders, PinePhone Qi charging & more!"
date: "2020-05-15"
authors: ["Lukasz Erecinski"]
categories:
  - "news"
  - "pinebook-pro"
  - "pinephone"
  - "pinetab"
  - "pinetime"
tags: 
  - "pinebook"
  - "pinebook-pro"
  - "pinephone"
  - "pinetab"
  - "pinetime"
cover: 
  image: "PineTab-Header.jpg"
images:
  - "/blog/images/PineTab-Header.jpg"
---

![](/blog/images/PineTab-Header.jpg)

With the PinePhone and Pinebook Pro production well under way and shipping in just a few days time, we’ll now be turning our attention to the other projects we have in the pipeline. There is a fair bit of material to cover this month - the main piece of news, however, is that we’ll be taking pre-orders for the PineTab at the end of this month!  

This may be the longest blog entry in some time, so let's get to it.

**TL;DR of this month’s community update:**

- Moving to PINE64 cluster will be completed by this time next month; expect community services outages
- Shipping Pinebook Pros and PinePhones this month; don’t spam support/ info emails please
- We’ll be accepting payments in cryptocurrencies soon 
- PineTab pre-orders start this month and ships with UBports’ Ubuntu Touch; please subscribe to blog for info when pre-orders go live
- PineTab adapters for individual and industry users; LTE, SSD, LoRa and RTL-SDR available soon
- PinePhone Ubuntu Touch OTA and factory image - a quick chat about the software
- PinePhone multi-OS bootloader is coming; many OSes showing signs of maturing
- Wireless charging coming to the PinePhone via add-on / using pogo pins
- A large (5000mAh) battery case for the PinePhone is being explored
- You will be able to support smaller PinePhone projects soon by buying their project branded case-backs
- Pinebook Pro - one week shipping delay explained
- Pinebook Pro you can now watch Netflix on Manjaro; many OS releases become available including official Debian support! 
- Pinebook Pro USB-C dock details locked in; spare parts are now in the PINE Store
- Pinebook (original) gets a facelift; we’re committed to the $99 price-tag
- PineTime can now sync on Sailfish OS; app will be ported to Ubuntu Touch  

#### Housekeeping

Moving community services over to the PINE64 cluster has hit a couple of roadblocks. As a result the process has been much slower than originally anticipated. While [our IRC has already been moved](https://forum.pine64.org/showthread.php?tid=9750&pid=64842#pid64842) to the cluster (thank you fire219 and Gamiee!) all the heavy lifting is still ahead of us. The good news is that we’ve now ironed out many of the core issues and expect to have everything moved in a little under a month from now. Since this will be a big undertaking, you should expect disruptions to various community services as the process begins. I’ll make sure there is a sufficient heads-up for when the next part of the move takes place. Keep an eye out for updates in the [news section](https://forum.pine64.org/forumdisplay.php?fid=2) on the forum.

![](/blog/images/photo_2020-05-15_12-48-55.jpg)

**One of the PINE64 Cluster nodes with a 1TB NVMe SSD mounted in the PCIe slot**

The next topic on the housekeeping agenda concerns shipping of the current PinePhone and Pinebook Pro production batches. Both devices are currently being assembled and should be ready for shipping in a matter of days. **We are currently expecting Pinebook Pros with Manjaro to start shipping after May 22 and UBports CE PinePhones after May 26.** However, with the Hong Kong border opening first on 7 June (at the very earliest) we had to pull off some magic to make shipping happen in the first place. This means there is a completely different logistics process in place for current shipments; on a purely human level, this will be a stressful time for the logistics and shipping teams, and therefore it would be greatly appreciated if you’d turn to us in the chat, forums or social media for updates rather than bombard info or support emails requesting updates. Thanks!

![](/blog/images/photo_2020-05-15_12-41-55-1.jpg)

**PinePhone UBports CE being assembled**

In other news, we recently ran a poll on [Mastodon](https://fosstodon.org/web/statuses/104112261219333071) and [Twitter](https://twitter.com/thepine64/status/1257418046915870726) asking whether you’d be interested in using cryptocurrency for PINE Store payments. On the whole, approximately a quarter of all respondents expressed interest in using such payment options. We're now happy to announce that we’ll be accepting cryptocurrency payments (BTC, BCH, ETH and XRP) in the very near future. The payment infrastructure is currently being set up, and should be available as an option at checkout starting next month. 

\[edit\] We no longer intend to support cryptocurrency payments at this time.

Lastly, a quick word about our Wiki. If someone would find the time for tidying and adding information to the relevant sections then I’d be very thankful (as I do not currently have time for that). More specifically, the ROCK64, PINE A64 and SOPine sections need a fair bit of editing and their OS release lists need to be cleared of ancient software and new OS’ should be added. Apart from this, I’d also appreciate it if someone would review the release sections for the Pinebook Pro and ROCKPro64 - many new OS options are still missing. Anyone can do the above using their forum login and password. Thanks in advance!  

#### PineTab pre-orders

With the PinePhone UBports Community Edition and Manjaro Pinebook Pro batches now shipping, we turn our attention to the PineTab. If you follow this blog regularly, then you already know that the tablet has been stuck in a production limbo since summer last year. The decision to postpone PineTab production was made with the purpose to prioritize assembly and shipment of Pinebook Pro and PinePhone batches - as these are PINE64 flagship devices. In light of the global events, which caused subsequent logistics turmoil, production was pushed back nearly 9 months. With the COVID19 pandemic subsiding in China, and factory lines reopening for business, we’re now happy to announce that **we’ll be taking orders for the PineTab later this month.**

Although we’re skipping any formal naming of this PineTab batch, I need to underline that this is a limited-quantity pilot-production run. In other words, these PineTabs are similar in nature to Braveheart PinePhones - they are aimed at early adopters who understand the implications of purchasing an early production-run device. I have written a lot over the past 9 months about the PineTab, and about the gradual improvements we made to it and its keyboard while we waited for a suitable moment to start production. I suggest you go back and read the relevant posts for more details ([https://www.pine64.org/tags/pinetab/](https://www.pine64.org/tags/pinetab/)). 

![](/blog/images/pinetab_KB_P64_UT.jpg)

**PineTab With keyboard attached**

Here is a quick run-down of the device's specs; the PineTab has a 10” 720p IPS LCD panel and features the same quad-core A64 SoC and 2GB LPDDR3 RAM used in the PinePhone. It also features the same 2Mpx front-facing and 5Mpx rear cameras that the phone uses. It ships with 64GB eMMC flash storage, and capacity can be expanded using a SD card (which can also be bootable) or a SSD via an optional M.2 adapter. You also get a full-sized USB 2.0, a USB-OTG and digital video output. This is paired with a large 6000mAh battery that can be charged via Micro USB or the barrel plug. The tablet can be used in conjunction with a magnetically attached backlit keyboard that also doubles-up as a cover and stand. 

**Pricing Details:**

- The PineTab - $99.99
- The magnetic backlit keyboard - $19.99

![](/blog/images/photo_2020-05-15_15-01-31.jpg) ![](/blog/images/photo_2020-05-15_15-01-33.jpg)

**PineTab keyboard doubles-up as a cover case**

Software-wise the PineTab is convergent with both PinePhone and Pinebook software releases. It will therefore, in time, run most mobile operating systems developed for our platform as well as popular desktop OS options. I am also certain that the number of choices will explode after the first batch gets into early adopters’ hands, and that we will see more desktop-oriented releases with touch input capabilities very soon. For this first batch however, we have decided to ship the PineTab with UBports’ Ubuntu Touch. The reason for this choice being that Ubuntu Touch works well for a traditional tablet use-case and, at the same time, converts into a more traditional desktop experience when the magnetic keyboard is attached. The transition is quite seamless and, frankly speaking, rather magical when you see it happen for the first time; check out the video Marius Gripsgard from UBports sent over showcasing this.

{{< youtube id="Ii6lAjgfW3c" >}}

**UBports Ubuntu Touch runs so well on the PineTab - you need to watch this**

We are also making an adapter board for the PineTab that will broaden its use-case application potential significantly. The adapter allows expansions to be mounted inside the PineTab chassis. Each module can be easily installed and swapped out by the end-user - all it takes is removing the tablet's back cover and undoing a single screw. To make it clear, you can only add one type of additional functionality to the PineTab at a time. That said, multiple expansions can be installed onto the adapter board simultaneously - for instance, a SSD and LTE module can be simultaneously mounted, but only one or the other can be used at a time. 

Here are the expansion options we have in store for the PineTab:

- M.2 SATA SSD add-on
- M.2 LTE (and GPS) add-on
- LoRa module add-on
- RTL-SDR module add-on

![](/blog/images/photo_2020-05-15_12-41-31.jpg)

**The PineTab expansion adapter board**

We hope that this selection of expansion modules will make the PineTab not only interesting to private end-users but also commercial and industrial customers. Especially when paired with LTE or LoRa functionality, I can easily imagine the PineTab being used as a point-of-sales terminal or an in-field device. With its large capacity battery, and thanks to all the optimizations done for the PinePhone, the PineTab can easily last a full work day. You can expect the SSD and LTE adapter functionality to already work on the PineTab, granted you use the same LTE modem already supported by PinePhone software. Implementations of the LoRa and RTL-SDR modules into existing OSes will, as always, depend on developers from the different partner-projects. Pairing all this functionality with an accessible asking price, we cannot wait to see how end-users will employ this multifunctional device. 

More information about the PineTab will be coming very soon, so please subscribe to this blog so you’ll be alerted when pre-orders go live later this month. 

![](/blog/images/photo_2020-05-15_12-41-27.jpg)

**PineTab with LTE installed in the adapter** 

#### PinePhone

Let me begin by acknowledging the amazing work that the UBports team poured into delivering a great OS image to the factory. They really put a lot of effort into shipping a polished build. The most important feature of the OS image is the inclusion of OTA update capability. The PinePhone now officially supports OTA updates on Ubuntu Touch, which means that users will be able to update their devices without ever having to reflash the OS. All you’ll ever have to do is navigate to settings menu -> update and fetch the newest build. Moreover, if you decide to connect the PinePhone to WiFi on initial boot-up, then you’ll be prompted to update your Ubuntu Touch installation once you complete the setup wizard.

I’ll go into more details about Ubuntu Touch on the PinePhone closer to delivery date and in a separate post, or better yet I may ask a UBports developer to write the post; what I will say at this time is, devs expect the day-one update to include most if not all key features bar the camera functionality (which will take a little longer to implement properly). I have a strong sense that many of you will be very impressed with the quality and performance of this build. For those of you who have Braveheart PinePhones - you can download the newest Ubuntu Touch image for the PinePhone [here](https://ci.ubports.com/job/rootfs/job/rootfs-pinephone-systemimage/).

https://www.youtube.com/watch?v=-MXOgb-U2jI

**Martijn Braam from postmarketOS showcases UBports CE edition factory image**

Since we’re already on the subject of software, I’d also like to give a huge shout-out to Martijn Braam from postmarketOS, who has put together the factory test OS image. For those who do not know, the factory test image runs a custom build of postmarket OS with the newest Linux kernel. It is now a feature complete and comprehensive test suite, which includes all radio connectivity, all sensors and inputs as well as both cameras. In other words, it tests all aspects of the device before it flashes the OS internal flash memory. If you want to check it out, and I know many of you Linux geeks love this sort of stuff, then here is the [link](https://images.postmarketos.org/pinephone/pine-pinephone-20200501-factorytest43.img.xz). 

In other notable software news, [Danct12](https://danct12.github.io/) shared a photo of a multi-boot menu on the PinePhone. While this isn’t the first solution of this kind shown-off on the PinePhone, this one comes from the devs behind [Jumpdrive](https://github.com/dreemurrs-embedded/Jumpdrive), and therefore I find it likely this project will be brought to fruition and well maintained. The multi-boot implementation is said to also support both eMMC and SD. Multi-booting is a piece of functionality that many users have been asking for some time, and I expect that once DanctNIX folks make this available it will be universally used by most PinePhone owners. We may even choose to install it on the factory floor in the future for general (non-CE) PinePhones. Let me know what you think in the comment section.  

![](/blog/images/bootloader-1.jpeg)

**PinePhone multi-OS bootloader via [Danct12](https://twitter.com/RealDanct12/status/1259936739855962112/photo/1)**

We have also seen a lot of progress, including significant performance improvements, on a number of OSes. It would take me too long to list every single improvement made across all the available builds, so instead I’ll focus on some of the highlights: Sailfish OS and Nemo Mobile can now make phone calls and feature a working web-browser (and run remarkably well!); postmarketOS’ makes it now possible to boot X86 PCs (and theoretically also the Pinebook Pro) from a virtual drive on the PinePhone; a-wai, the developer behind the popular Debian+Phosh build, has christened the project [_Mobian_](https://forum.pine64.org/showthread.php?tid=9850) - the recent Mobian build implements crust deep-sleep allowing the PinePhone to run for upwards of 12 hours with radio (WiFi and LTE) connectivity enabled; lastly, [Jolla is asking](https://twitter.com/JollaHQ/status/1260220618525597698) you to let them know if you’d like official SailfishOS support for our platform - I gently suggest you do so if you’re remotely interested in running Sailfish OS on your PinePhone.  

In PinePhone hardware news, we’re happy to announce that Qi wireless charging is coming to the PinePhone in the very near future. We’re currently working out the exact details of the charging coil implementation and making a series of related decisions, such as for instance whether we should bundle a charging plate with the add-on. If you have a suggestion then make sure to leave a comment in the section below. What is certain, however, is that this will be a universal Qi wireless charging implementation utilizing the PinePhone’s pogo pins. This also means that if you already have a Qi charging surface or station for your current phone then this implementation will, in all likelihood, ‘just work’ with the PinePhone. I should have more details regarding this subject in next month’s community update; we are currently expecting the wireless charging add-on kit to be available in approximately July this year. 

![](/blog/images/photo_2020-05-15_12-42-14-1.jpg)

**Here's the Qi charging coil we'll be using**

We have also begun exploring creating a battery case for the PinePhone. Although we’re confident that the PinePhone will eventually be capable of providing end-users with a full workday battery life, the reality of it is that - especially under heavy usage scenarios - battery life on the PinePhone may never match flagship Android devices. We understand that some users may require to use their PinePhone for hours at a time (on-screen time), and one way to remedy this situation is by adding a larger battery to the phone. To be precise, we’re currently exploring creating a 5000mAh battery case that would more than double the devices on-screen time. Keeping in mind that we will, eventually, reach ~16-20 hours standby time on the PinePhone via software improvements - let me know in the comments if such a battery case is something you’d be interested in.   

One other hardware-related topic I wish to briefly touch on concerns the optional PinePhone keyboard, which [we announced](https://www.pine64.org/2019/12/05/december-update-thank-you-for-2019/) a couple months ago. Long story short, presently isn’t the right time for us to take on this challenge - molding for the keyboard is very expensive and face-to-face communication with the vendor is currently impossible due to the closed borders. Investing effort and money into this endeavour at present time, when we cannot evaluate the hardware’s progress remotely, would be a risk that we’re not willing to take. So instead we’ll focus on other hardware and peripherals, and revisit the PinePhone keyboard concept when these uncertain times come to an end. It will happen, I assure you, but not now.   

The last topic in this section I wish to discuss regards support for individual PinePhone developers and smaller projects. We have been thinking about this internally over the past couple of months and arrived at the conclusion that it will be very difficult for us to run full-blown campaigns, such as the current one for UBports, for smaller projects. Here is our solution: we will sell custom back-covers for smaller projects featuring their logos in the store. We will charge $15 for such a cover, out of which we will donate $10 to the project. The regular [plain cover](https://pine64.com/product/pinephone-back-cover/), already available in the store for $5, will obviously remain an option to those who just want a replacement back for their phone. We hope that this will help smaller projects have a chance to grow and thrive.  

#### Pinebook Pro 

The Pinebook Pro production-run featuring the Manjaro KDE Plasma build will soon be heading out to end-users. We had to delay shipping by a week due to an unforeseen complication at the factory. If you’re interested in the details of the delay then read on, if you’re not the skip to the next paragraph; the factory testing image, which is built on a custom Android image booted from a SD card, failed to load up using the u-boot included with the Manjaro OS image which has already been flashed to eMMC. Prior to shipping the build out to the factory a couple of weeks ago, the developers and I diligently tested booting OS images from SD and encountered no issues. We did not, however, account for booting any Android images (this is my fault - I should have thought about it). Regardless, all Pinebook Pros now need to be disassembled so that their [eMMC disable](https://wiki.pine64.org/index.php/Pinebook_Pro#Pinebook_Pro_Internal_Layout) switches can be flipped for testing purposes. As you can well imagine, with many thousand units required to undergo the tests, this will require time and hence the shipping delay. 

Apart from this short delay in shipping, I have nothing but good news for all of you waiting for your Pinebook Pros to arrive. Thanks to the work of Spikerguy and Strit from the Manjaro ARM team you are now able to watch Netflix, Amazon and other Widevine DRM protected content on Manjaro KDE Plasma in Chromium. I am happy to report that playback of both Netflix and Amazon content is smooth even when viewed at full HD resolution, and the process of installing the [custom 32bit Chromium build running in a docker container](https://forum.manjaro.org/t/arm-testing-update-2020-05-05-icu-plasma-mobile-chromium-docker-pinebook-pro-firmware-and-kernels/140644) has now been streamlined for end-users. This is a welcome addition to the already incredibly polished Manjaro OS image, which I wrote at length about [last month](https://www.pine64.org/2020/04/15/april-update-ce-fcc-software-update-and-diy-router/). I can now say with complete confidence that the Pinebook Pro has become a daily driver for light-to-moderate workloads.

![](/blog/images/Netflix.jpeg)

**Netflix played back on the Pinebook Pro - via [Strit](https://forum.manjaro.org/u/strit/summary) from Manjaro ARM Team**

On the subject of software, the single most important release for the Pinebook Pro this month is Debian. Yes, that’s right, the Pinebook Pro - alongside other PINE64 devices - now has [official Debian support](https://d-i.debian.org/daily-images/arm64/daily/netboot/SD-card-images/). This is obviously great news, but I still strongly suggest opting to use the [Debian Installer](https://github.com/daniel-thompson/pinebook-pro-debian-installer) for the Pinebook Pro created by [Daniel Thompson](https://github.com/daniel-thompson) instead. The installer allows you to build and run a feature-complete mainline Linux Debian OS image in no time without hassle. In other software news, ayufan has now a series of mainline Linux [pre-release OS images](https://github.com/ayufan-rock64/linux-build/releases) available for the Pinebook Pro and other PINE64 devices. The notable addition to the Pinebook Pros line-up of available software is Ubuntu 20.04 with GNOME desktop. Please keep in mind that, at the time of writing, these images are in a pre-release state, which means that some (or all!) aspects of the software may not be functional.  Lastly, since I am asked at least twice a week about [Kali Linux](https://www.offensive-security.com/kali-linux-arm-images/) on the Pinebook Pro, I am happy to report that new OS images have just been released and are bootable from both eMMC and SD. From the little time I’ve spent using Kali on the Pinebook Pro, I am happy to report that it runs well and smoothly and - from what I can tell - all the tools you expect this distribution to offer work as intended. 

![](/blog/images/PRO-KEYBOARD_ANSI-01.jpg) ![](/blog/images/PinebookPro-ISO-Keyboard-1.jpg)

**Both ANSI and ISO keyboards are available in the Pinebook Pro [spare parts](https://pine64.com/product-category/pinebook-pro-spare-parts/) section**

In hardware news, we’ve now settled on our Pinebook Pro USB-C docking station I/O connectivity and the general form-factor of the dock. I’d like to thank all of you for offering your suggestions and feedback in the comment section regarding the dock - we’ve taken your suggestions onboard. The dock will be attached to - or slid under - the bottom of the Pinebook Pro chassis, with all I/O facing towards the back of the laptop. The docking station will offer 3x full size (A) USB 3.0 ports, a Gigabit Ethernet port, full-sized and micro SD card slots, as well as both a digital video and a VGA output. The dock will also be capable of delivering power to the Pinebook Pro via the USB-C connection and it itself will be powered using a USB-C PD cable. We are currently waiting for the final design of the dock, and I hope to be able to show you photos of it next month. 

Lastly, spare parts for the Pinebook Pro are now also [available in the PINE Store](https://pine64.com/product-category/pinebook-pro-spare-parts/). Both ANSI and ISO keyboard segments are available for backorder as we await for these spare units to arrive to us from the Pinebook Pro factory. 

#### Pinebook 

As I already wrote in last month’s post, the original Pinebook 11.6” will soon be making a return to the PINE Store. I do not have a firm date just yet, but it should be soon after the upcoming pre-orders of the PineTab come to an end. We’ll also be making a couple of aesthetic changes to it - both to freshen is up as well as bring its looks in-line with our remaining products. The Pinebook will now come in a sleek all-black chassis and, similarly to its big brother, feature no branding on the case except a PINE64 logo on the SUPER key. We’ll also be tweaking the keyboard layout slightly to bring it closer in-line with the one used on the Pinebook Pro. 

In terms of other changes, future Pinebooks will ship with an IPS 768p LCD panel and Manjaro with XFCE. We feel that the 1336x768 resolution is a better fit for both the small Pinebook screen as well as the A64 SoC. This is a good quality 768p IPS panel and, when paired with the excellent mainline Linux build of Manjaro XFCE, it makes the Pinebook feel snappy and responsive. There is, of course, also a financial aspect to this decision - namely, component pricing has gone up significantly in recent months, and the $99 price-tag (which is already subsidized by the PINE Store) would be impossible to maintain with a higher resolution panel. 

The $100 price-tag is important for us to maintain because we have already begun on building up a portion of upcoming OG [Pinebooks for charity](https://www.pine64.org/2019/08/19/its-time-to-start-giving-back/). More information on the Pinebook and how we will start on our project to help close the digital divide coming next month - stay tuned.

#### PineTime

I’ve written about the PineTime software progress at length in the past two months, showcasing the [smartwatch’s OSes](https://www.pine64.org/2020/03/15/march-update-manjaro-on-pinebook-pro-pinephone-software/) and the amazing community driving them. In March I wrote that we’ll be looking to have the PineTime supported across both Linux mobile OS and Android; two months later, the PineTime is able to communicate with both mobile and desktop Linux as well as Android. Pretty amazing, isn’t it?  Adam Pigg, one of the developers working on the Sailfish OS port for the PinePhone, worked together with JF and other PineTime developers to include core smartwatch functionality into an existing Sailfish OS application called Amazefish. The PineTime can now sync time as well as receive notifications from any Sailfish OS phone, which includes the PinePhone of course.

{{< youtube id="EMk7tB6bh-4" >}}

**PinePhone and PineTime chatting away! - via [Adam Pigg](https://twitter.com/adampigg/status/1255826610147725314)**

This Sailfish OS application will be ported to Ubuntu Touch and, in time, maybe also other Linux mobile operating systems. I suspect that while it may be possible to port this application to other Qt based systems - such as KDE Neon, Manjaro or even NEMO Mobile - we’ll need something else for systems using Phosh and GNOME as front-ends. In a recent tweet [Lup Yuen Lee](https://twitter.com/MisterTechBlog) implied that he will be using [gotk3](https://github.com/gotk3/gotk3) to build a GTK3 companion app for the PineTime. In the end, I am certain that a number of solutions will be available to sync the PineTime with your PinePhone or Android phone. As for the latter, I’ve now reached out to the Gadgetbridge developers and they'll be supporting PineTime on the Android platform. 

  
  

That will be all for this month’s update - comment away!
