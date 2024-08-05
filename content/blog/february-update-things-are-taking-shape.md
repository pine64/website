---
title: "February update: things are taking shape"
date: "2023-03-01"
categories: 
  - "community"
  - "pinebuds"
  - "pinecil"
  - "pinephone"
  - "pinephone-pro"
  - "pinetab"
  - "pinetime"
  - "quartz64"
  - "risc-v"
  - "rock64-2"
  - "rockpro64"
  - "soquartz"
  - "star64"
tags: 
  - "pinephone-keyboard"
  - "pinephone-pro"
  - "pinetab2"
  - "quartz64"
  - "soquartz"
  - "star64"
cover: 
  image: "Feb-update-header.jpg"
images:
  - "/blog/images/Feb-update-header.jpg"
---

![](/blog/images/Feb-update-header.jpg)

Let me start by apologizing to everyone for skipping yet another monthly community update. This has largely been my fault as I was rather busy in January and following FOSDEM at the start of February I found myself occupied with things related to the EU store. I hope for things to go back to normal now; you can expect future community updates at the end of each month as per usual. Again, I apologise, mea culpa. 

I hope that this month’s update and the news it brings will more than make up for the wait: the Nestflash section is absolutely packed this month, we’re revealing PineTab2’s pricing and SKU variants (both of which I’m sure you’ll be pleased with), announcing that Star64 will be available in the next 6 weeks (or so) and report on all the work that has gone into PinePhone (Pros) development in the recent two months … and much more

Let's get to it.

You can watch the synopsis of this month’s community update on YouTube (embedded below) as well as on [Odysee](https://odysee.com/@PINE64:a) and [PeerTube](https://tilvids.com/accounts/pine64tilvids/video-channels). To stay up-to-date with PINE64 news make sure to subscribe to this blog (subscription widget at the bottom of the webpage), follow the [PINE64 Telegram News channel](https://t.me/PINE64_News), the [announcements channel in Discord](https://discord.gg/pine64) as well as our [Twitter](https://twitter.com/thepine64) and [Mastodon](https://fosstodon.org/@PINE64).

I’d like to thank [Alex](https://twitter.com/AlexRob12252696) (clover), [JF](https://twitter.com/codingfield), [Danct12](https://twitter.com/RealDanct12), [William Starkey](https://fosstodon.org/@thanosengine), [Alex Horner](https://github.com/alexhorner), [River-Mochi](https://github.com/River-Mochi), [Biktorgj](https://github.com/Biktorgj) and [PizzaLovingNerd](https://www.youtube.com/channel/UCmGcm7dhEjS9CIOsOOv8y6w) for their contributions to this community update.

N.B. Comments on the blog post need to be in English and follow our [Community Rules and Code of Conduct](https://forum.pine64.org/showthread.php?tid=13209).

{{< youtube id="rN1gv1ttJAs" >}}

**Video synopsis of this month's update**

## TL;DR

- Housekeeping
    - FOSDEM was great - thank you to all who came and chatted with us at the stall
    - Pine Store is getting back to normal following CNY 
    - Next quarterly community Q&A on 17 March at 20:00 CET - be there or be square
    - PINE64 EU full restock on March 1st
- Newsflash
    - New release for R-Cade for Rock64, RockPro64 and Pinebook Pro is excellent - you need to try it 
    - PineSAM is a BLE app for the Pinecil V2 that allows you to change your Pencil V2 settings remotely! 
    - SOQuartz patches for PCIe2, video output, gpu, HDMI sound were merged into mainline kernel 6.2
    - SOQuartz is getting popular - MC Server Hosting share their experience with the module and BLADE
    - An awesome rugged 3D printed Pinecil case 
    - Issues with ANC in PineBuds Pro’s left earbud can be fixed by reflashing firmware; work on open firmware going strong & offers good sound quality
    - Significant progress on porting Linux to the 0x64 & video with instructions on how to flash the board
    - The new GAN 65W PinePower PSU now in the Pine Store
- PineTab2
    - PineTab will be available in two SKUs: 4GB RAM / 64GB eMMC & 8GB RAM / 128 eMMC
    - Pricing: **4GB/64GB version USD $159 & 8GB/128GB version $209**
    - First impression of the PineTab2 - most refined Linux-capable hardware from PINE64; very high quality all around and a major step-up from the original
    - PineTab2’s keyboard impressions - very good keyboard, sturdy and hefty stand and solid key backlight
    - PineTab2 software more mature than many of you expect - thanks to the work on Quartz64 and SOQuartz by the community; only a few bits missing
    - FOSDEM demo ran DanctNix Arch + KDE Plasma Desktop and was well received
    - Launch window – sometime in April, but no promises 
- Star64
    - We expect to have the Star64 **available in March or beginning of April**
    - We had a working demo of Debian with XFCE at FOSDEM (thanks to ayufan)
    - There is much interest in RISC-V platform and Star64 in particular
    - The software on RISC-V is in early stages - I share my experience 
    - Star64’s significance: we believe that affordable RISC-V hardware will drive Linux development on the platform 
- PinePhone (Pro)
    - So many PinePhone (Pro)s at FOSDEM! 
    - Megi’s newest keyboard firmware brings a 30 fold power reduction consumption, increasing standby time from 23 days to nearly 1.8 years
    - Megi’s 6.1 kernel brings many improvements - notably 60Hz refresh-rate on the PinePhone Pro and keyboard driver improvements allowing phone to charge directly from keyboard’s battery
    - Libcamera on the PinePhone Pro - a really promising experience & can now be installed on Mobian (and potentially also other OSes)
    - Apache NuttX is being ported to the PinePhone - for now for educational reasons but looks very interesting
    - First glimpse of Ubuntu Touch on the PinePhone Pro - a very smooth and positive experience
    - Many new software releases, including DanctNix Arch, postmarketOS, Mobian and Manjaro bring benefits of Megi’s newest kernel 
    - SailfishOS is really taking off and newest release brings keyboard and camera support 
    - Version 0.7.3 of biktorgj's PinePhone Modem SDK allows modem's userspace to connect to the Internet even when the PinePhone is suspended
- PineTime
    - Many PineTime’s at FOSDEM and interest in the device is not waning 
    - more than 30 pull-requests merged since last release - you can expect better battery level monitoring and UI improvements 
    - A Windows companion app - InfiniWindows
    - A more powerful replacement board compatible with existing firmware has been designed by community

## Housekeeping 

As you surely know we’ve attended FOSDEM in early February and had the opportunity to showcase many of our popular and upcoming devices. To me, however, the highlight was meeting members of the community and developers whom I rarely if ever get to see in person. While this FOSDEM wasn’t exactly smooth-sailing for us (Marek ended up in the hospital on day one and my kid got sick with a stomach bug the day we arrived), it was nonetheless a great experience to have the opportunity to speak with many of you. To this end I’d like to thank everyone who took the time to stop by, hang out and chat at our stall. As always our stall was bustling both days and kept us fully occupied for the duration of the conference. I always promise myself to spend more time walking around and talking to other projects and attend at least one talk - but as always I didn’t manage to find the time for either year around. Perhaps next year.

![](/blog/images/picture-from-FOSDEM-stall-people-1024x768.jpg) ![](/blog/images/Picture-from-FOSDEM-Stall-1024x768.jpg)

**Pictures of the crowd and hardware at our stall :)**

For the past month the Pine Store has been, for the lack of a better word, ‘recovering’ from the Chinese New Year backlog. As is the case every year, support staff have returned to a high volume of unanswered emails and the shipping department had to deal with pending shipments. This resulted in longer-than-usual response times for which I apologies; I am not aware of any delayed shipments, but if there were any then this too I am sorry for. The weeks following CNY are always somewhat chaotic, although my sense is that support and shipping have done a good job getting things back on-track quickly. February has also been a stressful period as production spools back up, factory floor time is being allocated and hardware delivery timelines are being finalized. So, what is the reason for me writing all this? - you’ve likely seen less activity on our end the past month but things should finally be returning back to normal in the coming days. Thank you for your patience.

{{< youtube id="8yzfyjIz5g0" >}}

**In case you missed it, here's the last Q&A from November of last year**

We’ll be hosting the Q&A on March 17 at 20:00 CET. The community Q&A is an opportunity for you to ask us questions and have them answered live. As always we’ll be taking questions from the chat and live-streaming to [Youtube](https://www.youtube.com/@PINE64inc) (as well as PeerTube if we finally can get it to work).  You can join us and ask questions in IRC, Discord, Matrix and Telegram all of which are bridged, so there is no excuse not to participate. We’ll remind you of the Q&A ahead of time and once again on the day but it is probably a good idea to put the date in your diary now. The event lasts an hour following which we usually hang out for another hour in the voice chat, which you’re also more than welcome to join. For those of you who won’t be able to make it, the unedited Q&A session will be available for viewing on Youtube, Peertube and Odyssee. I hope to see many of you there.  

![](/blog/images/restock_Feb_March-1024x576.png)

Lastly, [PINE64 EU store](https://pine64eu.com) has now received a complete hardware restock. As always, you can expect to see the PinePhone, Pinecil V2, PineTime, PinePower and other usual suspects available for purchase. This month the PinePhone (Pro) keyboard case is also making a return alongside the PinePhone + keyboard case bundle. The EU store will also be adding the PineBuds Pro to its assortment - these will be a permanent addition to the store’s repertoire moving forward. If you’re in the EU I encourage you to follow PINE64 EU on [Twitter](https://twitter.com/pine64eu), [Mastodon](https://fosstodon.org/@pine64eu) and [Telegram](https://t.me/pine64eu) for announcements and hardware availability information.

## Newsflash \[by Lukasz, Victor TC, [William Starkey](https://fosstodon.org/@thanosengine), and [MC Server Hosting](https://mcserverhosting.net)\]

We’ve got a new [release of R-Cade](https://github.com/retro-center/rcade_releases) for the Rock64, RockPro64 and Pinebook Pro and the experience is downright amazing. I tested the recent build on the RockPro64 and it must be one of the most well-polished, easy to set up and feature complete retro-game emulation software out there. It also happens to be optimised for the Rock64 and RockPro64, which results in nearly flawless emulation of nearly all included systems. I tested PSP and Dreamcast on the RockPro64 and the vast majority of games ran at full speed. Needless to say, older systems won’t pose any problem on either the Rock64 or RockPro64 (I know from past experience that Nintendo64 emulation on the Rock64 is also great). This is really an incredible job by [mrfixit](https://github.com/mrfixit2001). If you’re into retro-gaming and seek the best possible experience out there then consider R-Cade highly recommended (by me - a person a bit nuts about retro-games). 

https://youtu.be/N4gIxeddzNg

**A (very poor) video showcasing performance of R-Cade on the RockPro64 running Dreamcast and PSP**

PineSAM is a new **P**inecil **S**ettings **A**nd **M**enus BLE app for the V2 from [Builder555](https://github.com/builder555). It works on Linux/Mac/Windows and any browser, and can work from Android, iPhone, iPad. This open source python app runs locally on your pc/laptop, to contribute to the development effort [click here](https://github.com/builder555/PineSAM). It works like this: to quickly get it onto a phone on the same network, open web address _http://<ip-address>:8080/settings.html_ where <_ip-address_\> is the local ip address of the computer running the python app. It is currently actively updated so please check for the newest version. PineSAM allows changing most settings without using the Pinecil screen. A live "Work view" is coming soon which shows active live temperatures, watts, and volts to make it convenient to solder while monitoring & changing temperatures with a larger phone screen. For safety reasons, you have to start heating with the \[+\] button on the Pinecil, but after that you could work in the BLE app on a phone or PC screen. See the Readme if you have any install issues, or open a github issue ticket; Pinecil chat channel may also be able to help. It usually takes just a few minutes to get installed and running.

![PineSAM](/blog/images/PineSAM-q2vqvxijyxgy0hgzear5sj41en75vv9nktgw897ol2.png "PineSAM")

**The PineSAM application looks incredibly cool**

SOQuartz patches for PCIe2, video output, gpu, HDMI sound were merged into mainline kernel 6.2. This is very good news not only for regular end-users but also corporate customers already using a SOQuartz or looking to pick up a SOQuartz for their particular use-case. We’ve seen a major increase in the interest in SOQuartz in recent months so I’m sure this piece of news will be well received. I should also mention that new releases for Quartz64 and SOQuartz are now available from [Manjaro](https://github.com/manjaro-arm/quartz64-a-images/releases) and [DietPi](https://dietpi.com/downloads/images/DietPi_SOQuartz-ARMv8-Bullseye.img.xz). Unfortunately I don’t have any experience with either build, so cannot report on how well the respective OSes perform - if you’ve had experience with either then make sure to share your thoughts in the comments.  

![](/blog/images/quantumworks-cluster-SOQuartzBLADE-1024x768.jpg)

**Quantumworks cluster**

[MC Server Hosting](https://mcserverhosting.net) have been working with Kubernetes and Pine64's Single Board Computers (SBCs) for some time. They have tested various solutions such as sigmaris's pxe ready [uboot builds](https://github.com/sigmaris/u-boot), [jaredmcneill's UEFI](https://github.com/jaredmcneill/quartz64_uefi) for the Quartz & Soquartz, and initramfs hooks + [Empourus](https://github.com/emporous) magic for cluster booting, and are constantly impressed by the power and support of the community.

They write: “_recently, we had the opportunity to try out the SoQuartz Blade. We were delighted to find that it includes PoE and comes with a stable Manjaro image with a kubernetes arm package, ready for testing Rook Ceph network storage. Although these devices are PCIe gen 2x1 with a gigabit port, they are more than sufficient for small home or office setups, and their low power consumption (~10 watts per blade) makes them an economical choice for lab testing. In fact, we believe that a set of these blades and two PoE switches could even handle a large cluster with the proper Crush Map. Our testing showed impressive performance, with Random and Sequential read/write speeds in an optimal range._

_Replicated x2 RBD-NDB w/ osd using all cores_

_Random Read/Write IOPS: 3077/2335. BW: 117MiB/s / 71.2MiB/s_

_Average Latency (usec) Read/Write: 3871.43/1620.43_

_Sequential Read/Write: 115MiB/s / 64.6MiB/s_

_Mixed Random Read/Write IOPS: 3500/1175_

_In addition to mounting etcd for kubeadm and mon/mgr data on the NVMe drives, it is also possible to run the entire runtime of containers on these devices for a significant performance boost. This is particularly useful for applications and libraries that would otherwise be limited by the iops of the emmc/sdcard. Overall, we have found the SoQuartz Blade to be a great choice for setting up a cluster. You can even use etcdadm to run the core of your cluster on three of these blades._”

Browsing the official reddit I came across a pretty awesome looking Pinecil case and I believe that it is an evolution of an already existing case that I featured in a Newsflash section a few months ago. This one, however, from what I can tell is built more rugged and holds more gear: there is space for the USB-C cable, an integrated soldering iron holder which uses a bearing (super cool), space for two additional tips and the thingy to clean the iron. If you happen to have a 3D printer and are looking for a next project this one should be high up on your list. The STL files can be found [here](https://www.printables.com/model/345083-rugged-multipart-pinecilts100ts80-case-v2).  

![abc](/blog/images/Rugged-Case-for-Pinecil-1024x771.webp)

*Rugged Pinecil case by [Piotr Strog](https://www.printables.com/social/48409-pjotrstrog/about)*

For those of you who already own a pair of PineBuds Pro and have experienced issues with ANC in the left earbud - I’ve been told at FOSDEM that reflashing the stock firmware fixes the problem. This has been confirmed independently by a number of people at this point so can be considered an established fix. Instructions concerning flashing the firmware and all other pertinent information can be [found on the Wiki](https://wiki.pine64.org/wiki/PineBuds_Pro#Firmwares). As a side-note, work on the open firmware for the PineBuds Pro is steaming ahead and I’ve been told that it sounds great, so consider giving that a go if you don’t need ANC (which is still WIP on the open firmware)- it can be downloaded from [here](https://github.com/pine64/OpenPineBuds).  

Someone created a USB-C charger for the PineTime. While I can’t necessarily see a reason for substituting the existing cradle for one which accepts USB-C, this is certainly a very cool project from a repairability perspective. That is to say, if your cradle breaks for whatever reason there now is a proof of concept for how one would go about creating a substitute charging solution. Check out the original post and discussion [here](https://www.reddit.com/r/pinetime/comments/yte659/ive_made_a_usbc_charger_for_the_pinetime/). 

![](/blog/images/USB-C-charger-for-PineTime-1024x768.webp)

*Not sure what I make of this one - but it is undeniably cool - image by reddit user [PleasentEnd7990](https://www.reddit.com/user/Pleasant-End7990/)*

The OX64 has now been on the market for two months and it already is one of the best selling PINE64 devices. Who would have believed that an inexpensive Linux-capable RISC-V board would garner so much interest? Some early adopters have however complained that the OS flashing process is unclear and undocumented. One of the early adopters going by the handle [Platima Tinkers](https://www.youtube.com/@PlatimaTinkers) has thankfully put in the effort to document the process in the form of a video. The 15 minute-long video is truly great and gives anyone already owning or interested in getting the Ox64 a crash-course in getting it up-and-running. I am including the video below for your benefit.

{{< youtube id="czRtF-UNiEY" >}}

**Instructions on flashing Linux on Ox64 by [Platima Tinkers](https://www.youtube.com/@PlatimaTinkers)**

On the subject of Ox64, there has been significant progress on porting Linux to the 0x64 since our last update. Several drivers have been added, and we’re getting closer to having the 0x64 as a viable linux device for your projects every day. A buildroot configuration has been made, enabling easy creation of images to flash to the 0x64. Linux drivers have been added for the SD card slot, removing the tight storage space limitations of the spi flash, and we have basic drivers for GPIO and parts of the hardware cryptographic acceleration. Outside of Linux, we have managed to get code running on the LP core for the first time, quite a feat since that core isn’t even properly supported by the official SDK yet. The official SDK has also been updated recently along with new documentation released, making the BL808 an even better MCU platform.

Lastly, since we’ve been asked countless times about when the 65W portable GAN PinePower will be back in stock, I'd like to point out to everyone reading that the redesigned PSU is now available in the Pine Store. It comes with adapters for all regions and fixes a key problem with the original - namely, it no longer falls off from your wall socket, which was an issue for US customers. You can [pick one up here](https://pine64.com/product/pinepower-65w-gan-2c1a-charger-with-international-plugs/) if you’re interested. 

## PineTab2 

Let’s start with the big news which many of you have been waiting for - pricing and expected availability. The PineTab2 will be available in two hardware configurations: with 4GB of LPDDR4 RAM and 64GB eMMC flash and 8GB LPDDR4 RAM and 128GB eMMC flash storage. **The 4GB/64GB version will be priced at USD $159 and the 8GB/128GB version at USD $209**. Aside from the RAM and storage configuration both versions are identical and come with the detachable keyboard by default. The PineTab2 hardware review finished earlier this month and we expect that both hardware versions will be available simultaneously in the Pine Store - likely sometime in April. Obviously there is much that can go wrong during production (as it has with many devices in the past) and delay the delivery date so please consider this availability window tentative at the time being. Marek or I will notify you in the event of any setbacks and obviously also once a precise launch date has been set. 

![](/blog/images/PineTab2-Running-Linux-1024x768.jpg)

**Here's a picture of the PineTab2 FOSDEM demo**

I covered all core hardware specifications of the PineTab2 in the [last community update of last year](https://www.pine64.org/2022/12/15/december-update-merry-christmas-and-happy-new-pinetab/), so this month I’ll instead focus on sharing my impressions of the hardware, now that I’ve had some proper hands-on time with it. If you’ve missed the last community update then I encourage you to read it before continuing with this section. At the start of February I spent the better part of two days with the PineTab2 at FOSDEM demoing it for other people and showcasing its features. You’d be surprised how much you can learn something while being put in a position of showcasing it to others. This is in part because people are interested in different aspects of the device - so my attention was drawn to things I’d otherwise overlook - and partly because explaining things to others forces one to explore a device in-depth in anticipation of inbound questions. I therefore feel I’ve got a more complete picture of the device than I usually do after only having short hands-on time with it.  

Mandatory disclosure first: my experience is based on a pre-production prototype and anything and everything I share in the post below is subject to change. With that out of the way, here is what I can say with the PineTab2: for starters, the hardware’s construction is truly next-level. I don’t want to give you a false impression that the PineTab2 is impeccable or somehow on par with the fruit tablet for this isn’t the case, but it is certainly the most refined PINE64-branded Linux device thus far. The metal construction in conjunction with the fused tempered glass LCD panel results in a very robust and sturdy build that I cannot see anyone complaining about. There’s no creaking, no bending, no rough edges and there’s no doubt in my head that the PineTab2 could easily be passed off as a device twice the price. I should also mention that the finishing on the metal and the assembly fit is downright perfect. 

As for the rest of the construction - the rear camera cut-out is unobtrusive, sits flush with the case and is covered by tempered glass. The power-in USB-C and OTG USB-C ports offer a nice positive fit when a cable is inserted; there is no looseness or cable-wiggle to speak of and the ports are clearly labeled. The power and volume up and volume down buttons don’t have much travel but offer a satisfying actuation feedback when pressed. I honestly haven't noticed the front-facing camera under the bezel so I have nothing to report about it, perhaps aside from the fact that you’re also likely not to notice it either (which is a good thing in my book). The bezels around the LCD aren’t super thin by any stretch of the imagination but they are certainly not thick or obtrusive either. I find them perfectly adequate and obviously a massive improvement over the original PineTab’s design.

![](/blog/images/PineTab2-ports-1024x768.jpg)

**Close up picture of PineTab2 ports - via [Jozef Mlich](https://blog.mlich.cz/author/jmlich/)**

The LCD panel does get both bright at the highest setting and very dim at the lowest setting, although, in the very brightly lit corridor where our stand was located, it was a bit difficult to judge the actual brightness levels. It is less bright than my 2020 Pinebook Pro at max settings (these early Pinebook Pros had very bright screens) but at 75-to-100% brightness I think you’ll get work done in very bright environments without any issue. I can’t speak to the dimmest setting because I only tested the device in very bright conditions; at 10% brightness, in a bright daylit room, the image was very dim. The LCD offers very good viewing angles and natural or perhaps even slightly muted colors. I need to once again underline that I had my hands-on prototype and that the LCD’s cool color reproduction may have been down to this particular unit's calibration, the software settings, my objective perception or something entirely different. What I can say is that the display’s color reproduction did seem cool to my eyes. 

I won’t be able to tell you anything about the PineTab2’s audio because, despite getting it working on the second day of FOSDEM, the venue at the conference was so loud that even a high-end laptop would be barely audible on the premises. But what I can say is that the sound now works - I’ll speak more on software further down in the text. 

The other critical part of the PineTab2 is the keyboard which doubles up as a protective cover. I am happy to report that, similarly to the device itself, it is constructed really well. It is sturdy, the keys have a lot more travel than you’d think, the trackpad works well and attaching / detaching the keyboard from the PineTab2 is a seamless experience (thanks to the USB 2.0 protocol on the pogo pins). The backlight has two brightness settings and works well too - although, admittedly, I haven’t had an opportunity to test it in a dim environment. The backlight is visible in a well lit room so one stands to reason that it will be perfectly legible in the dark too. The keyboard is nearly as heavy as the actual tab, or at least so it feels. The reason for this is the construction of the stand which is a solid piece of metal attached to a solid metal hinge. When open, the PineTab2 isn’t going anywhere - the stand’s construction is rock solid. There is a cutout for the rear camera and all buttons and IO are unobstructed when the device is mounted in its case. The last things I’d like to mention about the keyboard are: it doesn’t feel particularly cramped, the material it is made of has a nice soft-touch feel to it and it holds the PineTab2 securely in place.

![](/blog/images/PineTime-back-1024x505.jpg)

**Being the genius that I am, I completely forgot to take pictures of PineTab2's rear - you can kind-of make out from the picture above  
**

The other important component of the PineTab2 is obviously its software. Here too I have good news to report. At FOSDEM we demoed a custom build of Arch with KDE Plasma Desktop and I’d describe the experience as very positive, especially given that [Danct12](https://twitter.com/RealDanct12) didn’t exactly have much time to generate the demo build. To be precise, there are currently only three ‘significant’ things that do not work: USB3.0 (it is being actively investigated), cameras and Bluetooth. The USB3.0 not working is a bit of a mystery, but it will be worked out in the end, the cameras will take time to implement as they have on the PinePhone and PinePhone Pro, and finally the Bluetooth functionality will require some driver-work. I need to mention that we can thank [Segfault,](https://github.com/TuxThePenguin0) DieselNutJob, [Danct12](https://twitter.com/RealDanct12), [Neggles](https://github.com/neggles/), as well as many other contributors who previously worked on Quartz64 and SOQuartz for the relative maturity of the software even before launch.

I’d describe interacting with the desktop environment as a good experience and on par with the Pinebook Pro or a higher-end Single Board Computers. It is certainly good enough for terminal tasks or running an office suite for work, browsing the web, watching local or online videos, playing FOSS or retro-games and even light photo editing in GIMP. For practical reasons we ran the OS from an SD card at FOSDEM, which resulted in slow(ish) opening of applications and it certainly also had a negative impact on application’s performance, in particular if said application requires frequently loading assets from or caching to storage. From my experience with the PinePhone (Pro) and Pinebook Pro, I expect that the performance will be greatly increased by running the OS from inbuilt flash. 

![](/blog/images/Running-Arch-1024x576.jpg)

**This is the demo build that we were running at the stall**

Despite being in use all the time, for hours on end, and being continually charged and discharged, not to mention having the LCD brightness set to 75-100% for much of the time, at no point did I experience the PineTab2 getting hot or even excessively warm. In all fairness, no one fired up a taxing application or a complicated benchmark on the demo machine but hundreds of people toyed with the PineTab2 at the booth, and a handful of applications ran open at all times. I cannot see thermals being an issue on the PineTab2. 

In summary, the PineTab2 is in all likelihood the most refined PINE64 Linux device yet and one that will offer a moderately mature software experience out of the box for early adopters. I suspect that the PineTab2 will prove a very popular device and I hope that the remaining software quirks will be ironed out and missing features will be added swiftly; perhaps even before it ships. I am personally very much looking forward to the PineTab2 as it is exactly the type of device I am currently in need of. I’ll make sure to keep you updated on any and all PineTab2 news in the coming weeks as we get closer to the launch window.

## Star64

We were thrilled to be able to demo the Star64 running desktop Linux at FOSDEM. [Ayufan](https://twitter.com/ayufanpl), one of our longest-standing contributors whom many of you will recognize from his work on the Pine A64(+), the Rock64, Pinebook Pro and RockPro64 (just to mention a notable few) managed to put together a demo build of Debian with XFCE for our stall. I should also mention that he put the build together in a record time, in about a week, and managed to set it up on-the-spot on the day of the first day of the conference. The demoed build was fairly rudimentary, in terms of both scope and function, but nonetheless it achieved its core goal: it showed off full-blown Linux running on the RISC-V SoC beating at the heart of the Star64. The setup was pretty cool, featuring a 1080p touch panel which worked remarkably well, as well as a more traditional keyboard and mouse input. I’d say that bar the PineTab2 and some of the very popular devices - i.e. the Pinecil V2 and PineTime - the Star64 was one of the most closely scrutinized pieces of hardware at the stall. 

![](/blog/images/Ayufan-setting-up-S64-768x1024.jpg)

**Here's ayufan setting up the demo live :)**

People were able to browse the web in Firefox (WiFi works), edit documents in LibreOffice, poke around in the terminal and do a wide-variety of simple desktop-oriented tasks. Many were impressed by the board despite some of the sluggishness caused by software rendering and running the operating system from a SD card, which resulted in long loading times. To many I spoke with, this was the first time they saw Linux running competently on a sub $100 RISC-V development board. I should also mention that the demo ran remarkably stable throughout the two days, with people opening dozens of Firefox tabs, attempting to find and install applications they use (a bit more on this later) and stressing the system. I think that the hacky and cobbled-together build only crashed twice over the course of the two days. 

As cool as this is, there isn’t a way to sugarcoat it, and it needs to be said the Linux experience on the platform is in its early stages. Indeed, Linux really is in its infancy on the RISC-V. And I’m not even talking about complicated things, such as driver-work or enablement of some particular kind - I am talking about Firefox not being present in the stock Debian repo and having to be installed in a round-about way or compiled from source. Alas, interacting with the Star64, as cool as it is, reminds me of running Linux on Arm in 2013-2016. It is instantly apparent that much work is still needed for parity to be achieved with other Linux-capable platforms. All this may sound like I am being negative about Star64 or RISC-V but nothing could be further from the truth - let me explain. 

For Linux to truly take off and grow on RISC-V there is a need for easily accessible and affordable hardware. Unlike other full-blown SBCs in our stables - most of which can be used by businesses, enthusiasts and regular end-users out-of-the-box - the Star64’s purpose, at least presently, is to lower the entry barrier to obtaining a competent RISC-V development platform. I see it as an important platform for developers already interested in RISC-V wishing to explore the architecture. No matter the product, be it a pie, pencil set or a piece of electronics hardware, there are always three fundamental conditions that need to be satisfied to drive adoption: 1) an existing customer interest or a gap in the market; 2) ability to deliver abundant availability of the product and 3) fair pricing making said product accessible. I think I don’t need to convince you that there is an existing interest in the RISC-V platform already, but what I do want to underline is that we’re committed to Star64 and will strive to make it an amazing value-proposition that anyone can pick up.  

![](/blog/images/Star64-FOSDEM-demo-1024x768.jpg)

**Star64 running Debian with XFCE desktop at FOSDEM**

Finally, I am happy to let you all know that Star64 has finally completed its review and entered production. I do not have a firm availability date to share just yet, but you can expect units from the initial production run to become available at the end of March or beginning of April. I will, of course, make sure that those of you aching to get their hands on our first RISC-V board get notified of availability. 

## PinePhone (Pro) \[by Lukasz & [Biktorgj](https://github.com/Biktorgj)\]

It has now been quite some time since I had a chance to report on the PinePhone and PinePhone Pro, and boy oh boy has there been much work done on both devices in the past two months. I should also mention that I learned of some developments in-person at FOSDEM. As a side-note, it was amazing to see so many people approach our stall, pull out their device and share their (overwhelmingly positive) stories of using the PinePhone or PinePhone Pro. The last time I attended FOSDEM was in 2020, when the volume of PinePhones was still relatively low and I had not been to a conference since, so it was truly a humbling experience to see so many PinePhone and PinePhone Pro owners gathered in one venue.  

Before I get down to reporting about the software developments on the actual PinePhone and PinePhone Pro devices, I first want to cover developments concerning the PinePhone (Pro) keyboard case. Many of you will be thrilled to learn that [Megi](https://xnux.eu/) released version 1.3 of his open firmware. The firmware brings a massive improvement to the phone's battery life when connected to the keyboard - to be precise, the new firmware brings a 30 fold reduction of power consumption, thereby extending the theoretical standby time from 23 days to nearly 1.8 years. Megi explains that previously a bug caused the MCU to _“(...)never \[get\] to that original 9 mW powerdown mode power consumption level \[...\] and it was just constantly consuming 20 mW. This was the cause of unexpectedly fast battery draining.”_ He concludes his post by writing that it is now possible to leave the phone connected to the keyboard without worrying about the phone’s battery draining - at least not in a tangible or meaningful way and under normal use. You can read the detailed post [here](https://xnux.eu/log/#078); the post also details how to upgrade your PinePhone (Pro) keyboard with firmware 1.3. 

Staying with Megi’s development (b)log just for a second longer, I should also mention that Kernel 6.1, which has found its way into some of the more popular PinePhone (Pro) OSes, brought a fix to the PinePhone Pro’s LCD display. The display now runs at the correct 60Hz whilst in the past it was limited to a suboptimal 53Hz refresh-rate. Speaking from experience, the 53Hz refresh-rate caused a variety of problems including but not limited to stuttering, which was evident even in the system UI. Ultimately this made the phone feel more sluggish. Megi’s Kernel 6.1 also brought an integration of the [power manager](https://xff.cz/git/linux/commit/?id=9166a1aa509a8b62e8d72d4b447d511fb91f4002) for the PinePhone (Pro) keyboard. This driver has a handful of improvements in its newest iteration, including better battery power reporting and higher power efficiency. The phone now uses the keyboard’s battery directly without needlessly having to recharge the phone’s internal battery first. Megi’s newest kernel also brings a number of other smaller improvements, which I [invite and encourage you to read](https://xnux.eu/log/#076) about on the author’s blog.    

In other welcome software news, the PinePhone Pro has now received support from [Libcamera](https://libcamera.org/). While the application is certainly at an earlier stage than [Megapixels](https://gitlab.com/postmarketOS/megapixels) on the PinePhone Pro, it does look extremely promising. With the PinePhone Pro’s camera sensor drivers now being upstreamed, and expected in mainstream kernel 6.3, support for the device has been merged in v0.0.4 of Libcamera. The application apparently features colour correction (which, to my eyes, is very evident on the rear camera) and either already has or soon will incorporate auto-focus. For those of you who wish to give it a spin you can now install the application on Mobian - I do not know whether other OSes have it already available in their repos. Ultimately, it is nice to have options, and whilst Megapixels is undeniably a great project I can see some end-users eventually settling for using Libcamera on their PinePhone Pro. In summary, Libcamera looks very promising and I am happy to see so much development happen around the PinePhone Pro’s cameras in such a short period of time. 

{{< youtube id="jnX7awgqPJk" >}}

**Video of Libcamera on the PinePhone Pro via [Libramera's Youtube](https://www.youtube.com/shorts/jnX7awgqPJk)**

Another development worth highlighting concerns [Apache NuttX](https://nuttx.apache.org/) being ported to the PinePhone by [Lup Yuen](https://twitter.com/MisterTechBlog). For those of you who may not be in-the-know, NuttX is a RTOS system - primarily used on microcontrollers - which places an emphasis on standard compliance and a small footprint. The latter of which is highly beneficial to the original PinePhone, which benefits from running light-weight OSes. I haven’t had the opportunity to try out the OS myself but from the few glimpses I caught of it I’ve been impressed by the fact that the screen and touch input seem already to work. Lup has publicly stated that, at present, NuttX isn’t an alternative to Linux on the PinePhone, since many drivers are still missing and hence the functionality of the device is very limited. He does, however, see the value of the port for educational purposes. Regardless of whether NuttX will see further development, growth and eventual adoption, I must say that it is nice to see yet another FOSS operating system on the phone. 

![](/blog/images/Apache-NuttX-Lup2-771x1024.jpg)

**NuttX running on the PinePhone - photo from [Lup Yuen's blog](https://lupyuen.github.io/)**

At FOSDEM I caught the first glimpse of Ubuntu Touch on the PinePhone Pro. Indeed, our friends from [UBports](https://ubports.com/) borrowed a unit for the purpose of demoing the build at their stall. I had the opportunity to toy around with the demo at UBports stall and I was very impressed with what I saw. The performance of the PinePhone Pro running Ubuntu Touch is indistinguishable from other mid-to-high-tier that were on display. To say that it runs Ubuntu Touch well is an understatement: the UI is perfectly responsive, applications launch fast (running from internal flash) and all this atop of mainline with open source GPU drivers. From what I could tell WiFi, Bluetooth and even the modem were all recognized on the current build - although I don’t have a complete overview of how (in)complete the demoed build is. Speaking of the build,I should also note that presently this isn’t an official port nor is it known whether UBports expect to keep on working on the device, although I certainly hope so since what I experienced was very promising to say the least. I captured a quick video, which I am including below.

{{< youtube id="6z7cwPUQybA" >}}

**Ubuntu Touch on the PinePhone Pro - how awesome is that?**

Just in the past 2 days we’ve seen the release of a new [Manjaro beta (version 29)](https://forum.manjaro.org/t/manjaro-arm-beta29-with-phosh-pinephone-pinephonepro/134604) for both the PinePhone and PinePhone Pro. Most notably, the new build brings Megi’s kernel 6.1, some of the benefits of which I described earlier in this text section. I’ve given the Beta a go on my PinePhone Pro and must say I was very impressed with the out-of-the box experience. In particular, for the first time I had no issues with plugging in the device, with the keyboard case connected to a dock and having all peripherals, including an external high-DPI monitor, just work. I feel that the PinePhone Pro has really received a lot of development in the past two months, which consequently has brought it much closer to feature parity with the original PinePhone, and Manjaro’s latest build truly manages to illustrate the scale and breadth of development. You can download the most recent Beta build [here](https://github.com/manjaro-pinephone/phosh/releases/tag/beta29).  

I should also mention that, similarly to Manjaro, a number of other OSes have received updates in the past few weeks, including [DanctNix’s Arch](https://github.com/dreemurrs-embedded/Pine64-Arch/releases), [postmarketOS](https://wiki.postmarketos.org/wiki/PINE64_PinePhone_Pro_(pine64-pinephonepro)) as well as [Mobian](https://mobian-project.org/). I haven’t had the opportunity to test out all these builds, although I did install Mobian to try out Librecamera earlier this month, but I believe that all of them have now moved to Megi’s kernel 6.1.X which I already discussed. That is to say, most if not all the aforementioned OSes should now have a 60Hz refresh on the PinePhone Pro and the keyboard case driver optimizations. It is also worth noting that postmarketOS has received an update to SXMO, which is now on 1.13.0 release and includes a number of [improvements and refinements](https://lists.sr.ht/~mil/sxmo-announce/%3C878rhjwca9.fsf%40momi.ca%3E). 

I would be remiss not to highlight some of the work that [Adam Pigg](https://twitter.com/adampigg) and contributors have done on the PinePhone (Pro) [SailfishOS](https://sailfishos.org/) port. I should also add that this is the nth year in the row that the PinePhone port of SaiflishOS tops the chart of unofficially supported devices - much thanks to the ongoing work which I’m about to highlight. SailfishOS now has support for both the keyboard case and both cameras. Adam demoed the camera and keyboard functionality recently and from the looks of it both are very functional on the operating system. The Pinhole camera application even offers support for different pixel formats and resolutions. Late last month I was also told that telephony on SaifishOS is now in a good state on the PinePhone - which includes receiving inbound calls when the device is suspended. Overall, I think it is fair to say that SailfishOS on the PinePhone is shaping up really well and that it may become a daily-driver candidate sooner rather than later. Wrapping up this section, I should also note that a [new build of Nemo Mobile](https://t.co/liF5kuBsUe),which is based on SailfishOS, has recently become available. I do not know how much of the work on the SailfishOS port carried over to Nemo mobile, but I’d be very glad to hear about your experience with this operating system on the PinePhone. 

{{< youtube id="QXNqZQSkf68" >}}

**SailfishOS now works with the keyboard case and the camera works too! - via [Adam Pigg's Twitter](https://twitter.com/adampigg/status/1619809546364674048)**

Lastly, I need to mention [Biktorgj's](https://github.com/Biktorgj) work on the PinePhone (Pro) modem. The recent testing release in the version 0.7.3 of biktorgj's PinePhone Modem SDK allows the modem's userspace to connect directly to the Internet even when the PinePhone is suspended. It is the [biggest release](https://github.com/the-modem-distro/pinephone_modem_sdk/releases/tag/0.7.3) of the PinePhone Modem SDK yet. I’ll let Biktor explain what this means in practice: _“This week I released a new firmware update for the Pinephone (and Pro) modem. I've had a lot of fun coding this, and while it isn't perfect (and has a small yet annoying bug that will be fixed soon), it gives new options to both users and tinkerers: 1) the ability to keep your network a bit more under control and 2) support for connecting to the internet from the modem's userspace, and then use the modem as a router._

_Tracking your network: the modem can now periodically read the current network data, save all the data provided by the baseband about it to disk (so you can later examine it, put it into a database etc.) and check that data against the OpenCellid database, and even shut itself down if it connects to a cell that it doesn't know about. While it's not foolproof against a modern IMSI Catcher, it can warn you and take action if it finds something out of the ordinary, which is already way more than what any other phone can provide._

_Internet on the modem itself: one of the big problems with notifications in the Pinephone is that when it suspends, the only way to wake it up again is from a call, a message or from a button press. Having the data session running directly from the modem's userspace allows it to stay always on regardless if the Pinephone is awake or sleeping. This first version is basically a PoC to allow us to know what else we need to fix, but the idea is to try to integrate something like UnifiedPush into the firmware... but that will be a story for when it's all done and working”._ These features obviously bring some incredible possibilities down-the line and I cannot wait to see how the community can make them work to the advantage of us all. 

## Pinetime \[by JF\]

This year, I attended both days of [FOSDEM](https://fosdem.org) (4th and 5th of February) and it was a nice opportunity to meet TL, Lukasz and Gamie from PINE64, as well as many PINE64 community members and users. With me I brought a few Pinetimes flashed with [InfiniTime 1.11 FOSDEM Special Edition](https://github.com/InfiniTimeOrg/InfiniTime/releases/tag/1.11.0-fosdem-edition) (this special edition displays the FOSDEM logo as a background for the Digital and Analog watchfaces) to showcase them at the PINE64 stand.

![](/blog/images/InfiniTime-Fosdem-special-edition-802x1024.jpg)

**FOSDEM special edition watchface**

To be honest, I did not expect the PineTime to have so much success on the stand, knowing that it was competing with other PINE64 devices shown (PinePhone, PinePhonePro, many SBCs, Pinecil, SoQuartz Blade,...) and 2 great demos - the PineTab2 and Star64!

I spent most of the time at the PINE64 stand. I had the opportunity to meet many visitors, users, community members and even some developers working on multiple projects around the PineTime and InfiniTime, most of them proudly wearing their own PineTime on their wrist! If someone had told me in 2019, when the project started, that I would see so much PineTimes in one place I wouldn't have believed it.

![](/blog/images/a-lot-of-pinetimes.jpg)

**So many PineTimes at one table!**

The feedback was very interesting - we talked about the history of the project, use-cases I would've never imagined, new features that could be added to the project, how we would like to see the project evolve, and much more. In many cases, feedback was very positive, and I would like to pass all the 'thank you' and 'congratulations' I received those 2 days to everyone involved in working on the PineTime and InfiniTime!

Let's continue this update with some news related to InfiniTime and the PineTime ecosystem!

We haven't released a new version of InfiniTime for some time now. This is mostly due to me having not so much time to dedicate to the project right now. We also want to focus a bit more on the maintenance of the project - to add more automations, refactor some parts of the code, optimize the memory usage and more. But that obviously doesn't mean that nothing happens in InfiniTime. Indeed, more than 30 pull-requests have already been merged in the development branch since last release. Among other things, you can expect better battery level monitoring and a few UI improvements in the next version. We are also reviewing changes that will improve the heart rate measurement, the addition of weather information in PineTimeStyle, and [many other things](https://github.com/InfiniTimeOrg/InfiniTime/pulls) that might be reviewed and merged in the future!

I'm happy to announce that we now have a Windows companion app! [TailyFair](https://github.com/TailyFair) started working on [InfiniWindows](https://github.com/TailyFair/InfiniWindows) since they [couldn't find any solution that would work for them on Windows](https://github.com/InfiniTimeOrg/InfiniTime/issues/1221#issuecomment-1403799414). I really hope this project will grow and become a part of the PineTime ecosystem!

![](/blog/images/watchmate1.png) ![](/blog/images/watchmate2.png) ![](/blog/images/watchmate3.png) ![](/blog/images/watchmate4.png)

**Watchmate allows you to flash firmware onto your PineTime**

The PineTime has always been intended to be a hackable smartwatch, and [Joaquim](https://www.joaquim.org) proved to us that it's true with [this amazing project](https://www.joaquim.org/pinetime-upgrade-board/). Joaquim, who has already contributed to InfiniTime especially with a nice overhaul of the UI, designed a replacement board for the PineTime based around the NRF52840 microcontroller. It provides more performance and memory than the NRF52832 from the original board. He also developed a custom firmware that runs on this board which looks really great. Have a look at the video he published on [his website](https://www.joaquim.org/pinetime-upgrade-board/)!

{{< youtube id="qb5manX6kZs" >}}

**PineTime with nRF52840 board running Joaquim's firmware - pretty awesome!**

That's it for this month, catch you all in March!
