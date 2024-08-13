---
title: "December Update: The Longest One Yet"
date: "2020-12-15"
authors: ["Lukasz Erecinski"]
categories:
  - "community"
  - "cube"
  - "news"
  - "pine64-community"
  - "pinebook-pro"
  - "pinecil"
  - "pinephone"
  - "pinetime"
tags: 
  - "community"
  - "pine64"
  - "pinebook-pro"
  - "pinecil"
  - "pinephone"
  - "pinetime"
cover: 
  image: "DecemberHeader.jpg"
images:
  - "/blog/images/DecemberHeader.jpg"
---

![](/blog/images/DecemberHeader.jpg)

Welcome to the last community update of the year. I want to start this month’s update by thanking everyone who helped us make this challenging year a fruitful and successful one. A special thanks goes to the core community team - our mods and admins - who keep the cogs spinning on a daily basis. Marek ([gamiee](https://twitter.com/gamelaster)) and Matthew ([fire219](https://twitter.com/fire219_SIMPL)) have done an incredible job this year reworking our community-facing infrastructure; this is something which was long overdue and is now appreciated by tens of thousands of end-users. I also want to thank our partner projects - _[UBports](https://ubports.com/), [postmarketOS](https://postmarketos.org/), [Manjaro](https://manjaro.org/)_ and [_KDE Community_](https://kde.org/) in particular - for working with us tirelessly to make the PinePhone, PineTab and Pinebook Pro a success. We literally couldn’t have done it without you. Special thanks also goes out to the independent contributors whose work continuously assists partner projects in building OSes for our platforms. Finally, I want to say thank you to the Pine64 community at large. We deeply appreciate you all for being the end-users who make this project thrive. 

I would be remiss not to acknowledge and thank the members of Pine Store’s logistics, sales and shipping teams who delivered tens of thousands of PinePhones and Pinebook Pros throughout 2020; this was no small feat I assure you.

You can watch a synopsis of this month’s community update on Youtube (embedded below) but also on [LBRY](https://lbry.tv/@PINE64:a) and [Peertube](https://tilvids.com/accounts/pine64tilvids/video-channels). To stay up-to-date with PINE64 news make sure to subscribe to this blog (footer at the bottom of the webpage), follow [PINE64 Telegram News channel](https://t.me/PINE64_News) as well as our [Twitter](https://twitter.com/thepine64) and [Mastodon](https://fosstodon.org/@PINE64).

I’d like to acknowledge [JF](https://twitter.com/codingfield), [Marek](https://twitter.com/gamelaster) (gamiee), [Alex](https://twitter.com/AlexRob12252696) (clover) and [PizzaLovingNerd](https://www.youtube.com/channel/UCmGcm7dhEjS9CIOsOOv8y6w) for their contributions to this community update. Thank you.

From all of us at PINE64, a very **Merry Christmas and a Happy New Year to you all!** 

{{< youtube id="ULs5gOiLrfY" >}}

**Video synopsis of the Community Update by [PizzaLovingNerd](https://www.youtube.com/channel/UCmGcm7dhEjS9CIOsOOv8y6w)**

**TL;DR for this month's update**

- RK3566 boards available to developers next month; more info in January
- Community page (.org) getting a make-over & chat bridge will be worked on over the holidays.  
- An apology to early KDE CE pre-orders who received refunds and an explanation of what happened
- A word about retail stores coming early next year
- Look back at 2020 - our shortcomings and accomplishments discussed
- PineTime - classy analogue watch faces available for InfiniTime
- PineTime - InfiniTime receives many fixes including wake-up time, battery readout and call notifications
- PineTime - new WaspOS version has been released 
- PineTime - Amazefish companion app now runs on multiple distros, including KDE Plasma Mobile; you can now sync your PineTime to the PinePhone running Manjaro KDE & more! 
- Pinebook Pro - production resumes after Chinese New Year, late February/ early March 2021 
- Pinebook Pro - is now supported by official Debian Installer (Alpha 3) 
- Pinebook Pro - the Docking Deck receives a warm response from end-users and reviewers 
- PinePhone - software and firmware news: Megi’s 5.10 kernel and new firmware for the modem result in improved power management + thermals
- PinePhone - Megapixels camera app now supports smooth 30FPS viewfinder; works on multiple mobile UIs. 
- PinePhone - We signed a contract for a PSION5-like keyboard with a specialized vendor(!); developers will receive keyboards already in January 2021
- PinePhone - Qi charging back case entered production (molding process) 
- PinePhone - We’re working on a fingerprint reader back case with a community member who created a working prototype
- PinePhone - showcase of awesome PinePhone hacks and DIY projects
- PinePower - a range of power supplies (PSUs) for PINE64 products coming soon 
- PinePower - portable 65W GaN PSU due in late Jan/ early Feb and a 120W desktop PSU coming later in 2021
- PineCube - we now have Armbian support (Debian & Ubuntu) for the PineCube
- PineCube - we created a case for the PineCube and released STL files for it
- Pinecil - initial batch sold out incredibly fast, more units are being produced for January 2021
- Nutcracker Challenge - more evaluation boards shipped 
- Nutcracker Challenge - we’re getting more source code soon & early community developed flashing tools now available 

##### Housekeeping

Just before finishing up this community update I received word that our next generation of RK3566-based single board computers will be available to developers next month. In case you’ve missed it, I wrote about our future strategy and non-Pro devices in [last month’s update](https://www.pine64.org/2020/11/15/november-update-kde-pinephone-ce-and-a-peek-into-the-future/). You can expect more information about these boards to follow in the January community update. 

Work will be carried out to the pine64.org community webpage over the coming holidays. This shouldn’t have an impact on the website's functioning, but we will likely have to disable blog comments at some point in the next two weeks. Blog comments will be reenabled once the new site goes live. I am looking forward to hearing your feedback in January when the new page design is revealed. 

![](/blog/images/OldComPage.jpg)

**Farewell old friend!**

In related community news, protocol chat bridge maintenance will begin soon. We will attempt to minimize chat room downtime, but a degree of disruption is unavoidable. The current bridge will need to come down and a new one will be erected in its place. In short, expect things to break. As for the time-frame, I don’t know if the process will take an hour or an entire day; regardless, on the day of maintenance a proactive outage warning will be posted on social media and the Telegram news channel.

Due to a database software error earlier this month, we had to refund people who pre-ordered the KDE Community Edition PinePhone within the first 18 hours of orders going live. The error applied incorrect shipping charges at checkout and affected orders #159750 to #159962. We sincerely apologise for this mishap - if you have been affected, please re-order your PinePhone now. This will not affect when your PinePhone KDE CE ships.

Lastly, earlier this month we announced that we’ll be launching regional online retail stores in 2021. These online stores will offer a more traditional purchasing and support experience to the Pine Store, and are aimed at people who are less familiar with PINE64 as a project and Linux communities in general. The Pine Store isn’t going away, however, and neither are the community oriented price-points. To learn more about this topic please read the [full blog entry](https://www.pine64.org/2020/12/02/pine-store-community-pricing-online-retail-stores/).  

##### 2020 Retrospective 

I’ve chosen a handful of shortcomings and accomplishments of PINE64 as a project for us to look back at. Much has happened in the past 12 months, and since I only have 2 pages allocated for this topic, I had to be rather selective. Feel free to let me know in the comments if I’ve overlooked some key shortcoming or achievement.  

This was a difficult year for everyone, and when I write ‘everyone’ I literally mean that everyone has been affected by the COVID19 virus in some way. The pandemic brought much of the world to a complete standstill - indeed the production and the supply chain in China are still reeling from the virus outbreak. Much of the present component shortages and price hikes, such as those preventing us from producing the Pinebook Pro and PineTab, can be directly linked to the January - May period, when most factories were forced to close their doors for business. Moreover, the border crossings to Hong Kong - where our most popular devices such as the PinePhone ship from - remains closed, with an expected reopening date of April, 2021. Despite these massive production and logistic challenges, the Pine Store managed to continually ship devices in 2020. Tens of thousands of phones and laptops shipped via an exceptionally difficult logistic route to reach the end-users. All this is something I wish you keep in mind as I proceed to discuss the successes and shortcomings of this year. 

Shortcomings: 

At [FOSDEM 2020](https://www.pine64.org/2020/02/03/fosdem-2020-and-hardware-announcements/) we announce a sizable number of devices to hit the Pine Store this year. While all the announced devices suffered a set-back, there was one particular one which unfortunately got axed. The HardRock64 (HR64) was meant to be small in size (B-type), have fewer I/O options and serve as a complimentary board to the RockPro64. Unfortunately, by the time we were able to start production of the HR64 the increase in component price, and introduction of competition’s hardware to the market, made the HR64 a much less interesting value proposition. Simultaneously, at this time we already began investigating future SoCs - a topic I touched upon in [last month’s update](https://www.pine64.org/2020/02/03/fosdem-2020-and-hardware-announcements/). In result, the decision was made to scrap the HR64 and create an A-type and B-type board based on future architecture of SoCs instead. These new boards will be available to developers next month - something to keep in mind while mourning the HR64. 

![](/blog/images/HRock64.jpeg)

**Picture of the unreleased HardRock64 SBC**

Despite having received a positive reception, I sadly need to list the PineTab as our second shortcoming this year. In short, the device has suffered constant delays since its inception and only saw a [limited production run](https://www.pine64.org/2020/07/24/all-about-the-pinetab-update/) this year. We are currently waiting for LCD and digitizer panels to become available to rectify this situation; hopefully a sizable batch will be produced following the Chinese New Year. We know you guys want it - more PineTabs will be available in 2021.

Third on my list of shortcomings is our failure to deliver the OG Pinebook-to-Pinebook Pro-like upgrade kit. In the end we were never able to overcome thermal management issues with the RK3399 in the plastic enclosures of the 11.6” and 14” OG Pinebooks. It also turned out that flashing the keyboard firmware, allowing the chassis to seemingly work with the Pinebook Pro mainboard, sadly isn’t a completely straight-forward process. I personally tried a number of times and never got it to work. Following these obstacles we reallocated the available time to deal with other issues we faced this year. We may come back to this topic at some point in 2021, but I can no longer promise a pro-like upgrade kit will be available for the OG Pinebook. Sorry.

![](/blog/images/PBPro-UpgradeKit1.jpg)

**Original Pinebook chassis fitted with a Pinebook Pro mainboard**

Lastly, I want to address the shipping difficulties we encountered with the Braveheart and UBPorts CE PinePhone batches. Following COVID19 lockdown and the border closure between Hong Kong and mainland China, we had to establish a very complex logistic process to ship out battery operated devices. We chose to ship the first two editions of the PinePhone at the height of the pandemic, which led to significant shipping problems, and in turn gave rise to frustration among a portion of our end-user base. I still maintain we had no way of foreseeing all the difficulties we encountered, nor could we remedy the situation once the devices shipped; that said, I wish to once again apologize to those who had a bad experience with initial PinePhone shipments. Thankfully, since postmarketOS CE we’ve perfected the logistics process and acquired a transition warehouse in Europe, which effectively resolved all our problems.

Accomplishments:

At the end of last year, I wrote that I foresee PINE64 transitioning in 2020 from a rather niche FOSS project to a more mainstream one. And indeed I think that this has happened. For one, we were invited to become [Arm's strategic ecosystem partner](https://twitter.com/thepine64/status/1296509158246756353) - a real  distinction and privilege. Our community of active participants has more-than doubled in the past 12 months. In the PinePhone chat alone we have nearly 10k participants across the different protocols. But active participation is just one measure of the project's growth, with the other important one being official software device support. The [PinePhone](https://wiki.pine64.org/wiki/PinePhone_Software_Releases) and [Pinebook Pro](https://wiki.pine64.org/wiki/Pinebook_Pro_Software_Release) \- arguably our flagship devices - are now supported by all major distributions and some notable \*BSD systems. We are also regularly approached by new projects interested in shipping their OSes on our platforms. This is obviously of major benefit to our community and all those who are considering PINE64 devices for industrial applications or personal use. This transition from a niche tinkering project to a mainstream FOSS one is undoubtedly our biggest accompaniment this year.

![](/blog/images/ArmEcosysPartner.jpg)

**We are Arm's [Ecosystem Partner](https://developer.arm.com/solutions/infrastructure/ecosystem/software-ecosystem)**

This year [we made the decision to self-host](https://www.pine64.org/2020/06/05/rockpro64-cluster-move-june-5-10/) all of our community-centred services and resources. The server move included the pine64.org community website, our IRC and Matrix chats, the PINE64 Wiki as well as the community forums. As many of you know, for this purpose we’ve built a massive RockPro64 cluster that is generously hosted at [BBXNET’s](https://www.bbxnet.sk/) server farm in the heart of Europe. Despite some teething problems, this has proven to be a major success for us and all the aforementioned services have been running problem-free for months now. Truth be told, we couldn’t be happier to dogfood our own hardware. As a side-note, to our knowledge we’re the only one’s relying on our own hardware to host the core infrastructure of the project; I trust this stands as a testimony to the work we and all our contributors do.

![](/blog/images/RockPro64-Cluster-Large.jpg)

**This website and all our community services are running on this cluster**

At the end of last year [I publicly asked](https://forum.pine64.org/showthread.php?tid=8500) about feedback regarding what you felt we did well and where we came up short in 2019. Two of the major gripes reported by our community were the Pine Store’s website (looks and functionality) and shipping options. This year we redid the Pine Store from the ground up. Not only does the new page look good, but it is also much more functional. Two of the functions that we managed to incorporate are shipping options and an Import Tax / VAT calculator. We already had some feedback regarding the store, and are actively working on getting more features ready. A store refresh was a much needed change - one which I believe most users are grateful for.  

![](/blog/images/oldstore.png)

**The old Pine Store wasn't exactly easy or pleasant to browse**

It probably will come as no surprise that the PinePhone has proven to be a huge success for us. Not only have we managed to ship an astounding number of PinePhones this year, we also had the privilege to work with and support 4 well established smartphone Linux projects. We built a community platform, from the ground-up, for developers to cooperate and share resources. We’re really proud of this. Thanks to the PinePhone efforts we now have an unrivaled cooperation framework for future devices. The PinePhone wasn’t the only success story of the year - the Pinebook Pro and other auxiliary devices (e.g., the PineCube, the Docking Deck and the Pinecil) were met with a lot of enthusiasm and widespread interest. Despite the global pandemic this year, we’ve noted a significant increase in interest in our devices by people within, and outside of, the Linux community.

![](/blog/images/2020CEs-1.jpg)

**First 3 of the 2020 Community Editions of the PinePhone**

The last accomplishment I wish to outline here isn’t really ours to boast about - the PineTime. Truth be told, the PineTime has significantly surpassed and exceeded our expectations. It is a completely autonomous project, largely informed by JF, Daniel Thompson and Lup and their community’s work, which has now gained a lot of traction and established its own sub-community. We’re very impressed by how far the PineTime has come this year, and that it is almost at the brink of being a fully functional smartwatch, now capable of pairing with Android and Linux smartphones. This is a success story that belongs solely to the community which is backing the PineTime project - hats off.  

##### PineTime (By JF)

As always, I'm thrilled to see the work done by the PineTime community! First, I would like to highlight the work done by [Electr0Lyte](https://twitter.com/SravanSenthiln1), who designed the gorgeous and [classy analog watch faces](https://zephyrlabs.github.io/Watchfaces/) based on InfiniTime and wrote documentation about them. This is proof that it's possible to design a nice and clear user interface even on low powered embedded system like the PineTime. 

![](/blog/images/PineTimeAnalogue.jpg)

Chrono watch face for the PineTime by [Electr0Lyte](https://twitter.com/SravanSenthiln1/status/1336965802449223682?s=20)

I've lately had less time to devote to the PineTime community and the InfiniTime, but fortunately this didn't prevent other developers from contributing to the project! Great pull requests are now being reviewed and merged, including ones that: reduce the wake up time, fix battery level readout, add call notification as well as a new 'paddle' game. Perhaps the most noticeable addition to InfiniTime is [this PR](https://github.com/JF002/Pinetime/pull/128) from [AirHamster](https://github.com/AirHamster), which adds Cyrillic alphabet support for notifications. This is not a complete translation of the firmware, but it's a first step for the support of multiple languages in InfiniTime.

![](/blog/images/CyrylicPineTime.jpg)

**Cyrillic alphabet / Russian language support for the PineTime by AirHamster ([original image](https://user-images.githubusercontent.com/6449804/98451305-87403180-2155-11eb-90c4-2d2c7c713ae0.jpg]))**

A [new version of Wasp-OS](https://github.com/daniel-thompson/wasp-os/releases/tag/v0.3), the micropython firmware has also seen a release in the past 30 days. This is a great release which adds cool functionalities like the heart-rate monitoring, step counting as well as notifications. Moreover, this release improves the support for over-the-air updates and adds the ability to install wasp-os from InfiniTime, which is the default firmware the PineTime ships with. I like wasp-os very much (it's very satisfying to enter the Python REPL running on the PineTime) and everyone interested in working with Micropython on embedded systems should really have a look at [the project](https://github.com/daniel-thompson/wasp-os) and its [extensive documentation](https://wasp-os.readthedocs.io/en/latest/index.html).

Now let's look at the PineTime ecosystem, and more specifically at [Amazfish](https://openrepos.net/content/piggz/amazfish). This companion app for smartwatches and fitness trackers was originally designed to run on SailfishOS. [Adam Pigg](https://github.com/piggz), the creator of Amazfish, worked hard on making the application easily portable to other Linux distros and various devices. With his help, we managed to build and run Amazfish on a x86 desktop computer (running Manjaro), the PinebookPro (running ManjaroARM) and on the Pinephone (running ManjaroArm with KDE)!

![](/blog/images/PineTimeSynced-scaled.jpg)

**PineTime running InfiniTime paired with Manjaro running KDE Plasma Mobile ([original post](https://twitter.com/codingfield/status/1337867256982859778?s=20))**

This is great news for the PineTime project and an achievement that opens up the PineTime ecosystem to a lot of Linux distribution and Linux devices such as the PinePhone.

Consider this also as a call for contributions - Amazfish really needs your help to package the application for multiple Linux OSes. Wouldn't it be nice to have Amazfish easily installable on Manjaro, PostmarketOS, UBPorts and the many other operating systems of the PinePhone?

##### Pinebook Pro

Let me get the bad news out of the way first: we’ve been unsuccessful in securing LCD panels for the Pinebook Pro. That said, we’re still actively working on finding a reliable source of  panels for both the Pinebook Pro and PineTab, however it appears that the component shortages in China are only getting worse. I don’t own a crystal ball, so I cannot predict with certainty whether or not the situation will reach a successful resolution by next month. Given the current state of affairs, we’re planning to resume production of the Pinebook Pro after the Chinese New Year in late February or early March 2021. I fully understand this information will come as a disappointment to many of those waiting to get their hands on a unit. We’re sorry, and there is very little we can do at the present time. For more details about this unforeseen extended halt in Pinebook Pro and PineTab’s production please read the [September](https://www.pine64.org/2020/09/15/september-update-let-it-sink-in/) and [October](https://www.pine64.org/2020/10/15/update-new-hacktober-gear/) community updates.  

On a positive note, we’ve seen an important software development, namely the Pinebook Pro will be [supported in the Debian Bullseye Installer](https://lists.debian.org/debian-devel-announce/2020/12/msg00001.html). This means that you’ll soon be able to install official Debian Bullseye on your Pinebook Pro (and OG Pinebook). While the Pinebook Pro already has really solid Debian support, thanks largely due to a community built [installer by Daniel Thompson](https://github.com/daniel-thompson/pinebook-pro-debian-installer), it is obviously a whole different thing to have official support directly from the Debian project. We’re looking forward to the third Alpha release of the installer. When it finally gets released make sure to give it a shot. 

![](/blog/images/DebianOnPBP-scaled.jpg)

**Debian on Pinebook Pro (image from Category5 Technology TV - [video link](https://www.youtube.com/watch?v=X3oAFQGbneU))**

Lastly, I am happy to report that the Pinebook Pro Docking Deck has received a very favorable response from the community. Early reviews have painted a very optimistic view of our USB-C dock. The Docking Dock has been long in the works, so it's a real relief to us that it has received this much praise upon its initial launch. For those of you who have experienced issues with getting the Docking Deck working with the default Manjaro OS image, please switch over to the unstable branch. This can be achieved by editing pacman-mirrors.conf and upgrading your installation: 

**_sudo nano /etc/pacman-mirrors.conf_**

Change from:

**_arm-stable_** to **_arm-unstable_**

Then run:

**_sudo pacman-mirrors -f5 && sudo pacman -Syyuu_**

You can expect Docking Deck support to be added to the stable branch of Manjaro Arm in the next major software update (to kernel 5.10). As for other OS images for the Pinebook Pro, enablement of the Docking Deck will depend largely on developers. If you are a developer and want to incorporate Docking Deck support in your Pinebook Pro OS image, then please see this [merge request by ayufan](https://gitlab.manjaro.org/manjaro-arm/packages/core/linux/-/merge_requests/1). 

{{< youtube id="uQoeCBW_bHE" >}}

**A review of the Docking Deck by [LearningLinuxTV](https://www.youtube.com/channel/UCxQKHvKbmSzGMvUrVtJYnUA)**

##### PinePhone

I’ll mostly have hardware-related topics to discuss this month, but there are a few noteworthy software and firmware subjects worth reporting on, since some of the recent developments affect the phone’s core functionality. Earlier in December, Megi released his version of [kernel 5.10](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/) for the PinePhone, which is now available for testing in a handful of OSes, noteworthily in [Manjaro Phosh](https://osdn.net/projects/manjaro-arm/storage/pinephone/) and [Manjaro KDE](https://osdn.net/projects/manjaro-arm/storage/pinephone/). The new kernel brings a number of general improvements to the modem driver, WiFi as well as USB-C dock support. Regarding the modem driver, the time to resume from deep sleep has now been significantly reduced from 1.2 seconds to 400 milliseconds. As for dock support, not only should more docks be supported now, but the power delivery via the dock itself should be more reliable. For more information please read [Megi’s news log](https://github.com/megous/linux/commit/db16c398a809ac303e7693f2f46ad20fad11d39a). 

Another piece of important software-related information concerns modem firmware. A new firmware for the Quectel EG25-G, which improves power management as well as call reliability, is now available for flashing. It significantly improves the thermal performance of the modem, reducing the operating temperature and power consumption. The new firmware also adds profiles for Sprint and Telus VoLTE and support for select German and Spanish GSM providers. Our thanks go out to [Biktor](https://github.com/Biktorgj/), who contributed to this firmware. We initially were hoping to have the KDE CE PinePhone ship with the new modem firmware, however due some issues with the automated flashing process integrated into the factory-test OS image (and a lack of time to troubleshoot what was wrong with it) all PinePhone users will have to flash their modems manually. Martijn Braam is currently looking into creating a simple and safe utility for flashing the firmware. I expect more information about this will follow shortly. 

Lastly, I want to report on the progress of the _Megapixels_, the PinePhone-specific camera application developed by and for postmarketOS, but used by many operating systems - including Mobian, Manjaro, KDE Neon, Manjaro with Lomiri and numerous others. The newest version of the application offers autofocus, manual controls for exposure and shutter, back-and-front camera switching, and now also a smooth 30FPS viewfinder. Although the application is still in beta, it shows a lot of promise and has continually exceeded everyone’s expectations. Moreover, the camera pictures have also shown a lot of improvement in recent months, and using manual controls, you now can take pretty good looking pictures. For more details please see Martijn Braam’s [Megapixels documentation](https://sr.ht/~martijnbraam/Megapixels/).  

{{< youtube id="3-GkcPYz2H0" >}}

**The viewfinder in Megapixels running at 30FPS**

Next up we have a lot of hardware topics to cover. Let me start with some good news for all of you who have been waiting for a PinePhone keyboard. After a lengthy back-and-forth and numerous design changes, we have now firmly settled on a design and signed a contract with a highly reputable and specialized keyboard vendor. Design-wise, we’ve gone a full circle and in the end decided on a PSION5-like ‘Vulcano’ key type keyboard, which will attach and interface with the PinePhone via the pogo pins. The keyboard will also feature a high-capacity (5000-6000mAh) battery. Aside from the obvious attribute of extending the device’s operating time, the battery also acts as a counter-balance for the phone when it is fitted with the keyboard and sat on a flat surface. This will be a high-quality peripheral and we expect it to be a highly desirable add-on for the PinePhone. 

![](/blog/images/photo_2020-12-15_15-19-37.jpg)

**PinePhone mounted to keyboard when open (disregard USB-C port)**

![](/blog/images/photo_2020-12-15_15-21-41.jpg)

**PinePhone with keyboard when shut**

![](/blog/images/PSION5KB-original.jpg)

**Original PSION5 keyboard for reference - the PinePhone keyboard will be very similar in form and function**

Due to the keyboard vendor’s expertise and manufacturing capabilities, we expect preview units to already be available in January. These early production units will be shipped out to developers so that the keyboard can be enabled across most if not all operating systems. Granted this enablement goes well, I think it is reasonable to expect the keyboard to be available in the Pine Store and regional stores sometime soon after the Chinese New Year (late February or early March 2021). We expect the PinePhone keyboard to cost somewhere in the $50 range in the Pine Store. 

In other hardware news, the Qi wireless charging case has now entered production. While we don’t have a price-point to announce at this time, we ought to have one by next month’s update since the back case should be available prior to Chinese New Year. The back case is 2mm thicker than the stock cover and can accommodate small add-on and accessory boards, such as for instance a LoRA module. We are still thinking of other applications apart from LoRA that could fit in the extra space offered by the case, but I’m sure end-users will find many interesting ways to make use of it. Personally, I cannot wait to see what functionality people will be able to hack into this case. 

![](/blog/images/photo_2020-11-13_13-48-44.jpg)

**The wireless coil design used in the back case**

Speaking of hacking-in functionality into the PinePhone, these past 30 days have seen some of the coolest end-user add-ons ever created for the device. There are three which I want to highlight here: a functional fingerprint reader back-case, a DIY keyboard and the [PineEye thermal camera](https://github.com/jnavarro7/pineeye_for_pinephone). Let me offer some information about the latter two first, as I have some exciting news concerning the fingerprint reader back case. The PineEye uses a custom breakout board and [PCB designed by jnavarro](https://oshpark.com/shared_projects/Z65YHSF2). The PCB hosts a Panasonic AMG8833 sensor which interfaces with the PinePhone’s pogo pins, more specifically the I2C port. The project is open and the sensor can be interacted with on most OSes by installing i2c-tools via OS specific package managers. It is my understanding that currently the add-on board does not function with Megapixels nor any other application, and could - at least in theory - be supported by a custom application, as [illustrated by Marijn Braam](https://www.youtube.com/watch?v=lFsQpd0bLTY&t=223s) earlier this year. I hope this project will expand and see more adoption. It is worth mentioning that the project is open hardware, so you can get your PineEye PCB today. 

![](/blog/images/PineEye.jpg)

**PineEye PCB attached via flex cable to pogo pins ([picture source](https://github.com/jnavarro7/pineeye_for_pinephone/blob/main/pictures/2.png))**

Similarly to the PineEye, the DIY keyboard created by [James Williams](https://www.thingiverse.com/thing:4662295) is something you could replicate on your own, granted that you have the technical mastery and tools. All you need is a 3D printer, some off-the-shelf components and a fair amount of time to complete the build. Just as the official PinePhone keyboard due early next year, the DIY keyboard by James snaps into the back of the PinePhone, replacing the default back case, and utilizes the I2C protocol on the pogo pins. The keyboard features small mechanical switches, a kickstand and a really nifty hinge design allowing the entire contraption to sit flush when closed. I really admire the effort and engineering that went into making this keyboard and wish I had the skills to replicate it on my own. To learn more about the project, please read the [original reddit thread](https://www.reddit.com/r/PINE64official/comments/jz38ne/pinephone_keyboard_i_designed/).  

![](/blog/images/Community_built_keyboard.jpg)

**DIY PinePhone keyboard ([picture source](https://www.thingiverse.com/thing:4662295))**

Last, but certainly not least, late last month we were absolutely blown away by Zachary Schroeder’s work, which resulted in a functional (!!!) [fingerprint reader back case](https://www.reddit.com/r/PINE64official/comments/jurehy/pinephone_fingerprint_scanner_update/) for the PinePhone. Soon after the original reddit post appeared I reached out to Zachary. We have since established a working-group consisting of numerous parties to help bring this design to fruition. His original design, while really cool, is not something we could help with manufacturing since the original sensor used was very expensive and large; this would result in a bulky and pricey back case. We have since managed to find a suitable replacement sensor, which not only is much more affordable but also smaller, thereby much simpler to implement. Zachary is currently in the process of enabling the new fingerprint reader and making it operational in software. It may still be a couple of months before this project reaches a production-ready status, but this will happen eventually. We’re really thankful to Zachary for wanting to work with us on this - it is a truly great and fun project. 

![](/blog/images/FingerPrintReader-prototypeproductionsensor.jpg)

**Prototype fingerprint reader back case; production sensor candidate pictured atop of the case**

##### PinePower

Early next year we’ll launch a line of PINE64 branded power supplies (PSUs). Both PSUs are based on reference designs, but we have made significant improvements to the internals so they are more performant than existing offerings. The portable version of the PinePower - the name we chose for our line of PSUs - is a 65W (total output) Gallium Nitride (GaN) design capable of delivering 5V 3A; 9V 3A; 12V 3A; 15V 3A; 20V 3.25A over two USB-C and one USB-A port. It will be able to easily simultaneously charge the Pinebook Pro, the PinePhone and PineTime at the same time. It can also be used to power the Pinecil. We currently hope to have the portable PinePower available in late January or early February 2021, with a price tag of  $24.99 in the Pine Store and $29.99 in regional retail stores. 

![](/blog/images/GaNPSU.png)

**The portable PinePower PSU will look like this**

The desktop version of the PinePower, due sometime later in 2021, will be capable of 120W total output. This PSU will feature 4x power delivery USB-A ports and a USB-C port. We will incorporate a LCD panel allowing for detailed and active monitoring of the power draw of each of the ports. We are currently debating whether we should incorporate a 10W Qi charging platform, situated on top of the Deskto PinePower’s chassis, so that the PinePhone fitted with Qi charging case or an Android phone could be placed on it. I’d really like to hear your feedback about this feature - good or bad idea, what do you think? 

I’ll have more information about the PinePower next month when the first samples roll off the factory line. 

##### PineCube

There are two pieces of PineCube information which I’d like to share with you this month. First, [Armbian](https://www.armbian.com/pinecube/) now offers a mainline (kernel 5.9) Linux build for the PineCube. There is an Ubuntu Focal and a Debian Buster version of the Armbian build for you to choose from. This is obviously great news, and we are very thankful to the Armbian project for supporting the PineCube so quickly after launch; a special thanks goes out to Moe Icenowy for making this happen. The support for the PineCube was added yesterday (from the time of writing) and I have not yet personally had an opportunity to test it. I am, however, very much interested in hearing people’s experiences with the PineCube running Armbian - if you’ve tried it, make sure to let us know your impressions in the comments section

![](/blog/images/PinecubeCase1.jpg)

**PineCube case**

Secondly, we’ve created a housing for the PineCube. We will, eventually, make it available in the Pine Store for purchase. Meanwhile, [we’ve decided to release the STL files](https://files.pine64.org/doc/PineCube/PineCube%20Case%203D.zip) for the housing so that anyone with a 3D printer can print their own. If you would like to upload it to Thingiverse, then you’ve got my blessing to do so. You are also allowed, and indeed even encouraged, to alter and improve the default design. 

##### Pinecil

The first production run of the Pinecil has sold out in under 3 days. While we knew that it would prove popular, we weren’t quite prepared for such an enthusiastic response. Mind you, this wasn’t exactly a small production run either. Taking this into account I am sure many of you will be happy to hear that the next batch is currently being manufactured, and we expect to receive the next shipment of Pinecils sometime in January. I’ll make sure to give everyone a heads up when the next shipment becomes available on [PINE64 Telegram News channel](https://t.me/PINE64_News) as well as our [Twitter](https://twitter.com/thepine64) and [Mastodon](https://fosstodon.org/@PINE64). 

![](/blog/images/pinecilinthewild.jpg)

**First Pinecils are now in the wild - photo by Mozzwald ([original source](https://twitter.com/mozzwald/status/1336065055260086275/photo/1))**

Over the past few weeks we’ve been closely monitoring [Pinecil feedback](https://www.reddit.com/r/PINE64official/comments/kcfawp/pinecil_reviewcomparison_to_ts100/) from the community. As always, we’re thankful for the input received. We’re also glad to see that the device has been met with such good reception from end-users. We’ll keep on reviewing incoming feedback, and granted that no major issues are reported, we’ll probably have a steady Pinecil production flow post Chinese New Year. 

To those who already got their Pinecils, please share your experience of the device with others. 

##### Nutcracker Challenge (by gamiee) 

Closing out this month’s community update, here is a short update on the current state of the [Nutcracker challenge](https://www.pine64.org/2020/10/28/nutcracker-challenge-blob-free-wifi-ble/) - our effort to bring a fully open source firmware Bluetooth and WiFi module to current and future PINE64 devices and single board computers. Since last month’s blog post another 19 developers have received their PineCone evaluation board (EVB), and we have seen many new contributions to the project. Bouffalo, the company behind the BL602 RISC-V BT/WiFi silicon used by the PineCone, has made a promise to us that more source code related to the WiFi and Bluetooth blobs will be released shortly. While we wait for the code, the community has started exploring other parts of the SoC. More specifically the present efforts are concentrated on exploring the flashing mechanisms and internal BootROM code. This resulted in early open-source flashing tools, written in [Python](https://github.com/stschake/bl60x-flash%20https://github.com/renzenicolai/bl602tool) and [Rust](https://github.com/spacemeowx2/blflash), being released. Moreover, we released an initial Arduino support for the BL602, with working hardware serial, GPIO, PWM and I2C peripherals - please see our [PineCone GitHub](https://github.com/pine64/ArduinoCore-bouffalo) for more details.      

Lastly, Lup Yuen - whom you may know from his excellent work on the PineTime - has been writing phenomenal articles about the PineCone. We strongly recommend you give them a read if you’re interested in the Nutcracker Challenge; the articles can be found on [Lup’s Github](https://lupyuen.github.io/articles/pinecone).

That is all for this month’s update - catch you all in 2021!
