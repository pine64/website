---
title: "July Update: biggest update in months!"
date: "2020-07-15"
authors: ["Lukasz Erecinski"]
categories:
  - "cube"
  - "news"
  - "pinebook-pro"
  - "pinecil"
  - "pinephone"
tags: 
  - "pinebook-pro"
  - "pinecil"
  - "pinecube"
  - "pinephone"
  - "postmarketos"
cover:
  image: "/blog/images/PostBanner.jpg"
images:
  - "/blog/images/PostBanner.jpg"
---

![](/blog/images/PostBanner.jpg)

I cannot remember the last time I had this much to report. With so many announcements and highlights, I ran out of time and didn’t cover a handful of topics that happened this month. If I find the time, I’ll make a complimentary post later this month to cover the outstanding topics. Before we get into it, I’d also like to thank [JF](https://twitter.com/codingfield) for his contribution to the text.

The big announcement of the month is that we’re introducing the PinePhone Convergence Package and that postmarketOS Community Edition (CE) pre-orders open today. The Convergence Package features a PinePhone with 3GB of RAM and 32GB of eMMC flash storage as well as a USB-C dock tailored for the PinePhone. 

This month we’re also unveiling the Pinecil RISC-V soldering iron and reintroducing the PineCube (formerly CUBE) FOSS IP camera into our product line.

There’s plenty of ground to cover, so let’s get to it.

**TL;DR for this month** 

- We’re trying out a new shipping arrangement to EU with postmarketOS CE; expect it to benefit end-users in Europe
- We are presently unable to ship any devices to Russia or India (doesn’t apply to SBCs & peripherals)
- PinePhone postmarketOS CE pre-orders open today! 
- Introducing PinePhone Convergence Package with postmarketOS CE featuring 3GB RAM/ 32GB eMMC and a USB-C dock for $199; available alongside regular PinePhone postmarketOS CE for $149
- PinePhone spare battery charger and protective tempered glass are now in PINE Store
- The PinePhone can now achieve 100hrs standby time without modem; over 24hrs with modem enabled (!)
- PinePhone state of software, including postmarketOS, Manjaro, and Mobian
- Pinebook Pro - finally good news from \*BSD community; FreeBSD is coming together
- Lomiri (formerly Unity8) running on Manjaro on Pinebook Pro
- No (OG) Pinebooks being produced right now; we’ll wait for component prices to come down
- Next round of Pinebook Pro pre-orders at the end of July/ beginning of August
- Pinebook Pro dock is being evaluated by developers; it will be a little longer before we show it
- Pinebook -to- Pinebook Pro-esque upgrade kit is finally coming soon  
- PineTime software and development status; working towards an early adopters edition _\[authored by JF\]_
- Pinecil is a TS100 compatible RISC-V soldering iron. Improved device ergonomics and firmware from original TS100 firmware creator Ben Brown; coming late September for $24.99
- PineCube (formerly CUBE) going into production soon, with improved hardware specs; available in 6-8 weeks for ~$24.99
- Personal note: I’ll start getting back to your emails now that I’ve got some spare time.

#### Housekeeping

Let’s start with a handful of shipping notices. With the upcoming postmarketOS CE we’ll introduce a new shipping arrangement for the EU (please see the PinePhone section of this post for details), which we hope will result in significantly reduced shipping costs for end-users. We’re always looking for the best arrangements and new ways to deliver our hardware, and we hope that this route will eventually grow to encompass other devices. We will have more news concerning servicing EU end-users in coming months, so please stay tuned and subscribe to this blog for further updates. On the subject of shipping, we also have bad news for our end-users in Russia and India. We are currently not able to fulfil postmarketOS CE PinePhone nor upcoming Pinebook Pro orders to said destinations since there currently aren’t any available shipping routes for these devices at our disposal. 

In anticipation of someone writing “but I can get product X into Russia/India using service Y”, let me elaborate on the situation a little further. We have been informed that we’re not allowed to ship devices with the encryption capabilities of the PineTab, PinePhone and Pinebook Pro into the Russian Federation. Shipping these devices could (and has multiple times in the past) lead to confiscation of the devices at the border by customs and even to being outright banned or barred from entering the country. There are avenues for us to explore in this regard, however, and we will do so in the coming weeks. Once a suitable shipping option is found, shipping to Russia and India will be reinstated immediately. I’ll make sure you’ll be notified of this as it happens.

Lastly, we will be looking into improving the PINE Store layout and shopping experience in the coming weeks. While we’re considering the store’s potential layout and structure, we’d appreciate hearing your views and ideas on how we can improve its front-end. I deem the comments section of the blog not the best place for this discussion, so I have [opened a thread](https://forum.pine64.org/showthread.php?tid=10670) in the community section of the forum where we can exchange ideas. I am really looking forward to hearing from you.

#### PinePhone

The PinePhone UBports Community Edition campaign has now come to an end. Earlier this month we donated our financial contribution to the UBports Foundation and became listed as one of the [Premium Sponsors](https://ubports.com/foundation/sponsors). We would like to thank the entire UBports community - and especially Marius, Dalton and Ricardo - for their work and cooperation during the past couple of months (Editor’s note: Thank you to PINE64 and the community for making this possible! - Dalton).

I must admit that despite the difficult circumstances that surrounded this campaign - everything from manufacturing to shipping - this has been a valuable exercise for us as a project. We have learnt a lot from the problems we encountered, and as a result of this we will be trying out new shipping strategies as well as altering how we tackle shipping periods. As I already mentioned earlier in this blog entry, we are setting up a warehouse in the EU (Poland), which will service European customers. This warehouse will, at least presently, only be used for PinePhones. If this setup proves to be as convenient and beneficial to the community as we think, it may end up hosting our remaining devices in the future. Using this new shipping arrangement, EU customers will not be asked to pay import tax, but rather the PinePhone price, $20 shipping charge as well as local VAT. Please note that this is a trial - something we’re testing out with this Community Edition production-run - and we may choose to fall back on previously established shipping arrangements in the future. Shipping arrangements for users in the US and rest of the world remain unchanged. 

Before moving to this month’s big announcements, I’d like to thank all of you for your patience - I know that it has been a long wait for some of you (and that many of you are still waiting). If you are just getting your UBports CE PinePhone now, then please consider joining the dedicated [Ubuntu Touch on PinePhone telegram group](https://t.me/utonpine).

![](/blog/images/photo_2020-06-30_23-29-43-1024x466.jpg) ![](/blog/images/photo_2020-06-30_23-29-48.jpg)

**Cleverly reworked box for the PinePhone Convergence Package**

**Pre-orders for postmarketOS CE open today** and I am happy to announce that alongside the standard PinePhone CE hardware configuration priced at $149, **we** **are launching the PinePhone Convergence Package**. The PinePhone Convergence Package features a PinePhone with 3GB of RAM and 32GB of eMMC storage as well as a compatible USB-C dock. The dock that is included with the Convergence Package is capable of delivering power to the phone via USB-C power-in (3A 5V), outputting digital video via HDMI, 10/100 Ethernet connectivity and two USB 2.0 ports (for e.g. external storage / mouse and keyboard). The spec bump and inclusion of the dock comes at the price of **$199**. We presently do not know whether the Convergence Package will become a permanent option, something we’ll do on occasion or simply a one-off (although the last option is unlikely). It obviously largely depends on people's response to this PinePhone variant and how much demand we see for it.

Both the regular (2GB RAM/16GB eMMC) and Convergence Package (3GB RAM/32GB eMMC) postmarketOS CE PinePhone versions will ship with a mainboard designated 1.2a. The ‘a’ in the mainboard’s designation refers to a minor alteration, allowing for better power delivery negotiation (which will result in improved charging performance under some circumstances), as well as the possibility to connect USB devices to the phone and output video to an external monitor.

**Head over to the PINE Store to** [**pre-order your postmarketOS CE PinePhone**](https://pine64.com/product-category/pinephone/).

https://www.youtube.com/watch?v=yBeza4UNOm8

**PinePhone running postmarketOS docked by Martijn Braam**

While we’re discussing this topic, let me tackle the elephant in the room and acknowledge that a design flaw in PCBA rev. 1.1 and 1.2 prevents this functionality (please see relevant [documentation related to CC pin](https://wiki.pine64.org/wiki/PinePhone_v1.1_-_Braveheart#USB-C_CC_pins_are_pulled_to_the_GND_by_AW3512_.28VCONN_switches.29_when_VCONN_is_off)) on Braveheart and UBports CE phones. This issue was originally identified, and the fix for it was found, by [Ondřej (megi) Jirman](https://github.com/megous). His work on the  anx7688 makes USB-C features, such as PD charging, video output or other functions of the docking station work. Thankfully the fix to the problem - the removal of two small components from the PCBA - is relatively simple to perform for someone with good soldering skills. At the same time I recognize that many community members, myself included, are not capable of completing this operation. To this end, we will set up a chain of local (in your geographic area) workshops, makerspaces or individual technicians capable of performing this fix, so you can send your 1.1 / 1.2 phone to them to complete the repair. 

https://www.youtube.com/watch?v=xf8OJtjNWUM&feature=youtu.be

**Quick Look at the required CC fix on PCBA 1.1 / 1.2. By Mozzwald**

When we sold Braveheart PinePhones we made a promise to the early adopters that we won’t leave them behind, so I’d like to extend the offer for fixing the CC pin issue to all Braveheart owners too. More information will follow about the process later this month - I have to figure out the smartest way to set up the infrastructure about it first. In my dedicated post on this topic, there will be a sign-up for individuals and shops who would like to make their services available. So, if you’re handy with a soldering iron then please subscribe to the blog and watch for a post later this month.   

In other hardware news, there are now two new PinePhone items available in the PINE Store. We have a tempered glass screen protector (it's very good, I use it on my phone) and an external PinePhone battery charger. The charger makes it possible for you to charge a PinePhone battery externally, so you do not need to disassemble your phone to charge a spare battery unit. Both items come in at $4.99 and I suggest you at least pick up the glass screen protector alongside one of the phone cases for your phone. Both items can be found in the [PinePhone spare parts section](https://pine64.com/product-category/pinephone-spare-parts/). One last little bit of hardware news I’d like to let you know about is that now, with access to vendors in China becoming easier, we have resumed exploring the creation of an external keyboard for the PinePhone. To be precise, we have approached a vendor and began exploring our options for a slide-out keyboard akin to those used on the Nokia N900. If the talks come to fruition then I’ll make sure to ask for your opinions - as I did with the Pinebook Pro - regarding the keyboard layout and features (no, there won’t be multiple layouts).

![](/blog/images/chargerandglass-1024x512.jpg)

**Battery charger and tempered glass protector**

I have already used up all the time and space reserved for the PinePhone section in this blog, but I feel strongly compelled to cover some software updates. For starters, I know many of you are curious about the software status of the postmarketOS build that will ship with the postmarketOS CE PinePhone. The build will include a phenomenal out-of-the-box user setup and installer, which will not only allow you to fully encrypt your eMMC storage but also enable services, such as SSH. Our friends from postmarketOS have posted a very detailed post [detailing the state of software](https://postmarketos.org/blog/2020/07/15/pinephone-ce-preorder/). I strongly suggest to head over to their blog and have a read. 

![_DSC0007](/blog/images/DSC0007-682x1024.jpg)

![_DSC0008](/blog/images/DSC0008-682x1024.jpg)

![_DSC0009](/blog/images/DSC0009-682x1024.jpg)

![_DSC0010](/blog/images/DSC0010-682x1024.jpg)

![_DSC0011](/blog/images/DSC0011-682x1024.jpg)

![_DSC0012](/blog/images/DSC0012-682x1024.jpg)

![_DSC0013](/blog/images/DSC0013-682x1024.jpg)

![_DSC0014](/blog/images/DSC0014-682x1024.jpg)

![_DSC0018](/blog/images/DSC0018-682x1024.jpg)

Previous Next

**postmarketOS initial user setup. By Martijn Braam**

The other big software news of the month concerns the amazing work of [Samuel Holland](https://github.com/smaeul) on [Crust](https://github.com/crust-firmware/crust) advanced power management; the PinePhone is now able to idle for ~100hrs (that's not a typo, I wrote 100) using as little as 110mW in deep sleep. This is, of course, with the modem switched off. With the modem ON, you can expect the PinePhone to achieve an idle run-time of approximately 24hrs, which we feel brings the device firmly into the realm of what we’d consider a daily-driver smartphone being capable of. 

The second bit of software news I’d like to cover is Mobian’s implementation of camera functionality on the PinePhone. This implementation builds on work by [Ondřej (megi) Jirman](https://github.com/megous), who has been working on both the ov5640 rear and gc2145 front cameras.  For those of you who do not know, [Mobian](https://twitter.com/MobianLinux) is a dedicated Debian distribution for the PinePhone which I happen to be a fan of. The camera implementation is rather slow and the photos aren’t the best quality, but what is important is that we’ve seen this goal being achieved in a relatively short period of time. Somewhat noteworthily, I’d also like to note that I’ve had no problems using GPS on Mobian, and even did some navigating on foot with phone-in-hand finding my desired destinations and best routes. I’m really impressed.

![](/blog/images/cameramobian-1024x768.jpeg)

**Camera now works on Mobian**

Lastly, I want to give a shout-out to the Manjaro team and their work on the PinePhone over this past month. Manjaro are such an integral part of our community and one of the main driving forces behind end-user facing development. That said, perhaps because of their dedication to the Pinebook Pro hardware and the time they put into it, their Alpha OS images for the PinePhone were lacking in comparison to some of the dedicated cutting-edge distributions. This, however, is a thing of the past. It appears Manjaro have now settled on Phosh as their default UI (as opposed to Plasma Mobile) and achieved a lot of software parity with other distributions. Their most recent OS image, at the time of writing, has LTE functionality, places phone calls, has the newest Phosh features (including auto-scaling) and even apparently the newly released Crust power management improvements. I know there are many fans of Manjaro in the community, so I suggest you give [their most recent pre-release](https://osdn.net/projects/manjaro-arm/storage/pinephone/phosh/) a go.

#### Pinebook Pro

We know that many of you are waiting for the next Pinebook Pro batch to open. I currently cannot offer you a precise date for when the next batch will become available, but we’re working towards starting pre-orders at the end of this month. The next production run will be produced by a new factory, which we are still in talks with. Therefore, it’s taking a little longer than usual. Regardless, we’re set to start producing Pinebook Pros in August, so you will not have to wait for much longer to get into the queue for your unit.

The Pinebook Pro has seen quite a few software developments over the past month. For starters, we finally have some progress coming from the \*BSD communities. Although the Pinebook Pro has already been shown running \*BSD months ago - and NetBSD has been available for install for some time - there haven’t been any guides or tutorials on how to get Open or FreeBSD working until now. In fact, very little information about Open and FreeBSD has been made available on our forum or Wiki. I believe this is about to change, however, as [nrgmilk](https://twitter.com/nrgmilk_) - a FreeBSD developer (who also [booted FreeBSD on the PinePhone](https://dmesgd.nycbug.org/index.cgi?do=view&id=5574)!!!!) - tweeted that FreeBSD 13.0 now boots on the Pinebook Pro with LCD output. Just a few days later, [Vincent Milum Jr. shared information](https://twitter.com/DarkainMX/status/1282764108060717056/photo/1) that he successfully implemented big.LITTLE support for the Pinebook Pro on FreeBSD 13.0. I have been told that while there is still a lot of work to be done on FreeBSD, and indeed all \*BSDs, the movement we saw this month may be the breaking point which will propel work on our platform forward.

![](/blog/images/fbsd-1024x801.jpeg)

**FreeBSD booted on Pinebook Pro by [nrgymilk](https://twitter.com/nrgmilk_/status/1281268985816735747/photo/2)**

In other software news, we saw Manjaro booted with Lomiri (formerly Unity8) on the Pinebook Pro. While this is fun to see from a technological standpoint, I am mostly glad to see PINE64 as a platform facilitating the growth and cooperation of projects. Ubuntu Touch and Manjaro are fairly distant relatives of the Linux family tree, and yet they found a common (and innovative) ground to work on within the premises of our community. I am told that you can already install Lomiri alongside KDE Plasma on the Pinebook Pro if you [switch to the unstable repos](https://forum.manjaro.org/t/another-mirror-transition-manual-intervention-required/132302).

![](/blog/images/lomirionmanjaro-1024x604.jpeg)

**Lomiri on Manjaro via [Manjaro Linux](https://twitter.com/ManjaroLinux/status/1282468360358432768/photo/1)**

This month we’ve also seen the first proper graphical U-Boot implementation on the Pinebook Pro thanks to the work of [Samuel Dionne-Riel](https://github.com/samueldr) from NixOS. Samuel writes that this version of U-Boot still has some issues with booting the most current mainline kernels (5.6+) - including Manjaro’s Pinebook Pro kernel (5.7) - but this is surely something that can and will be fixed in nearby future. This is an important step in Pinebook Pro software evolution, as it makes booting and installing alternative OSes from SD, USB 2.0, USB 3.0 and NVMe trivial. I am including Samuel’s quick video showcasing the U-Boot video init working below. 

https://www.youtube.com/watch?v=rdosT2yyA4g

**U-Boot visual output via [Samuel Dionne-Riel](https://www.youtube.com/channel/UCrMUS_fve7Fpj1DBXJTNhww)**

We have sent the Pinebook Pro dock to a handful of partner project developers for evaluation. The process of enabling all of the dock’s functionality on the Pinebook Pro is ongoing, and we’re still missing video output implementation. We also want to redesign some minor bits and pieces before showing it off, so you’ll need to wait a little longer before I post a picture of a prototype we’re happy showing off publicly. I also have some news regarding the redesigned OG Pinebook. At present component prices - especially prices of LCD displays - the BOM cost of the Pinebook significantly exceeds our asking price. In other words, we’d have to significantly subsidize it, which is not something we’re willing to do with all the cost-inducing activities we engage in. Once the post-COVID19 market stabilizes and prices come down, I assure you that we will resume production of the Pinebook. 

Finishing on a positive note, we’re now moving forward with the OG Pinebook-to-Pinebook Pro-esque upgrade. The upgrade will require you to be moderately handy with a screwdriver and the command line. It involves removing the A64 board, applying the heat-dissipation material to the case bottom and lastly installing the RK3399 mainboard in the chassis. On the software side, you will have to flash new firmware to your keyboard and trackpad (similarly to how it is [done on the Pinebook Pro](https://wiki.pine64.org/wiki/Pinebook_Pro#Keyboard)). I’d also like to make you aware that thermal performance of the upgraded OG Pinebook - even when using a graphene layer - will be poorer than the Pinebook Pro. That said, this doesn’t entail that the thermals are bad, and kernel 5.7 and allegedly also the upcoming 5.8, improve the RK3399’s thermal profiles, so you don’t have to worry about heat-related issues under regular load. [Here](http://ix.io/2rGo) is a thermal test using the graphene heat-pad used in an upgraded Pinebook; please disregard the 18\*C read-out and focus on the core frequencies - all you need to know is that the SOC throttles at 72\*C. We aim to have the upgrade kit available in a few weeks time in the PINE Store. 

![](/blog/images/photo_2020-07-15_13-48-35-1024x766.jpg)

**OG pinebook with the upgrade installed**

#### PineTime \[****_authored by_** [**_JF_**](https://twitter.com/codingfield)**\] 

Here is the latest news from the Pinetime community!

First, a big announcement: PINE64 has decided to move towards an early adopter edition of the PineTime, and I'm really excited that the community chose [my project](https://github.com/JF002/Pinetime) as the first FOSS firmware to be flashed at the factory for this early adopter edition! Until now, the Pinetime dev kits were programmed at the factory with what we call the stock firmware - it implements most of the features of the watch but it is closed source. Moreover, the flash memory is read-protected to prevent anyone from reading the binary file from the memory.

When this early adopter edition is available, you'll enjoy the result of months of work by the PineTime community (I'm not the only one working on this firmware, but I still have to find a better name for it...), and you'll be able to hack, debug and flash your watch more easily than before because you won't have to disable the memory protection.

The firmware is still under development but it already integrates basic features like displaying the time, synchronizing the date and time with a companion application on a smartphone, and receiving notifications. Right now we are in the process of testing and debugging this firmware as much as we can, and everyone is welcome to come and help us in this exciting task!

Another great achievement for the project is the development of Over The Air (OTA) update capability. Not only are we now able to update the firmware running on the Pinetime over BLE, but we can also switch from one firmware to another! We've successfully ran a demo showing an update from my firmware to [Lup Yuen](https://twitter.com/MisterTechBlog)'s.The OTA feature is still experimental, but it gives really promising results!

https://www.youtube.com/watch?v=tFm\_cGP3AHw&feature=youtu.be

**PineTime OTA update via Bluetooth**

In a previous community update, Lukasz announced that Amazfish - a companion app running on SailfishOS and on the PinePhone - was able to communicate with the PineTime. Since then, Gadgetbridge (Android) joined the team. And, last but not least, Lup is also working on a companion app and one of his goals is to make it run on the Pinephone.

https://www.youtube.com/watch?v=myMUNepyB5I&feature=youtu.be

**PineTime receiving notifications via Gadgetbridge**

What else happened in the community? A lot of work has been done on the heart-rate sensor and the accelerometer and power consumption, with very good results from ATCWatch. I've seen interesting discussions about the design of a dev cradle that would make it easier to connect the pinetime to the SWD debugger. There are also a lot of people interested in Python development thanks to WaspOS, and the community keeps on welcoming new developers that are excited to learn and work on Pinetime.

#### Pinecil

Let me start by thanking all those who played along last month and took a shot at my riddle. I must admit I was quite surprised how quickly people correctly identified what the Pinecil is. I was also blown away by the accuracy with which the clues were deciphered. Next time I’ll know to make my riddles more cryptic and difficult to decipher. Before we proceed to talk about the device itself, let me just list the names of the three winners (first to correctly identify device type; first to accurately identify SOC type; first to correctly identify all clues). If your name/ handle is on this list then please email me directly ([l.erecinski@pine64.org](mailto:l.erecinski@pine64.org)) using the email registered on this blog. The first three production Pinecils are going to: 

- Andrew Stoehr 
- Jonas
- Ignas Kiela

The Pinecil is a RISC-V based soldering iron - it is inspired and compatible with the widely acclaimed TS100, which is used by tinkerers and makers worldwide. The Pinecil maintains compatibility with TS100 tips and delivers performance identical to its muse, but at a community friendly price of $24.99. Having spoken to, and gathered feedback from, people who are experts in the field, we have made a handful of improvements to the general design and functionality of the soldering iron. In terms of ergonomics, compared to the original TS100 design, the Pinecil is more comfortable to hold and features a grippy rubberised texture where you place your fingers. It is also slightly longer and can be powered via either USB-C or a barrel jack. This makes the soldering iron more versatile, especially if you intend to use it for in-field repairs. The USB-C connection also includes embedded UART, i2c, SPI, and USB signals for ease of development. We know some of you want to play Tetris on your soldering irons … for everyone else, yes, it's actually a thing. Speaking more seriously however, this means you can use the Pinecil as a platform to create something completely different based on this platform, such as a drill or a multimeter.

![photo_2020-07-15_13-49-26](/blog/images/photo_2020-07-15_13-49-26.jpg)

![photo_2020-07-15_13-49-21](/blog/images/photo_2020-07-15_13-49-21.jpg)

![photo_2020-07-15_13-49-16](/blog/images/photo_2020-07-15_13-49-16-768x1024.jpg)

![photo_2020-07-15_13-49-13](/blog/images/photo_2020-07-15_13-49-13-768x1024.jpg)

![photo_2020-07-15_13-49-09](/blog/images/photo_2020-07-15_13-49-09-768x1024.jpg)

![photo_2020-07-15_13-49-06](/blog/images/photo_2020-07-15_13-49-06-768x1024.jpg)

Previous Next

**Pinecil renders and mockup**

Obviously the one crucial bit of having the Pinecil actually functional is having software support for the device. This effectively means porting an existing firmware to the RISC-V platform. Thankfully we’ve been able to interest [Ben Brown](https://twitter.com/RalimTek) - the person behind [the original TS100 firmware](https://github.com/Ralim/ts100) - to take a look at the Pinecil. Sending him a prototype just a little over a month ago, all we hoped for was for him to take a look at it and evaluate the design's feasibility. Suffice to say Ben exceeded our expectations by practically porting all essential functions to RISC-V, thereby making the Pinecil functional. 

As of today, the following is working: 

-  PWM tip drive
-  OLED
-  Accelerometer (ish - needs work somewhere)
-  FreeRTOS
-  Basics of all of the code

Still needs work:

- Tune PWM timings
- FLASH for saving settings
- DMA for I2C (to make screen updates smoother)

![](/blog/images/photo_2020-07-15_13-48-53-1024x437.jpg)

**Pinecil hardware running (prototype)**

We hope that you guys are as excited about the Pinecil as we are. We are currently aiming to make the Pinecil available for purchase sometime in the next 3 months. I will make sure to keep you up-to-date on how the project is progressing until then.

#### PineCube

This will likely come as a bit of a surprise to many of you, but production of the PineCube (originally CUBE) open source IP camera will be starting soon. Some of you may recognise this project as it has been well over a year in the making - we first announced it at FOSDEM 2019. The thing that originally held the PineCube back was a lack of camera integration in the software. Other projects took priority and, eventually, the project was shelved until we had the time and free resources to tackle it again. With all major disasters now behind us for this year (\*knocks on wood 3 times\*), and with all the big devices shipping, we feel the time has come to revisit the much anticipated PineCube.

The PineCube is a compact and completely custom built IP camera that runs mainline Linux. It features an m12 mount, which accommodates various lenses for different use-cases (wide-angle, zoom, fisheye, etc.,), and it comes equipped with IR LEDs for night vision. The small device also bundles a microphone, GPIO, USB 2.0, 10/100 Ethernet, Bluetooth and WiFi. It's worth mentioning that the PineCube can be passively powered over Ethernet. All these features allow for a high degree of versatility, making the PineCube suitable for a wide array of use-cases, ranging from a baby or security camera to a drone or robot camera.

![photo_2020-07-15_13-48-28](/blog/images/photo_2020-07-15_13-48-28.jpg)

![photo_2020-07-15_13-48-26](/blog/images/photo_2020-07-15_13-48-26.jpg)

![photo_2020-07-15_13-48-24](/blog/images/photo_2020-07-15_13-48-24.jpg)

![photo_2020-07-15_13-48-21](/blog/images/photo_2020-07-15_13-48-21.jpg)

Previous Next

**A look at the new PineCube**

Since its original announcement in 2019, a number of changes have been made to PineCube’s core hardware. The original camera module has been switched out for the OV5640 5MPixel sensor used in the PinePhone and PineTab. Progress made on the OV5640 on the big devices will hence directly translate to the PineCube. The IR LED array has also been altered to allow for better and further-reaching night vision. Perhaps most importantly, however, the SoC has been upgraded to the S3 (up from S3L), which is paired with 128MB of DDR2 RAM. The upgraded RAM as well as the Cortex-A9 running at up-to 1Ghz make for quite a powerful platform. 

In the coming weeks I’ll be reaching out to developers and project maintainers to get early PineCube units into their hands. We have commissioned the factory to start production and been informed that the lead-time is approximately 6-8 weeks. We expect to be able to offer the PineCube for $24.99.Let me know if you’re planning to get a PineCube and what you’ll use it for in the comments section. I expect to have more updates for you about this project in a month’s time. 

#### Personal note

This has been a busy period for us - and I’ve also been working on my own PINE64-related project that I’ll be unveiling soon (shameless plug) - and my inbox is literally filled with queries from community members, media and potential partner projects. I’d like to apologize to you all for being so unresponsive and at the same time promise to start going through the pile of correspondence starting today. 

That concludes this month’s update - I am looking forward to your comments!
