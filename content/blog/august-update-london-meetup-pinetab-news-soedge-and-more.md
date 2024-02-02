---
title: "August Update: London Meetup, PineTab News, SOEdge and More!"
date: "2019-08-05"
categories: 
  - "news"
  - "pinephone"
  - "pinetab"
  - "soedge"
tags: 
  - "ai"
  - "pinephone"
  - "pinetab"
cover: 
  image: "PineTabMain.jpeg"
images:
  - "/blog/images/PineTabMain.jpeg"
---

![](/blog/images/PineTabMain.jpeg)

PineTab development prototype

July has been a busy month for all members of the PINE64 project. Between the updates to various systems, preparation of Pinebook Pro pre-orders and the subsequent launch, shipping of PineTab development kits as well as production of the PinePhone prototype, there has been little to no downtime. To this end I wish to publicly thank fireTwoOneNine for doing a hell of a job helping out, troubleshooting problems and setting up the systems necessary to keep the wheels turning. An awesome job and a huge thank you. Here is what is on this month’s update agenda: 

- We’re meeting up in London - join us!
- Just the Wiki left to do - help wanted
- PineTab is up and running! ; getting an illuminated keyboard
- Pinebook Pro pre-orders sum-up ; **public pre-orders 25 August**
- PinePhone prototype this month ; software coming along
- SOEdge AI module

#### Meetup in London

We’re having a casual meetup in London on August 18, noon (12:00) at [Serpentine Bar & Kitchen located in Hyde Park](https://www.google.com/maps/place/Serpentine+Bar+%26+Kitchen/@51.5047056,-0.1630811,16z/data=!4m5!3m4!1s0x48760537434b22bf:0x2e1c0b8803272111!8m2!3d51.5049912!4d-0.1598543). We’ll have a few things with us (including a Pinebook Pro prototype) to show and toy around with. We will also share information about new and upcoming devices at the meetup - as always we’re very keen to hear your feedback regarding what we’re doing. If the weather is good then we can sit outside in the sun; it not, well, then we can sit inside and later head out to the closest pub. So if you live in London, or otherwise able to make the journey, then we’re looking forward to meeting you in person. Everyone is welcome.  

#### Housekeeping

In June I wrote that the next things on our community to-do agenda are the chats and Wiki. Let's start with the prior - we have now improved the way in which the various chat protocols are bridged and, after a few hiccups, everything seems to be running smoothly \*knocks on wood\*. There are now also Telegram groups for [Pine64](https://t.me/mtrx_pine64), [Rock64](https://t.me/mtrx_rock64), [PinePhone](https://t.me/pinephone) and [Pinebook](https://t.me/mtx_pinebook) (Pro) that have been linked to their Discord, IRC and Matrix counterparts. They’ve been added the the community tab on the website. In a nutshell, you now have more ways to communicate with each-other and it's all interlinked in a neater way. If you haven’t joined in as of yet, then consider doing so as much information shared in the chat never reaches the forum. 

Onto the subject of the Wiki. This is the last item on our community ‘fix-and-improve’ itinerary, and something that has been in the back of my mind for well over a year. Similarly to many other things in the PINE64 project, the idea behind the Wiki is that the community runs and maintains it. Whilst handing over control of much of the project to the community  - the website, forum, chats, etc., - has been a great idea and success, this approach has not worked equally well for the Wiki. This isn’t to say that people have not contributed, because there have been numerous contributions, but it has become evident that a long-term and sustainable strategy needs to be put in place. A community member - [**zaius**](https://forum.pine64.org/member.php?action=profile&uid=11227) **-** has taken it upon himself to organise a group of a few people to accomplish just this. If you’re interested in helping out then make sure to reach out to him directly on the forum (and CC me in PMs please). 

#### The PineTab is up and running! 

Let’s talk about the PineTab, which I feel is the one device that hasn’t gotten the exposure it deserves thus far. In this update I will make an attempt to rectify this, especially since I thankfully have nothing but good news to convey. This month developers from partner projects received their PineTab kits and it didn’t take long before the first demo images became available for testing and showcasing functionality. As is always the case, we have already gotten a lot of valuable feedback from developers in regards to both electrical and mechanical issues with the dev-kits. We will collect and convey all the reported feedback to the factory so that everything is ironed out before the PineTab ships to end-users. 

Speaking of shipping, apart from the handful of reported shortcomings, the hardware is coming together nicely and we’ve already locked in the key specs weeks ago. At this point production could start any moment granted a suitable OS image becomes available; I’m discussing software progress further down in this post. As we announced in June, a number of upgrades have been made to the PineTab since the February unveiling - this includes a larger 64GB eMMC capacity (voted on by the community) as well as an optional M.2 key adapter that can be used for LTE or storage. I expect that the potential to mount a LTE module is of particular interest to many users on-the-go. I am including pictures of the PineTab with a M.2 SATA drive and LTE module mounted in the case. 

![](/blog/images/IMG_20190805_105444.jpg)

LTE

![](/blog/images/PineTabNVMe.jpg)

M.2 SATA

But this isn’t the end of improvements made to the device and peripherals. We’re pleased to announce that the keyboard (which you probably should get) - that also doubles up as a cover for the tab - will ship with a backlit ANSI-layout. We’re still figuring out the details, but it will likely be customised in accordance with the feedback we received for the Pinebook Pro. The quality of the fabric on the keyboard/ cover has been improved as has the key spacing, making it both more durable in transport and comfortable to type on. I trust that this is a welcome upgrade for those eagerly awaiting the PineTab since input quality is clearly at the very top of the priority-list of PINE64 user-base. 

![](/blog/images/NewPineTabKeyboard.jpg)

PineTab New Keyboard

Another yet unannounced PineTab upgrade that we’ve recently made is a spec bump of the battery. The PineTab page currently lists a 4500mAh battery but we’ll be shipping the PineTab with a 6000mAh battery. This is the maximum size of a single slab (cell) produced, and using more than one slab is out of the question as we need to keep some space inside the case free for those who will be mounting M.2 storage or LTE inside. As you can see from the pictures above, there isn’t much space left inside the case with LTE or storage mounted. While the PineTab may not reach the 10 hour battery life of the original Pinebook, with its lower screen resolution and smaller display size I still expect that the battery-life to be in excess of 6 hours of continuous run-time. The battery can be charged in two different ways: via the standard barrel connector or the micro USB port. While charging via micro USB is not ideal under normal circumstances, since it is relatively slow, it is a major bonus because it makes it possible to charge the device from a powerbank. These features combined with the small size and versatility of the device will make it a good travel companion - something you may wish to take with you on long flights or treks in the wild. 

On to the software; there are quite a few images already available and, thanks to all the development that has gone into the Pinebook and the PinePhone, they are already very functional. There are already postmarketOS, AOSC, Manjaro, Ubuntu Touch, KDE Neon and numerous other OS images being worked on - many of which are being developed alongside Pinebook or PinePhone OS images. As a result, I expect that software support for this device will be solid on launch day, and it will benefit from both the Pinebook (desktop-oriented) and Pinephone (touchscreen oriented) OS and front-ends. The ultimate goal is to have many options for the PineTab, so that those who primarily wish to use it as an ultra-portable laptop and those who actually want a ‘tablet-first’ device have a range of options. That said, we’re currently still waiting for one feature-complete OS image that the PineTab can ship with. 

![](/blog/images/Pinetab1.jpg)

![](/blog/images/Newer-PineTab-Plasma.jpeg)

Different OS images and front-ends

![](/blog/images/PineTabPMOS2.jpg)

I was really excited to see [Martijn Braam](https://www.youtube.com/channel/UC4UXU2ZkeAwEFlLv1Yt1UMQ) from postmarketOS demo the PineTab running a build with the Sway window manager. Watching the video gives you a sense of the sort of interesting experiments that such a laptop-tablet hybrid device opens up. You can see Martijn use the trackpad and keyboard for the usual window manager and terminal stuff, and then switch to the touchscreen to interact with web pages in the browser. Obviously the Sway WM may not be a natural nor a perfect fit for the device, but the option is there for those who only occasionally need the touchscreen functionality and love tiling managers. Moreover, looks like Sway will be getting touch navigation buttons on the top bar, gesture navigation and a virtual keyboard in the foreseeable future - making is a real option. Let’s face it, if tiling WM experience can be enriched by the touchscreen then every other scenario I can think of - perhaps with the exception of running a raw Bash shell - is almost certainly viable. Martijn also has a video showcasing Phosh shell running on postmarketOS. It is very cool to see a work-in-progress front-end crossover from another great FOSS project. I have also seen KDE Plasma and plasma mobile running on the device; I am linking the relevant media below.    

https://www.youtube.com/watch?v=-ZG0eBRzSBc&t=1shttps://www.youtube.com/watch?v=FFgKjJYHfas

#### Pinebook Pro pre-order launch 

I spent all of last month’s update on the Pinebook Pro so I’ll keep this section short. Although the pre-order launch was not exactly problem-free, I feel that it went pretty well overall. Initially a bug in the database prevented people who either signed up to the forum or changed their password since late May 2019 from being accepted for a pre-order. This issue was quickly traced down and rectified (it took 40 minutes from the first report of issues to system being fixed) and, to the best of my knowledge, everyone who wanted to receive a pre-order confirmation eventually received an acceptance email. I’ve also received reports that some users, who already received their purchase-coupons, ran into issues with completing their order after selecting additional accessories such as the NVMe adapter - this has now been resolved.

I understand that the various little problems have proven frustrating to some of you, and I appreciate that it made the process less than perfect. What I will say, however, is that one of the reasons we chose to open pre-orders to the community first is so that our system could be properly tested on a smaller scale first. We’ve now learned from the launch and have ideas to further improve, streamline and simplify the pre-order system in the future. Since a similar system will likely be used for future products too, this pre-order launch effectively made for a test-run of long-term system viability. To this end, I thank those of you who signed up for pre-orders - knowingly or not, you’ve helped improve the experience for others in the future.

I sincerely hope those of you who receive the Pinebook Pro next month will take the time to actively offer feedback and help us address any potential shortcomings. Meanwhile, we’ll be opening **pre-orders to everyone outside of the forum on August 25th.** We expect that there is a fair amount of interest in the Pinebook Pro outside our core community and cannot wait to welcome new members into our ranks. To those community members still on the fence, deciding on whether you want a unit with 128GB eMMC: please be aware that the community member pre-orders close on August 24th. This means that from this point on only 64GB eMMC Pinebook Pro models will be built. 

_(Note: For those wondering about when their coupons will be emailed-out and units will be shipped, keep up to date with [this thread](https://forum.pine64.org/showthread.php?tid=7752).)_

#### PinePhone - here is what's happening 

I expect there to be a lot of news about the PinePhone in coming weeks. If all goes well then in the next news update we’ll be taking a look at the PinePhone prototype and, granted its functional \*knocks on wood\*, we’ll be seeing it boot for the first time. But since my crystal ball has been malfunctioning as of late, instead of talking about the future, let’s instead focus on the things that are happening now. For starters, some developers have now received revision (2.0) of the PinePhone development kit. It fixes all of the issues that were present in previous iterations of the kit and aligns the functionality with the actual phone. We expect this to be the final revision of the board, but we will likely be replacing the touch panel on the kits and the actual phone, since the current one is giving developers grief. To consolidate things, and make development easier, we will use the same touch panel driver as the one implemented on the PineTab; we haven’t heard any complaints about the driver from developers and it clearly is superior to the one currently used on the PinePhone dev kit. 

To the layman, the most important feature of the dev kit 2.0 is its capability to output video via USB-C, but there are many other tweaks that improved the operational stability of the setup. For all intents and purposes, this is just an evolution and not a revolution, and developers can happily keep on using the older development iterations until the actual phone ships. I’ve already mentioned that the prototype is being built and this is progressing well without any major setbacks. We were initially hoping to get a chance to show it off during the London meetup and get some live feedback from attendees, but due to a relatively minor delay (we’re some ~2 weeks behind schedule) it's unlikely that we’ll have it with us. Regardless, the production of the prototype is a crucial milestone and you can take a closer look at how all the bits-and-pieces will be jigsawed together in the pictures below. 

![](/blog/images/PinePhoneJigsaw.jpg)

PinePhone Jigsaw

Once the Prototype is done it will have to undergo proper testing, which will take some time. Once all the testing has concluded we’ll have a better idea of when the first batches - aimed at developers and enthusiasts - will start shipping. We’re confident that it will be in early-to-mid Q4 this year. We’re currently evaluating and thinking about how to best launch the device so it only gets into the hands of those who are completely aware that they will need to deal with numerous OS teething pains until the software matures. Before someone points it out, I understand that this means we’re going back on what we initially said, namely that “(...) the PinePhone will first ship when software is ready (...)”. The reality of the situation, however, is that advanced users want to get their hands the PinePhone, and we don’t want it sitting in a warehouse until end-user level performance is achieved. I am still hoping that we can have at least one solid OS on day-one, and seeing how fast progress is made in recent weeks, I think that there is a possibility for at least an image or two achieve core functionality by production time.

As I have said in the past, I am not the best person to evaluate or report on software progress, but even with my limited understanding of the development complexities, I can tell that much is happening and progress is made. For those who do not follow the chats on a regular basis here is a quick run-down of what has been happening with the PinePhone for the past few weeks: There is now a relatively error-free postmarketOS plasma mobile build for the PinePhone. In the past, applications would not run and many of the UI elements that ought to be opaque were transparent. There are still performance issues with the build - the UI, despite being accelerated, is slow to respond (potentially something to do with shaders) and the touch screen is somewhat laggy. But as you can see below in the linked video, this is starting to look pretty good. We’ve also had our first look at Sailfish OS running on the PinePhone. The short demo shows the UI being quite responsive when entering and exiting the settings app, and scrolling though the different options seems very smooth as well. From what I can tell a lot has been done in the graphics driver driver, in this case Lima, to make this possible on mainline. I can only report on these information snippets due to time constraints and my insight. You can follow development live in the chats.

One last thing - as promised, we will have all the documentation about the PinePhone available just before the launch. Since we announced that we’ll be exposing I2C via pogo pins on the PCB (refer back to the blow-up diagram) many have expressed interest in 3D printing and otherwise making back-covers to use the interface. To this end, we’re releasing the back cover .stp file for you start planning or creating your add-ons for the PinePhone.

![](/blog/images/newer-PinePhone-PLasma.jpeg)

Plasma Mobile (pmOS)

![](/blog/images/PinePhoneUT.jpg)

Ubuntu Touch

![](/blog/images/PinePhonePhosh.jpeg)

Phosh (pmOS)

#### SOEdge AI Module

This is more of a teaser than a full blown announcement. As I have hinted in the June community news update, we have been toying with the idea of an AI module for some time. In fact, we initially intended for an AI variant of the RockPro64 but decided against it due to delays of the RK3399Pro SOC. Since we initially set out to create a RockPro64 AI a more feasible alternative arose, namely the option of creating a stand-alone AI module that can work independently or in conjunction with an existing SBC via fast I/O. The SOEdge neural module is based on the RK1808 and comes in a standard SODIMM form factor that it shares with the SOPine. It features 2GB of DDR4 SDRAM, 128Mb of SPI-NOR Flash as well support for eMMC.  

We have taken great care to ensure a high degree of compatibility between the SOEdge and SOPine peripheral/ baseboard compatibility. In result, the new module can be used with the SOPine baseboard (N.B. the SOEdge doesn’t have digital video out functionality, so the digital video out port on the baseboard will not function) as well as the Clusterboard. We also intend to create a SOEdge-specific baseboard as well as PCIe and USB 3.0 adapters for it, so that it can be paired with the ROCK64 via USB 3.0 or the ROCKkPro64 using PCIe. We have spoken and worked closely with Rockchip and they’ll be open-sourcing all the relevant source code and documentation related to the SOEdge. I will be returning to look at the SOEdge, as well as other things we’ve been working on behind the scenes, at a later date when the software is up and running and there is something to showcase. 

![](/blog/images/SOEdge3_Baseboard.jpg)

SOEdge in SOPine Baseboard

![](/blog/images/SoEdge1.jpg)

SOEdge AI module

There is a lot more news coming and I cannot wait to share it all with you next month. That’s all for now - you know where to find me if you want to have a chat.
