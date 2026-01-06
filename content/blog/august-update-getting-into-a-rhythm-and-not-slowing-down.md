---
title: "August update: getting into a rhythm and not slowing down"
date: "2020-08-15"
authors: ["Lukasz Erecinski"]
categories:
  - "news"
  - "pinebook-pro"
  - "pinecil"
  - "pinephone"
  - "pinetab"
  - "pinetime"
tags: 
  - "pinebook-pro"
  - "pinecil"
  - "pinecube"
  - "pinephone"
  - "pinetab"
  - "pinetime"
cover:
  image: "/blog/images/AugustHeader-elementary.jpg"
images:
  - "/blog/images/AugustHeader-elementary.jpg"
---

![](/blog/images/AugustHeader-elementary.jpg)

**elementary OS 6 _Odin_ on Pinebook Pro - image via [Alan Pope](https://twitter.com/popey/status/1293862021495169024)**

I am currently traveling and have a limited amount of time to write, so I’d like to apologize in advance for not covering all topics and not answering outstanding answering questions that some of you are waiting to hear about. I also had less time to review chat backlogs, tweets, the forum and other information sources, and in result it is possible that I missed some information which ought to be covered.

I’d also like to thank [JF](https://twitter.com/codingfield) for covering the PineTime progress leading up to the early adopters edition of the PineTime, which will be available for purchase in the coming weeks.  

**TL;DR for this month**

- New and clear rules of community engagement are coming
- PINE64 logo and brand-name infringements
- Pinebook Pro production is on schedule; factory will deliver PBPs to us on 24 August
- Pinebook Pro is getting elementary OS 6 _Odin_ support!
- A look at the Pinebook Pro USB-C docking station; waiting for software support
- PineTab delayed one week; volume button flex cable mistake
- A look at RTL-SDR and LoRa expansion expansion boards for the PineTab
- PineTab pre-orders reopen late this month
- Last chance to get the postmarketOS CE - sold out any day now.
- PinePhone: we’re on a roll and we’re not slowing down (until CNY)
- PinePhone community hardware mods and awesome projects
- We’re exploring keyboard options for the PinePhone
- Notable PinePhone software developments
- Pinecil coming in September; a tipset will be available at launch
- PineCube positive response; available in September/ early October
- PineCube accessories - LCD panel and battery

##### Housekeeping

A recent series of events led me to rethink our formal rules of community engagement. As the community grows - and at a rapid pace at that - moderators and community members need to have clear guidelines to reference concerning the type of engagements we, as a community, are willing to accept. Before I write anything else, let me start by saying I am not a fan of heavy-handed moderation; I believe that just as in everyday life you’ll eventually run into a jerk in any community. This is just how life is, and I don’t believe that it's the role of moderators to educate people about civil conduct. But there are certainly some new and worrying trends that need to be addressed, so I’ll be writing up a new code of conduct / community rules in the coming weeks. The reason why I am mentioning it in this section, is because I’ll be [posting the draft](https://forum.pine64.org/showthread.php?tid=11034) of the new rules on the forum so that we can debate various aspects of the rules and (hopefully) agree on some of the more nuanced points I intend to make. 

The second topic I wanted to touch upon in this section concerns the use of the PINE64 logo and brand-name. We have recently experienced three types of infringements: 1) online resellers selling PINE64 hardware pretending to be Pine Store Ltd.; 2) merchandise sellers using our logo on swag without consent and; 2) our logo being used and misused without our consent in undesired contexts. In result, we are currently working on precise guidelines pertaining to the use of our logo and brand-name. This will arm PINE64 community and Pine Store Ltd., with the necessary documentation to tackle instances of infringements (e.g. when sending out _Cease and Desist_ notices to parties at fault) and when seeking legal recourse. This documentation will be available on the [PINE64 Wiki](https://wiki.pine64.org) next month. For those of you who wonder, here are the general rules concerning the use of the PINE64 logo and brand-name. You are allowed to use, alter and replicate both the logo and brand-name for non-commercial use without any prior consent. This extends to both software and non-software material. If you are one of our partner projects you’re welcome to use our logo alongside your own in commercial software or in promotional materials. For small-scale commercial use benefiting the community - such as, for instance swag, hardware add-ons or embellishments (e.g. protective vinyls) - you’ll receive consent after contacting us. All other use of the PINE64 logo or brand-name in a commercial context requires consent which can only be granted by Pine Store Ltd., in a legally binding document.  

Lastly, if you haven’t done so yet I’d like to invite you to watch Matthew (fire219) Petry’s talk on Matrix’s Youtube channel. Matthew spoke about the PINE64 community, the separation of competences between the community and Pine Store Ltd., as well as his hurdles with getting the ROCKPro64 cluster fully functional. 

https://www.youtube.com/watch?v=tJ8tthkVAOQ&t=1s

**Open Tech Will Save US Meetup #5**

##### PineBook Pro

Let me start by assuring you that the current Pinebook Pro batch is still [on schedule](https://www.pine64.org/2020/07/20/pinebook-pro-pre-orders-open-with-shipping-in-august-2020/) and will be delivered to us, from the factory, on August 24. This is yet another large batch of Pinebook Pros, and it will surely bring in new developers to the existing talent pool as well as draw the attention of prospectus partner projects. As you will find out further on in this section, this is also arguably the best time to be getting your unit as support for the device is growing. As for the hardware itself; for this batch of Pinebook Pros - as well as for all future production-runs - we are using a third-party QA service to give the laptops a thorough check prior to shipments going out. This is an arrangement which we reached via a mutual understanding with the new Pinebook Pro factory. We trust this will further reduce reports of DOA units and other types of hardware failures.

The big news of this month is that elementary is currently testing a pre-release of elementary OS 6 _Odin_ for the Pinebook Pro. For those of you unfamiliar with elementary OS, it is a sleek distribution built on Ubuntu LTS, which ships with a (subjectively) beautiful and simple GTK desktop environment called Pantheon and a tailored store - the AppCenter.  When the build becomes publicly available, it will offer a tailored experience for the Pinebook Pro, featuring countless tweaks to make Pantheon run well on the hardware. I also feel it is worth mentioning that the Pinebook Pro is the first Arm device to receive support from elementary. Needless to say, we are thrilled to see another highly requested OS land on our platform, and we’re thankful to the devs for all their effort in making this happen. I have now been running elementary OS on my Pinebook Pro for the past couple of weeks and I am happy to report that the experience is already very solid. I highly encourage you to visit [elementary’s website](https://elementary.io/) and join their friendly [community](https://www.reddit.com/r/elementaryos/). If you can’t wait to try the build out, then please consider supporting elementary via GitHub sponsors - [builds.elementary.io](https://builds.elementary.io) - as this will grant you early access to the OS image.

![](/blog/images/elementarydocked.jpg)

**Docked Pinebook Pro running elementary OS pre-release**

Lastly, I know many of you are waiting for an update on the Pinebook Pro dock. Let me premise this section with an explanation that we’re ready to pull the trigger on production for the dock literally any day now. Developers have, however, been struggling with making the digital and analog (VGA) video outputs work properly and this has held back our decision to start the manufacturing process. That said, this past Tuesday I met with ayufan over a pint of beer in Warsaw and asked him to help the current efforts to make the dock fully functional. I hope and trust that his input will speed the enablement process along. As mentioned in previous community updates, I  have been internally torn whether to show the dock or not because there is still an uncertainty whether we’ll proceed to manufacture this design, but ultimately I feel that the community waited long enough to see what we’re contemplating. I am including a picture of a docked Pinebook Pro below, with all the ports of the dock exposed. Please keep in mind that until we know we can have all of the functionality worked out this is still just a tentative design which may change.

![](/blog/images/dock.jpg)

**Proposed Pinebook Pro Docking Station**

##### PineTab

Let me get the bad news out of the way first - PineTab has suffered a 7 day production delay. The delay is caused by a mistake, which caused the volume buttons to be swapped around (vol - and vol +) on the flex cable. This is something which could easily be remedied is software, but we decided to do it properly from the get-go. In result the small cable hosting the volume buttons had to be scrapped and redone from scratch. Based on the present production schedule, the PineTabs will be delivered to us on August 21, and we will see to it that they are shipped out as soon as possible. We apologise for this slight delay.

On a positive note, I have a handful of good hardware news to cover. We have now received the RTL-SDR and LoRa expansion board samples for the PineTab. The RTL-SDR expansion board comes from a highly reputable vendor and uses 0.5ppm TCXO as well as tantalum capacitors. The LoRa expansion boards can either be fitted internally or attached to a USB port. We hope that the addition of a USB header on the expansion board will broaden its development opportunities as all of our hardware, and just any other computer with USB, can interface with this module.

![](/blog/images/RTL.jpg)

**PineTab RTL-SDR expansion board**

The LTE expansion board is still under development, but when completed it will feature the same LTE EG-25G modem found on the PinePhone. We’re also happy to announce that GPS functionality will work on this interface board just as it does on the PinePhone. In fact, we expect modem features which work on the PinePhone will function on the PineTab fitted with the LTE expansion board.

![](/blog/images/lora.jpg)

**LoRa expansion board/ USB dongle**

The last bit of news I wish to cover concerns the Ubuntu Touch OS build that will ship with the PineTab. The build is still very much a work-in-progress piece of software, but it has benefited greatly from all the PinePhone development as both devices share core components. That said, a handful of quirks remain to be worked out; notably, PineTab’s trackpad doesn’t currently work - at least not well - with the Ubuntu Touch build. In short, the trackpad behaves erratically making the cursor ‘jump around’ instead of tracking as it should. Rest assured this is not a hardware issue - we checked and confirmed this already. We hope that one of you early adopters will help in solving this mystery.     

Lastly, for those of you who did not pre-order an early adopter’s units and hoping to get their hands on a PineTab, you’ll be glad to know that we will reopen pre-orders later this month. Before proceeding to production we will, however, want to hear back from early adopters so that their testing and experience can be accounted for prior to commissioning the next production-run. Please stay tuned to this blog and follow us on Twitter or Mastodon to be notified when the pre-orders go live.

##### PinePhone

I feel like we have finally gotten into a good production rhythm; it was only last month we announced the postmarketOS Community Edition of the PinePhone, and this month I am here to tell you that the factory will deliver the phones to us at the end of this month. Moreover, the presentation boxes featuring the (top secret) postmarketOS artwork and USB-C docks have all been delivered. I don’t know about you, but I think that this is a rather good production pace. At the time of writing, and based on current sale rates, the postmarketOS production-run will sell out in a matter of days - so if you’re on the fence whether to pick one up, then this is your last chance to make a decision. While I have no further announcements at this  time, what I will say is that we have no intention of slowing down the pace now until February 2021 (when Chinese New Year begins). So if you’re interested in the PinePhone, then I strongly suggest you subscribe to this blog for any future hardware announcements. 

Some really awesome projects related to the PInePhone have surfaced this month. We have literally seen a boat-load of cool and innovative things people have attempted at tackling, but three stand out as particularly ambitious - at least to me. The first of which is a [fingerprint scanner for the PinePhone](https://www.reddit.com/r/PINE64official/comments/i8l25y/progress/), which will interface with the phone via pogo pins. I know very little about how far along this project is, however the person working on it assured the community on our subreddit that the software is coming along but the hardware is still a way off. If his implementation works well, then we may see a custom PinePhone back-cover with a fingerprint scanner in the future.

![](/blog/images/fingerprint-768x1024.jpg)

**Picture showing fingerprint scanner icon on PinePhone - [image source](https://www.reddit.com/r/PINE64official/comments/i8l25y/progress/)**

The second project that caught my attention was Martijn Braam’s video showcasing the addition of hacking a thermal camera into the PinePhone. To be precise he added a MLX90640 thermal camera module, with a 32x24 pixel resolution, making use of the standard Linux i2c driver. The module, Martijn writes, is similar to the Flir lepton module you can get commercially to attach to your existing Android or iPhone smartphone. While this mod will never become an official add-on (since I cannot see any broad demand for this in the community) it is yet really quite awesome. Also, both the PinePhone and Pinebook Pro in the video are running postmarketOS - pretty cool right? 

https://www.youtube.com/watch?v=lFsQpd0bLTY

 **Martijn Braam’s video adding a thermal camera to PinePhone**

Lastly, via a community effort (I have been specifically asked not to credit one particular person), numerous users have begun creating their own PinePhone cases. I have now seen numerous people who replaced their PinePhone mid-sections and back-covers with their own 3D printed versions. I hope that in the future we’ll see many community-made variations of the PinePhone body, and I truly hope that some of them will be capable of housing new hardware additions.

![](/blog/images/3dprinted-768x1024.jpg)

**PinePhone 3D printed mid-section**

In other hardware news, you’ll be happy to hear we have three solid candidate options for a PinePhone keyboard. We’re currently investigating which out of the three choices are something we could invest in and move forward with. All the options can be configured as a slide-out or clam-shell design and they all offer different functionality. There are many pros and cons to weigh in on so the process of selecting the right reference design may take another month or two. In the meantime, we’re looking forward to hearing and seeing [what you can come up with](https://www.pine64.org/2020/07/29/invitation-to-play-along/). We’re always waiting for community submissions, so if you come up with a design that is both innovative and holds the potential for mass-produce then make sure to let us know - we’re all years. 

As a closer for this section, here is a quick run-down of some (not all! - apologies to devs if I left something out) notable software developments in the past month. For starters [Ondrej (Megi) Jirman](https://github.com/megous) has been working on power consumption optimisations which include the modem and the LCD panel. I believe that work on the LCD is still very much still a work-in-progress, but modem’s power management has already [been published](https://xnux.eu/devices/feature/modem-pp.html). In Ondrej’s own words, power management of the modem comprises _“letting the modem sleep when it's not in use, and waking it up when it's needed for something, and letting the host sleep, and configure the modem to wake the host up, when some important event happens (incoming call, sms, …)_” This is a development, which we expect will push the PinePhone well beyond a 24hrs battery standby time soon. 

In other exciting news, postmarketOS developers have released and shared a [mobile configuration for Firefox 78](https://gitlab.com/postmarketOS/mobile-config-firefox), which allows all projects that allow installation of Firefox to scale the browser properly on the PinePhone. Until this point in time, projects had to rely on Firefox ESR 68, because scaling on newer software versions presented the user with tiny UX elements. This config comes just-in-time as Firefox 68 is about to reach EOL. 

Ubuntu Touch fans should rejoice as UBports developers have managed to enable both GPS and the camera. These features are currently available in the development channel, which can be switched to in the Software Update settings panel. Moreover, I have been told that GPU acceleration for the Morph browser is coming to the PinePhone soon. Earlier this month Marius from UBports tweeted a video showcasing the browser smoothly scrolling through a lengthy section of search results, rendering a webGL demo and playback of youtube videos. These changes will surely make the next stable OTA update for the PinePhone. 

https://www.youtube.com/watch?v=OARRK6bEgiE&feature=youtu.be

**Accelerated Morph Browser on Ubuntu Touch - via Marius Gripsgard (UBports)**

Manjaro have released new alpha builds featuring both Phosh and KDE Plasma Mobile. The Phosh build is really far along and offers all core functionality, including telephony, GPS, LTE, BT and even the camera. It is also, subjectively, one of the snappiest experiences on the platform. That said, the Manjaro team is also planning to release a Lomiri (formerly Unity8) build for the PinePhone, which is said to run spectacularly well. To me, however, the most important aspect of this build version concerns the cooperation between UBports and Manjaro, which started on our community platform.

![](/blog/images/lomirimanjaro-576x1024.jpg)

**Manjaro Running Lomiri UI - [via Spikerguy (Manjaro)](https://twitter.com/fkardame/status/1293681887572107264/photo/1)**

Lastly, I feel like it is worth mentioning that multiple operating systems now support Anbox. If I understand the technology correctly, Anbox is basically Android running inside a container on the PinePhone. This will, in time, allow users to access some native Android applications unavailable on Linux. I suspect that this will become a common solution for those who need their city transport, shopping, banking or other Android applications available on the go. I do not have an up-to-date list of all distributions that currently support Anbox, but some of the favorites including Mobian, postmarketOS and the community built Arch Linux now all have the capacity to run Anbox.  

https://www.youtube.com/watch?v=v06KUrfs69k

**Anbox on PinePhone running Mobian - via** **[LINMOBnet](https://www.youtube.com/channel/UCR-_DvrwKkk3rpQbzCRFHOw)**

##### PineTime \[****_authored by_** [**_JF_**](https://twitter.com/codingfield)**\]

In the last community update, we announced that the next batch of Pinetime devkits will be programmed at the factory with my project (now renamed InfiniTime, more about this further in this post). Since then, the devkits are not yet available on the shop, what happened?

Well, I sent the binaries from the latest release to the factory. Many people from the chat rooms installed this release on their device and checked that it was working correctly, with positive results, yay!

But... It was not working so well at the factory. One important thing to know is that we are all working as hobbyists, amateur embedded software developers using hobbyist hardware and setup. To give you an idea, here is a picture of my desk with my Pinetime devkit and its debugging wires on the left, and my NRF52-DK board hooked on my small digital logic analyzer on the right.

I didn't visit the factory, but I'm quite sure that the production line does not look like my desk, and they most certainly use other tools and softwares that are more appropriate for mass production than mine.

A good example is the external flash memory. Yes, the Pinetime has 2 flash memories : one integrated in the MCU (512KB) and one external (a huge 4MB) connected to the MCU via a SPI bus. For me, the only way to program this external memory is by writing a special firmware that writes data to the flash memory. This is time consuming, and not practical at all, but that's all I have. At the factory, they use another hardware to program this SPI memory: a SPI programmer. This tool, connected to test points on the PCB, is able to program the SPI memory easily and at high speed. So I had to convert my little firmware that writes data to the external memory into a file that this SPI flash programmer understands… without having the means to check that this file is actually working!

And this is just an example of the difficulties we encountered. We also had to find the correct file format for the firmware, merge the bootloader and the firmware into a single file so that they can actually use the files on their setup and use their procedure.

Last but not least: time zones and language barriers did not help this process. The factory is located literally on the other side of the planet and when I sent screenshots of my software setup in French, they would answer me with screenshots in Chinese. We needed some time to understand each other :) There is good news however: David, the production manager, told me yesterday morning : "It looks like it's working again. I will test a few more times". Let's hope it will work correctly with many pinetimes so that they can start the production of the new devkit!

Aside from production issues, here are other news.

I have (finally) decided to release Pinetime-JF under the GPL3 license, and to rename it "[InfiniTime](https://twitter.com/codingfield/status/1289954080845172741?s=20)". I want this project to be a community endeavour and not just "JF's firmware" and I think it was the right move to achieve that goal! We are investigating solutions to reconcile our MCUBoot based bootloader with SoftDevice based firmwares which could make the OTA from one to another possible. Without going into details, for now, it is not possible to go from ATCWatch or Wasp-os to InfiniTime and vice-versa. In the end, our goal is to be able to switch between completely different platforms.

New people keep on coming in the community chat and they start working on new features. For example, some of them designed shiny new boot logo and new watch faces.

![](/blog/images/pinetimeface.jpg)

**PineTime boot logo and watchface - via [Lup Yuen Lee](https://twitter.com/MisterTechBlog/status/1293326281547739136/photo/1)**

Wasp-os found a way to implement step counting and heart rate monitoring using free software/open source drivers and Hypnos, a Zephyr-based firmware is making great progress and is looking to implement the OTA functionality.

Finally, as long as I have the floor, I take this opportunity to encourage all developers who are interested in developing an open-source firmware for an open source smartwatch to join us in the chat rooms or forums! There are many projects to join, and a lot of work to do to change the world and create a complete ecosystem around the Pinetime and the Pinephone!

##### Pinecil 

We’re well on track to start production of the Pinecil at the end of September. We have already received the PCBs and assembled a small number of (PCBA) units for testing and development purposes. In my last community update I mentioned that the Pinecil is a truly open platform, and for those of you up to a challenge, it can be made into a completely different device. To this end, we’re happy to report that the Pinecil’s memory has been doubled for the production version, which further increases its versatility; given the ease with which you can program the device, you can truly think of the Pinecil as something much more than just a soldering iron.  

![](/blog/images/pinecilpcba.jpg)

**Pinecil PCBA**

Presently we’re waiting for the factory to deliver the first samples of the Pinecil body to us. Many of you have correctly identified that the Pinecil will be quite different to the TS100 in terms of overall layout and ergonomics. The buttons on the device will be located on each side of the display; we found that users tend to hold the iron horizontally when accessing settings, so this button placement makes it more sense from a UX perspective. The device will also be slightly longer - to accommodate the USB-C and power jack - and feature a rounder and rubberised segment where you rest your fingers. These are small tweaks in the grander scheme of things, so the iron should feel familiar to those who use a TS100, but we think they will go a long way to improving the overall experience of using the device.    

We will also be selling a high quality 4 tip set for the Pinecil upon release. At this point I need to come clean and say that I know very little about soldering irons and tips in general, so you’ll have to wait a little longer to hear exactly what variety of tips the kit will include. That said, I have been told these will be high quality tips which, as you have come to expect from us at this point, will be priced lower than anything else on the market.

##### PineCube

We were really surprised by how many of you showed an interest in the PineCube when I initially announced that the device is making a return from a two-year-long hiatus. Since the PineCube is really the first (that we know of) dedicated FOSS IP camera, we had no idea that there were so many of you awaiting this type of device. Today we’re happy to let you know that the PineCube has successfully passed CE/FCC certification tests and production of the device has already begun. We presently expect first units to roll off the factory line at the end of September or early in October and be available for purchase soon thereafter. 

With so much interest in the PineCube we already started preparing peripherals and add-ons for the device. The first two things that ‘just work’ with the current Linux build are a 40 pin LCD panel and a 1350mAh battery. Combined with the PineCubes GPIO pins and networking, these two accessories really extend the device's versatility. I can well imagine people using the PineCube in conjunction with the battery to make an ‘action cam’ for a quadcopter or a scientific experiment, such as a weather balloon. Batteries sold in the PINE Store will likely only be available to community members in the US, but similar batteries are already available from reputable tinkering or hardware online shops.  

![](/blog/images/Cubebattery.jpg)

**PineCube with battery in chassis**

As the name entails the PineCube comes assembled into a small cube. But the device is actually constructed out of 3 PCBA pieces connected via flex cables: the front PCBA (with sensors and IR LEDs), the camera module in the middle and back PCBA (with networking, SoC and GPIO). If required these can be detached from the plastic frame; this is something we imagine can be useful when embedding the device, especially in an industrial or project scenario. I am including a picture of the PineCube pieces detached from the frame and a LCD displaying camera feed and debugging information attached. 

![](/blog/images/cubeLCD-792x1024.jpg)

**PineCube disassembled and LCD attached**

We do not have any announcements concerning LCD panel and battery pricing but as I am sure most of you have come to expect the pricing of both items will be more than fair. More information about the LCD panel will be available closer to the date as we reach an agreement with the vendor. 

This is all for this month, hope you too are somewhere nice and sunny!
