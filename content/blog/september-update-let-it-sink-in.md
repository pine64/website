---
title: "September Update: Let it sink in..."
date: "2020-09-15"
categories: 
  - "community"
  - "cube"
  - "news"
  - "pinebook-pro"
  - "pinephone"
  - "pinetab"
  - "pinetime"
tags: 
  - "pinebook-pro"
  - "pinephone"
  - "pinetab"
  - "pinetime"
cover: 
  image: "Septbanner2.jpg"
images:
  - "Septbanner2.jpg"
---

![](/blog/images/Septbanner2.jpg)

We have been fortunate to welcome many new members into our ranks over the past 30 days. This is in large part due to the continued interest in the Pinebook Pro and PineTab, which have just shipped, as well as the ongoing massive demand for the PinePhone. By my estimate, come December we will have shipped more PinePhones than OpenMoko and the original Ubuntu Touch smartphones … **combined**. Let this sink in for a minute. 

I’d also like to thank [JF](https://twitter.com/codingfield) for once again providing this month’s PineTime community update.

There is plenty of stuff to get to, so let's get to it!

**This month’s TL;DR:** 

- Shipping is coming along quite well; stay tuned to shipping updates on the forum 
- New Pine Store in the works; not only will it look better but will also support more payment options 
- We’re an Arm ecosystem partner now; Pinebook Pro laptops will be give-aways at this year’s Arm Dev Summit
- Pinebook Pro: production halted temporarily due to LCD panel shortages (hopefully will resume in 2 months time) 
- Pinebook Pro: check out the Fedora 32 community build with a choice of multiple DEs
- PineTabs are being delivered; positive initial reception
- Mobian and Arch Linux builds are now also available for the PineTab
- PineTime dev kits with InfiniTime ought to be available in Pine Store September 20
- PineTime Hypnos - a Zephyr based firmware spotlight
- **PinePhone Manjaro CE available for pre-order September 17**
- PinePhone software development: 13 OSes, multi-boot, and the p-boot bootloader is awesome
- PinePhone camera implementations on Ubuntu Touch; 30FPS viewfinder and Qt 5.12 updates
- PinePhone Megapixels camera postmarketOS app; both main and front cameras working, and taking higher-resolution pictures
- PineCubes are awaiting assembly; should be available in the store later this month 

#### Housekeeping

The first topic on the housekeeping agenda concerns shipping. Generally speaking, this round of shipping is proceeding pretty well. Most DHL shipments have already been dispatched and delivered, as have regular shipments for most destinations bar Europe. For those of you waiting for your device to show up, please make sure to follow the [forum shipping thread](https://forum.pine64.org/showthread.php?tid=11134); I’ll keep posting updates until the dispatch process comes to an end. In summary, I think that the grand majority of devices will be shipped and delivered before the month is up. If you have any questions concerning shipping, make sure to post your question in the aforementioned forum thread.  

Second subject I’d like to touch on in this segment is the announcement that we’re actively working on a new store. It will be a couple of weeks yet before it goes live since we’re redoing everything, including the store database, which means adding all entries and accompanying descriptions manually. Apart from a facelift, the store will also feature alternative payment methods. At this point we’re happy to announce that Stripe will be available when the new store launches. Other services may also be available at the time of launch or shortly thereafter. We’re also working on implementing crypto currency payments - however, for reasons I will not get into, at this time we’re experiencing issues with implementing coin payments. More information concerning the store and available payments will be made available prior to the store’s launch sometime next month. 

![](/blog/images/storepost-scaled.jpg)

**New Pine Store sneak peek**

Another major piece of news is that last month we became an [Arm ecosystem partner](https://developer.arm.com/solutions/infrastructure/ecosystem-partners). This is obviously huge for us, and we are both honoured and thrilled to be invited by Arm to take part in this program. Just this past week additional information about PINE64 has been added on Arm’s website, with annotations to the Pinebook and Pinebook Pro laptops, as well as [an entire dedicated sub-section](https://developer.arm.com/solutions/infrastructure/developer-resources/development-platforms/pine64) concerning our hardware solutions, project’s philosophy and the community. But this isn’t all. For the past month we’ve been working with _Arm Software Developers_ representatives to make Pinebook Pro laptops this year's give-aways at the [Arm Dev Summit 2020](http://devsummit.arm.com/arm-infrastructure). Up-to ten lucky developers being part of the _Arm Innovator Program_ will receive a Pinebook Pro as recognition for their ongoing efforts on the Arm platform. Speaking of the Arm Dev Summit, I suggest you sign up for the event and attend the _Linux_ _AArch64 Laptops BoF_ talk scheduled for October 6, 11:00AM PDT. Lastly I want to give [Robert Wolff](https://twitter.com/fixxxxxxer) from Arm a huge shout-out for being so helpful, accommodating and easy to work with - cheers!

![](/blog/images/Pine64onarmwebsite.jpg)

[**PINE64 on Arm's website**](https://developer.arm.com/solutions/infrastructure/developer-resources/development-platforms/pine64)

Lastly, we’ve been making upgrades to the PINE64 cluster which now powers most of our infrastructure. The most recent upgrade to the cluster will, on the one hand, significantly increase individual nodes’ stability (iSCSI implementation) while, on the other, improve our ability to remotely control and reboot individual ROCKPro64 nodes. This is a significant step forward as we hope to get more services added to our infrastructure in the coming months. I’d like to give Marek (gamiee) a huge shout-out for the time that he put into getting the cluster setup at the datacenter - well done! 

#### Pinebook Pro

I am afraid I have some bad news. Back-to-school programs of large laptop manufacturers, in conjunction with the pandemic-induced production freeze earlier this year, resulted in LCD panel shortages. This in turn has now led us to halt production of the Pinebook Pro for a month or two. We have the laptop chassis, all the components and the PCBAs, but we do not have the LCD panels. To continue production at this time, we would have to buy LCD panels from the open market, and we’re not keen on doing that. Let me explain. When we buy panels directly from a vendor, then we receive a quality assurance that the batch we purchased measures up against standard LCD panel rating. Quality assurance of this sort is impossible when buying from the open market rather than from the vendor directly. Not only would we be paying more for the panels, but we would also be taking a considerable risk that the LCDs will be of a poor or varying quality. 

We suspect that it will take a month or two for the LCD manufacturers to replenish their stock, at which point we’ll acquire suitable panels and Pinebook Pro production will resume. We currently hope to offer pre-orders for at least two batches prior to the Chinese New Year, which begins early February 2021. There is still a sizable amount of ANSI Pinebook Pros available in the Pine Store, which I suspect will last until the end of September; ISO units will, however, remain unavailable for the next two months or so. I will make sure to keep you up-to-date on how the LCD situation looks in the upcoming community update. Were the situation to change suddenly - which is unlikely but not impossible - then I’ll make a separate short post on the subject. 

In other news, I am still waiting for information from developers on whether they can successfully enable HDMI output on the Pinebook Pro’s dock. The HDMI output has been confirmed to work on the BSP kernel, so it is just a question of the mainline kernel supporting the dock’s hardware. It is my understanding that currently, in the newest Manjaro release (which I highly suggest you [check out or upgrade to](https://forum.manjaro.org/t/arm-stable-update-2020-09-08-kde-plasma-and-applications-thunderbird-and-kernels/22955)), the DP alt mode is broken (to fix it - manually install _linux-pinebookpro_ via pacman), which may further slow things down. Regardless, we will not release the dock until we know that it works well with the default software. Simply put, we fear people emailing support or requesting RMA for what they would view as dysfunctional hardware.   

![](/blog/images/fedora-on-PBP.jpeg)

**Fedora 32 with GNOME - image via [Radek Pawlinski](https://twitter.com/r_pawlinski)**

Software wise, we keep looking forward to the release of elementary OS 6, which was announced in last month’s update. If you want to support the elementary project and get your hands on daily builds of elementary OS for the Pinebook Pro, then consider entering their early access scheme. The OS has now been [added to the Wiki](https://wiki.pine64.org/index.php?title=Pinebook_Pro_Software_Release#elementary_OS) and will be made available once elementary OS 6 rolls out. In other software news, I'd like to talk about Fedora for the Pinebook Pro. It has now been 5 months since Fedora’s announcement of support [for PINE64 devices](https://fedoramagazine.org/announcing-fedora-32/), but an official Pinebook Pro build has not been made available to date. Thankfully there is now an excellent community build, which features all core functionality of the Pinebook Pro and uses (from what I can tell) very few patches to achieve this. You also get a choice of desktop environments - including XFCE, GNOME, KDE Plasma and Cinnamon, all of which performed really well in my testing. So, If you are a Fedora fan, then I recommend you give [this community a](https://builds.armdevelopers.com/pinebook-pro/releases/dev/) go. 

#### PineTab

Earlier this month PineTabs were sent and, in most instances, delivered to early adopters. Let me begin by apologizing once again for the 2 week delay in delivering the PineTabs; shipping from Hong Kong remains a burdensome arrangement under the current regulatory regime. The process is a real jigsaw puzzle, where the variables of time, quantity and weight all need to be precisely synced for shipment. With that out of the way, let’s talk about the device itself. For starters, we’ll be monitoring hardware-related feedback over the coming weeks so that if any unforeseen issues are found we’ll have the head-room to apply alterations to the design. Thankfully it appears that there are no major issues - as these would have surely already been documented and brought to our attention. As things stand, all the issues I’ve seen reported are directly related to the work-in-progress status of the available software.

Speaking of PineTab software, we’ve seen a lot of development in the past two weeks. For starters, Mobian - one of the most popular and fastest growing OSes on the PinePhone - announced support of the PineTab earlier this month. I am told (seeing as I don’t have a PineTab myself at this time) that the operating system works really well in both stand-alone tablet mode and when paired with the keyboard. Nightly Mobian releases are [available for download](https://images.mobian-project.org/pinetab/nightly/) and can be booted from either the onboard eMMC flash or a SD card. But there is more; we have also received a great community build of Arch thanks to [Danct12](https://github.com/Danct12). For those of you who do not know, Danct12 is a community developer who brought Arch to the PinePhone. The Arch image is - as you’d probably expect - very cutting edge, and includes much of the quality-of-life improvements present in the PinePhone image. You can find the latest pre-release of Arch for the PineTab by [clicking this link](https://github.com/dreemurrs-embedded/Pine64-Arch/releases/tag/20200910pre).  

![](/blog/images/Mobian-PT1.jpg)

**Mobian on the PineTab - image via [devrtz](https://forum.pine64.org/member.php?action=profile&uid=17348) from [Mobian](https://mobian-project.org/) Project**

While we’re already on the topic of software, let me squeeze in a quick PSA and offer some advice pertaining to the Ubuntu Touch build with which the PineTab ships. As many of you have noticed, the build only reports ~15GB of free flash storage. The reason for this is that the development tablets only feature 16GB of eMMC, as opposed to the 64GB found on the production PineTab units. If you switch over to the _Release Candidate_ channel in the system menu, and apply the update, you’ll have the _User Data_ partition resized to take up all remaining unallocated disk space. Thanks to Dalton from UBports for getting this day-one fix out quickly!

![](/blog/images/Pinetabarch2.jpg)

**Arch Linux on PineTab - image via [Danct12](https://github.com/Danct12)**

Lastly, I currently do not have a date for when we’ll resume production of the PineTab. As I already wrote, we want to gather users' feedback and wait until the current LCD shortage passes (see Pinebook Pro section for details). Since I know many will ask for an approximation - let me tentatively say that the next pre-order round will start no earlier than in one month’s time. In the meantime, I encourage you to sign up to this blog and follow us on our social media accounts to stay up-to-date on the PineTabs software development.    

#### PineTime 

The PineTime dev kits have been out of stock for quite a long time, and many of you have been waiting for the new batch for a long time. Here is some good news: the wait is almost over!

Last month, I explained that we had encountered some difficulties with the programming of InfiniTime on the PineTime at the factory. These issues have now been solved, and the factory sent a sample to Lup and myself to check them out in the picture below.

![](/blog/images/PTkit-768x1024.jpeg)

**New PineTime dev kit - image via [Lup Yuen Lee](https://twitter.com/MisterTechBlog/status/1300972111280783360)**

And it turns out that the result is nearly perfect - the PineTime running InfiniTime works as expected, all the devices are working correctly and the upgrade to a new version of the firmware was also successful!

The only issue encountered involved the memory protection, which was still enabled. This feature is enabled in production devices so that people can’t snoop into an nRF52 gadget and tamper with the ROM, but it is absolutely not relevant in the context of open source software. So we wanted to take this opportunity to disable it at the factory, so that future developers do not need to buy expensive equipment to disable it themselves.

A new sample is en route to Lup's. He should receive it one of these days and hopefully confirm that everything is now alright, and that the memory protection has been removed.

If all goes well, PineTime dev kits should be in stock on September 20 along with the new pogo pins, a new tool that eases the connection to the SWD pads on the mainboard of the watch.

![](/blog/images/pogopins-768x1024.jpg)

**New pogo pin programming tool**

This month, I would like to showcase [_Hypnos_](https://github.com/endian-albin/pinetime-hypnos), a Zephyr based firmware for the PineTime by endian-albin. He made a lot of progress these last few weeks and the first version of [the firmware](https://forum.pine64.org/showthread.php?tid=11405) was released a few days ago. The most interesting feature of Hypnos is that it supports the same bootloader and OTA procedure as that used in InfiniTime. It means that it is now possible to switch from InfiniTime to Hypnos and vice-versa using BLE. In the future, PineTime users will be able to choose the firmware they want to use and even easily switch from one to another as easily as Pinephone users distro hop between many Linux distributions!

![](/blog/images/Hypnos-768x1024.jpg)

**Hypnos running on the PineTime**

#### PinePhone

Let’s get the piece of information everyone is waiting for out of the way first: the Manjaro Community Edition PinePhone will be available for pre-order this Thursday, September 17. In the event you didn’t catch [the announcement](https://forum.manjaro.org/t/18369), here is a quick recap: the Manjaro community edition will ship in a custom presentation box designed by Manjaro’s development team, and the PinePhone itself will feature a sleek-looking Manjaro logo on the back-cover (see renders for reference). The device will also ship with the newest PCB revision (1.2a) and be available for pre-order in two hardware configurations: 

- $149 standard version — featuring 2GB RAM and 16GB eMMC internal flash storage. 
- $199 convergence package — equipped with 3GB RAM and 32GB eMMC flash storage as well as a bundled USB-C dock. 

Our friends at Manjaro currently offer three different flavours of their mobile OS for the PinePhone - with Lomiri, Phosh and Plasma Mobile. While it remains to be seen which the Manjaro team will settle for, all images are great and if you are a fan of the project you probably will want to try all three, regardless of which build ends up shipping with the device. For those of you who already have a PinePhone, I strongly suggest giving all these builds a go - [click here](https://osdn.net/projects/manjaro-arm/storage/pinephone/) to head over to Manjaro’s PinePhone CDN. Now, onto other software news. 

![](/blog/images/manjaroCE-header.jpg)

There is currently so much ongoing software development that I will not be able to cover all the important strides made in the past month. There is simply too much stuff happening across many projects on a nearly daily basis. So, instead, I will focus on the three things I found the most interesting. To this end, hands-down the coolest of all recent developments is [Ondrej (megi) Jirman’s multiboot image](https://forum.pine64.org/showthread.php?tid=11347), which allows one to boot multiple phone distros from one installation (eMMC flash or SD card). It features a very snappy, intuitive and surprisingly polished bootloader - called [the p-boot](https://xnux.eu/p-boot-demo/) - that appears instantaneously after you power on the PinePhone. All installed distros share the newest kernel (5.9), modem power management and latest Crust firmware. Needless to say, I feel that this a very valuable tool, especially at this early development phase of bringing the software up, as it allows users to check out numerous popular OS builds; moreover it exposes users to builds they would otherwise likely omit, such as Lune OS or Maemo Leste. It currently only supports PinePhones with PCB revisions 1.2 and 1.2a, but megi has publicly stated that future iterations of the image will also support Braveheart (1.1) PinePhones soon. I strongly suggest you give it a go. 

![](/blog/images/pbootdetails.jpg)

**p-boot details - screenshot of [megi's website](https://xnux.eu/p-boot-demo/)**

The second thing I’d like to bring to your attention is the array of improvements made to the camera. In this respect there are two OSes that truly stand out right now - Ubuntu Touch and postmarketOS. While many distributions already have the camera enabled, the viewfinder experience and picture quality remain suboptimal. This, however, is about to change thanks to the awesome work from the UBports development team, which demonstrated the viewfinder running at steady 30FPS and taking better-looking pictures. Moreover, Ubuntu Touch - which already received an incremental performance improvement patch recently - will be seeing a move to QT 5.12 in the foreseeable future. This will result in a major performance improvement of the operating system; this is something I can vouch for, since I got a chance to experience Ubuntu Touch with QT 5.12  just the other week. 

{{< youtube id="0bqy8Mzm4lw" >}}

**Viewfinder on Ubuntu Touch - via [Marius Gripsgard](https://twitter.com/Mariogrip/status/1302410923383103488)**

Going back to the ongoing camera enablement efforts - Martijn from postmarketOS has been working on a camera application that supports both the main shooter as well as the forward-facing selfie camera. But there is more, not only does the front and main shooters work, the app allows the main camera to take higher resolution pictures (1080p) by default. You can also change the camera settings by editing _/etc/megapixels.ini t_o your liking_,_ which also includes altering the front camera’s setting, allowing it to capture 1600x1200 still images. The application, which Martijn called Megapixels, should be making an appearance on postmarketOS today, and I suspect that other distributions will be porting it to their builds soon enough.  

![](/blog/images/backcam.jpeg) ![](/blog/images/frontcam.jpeg)

**Front and back camera on the PinePhone - images via [postmarketOS](https://twitter.com/postmarketOS/status/1305608431123009537)**

Lastly, I want to give a shoutout to Adam Pigg, who has been working on a port of SailfishOS for the PinePhone (Yes, I know, it’s not fully FOSS - put the pitchfork down and keep on reading). I have recently given SailfishOS a try and I must say that I am very impressed with both how smooth, functional and all-around polished the PinePhone build is. Opening applications, swiping between active panels, pulling up and down the application and task drawers all feel very smooth. Same goes for browsing the web (including LTE) or watching local video playback. It is clear to me that a lot of work has gone into this community port of SailfishOS, and I think more people ought to give it a proper go. The latest build of SailfishOS can be easily [flashed using a special script](https://github.com/sailfish-on-dontbeevil/flash-it/) to a SD card or Jumpdrive-mounted PinePhone. 

#### PineCube

A large stack of PineCube PCBAs is currently awaiting assembly. All that is currently missing is a delivery of the plastic frames, which keep the three PCB elements in their respective positions and give the device its cube-like appearance. This last piece of the puzzle should be arriving this week, which means that PineCubes should be available in the store next week! As is the case with many of our devices - especially ones that need to build up a community around them - the PineCube will initially be sold with a disclosure that it is strictly meant for developers and enthusiasts, willing to work on software enablement for the device. To learn more about the PineCube and its features I invite you to read [last month’s update](https://www.pine64.org/2020/08/15/august-update-getting-into-a-rhythm-and-not-slowing-down/), where I went into details listing the device’s specifications and planned add-on peripherals. 

{{< youtube id="ex38i3SvJlc" >}}

**PineCube presentation box**

I leave you with a short movie showing off the packaging box the PineCube will ship in. I trust you’ll enjoy it.

That is it for this month!
