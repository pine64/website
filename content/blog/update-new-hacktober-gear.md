---
title: "Update: new hacktober gear"
date: "2020-10-15"
categories: 
  - "community"
  - "cube"
  - "news"
  - "pinecil"
  - "pinephone"
  - "pinetime"
  - "soedge"
tags: 
  - "pinecil"
  - "pinecube"
  - "pinephone"
  - "pinetime"
  - "soedge"
cover: 
  image: "OctoberCommunityUpdate.jpg"
images:
  - "/blog/images/OctoberCommunityUpdate.jpg"
---

![](/blog/images/OctoberCommunityUpdate.jpg)

Let me begin this month’s community update by teasing the November update, in which I’ll talk about the next generation of SoCs and our plans for the future. If you haven’t done so yet, then now is the right time to subscribe to our blog and follow the news on the [PINE64 Telegram news channel](https://t.me/PINE64_News). 

I’ll be mostly focusing on hardware in this month's update, I’ve been out of the software development loop for much of the month due to personal reasons. This, however, gives me an opportunity to talk to you at more length about the PineCube, Pinecil and SOEdge as well as some community-centric things.  

As always, massive thanks to [JF](https://twitter.com/codingfield) for contributing the PineTime section of the update! 

Much has happened in the past month so let's get to it.  

**TL;DR**

- New store and its features; store move to .com domain
- I’ve been working towards setting up an EU store 
- Community-created content for PINE64 Youtube and LBRY channels
- Pinebook Pro and PineTab LCD shortages continue; hopefully panels become available in December
- Manjaro PinePhone CE OS build is finished & sent to factory yesterday
- Manjaro’s build closest to end-user ready yet; ships with Phosh
- Work on PinePhone back-covers adding functionality started
- First two back-covers will add: wireless Qi charging (already works) and NFC
- PinePhone keyboard design green-lit and started; clam-shell design with large battery
- SOEdge modules are ready!
- Chicken-and-the-egg problem, the SOEdge needs Linux devs
- PineCube is available for purchase; software development is coming along 
- PineCube lens selection coming to the Pine Store
- Pinecil firmware is coming together very well 
- Pinecil will ship with a B2 tip, but two packages with four tips each will be available ($24.99 each)
- We created a breakout board for the Pinecil … it is now an SBC (sort of anyways)
- PineTime with InifiniTime FOSS firmware is now available and shipping! 
- PineTime music control in Android with _gadgetbridge_ and playing games on the watch
- PineCom - a small PDA-style device relying on alternative communication protocols
- Addressing the PineCom push-back from the community (thank you for your feedback)

#### Housekeeping

There are a handful of important housekeeping topics to discuss this month. For starters, let’s talk a little about the new Pine Store. We hope that the new store not only improves the browsing experience but also addresses much of the [feedback](https://forum.pine64.org/showthread.php?tid=10670) that we received from our community. Feature-wise, you are now also able to pay using credit cards (as well Apple Pay and similar services) and calculate shipping and import-related costs, such as VAT, for various items. We have also implemented a system to notify customers about DHL’s _Remote Area Surcharge_ (RAS) payments if their geographical location is deemed as ‘remote’ by DHL. Massive thanks to Marek (Gamiee) for getting this working - it was a difficult feature to incorporate. A quick word of caution about the RAS notification feature; our implementation of the RAS notification is based on a location list we received from DHL. The list includes thousands of entries and we cannot guarantee that it will always be up-to-date at all times despite our best attempts. 

![](/blog/images/checkout-1024x706.png)

**Checkout and payment options in the new Pine store**

Seeing as I know someone will ask about this; we are still working towards a cryptocurrency payment arrangement that would work well for us and our community members. We are talking to multiple parties and trying to find some sustainable arrangement - I hope that one can be reached in the coming weeks. 

As many of you have noticed, the Pine Store has also moved to a dedicated .com domain - [pine64.com](http://pine64.com) - from its previous subdomain at _store.pine64.org_. The purpose of moving the store to a commercial domain is to denote its separation from all community-run services and subdomains at [pine64.org](https://www.pine64.org/). We hope that this will help distinguish the two sides of PINE64 - that of a business and a community run project. 

I’ve also been working towards setting up a dedicated European Pine Store for a couple of months. Under normal circumstances the process would be relatively trivial, but unfortunately current travel restrictions are making it difficult to complete all formalities involved with getting this off the ground. Without getting into unnecessary detail - the store will be registered in a different EU country to where I reside, and physical presence is required to complete portions of the paperwork submissions. Given current travel restrictions in Europe, I think it will be a couple of months before I get everything sorted - I’ll make sure you know when it is all ready to go.

Before I head off and talk about another topic, there is one more thing I’d like to mention with regards to the store. Apart from upgrading the store front-end, we also did a lot of work on the store’s backend. You should now reliably receive store order and shipping notifications in your mailbox; if you do not, however, please make sure to reach out to myself, Marek (Gamiee) or Matthew (fire219) in the chats. 

Lastly, I have been in talks with a handful of community content creators for the past couple of months regarding our existing [Youtube](https://www.youtube.com/channel/UCs6A_0Jm21SIvpdKyg9Gmxw) and newly started [LBRY](https://lbry.tv/@PINE64:d?page=1) channels. I have now reached an agreement with [PizzaLovingNerd](https://www.youtube.com/channel/UCmGcm7dhEjS9CIOsOOv8y6w), who will create monthly videos to compliment the written monthly community updates. I also hope to develop a show-and-tell Youtube/ LBRY series - perhaps one that would actively engage with the community and involve the developers. If you’re interested in creating content for the PINE64 Youtube/ LBRY channels and have other ideas, then please make sure to reach out to me in the chats or elsewhere. 

#### Pinebook Pro and PineTab availability status

I feel like a paragraph concerning the Pinebook Pro and PineTab is in order given the frequent questions about pre-order availability. As things stand, we have all the bits and pieces - bodies, mainboards, other electronics, etc - to manufacture PineTabs and Pinebook Pros, but we’re still missing the much needed LCD panels. As I mentioned in [last month’s update](https://www.pine64.org/2020/09/15/september-update-let-it-sink-in/), back-to-school programs run by large companies created a severe LCD shortage on the market. The market, which already suffered from low panel volumes (caused by the COVID-19 pandemic), has now been practically drained of grade-A LCD panels within the target price-range. As I explained last month, purchasing from the open market isn’t an option. Open market LCD panels come without warranty or reliable quality assurance that vendors always offer.

According to some projections LCD panels ought to be available again in December. Granted this projection is accurate, we may see new batches available prior to the Chinese New Year (February 2021). I will, of course, keep you updated on the situation in future community updates.

#### PinePhone

![](/blog/images/Manjarobox.jpg)

**Manjaro CE presentation box design**

The Manjaro PinePhone CE OS image, which will ship with the upcoming PinePhones, was sent to the factory just the other day (congrats Manjaro team!). Personally, I feel that this is the most end-user ready OS image to ship on the PinePhone thus far. This isn’t exactly surprising given that the Manjaro team has had the most time to create an OS image and benefited from the overarching development on the platform. The OS image ships with Phosh and is probably the smoothest experience on the PinePhone to date. Moreover, to my knowledge - and I’ve tested the software extensively - all major features of the phone work with Manjaro. It also features a solid variety of well-tuned applications to get you started, including Firefox, GNOME Maps and Megapixels camera application, just to mention a few. Don’t get me wrong, the software will still require a layer of polish to be considered ‘daily-driver’ worthy by a broader audience, but I have been running it exclusively on my phone for weeks and it has been a great experience.

Before moving onto talking about hardware, let me quickly mention the awesome work Martijn Braam from postmarketOS has been doing with the camera. His _Megapixels_ application now supports both the front and back cameras, a smooth viewfinder (at 720p), manual ISO and shutter user-facing controls, autofocus (!!) as well as various forms of post processing. This application has greatly benefited the community as a whole, including the upcoming Manjaro CE. Frankly speaking, I’ve been blown away by the camera’s performance. Please read [Martijn’s blog](https://blog.brixit.nl/pinephone-camera-pt4/) for more technical details; I am attaching two pictures taken on the Manjaro CE device for you to check out.

![](/blog/images/MainCamPinePhone-scaled-down-768x1024.jpg) ![](/blog/images/SelfiePinePhone-768x1024.jpg)

**No one wanted to pose for pictures, so its my kid's dinosaur (main camera, picture down-scaled) and me (front-facing camera). Higher quality main camera picture [here](https://imgur.com/rxPFr3t)**

I have a handful of exciting hardware-related topics to discuss, including news about back covers with additional functionality and the physical keyboard for the phone. Let's start by talking about the custom back-covers. As we said from the start of the PinePhone project, we’re planning on adding functionality to the phone via custom back-covers that will communicate with the phone via the pogo pins. The first two covers will introduce Qi wireless charging and NFC to the PinePhone. Qi wireless charging already works since it doesn’t require software, but NFC implementations will obviously require software enablement. The Qi charging back-case has been ready to go for [some time](https://www.pine64.org/2020/05/15/may-update-pinetab-pre-orders-pinephone-qi-charging-more/), but as it turned out the coil and electronics couldn’t fit into our current cover design. The back-cover design had to be retooled slightly to accommodate the new functionality - the physical space was increased to accommodate the additional electronics - and you’ll be happy to know that we’ll release the new STL file on the Wiki so you can experiment with creating your own add-ons. This is just the start, we have more ideas for future add-ons which I’ll be sharing with you in the coming months. 

![](/blog/images/qicoil-768x862.jpg)

**Here is the Qi wireless charging coil we'll be using**

I’m also happy to let you all know that 3GB/ 32GB PinePhone mainboards will be available in the Pine Store in November. If you already have a PinePhone and want to upgrade to the higher capacity and RAM variant, you don’t have to buy a new unit - just the mainboard. We also have a little token of appreciation in store for early adopters (Braveheart and UBports CE) owners who wish to upgrade their mainboards, but I won’t spoil the surprise in this post.

Lastly, we have given a hardware vendor the green light to start preparing a prototype of the keyboard for the PinePhone, and the vendor has informed us that they’ll strive to have the prototype ready by the end of this year. We find this schedule for delivering the prototype difficult to achieve, but at the same time we (all of us) are looking forward to being pleasantly surprised if they manage to pull it off. I am including the renders for you to check out below.

![](/blog/images/PinePhoneKeyboardRender.jpg)

**PinePhone keyboard render**

After some consideration we have opted to go with a clamshell design for the keyboard. The PinePhone is large and heavy enough to be unwieldy when held by a thin slab of plastic such as that of a slide-out keyboard. This clamshell design can, however, be folded practically flat so it is comfortably used without placing the device on a surface. The keyboard section also holds a large (probably 5000mAh) battery, which not only more-than-doubles the phone’s stand-by time but also acts as a weighty counterbalance. Many of you will also recognize that we decided to use the keyboard layout we [proposed and discussed](https://www.pine64.org/2020/07/29/invitation-to-play-along/) with the community in August. From a mechanical standpoint, the keyboard clamps onto the phone (for which you need to remove the back-cover) and interfaces with the device using the pogo pins.  

I’m sure this news will get many of you excited, but please keep in mind that presently it is impossible for me to guarantee that this particular plan for the keyboard will pan out and that the vendor will come through on their promises. But I think there is a good chance it will happen, so I decided to share it with you.

#### SOEdge

The SOEdge AI modules and the accompanying model-A baseboards have now been delivered to us from the factory. However, the SOEdge currently suffers from a chicken-and-the-egg problem: there is no Linux software running on the device. This, in turn, means that it cannot be sold to end-users (even enthusiasts). What the SOEdge needs at this point in time is a group of developers keen to lay the foundations for getting the module up and running. I took a look at the [BSP offered by Rockchip](https://github.com/rockchip-linux/rknn-toolkit) and it seems like a good starting point (unless there is already an ongoing mainlining effort I am not aware of).

Consider this a call to action; if you’re interested in working on the SOEdge make sure to reach me in the chats or the [forum](https://forum.pine64.org/) (start a public thread).  

Needless to say, the device has a lot of potential and not only in the realm of AI but also more traditional computational applications. The SOEdge offers fast IO, including PCIe 2x and USB-3.0 as well as Gigabit Ethernet, making it ideal for a variety of high-throughput and low-power applications. Aside from its powerful NPU, the device also features 2GB of PC-2133 RAM and a dual-core cortex A35 running at 1.6Ghz.

![](/blog/images/SOEdge-1024x768.jpg)

**SOEdge socketed in model-A baseboard**

The development model-A baseboard features all key connectors and I/O, including USB 3.0 and PCIe 2x (either PCIe or USB 3.0 can be used at the same time), Gigabit Ethernet, MIPI DSI, MIPI CSI, SDIO (compatible with current WiFi/ BT modules) as well as  touch panel input and CSI. You also get a full GPIO header, RTC, SPK and bootable SD card slot (there is also an eMMC mount on the SOEdge module). As you can see, the range of possibilities the module offers is quite extensive and I trust that a group of interested developers will pick it up.

#### PineCube

In the event you’ve missed it, the PineCube is [now available](https://pine64.com/product-category/pinecube/?v=0446c16e2e66) for purchase in the Pine Store. If you’re interested in helping to get this little FOSS IP camera off the ground, here is your chance. I am told that software progress on the PineCube is coming along well but it's all in very early stages. From a development standpoint, the goal at this point is to build a mainline Linux (Debian) OS image. Marek (Gamiee), who is currently working towards making such an image, is currently waiting for some u-boot patches that will allow the PineCube boot from SD card as well as writing a video encoding library for the mainline kernel. 

![](/blog/images/PineCube-1024x768.jpg)

**The PineCube**

By the time this post goes live the PineCube chat and forum infrastructure should be available, and I highly encourage you to engage with others at this early stage of bringing the PineCube up. I’d also like to point out that the [PineCube Wiki page](https://wiki.pine64.org/index.php?title=PineCube) is now up with some very rudimentary information to get you started. Anyone can create a Wiki account and contribute to any of the existing device subsections; as per usual, it will take a community effort to get this project up and running.

![](/blog/images/PineCubeLenses.jpg)

**PineCube compatible m12 lenses**

We will soon also offer a wider range of m12 mount lenses.  We’ll make sure to provide a wide selection of lenses for a variety of applications, including a long range zoom and a fisheye 185 degree lens. I’m not exactly sure when these will become available in the store, but it shouldn’t be long until you can pick up a set alongside the PineCube itself. 

#### Pinecil

The Pinecil is proceeding well and, thanks to the hard work of Ben Brown on porting the firmware to RISC-V, for the most part operational. The firmware will still need some degree of tuning, but the all features of the soldering iron have now been enabled and are working which means it will be available for purchase soon. Hardware-wise, the molding for the Pinecil is now finished and the pre-production units feel great in the hand. I am attaching a picture and a render below: the picture shows the Pinecil prototype running (powered via USB-C in this particular picture) while the render shows the final look of the iron that we settled on, with a PINE64 blue accent on the rubber grip.  

![](/blog/images/PinecilPrototype.jpg)

**Fully functional Pinecil prototype**

![](/blog/images/PinecilFinalRender.jpg)

**Render showing final look of the Pinecil, with the blue rubber handle**

The Pinecil will ship with a B2 tip, but two additional tip sets will be available for purchase on launch day - each priced at $24.99, the same price as the Pinecil itself. I am attaching a picture of both tip sets below so you can check them out. If you already have a TS100 iron and an accompanying set of tips, then you’ll be happy to learn that your existing tips will work with the Pinecil. 

![](/blog/images/PinecilTipSets-scaled.jpg)

**Set 1 (left) and Set 2 (right) of soldering tips for Pinecil**

Lastly, something admittedly a bit crazy - we have created a Pinecil breakout board which exposes all of the SoCs available pinouts and protocols. To be precise the breakout board exposes ADC/DAC, SPI, UART. SPI, USB and JTAG. The board attaches to the USB-C port on the Pinecil, allowing the device to be fully operational and fully assembled when tinkering. So yes, the breakout board converts the Pinecil into a single board computer of sorts… or, at the very least, a tinkering device. I am sure that many of you will find some type of valid application for this breakout board and come up with innovative applications for the device. I am attaching a picture of Pinecil mainboards and the breakout board below. 

![](/blog/images/Pinecilmainboardandbreakbout.jpg)

**Pinecil mainboard PCB (top) and break-out board PCB (bottom)**

#### PineTime

This month, the PineTime project reached a new milestone - the new PineTime development kit is (finally) [available in the Pine Store](https://pine64.com/product-category/smartwatches/). This new batch of PineTime development kits now ships preloaded with InfiniTime, the very first FOSS firmware to be programmed at the factory into the smartwatch! I've already seen many people have received their new PineTime devkit and quickly began to test InfiniTime, flash new firmwares and even develop new functionalities and projects.

![](/blog/images/PineTimePINE64devices-1024x1024.jpg)

**PineTime running InfiniTime  - picture by [JF](https://twitter.com/codingfield/status/1310320631993561091/photo/2)**

As the maintainer of InfiniTime, I noticed this new crowd of PineTimers by the number of bug [reports, questions, suggestions](https://github.com/JF002/Pinetime/issues) as well as [pull-requests](https://github.com/JF002/Pinetime/pulls) the project received this last couple of weeks. I'm really happy to receive all this feedback from people all around the world, and I am proud that people actually help me build and improve the project I started nearly 1 year ago! I would like to thank anyone who has already contributed to the project, and I'm sure that this is just the beginning of a great journey.

Around the same time as the devkits became available in the store I released a [new version](https://github.com/JF002/Pinetime/releases/tag/0.8.2) of InfiniTime. This version has been tested by many members of the community, so it should be safe to upgrade (OTA via BLE) your development kit. This new version of the firmware brings many improvements and a music control application. That's right, InfiniTime paired with the [new version of Gadgetbridge](https://codeberg.org/Freeyourgadget/Gadgetbridge/src/tag/0.47.2) adds support for the music and playback control on your Android phone directly from the PineTime. I've also heard that even more new features like OTA are in the works thanks to @Avamander.

Avamander is also working on improving the music application of InfiniTime by adding a nice animation, song progression and support for touch gestures. 

**PineTime music control on Android smarphone**

I was also amazed to see people writing games for the PineTime! Here is a Pong game by @Electr0Lyte [https://twitter.com/SravanSenthiln1/status/1312961476580175873?s=20](https://twitter.com/SravanSenthiln1/status/1312961476580175873?s=20) and a breakout game by @TT\_392 [https://www.youtube.com/watch?v=5rt6C1FeglM](https://www.youtube.com/watch?v=5rt6C1FeglM). This last video also introduced you to Lupyuen's new innovation - [the remote pinetime](https://github.com/lupyuen/remote-pinetime-bot). Lup wrote a Telegram bot that allows people who haven't received their devkit yet to flash their firmware into his own PineTime. This development kit is streamed H24 on Youtube: [https://www.youtube.com/watch?v=U4EhPuKqEG8](https://www.youtube.com/watch?v=U4EhPuKqEG8). Crazy idea, but it works!

One last project I would like to highlight this month is the [test framework](https://forum.pine64.org/showthread.php?tid=11711) of @maiden. This test framework will ultimately run automatic test sequences on new versions of the firmwares for the PineTime while measuring the power consumption of the device. This tool will be invaluable to ensure that new versions of our firmware work correctly prior to release.

The PineTime community is literally boiling with activity and new ideas pop out every day, it’s really exciting!

#### PineCom

![](/blog/images/PineCom.jpg)

**Abstract PineCom illustration**

Earlier this month we asked what you’d like to see in a [small PDA-style IoT device](https://forum.pine64.org/showthread.php?tid=11772), which will rely on LoRaWAN, WiFi and other alternative protocols for communication. We envision the device to be small in size - with a 5” or smaller LCD panel - and possibly quite modular. The PineCom would also be based on the same underlying architecture as the PinePhone, sharing many of its core features and making it pin-for-pin software compatible. As the name of the device indicates, the idea behind the PineCom is to explore alternative communication methods, but I can also see it being used for a variety of IoT applications, as a portable media player as well as a _Point Of Sales_ device. I’m sure that you can think of other applications too. 

I also need to note that the idea for the PineCom has been met with a fair bit of push-back from the community. Browsing the comments, those who oppose the introduction of a new device appear to think that it may detract from PinePhone development. There is also another group of people, lobbying for having PineCom’s features implemented into the PinePhone via custom back-covers and the i2c protocol. Let me address both points. The PineCom will not detract from PinePhone development because the new device will be compatible with existing PinePhone OS images. If anything, PineCom may bring new developers into the our ecosystem; but even if not, I cannot see it being a hindrance or draining existing resources. Secondly, having LoRaWAN and other alternative protocols enabled and working in Linux on the PineCom may actually convince us to create custom back-covers with these protocols for the PinePhone. 

At any rate, I am really happy to have received so much feedback regarding this device. We will monitor the thread for weeks and will, most certainly, take all reasonable feedback under advisement. On a personal level, I don’t find the fears grounded in reality, and I’ll do my best to persuade you about it in the months to come.  Ultimately however, if the community decides that the arguments are unconvincing and remains adamantly against the device then we won’t make it.

That's all for this month, make sure to subscribe for some really exciting news the next month!
