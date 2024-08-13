---
title: "November Update: Brave Heart, Pinebook Pro reception and more"
date: "2019-11-05"
authors: ["Lukasz Erecinski"]
categories:
  - "community"
  - "news"
  - "pinebook-pro"
  - "pinephone"
  - "pinetab"
  - "pinetime"
  - "rockpro64"
tags: 
  - "rockpro64"
  - "cluster"
  - "pinebook-pro"
  - "pinephone"
  - "pinetime"
cover: 
  image: "Brave-Heart.png"
images:
  - "/blog/images/Brave-Heart.png"
---

![](/blog/images/Brave-Heart.png)

Our core focus for the past month was on getting the manufacturing process and shipping of the Pinebook Pro, PinePhone and PineTime development kits back on track. I will not reiterate the events that led to the delays of those devices in this post, but if you’re interested then read the detailed account of what happened in [last month’s community update](https://www.pine64.org/2019/10/05/october-update-pinetime-delays-and-shipping-news/). 

With the Pinebook Pros and PineTime development kits now shipped, and with the PinePhone developer edition now shipping, I feel that we’ve done a good job in handling the situation. 

The big news for this month is that we will start taking pre-orders for the PinePhone _Brave Heart_ edition on November 15 and that the next Pinebook Pro production-run pre-orders, offering a choice of ANSI or ISO keyboard, starts today. Let's get to it.

\[update 19/11/2019\] I have now posted a follow-up to this community update on the forum; mostly containing information about the PineTime dev kits and PineTab availability based on your feedback. It can be read [**here**](https://forum.pine64.org/showthread.php?tid=8365). 

**Here’s the TL;DR:**

- Our monster clusters; core community services will migrate to our own hardware in 2020
- Pinebook Pros shipped; Last pre-orders for ~3 months start today (ANSI +ISO)
- We’re aware of NVMe adapter & Trackpad issues, expect fixes soon
- OG Pinebook upgrade to Pro-esque setup in Q1 2020
- PinePhones for developers (finally) ship November 5-18th
- PinePhone Brave Heart Pre-Orders start November 15th; delivery December 2019 / January 2020
- PineTab production conundrum; state of software 
- PineTime dev kits shipped; development proceeding exceptionally well

#### Housekeeping

Earlier this year we announced that we’ve built two monster ROCKPro64 clusters with the intention to host our website, Wiki, forums, CDN, Matrix instance, IRC, etc., as well as provide the community with an efficient OS images build server. We’ve have since been looking for a reliable host that would meet our criteria in terms of support, bandwidth, services and access that could house the server. Thanks to Gamiee - a community member, contributor and moderator - we were able to get in touch with [BBXNET](https://www.bbxnet.sk/), who agreed the host the cluster for us at their datacenter and provide us with exactly the service we were looking for. 

BBXNET are located in central Europe, Slovakia, and offer a wide range of services including Internet and Television to their customer base. I feel compelled to let you know that they are helping us out of their own accord for no financial gain, a rare type of generosity, and in exchange for their help we’ll host a banner with their company logo on the website. It is the least we can do. 

As the setup process gets underway, Gamiee (who has a high degree of access to the server farm) will be taking pictures of the installation process. These pictures will be featured in future community updates. The transition of services to the cluster will be gradual, as we do not intend to compromise stability of our community services. I expect that Matrix and CDN will already be operating on the cluster in early 2020. If you live in Slovakia and in BBXNET’s service region, be sure to consider them when choosing your next ISP. 

![RockPro64-Cluster-Large](/blog/images/RockPro64-Cluster-Large.jpg "RockPro64-Cluster-Large")

**48x ROCKPro64 cluster**

**\[edit 8/11/2019\]** It turns out that the smaller of the two clusters, featuring 24x ROCKPro64 will be installed at BBXNET. I apologize for the confusion. I am including a picture of the smaller cluster below. Gamiee has already [tweeted a picture](https://twitter.com/gamelaster/status/1192551455334576128) of the server case and will be rebuilding and installing it at the final destination this month. More information to follow.

![](/blog/images/smaller-cluster.jpeg)

**24x ROCKPro64 cluster**

#### Pinebook Pro 

Thanks to the amazing efforts of the factory and shipping teams, the Pinebook Pros from both community production-runs and a large portion of the ‘public batch’ have now shipped. I expect that the majority of the ‘public batch’ will be at some stage of delivery processing from Hong Kong by the time this post goes live, or shortly thereafter. In short, if you haven’t gotten your Pinebook Pro yet, don’t worry, you should be receiving your shipping notification soon. 

As things currently stand, we are approximately two weeks behind the original shipping schedule for the remainder of the public batch. This means we’ve got just enough time to launch one more round of pre-orders for another large production-run before the Chinese New Year. Unlike the first batches (which have already shipped), this production-run will feature the much-requested choice of ANSI (US) or ISO (UK) keyboards. So if you have been holding out on buying a Pinebook Pro because you wanted to get an ANSI keyboard version, now is you chance.

It is important to emphasize that this will be the last production-run until after the Chinese New Year (which comes to an end in February 2020). During the holiday, production ceases completely at Chinese factories, and there are often production challenges immediately after people return to work after CNY. Here is what you need to know: if you do not pre-order a Pinebook Pro from this next batch before CNY, you probably won’t get your hands on one until late March or early April 2020.

![PBP preorders](/blog/images/PBP-preorders.png "PBP preorders")

Let’s talk about user feedback, initial reactions and community engagement. Reported and known issues aside (I’ll get to that), the reception of the laptop has been very good and it appears that we have delivered on our promises in the eyes of end-users. I've now seen a number of Youtube videos and it appears that they echo the positive sentiments [end-users share on the forum](https://forum.pine64.org/showthread.php?tid=8024) and elsewhere. DASGeek even ran a live unboxing of the Pinebook Pro stream the other night, which I feature below. We’ve felt good about the physical build quality and software maturity of the Pinebook Pro from the very start, but it is a relief to get an affirmation from the community.  Speaking of the community, we’re also very glad to see a high degree of engagement from people who continually contribute to testing, identifying and debugging software issues. Your efforts are much appreciated!

https://www.youtube.com/watch?v=b-XikeQDKOw&t=1s

**DASGeek live unboxing and Pinebook Pro showcase**

For those of you looking to have more choice of operating systems, you’re in luck as many partner-project OS developers are now starting to receive their Pinebook Pros. It will obviously take them some time to bring support to the platform - this doesn’t just happen overnight - but I am happy to say that we expect to see Manjaro, Kali Linux, Q4OS (Debian), Fedora, KDE Neon as well as (hopefully) Ubuntu MATE OS images on the Pinebook Pro in the foreseeable future. The same is true for \*BSD OS images, but I have a much less knowledge regarding the \*BSD communities and their development cycles, so I cannot comment on a prospective roadmap. Regardless of how things pan out for the individual projects, I expect there to be considerably more OS choices available in January of 2020. 

As a teaser I attach an image of Manjaro running mainline kernel and Panfrost FOSS GPU drivers on the Pinebook Pro - pretty cool huh?

![](/blog/images/mainline.jpeg)

**Picture from Manjaro devs (thanks for sharing!)**

Last but not least, we are aware of the problems with the NVMe adapter and trackpad issues - both of which I discussed in last month’s update. 

Let me start with the trackpad: we’re working closely with the vendor to resolve this as soon as possible and we’ve already successfully compiled the [keyboard firmware utility](https://github.com/ayufan-rock64/pinebook-pro-keyboard-updater) from source and applied the correct license (huge shout-out to Ayufan for offering help getting this code functional in record time). The underlying issue itself has now been identified and a firmware patch is incoming soon. As soon as the trackpad issue is resolved the updater will be compiled into a binary and bundled with the necessary firmware; all that will be needed to apply the fix is hitting a big ‘START’ button and restarting the Pinebook Pro.

As for the NVMe adapter it looks like we got it wrong twice (whoops, sorry! Let's hope the third time's the charm). We’ll make it right, so don’t worry; the engineering team needs to sit down and do a bit of thinking as to how this can be best addressed in the shortest time-span and in the most efficient way. I’ll make sure to get back to you when I hear something from people in the know. We really appreciate your patience. 

There is one more thing I’d like to mention before heading on to the next section. When we first announced the Pinebook Pro we made a commitment to those of you with the original Pinebook (featuring the Allwinner A64) that it will be possible to upgrade existing Pinebooks to Pro-esque versions. We have since struggled with two engineering issues to make this a reality, the most important of which is heat-dissipation of the RK3399 in a plastic shell. It now looks like we’ve cracked this issue by using heat dissipating metal foil and a thermal pad. Provided that this solution holds up under testing, you can expect the upgrade kit in Q1 2020. We hope that by providing this kit we not only cater to our community but also do our part in reducing the number of OG Pinebooks ending up in landfills.   

#### PinePhone

The road to deliver the PinePhone has been a bumpy one for us in the recent months. If you haven’t done so yet, I encourage you to read [last month’s update,](https://www.pine64.org/2019/10/05/october-update-pinetime-delays-and-shipping-news/) in which I explain some of the difficulties we encountered in the process of manufacturing developer units. I usually don’t like shifting blame onto others for delays - it just feels like a cheap excuse - but frankly, the current PinePhone delay is caused solely by third parties. More specifically, it is caused by part vendors that failed to deliver the necessary components to us on time. We usually plan for these situations, and we did in this instance too, but we were stood up by more than one vendor and on more than one occasion, resulting in the production stalling each time. I am not going to go into details here, mostly because I don’t want to waste time on it, but for what it's worth - it all boils down to reliably sourcing quality digitizers. To date, we had to reschedule assembly thrice because of this.  What can I say, you live - you learn - you get over it and move forward. The good news is that we’re now moving forward and full steam ahead with a reliable supply of components. 

**Here is the PinePhone road-map for the foreseeable future:**

- Pre-release PinePhones are currently shipping and we should have them all out by November 15th. Once shipped, delivery should be between 7 and 14 days.  
- _Brave Heart_ edition PinePhone pre-orders start 8:00AM, November 15th (GMT+0).
- _Brave Heart_ edition will be delivered December 2019 / January 2020. 
- Mass production begins after Chinese New Year, likely in early March 2020. 

Let me address each of the points above, because I feel there are a few subtleties the community needs to be made aware of. The developer PinePhones will start going out this week and we expect that shipments will be concluded by November 15th. Ironically, the delay in production of  PinePhones for developers has brought about a number of key benefits to these units. For one, based on internal testing and feedback from partner-project developers with existing prototypes, we managed to address all known hardware issues as well as implement proper antenna arrays. Prior to the delay, we were planning on shipping PinePhones for developers with off-the-shelf u.FL antennas. Such antennas, while not ideal, would have served the development purposes just fine. The delay, however, granted us the additional time to properly implement the antennas into the phone’s body and tune them according to requirements for end-users. We were able to complete the tuning process of 3G, 4G, and GPS antennas . We’ve made progress tuning the 2G antenna but haven’t finalized it yet.

This effectively means that developers will be receiving a well-rounded, complete and (to our knowledge) problem-free platform to build their OS releases and applications. These units are much closer to those that end-users will be receiving this and next year. We were hoping to have developers give us one last bit of feedback on the hardware before it enters production and ends up in enthusiasts’ hands. But it is too late for that. The window for PinePhone _Brave Heart_ production is closing very fast due to the upcoming Holidays in the West and, more importantly, the Chinese New Year in January 2020 which shuts down Chinese production lines for over a month. This effectively means that if we didn’t start _Brave Heart_ edition production now, we would find ourselves in no position to deliver any PinePhones until March 2020. Suffice to say, we don’t want to do that. As a result, _Brave Heart_ circuit board assembly is already underway, the molds are pumping out PinePhone chassis and the necessary components have been sourced and are en route to the designated factories. 

![](/blog/images/WeChat-Image_20191106083317.jpg)

**\[edit 06/11/19\] Here is a picture of the infused antennas used in the _Brave Heart_ batch**

![](/blog/images/PinePhone.jpeg)

**Prototype - photo by Martjin Braam**

I don’t want to give you an impression that the _Brave Heart_ PinePhone edition is a rushed or incomplete product - that is not the case. We have carried out extensive in-house testing of prototypes and sent prototype phones to a number of key developers from partner projects. Youtube videos show these prototypes in action - you can search for them online or check out [last month’s community update](https://www.pine64.org/2019/10/05/october-update-pinetime-delays-and-shipping-news/), where I feature some of them. We have addressed all known issues with the hardware and tested software compatibility extensively, both in-house and with our partner-projects. Indeed, this is more testing than we usually do on any other hardware, including flagship devices such as the Pinebook Pro. The extensive testing carried out on the PinePhone is a result of both the complexity of the device as well as our understanding of its importance, which spans far beyond our community.

With that out of the way, I’m happy to announce that the **Brave Heart production run of PinePhones will be available for pre-order in 10 days time from the day of publishing this blog entry, on November 15, 2019 at 8:00AM (GMT+0).**

![](/blog/images/timer.png)

**Timer on [main page](https://pine64.org) counting down to pre-orders  opening**

So, what can _Brave Heart_ adopters look forward to and what should they be aware of? Let’s talk about the hardware first: the _Brave Heart_ PinePhones will, by and large, be identical to PinePhones produced in 2020 and onwards. This applies to the case molding, PCB, LCD assembly, cooling, as well as various other components making up the phones, including aesthetic ones. These are effectively considered ‘final’. That said, as I already mentioned, we will likely be further tweaking 2G antennas to improve reception of the respective bands and we reserve the right to fix any issues that may be uncovered in the hardware. We do not, however, deem it likely that any major issues will transpire or affect end-users. Still, keep in mind that this batch is called _Brave heart_ for a reason - we’re looking for those brave enough to be the first adopters of this hardware. If bravery is not in your nature, or this isn’t something you’re willing to take a risk on, then please sit this one out and wait until March 2020 to get your production unit. 

As for the software, I have nothing but good news to relay. It is my understanding that, with the exception of the front-facing ‘selfie’ camera, all core features of the phone are now functional. Developers still have a lot of software optimisation to do, including voice calls (which are a work-in-progress) and camera functionality, as well as other kernel and userspace parts. To give you a vague sense of where software is at using traditional computer terminology, which most of us can intuitively understand; you can think of the main flagship OSs as first stable ‘beta OS images’. Not everything works, bugs are to be expected, but overall things are really shaping up nicely. In a similar vein to what I wrote regarding the PinePhone _Brave Heart_ hardware - if trying out beta builds isn’t something you enjoy, then please wait until polished OS images become available in Q1 2020. I expect that this is something most users who want an early PinePhone already expect and understand, nonetheless I felt it necessary to underline this so that only those with the right mindset get one of those units. 

Finishing off this already lengthy PinePhone section, I completely forgot to mention that _Brave Heart_ schematics and other associated documents have now been made available. I am linking them below for you to view and comment on: 

- [PinePhone Brave Heart Schematic](http://files.pine64.org/doc/PinePhone/PinePhone_Schematic_v1.1_20191031.pdf)
- [PinePhone Brave Heart Changes (vs prototype units)](http://files.pine64.org/doc/PinePhone/PinePhone_BraveHeart_edition_version_1.1_change_list.pdf)
- [PinePhone Exploded Diagram of Brave Heart edition PinePhones](http://files.pine64.org/doc/PinePhone/PinePhone_Exploded_Diagram_ver_1.0.pdf)

#### PineTab

**\[edit 8/11/2019\] _Vox Populi, Vox Dei_. Looks like there is a lot of interest in an early-adopter production run of the PineTab. Subsequently we have decided to make it happen. We still need an suitable OS to emerge however; we hope that news of the production now being underway will help in making this happen.**

We’ve made no secret of the fact that the PineTab is currently taking a backseat to the Pinebook Pro and the PinePhone production schedules. That said, we constantly get asked about the PineTab status on the forum, Twitter, Mastodon and elsewhere (even by podcast hosts). Hence, I felt it necessary to provide the community with some general sense of the hardware and software development stages, as well as share our thoughts on a suitable time for starting production. Spoiler alert, we aren’t quite sure as to the latter.  

As I mentioned in last month’s community update, we are currently waiting for a suitable OS image to emerge so that we can ship the tablet with it. We also need to make a couple of minor improvements to the hardware itself - we’ve gotten feedback from partner-project developers that the keyboard pogo-pin connector needs to be strengthened and the speaker replaced with a better one. To date, no other major issues have been reported with the prototypes, and so - as I’ve already stated in the past - we can theoretically start production of the PineTab relatively soon. With the Holiday season and Chinese New Year now looming over our production schedules, we’re at the brink of making a decision on whether now is a viable time to start an early adopter production-run. The next couple of days will determine if we find this time feasible or not. I’ll make sure to update this entry when a decision on this subject is reached. 

As things stand, we have already settled on the keyboard design that we’ll use for the tablet. It is a really nice chiclet keyboard - at least as far as small form-factor keyboards go - and features sturdy illuminated keys. Similarly to the keyboard you may have seen used with prototypes, it doubles up as complete tablet cover and features a really _pu leather_ (fake leather) finish. We’re really pleased with how it turned out and I am confident in saying that most of you will like it too. 

As far as the software is concerned, we’ve got a couple of options available to us. The PineTab has benefited greatly from the amount of development that has gone into the PinePhone. But there is more than mobile OS devs in the development pool. Indeed, there are a number of original Pinebook developers and projects that have taken on the task of developing for the PineTab too. There are a handful of very promising OS images from big and small projects alike, but to my knowledge none that could be defined as ready for prime-time. Some of the OS images feature a traditional desktop environment and are, to a greater or lesser degree, tweaked ports of OS images for the original Pinebook. One such example is Manjaro with KDE - probably the most popular distro on the original Pinebook. From the phone lineage of OSs, there are already builds of Aurora, SaifishOS, Ubuntu Touch and PostmarketOS for the PineTab. I have not tested all of the aforementioned builds and so I cannot speak to their ‘completeness’. [Danct12](https://www.youtube.com/user/danct12cp/videos) from PostmarketOS has great showcases of the PineTab development progress, as well as various novelty items related to the tablet, uploaded on his youtube channel. I link some of his videos below.

What do you think, should we run an early adopters batch before the Chinese New Year? I am really eager to hear what you think, so leave a comment under this post with your thoughts on this. Thanks!

![](/blog/images/aurora.jpeg)

**Aurora on the PineTab - by Sergey Chupligin (neochapay)**

https://www.youtube.com/watch?v=ahONNYFLjK4

**OpenGL demo on the PineTab - by Danct12**

#### PineTime

Despite development being in its infancy, the PineTime is already running FOSS software. Developers working on the watch deserve a huge shoutout for making so much progress in so little time - it hasn’t even been a month since they received the development kits. There are only so many things that I can keep track of when it comes to development, especially when there are so many things that have to be actively dealt with, so I am not going to pretend I have any real insight into how far devs have gotten. That said, the development process has taken on a striking resemblance to what I’ve seen with the PinePhone, where developers from different backgrounds and walks of life work together in getting the project off the ground. It's probably corny to write this, but it's genuinely quite heartwarming to see people bundle around what is effectively a proof-of-concept idea at this time. 

Since this is a community driven side-project, we have started considering making the dev-kits available to everyone in the store. In contrast to the PinePhone, which requires expensive and sophisticated development kits, a PineTime development kit is effectively an open watch with a debugger. Therefore, producing more of such kits is relatively simple. At the time of writing, a decision has not been reached yet whether we’ll proceed with making more kits available or not. But there is no denying that there is a lot of interest in this project also from people who want to use the PineTime in novel, interesting and important ways. For instance, we’ve been contacted by researchers from a reputable institution who wish to use the PineTime in a health-related capacity rather than a smartwatch. 

I’ll make sure to let you all know how the PineTime project evolves in the coming weeks and months. In the meantime, I leave you with a picture of the PineTime running its first FOSS watchface (and OS).

![](/blog/images/PineTime.jpeg)

**The PineTime's first watchface running TinyGo - photo by** **Ayke van Laethem**

This is all for this month, thanks for reading!
