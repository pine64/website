---
title: "October Update Follow-up"
date: "2021-10-29"
categories: 
  - "news"
  - "pinecil"
  - "pinedio"
  - "pinephone"
  - "pinephone-pro"
  - "soquartz"
tags: 
  - "pinedio"
  - "pinephone"
  - "pinephone-pro"
  - "quartz64"
  - "soquartz"
cover: 
  image: "updatefollowup-fix.jpg"
---

![](/blog/images/updatefollowup-fix.jpg)

Happy Halloween! As promised earlier this month, here is the follow-up to the [October community update](https://www.pine64.org/2021/10/15/october-update-introducing-the-pinephone-pro/). Some of the topics I’ll touch upon will be covered in more detail in November. I’ll keep this one brief. 

## Housekeeping 

PineTalk discussed the PinePhone Pro in last week's episode. At the time of writing, it is the most listened-to episode of our community-run podcast, and there is a reason for it - it is a very good episode. I encourage you to [have a listen](https://www.pine64.org/pinetalk/).  

Earlier this week we had a guest post about the creation of the [_Meet the PinePhone Pro_](https://youtu.be/wP2-6Z74W44) announcement trailer. If you’re interested in learning how the trailer was made, and which software was used during its production, then I invite you to [have a read](https://www.pine64.org/2021/10/27/how-meet-the-pinephone-pro-was-made/). 

Logistics issues in China and the USA have caused a significant increase in parcel delivery times. The USA is particularly affected by the situation. There is nothing we can do about it, but the reason I am bringing it up is due to the increase in support tickets requesting help in tracking down packages (and sporadic claims of packages being lost). All I can do is ask you for patience - it may take a long time, but in 99.9% of cases the parcel will eventually arrive at your doorstep. 

Lastly, our Discord is about to reach (or already reached) 9000 members, making it the biggest chat platform out of all protocols used by our community. I think this is quite the milestone and I am very happy to see many new faces actively engaging in discussions. I know Discord is frowned upon by some in the FOSS community, so before anyone complains - there are corresponding and bridged channels in Telegram, IRC, and Matrix available for those who wish to use a different platform. Full chat list [here](https://wiki.pine64.org/wiki/Main_Page#Chat_Platforms).  

## SOQuartz

The SOquartz module will be available for purchase in the [Pine Store](https://pine64.com/product-category/compute-and-ai-modules/) next week. I already covered the SOQuartz in-depth in the [June update](https://www.pine64.org/2021/06/15/june-update-new-hardware-and-more-on-the-way/), so I encourage you to read that blog entry for more information. For those who do not know, the SOQuartz is a module that is pin-compatible with the Raspberry Pi Compute Module 4 (CM4). It will work with existing CM4 baseboards but we’re also creating some of our own. 

We have a model-A type hostboard - primarily for the purpose of development, with all available IO exposed, but it can obviously also be deployed in different scenarios. There is also a small footprint hostboard with dual cameras, 2x USB 2.0, HDMI and GbE for embedded projects. These are just some of the hostboards we have planned for the SOQuartz, and belive me I’ve kept the best ones for future updates. We've got some really cool stuff coming that I think many of you will be thrilled to learn about. I'll return to the subject of SOQuartz hostboards in November.

![](/blog/images/photo_2021-10-29_07-56-17-2.jpg)

**small form-factor hostboard**

![](/blog/images/photo_2021-10-29_07-56-16.jpg)

**Model-A hostboard**

The module will be available in three configurations: **2GB, 4GB, and 8GB of RAM for $35, $50, and $75** respectively. These prices are for SOQuartz with onboard WiFi/BT (there will be a version without), without soldered-on eMMC (you can install one of our standard eMMC modules). We expect that the introduction of SOQuartz will be well met by our industry partners, but we also have plans to make it an interesting platform for community projects. The hostboards are only a part of the strategy to get the community interested in the SOQuartz - something to look forward to in 2022. 

## PinePhone Pro 

We have now closed the PinePhone Pro dev unit applications and will start going through purchase coupon applications next week. We have 4 times more applications than available dev units, so those of you who will not receive a coupon at this time will have to wait until the _Explorer Edition_ becomes available later this year. 

As a side note, I got hands-on time with the PinePhone Pro last week. This is the first time I had an opportunity to see the PPP running Linux - Manjaro with Plasma Mobile in this particular case. As far as impressions over a pint in a pub are concerned, I can say this with confidence: it's very fast. Despite it being an early engineering unit, I didn't encounter any apparent heat or excessive battery drain issues, so things are already looking good. Megi and other developers have been putting in a lot of work into the PinePhone Pro these past two weeks - you can follow Megi’s work [here](https://xnux.eu/log/).

https://www.youtube.com/watch?v=ZBgNAbb0rFs

**I recorded a video at the [pub with Kamil](https://twitter.com/LukaszErecinsk1/status/1451630271783112704), but you're probably better off watching a more coherent video by [Martijn Braam](https://twitter.com/braam_martijn)**

Three more things. First, a quick correction regarding what I wrote in the October update and elsewhere: the regular PinePhone protective cases will fit the PinePhone Pro. I tried the hard case - it is a tight fit but a fit nonetheless. Secondly, I ran an [AMA on /r/Linux](https://www.reddit.com/r/linux/comments/qald3w/pinephone_pro_was_announced_last_week_ama/) earlier this month, you may wish to check out some of the questions I answered. Lastly, the PinePhone Pro is now undergoing CE/ FCC certification. 

## PinePhone** **/ PinePhone Pro Keyboard

The PinePhone / PinePhone Pro keyboard has entered production. I know that there has been a lot of back-and-forth on this topic these past months - as it turns out, creating a keyboard is much harder than one would think. In fact, it is almost as hard as making a stand-alone device. I wrote extensively about some of the problems we encountered in the [September community update](https://www.pine64.org/2021/09/15/september-update-hurdles-and-successes/) if you’re keen to learn more.

![](/blog/images/ppp-kb2.png) ![](/blog/images/PPP-KB.png)

**I've used mine to take notes on the go recently, and it's been a great experience - especially when thumb-typing**

Since September there have been two additional internal revisions of the keyboard. During this time the vendor addressed mechanical and electrical concerns which were raised by the design team and developers. With the fixes in place, the final design was submitted for production. We’re confident all kinks have now been ironed out.

The currently produced batch is a pilot run of sorts and should be available in the [Pine Store](https://pine64.com/product-category/smartphone-accessories/) in November. Minutes before posting this follow-up, I was told that the first units have been delivered. The price of the keyboard will be **$49.95**.

## PineNote

Unlike the PinePhone Pro dev units, PineNote dev unit pre-orders will remain open for quite some time. Frankly speaking, PineNotes will likely remain behind a developer pre-order ‘wall’ until the e-paper display becomes enabled in Linux. I have written about the development progress, also in relation to enabling the PineNote’s e-paper display, in both [this](https://www.pine64.org/2021/10/15/october-update-introducing-the-pinephone-pro/) and [the previous month’s](https://www.pine64.org/2021/09/15/september-update-hurdles-and-successes/) community update. 

We will start going through the dev pre-order coupon requests starting next week and keep actively reviewing incoming applications on a weekly basis for the foreseeable future. We haven’t yet made the decision if units for ‘early adopters’ will also be available only via the pre-order system, but I suspect that they will. 

Software progress on the RK3566 platform is proceeding well, and I intend to discuss it at length in November. For those of you who are interested in following software progress, I suggest taking a look at the current [mainline Linux support ‘status’ matrix](https://wiki.pine64.org/wiki/Quartz64_Development) and [e-paper display reverse engineering](https://wiki.pine64.org/wiki/RK3566_EBC_Reverse-Engineering) effort status.

## Pinecil

The Pinecil remains one of the best-selling devices we have in the store. Recently, a big Youtuber made a video about the Pinecil praising it. We still have a lot of stock, but if the current sales volume continues for the next 2 days then we’re at risk of running out. I’m not sure if more Pinecil production was scheduled for this year - consider this a heads up if you want to [get one](https://pine64.com/product-category/pinecil/). 

## PineDio \[by [JF](https://twitter.com/codingfield)\] 

The PineDio range of products is composed of multiple devices and is all about LoRa: a LoRa gateway, a USB LoRa adapter, a RISC-V development kit with an embedded LoRa module, and a LoRa adapter for the PinePhone (Pro). These past few weeks, [Lup](https://twitter.com/MisterTechBlog) and I worked on writing software and firmware for these devices - all of which are based on the Semtech SX1262 LoRa module. Lup has already managed to connect the [STACK to a LoRaWAN gateway](https://lupyuen.github.io/articles/lorawan2) running [ChirpStack](https://www.chirpstack.io/), and even to [The Things Network](https://lupyuen.github.io/articles/ttn) ([TTN](https://www.thethingsnetwork.org/) is a public LoRaWAN network).

![](/blog/images/lora-raw-setup.jpg)

**Raw LoRa data received/ sent using PineDio USB dongle (on Pinebook Pro!)**

![](/blog/images/usb-pinedio2-768x1024.jpg)

**LoRa SX1262 Linux driver for the USB PineDio adapter - via [Lup](https://lupyuen.github.io/articles/usb?29#whats-next)**

Meanwhile, I spent time trying to understand the low-level layer of the LoRa protocol by implementing "raw" LoRa communication between multiple devices (the USB adapter, the STACK, and other LoRa modules). I ran into some issues, but finally, thanks to Lup,  communication between the devices was successfully established. I can't wait to continue these experiments with the platform, and eventually build actual applications based on LoRa and the PineDio devices!
