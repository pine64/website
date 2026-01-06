---
title: "March Update: Manjaro on Pinebook Pro & PinePhone Software"
date: "2020-03-15"
authors: ["Lukasz Erecinski"]
categories:
  - "digital-divide"
  - "pinebook-pro"
  - "pinephone"
  - "pinetime"
tags: 
  - "manjaro"
  - "pinebook-pro"
  - "pinephone"
  - "pinetime"
cover:
  image: "/blog/images/maincorrected.png"
images:
  - "/blog/images/maincorrected.png"
---

![](/blog/images/maincorrected.png)

COVID-19 recovery in China is underway and factory work is slowly returning back to normal. This is good news, and we hope to have a constant stream of updates for you in the coming weeks. That said, we’re taking it one step at a time, since factories are still at 20% of the normal manufacturing capacity and it's hard to predict the recovery pace. So rather than offering you my guesstimates for particular device availability, we will make announcements once all stages of production are secured for each device. Frankly speaking, this also means that announcements will likely drop suddenly; so If you haven’t done so yet, this is probably the time to subscribe to this blog and be notified when it happens. 

The big news of this community update is that Pinebook Pros are about to re-enter production and will be shipping with Manjaro KDE as the default operating system! Pre-orders for the new production run starts on Wednesday (March 18th) and shipping is planned for early May. 

**TL;DR for this month**

- Moving PINE64 services to the PINE64 cluster 
- Spare parts for the PinePhone and Pinebook Pro 
- OG Pinebook entering production for charity; closing the digital gap 
- PINE A64-LTS will be produced until 2025 
- Pinebook Pro pre-orders start March 18th; expected shipping date early May
- Manjaro KDE is the new default OS for the Pinebook Pro!
- mainline kernel 5.7 mainline Pinebook Pro support 
- Minor Pinebook Pro refinements and tweaks
- PinePhone development is steaming ahead; new OSes and features 
- PinePhone soft and hard protective cases available soon
- PineTime OSes start coming together; first glimpse at a fully fledged FOSS OS

#### Housekeeping

We’re getting ready to move PINE64 community services to our ROCKpro64 cluster. The IRC and Matrix are the first services on our list, which means disruptions to all chats are expected at some point this month. We obviously hope that the downtime will be minimal, but given the complexity of our communications setup - which spans across multiple chat protocols bridged together - we cannot rule out that things may be a bit iffy for a few days before kinks are ironed out. I’ll make sure to give everyone a few hours heads-up when we’ll commit to the move so as not to disrupt ongoing workflow in the chats without a notice. With IRC and Matrix successfully migrated over to the cluster, we’ll be looking at moving the forums and Wiki next. This, however, will likely first be happening mid-April.  

The second piece of important housekeeping information concerns the availability of spare parts for the Pinebook Pro and the PinePhone. I recognize that this has been some time coming, but unexpected events - such as social unrests in Hong Kong and the COVID-19 outbreak - have made it hard for us to stick to initial production schedules. At any rate, spare parts for the PinePhone will be available in the PINE store within two weeks time, closely followed by parts for the Pinebook Pro later this month or in early April. Spare PINE64-branded batteries for the PinePhone will also be available but only in the USA. Further information about the parts and shipping options will be announced as items appear in the PINE Store.  

We are also starting to look into resuming production of the original Pinebook. Last summer we announced that we will be [contributing to closing the digital gap](https://www.pine64.org/2019/08/19/its-time-to-start-giving-back/) by producing subsidized Pinebooks and distributing them to groups of people in need of a simple, reliable and easily repairable laptop. These Pinebooks will be subsidized from sales of the soft silicone cases for the PinePhone (more on this later). In short, 10 PinePhone transparent silicone cases sold amounts to one subsidized Pinebook produced. Once production resumes and everything returns to normal at the factories I’ll be setting up a committee and installing some democratic process allowing us to collectively decide on who should receive these Pinebooks. I’ll have more information on this topic as we get closer to production date. Noteworthily, a sizable portion of the Pinebook production-run will also be available for purchase by end-users. 

The last point on our housekeeping list is primarily aimed at our industry end-users; we’re happy to announce that the PINE A64-LTS production has been extended by 3 years. We recognize that the PINE A64-LTS is utilised in a wide variety of industrial and commercial applications, and that a sizable number of businesses rely on it to complete a job or deliver a service. We therefore commit to deliver the PINE A64-LTS until the year 2025 (**N.B.** the product page is yet to reflect this change). This date will, however, in all likelihood be extended further into the future if end-users decide to remain on the platform. 

#### Pinebook Pro

As many of you know we have developed and fostered a truly special relationship with the Manjaro team over the course of past 3 years. Their OS images for our single board computers and the original Pinebook were and remain some of the best supported software options to date. It is therefore no surprise that Manjaro builds for the Pinebook Pro have also proven to be highly popular among our community members. Manjaro currently offers a KDE, XFCE and i3 variant of their OS image for the Pinebook Pro, each of which provides a highly tailored experience. These builds feature a cutting edge Linux kernel (5.6 at the time of writing), which supports all key Pinebook Pro functionality including USB-C charging, USB-C video out and are compatible with a number of USB-C docks. Out of the three, KDE version is arguably the most end-user friendly and polished, not in the least because Plasma makes use of the Panfrost open source GPU driver for desktop and application acceleration. 

![](/blog/images/Manjaro-Linux-Tage.png)

**Original Pinebook showcased at Manjaro booth, Linux-Tage 2019**

We’re excited and proud to announce that future Pinebook Pros will ship with Manjaro KDE as the default operating system. Pre-orders for the next production run of Pinebook Pros starts on March 18, 2020 with an estimated shipping date of early May, 2020 (once Hong Kong border opens to our shipping staff). The image that ships with the upcoming Pinebook Pro batch features an additional layer of polish, which extends to a custom set of wallpapers and tweaks to the default application list to include popular software. If you are a Manjaro enthusiast, then I probably don’t need to convince you any further, and if you haven’t gotten a chance to try Manjaro yet then I suspect you’ll really enjoy the out-of-the-box experience. Speaking of the out of the box experience, Manjaro ships with an OEM setup / installer that allows you to set your username and password as well as choose your keyboard layout and system locale on initial boot. 

![](/blog/images/ISOANSI.jpg)

**ANSI (left) and ISO (right) Pinebook Pros running Manjaro with KDE Plasma**

If Manjaro isn’t your OS of choice, then you’re of course welcome to try any of the [many options](/documentation/Pinebook_Pro/Software/Releases/) available for the Pinebook Pro. Nearly all available OSes can be booted from a SD card and, once you find what you’re looking for, the chosen distribution or \*BSC can be installed to eMMC flash memory. The list of available software is continually growing with new, novel and interesting releases becoming available weekly. Two notable releases from the past couple of weeks include [Recalbox (pre-release)](https://github.com/mrfixit2001/recalbox-rockchip/releases) by the one and only [MrFixIt](https://github.com/mrfixit2001/), as well as [postmarketOS](https://images.postmarketos.org/pinebookpro/) and [Slackware](https://gitlab.com/sndwvs/slackware_arm_build_kit). So if you’re keen on trying something different (and yet familiar - since posmarketOS is built on Alpine Linux), or experience Slack nostalgia, then here’s your chance. I am also sure that retrogaming enthusiasts will be happy to see a dedicated Recalbox image for the Pinebook Pro; the Pinebook Pro is able to run Dreamcast and PSP games at upscaled resolutions at full speed, making it a great on-the-go gaming system. One of the cool features of Recalbox is that if you boot with either an USB-C-to-HDMI dongle or a USB-C dock connected, then the output will automatically switch to the external monitor.   

![](/blog/images/RB.jpg)

**Recalbox on the Pinebook Pro via [Vercas](https://github.com/vercas)**

I almost forgot to mention that there is now also a dedicated Kali Linux OS image (which happens to be something many of you have been asking about) so you no longer have to rely on the build script to generate your own image - all you need to do is DD the provided Kali image to a SD card and try it out for yourself. 

![](/blog/images/kali.jpg)

**Kali Linux on the Pinebook Pro**

The OS choice for the Pinebook Pro will expand even further in the coming months since - thanks to efforts by Tobias from Manjaro and other developers - the RK3399, and many of the core Pinebook Pro features, will be included in the mainline kernel 5.7. This means that you’ll be able to download any generic ARM64 OS image provided by a distro and use it on the Pinebook Pro (!). I suspect that the generic builds will not be as feature complete or functional as those tailored for the Pinebook Pro (as well as ROCKPro64 and HardROCK64), but this is a very important step nonetheless as it significantly simplief OS porting to our platform. 

The last bit I want to touch upon in this section concerns minor structural tweaks to the Pinebook Pro construction. I’ll write up a more complete list of these improvements this coming week and post them on the Wiki - here I’ll focus on the more significant changes: 1) stand-off height for pillars holding the keyboard and bottom of the chassis together has been improved; 2) kapton tape is used in places where electrical shorts can introduce interference to audio devices; 3) soft non-conductive standoffs are used around various parts inside the case preventing shorts and making it more sturdy; 4) screen bezels are now not only pressure-fitted but also held in place using adhesive tape - this prevents dust from entering the crevices between the LCD and the bezel; 5) the plastic formula was tweaked to make the plastic less brittle. In all likelihood, none of you would notice these changes unless explicitly told about them; I have a reason to believe so, since the ANSI batch already included most, if not all, of these changes. 

#### PinePhone

Before I proceed to write about the current state of PinePhone software, I first want to write a few words about the PinePhone itself. Undoubtedly many of you are anxiously waiting to hear news concerning PinePhone production resuming following the novel coronavirus recovery. I want to assure you that the PinePhone is at the top of our out ‘to-do’ list, however there are yet a number of things we need to work out before the next production-run gets commissioned. In short, we’re working on it. 

On a topic somewhat related to hardware, I’d also like to mention that both the hard (black) and soft (transparent) protective PinePhone cases should be available in the PINE Store within two weeks time. I have written about the cases [in the past](https://www.pine64.org/2019/12/05/december-update-thank-you-for-2019/) so I won’t repeat myself, but the one noteworthy piece of information that I wish to underline is that revenue from sales of soft cases goes to manufacturing the Pinebooks aimed at efforts to close the digital divide (please see _Housekeeping_ section).

![](/blog/images/cases.jpg)

**Transparent silicone case (left) and hard black case (right)**

Software-wise things are moving quickly and starting to look good. As always, in a project that has so much depth and breadth as the PinePhone, it will be difficult for me to cover all aspects of development that have taken place in the past 30 days. Instead, I’ll focus on the key developments and some of the more interesting things that transpired recently. Let me start with what is undoubtedly most interesting to existing and prospective PinePhone owners, namely outgoing and incoming phone calls. The key development here, as I understand it, is that megi and smaeul - along with other developers - managed to get automatic audio-routing working in late February. This effectively means that the audio output can change dynamically when making or receiving phone calls. In other words, you can watch a video or listen to music with audio coming from the speaker and then make a phone call and have the audio automatically routed to the earpiece. This has now been implemented in most OSes. 

As for phone call capability itself, from the OSes that I’ve seen and tested in the past 30 days, nearly all systems can receive and make phone calls. I have also noticed a quality improvement in audio quality on the receiving end in [KDE Neon](https://images.plasma-mobile.org/pinephone/) (after _sudo apt update && sudo apt upgrade_) as well as in the newest [Debian+Phosh](http://pinephone.a-wai.com/images/) image. I also know that various developers, from different projects, are currently attempting to enable the notification LED, vibration motor and to make the phone ring when the phone receives a call. These are obviously important features to  make you notified of incoming calls as well as received SMSs or other messages. By the time I publish the next community update I expect some OSes will have these features either implemented or in the process of testing. Speaking of sensors, [Marius](https://twitter.com/Mariogrip) from UBports and [Bhushan](https://twitter.com/BhushanNShah), who's working on KDE Neon, have demonstrated auto-rotation using PinePhone’s accelerometer on Ubuntu Touch and Plasma mobile respectively. Noteworthily, auto-rotation now also works on LuneOS, which remains a well performing and interesting alternative to more popular OS propositions. I expect to see the auto-rotate feature to also find its way into the next releases of the aforementioned OS images in the coming weeks.

{{< youtube id="BWhXA3DkF_E" >}}

**Auto-rotate on Ubuntu Touch, originally posted by Marius**

{{< youtube id="F56p3rTkTn4" >}}

**Auto-rotate on KDE Neon, originally posted by Bhushan**

A major development task currently concerns improving battery life in idle state. This is something which is something I already touched upon in [last month’s community update](https://www.pine64.org/2020/02/15/february-update-post-cny-and-fosdem-status-report/). There are a number of different attempts at making the PinePhone last a day on battery, but perhaps the most impressive to date can be seen in the newest KDE Neon build. Running KDE Neon, with WiFi and the LTE modem turned on, the PinePhone can now last approx 10 hours on the battery alone. Now, I recognize that this may seem underwhelming compared to our Android or iPhone smartphones, but keep in mind that this device is nothing like your ordinary phone. Moreover, there are also many known areas that can be improved upon in this regard. I think that it's fair to say that, given the length of time in development, a 10 hour stand-by time with connectivity enabled is very good improvement over the previous 4-6 hours. 

Another topic I wish to touch upon is growing OS availability. Software options literally exploded in the past 30 days as Braveheart brought many new developers who began porting a variety of OSes, some of which have previously not been seen on a small form-factor device such as a phone. Among others, we’ve now seen an early port of Android 10 - running kernel 5.6 no less - as well as the much anticipated NixOS (much anticipated by me that is - not sure of its overall popularity). I have, sadly, not had any hand-on time with either of these systems, but from what I’ve gathered NixOS already works well, while Android 10 is mostly unusable at present time. As for the [Arch Linux](https://github.com/dreemurrs-embedded/Pine64-Arch/releases) OS image, this one is clearly aimed at tinkerers and experienced enthusiasts; it comes with no desktop environment nor UI, and clearly invites you to build your own custom experience atop the bare Arch OS image. Last, but certainly not least, we’ve seen an impressive amount of work done on the PinePhone [Fedora port](https://github.com/nikhiljha/pp-fedora-sdsetup/releases/). The port already runs great and has much, if not all, of the functionality that other OSes offer. This  includes phone call functionality, SMS, LTE, GPU acceleration, etc., I’d like to give a shoutout to Peter Robinson from Red Hat, who actively helps and mentors the dedicated group of enthusiasts porting Fedora over to the PinePhone.  

![](/blog/images/fedoraPP.jpg)

**Fedora on PinePhone, picture via [Tor.sh](https://twitter.com/torbuntu/status/1232471283381616640/photo/1)**

![](/blog/images/androidpp.jpg)

**Android 10 on PinePhone by [Moe Icenowy](https://github.com/Icenowy?tab=stars)**

Lastly, across the board we’ve seen improvements in UI performance. For instance, the recently pushed Ubuntu Touch OS image runs much smoother than in the past and features a number of stability improvements. I also subjectively feel that Phosh and KDE front-ends have benefited significantly from recent development. That said, I have also experienced new bugs - such as stuttering in Angelfish on KDE Plasma -  previously absent on the same OS images or front-ends. There is no denying that it’s all still very much a work in progress; with so much changing on a bi-weekly basis, testing new builds and providing structured feedback is important. So, if you happen to have a PinePhone Braveheart edition, I strongly suggest you visit the (well maintained) [PinePhone software releases](/documentation/PinePhone/Software/) page on our Wiki and try out recent OS images.

#### PineTime

I usually pay the PineTime less attention in my updates than the other devices. This isn’t because I care less for it - quite to the contrary, I was the one who pitched the idea of making it in the first place - but rather because I have little to no knowledge regarding the software it is running. Besides, my posts simply could not measure up the [publications](https://lupyuen.github.io/) by Lup Yuen Lee on the PineTime, which I encourage you all to read. Regardless, I do feel that the project is underexposed by us and that it deserves a bit more love. To give the project and the devs hard work a bit more spotlight we have now placed a large PineTime widget on the main page. I trust this will help in showing off the device and the work that has gone into it to prospectus users browsing our website. 

And there truly is plenty to marvel at and appreciate. This month I want to take a look at the first piece of software that resembles a full FOSS OS for the PineTime created by [JF](https://twitter.com/codingfield), whose work I previously featured in [community updates](https://www.pine64.org/2019/12/05/december-update-thank-you-for-2019/). Until recently all PineTime software developed by the community, while highly impressive, amounted to the functionality of a “dumb” watch capable of syncing with a smartphone. JF’s current work offers a first glimpse at what may become the first full OS for the device built by the community. In the video posted earlier this month, we see JF flip though (smoothly I may add) the various functional demonstration elements of his PineTime front-end. Among the demonstration applications shown are an information widget, a timer of sorts and an analogue watch counting down seconds. There are also other demo applications registering user input - finger taps specifically - and other such functions. All this functionality is accessible via a pull down drawer which appears over the watchface. 

![](/blog/images/JFPineTime.jpeg)

**JF's OS on the PineTime - different demo apps shown**

The hardware limitations of the PineTime also invite some interesting work-arounds and implementations. For instance, due to the slow refresh rate, JF implemented a scrolling transition when the screen needs to be fully refreshed. It provides a perfect illusion of a fast and smooth transition when the app drawer is pulled down by the user. The experience is very reminiscent of what you may see on much more complex smartwatches from big brands. The OS itself is written in C++ and uses FreeRTOS as well as LittleVGL - a free and open-source graphics library - to provide the UI graphical elements. If you are interested in the project then please check out [JF’s github](https://github.com/JF002/Pinetime/releases/tag/v0.3.0) and, if you’re able, contribute to his work - I’m sure he’d appreciate input. 

{{< youtube id="D4Rj_ZIhl8U" >}}

**Demo apps in action, originally posted by JF**

I’d also like to mention that this is only one out of many ongoing efforts to build a fully functional OS for the PineTime. Many other developers are actively working on their own front-ends and/or applications. If you are interested in the PineTime, and wish to learn more about it from someone more competent than me, then I suggest you take the plunge and join the PineTime chat available via Discord, IRC, Telegram and Matrix (all bridged together), accessible from Forums And Chats tab on this website. The community there is very welcoming and will gladly help you with getting started. In the spirit of community development, the PineTime dev kits have now been available to all those who are interested in it for some time, so anyone can have a go at testing and contributing to the project.

That will be all for this month. We have a lot more news coming in the next few weeks, so subscribe to the blog and stay tuned!
