---
title: "October Update: PineTime, Delays and Shipping News"
date: "2019-10-05"
categories: 
  - "pinebook-pro"
  - "pinephone"
  - "pinetime"
tags: 
  - "pinebook-pro"
  - "pinephone"
  - "pinetime"
cover: 
  image: "PMOS-main1.jpeg"
---

![](/blog/images/PMOS-main1.jpeg)

This month’s update will be slightly shorter than usual - I have been dealing with some health issues recently, which significantly reduced my time to actively engage with the community. Hopefully I’ll make it up to you in November. 

September has been a bitter-sweet month for us. On the one hand, we’ve seen a lot of great developments: the first Pinebook Pros have reached their owners, and the reception has so far been great; core developers have started receiving their PinePhone prototype handsets and dev pre-order coupons have started going out; and we’ve announced the PineTime smartwatch - a companion for the PinePhone and other Linux phones. 

On the other hand, (and I have no intention of sugar-coating the situation) things haven’t gone exactly according to plan regarding shipments of developers’ PinePhones and Pinebook Pros for end-users. A series of miscommunications, factory errors as well as just good ‘ol bad luck resulted in dates slipping by a few weeks. To those of you who had to wait for your units and to those whom are still waiting - we apologize for the delay, we’re very sorry. Read on to find out what happened. 

**\[EDIT 18/10/2019\] Since writing this blog entry I provided an update on the situation (Pinebook Pro, PinePhone and PineTime dev kits shipping) on the forum. [Click here](https://forum.pine64.org/showthread.php?tid=8085).**

**Bullet Points:**

- Pinebook Pro first batch shipping delay causes explained ; we’re sorry
- Future shipments 2 weeks delay ; we won’t put shipping staff at risk
- Pinebook Pro early adopter feedback very positive ; issues noted and worked on
- PinePhone Dev edition delay explained ; prototypes run great
- The PineTime ; a side-project with a lot of potential ; community driven
- Closing thoughts - are we being stretched thin? 

##### Pinebook Pro shipping delay detailed explanation

Let me give you a run-down of the events that caused the delay in the shipment of Pinebook Pros to customers. The delay was caused by a series of intertwined events, so it's just appropriate that I list them in chronological order. The first issue we encountered during production was that the Pinebook Pro doesn’t power on with the battery disconnected. This isn’t an issue that will affect the majority of users, but it had to be addressed nonetheless. Finding and implementing a solution (a bypass cable - please see the [engineering notice](http://files.pine64.org/doc/PinebookPro/PinebookPro_Engineering_Notice.pdf)) set us back a few days.  

However, the majority of time was lost on the second issue. To understand the problem you first need a little technical background; the RK3399, which is the SOC used in the Pinebook Pro, has a hardwired boot sequence that prioritizes eMMC over SD. This means that, unless the bootloader on the eMMC is altered to seek out bootable SD or USB 2.0/3.0 flash (such as uboot on the Debian + MATE build), the OS residing on eMMC will always boot prior to bootable micro SD or USB 2.0/3.0 flash.

Now here is the problem - the factory we work with is accustomed to carrying out hardware and QC test using a custom Android build. They always flash this build to eMMC modules before completely assembling the devices. This Android build doesn’t have the necessary uboot alterations to prioritize SD or USB bootable storage; as a result, we found ourselves in a position where all the fully assembled Pinebook Pros were running factory Android and there was literally no way to reflash them with Linux without disassembling all the laptops and reflashing them manually. Moreover, the factory uses a proprietary Rockchip utility to install the Android image and is completely unaccustomed to flashing ‘normal’ DD images. Needless to say, solving all problems related to this situation took a very, very long time - over a week in total. 

For those interested, I am including our solution to the problem that will be used in future batches. Our offices in China will deliver pre-flashed Debian MATE eMMC modules (since the build features uboot that prioritises SD and USB storage over eMMC) to the factory, and the factory will carry out its tests on the custom Android running from SD. This effectively means that we’ve taken on a part of the production process, which is a burden to our staff but the simplest way to resolve this issue. 

The third, and last, technical issue was first found after all units were assembled and moved out of the factory. Someone from the shipping team realised that the laptop emits an annoyingly high pitched noise when charging. This did not affect the operation of the Pinebook Pro, but we were certain that users would be displeased with this imperfection. So, the laptops were brought back to the factory over the weekend and the tiny component making the noise was removed and replaced. The reason for this issue being caught this late is quite simple - the high pitched noise isn’t loud enough to be heard on a factory floor with all sorts of machinery operating. It’s only noticeable at ambient noise levels; e.g. at home with the TV off.  

At this point in time we missed our shipping date by weeks, but it was now September 27 and geopolitical events - which I will not discuss or debate here - caused further setbacks. The Pinebook Pros are produced in Shenzhen, mainland China, but ship out from Hong Kong via DHL. This means that our shipping staff needs to make the trip to the Hong Kong storage bay where the Pinebook Pros get picked up for delivery. If you follow global news, then in all likelihood you’re aware that the situation in the region is volatile at the moment. As a result of the situation in China and Hong Kong, only half of the original first production run shipped out. The remaining portion of the first batch will be shipped in the next couple of days, after the week-long national holiday comes to an end, and (hopefully) things calm down slightly. 

Before I wrap this section up let me assure you that we **will not expose our shipping staff to situations where their life or wellbeing could be jeopardised**. I hope this decision is self-evident, and that we can all agree this it is the only sensible course of action. This also means that if the situation in the region will remain unstable, then future shipping dates may slip too. 

##### Future Pinebook Pro shipments, early reception and feedback

The current delay in delivering early Pinebook Pros has pushed our dispatch dates for the second (community) and third (public) batch slightly forward. Granted that production and shipping processes are not impacted by the unrest in the region, we will be shipping these two batches collectively at the end of October or in early November. With most issues ironed out during the production of the first batch, I trust it should be relatively smooth sailing from this point on. Famous last words, I know. Based on feedback from early adapters, it seems that there are no glaring or core experience hampering issues we need to address at this point in time, and the minor things users have found should all be fixed swiftly. As always, I’ll keep you posted on how things progress on the forums and chats, as well as on Twitter and Mastodon. 

Right now we are aiming to open up the next round of pre-orders on the day that the second and third batch ship out to end-users. I can currently only offer a guess as to when this will be - likely sometime between October 25 and November 4. 

Before wrapping this section up, let me discuss end-user reception and feedback. I am happy to say that Pinebook Pro reception has been overwhelmingly positive. There is an entire thread dedicated to [people’s early impressions of the Pinebook Pro](https://forum.pine64.org/showthread.php?tid=8024), which I encourage all of you to read - especially if you’re on the fence if you want one for yourself. Let me add that I am impressed with the quality of the feedback thus far - it has been on-point and constructive. I am actively monitoring the information flooding in on the forums and chats, and from what I’ve gathered the grand majority of users are impressed with the hardware and happy with the default software. This is obviously a huge relief to us. A number of people have already posted pictures and youtube videos of their Pinebook Pro running and showcasing its various features, so I am posting them below for all of you to check out. 

![](/blog/images/pbp_booted.jpeg) ![](/blog/images/PBP2.jpg)

**User submitted pictures (by Mrfixit2001 & kunger)**

https://www.youtube.com/watch?v=Sm4DEGP-qIE

**Quick unboxing video**

That said, there appear to be some minor problems with additional hardware and the keyboard firmware. Let's start with hardware: reports indicated that the optional PCIe-NVMe adapter can push the trackpad up-and-out of the chassis if a NVMe SSD is too thick or the adapter is installed incorrectly. It will take us some time to replicate this and figure out what can be done; I don’t have a solution for this from the top of my head. My guess is that it is caused by the thickness of particular NVMe drives, in which case we’ll have to compile a list of drives that fit inside the Pinebook Pro chassis. We’ll try things out on our end and let you know. Onto trackpad/keyboard firmware: we’re aware that under particular circumstances the trackpad/keyboard firmware can misbehave causing delayed input. From my testing, it seems to be a relatively rare occurrence, but when it happens it is indeed quite annoying. Thankfully, we have the source code for the utility used to alter and patch the keyboard firmware - it was open sourced to us by the keyboard vendor. We’re in the process of building and testing this utility on ARM. Rest assured that this is an issue that we’ll solve in the future, and it should be a relatively painless process for end-users to get the firmware patched. The utility has a simple GUI, all you need to do is press ‘START’ and wait for the software to run its course installing the keyboard/ trackpad firmware binary.

##### PinePhone prototypes and developer pre-orders

Last month we opened PinePhone pre-orders for developers intention to have them shipped by now. However, right before assembling complete prototypes we received word from partner-project developers who already had core PinePhone components, that the digitizer has issues with registering swipe-motions. Based on this information we were forced to hold off on starting production and turned to another vendor for a suitable digitizer replacement for the PinePhone. Sadly, the time it took to deliver and test the new part was long enough that we were unable to complete prototype production before the current Chinese National week-long holiday, which is ending on Monday October 8th. This is another case of bad luck we ran into last month. Despite the unfortunate delay in assembling the phones, we are happy that this flaw was found prior to the devices being shipped out.

But it is hardly all doom and gloom. We’ve tested the hardware last week and are now positive that the new digitizers work well. This means that the PinePhones for developers can be built once the aforementioned holiday finishes next week. The pre-order coupons for approved developers have now started going out and will keep on being dispatched until the end of next week, and possibly even further into the future. I’ve seen numerous reports that people have gotten their coupons already. Some of you who follow us on social media may have also already seen that a handful of key developers, whom we’ve been working with since the very start of the project, have gotten their prototypes ahead of the holidays. In fact, Martijn from PostmarketOS even built his unit on camera for all of you to enjoy. Check out the video below.

https://www.youtube.com/watch?v=VyeD1sfQNoM&t=1s

**Building a PinePhone Prototype and running PostmarketOS**

The initial feedback from those who got their hands on the PinePhone prototypes has been great. Marius from UBPorts shared a video showing that the prototype with the new digitizer not only looks great but also runs Ubuntu Touch very well. It’s noteworthy that both PostmarketOS shown in Martijn’s video, and Ubuntu Touch in Marius’ video run the open-source Lima driver. This means that UI performance will only improve with time as the Lima driver gets polished and improved upon. From the videos circulating online you can also see that most of the core features now work flawlessly on many available OSs. Even browsing the web and watching youtube already works very well on most systems; I recently tested a recent build of LuneOS, and I was completely blown away by how much of the core functionality is already in a mature state. The prototype isn’t completely problem-free however, and the remaining bits and bobs will need to be addressed before production of the Brave Heart editions starts in late October. I’ll keep you posted.  

{{< youtube id="RIkQXnLnxD0" >}}

**Ubuntu Touch running smooth on the PinePhone**

![](/blog/images/pinephoneut2.jpeg) ![](/blog/images/pinephoneUT.jpeg)

**Ubuntu Touch on the PinePhone**

##### The PineTime 

Finally some truly good news - the PineTime. I’ll immodestly take the credit for the start of this project, since I pushed for us to explore the potential for creating a FOSS smartwatch for some time now. After initial talks, we quickly agreed that the PineTime should be a side-project (like the CUBE FOSS camera), completely community driven and positioned as a complementary device to the PinePhone. Therefore, rather than looking into creating a complex device (which would be cool too! - it’s something we may look into in the future), we opted to make a simple and inexpensive smartwatch based on a FOSS friendly SOC. To this end, we quickly determined that the core functionality of the watch should be similar to that of the Pebble, but with some modern functionality, such as a colour LCD touch screen and a heart rate monitor. 

Early on in the planning process we also decided on using a square watch chassis for the PineTime. We had a choice of a few form factors, including a round-one, but decided to proceed with an unassuming and simple design. The main reason for the choice of square chassis, however, is not the looks but rather ease of development. Simply put, it's easier to develop an OS using a square display. It was a safer choice from a development standpoint, especially when taking into account that entire OSs need to be built, or ported to, the PineTime watch. Apart from the display and SOC choices, we also had a few other criteria in mind: the watch had to have multi-day battery (a week at minimum), feature a touch panel, be waterproof and lightweight. We have started writing up the [Wiki for the PineTime](https://wiki.pine64.org/index.php/PineTime), so if you want to learn more technical details of the watch you know where to find them. I’m including some prototype pictures below. 

![](/blog/images/PineTime_on_wrist_Photo.jpg)

**Prototype on wrist**

![](/blog/images/PineTime_Devkit-4.jpg)

**Development kit**

![](/blog/images/PineTime_Charging_Cradle_Photo.jpg)

**Charging dock**

![](/blog/images/PineTime_Devkit-1.jpg)

**Internals exposed**

The core idea behind the PineTime is to have a simple and open-source watch that connects to your Linux smartphone. It will push notifications from your phone to your wrist, inform you of incoming calls, help you keep track of your activity, but it won’t attempt to replace your smartphone. Not to mention that it will not need to be recharged every day - we currently aim at a 10 day battery life. I trust that many of you feel that this is the correct approach to creating a wearable device, and I hope that developers will offer an interesting range of systems and front-ends to run on it. We have now assigned all dev kits to developers who contacted us and will start production of the kits this month. We cannot wait to see what people and the community will be able to do with the little device. 

There is one last bit worth touching upon in relation to the PineTime. A smartwatch of this type requires a companion app on the smartphone. This effectively means that PineTime developers will have to work together with - or at the very least get help from - Linux-on-Phone developers to bring apps to the different OS platforms. Then there is the question of creating a companion app for Android phones, since I am sure many users relying on open variants of Android will be interested in the PineTime too. As I’ve already mentioned, this is a project which we’ll leave with the community - it will be ready when it's ready, be it in 3 or 6 months, or even a year. On our end, we’re ready to start production of the watch as early as January 2020. 

As for pricing, we are presently aiming for a price point of approx. $20. The price includes the watch and a charging dock. We decided on selling the 20mm watch-straps separately, since most people have their own preferences of style, and hope to carry a wide selection at launch. These straps will vary in price, starting at approx $3 for regular silicone sports straps. You can obviously pick up any standard 20mm watch straps on your own, they will most likely fit the PineTime. 

##### Closing thoughts

We’ve heard community members as well as podcast hosts express a concern that ‘we’re stretching ourselves thin’ with respect to all the projects that we have in the pipeline. This is not completely accurate, please let me explain. We’re not stretched thin from a production, manufacturing or financial standpoint. The Pinebook Pro, the PinePhone and the PineTime are all produced by different factories and the work on these devices is carried out by separate engineering teams. Hence, it is not true that a delay in the shipping of one device will necessitate the delay of another device; to use the events of last month as an example, the delay in Pinebook Pro production and shipment last month had nothing to do with the delay in shipping out PinePhones to developers. As I have outlined in earlier sections of this community update, these situations were purely an unfortunate coincidence. 

That said, we - the people end-users and factory representatives have contact with on a daily basis, as well as the people behind logistics - are indeed stretched thin due to the workload brought about by manufacturing delays. I think I have some 30 emails still sitting unanswered in my mailbox, not because I didn’t want to answer them but rather because I’ve been busy doing other things that are more urgent. When everything runs smoothly, productiontion and shipments are timely, the number of devices produced doesn’t impact our workload. Its first when things go South that we get overwhelmed. With Murphy’s law in full effect last month, we did ‘get stretched thin’ because we had to deal with multiple issues at the same time. 

We’ve now placed some of the secondary projects on temporary hold - at least until we ship the PinePhone Brave Heart and October Pinebook Pro batches. This clears out a little bit of space for us to deal with any unforeseen events related to these projects. At the same time, don’t worry, we’ve got a lot of cool stuff coming in early 2020 - including the PineTab.   

That wraps it up for this month. Thanks to all of you guys who are there cheering us on, it really makes a difference.
