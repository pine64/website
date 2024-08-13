---
title: "April Update: CE & FCC, Software Update and DIY Router?"
date: "2020-04-15"
authors: ["Lukasz Erecinski"]
categories:
  - "news"
  - "pine64-community"
  - "pinebook-pro"
  - "pinephone"
  - "pinetab"
  - "pinetime"
  - "rockpro64"
tags: 
  - "pinebook-pro"
  - "pinephone"
  - "pinetab"
  - "pinetime"
  - "rockpro64-2"
cover: 
  image: "header.jpg"
images:
  - "/blog/images/header_with_pinephone_and_pinebookpro.jpg"
---

![](/blog/images/header_with_pinephone_and_pinebookpro.jpg)

I hope and trust this update finds everyone well. Production in China is picking up pace and we expect to start shipping the Pinebook Pro with Manjaro and PinePhone UBports Community edition next month. I am happy to report that, for the time being, everything is proceeding  smoothly and we’re on track to ship devices in accordance with our original plans. Still, I encourage you to sign up to this blog to stay up-to-date on shipping information since anything can happen in the next 30 days. 

**Here is the TL:DR for this month’s community update:**

- ROCKPro64 cluster is up and running; IRC and Matrix will be moved over to it soon
- We’re shipping surgical masks to those in need in your local community
- PinePhone UBports edition gets CE, FCC and RED certifications
- UBports Ubuntu Touch shaping up nicely; major development milestones reached
- Other PinePhone OSes begin maturing; state of development + new phone OS
- CRUST suspend on the PinePhone; 15 hours battery now possible
- Schematics for PCBA v1.2 available after testing;  v1.2 will be available in the store for BH users eventually
- Pinebook Pro Manjaro KDE build is very polished; development report
- Docking your Pinebook Pro using USB-C; using Manjaro mainline kernel
- We’re making our own USB-C dock; better ergonomics than most OEM options
- RK3399 OG Pinebook upgrade kit testing and challenges; we’ll likely use graphene for cooling 
- PineTab delayed until pandemic over; ready for fabrication and report of improvements + tablet keyboard is ready
- The PineTime is now a smartwatch; BLE notifications support; we need a Linux + Android companion app 
- OpenWRT on ROCKPro64; what do you think about a ROCKPro64-based router?

#### Housekeeping

The PINE64 ROCKPro64 cluster has finally made it to its location at [BBXNET](https://www.bbxnet.sk/) and the process of setting it up began. For those who don’t know, in [November last year](https://www.pine64.org/2019/11/05/brave-heart-edition-pinephones/) we announced that we’ll be moving our services over to a custom 24-node ROCKPro64 cluster. At the time of writing the cluster is already up and running but not quite ready for having services moved to it just yet. The set-up process was interrupted by stricter social-distancing restrictions in the country where it is hosted, but we expect that in a week or two the process will resume. 

Once we have access to the server farm again we’ll slowly start transferring services. IRC and Matrix chats will be the first to be moved over, followed by other community-centric services such as the Wiki and forums. I’ll have more for you on this subject as it happens; in the meantime I invite you to enjoy the pictures of the cluster below.

![](/blog/images/cluster1.jpeg)

**ROCKPRo64 PINE64 cluster**

![](/blog/images/cluster2.jpeg)

**PCB detailed look**

This month we also announced that we will be contributing to COVID-19 relief efforts by donating surgical masks to where they are needed. This has been met with a phenomenal response from the community resulting in tens of thousands masks shipped. We still have some mask cartons left, so if you know of an institution in need of gear to protect their staff or dependants then make sure to contact me. The masks will be delivered in your name to a dedicated address charge free if you have been actively engaged with our community. Details can be found [here](https://forum.pine64.org/showthread.php?tid=9544). 

![](/blog/images/EUsC3VPWkAMVizc.jpeg)

**Mask boxes**

![](/blog/images/EUsC3VyXYAAQHzr.jpeg)

**Depiction of masks on the box**

Lastly, I’d like to point your attention to a [PSA](https://forum.pine64.org/showthread.php?tid=9619) I was recently compelled to release, in which I ask community members to stay away from the r/pinephone subreddit. Unlike all other community run subreddits concerning PINE64 equipment, we find this particular subreddit to be run in bad faith and potentially for malicious reasons. I’d like to take this opportunity to also shut down the notion that we’re ‘after’ this subreddit because it encourages those subscribed to sell and buy second-hand PinePhones. Your PinePhone is yours to do what as you please - keep it, sell it, throw it into a lake or make it into a dollhouse dining table, we have no say in it either way. 

#### PinePhone

As I’m sure you’re all probably already aware, the [UBports Community Edition (CE)](https://ubports.com/blog/ubports-blog-1/post/pinephone-ubports-community-edition-pre-orders-are-open-271) PinePhone is now up for pre-order with an expected shipping window of late May. We’re very excited for this first CE of the PinePhone - our cooperation with the UBports developers has been a cornerstone of the project from the very start and we’re happy to call them our friends. I won’t reiterate everything that has already been said and written about this edition in the past two weeks, and instead refer you to the [official announcement](https://www.pine64.org/2020/04/02/pinephone-ubports-community-edition-pre-orders-now-open/) on this blog. 

This CE ships with Ubuntu Touch preinstalled and addresses some of the issues identified in _Braveheart_ PinePhones. It also comes packaged in a box with custom artwork from the UBports team (I’ll keep a secret - I don’t want to spoil the surprise for you), includes UBports Yumi mascot etched on the back of the phone and includes a multilingual user manual and a charging cable. I’d like to give a huge shout-out to all those who [helped in translating](https://forum.pine64.org/showthread.php?tid=9631) the [user manua](https://wiki.pine64.org/index.php/File:USER_MANUAL_-_QUICK_START_GUIDE_EN_GER_FR_ESP_V1.3.pdf)l to their mother tongue; it never ceases to amaze me how people step-up in this community to make things happen and help us out. You guys are awesome.

Perhaps most important of all, this PinePhone edition includes CE, RED and FCC certification. Getting this certification ‘done’ has been a major undertaking and I’d like to thank all those who have helped in its completion. For those who are unaware, CE, RED and FCC the PinePhone is in compliance with regulatory requirements in all our key markets.

![](/blog/images/PinePhoneFCCCE.jpeg)

**Label with FCC and CE markings**

Development on the build that will ship with the UBports CE is coming along at a very rapid pace. Just in the past few weeks we’ve seen implementation of the proximity sensor (which activates when you’re on a call), a wake-up trigger for the screen on an incoming call, notification LED, Bluetooth integration, the vibration motor as well as audio auto-routing. The OS will also run much smoother with a newer mesa version (not in current image at time of writing), making the device feel considerably snappier. In a video I published on a whim, I also showcased the camera working on Ubuntu Touch; it is my understanding that the implementation I showcased is quite hacky, so it may not be present in the build that ships.

Currently the development is focused on improving battery life, proper camera implementation and OTA updates. I’d also like to assure everyone that OSes, including this one, will be supported by all revisions of the PinePhone - this obviously also extends to BH PinePhones. Developers are now starting to incorporate more advanced battery preservation methods, notably CRUST (suspend), into their OS images. Upcoming Ubuntu Touch and KDE Neon images will ship with CRUST, extending the PinePhone’s battery life past 15 hours with the LTE modem and BT/WiFi module on. This feature is currently in early stages of testing but it is already working very well overall; I expect you’ll start seeing OS images with CRUST suspend available in a matter of days. This is obviously an important development, as an improved battery life brings the PinePhone closer to achieving daily driver status for those who want to use it as their only smartphone. 

https://www.youtube.com/watch?v=3Ne6G0-hn9g

**A quick and crude look at Ubuntu Touch on the PinePhone**

In other software news, we’ve seen a lot of improvement to popular OS choices as well as introductions of new ones. In the past few days I have used KDE Neon, Postmarket OS and Debian with Phosh. I found all of these OSes performing exceptionally well nowadays, especially in terms of UI fluidity. Let me start with KDE; I was very impressed with both its new features as well as how it performs even when running from an SD card. The most recent KDE Neon image supports autororation, incoming and outgoing calls, auto-brightness and all key functionality of the modem. Installing most common applications, such as Telegram, was a breeze and I was pleased to see the phone responding snappily to the power button being pressed to lock the screen. Little things, such as volume keys working and a power-dialogue showing when the power button is held down, have also been implemented since I tried the image last. The latest image has a significantly improved battery life, a reduction in battery consumption of 30-35% from previous OS iterations, thanks to Sameul’s work on suspend. It is a real pleasure to see Plasma Mobile mature, and I hope and trust the PinePhone has contributed to the maturing process in no insignificant way.

The two popular OSes using Phosh as the front-end are Postmarket OS and Debian with Phosh; despite sharing a common front-end, the two systems differ somewhat in terms of bundled applications and some features and functions. Postmarket OS exposes - for a lack of a better word - more options in the settings menu and ships with a cutting-edge kernel (5.6). Debian, on the other hand, has a couple more features implemented - such as auto-brightness and the proximity sensor. Both have functional GPS, incoming/outgoing calls (with great sound quality), SMS support and well as LTE - all initiated on boot. Both also ship with Firefox alongside the default GNOME browser; Firefox works really well on both and scales nicely to the screen-size of the PinePhone. I am including a short video from an end-user, showcasing the most recent build of postmarket OS on the PinePhone. 

In terms of New releases, [NixOS is now available](https://mobile.nixos.org/news/2020-04-07-march-2020-round-up.html) for the PinePhone for those who wish to try it out. I have not yet had the chance to run it but it is my understanding that all NixOS core functionality works well out-of-the-box on the PinePhone.

![](/blog/images/phones.jpg)

**It's all about choice**

Before moving on to the next segment, I’d also like to mention that the revised schematics for the v1.2 PCBA in the UBports CE PinePhones will be available in the Wiki once the new boards pass all required tests later this month. I know a lot of _Braveheart_ owners also ask about availability of the v1.2 PCBA revision in the store - the answer to this is ‘yes’, it will eventually be available in the [spare-parts store section](https://pine64.com/product-category/pinephone-spare-parts/), but we really do not see a point in getting a newer PCBA as v1.1 will be supported forever.

#### Pinebook Pro

The Pinebook Pro production is underway and it presently looks like shipments will go out at the same time or prior to the UBports CE PinePhones. Obviously the most important fact about this upcoming production-run is the preinstalled OS. I wrote about this at length in [last month’s community update](https://www.pine64.org/2020/03/15/march-update-manjaro-on-pinebook-pro-pinephone-software/), so rather than reiterating what I already wrote I’ll offer a closer look at the state of Manjaro on the Pinebook Pro. 

The Manjaro team has been working on delivering the most polished and tailored build of KDE yet. I am now confident that this effort will result in a true daily-driver device for light-to-medium tasks. I cannot overstate the level of testing and polish that has gone into this build; it extends to custom backgrounds for the Pinebook Pro, optimised trackpad settings, additional popular applications such as KODI and the right amount of opacity for the panel and menu. On first boot you’ll also be asked to complete an OEM setup, selecting your username and password, your keyboard layout, locale and language preferences.

![Manjaro_ARM_6b](/blog/images/Manjaro_ARM_6b.jpg "Manjaro_ARM_6b")

**The Pinebook Pro Manjaro wallpaper is pretty stunning in my opinion**

I often use the Pinebook Pro for writing on-the-go and then revert to using my stationary computer at home. With the pandemic lockdown now in place, I figured that I’d try docking the laptop and seeing how it will hold up as a desktop replacement. To my surprise, even at 1440p, it worked extremely well. Apart from the obvious benefits of having a device that is mobile on the one hand and can perform the task of a low-load workstation when docked on the other, it's worth pointing out that the Pinebook Pro can be powered from a 15W power supply - while my stationary PC requires a 650W power supply. So, for light tasks, I’ll keep using my Pinebook Pro from now on, as it's better for the energy bill and the environment.

![](/blog/images/pbpdocked.jpeg)

**Pinebook Pro docked**

We are currently in the process of making a custom USB-C dock for the Pinebook Pro, which will include all of the key features we expect everyone wants while delivering better ergonomics than most existing third-party docks lack. In short, after testing a number of common OEM USB-C docks, we arrived at the conclusion that we really don’t like how they handle cable management. Our dock will have all inputs and outputs stacked on one leading edge, so that you can have it sit nicely on your desk with the cables facing in one direction. As for functionality, you can expect power-in, HDMI out, USB 3.0 as well as a Gigabit Ethernet connection. These specs are not final, so if there is something you’d very much like to see added then make sure to let me know in the comments section. 

![](/blog/images/PBP_ish.jpeg)

**Pinebook Pro-ish**

Lastly, work on the upgrade RK3399 kits for the original Pinebook is underway. We already did a fair bit of testing to determine the best way to cool the SOC in the plastic chassis. Our initial ideas to cool the RK3399 using a thin sheet of copper fell through, as the SOC ran hot and throttled quickly under moderate load. We’ve now moved onto testing using a graphene cooling system, which we believe will deliver much better thermal dissipation performance. One issue I’ve encountered insofar is with getting the keyboard firmware to play nice with the Pinebook Pro board - as a result, I expect this is likely something developers will have to get their hands on prior to end-users.

#### PineTab

I wish I had some good news for you regarding the PineTab, but we’ve made the decision not to ship the device during the pandemic. With the two major devices - the PinePhone and Pinebook Pro - already proving difficult to arrange shipments for at this point in time, taking on additional burden is something we consider unwise. At the same time I’d like to assure you that the tablet is very much still in the works and something we sell this year, hopefully as soon as COVID-19 loosens its hold on the globe.

Much of the PineTab PCBA and body-work are, in fact, already at a fabrication stage. Even the backlit keyboard has now been customised to our spec and is ready for manufacturing. Speaking of the keyboard, we’ve made a number of improvements to it and its attachment mechanism based on feedback from developers. The keyboard has a white multi-level backlight and is branded with a PINE64 logo on the SUPER key in a similar fashion to the Pinebook Pro. The magnets that hold the keyboard attached to the PineTab have been considerably beefed up, so you can even lift the tablet up with the keyboard attached without it falling off (not that I advise or recommend doing so).

![](/blog/images/keyboard.jpeg)

**New and improved PineTab keyboard - look how many magnets!**

We’ll treat this delay as an opportunity to further review existing OS images for the PineTab to determine which of the existing options would best suit an early-adopters edition. Earlier this year at FOSDEM I saw Ubuntu Touch running on the PineTab and I was very impressed at how well it performed. This was over 2 months ago and since then development has made significant strides in terms of both performance and overall functionality. Admittedly these advancements have been made on the phone, but I expect that all improvements are directly transferable to the tablet. There are, of course, other options including more traditional desktop OSes such as Manjaro to consider too.  Regardless of what we decide on in the end, the delay - while unfortunate and unplanned for - can turn out to be good for the PineTab project, as we’ll be able to ship a better performing and more polished OS on it from the very start. 

If you’re interested in the PineTab then I encourage you to subscribe to this blog. I’ll make sure to keep you updates as more information becomes available.

#### PineTime

[Last month](https://www.pine64.org/2020/03/15/march-update-manjaro-on-pinebook-pro-pinephone-software/) I reported on PineTime development in which I focused on [JF’s incredible work](https://github.com/JF002/Pinetime). We currently feel that this firmware stands the best chance of becoming the first to ship with an end-user PineTime production-run later this year or early in 2021. Since last month’s update we saw another major milestone in PineTime development, namely BLE notification support. This effectively turns the PineTime from a ‘dumb’ watch capable of syncing with an Android or Linux phone, into an actual smartwatch capable of displaying notifications on your wrist.

However, for this functionality to actually work we need a companion app for the PinePhone and Android. I’ll be reaching out to relevant people whom I know of, asking if they’d be willing to work together with JF and other PineTime developers on porting an app to mobile operating systems. But consider this a ‘call for development’ - perhaps you’re interested in taking on the challenge? If yes, please reach out to me or JF and have a chat about what you’ve got in mind.

{{< youtube id="O3l5zb_jUr4" >}}

**[JF showcases](https://twitter.com/codingfield/status/1243647528622534656) early work on notifications on the PineTime**

#### ROCKPro64 

I rarely focus on SBCs in my community updates because, well, I assume that most people who pick up a SBC know more-or-less exactly what the capabilities of a particular board are and what they want to use it for. Moreover, unlike the PinePhone, PineTime or Pinebook Pro, which are ultimately built to serve a particular purpose, SBCs are development platforms and deployed in a wide array of projects and scenarios. Covering all applications of a SBC, however interesting that may be, lies outside of the scope of community updates on the blog; that said, if someone wants to run a dedicated SBC segment on the blog then I’d be happy to accomodate this, as I think it's a great idea. You know where to find me.  

One recent project sparked my personal interest however, so I want to report on it here. Tobias (_Manawyrm_) from Manjaro managed to build [OpenWRT](https://openwrt.org/) for the ROCKPro64 and have it play nice with a PCIe GbE expansion board. The ROCKPro64 could even be used with a 10GbE card thanks to the PCIe connection. Tobias has already issued a [pull request](https://github.com/openwrt/openwrt/pull/2917/commits) for his work on the ROCKPro64, and when accepted I can see us exploring this concept further. I have already voiced my interest in making a router in the past, and with reports of the ROCKPro64 performing well in this role, I will be asking TL to brainstorm this notion further. I am thinking of a special router-oriented enclosure and a 4xGbE expansion board, as well as u.fl cutouts in the case to mount high gain antennas for the AC module. What do you think, should we explore this further? Would you be interested in building your own ROCKPro64-based router? Let me know in the comments.

![](/blog/images/EVV1ItxWkAI-NYb.jpeg)

**Photo via [Tobia's Twitter](https://twitter.com/Manawyrm/status/1249038130231066624)**
