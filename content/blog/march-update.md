---
title: "March Update: Status Report"
date: "2021-03-15"
authors: ["Lukasz Erecinski"]
categories:
  - "community"
  - "pinebook-pro"
  - "pinephone"
  - "quartz64"
  - "soedge"
tags: 
  - "pinebook-pro"
  - "pinephone"
  - "quartz64"
  - "soedge"
cover:
  image: "/blog/images/marchupdate-1024x594.jpg"
images:
  - "/blog/images/marchupdate-1024x594.jpg"
---

![](/blog/images/marchupdate-1024x594.jpg)

Welcome to this month’s community update. We’re now facing one of the most challenging electronics manufacturing circumstances in years, and possibly even in all of electronics history. Despite this, I’ve got some good news to relay this month, including a Quartz64 pilot production-run, SOEdge being available next month and plenty of community news. _Last minute update: looks like we will have the PinePhone and Pinebook Pro for pre-order next week too, hurrah!_

You can watch the synopsis of this month’s community update on YouTube (embedded below) as well as on [LBRY](https://lbry.tv/@PINE64:a) and [Peertube](https://tilvids.com/accounts/pine64tilvids/video-channels). Stay up-to-date with PINE64 news and make sure to subscribe to this blog (subscription widget at the bottom of the webpage), follow [PINE64 Telegram News channel](https://t.me/PINE64_News) as well as our [Twitter](https://twitter.com/thepine64) and [Mastodon](https://fosstodon.org/@PINE64).

I’d like to acknowledge [JF](https://twitter.com/codingfield), [Marek](https://twitter.com/gamelaster) (Gamiee), [Alex](https://twitter.com/AlexRob12252696) (clover), and [PizzaLovingNerd](https://www.youtube.com/channel/UCmGcm7dhEjS9CIOsOOv8y6w) for their contributions to this community update. Thank you!

Let's get to it.

{{< youtube id="c7fflSOUUlY" >}}

**Video synopsis of this month's Community Update**

**TL;DR** 

- Housekeeping pt.1: we’re facing difficult manufacturing circumstances - pre-orders for Pinebook Pro & PinePhone will open after production is underway.
- Housekeeping pt.1: stock availability of SBCs, SOMs and other devices will likely change on a weekly basis 
- Housekeeping pt.2: we’re working on a stock and pre-order tracking system for the Pine Store
- Housekeeping pt.2: the PineOne riddle was solved in record time
- Housekeeping pt.2: I was on FOSS-North podcast talking about PINE64
- Housekeeping pt.2: fourth episode of PineTalk is out; PineTalk has been listed on Podcast Index 
- SOEdge: SOEdge AI module now fully functional thanks to Marek (Gamiee); runs BSP Linux and build is tailored to support existing PINE64 hardware / peripherals
- SOEdge: the SOEdge baseboard and USB 3.0 adapter are currently being produced, and will be back next month, at which point they’ll go on sale; expect availability in April 
- Quartz64: The current situation forced our hands - we started a Quartz64 pilot production-run; available in April
- Quartz64: 8GB RAM Quartz64 units started shipping to developers this week 
- Quartz64: e-ink panel now works with Quartz64, and the performance is really good from what I’m told 
- Quartz64: model-B of the SBC placed on temporary halt, due to component shortages
- Pinebook Pro: we’re aiming to start production later this month, at which point pre-orders for the new Pinebook Pro batch will open **\[last minute edit: pre-orders likely to start next week\]**
- Pinebook Pro: a price increase forced by the market situation - $220 for current PBPs, may further increase in the future 
- Pinebook Pro: phenomenal Armbian with GNOME desktop OS images are feature complete and utilize Panfrost FOSS GPU drivers for desktop acceleration
- Pinebook Pro: postmarketOS for the Pinebook Pro is now available, looks awesome, and features a neat installer utility with disk encryption
- Pinebook Pro: Manjaro now offers a MATE OS image alongside KDE, XFCE and tiling managers (Sway / i3)
- PinePhone: production hurdles at the time of writing; an explanation of the situation **\[last minute edit: pre-orders likely to start late this month\]**
- PinePhone: we’re still hoping to start taking pre-orders soon, however we need to wait for production to start; presently difficult to define when exactly factory can source missing component
- PinePhone: the upcoming production-run, and subsequent few, will be called _Beta Edition_ to indicate software status
- PinePhone: the keyboard is progressing well - but we’re still waiting for the keycaps; they should be delivered later this month
- PinePhone: the fingerprint scanner case is coming along as is the Qi-wireless charging case, but those will first be introduced when the manufacturing situation eases
- PineTime: InfiniTime has seen 3 releases in a matter of a month; new firmware functionality and a new bootloader
- PineTime: WaspOS has also seen a new release and is now supported by Gadgetbridge
- PineTime: two new companion apps for the PineTime, which can be used with the PinePhone and an update to Amazfish 

### Housekeeping pt1: production hurdles 

Last week [we notified](https://twitter.com/thepine64/status/1370094160338948097) our user base that we will only start taking pre-orders for our popular devices like the PineBook Pro and the PinePhone, once production is securely underway. Pine Store inventory items such as the Pinecil, the PineTime dev kits, and the SOPine modules have also drifted in-and-out of Pine Store’s stock over the course of past weeks. This is the result of very severe manufacturing circumstances that have affected the entire electronics industry, and our neck of the woods is no exception. As things stand, all components, down to discrete transistors, have lead times of 40 weeks or more. RAM and eMMC memory, as well as key parts such as LCD panels, are in severe shortage and have in some instances seen their prices double since March 2020. The lead time on LCD panels, just as an example, is currently 60+ weeks, so the expected delivery date falls well into 2022. Silicon is not exempt from this: SoCs such as the A64 are also in short supply and have seen their price increase by a third. 

![](/blog/images/routers-1024x485.jpg)

**This now affects much of the electronics industry, including tech giants - via [Reuters](https://www.reuters.com/article/us-chip-shortage-qualcomm-idUSKBN2B32OO)**

I am trying to find a suitable analogy, which would somehow illustrate the situation. The best I can do is this: do you remember the toilet paper and hand sanitizer shortages at the beginning of the COVID19 pandemic in the West? - it’s like that, but with transistors, PC/phone parts and silicon. Similarly to the spineless scalpers who sold hand sanitizer for $10+ on eBay to the panicked public in 2020, many component vendors are exhibiting out of character behaviour, preying on factories and businesses in distress. Quoting the words of a factory head we work with: _“I haven’t seen anything like this in the 15 years that I’ve been in the business.”_ Worst of all, there isn’t a clear path out of this situation for factories or businesses. The situation is currently growing more severe and there is no end in sight. 

So, why am I writing all this? Because I want to put out the word that we at Pine64 will be more cautious with taking pre-orders for devices, as well as actively monitor Pine Store stock. With regard to devices such as the PinePhone or Pinebook Pro: we don’t want to open pre-orders today just to find out in a week or two that the factory doesn’t have the means to deliver stock for weeks or months. I’m sure that you ultimately prefer to patiently wait, and have certainty that the device will be delivered in a timely manner, rather than have us hold onto your money for an extended period of time. As for single board computers, compute/AI modules and smaller devices such as the PineTime or Pinecil: since we cannot assure a steady flow of such devices from the factory, we’ll only sell things we currently have in our inventory. We currently keep selling units whilst awaiting delivery (usually every week or two), but for the foreseeable future we’ll halt the sales until the next production-run is physically delivered. So expect to see such stock pop up every couple of days or weeks as new deliveries arrive at the warehouse.

I hope this clarifies the situation. At the same time I ask you not to bombard info and sales with questions about availability - they don’t have up-to-date insight into the production status. Instead, please subscribe to the [Telegram News Channel](https://t.me/PINE64_News). It isn’t a chat, it is just a stream of announcements, and presently the best way to be notified of device availability. We’re working on an availability tracking solution (read pt.2 of the _Housekeeping_ section for details) but it will take some time to implement. 

### Housekeeping pt. 2: community insight 

We are working on a system that would allow users to track product availability and expected pre-order windows. If you read pt.1 of _Housekeeping_, then you already know that this wouldn’t really be of any help to us now due to production uncertainty, but it is something that end-users will benefit from in the future once the world returns to normal (whenever that may be). Frankly speaking, we also hope that this will unburden support, info, and sales teams currently spammed by questions of availability. We will be testing out the system next month, or the month after that, and we’ll likely start with one of two devices which aren’t at production risk. If you know of a company that has a good product availability system in place, then please share it in the comments section - I’ll make sure to take a look at it and show it to Matthew (fire219) and Marek (Gamiee). 

Last week I posted the [PineOne riddle](https://www.pine64.org/2021/03/09/risc-v-sbc-riddle/), and to my surprise it was cracked in record time. I’d like to congratulate Dalton who was the first to solve the cyphre and provided a detailed explanation of his thought process. I must say I was shocked by how fast this riddle was deciphered - I really expected it would take hours, or even days, for someone to correctly identify the solution. This is the third riddle we’ve done as a community and judging from the response I feel that people find it to be good fun. There aren't any other announcements on the horizon currently, but once the next opportunity arises I’ll make sure to involve people with some knowledge of riddles to come up with something more challenging. I may also rethink how we select the winner(s) - time zones make it difficult for some people to participate, making the exercise a bit unfair to our friends in Asia and Oceania. 

I was recently on [FOSS-North podcast](https://foss-north.se/pod/) talking about PINE64, our strategy of community engagement and our plans going forward. I encourage you all to take a listen when the episode airs. In the meantime, FOSS-North has an extensive backlog of tremendous content with some of the most insightful industry insiders. The podcast is a part of a FOSS conference taking place in Gothenburg, Sweden; they have put out a [call for papers](https://foss-north.se/2021/contribute.html#papers) and everyone is welcome to submit written material. Check them out.  

On the subject of podcasts, our very own PineTalk podcast has recently been added to the [Podcast Index](https://podcastindex.org/podcast/1385929). There is now also a PineTalk [Mastodon account](http://@talkpine@fosstodon.org) to make it even easier for you to interact with Peter and Ezra, ask them questions, offer feedback and suggest discussion topics. Their most recent episode aired last Friday - the guys discussed video calls on the PinePhone, RISC-V GPUs, offered their views on your suggestions for future PINE64 gear and responded to community questions. Have a listen to the latest episode [here](https://www.pine64.org/2021/03/12/004-gpu-o-rama/). 

### SOEdge 

For those of you who do not know, or do not recall, the SOEdge is a powerful AI module in a SODIMM form-factor; you can learn more about it [here](/documentation/SOEDGE/). Thanks to Gamiee’s hard work, the SOEdge is finally ready for prime-time, as we can now run a [fully functional BSP Linux](/documentation/SOEDGE/Releases/) on the AI module. The Linux build is capable of utilizing the SOEdge’s powerful NPU and includes enablement for all core functionality of the module. This includes, but is not limited to, Gigabit ethernet, USB, PCIe as well as the LCD DPI interface with touch input. I am told that, when inserted into a model-A sized SOPine or SOEdge baseboard, the SOEdge is also able to utilize either of our WiFi and Bluetooth SDIO modules. Getting the SOEdge build operational was a monumental undertaking and Gamiee did a phenomenal job not only in bringing Linux to the platform, but also in having the software support existing PINE64 hardware. As you can see in the attached video, the SOEdge Linux build has been customised to also work with existing PINE64 hardware, such as for instance the [7” Pine A64 LCD touch panel](https://pine64.com/product/7-lcd-touch-screen-panel/?v=0446c16e2e66).

{{< youtube id="G-L3rPQhEOM" >}}

**SOEdge Linux test image booting with a LCD touch panel attached**

While the SOEdge is capable of working on the SOPine baseboard, thanks to pin-out compatibility of both the SOPine and SOEdge modules, we’re currently in the process of producing a SOEdge-specific baseboard which, among others, will expose PCIe - not present on the SOPine mainboard. Thanks to the SOEdge’s pin-out compatibility with the SOPine, it can also be inserted into the Clusterboard. You can even mix and match SOEdge and SOPine modules on the Clusterboard to achieve a very interesting computational and AI setup. Indeed, the possibilities are truly substantial. You could, for instance, also populate all Clusterboard slots with SOEdge modules, and equip each module with a USB UVC camera. I’ll come clean and say that I know very little about AI, but I can imagine that from a machine-learning enthusiast’s perspective the prospect of having 7 AI modules, paired with 7 cameras, in a compact mini-ITX enclosure is quite compelling. 

![](/blog/images/Clusterboard-with-both-SOEdge-and-SOPine-766x1024.jpg)

**SOEdge and SOPine modules in the [Clusterboard](https://pine64.com/product/clusterboard-with-7-sopine-compute-module-slots/?v=0446c16e2e66)**

The SOEdge baseboard should be back from the factory next month along with a USB 3.0 adapter board allowing the SOEdge to couple with any USB 3.0 enabled X86 PC or single board computer. We’re currently planning on having the SOEdge, the SOEdge baseboard and USB 3.0 adapter board available in the store mid-April. 

### Quartz64

We decided to produce a pilot batch of Quartz64 model-A single board computers (SBCs). The current manufacturing situation has, in a sense, forced our hand. We originally planned on a much slower roll-out of the board(s), with an extensive development cycle proceeding the launch, but with the production window closing rapidly, we ultimately decided to take a leap of faith and push the ‘go’ button. As a result, the first boards will be available late next month. I cannot stress this enough - this production run is aimed strictly at developers, not end-users. If you want a fully functional SBC at present time, then I encourage you to pick up a ROCKPro64 or PINE A64-LTS (depending on how much performance you require) instead. It will take time for Quartz64 to reach its full potential, and if you’re not interested in participating in the bringup development process then you’d be wise to look elsewhere for SBCs for your computational or project needs. 

![](/blog/images/8GBQ64s-575x1024.jpg)

**First 8GB RAM Quartz64 SBCs heading out to developers**

Speaking of development, the first 8GB Quartz64 boards have just been dispatched to contributors participating in the early bringup process. With more people participating in development, I expect to have more early software progress to relay next month. As things stand, the product team managed to boot Rockchip’s Board Support Package (BSP) Linux with kernel 4.19 on Quartz64 and enabled some of the board’s basic functionality for testing. Community developers, however, haven’t been able to boot the board into Linux yet. It’s still very early days, so we’ll need to wait a little longer to see Linux running on the device. 

The product and engineering teams have been evaluating various e-ink displays that can be used in conjunction with the board. The e-ink display has now been brought up to work with the Rockchip SDK and the stock Android build. The performance, I’m told, is better than devices with a similar power and thermal envelopes currently available on the market. This is obviously a very exciting prospect, not only for the Quartz64 but also for the devices that it may give birth to. We have obviously seen many of you suggest we use the board as a base for an e-ink type device, and we have given this suggestion a serious thought. But it is one thing for the e-ink panel to work with the default SDK and another thing to have it work with BSP Linux. Yet another thing is mainlining this e-ink protocol. So, yes, we do share your enthusiasm for an e-ink based device built upon the Quartz64, but at the same time recognize that the road ahead of us is likely long and winding.

![](/blog/images/Q64-eink-988x1024.jpg)

**Quartz64 with an e-ink display attached running stock factory Android**

As for Quartz64 model-B, which features a smaller footprint than model-A, it will have to wait a little longer to see the light of day. We’re very happy with the model-B design. However, despite being in possession of approx. 70% of all RK3566 SoCs on the market, we don’t have enough to produce both model-A and model-B simultaneously. This, in conjunction with what I wrote in the housekeeping section, should give you an idea of how severe the silicon shortages truly are. In the end, model-A needs to take priority at this time due to its development focused nature. As a result, the model-B may be delayed for quite some time.

### Pinebook Pro

We are hoping to open Pinebook Pro pre-orders this month, however as I explained in _Housekeeping pt. 1_, this is wholly dependent on production proceeding without a hiccup. As things stand, at the time of writing, the factory plans to begin the manufacturing process the week of 22-28 March **\[_Last minute edit_**_: it looks like we're on track to open pre-orders next week, however only ANSI units will be available at this time_\]. This gives you a general sense of when to expect Pinebook Pro pre-orders, granted everything goes according to plan. This Pinebook Pro production-run will be introduced at a revised price-point of $220, reflecting the component price-hike. As I explained in the [January update](https://www.pine64.org/2021/01/15/january-update-happy-new-gear/), when faced with the dilemma of whether to increase Pinebook Pro’s price point or further postpone production (awaiting component prices to decrease), we will proceed by increasing the price point. At this time, our priority is to resume production, even if the price needs to be increased by 10%. I simultaneously would like to make you aware that the price will likely increase further in future batches. We don’t like increasing the price of our devices but at this point it is simply unavoidable.

![](/blog/images/armbian-1024x771.jpg)

**Armbian with GNOME DE runs great on the Pinebook Pro**

The good news is that this is a great time to pick up a Pinebook Pro. Armbian has recently released [new OS images](https://forum.armbian.com/topic/17192-first-panfrost-enabled-desktop-builds/?tab=comments&_fromLogin=1) featuring Panfrost acceleration. This includes a version of Armbian that ships with the GNOME desktop environment. I have now spent over a week testing out the image featuring GNOME and I have to say that it has been a very pleasant experience overall. I need to come clean at this point, and admit my preference for Manjaro and Plasma desktop, but the GNOME on Armbian runs just as fast as Plasma on Manjaro and all applications, including firefox, are just as responsive. Overall, I must say that I am highly impressed. So to those of you who have been longing for a traditional (and well supported) Ubuntu-like experience on the Pinebook Pro, I finally get to say that this is now a reality. If you already got a Pinebook Pro, then you can get the Armbian Focal with GNOME [here](https://redirect.armbian.com/region/EU/pinebook-pro/Focal_current_gnome). I should mention that Armbian also offers OS images with XFCE and MATE, as well as testing images with Cinnamon and Budgie desktops. 

In other Pinebook Pro software news, we now have a [postmarketOS image](https://images.postmarketos.org/bpo/edge/) featuring kernel 5.11.x and GNOME desktop for the Pinebook Pro. Both a ‘live’ and an ‘installer’ OS image is available. The installer OS image allows you to encrypt your filesystem, set your user name and password as well as tweak a few other variables. Although postmarketOS is primarily a mobile operating system, it is lightweight and tailored to run on ARM systems thanks to its Alpine Linux base. This makes it a natural candidate for running on the Pinebook Pro. I encourage you all to have a look at postmarketOS on the Pinebook Pro - images can be found [here](https://images.postmarketos.org/bpo/edge/).

https://www.youtube.com/watch?v=hjzNr7wnBpk

**Installing postmarketOS on the Pinebook Pro by [Martijn Braam](https://twitter.com/braam_martijn)**

Last but not least, I ought to mention that our friends at Manjaro recently released the [Manjaro Arm 21.02 build](https://forum.manjaro.org/t/manjaro-arm-21-02-released/55788) which will ship with the new production run of the Pinebook Pro. While the Pinebook Pro ships with Plasma Desktop by default, Manjaro now also offers an officially supported MATE OS image for the Pinebook Pro. We have also seen a lot of Pinebook Pro related experimentation on the Manjaro base, most notably a [build by Alex (clover) which features Lomir](https://www.youtube.com/watch?v=UJexp6Y65lw)i (formerly Unity8). From what I’ve been told, Lomiri runs decently on the Pinebook Pro and offers a pretty unique experience on the platform. I should also mention that official Manjaro builds with tiling managers such as i3 or Sway are also available in the [Manjaro repo](https://osdn.net/projects/manjaro-arm/storage/pbpro/).    

### PinePhone 

**\[Last minute edit\]**: _just prior to publishing the update, I got word that we will be replacing the elusive part we cannot source with an alternative; granted no other issues arise, pre-orders will begin late this week or sometime next week. Mind you, uncertainty remains high, so this is still subject to change, but things don't look quite as dire as they did when I wrote this section. A [placeholder pre-order inventory](https://pine64.com/product-category/pinephone/?v=0446c16e2e66) item has been published already on the PineStore. I am leaving the rest of the PinePhone section unchanged because it gives you an insight into current hurdles (and I don't have time to rewrite it extensively)._

![](/blog/images/phones-in-store-1024x594.jpg)

**As soon as we get word that production started, you'll be able to pre-order one**

Let me start by writing extensively about the production status. If you haven’t done so yet, then please backtrack to the beginning of this month’s update and read pt.1 of _Housekeeping_ - it will provide you with the necessary context for understanding the following section. As many of you know we were initially planning on launching PinePhone production last week and opening pre-orders this week. We had all our components (both discrete and key parts) ordered months in advance and the production floor reserved as well. In short, everything required to produce the next PinePhone batch was in place by the time we entered the Chinese New Year in February. At that time we couldn't have predicted that vendors would not hold up their end of the agreement. I’ll spare you the details, they aren’t particularly pleasant nor interesting, but it boils down to this: components we booked in advance were sold to other parties (presumably at a much higher price). We managed to source many of the components we lost, but we’re currently short of one discrete component (usually very easy to obtain) which is nowhere to be found. 

The production team is continually looking for the said component, and the moment they’ll find it production will be able to begin. However, at present time, I simply cannot tell you whether that will be later today, tomorrow, in a month or in 3 months time. I’m sure you can appreciate that we want to open pre-orders for the next batch just as much as you want to place one; but, as I already explained earlier in this community update, this will only only happen once we know that the production is well underway and there are no obstacles in sight. The announcement of PinePhone pre-orders starting will likely drop quite suddenly, without a prior warning as there is no scheduling. Please subscribe to our Telegram news channel, follow us on Mastodon or Twitter to be notified. 

![](/blog/images/PinePhoneBox-1024x596.jpg)

**How do you like the default PinePhone presentation box?**

On the flipside, the good news is that aside from the one missing component we’ve got everything lined-up and ready to go. The upcoming production-run, as well as the next two or three following it, will be referred to as the _Beta Edition_. The term “Beta” indicates the present software status. Despite huge strides made by Manjaro and KDE Plasma Mobile teams in the past 3 months, the software isn’t yet at a stage where we’d be comfortable selling the PinePhone as an end-user ready product; even if the target end-users of the PinePhone are informed Linux enthusiasts. It will be yet a couple of months before the software reaches a status where we’d be willing to pitch the PinePhone as a “_completely functional smartphone for advanced Linux enthusiasts_”. That said, let's take a moment to appreciate the fact that the software has moved out of an Alpha-stage and that core smartphone functionality has now reached considerable maturity, thanks in large part to the Community Edition (CE) scheme which ran throughout 2020. 

The Manjaro KDE Plasma Mobile build has already been submitted to the factory, alongside the default presentation box and documentation. Below you’ll find a render of the default PinePhone presentation box - personally I think it turned out great. I am also attaching the ‘[READ ME](https://wiki.pine64.org/wiki/File:READ_ME.odt)’ note that will ship in the box alongside the ‘Quickstart Guide’ for those of you who wish to read it. Since someone will surely ask: the hardware remains unchanged from the past three community editions, and will feature the [1.2b revision](/documentation/PinePhone/Revisions/PinePhone_v1.2b/) of the PCB.  

![](/blog/images/bk2-1024x768.jpg) ![](/blog/images/kb3-1024x768.jpg)

**Some assembly still required, but we're getting there**

Before finishing the PinePhone section, I want to touch upon the status of the much anticipated keyboard accessory as well as the fingerprint back case. As for the prior, we’re still waiting for the keycap molds to come back from the factory. We were told in the latest communication to expect the keycaps in the second half of this month. The moment I get an update on the keyboard, I’ll make sure to put out a tweet alongside pictures of the PinePhone in a PDA-like configuration. Assuming no issues are found with the molding, we could see the PinePhone keyboard in the Pine Store as early as mid-May. Keep your fingers crossed! As for the fingerprint back case, I’m glad to let you know that considerable progress has been made: the PCB and case design have been submitted for manufacture. We had to make some alterations to the original design by Zachary because of availability and pricing of the chosen sensor. I don’t have an ETA for you at this time, but the case should be ready at some point in Q2 granted the manufacturing situation doesn’t worsen even further.

### PineTime (by JF)

This month I have a lot of news to share about the progress of the PineTime project: we have a new bootloader, InfiniTime and WaspOS released new firmware versions, two new companion apps were created, and Amazfish and Gadgetbridge continue to improve their integration with InfiniTime. Let's start with the bootloader and the [release of the new MCUBoot bootloader for PineTime](https://github.com/JF002/pinetime-mcuboot-bootloader/releases/tag/1.0.0). I've already written about this bootloader in the [January community update](https://www.pine64.org/2021/01/15/january-update-happy-new-gear/), and since then we performed numerous tests to ensure that it works correctly and that the upgrade procedure itself is as safe as possible!

Let me explain. The bootloader is a very critical piece of software that is run when the watch boots up. It's responsible for upgrading the firmware when a new version becomes available and for loading the firmware (InfiniTime, for example). We use [MCUBoot](https://mcu-tools.github.io/mcuboot/) as the base of the bootloader. MCUBoot ensures that the upgrade of the bootloader is 100% safe by swapping the old and new version of the firmware in memory. In the event an unexpected error occurs, it is able to revert to the old version of the firmware. Any issue with the bootloader could temporarily or permanently brick the PineTime, and that's why we put a lot of effort into the bootloader.

Upgrading the bootloader is also a critical operation as there is no fallback in the event an error occurs during the upgrade. From the feedback I received until now, it looks like everything is working well and that it's fairly safe to apply the update. You just need to [read and apply the instructions](https://github.com/JF002/pinetime-mcuboot-bootloader/blob/339224cf5ed21f4e8b2d22eaeab9869120f7f752/docs/howToUpdate.md) carefully.

See the [video here](https://video.codingfield.com/videos/embed/831077c5-16f3-47b4-9b2b-c4bbfecc6529).

**Video of the new bootloader**

All of this would not have been possible without [Lup Yuen](https://github.com/lupyuen)'s work. Lup was the first to dare work on a bootloader for the PineTime, and this new version is mostly an improved version of his original work. We fixed a few bugs and added some features like a basic UI and a recovery firmware. This recovery firmware can be loaded by keeping the button pressed while the bootloader is running and allows the user to OTA a new firmware in case the current firmware does not work correctly and/or does not provide the OTA functionality.

Since last month 3 versions of InfiniTime were released; InfiniTime [0.12](https://github.com/JF002/InfiniTime/releases/tag/0.12.0) and [0.13](https://github.com/JF002/InfiniTime/releases/tag/0.13.0) improved the BLE connectivity by a lot! While it is still not perfect, BLE connection is now more reliable. Users should notice less unexpected disconnections and fewer failed OTA firmware upgrades. Version 0.13 also added vibrations on notifications and  notification on call - when your phone receives a call, the companion app sends a notification to InfiniTime with the name of the caller. The notification app allows the user to accept, reject or ignore the call on the smartphone.

[InfiniTime 0.14](https://github.com/JF002/InfiniTime/releases/tag/0.14.0) "Green Avocado" brought the first UI update of InfiniTime, thanks to [Joaquim](https://github.com/joaquimorg/)'s work! Joaquim did an awesome work updating [LVGL](https://lvgl.io/), the open source graphics library we use in InfiniTime. This new version brings many features that will be useful to create nicer apps and watchfaces. Joaquim did not stop there and also improved the UI of many applications, like the notification app, which is really looking good now!

![](/blog/images/800-600-max.jpg)

**InfiniTime 0.14 UI element redesigns look phenomenal**

[WaspOS](https://wasp-os.readthedocs.io/en/latest/index.html), the MicroPython based firmware also released a new [0.4 version](https://wasp-os.readthedocs.io/en/latest/TODO.html#id12). The main focus of this version was the integration of the watch with the phone. WaspOS worked with Gadgetbridge and the last version of the Android companion app now supports WaspOS. Version 0.4 also added a nice analog clock face, new UI widgets and a brand new theming engine.

https://www.youtube.com/watch?v=nps8Kd2qPzs

**Wasp-OS doesn't just look great, it also features a tonne of functionality**

Companion app developers did not rest this month either; clover aka [Alex Robinson](https://twitter.com/AlexRob12252696) released [Siglo](https://github.com/alexr4535/siglo), a GTK based companion app for the PineTime. It's capable of synchronizing time with InfiniTime and I heard that Alex is working on adding the OTA flashing functionality to the app. Another new companion app (yes, a second one!) appeared in the PineTime ecosystem. [WebBLEWatch](https://github.com/hubmartin/WebBLEWatch/) is a web based application that uses WebBLE (on Chrome) to connect and set the time on InfiniTime. [Martin](https://github.com/hubmartin), the developer of this app, describes it as a proof-of-concept, but I do really hope he'll continue the development and will add the OTA functionality in the near future ;)

You can [try this web application online](https://hubmartin.github.io/WebBLEWatch/) if you are using the Chrome web browser.

[Gadgetbridge](https://gadgetbridge.org/), the Android companion app released [version 0.55](https://blog.freeyourgadget.org/release-0550.html), which fixes the music controller app (we broke it by changing the BLE UUIDs in a recent upgrade of InfiniTime...) and also adds the support of the call notifications. Finally [Amazfish](https://github.com/piggz/harbour-amazfish), the Linux companion app by [Adam](https://twitter.com/adampigg), also added the support for call notifications and improved the way notifications are displayed. Now, the name of the application pushing a notification and the full text message is displayed in the notification app in InfiniTime. I am attaching a video from Adam showing Amazfish in action, upgrading the bootloader and InfiniTime, displaying a text notification and a call notification.

I'm really amazed by all the work the community achieved this month, and I look forward to seeing what we'll accomplish next month!

See the [video here](https://video.codingfield.com/videos/embed/f7bffb3d-a6a1-43c4-8f01-f4aeff4adf9e).

**A look at PineTime InfiniTime functionality**

That is all for this month. Make sure to subscribe to the blog and follow [PINE64 Telegram News channel](https://t.me/PINE64_News) as well as our [Twitter](https://twitter.com/thepine64) and [Mastodon](https://fosstodon.org/@PINE64). Until next month!
