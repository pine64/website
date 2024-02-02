---
title: "August update: RISC and reward"
date: "2022-08-28"
categories: 
  - "community"
  - "news"
  - "pinebuds"
  - "pinecil"
  - "pinephone"
  - "pinephone-pro"
  - "pinepower"
  - "pinesound"
  - "pinetime"
  - "quartz64"
  - "risc-v"
tags: 
  - "pinebuds"
  - "pinephone"
  - "pinepower"
  - "pinetime"
  - "risc-v"
  - "soquartz"
  - "star64"
cover: 
  image: "August-update.jpg"
images:
  - "/blog/images/August-update.jpg"
---

![](/blog/images/August-update.jpg)

This month we take a close look at the Star64, check out PineBuds (Pro) progress and discuss the Pinecil V2. I also come bearing good news concerning the PinePhone Pro, which has seen a small but significant hardware redesign and some important software updates.    

Let’s get into it.

You can watch the synopsis of this month’s community update on YouTube (embedded below) as well as on [Odysee](https://odysee.com/@PINE64:a) and [PeerTube](https://tilvids.com/accounts/pine64tilvids/video-channels). To stay up-to-date with PINE64 news make sure to subscribe to this blog (subscription widget at the bottom of the webpage), follow the [PINE64 Telegram News channel](https://t.me/PINE64_News), the [announcements channel in Discord](https://discord.gg/pine64) as well as our [Twitter](https://twitter.com/thepine64) and [Mastodon](https://fosstodon.org/@PINE64).

I’d like to thank [Alex](https://twitter.com/AlexRob12252696) (clover), [Gamiee](https://twitter.com/gamelaster), [JF](https://twitter.com/codingfield) and [PizzaLovingNerd](https://www.youtube.com/channel/UCmGcm7dhEjS9CIOsOOv8y6w) for their contributions to this community update.

N.B. Comments on the blog post need to be in English and follow our [Community Rules and Code of Conduct](https://forum.pine64.org/showthread.php?tid=13209).

{{< youtube id="jZLvyBNwHII" >}}

**Video synopsis of the August community update**

**TL;DR**

-  Housekeeping
    - We’re sponsoring Akadamy; meet us there!
    - Community Q&A was held August 13, you can now watch it on YouTube
    - A call for sticker design - looking forward to seeing what you come up with
    - Blade hostboard for the SOQuartz is now in the PineStore
    - The PinePower in the Pine Store and EU store is grounded - cause for confusion outdated photographs 
- PinePhone (Pro)
    - Spare parts for the PinePhone Pro are now in stock
    - Small hardware redesign - the PinePhone Pro now takes nano SIM
    - Megi’s patches bring improvements to sound on the PinePhone Pro
    - New releases from postmarketOS, DanctNIX, OpenSUSE and Manjaro; OpenSUSE shows off Qi Wireless charging
    - Work-around instructions for Mobian installer issues
- Star64
    - Pictures of the first Star64 prototype 
    - Overview of the final Star64 IO layout, components (WiFi 6 & BT 5.2among them) and features
    - Debian and Fedora already being ported to the SoC; we trust many other OSes will follow
- Pinecil
    - First batch of Pinecil V2 sold out in record time; next batch in EU store early September and Pine Store mid-September
    - Pinecil V1 vs V2 and tip comparison by end-user - very cool video
    - Pinecil V2 online authenticator; a walk-through of how to check whether if your unit is legit
    - Ships with newest IronOS firmware
- PineTime
    - Watchmate: new companion app for desktop and Linux phones
    - Watchmate works with InfiniTime and incorporates key functionality
    - InfiniLink iOS companion app transferred to PINE64 community

## Housekeeping

  
We’re once again one of the sponsors of this year’s [Akademy](https://akademy.kde.org/2022), which is taking place in Barcelona 1-7 October. For those of you who don’t know about Akademy - it is an annual non-commercial meetup organized by the KDE Community. From memory, this is the 5th time that we’re a part of and sponsoring the event. Since this year’s meetup is an in-person event we’ll be flying into Barcelona to attend. Keep an eye out for Marek, TL and myself during the weekend of 30 September and October 3rd. We’re taking this as an opportunity to meet and mingle with people, so it is unlikely that we’ll be holding any talks or the like.

![](/blog/images/Akademy-22.png)

**If you live in Europe, are a fan of KDE and happen to like our products then drop-by Akademy in Barcelona this year**

We held the quarterly Q&A on August 13. As usual, Marek and I answered questions from the chats and for the first time managed to answer nearly all the questions posed. This time around we also managed to stream the Q&A to both Youtube and Peertube, while simultaneously having people in the Discord stage. Kudos to Marek for getting it all working this time around. The recording of the full and uncut Q&A session is available on Youtube, and thanks to [Pak0St](https://twitter.com/PakoSStoyanov) there are chapters available so you can easily find the bits and pieces you’re particularly interested in. The next Q&A will be held sometime in November. 

{{< youtube id="YAviFY3-IIA" >}}

**Live recording of the third community Q&A held on August 15, 2022**

In other community news - we’ll be printing PINE64 stickers for upcoming community events (I am keeping my fingers crossed FOSDEM 2023 is an in-person event). While we’ll surely be printing some fairly generic PINE64 branded stickers, we also want to reach out to you for submissions. So if you’re artistic and would like to submit a PINE64-centered sticker design, then we’re more than happy to receive it. Make sure to have the sticker design include your name or handle. As for design requirements, it needs to be a grayscale and read well in a small size. If we receive multiple submissions, then we’ll run some sort of community poll and have you select the ones you feel represent the project best. Please post your submissions on the forum or, if you prefer, in the #offtopic community chat; make sure to ping the mods to make them aware of the submission.   

  
The Blade hostboard for the SOQuartz is now available in the [Pine Store](https://pine64.com/product-category/cluster-accessories/). In case you missed it, I wrote about the Blade and other SOQuartz hostboards [back in May](https://www.pine64.org/2022/05/31/may-update-worth-the-wait/). This hostboard has been designed for clustering and fits inside a standard 1U server rack. You can fit 12 or more Blade hostboards into a single rack. I had the opportunity to check out a Blade prototype in May and was really quite surprised by how slim it was and how much I/O was present in the tiny space that the PCB provides. If you’ve been interested in clusters and were waiting for a spiritual successor to the Clusterboard then here it is.

![](/blog/images/WeChat-Image_20220823113629-768x768.jpg)

**BLADE hostboard with 8GB SOQuartz installed**

Lastly, I want to make it clear that the PinePower desktop currently sold in the [Pine Store](https://pine64.com/product-category/pinepower/) and [EU store](https://pine64eu.com/product/pinepower-destkop/) is grounded (and has 3 prong plug) as requested by the community. I wrote about this new hardware revision already in the [April community update](https://www.pine64.org/2022/04/15/april-update-no-more-unicorns/) -I encourage you to read the blog entry in case you missed it. I am aware that the pictures in both stores were outdated for a couple of days when the new batch arrived, which led to some confusion as to whether the hardware is from the new revision. All PinePower desktop units currently on sale and produced in the future will be grounded. Apologies for the confusion caused by outdated pictures.

## PinePhone (Pro)

Let’s start with some hardware news. Spare parts for the [PinePhone](https://pine64.com/product-category/pinephone-spare-parts/) and [PinePhone Pro](https://pine64.com/product-category/pinephonepro-spare-parts/) are now in stock. I know that many users with cracked screens or damaged back-cases have been waiting for these parts to return to the store. I am happy to let you know that spare PinePhone (Pro) keyboard PCBs are now also available for purchase. I am mentioning the availability of these parts explicitly at the start of this section because I’ve recently seen people question our commitment to creating repairable hardware. So, let me assure you that we’re as committed to making repairable hardware as we always have been. The reason why spare parts were out of stock for a period of time is simply due to them selling out from the last PinePhone (Pro) production batches - spare parts are usually only delivered with a new production run. The spare parts are basically unassembled PinePhone (Pro) units. Same goes for keyboards and other equipment. If there is a break in hardware deliveries then it is likely that spare parts will temporarily sell out too. However moving forward we’ll hold a larger stock of spare parts. 

In other hardware news, the most recent production run of the PinePhone Pro has seen a small but important redesign, at least for newcomers. One of the most common failure points on the PinePhone and PinePhone pro is the SIM slot. Users were required to use an adapter for their nano SIMs to fit into the micro SIM slot - some would insert the adapter without a SIM, pull it out, and damage the pins in the process. Others would insert a micro SD card into the SIM slot thereby damaging it. For this reason, the new production run of the PinePhone Pro incorporates a nano SIM slot instead. The slot has a clever design which prevents new users from accidentally inserting a micro SD inside too; to insert the SIM card you need to pull out a little tray (which doesn’t come all the way out), into which the SIM is inserted. We hope that this small improvement will result in fewer broken SIM and SD slots moving forward.

![](/blog/images/photo_2022-08-27_13-02-34-1024x576.jpg)

**Nano SIM slot on the PinePhone Pro**

There are a few software news I’d also like to cover this month. The most notable of which, and one which will eventually surely find its way into all OSes, concerns sound on the PinePhone Pro. [Megi](http://xnux.eu/) has recently released a set of patches that address some of the issues people have been experiencing: sound codec not working after boot (prior to an app playing audio), changing controls while headphone or speaker output is active breaks audio, sound stutter when serial console is enabled in CLI, OUTMIX and RECMIX drivers not matching the schematic and microphone quality. I invite you to read and follow [megi’s development (b)log](https://xnux.eu/log/#074) to learn of the details but, in short, the patches ought to improve the sound situation on the PinePhone Pro. I hope to see them make their way into individual OSes soon. 

As for the OSes, we’ve seen a few releases for the PinePhone and PinePhone Pro this past month. This includes (at least to my knowledge - there may be others) postmarketOS, Manjaro, OpenSUSE and DanctNIX (Arch). Most of the distributions shipping the Phosh mobile environment have now updated to the newest version which adds swiping motions; I haven’t had the opportunity to try the newest version of Phosh myself, but I hear very good things about it. I would also like to note that OpenSUSE shared an image of the PinePhone charging wirelessly using the Qi wireless charging case (currently out of stock), which is super cool to see. I am including a picture from the tweet below.

![](/blog/images/wireless-charging-1024x768.jpg)

**Wireless charging on the PinePhone running OpenSUSE - via [Adrian Campos Garrido](https://twitter.com/hadrianweb)**

There is one more thing I’d like to mention in this blog post that is distro-specific: I’ve seen reports that Mobian users have issues with the installer image. The problem it seems concerns the [root partition not expand](https://gitlab.com/mobian1/issues/-/issues/440#note_1018769896)ing properly during the installation process. I reached out to Mobian developers about a potential work-around and [Undef](https://gitlab.com/undef1) was really helpful in emailing me comprehensive instructions. I should also note that Mobian’s dev team is aware of the problem and actively working to resolve it. 

Here's the work-around:

Resize the primary partition using parted.

- _$ sudo apt install parted_

Make sure to select the right storage device (exchange for x below); 2 will usually be eMMC while 0 is likely to be SD.   

- _$ sudo parted /dev/mmcblkX_

Inside parted run print just to make sure you are using the proper 

device. You should see two primary partitions:

- _(parted) print_

Enlarge the 2nd to 100% capacity:

- _(parted) resizepart 2 100%_

Print to see if the partition expanded correctly and then quit the program:

- _(parted) print_
- _(parted) quit_

If you’re using an encrypted device run the following command - you will be asked for your encryption password: 

- _$ sudo cryptsetup resize calamares\_crypt_

Then proceed to resize the ext4 filesystem:

-  _$ sudo resize2fs /dev/mapper/calamares\_crypt_

Finally resize the btrfs filesystem and check results:

- _$ sudo btrfs filesystem resize max /_
- _$ df -h_

  Once again, many thanks to Undef for the detailed instructions. 

## Star64

This month I come bearing good news about the Star64 RISC-V single board computer. Just three months after the board's initial announcement today I get the privilege of unveiling the prototype - and I hope you’ll admit that it looks mighty cool. Star64 is the first true RISC-V SBC from us (I mean, unless you really consider the Pinecil a SBC), but as I wrote [last month](https://www.pine64.org/2022/07/28/july-update-a-pinecil-evolved/) it certainly isn’t the last RISC-V piece of hardware you’ll be seeing from us. Just as a short recap: Star64 comes with a StarFive JH7110 64bit CPU sporting quad SiFive FU740 cores clocked at 1.5GHz. The SOC is equipped with BXE-4-32 from Imagination Technologies, which is said to be a solid mid-range GPU. Star64 will be available in two configurations - with 4Gb and 8GB of RAM, similarly to the Quartz64. Both hardware versions include USB 3.0 and a PCIe slot as well as two native Gigabit Ethernet NICs.

![](/blog/images/WeChat-Image_20220823213606-1-1024x1024.jpg) ![](/blog/images/WeChat-Image_20220823213629-1024x1024.jpg)

**Star64 IO -- left: dual Gigabit Ethernet, HDMI & power-in // right: 3X USB 2.0 & USB 3.0**

The IO arrangement is very similar to what you’ve come to expect from one of our model-A type boards. Along the long leading edges you’ll find PCIe on one end and GPIO on the other. At one end of the board you’ll find a digital video output, a double-stacked Gigabit Ethernet port and a 12V barrel plug for power. On the opposite side, you’ll find 3x USB 2.0, 1x USB 3.0, an audio jack as well as a power button. There are also two U.FL ports for antennas - one for bluetooth and the other for WiFi.

![](/blog/images/WeChat-Image_20220823213717-1024x1024.jpg) ![](/blog/images/WeChat-Image_20220823213742-1024x1024.jpg)

**Star64 -- left: top view // right: bottom view**

The onboard WiFi/BT module is RTL8852BU MIMO WiFi 6 with BT 5.2; it may already be supported in mainline Linux. The Star64 also has an MiPi display output complete with a touch panel (TP) input, a 12V power port, a CSI camera port and an eMMC slot. A micro SD card slot can be found at the bottom of the PCB. Similarly to the RockPro64 and Quartz64,  the 12V port on the Star64 can be used for powering other hardware directly from the board - a popular example is powering one or multiple SSDs connected to a PCIe SATA adapter. I’ll add that, at least in theory, the Star64 would make a great NAS because of its SoCs low thermals and idle power. I am looking forward to seeing NAS-focused Linux or BSD\* OSes available for the board.

Speaking of software, efforts to support the SoC in Linux have already begun. I’ve been told that both Debian and Fedora are already being ported to the StarFive JH7110, which is great news. We are certain that many other OSes will follow swiftly - especially once we start delivering the Star64 to interested developers. On the subject of availability: the Star64 will be available in a few weeks time, and will initially be available to developers. Given the interest in the Star64’s and the SoC powering I hope to see functional distributions available for the board soon after launch. We will obviously be monitoring the Star64’s software progress in the months to come and keep you posted on how development proceeds.

## PineBuds Pro

A quick foreword about PineBuds changing name to PineBuds Pro prior to release: the hardware stays the same, it's just naming convention - or branding if you will - changes to include the ‘Pro’ suffix. We’re doing this to indicate the additional functionality that the earbuds are capable of - ANC in particular. That’s all.  

I am glad to report that development of the PineBuds Pro is proceeding well. In fact, CE/FCC testing is scheduled to start early September, so a mid-Q4 release is highly likely.  In July I shared pictures of the first moulded PineBuds carry case without the electronic guts - today I get to show pictures of the first moulded and working prototypes. This time around this includes the pods and the case, both of which arrived from the factory just the other day. As you can probably tell from the picture, the final mould of the carry case looks much more refined than the CNCd version shown in April. It is hard to make it out from the photos, but the case features a textured finish on the outside and a smooth finish on the inside. The buds themselves have a two-texture finish too, with the stems made out of shiny plastic and the body of the buds being matte. While none of the pictures below depict this, the case now also features a small row of LEDs on the front, used to indicate charging status and remaining battery. But let me stress this again - these are pictures of prototypes, and thus everything you see is subject to change.

![](/blog/images/WeChat-Image_20220824065348-1024x1024.jpg) ![](/blog/images/WeChat-Image_20220824065414-1024x1024.jpg)

**PineBuds -- left: buds in carry case // right: buds seen next to the casa**

Since the last post discussing the PineBuds we received much feedback regarding our initial decision not to brand the buds. This is not the first time we receive feedback concerning branding from the community; as a rule of thumb, we usually try to keep branding to a minimum on our hardware. As was the case with the Pinebook Pro, PinePhone and PineTab - we always try to incorporate the PINE64 logo in some tasteful and non-intrusive way. But this is a bit hard to achieve on something as small as a pair of wireless earphones. However, it does seem people are keen on rocking buds with a PINE64 pine cone, so we’ll run some test prints in the next few weeks and see how they turn out. I am attaching some impressions for you to take a look at below. 

Lastly, the Pine Store commissioned development of an alternative SDK and firmware for the PineBuds. The hope is that the new SDK will make development of community customised and user-tailored firmware easier to achieve. The custom firmware and SDK builds are about 2 weeks away I am told - once delivered we’ll have developers evaluate the efforts. If this is the first time you’re hearing about the PineBuds I invite you to read the [April](https://www.pine64.org/2022/04/15/april-update-no-more-unicorns/) and [May](https://www.pine64.org/2022/05/31/may-update-worth-the-wait/) community updates in which the hardware was introduced and discussed at some length. I am sure I’ll have more information about the PineBuds to report next month, so stay tuned. 

![](/blog/images/photo_2022-08-26_08-06-52.jpg)

**Proposed PineBuds branding - let us know what you think**

## Pinecil \[by Gamiee\]

The Pinecil V2 landed earlier this month and sold out almost instantly. The next production run of the ought to be available soon however - you can expect the next batch to land in PINE64 EU at the beginning of September and in the Pine Store a few weeks later. There will likely be a limit on how many units can be ordered by one person to make sure that everyone who wants one can get one (if they order within the first 72 hours or so). To be notified of availability, please follow [PINE64](https://twitter.com/thepine64) and [PINE64 EU](https://twitter.com/pine64eu) on Telegram, Mastodon and Twitter. We’ll make sure to give everyone a solid 24hrs heads-up before the next Pinecil batch becomes available again. 

Earlier this month I came across a very interesting comparison between Pinecil V1 and V2, which also includes a performance overview of the new tips. Spoiler alert, the V2 performs better when supplied enough power, but the new tips heat up much faster on both the V1 and V2. When combined with the right power source and fitted with the short 6.2 ohm tip the V2 heats up to a temperature of 300\*C in under 3 seconds. It is a really interesting video by one of our community members, and I advise anyone interested in the Pinecil V2 to watch it. 

{{< youtube id="nTC-ah4f0hg" >}}

**A comparison between Pinecil V1 and V2 as well as the new 6.2ohm tips - by River B.**

As we mentioned in the previous community update, we have implemented a few anti-counterfeit measures into Pinecil V2. One of them is the possibility to verify that your Pinecil V2 is original. And you can do this on our authenticity verification page, which you can find on [https://pinecil.pine64.org/](https://pinecil.pine64.org/). The process is quite simple: on your Pinecil enter the debug menu by holding down the minus (-) button, scroll down to the ID tab using plus (+) and enter the serial number (first row) into the online authenticator. You’ll be immediately informed whether your V2 is an authentic PINE64 product or a knock-off. 

![](/blog/images/PinecilV2-authenticity-check.png)

**Authenticity checked page**

The Pinecil V2 is being shipped with IronOS v2.18, which is still up-to-date at the time of writing. There are no requirements to update the firmware, but if anyone wants to update their V2 then it is not currently possible. This is due to the new Bouffalo chip not using the DFU protocol for flashing and the flash tool, which supports the Bouffalo’s flashing protocol, is still a work in progress. It should, however, be available soon; stay tuned for more information in the coming weeks and months.

## PineTime \[by JF\]

This month, we welcome a new companion app in the PineTime ecosystem: [watchmate](https://gitlab.com/azymohliad/watchmate). The author announced it on [Twitter](https://twitter.com/azymohliad/status/1560523188290846722?s=20&t=9U2IQkn6Qwe81TuMDPi3rw) and [Mastodon](https://fosstodon.org/@azymohliad/108848280780940837) a few days ago. Watchmate is a companion app which runs on desktop and mobile Linux and is compatible with PineTime running InfiniTime. Written in Rust and based on libadwaita and BlueR it already supports many features from InfiniTime, such as setting the time, reading battery level, recording the heart rate value, controlling media player and OTA firmware updates.

The UI is really nice and easy to use and a bit similar to [Siglo](https://github.com/theironrobin/siglo): once connected, it displays various info, allows you to select the media player that will send info to the Music app and upgrade the firmware over the air (OTA). Watchmate will display a notification when it detects that a newer version of InfiniTime is available i[n the project’s repository](https://github.com/InfiniTimeOrg/InfiniTime), which is a very convenient feature!

![](/blog/images/collage-1024x388.png)

**Watchmate functionality**

A few features like secure pairing and notifications are not implemented yet but they are already listed in the [project roadmap](https://gitlab.com/azymohliad/watchmate#roadmap). They waited to test watchmate and have enough time to maintain the project, and that they would transfer the project to anyone who would like to take over it. Since then the Github project has already been transferred to the [InfiniTime organization](https://github.com/InfiniTimeOrg/InfiniLink) and the application on the app store has been transferred to an account managed by Pine64 to ensure that it remains available on the Apple Store until it finds a new maintainer! Thanks again to xan-m for their work on InfiniLink!

![](/blog/images/watchmate.png)

**Watchmate running on the PinePhone Pro and Pinebook Pro**

Thats all for this month, I'll catch you all in September.
