---
title: "March Update: Making waves"
date: "2024-03-17"
categories: 
  - "ironos"
  - "pinecil"
  - "pinetime"
  - "pinevox"
  - "cluster"
tags: 
  - "ironos"
  - "pinecil"
  - "pinevox"
  - "cluster"
  - "pinetime"
cover: 
  image: "march-update-making-waves.png"
images:
  - "/blog/images/march-update-making-waves.png"
summary: "Long awaited community update is here! Introducing PineVox and bone conduction headset (help us find a name!), IronOS progress, PineNote insights, and PineTime news! We also cover cluster failure, state of services, and the future of the community updates. See you in the upcoming Q&A!"
---

![](/blog/images/march-update-making-waves.png)
{{< credits "Banner artwork: Caffeine" >}}

## New products in development

{{< credits "Authors: Ralim, gamiee" >}}

As probably one of the most anticipated sections of the blog, we can confirm that there are more new products in the pipeline.

The first two were shown at the FOSDEM table in Feburary.

### PineVox - Virtual assistant

The PineVox is a BL606P based home assistant smart speaker. Designed to help build a good community option for voice interactions with software such as Home Assistant.

![PineVox photo](/blog/images/2024-march-update/pinevox.jpg)

Currently a small number of developer seed units have been given out. Work is ongoing by Ralim & Gamiee to get a minimal firmware image ready to allow for demonstration and to prove all hardware fully functional etc. 

More information on the unit should be available soon on our new [documentation page](https://pine64.org/documentation). Features of note include the hardware microphone kill switch, and the ability to debug the unit externally. The hardware microphone killswitch allows the software to mute the microphone but unmuting has to be performed using the button on the device. Muting the microphone disables the clock connection to the microphone, giving peace of mind that it really, really isnt listening to you.

Giving users control of the smart devices in their home and allowing for _you_ to control the security is important, and we are working on the PineVox to help enable that future. 

Another notable aspect worth mentioning is the speaker. Designed specifically for voice applications rather than music playback, it ensures clear and high-quality voice audio reception.

### Bone conduction headphones

![Bone conduction headphones](/blog/images/2024-march-update/bone-conduct-headphones.jpg)

These are a set of bone conduction headphones using the same BES2300 chipset as found in the PineBuds Pro. The plan is to expand OpenPineBuds project with support for these before they enter manufacturing. Currently there is amazing work going on to sort out licencing of the BES2300 codebase; so work to support these is being done carefully to minimise impact on the code base.

The enclosure design is not final yet, nor is the software complete. However in the interests of being open, this is the current design.  
I am hoping that we will be able to post another update soon once the hardware in finalized, we're really excited to show off the final project.

#### We need a name!

As you might have noticed, there is no name for this product, so we're reaching out to the community for suggestions! Share your name ideas on [Reddit](https://www.reddit.com/r/PINE64official/comments/1bh6dn2/march_update_making_waves/) and [Mastodon](https://fosstodon.org/deck/@PINE64/112112723757342384). In the next update, we'll select the best one, and the author will receive a free unit!

### It's been a while... Allwinner

It has been a while since we have released a product with an Allwinner SoC, the last one was with the PineCube that released in 2020. But that's going to change soon, as PINE64 is collaborating with [YuzukiHD](https://github.com/YuzukiHD), an organization who have made several SBCs, such as the Yuzuki Chameleon (Allwinner H616) and Yuzuki Lizard (Allwinner V851S).
So in the upcoming months, the Pine Store plans to manufacture and sell new YuzukiHD's SBCs with the Allwinner H618, V851S, and a brand new SoC, the Allwinner A527, which is looking very promising. The A527 is finally using a more modern ARM CPU core Cortex-A55, in cluster 4xA55&#64;1.8GHz + 4xA55&#64;1.4GHz. The GPU is has also been upgraded to an ARM Mali-G57 MC2. A suprising addition is an eDisplayPort, along with a single-lane PCIe 2.1 controller, but sadly, it's shared with the USB 3.0 controller, so we can't have both at same time. The main down-side is that we are still limited to only 4GiB of RAM. Still, this SoC is very promising and it will find it's usage. For more information, take look at [linux-sunxi.org A523 SoC Page](https://linux-sunxi.org/A523).

## IronOS

{{< credits "Authors: Ralim" >}}

Hello,

IronOS released 2.22 as the last majour release since the last blog posts.
Work has of course started on 2.23, though this is still ongoing.

The two large improvements for the Pinecilv2 are improved temperature stability as well was support for boot up logos.

These both have been a bit long time coming but are finally here; boot up logos can now be generated using the tooling in the Meta repository using the instructions on the main docs page.

The `blisp` command line tool for flashing buffalo devices was updated to support `.dfu` files to enable this, as due to the way logos are programmed to the device partial flashes are required.

### A small note about the boot up logos

In order to keep the code base for IronOS easier to maintain, so far I have not implemented USB support on any of the devices. 

This was originally fueled by not having a huge amount of flash space on the first generation devices (Pinecil V2 is the exception here), however it is now largely to reduce complexity.

This is the root cause of the boot up logos requiring a custom conversion tool; the tool is actually converting the image you pass into the flat binary representation the device's OLED screen uses. This means that the device does no image processing, but just pushes this binary buffer directly to the screen.

A later edition was to support animated boot up logos as well; this expanded the logic to allow for multiple frames which are either encoded as entire images or delta encoded (which ever results in smallest code).

The binary blob of data that this process emits is then flashed near the end of the flash on the device. This is why `blisp` had to be updated to allow for partial flash operations. I added `.dfu` files as they are very trivial format, and simple to add handling for them into the code base.

The logo generation has been expanded to support the `Pinecilv2` model, which will cause a `.dfu` file to be generated at the correct offset for the large flash fitted to the Pinecil V2.

Huge apologies for the delay this took getting fully functional, but its here now to stay; and `blisp` is all the better for more support.

The flashing tool Pineflash  by Spagett1 has already been updated to support flashing these files.

### Tuning the tip temperature control

After some earlier fixes to how the temperature regulation code was run on the Pinecil v2; there was the unfortunate outcome that this de-tuned the tip temperature control. After a bunch of testing different tuning profiles and none being consistent across all tips I've gone back to the roots of the code and pulled back in the old PID controller. This has now been tuned to work fairly well on all the tips I have here. 

This means that 2.22 should bring us back to nice; clean temperature control of the tip. Of course if you find any instability I'd love to hear about it as an Issue or discussion on GitHub.

### Desktop & Mobile apps

I take no credit for the awesome BLE enabled apps in our community; but huge shout out to them.

We have new multi-platform app (currently Android & iOS) made in Flutter by amazing [Aguilaair](https://github.com/aguilaair/), and thanks to the Pine Store providing us developer accounts for both platform stores, you can download the apps right now from [App Store](https://apps.apple.com/us/app/ironos-companion/id6469055544) and [Google Play](https://play.google.com/store/apps/details?id=dev.eduardom.ironos_companion).

If you prefer native apps, there is native app for iOS [PineTool](https://apps.apple.com/us/app/pinetool/id6448319330) from Lachlan Bell.

For desktop, you can use [PineSAM](https://github.com/builder555/PineSAM) by Builder555, and [BLE browser API](https://joric.github.io/pinecil/) by Joric.

These are amazing resources to use when tracking down issues, but are really aimed at giving you remote control and a second screen for viewing the status of the device.

For those of us (myself included) that love to integrate everything into Home Assistant, T3chguy has gone the extra step and [made an integration](https://github.com/t3chguy/pinecil_ble) that can be enjoyed as well.


## PineTime

{{< credits "Authors: JF002" >}}

As always, FOSDEM was a nice opportunity to meet with community members, users and contributors of the PineTime project.
And just by looking at the number of people proudly wearing their PineTime on their wrist, I can safely say that the PineTime project is still very popular, more than 3 years after it was created!

![Pine64 stand at FOSDEM24](/blog/images/2024-march-update/fosdem.jpg)

I had a lot of interesting discussions with many many visitors on the stand.
People would explain how they use their PineTime (and the Navigation app) for biking, how they would like to modify InfiniTime to use it for sailing, ask question to use it on a university course and many other things.
All of this is made possible by a nice hackable device and an awesome open source community

Users are mostly happy and thankful regarding InfiniTime : it works, it fits most of their needs, and they enjoy discovering the improvements that are added releases after releases.
Regarding feature requests, I noticed 2 main trends.
On one side, users want more advanced features like health and activity tracking, and on the other side, they would like to see some quality of life improvements integrated in InfiniTime.

InfiniTime also received some fair criticism from contributors : they feel frustrated by their PR that are sitting there with no comment or review for a long time.
The lack of clear roadmap was also mentionned.

One more thing about FOSDEM : this year, two talks about the PineTime were organized : [PineTime: A Programmer's Toy and Beyond](https://fosdem.org/2024/schedule/event/fosdem-2024-3319-pinetime-a-programmer-s-toy-and-beyond/) and [Smartwatch firmware... in Go? On TinyGo, small displays, and building a delightful developer experience](https://fosdem.org/2024/schedule/event/fosdem-2024-2562-smartwatch-firmware-in-go-on-tinygo-small-displays-and-building-a-delightful-developer-experience/).

![Smartwatch firmware... in Go? On TinyGo, small displays, and building a delightful developer experience.](/blog/images/2024-march-update/ayke.jpg)

![PineTime: A Programmer's Toy and Beyond](/blog/images/2024-march-update/jozef.jpg)

At the beginning of the year, the InfiniTime team released [InfiniTime 1.14](https://github.com/InfiniTimeOrg/InfiniTime/releases/tag/1.14.0).
This new version brings among other things new memory optimizations, improvements to the raise-to-wake algorithm and a new lower-to-sleep algorithm.

The team also worked on a new implementation of the weather feature : the Simple Weather Service.

![Simple Weather Service in InfiniTime working with Gadgetbridge](/blog/images/2024-march-update/infinitime-weather.jpeg)

This re-design of the feature was necessary to fix some issues of the original one : it would use too much memory, it would crash under certain conditions and the integration was not easy for companion app.
This new implementation is the result of the collaboration between developers from InfiniTime and from companion apps.
We tried to define a new BLE protocol that would fit our need and then implement it in InfiniTime and companion apps.
To my knowledge, it's currently integrated in Amazfish and Gadgetbridge, and we hope that it'll be integrated in other companion apps soon!

InfiniTime is a monolithic firmware : everything must be built into it at compile-time.
Support for "dynamic applications" that can be installed at run-time is a long term goal, but we're not there yet.
In the meantime, we introduced the compile time configuration of applications and watchfaces.
Developers can now easily specify which apps and watchfaces will be built into the final firmware image.
We might use this in the future to add more appliations and watchfaces to InfiniTime, and maybe provide multiple variants of InfiniTime, each with a different set of applications and watch faces.

On the InfiniSim side, [Victor](https://github.com/vkareh) added support for the weather feature. This feature generates random weather data and forecast in the simulator to help testing the weather integration in InfiniTime. Good job!

![Generate random weather data PR in InfiniSim](/blog/images/2024-march-update/infinisim.png)

InfiniLink, the iOS companion app found a new maintainer : [Liamcharger](https://github.com/liamcharger) took over the project and will continue its development.
This is a very great news for PineTime users using Apple device.
They can expect InfiniLink to receive update and new features in the near future!

Liam has already done some work on the project.
For example, he [re-designed and improved the UI](https://github.com/InfiniTimeOrg/InfiniLink/pull/98), [added support for the weather](https://github.com/InfiniTimeOrg/InfiniLink/pull/108) and for [the external resources](https://github.com/InfiniTimeOrg/InfiniLink/pull/116).

![New UI in InfiniLink](/blog/images/2024-march-update/infinilink.png)

Finally, I would like to mention [GopherWatch, the PineTime firmware written in Go](https://github.com/aykevl/things/tree/master/watch).
I had to chance to talk with [Ayke](https://github.com/aykevl), this author of this project, and to see the firmware running on the PineTime and it's very nice!

![Screenshot of the watch simulator](/blog/images/2024-march-update/gopherwatch.png)

The font rendering on the display is very nice, it features very smooth scrolling animation, supports display rotation, and allow a month long battery life, which is absolutely amazing!

## Pinetab 2

{{< credits "Authors: Caffeine" >}}

For this month’s community update I talked to Danct12 from the Danctnix project concerning the current state of the device.

### Hardware/software status
* At this stage the camera is nonfunctional due to support for Rockchips ISP (Image Signal Processor) not being in mainline yet.
* There is no USB-PD driver yet.
* A new BES Wi-Fi/Bluetooth driver is now included in the kernel.
* H.264 video encoding/decoding driver isn’t in the kernel yet.

Since the last update on the Pinetab 2, Danct has been planning to send a new updated Arch image to the factory along with starting work on a first-time setup screen which will allow users to set a user and password.  

Also, for current users of Danctnix/Arch Arm, an issue has been discovered with the pacman db lock file which has been stopping users from updating their system using Discover. If you are are having trouble with using Discover to update your system, try deleting `/var/lib/PackageKit/alpm/db.lck`. 

### Wifi/Bluetooth driver
BES have been working on an improved driver for Wi-Fi and Bluetooth stability. It is currently in the kernel, but is disabled by default. **PLEASE NOTE**: At this stage the driver is in beta, it cannot handle sleep/suspend modes and will hang if you do not turn Wi-Fi off before shutting down. Proceed with **CAUTION**.

You can enable the beta driver by typing `sudo modprobe bes2600` in your terminal. If you wish to turn off the driver again you can use `sudo modprobe -r bes2600`.

### Conclusion
We are hoping that support for the Rockchip ISP and H.264 driver will land soon and we’re glad to see the situation with the Wi-Fi driver is improving. Overall, the Pinetab 2 is shaping up to be a solid device in the Pine64 hardware lineup.

## PineNote

*Authors: Ralim*

Please note that this section is written by _Ralim_. I am **not** a staff member of Pine64, but I want to represent the state of the Pinenote as best to my knowledge.  
During FOSDEM the current state of the Pinenote was available for people to interact with (and also to show the device does exist).

A huge amount of work has been done by Maximilian to bring up a working Debian/Gnome environment and continued refinement has seen this software maturing significantly. Currently a lot of work is being to track down and resolve artefacting issues that have been cropping up on the open source driver. Recent efforts have reduced these significantly however some work remains.

The OS image has also been updated to build upon Debian Trixie, this has improved the situation with bluetooth along with the update.  
Currently more testing is desired to help find remaining bugs and resolve first-use bugs with the OS. If you have one of the earlier developer batch units, it would be highly appreciated if you could help out Maximilian with testing the images.  

## What exactly happened with the cluster

{{< credits "Authors: gamiee" >}}

On the 20th of January 2024 at 10:30 PM CET, most of the DB based services went down and started throwing errors when attempting to connect to the MySQL databases. 
After some analysis, all of the nodes in the cluster had failed, making the rootfs mount as read-only. In the current cluster setup every node has its rootfs mounted over the network, this leads to one likely culpret, that something had gone wrong with the storage node. 
I wasn't able to connect to the storage node, so I went to the datacentre where the cluster is hosted. Once on site, I found that the storage node's SSD (which hosts all of the data for the other nodes) had switched to read-only mode reporting issues about writing to SSD. 
Thankfully as the [temporary cluster](https://pine64.org/2021/09/01/clusters-build-log-moving-to-temporary-cluster/) is only a small number of nodes, I took it home so I could recover the data.
Before the shutdown of remaining cluster nodes, I took a moment to make a screenshot of the main node's (gateway & firewall) uptime:

![Cluster main node uptime](/blog/images/2024-march-update/cluster-main-node-uptime.jpg)

2 years and 4 months of non-stop service, handling all the traffic of PINE64 community services. One of the reasons behind having a custom cluster was to show-off the stability and reliability of PINE64 SBCs, and I think the cluster fulfilled this perfectly.

The next morning (21st of January 2024), I prepared a new VPS and got Matterbridge running, which is the service that bridges between Telegram, Discord, Matrix and IRC. Afterwards, I wanted to have at least the main website working, and as the new website is based on the Hugo framework, which generates a static website, I deployed it on the new VPS (Thanks to Funeral for all the help). This was significantly faster to get set up for hosting than to bring up the old website. But since we also self-host IRC, the next step was to get IRC back online as soon as possible.

As we are rebuilding the large cluster, we are planning to use Kubernetes to manage scheduling the workload across all of the nodes. To help with the future migration of services to the new cluster, I decided that as I restored all the services, I would set them up to run in Docker containers. So 3 days later, I managed to bring the whole IRC server online with data from the latest backup (which was from December). This took longer than I expected, as I had a lot of work at my daily job. I also needed to create my own Docker image for unrealircd, as there isn't any good one (Thankfully, anope have official Docker container).

The following days were all about analyzing what happened with the SSD and how to recover the data, rather than relying on stuff from backups. But this took longer than I expected, due preparations for FOSDEM and also more work at my daily job. Thankfully, I was able to restore the data from the SSD, the wiki, forums and files were then restored 31st of January 2024.

### Current state of services

- Main community website (www.pine64.org): Since the new Hugo website seems to already be in a good shape, we decided to keep it as our main website. Some things are still missing or unfinished, such as the newsletter, comments, and some pages still need more polishing, but we will work on all of this in the upcoming months.
- Wiki (wiki.pine64.org): After the wiki was recovered on the new machine, it started to misbehave, throwing weird errors on some actions. Because of this, we put the wiki in read only mode. The decision of what will happen to the wiki is still unknown, since we have a replacement (www.pine64.org/documentation) which is part of our statically generated Hugo website.
- Forums (forum.pine64.org): Thankfully, the forums weren't problematic and work very well, although, emails are not working, but we will try to get emails up and running as soon as possible.
- Files: Essential files such as schematics and documents were recovered, although, big files such as images and SDKs, are still not available. We are working with the Pine Store to bring them back in following months.
- Chat Bridge: Bridge (Matterbridge) Works as it did before.
- Pinecil Verify website (pinecil.pine64.org): Works as it did before. 
- IRC Server: With IRC it was complicated, mainly because of the flood of spam messages and Docker network misbehaving between UnrealIRCD and Anope. Anope was configured to save data into flatfile, so the IRC configuration was lost multiple times. We migrated to db_sql_live together with MySQL DB Backend, and applied a rate-limit to fight with spams (thank you Danct12!). Although, since the spammer always finds a way to bypass our limits, in every channel except main one (#pine64) you need to be registered to send messages, and registrations are manually reviewed. If your account is not confirmed within few days, please ping me (@gamiee) on any platform.
- CedarSentinel (Anti-Spam system): CedarSentinel is a service, which was created by (currently retired) PINE64 Sysadmin **fire219** to detect and remove "casual" spam, such as crypto offers from Telegram, with the help of Machine Learning. Thanks to the community member **kj7rrv**, CedarSentinel is being re-trained and it's already deployed on new VPS. By the way, CedarSentinel is open-source, and you can check it out on [Github](https://github.com/kj7rrv/CedarSentinel)!

### Moment for appreciation

As it was mentioned earlier, community services are now up and running on a VPS to keep everything stable until I have some time to finish getting the main cluster working again.
While choosing where to purchase the new VPS from, I recalled a host that is very similar to our community, they are community driven by Linux enthusiats. 

I looked into [VPSfree.org](https://vpsfree.org), a non-profit association located in Czechia, which provides their members virtual servers for a great price. They are using their own operating system for virtualization [vpsAdminOS](https://kb.vpsfree.org/information/vpsadminos), together with many other tools, which are all open-source. 
I have been a very big fan of them for several years, and I am very thankful for the help and support that they have provided us. So, if you are looking for a cheap and good VPS, consider taking a look at their offerings.

I want to say a huge thanks to **fire219** for all the hard work he's put into PINE64 Community Services, as he stepped down as sysadmin in August 2023. fire219 has been part of our community for many years – even before I joined in 2018! He's been taking care of things like the Forums, Wiki, IRC, CedarSentinel, and a bunch of other stuff. Thanks you for everything, and best of luck with whatever comes next!

Also, I want to give a big thank you to all who have helped with our community services in the past. Special thanks to Danct12, dsimic, Funeral, kj7rrv, PaulFertser, Phiten, and Ralim for all their contributions.

### What's next

We still plan to host our services on the cluster, but before that, we need to fix some issues, which the previous cluster had. But for those who are only just learning about the cluster for the first time, let me start from the beginning.

[In 2019](https://twitter.com/gamelaster/status/1192551455334576128), we received from the Pine Store a custom-built cluster, which consits of a server case, TP-Link switch, server power supply, 24x RockPro64s and 3x special PCB for node power control.

![Cluster photo](/blog/images/2024-march-update/cluster-photo.jpg)

In September 2021, I wrote the [blog post](https://pine64.org/2021/09/01/clusters-build-log-moving-to-temporary-cluster/), about building the new "temporary cluster", and exchanging it with the "final one". I recommend reading the blog post, it explains a lot about the cluster and the reason we moved to the temporary cluster. In short, unfortunately, the cluster was deployed in a hurry, and things like power management for the nodes were not finished. For proper implementation, it would have been best to have had the cluster at my place, so a temporary cluster was built. (The temporary cluster was in the server housing until the failure)

Sadly, life got busy, and there was not a lot of progress on the cluster until 2023. Me and Ralimtek started working on a new PCB, which will serve as the "motherboard" of the cluster. This is for managing the power supply, communication with power management boards and a UART output logger for all nodes. For the first revision, this board was designed as a daughterboard for SOPine A64 Baseboard, the final version will be a PCB that will house a SOPine A64 module. A few weeks ago, I managed to assemble the daughterboard and perform some tests. Aside from some very minor issues, the board works pretty well!

![Assembled daughterboard](/blog/images/2024-march-update/assembled-daughterboard.jpg)
![Daughterboard on SOPine A64 Baseboard](/blog/images/2024-march-update/daughterboard-mounted1.jpg)
![Daughterboard on SOPine A64 Baseboard](/blog/images/2024-march-update/daughterboard-mounted2.jpg)

In the following months, we will start work on the software side, which will be a buildroot filesystem with software for remote access of the cluster. We will provide more information about this effort, most likely in a separate blog post.

## Future of community updates

{{< credits "Authors: gamiee" >}}

Monthly updates were an essential part of the community for a very long time, so not having them was indeed very damaging. That's why it was priority #1 on our topics to discuss at FOSDEM 2024. Thankfully, we have a new plan with getting updates released again. We still aren't sure if it will still be on a monthly basis like it used to be, but it will be periodically released. Not only that, we are planning on improving community engagement and moderation. We will explain our plan further in following updates.

### Let's do an Q&A

As it has been a very long period without any updates, along with proper community engagement, we have decided to organize a Q&A! The community is free to ask any question that they may have! As in previous times, we will be using Discord Stage to host the Q&A, which will be streamed to YouTube and (hopefully) PeerTube. But this time, the place for asking the questions will be on Reddit and Mastodon. When we used Discord, Telegram and IRC for questions, there were many duplicates, it was hard add reply to the questions (like a link to stream with timestamp) and it was impossible to sort through. So before asking any questions, please take look if your question has been asked already, and up-vote questions you would like to be answered! So see you there at 22th March 2024 at 7:00 PM CET (10:00 AM PST, 1:00 PM EST). You can ask questions here on [Reddit](https://www.reddit.com/r/PINE64official/comments/1bh6dtq/pine64_quarterly_community_qa_2024_q1_ask_your/) and [Mastodon](https://fosstodon.org/deck/@PINE64/112112732034587306).



