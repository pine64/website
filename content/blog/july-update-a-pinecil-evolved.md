---
title: "July Update: A Pinecil Evolved"
date: "2022-07-28"
authors: ["Lukasz Erecinski"]
categories:
  - "pinecil"
  - "pinesound"
  - "pinetime"
  - "quartz64"
  - "quartzpro64"
  - "star64"
tags: 
  - "pinebuds"
  - "pinecil"
  - "pinesounds"
  - "pinetime"
  - "quartz64"
  - "quartzpro64"
  - "star64"
cover: 
  image: "July-Update.jpg"
images:
  - "/blog/images/July-Update.jpg"
---

![](/blog/images/July-Update.jpg)

Welcome to the July community update - I hope you’re staying cool in the heatwave. This month we’re introducing the Pinecil V2  - an evolution of the original Pinecil - and taking a closer look at the Star64 RISC-V SBC. We also discuss Quartz64’s development progress, the PineBuds and receive an update on PineTime and InfiniTime from JF. 

Let's get into it.

You can watch the synopsis of this month’s community update on YouTube (embedded below) as well as on [Odysee](https://odysee.com/@PINE64:a) and [PeerTube](https://tilvids.com/accounts/pine64tilvids/video-channels). To stay up-to-date with PINE64 news make sure to subscribe to this blog (subscription widget at the bottom of the webpage), follow the [PINE64 Telegram News channel](https://t.me/PINE64_News), the [announcements channel in Discord](https://discord.gg/pine64) as well as our [Twitter](https://twitter.com/thepine64) and [Mastodon](https://fosstodon.org/@PINE64).

I’d like to thank [Alex](https://twitter.com/AlexRob12252696) (clover) [Ben Brown](https://twitter.com/RalimTek) (Ralim), [pillow](https://github.com/CounterPillow), [JF](https://twitter.com/codingfield) and [PizzaLovingNerd](https://www.youtube.com/channel/UCmGcm7dhEjS9CIOsOOv8y6w) for their contributions to this community update.

N.B. Comments on the blog post need to be in English and follow our [Community Rules and Code of Conduct](https://forum.pine64.org/showthread.php?tid=13209).

https://www.youtube.com/watch?v=Tn4S1mdt7QQ

**July Update video synopsis**

**TL;DR**

- Housekeeping
    - New PineTalk episode is out 
    - Quarterly Q&A on August 13, at 8:00PM CEST (UTC+2)
    - Alternative payment methods available in Pine Store again
    - The Pinebook Pro is available 
    - PINE64 EU has launched 
- Pinecil (V2)
    - New RISC-V SoC 
    - Adds BLE - opening potential for OTA updates & remote telemetry
    - Automatic detection of tip resistance
    - Compatible with existing peripherals and accessories, including cases
    - Range of new, shorter 6.2ohm tips for higher power level 
    - IronOS already ported 
    - Counterfeit protection; future option for users to verify if their Pinecil V2 is legit
    - Available very soon
- Star64
    - Congratulations to Gav for being the first to solve the riddle!
    - Star64 is in final layout stages and we want to bring it to the market soon
    - Uses StarFive JH7110 64bit CPU paired with BXE-2-32 GPU
    - Available in 4 and 8GB RAM configuration
    - Equipped with 2x Gigabit Ethernet ports (a variant with 1x GbE will be available later on for $5 less), PCIe, USB 3.0 as well as 2x USB 2.0 and GPIO
    - Follows Quartz64 model-A pricing and footprint
- PineSound
    - PineBuds plastic molding is now complete and first test molds underway
    - Hoping to being PineBuds to the market as soon as possible - maybe in October
    - Similarly to the Pinecil and PineTime, PineBuds have been built to deliver a great out-of-the-box experience for everyone, while also offering depth for tinkerers and those who wish to hack
- QuartzPro64 & Quartz64
    - QuartzPro64 dev units started shipping; we’re still accepting coupon requests from developers
    - Quartz64 receives DietPi support; now supported by Armbian, Manjaro, DietPi as well as giving option to run Arch Linux and NetBSD
    - Pillow submitted patches enabling PCIe and analog audio, a fix for fast SD cards has been accepted upstream, and patches enabling JPEG encoder have been merged
- PineTime
    - Infinitime 1.10 released with many changes & improvements under the hood
    - It is now possible to dismiss notifications
    - Tweaks to display, colour and gamma settings - making things look better
    - InfiniSim new features include animations & allows screen capture in GIF format
    - Ongoing work to improve memory situation by leveraging additional 4MB of internal flash
    - InfiniTime has 584 forks

## Housekeeping

Before we get to all the news of this month there are a few housekeeping items. In case you missed it, the [most recent episode](https://www.pine64.org/podcast/) of the PineTalk was released earlier this month. In this month’s episode, Zed - the show's editor - replaces Brian as co-host and joins Justin in discussing PINE64 news, gaming on Linux and gaming-related Linux hardware. The latest episode can be found on [PineTalk’s page](https://www.pine64.org/podcast/) along with all previous episodes. If you haven’t done so already I suggest you subscribe to the [podcast’s RSS feed](https://www.pine64.org/feed/mp3/)or follow it on the streaming platform of your choice. 

It is time for the quarterly Q&A. The Q&A is a community event which provides you with an opportunity to ask questions live in the chat and have us answer you live. In theory, we should hold the Q&A this month, but due to the holiday season - Marek is unavailable at the end of this month and I’m away at the beginning of the next - we’ve decided to schedule the Q&A for August 13th, 8:00 PM CEST (UTC+2). Just as last time, you will be able to pose questions on Discord, IRC, Telegram and Matrix and we will be live-streaming on Youtube. Many people asked us to simultaneously also live-stream the Q&A session to PeerTube - we will try to accommodate this request. A reminder about the Q&A will be released closer to the date via Telegram, Discord News channels and Social Media. Stay tuned!

{{< youtube id="qvJiBxRY_pY" >}}

**The last community Q&A in case you missed it**

In other news, it is once again possible to pay using alternative methods in the Pine Store via Stripe. For the past few months people only had the choice of PayPal at checkout, but now credit / debit card payments as well as payments via Apple and Google Pay have been reintroduced. We are well aware that people want multiple choices at check-out, and the Pine Store actively explores ways to provide an array of payment options. 

Speaking of the Pine Store, in case some of you missed it the [Pinebook Pro is once again available for purchase](https://pine64.com/product-category/pinebook-pro/). I know that many of you have been waiting for the Pinebook Pro to make a return, so if you’ve been waiting to pick up a unit then now is your chance. Dsimic is working on a write-up about the PCB of this Pinebook Pro batch, so keep an eye out for his post on this topic in the coming weeks. 

![](/blog/images/PBP-stock.png)

**The ANSI variant is avaialble now. There is no schedule for the ISO variant.**

Lastly, this month PINE64 EU finally launched following a delay due to various regulatory and technical hurdles. The store’s opening has been met with overwhelming positivity and I am humbled by the response. I am also thrilled to see the number of people who decided to check PINE64 EU’s website out and to pick up hardware - I never expected this much traffic. There is more stock on the way and as I stated in the past the selection of available gear will gradually grow. Early August will see the addition of the PinePower, USB-C cables and swag, as well as a restock of the PinePhone and the PineTime. I invite you to follow [PINE64 EU’s Twitter](https://twitter.com/pine64eu), [Mastodon](https://fosstodon.org/web/@pine64eu) and [Telegram](https://t.me/PINE64_News) news channel to be notified when hardware gets restocked.    

## Pinecil (V2) \[by [Ben Brown](https://twitter.com/RalimTek)\]

Two years ago, the Pinecil V1 was announced, and since then has become PINE64’s most popular consumer hardware. Sadly, I'm far worse at Riddles than the great Lukasz, so to cut to the chase, today we are announcing the follow up version two, which is more of an evolution than a revolution. Featuring improved hardware and accessories it retains the same ergonomics and design as the original Pinecil, and it will work with any accessories you already have. It will obviously work with any external accessories, such as cables, but also with existing cases and tips.

![](/blog/images/Pinecil-butt-1024x1024.jpg)

**There are more improvements than just the teal silicon grip ;)**

On the subject of tips, as well as the new Pinecil, we are creating a new line of tips for both the Pinecil V1 and V2. These tips are optimised for a higher power level than the standard Pinecil tips. By reducing the tip resistance from 8 to 6.2 ohms, they allow 65W at 20V USB-PD standard input. These tips will ship with the Pinecil V2 by default, but if you already own an original Pinecil then you’ll be able to pick up the 6.2 ohms tips from the Pine Store and use them with your existing device.  

![](/blog/images/Pinecil-V2-dissasebled.jpg)

**All parts are directly interchangeable and replaceable with the V1**

The Pinecil V2 is a natural follow on from the first version, still using a RISC-V processor, but adding noticeable upgrades to the hardware. Key changes from version one:

- New Processor (BL706)
    - Adds Bluetooth Low Energy       
- Higher maximum input voltage    
- Tentative support for USB-PD EPR (28V)
- Support for measuring tip resistance
    - Allows automatic detection of 6.2 vs 8 ohm tips    

Things staying the same:

- GPIO is broken out on USB-C for creating your own projects
    - Same pinout as Pinecil V1
- Same great feel, including the rubber grip
- Works with all existing tips
- Same DC input + USB-C input connections
- Same case as V1 and compatibility with the red and transparent cases

A notable improvement is the new BL706 RISC-V processor from Bouffalo. It is similar to the BL602 in the Pinenut from the Nutcracker challenge. The BL706 features Bluetooth Low Energy; so future IronOS releases will work to enable exposing features over Bluetooth Low Energy. One obvious future feature making use of BLE would be OTA firmware updates. That said, while technically possible, implementing OTA updates will be a non-trivial amount of work. It is something I suspect someone will make at some point for the bl70x/bl60x chips however, and If someone makes it, I’d be happy to incorporate it into IronOS.

![](/blog/images/pinecil-v2-PCB-1024x1024.jpg) ![](/blog/images/pinecil-v2-PCB-back-1024x1024.jpg)

**Pinecil V2 PCB top and PCB bottom**

The other potential future feature that BLE offers is remote telemetry and control. I'm currently thinking about what the future use of it would be, and I am always open to community requests and suggestions. For like a year now there has been chatter in the Pinecil chat about hacking a bl60x into Pinecil V1 to add WiFi/BLE; main driver has been having a remote control screen and possibly integrating into other software to, for example, turn on the air vent automatically while soldering. I suppose one’s imagination and the sky's the limit, but these two implementations would be legitimately useful additions rather than gimmicks. The inclusion of BLE is directly inspired by discussions that have been going on in the community chat for the Pinecil, and we are looking forward to seeing where the community takes the new feature set.

Additionally the hardware is designed for higher voltages to enable USB-PD EPR support (the higher voltage USB-PD standard is starting to become available). Using this new EPR standard, 28V PD chargers can be used with automatic negotiation. 

![](/blog/images/Pinecil-V2-box-1024x1024.jpg)

**Pinecil V2 comes in a simpler box, more in line with the aesthetics of other PINE64 hardware**

**\[edit from Lukasz\]** The Pinecil V2 will be available shortly: it may, in fact, be already available in the Pine Store when you’re reading this. The original Pinecil is the most popular PINE64 device - not counting the industry-focused SOPine modules - and it is also the most counterfeited hardware in our lineup. The Pinecil V2 introduces some measures to combat counterfeiting, which I won’t be discussing as I’m sure you’ll understand, but Ben told me that eventually users will be able to verify the authenticity of the Pinecil V2 on their own. Countermeasures aside, you should be aware that there are no more genuine Pinecil V1 units available and there won’t be any moving forward. In other words, all Pinecils available for purchase now on popular large web-stores aren’t legitimate.     

Lastly, many thanks to Ben for introducing us to the Pinecil V2 and for the amazing support from [IronOS](https://github.com/Ralim/IronOS). 

## Star64

Last month I had the pleasure to announce the Star64, PINE64’s first RISC-V single board computer. If you missed it, the [announcement took the form of a riddle](https://www.pine64.org/2022/06/28/june-update-who-likes-risc-v/), and I was thrilled to see so many people from the community participating and offering responses and guesses. I would also mention that I found some of the inaccurate guesses truly inspiring, and may draw on them for inspiration in the future when we’re working on new hardware. Congratulations to Gav who was the first to correctly decipher the riddle - someone will reach out to you for your shipping details closer to Star64’s release date. For those of you who are interested in the riddle, I’ll do a short run-down analysis at the end of this section. 

I covered a lot of the core hardware specifications last month, but just as a recap the Star64 is a single board computer comparable to the Quartz64 model-A - the notable difference being the RISC-V SoC at the heart of the SBC. The StarFive JH7110 64bit CPU features quad SiFive FU740 1.5GHz cores and comes paired with BXE-2-32 GPU from Imagination Technologies. I’d like to note that this is a different SoC to the one introduced last year, not in the least because this one includes a GPU. The board will be available in two configurations, with 4 and 8GB of RAM and we aim to match the Quartz64’s price point of the respective hardware versions. Similarly to the Quartz64 model-A, the Star64 will feature an open-ended PCIe port, USB 3.0 and GPIO. One thing I hinted at last month was that the Star64 will have 2 native Gigabit Ethernet ports. A version with only one Ethernet port will also be available at a later date, and we expect it to cost $5 less.

![](/blog/images/Star64-PCB-layout-1024x646.jpg) ![](/blog/images/Star64-layout-bottom-1024x662.jpg)

**A look at the final layout of the Star64**

Much of the work on Star64 work has now finished and the board in its final layout stage. There is still some testing needed, which will help us characterize the single board computer's qualities and performance. The initial review has yielded some very positive results, partly because the SoC runs cool without the need for passive or active heat dissipation, even under load. The SoC running cool without a heatsink is great news, as it opens the door for the platform to become a basis for future devices. In any case, the initial impressions are very good and we have high hopes for the Star64 becoming an opener for our RISC-V single board computer range. It will still take some time before Star64 finds its way into the Pine Store, but the engineers are working hard to make the launch happen sooner rather than later. I will keep you posted on Star64’s progress in the coming months.

Finally, for those of you who are interested, here is a short breakdown of the riddle. I titled the riddle _Victoria Line Station,_ because a station on the Victoria line underground in London is called Seven Sisters, which is the common name for Pleiades star cluster. First stanza: people who sing, act and dance and are recognizable are usually referred to as ‘stars’. The final line of the first stanza is a reference to a falling star. Second stanza: aside from the sky, stars can also be found in the sea - sea stars. I also associate stars with magic depictions in kids books. The final line of the second stanza indicates that 64 should be added at the end of the root name. Final stanza: here it would appear that I’ve made a mistake - stars first turn to blue giants, then to red giants, and only then explode. I should have gone back and double-checked my highschool knowledge.  

## PineSound 

It has been a little while since the last update on the PineSound project and the PineBuds in particular. The PineBuds were [first introduced in April](https://www.pine64.org/2022/04/15/april-update-no-more-unicorns/) and we have since been working hard to accelerate the pre-manufacturing process to bring production units to the market as soon as possible. I now come bearing news that the PineBuds tooling is finished and plastic molding has started. Obviously the plastic chassis of the buds and their case are just one part of the manufacturing jigsaw puzzle, but it is also a very important one. Granted the plastics turn out well, and no major changes to the mold will be necessary, then the next step is to deal with the electronics.  

![](/blog/images/PineBuds-final-render.jpg)

**A decision was made to go with no branding on the buds**

It may seem a bit counter-intuitive but, in a sense, the electronics are easier to deal with than the plastic molding. The most challenging part in this day and age is perhaps selecting components that can be reliably sourced in the long term. At present, we expect the production of PineBuds’ electronic components to be fairly straightforward, especially given that the prototypes have been thoroughly tested and found to be very reliable over the course of the past 5 months.  

![](/blog/images/PineBuds-plastic-mold-production-case-1024x834.jpg)

**First plastic mold of the PineBuds carry case**

If everything pans out, we hope to be able to make PineBuds available for purchase in early October. I hope that the Pinebuds will turn out interesting to a wide demographic by offering solid core functionality to those who simply want good in-ear headphones, as well as a deep and easily accessible array of options for those who wish to tinker and hack. In this sense the PineBuds are a very similar product to the PineTime and the Pinecil. Needless to say, we hope that the PineBuds will see the same level of success as the PineTime and the Pinecil have enjoyed.   

## QuartzPro64 & Quartz64 

Before I get into some of the Quartz64 news, I would just like to mention that the first batch of QuartzPro64 boards have gone out to developers. I was glad to learn that the first round of developers have already received their boards and began working on supporting the platform. This was the first dispatch of QuartzPro64 and many more are yet to come. We have received a good response from the development community and the boards sent out earlier this month have found their way into the hands of very skilled developers. We are, however, still actively seeking the best possible candidates for these early development boards, so if you are someone who could contribute to the bring-up process of the RK3588 then make sure to [submit your application](https://preorder.pine64.org/#/quartzpro64) to purchase a dev unit at half the price.

![](/blog/images/Screenshot_20220728_113113-896x1024.png)

**Thankfully you have quite a few heatsink mounting options [Sergio](https://twitter.com/slpnix) - got a RockPro64 or (very) old GPU heatsink laying around?**

Now, let us discuss Quartz64 developments. Earlier this month DietPi added support for both Quartz64 and SOQuartz. The Quartz64 is now officially supported by DietPi, Armbian and Manjaro, but instructions for running Arch Linux and NetBSD have also been added to the Wiki in recent weeks. We also hope to get other OSes on board supporting Quartz64 in the coming weeks. As a side-note, if you are a maintainer of a distro that added support for the Quartz64 then please reach out to one of the mods and notify them so they can add relevant entries on the Wiki. The reason why we’re seeing an increase in the number of OSes supporting the platform is the pace at which the Quartz64 matures. As I [showcased last month](https://www.pine64.org/2022/06/28/june-update-who-likes-risc-v/), the current development pace has helped push the PineNote closer to a more general early-adopter release. Obviously the benefits are mutual, and development on the PineNote has also helped the Quartz64.  

![](/blog/images/DietPi-support.png)

**DietPi announcing [support for Quartz64](https://dietpi.com/docs/releases/v8_6/) this month**

I spoke to [Pillow](https://github.com/CounterPillow) this past week to learn what advances have been made in the past month. I was told that they submitted patches enabling PCIe and analog audio output for the Quartz64 Model-B to mainline Linux. A fix for fast SD cards not working on the Quartz64 has also been submitted upstream and will hopefully find its way into previously mentioned OSes with the next Linux installment. Last but certainly not least Pillow patches enabling the JPEG encoder on the RK3566, which benefit not only the Quartz64 but also the SOQuartz and the PineNote, have now been merged. This is a tonne of fixes in a relatively short period of time, and these are fixes that benefit the entire RK3566-based ecosystem. I am thrilled to see the platform taking a hold in the community, maturing and gradually improving.   

## PineTime \[by [JF](https://twitter.com/codingfield)\]

We released [InfiniTime 1.10 "Yellow Mango”](https://github.com/InfiniTimeOrg/InfiniTime/releases/tag/1.10.0) shortly after last month's community update. This new release is the result of nearly 3 months of work by the community: 54 pull-requests were merged, totalling 139 commits and 242 files changes. Thanks to everyone who participated in this new version of InfiniTime! InfiniTime 1.10 contains a lot of changes under the hood: code cleaning and refinements, improvements to the build system (automatic font generation), update of the toolchain, and more. These changes are not visible to the end users but are very important for the maintenance of the project in the long term.

Of course, we have also added some features that will please our beloved users. A lot of them were asking for this for a long time for a possibility to dismiss notifications. This is now possible in InfiniTime - all you need to do is swipe on the notification from left to right to dismiss it.

Here's a video I shot when testing this new feature on my devkit using the PinePhonePro:

<iframe title="Work in progress : testing notification dismiss" src="https://video.codingfield.com/videos/embed/bab9b8d2-d4cd-4942-bdf2-495197741171" allowfullscreen sandbox="allow-same-origin allow-scripts allow-popups" width="560" height="515" frameborder="0"></iframe>

**Testing notification dismiss from a PinePhone Pro with keyboard case**

We've also tweaked the display settings and gamma to improve the color displayed by the LCD, improved the Timer app interface, and reduced the time needed for the watch to go to sleep. These are just some of the more noteworthy refinements, but this release has  many other improvements and bug fixes.

[InfiniSim](https://github.com/InfiniTimeOrg/InfiniSim), the InfiniTime simulator, has also received a couple of new features: it now supports InfiniTime animations (vertical and horizontal transitions) and allows recording screen capture in GIF format. This is a very useful feature that allows us to easily do demonstrations and share progress with other people. We’ll probably also use it extensively in our documentation in the near future.

![](/blog/images/infinisim_gif.gif)

**Screen capture from InfiniSim showing animations and dismissing of notifications**

[Siglo](https://github.com/theironrobin/siglo) also received a few updates and released [version 0.9.9](https://github.com/theironrobin/siglo/releases/tag/v0.9.9) at the beginning of this month. In contrast, [InfiniLink](https://github.com/InfiniTimeOrg/InfiniLink), the iOS companion app for InfiniTime, is still looking for a maintainer. [Xan-m](https://github.com/xan-m), the original author, [announced a while ago that they would not be able to maintain the project](https://github.com/InfiniTimeOrg/InfiniLink/commit/58c5caf23d18386e0618948515f7af28dac0b263) and that they would transfer the project to anyone interested to take over it. In the meantime, the Github project was transferred to the [InfiniTime organization on Github](https://github.com/InfiniTimeOrg). We also plan on transferring the app to an Apple developer account managed by Pine64 to ensure that the app will be available on the app store when Xan-m's account expires.

InfiniTime is an open source project. It means that the code is [publicly available](https://github.com/InfiniTimeOrg/InfiniTime) and that anyone is free to do whatever they want with it as long as they comply with the license of the project ([GPLv3](https://github.com/InfiniTimeOrg/InfiniTime/blob/develop/LICENSE)). Therefore a lot of people contribute to the project by creating pull-requests and asking the core-developers to review and merge their contributions into the original project.

However, some changes cannot always be integrated in the project, and for various reasons: they do not fit with the project vision or priorities, developers do not have the time to review them or... the changes consume too much memory! 

I've already mentioned this in the past: the PineTime is based on a tiny hardware that embeds a very limited amount of memory - 512KB of flash and 64KB of RAM. InfiniTime does not fully use the memory yet, but I take great care to avoid hitting the limit as that would make the maintenance of the project very difficult.

In such cases, some developers decide to maintain a fork of InfiniTime with their changes. A fork is basically a copy of the project that they maintain on their own. To this day, InfiniTime counts [584 forks](https://github.com/InfiniTimeOrg/InfiniTime/network/members)! Among these forks, you'll find [Sec42](https://github.com/Sec42)'s [fork](https://github.com/Sec42/InfiniTime/releases) that adds changes to make notifications easier to read by "old" eyes and [Dmlls](https://github.com/dmlls)'s [fork](https://github.com/dmlls/InfiniTime/releases) which adds the Infineat watchface and is very well maintained. These forks are a good thing as they allow developers to make their contributions available to the public even if they cannot be merged in InfiniTime right now, and they provide more choice to the users. Everyone wins!

Speaking of memory usage, I'm currently working on improving the situation by leveraging the additional 4MB of external flash memory available on the PineTime hardware. [My work](https://github.com/InfiniTimeOrg/InfiniTime/issues/321#issuecomment-1133959435) is still in the "proof of concept" state, but shows very good results. The goal here is to store data that needs a lot of space (mainly pictures and fonts) in this external memory to free some space in the internal memory. I've recently demonstrated [a build](https://github.com/InfiniTimeOrg/InfiniTime/pull/1226) with the [G7710](https://github.com/InfiniTimeOrg/InfiniTime/pull/1122) and the [Infineat](https://github.com/InfiniTimeOrg/InfiniTime/pull/1024) watchfaces where pictures and fonts are stored in the external memory. There is a slight impact on the performances and display speed, but it opens the road to many new apps and watchfaces in the future!

<iframe title="Work in progress : test background image and font loading from external flash memory" src="https://video.codingfield.com/videos/embed/d6ccf261-df2e-45cc-b852-b73c23680e8e" allowfullscreen sandbox="allow-same-origin allow-scripts allow-popups" width="560" height="515" frameborder="0"></iframe>

**Testing background image and font loading from external flash memory**

As you can see, the community is still at work on anything related to PineTime! However, don't worry if you notice a small drop in activity - we are just enjoying the summer and taking well-deserved holidays!

Finally, let me remind you that you can purchase the PineTime from the new [PINE64 EU store](https://pine64eu.com/) that opened at the beginning of July!
