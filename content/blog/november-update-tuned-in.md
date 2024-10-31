---
title: "November Update: Tune(d) in"
date: "2022-11-15"
authors: ["Lukasz Erecinski"]
categories: 
  - "community"
  - "ox64"
  - "pinebuds"
  - "pinetime"
  - "star64"
tags: 
  - "community"
  - "ox64"
  - "pinebuds"
  - "pinetime"
  - "star64"
cover: 
  image: "November-Update-final-1024x576.jpg"
images:
  - "/blog/images/November-Update-final-1024x576.jpg"
---

![](/blog/images/November-Update-final-1024x576.jpg)

We’ve got three key hardware availability announcements this month: for the PineBuds Pro, the Ox64 and Star64, all of which ought to be available in the coming weeks. However, reading this update I’d like you to keep in mind that Chinese factories and logistics are currently experiencing significant restrictions due to the zero-COVID policy. This means that some of the predicted availability dates may change. That aside, we’ve got a great update for you this month, so tune in and let’s get to it. 

You can watch the synopsis of this month’s community update on YouTube (embedded below) as well as on [Odysee](https://odysee.com/@PINE64:a) and [PeerTube](https://tilvids.com/accounts/pine64tilvids/video-channels). To stay up-to-date with PINE64 news make sure to subscribe to this blog (subscription widget at the bottom of the webpage), follow the [PINE64 Telegram News channel](https://t.me/PINE64_News), the [announcements channel in Discord](https://discord.gg/pine64) as well as our [Twitter](https://twitter.com/thepine64) and [Mastodon](https://fosstodon.org/@PINE64).

I’d like to thank [Alex](https://twitter.com/AlexRob12252696) (clover), [Gamiee](https://twitter.com/gamelaster), [Danct12](https://twitter.com/RealDanct12), [mothenjoyer69](https://github.com/mothenjoyer69) and [PizzaLovingNerd](https://www.youtube.com/channel/UCmGcm7dhEjS9CIOsOOv8y6w) for their contributions to this community update.

N.B. Comments on the blog post need to be in English and follow our [Community Rules and Code of Conduct](https://forum.pine64.org/showthread.php?tid=13209).

{{< youtube id="Qr97PEaldts" >}}

**Synopsis in video format**

**TL;DR**

- Housekeeping
    - Community Q&A November 25th 20:00 UTC; your chance to ask us questions live in the chat 
    - We’re reworking the main PINE64 website to better reflect the community aspect of the project; we can’t til you see it
    - PINE64 EU restock of most hardware; Pinecil V2 available on Nov. 14, 19, 24, 29 an in December
- Newsflash
    - Newsflash - new segment of the update focusing on shorter stories focusing on community projects, software development and smaller announcements
    - Pinecil mod adds LED lights powered from the iron
    - A DIY LiPo battery pack for the Pinecil (V2)
    - An awesome PinePhone (Pro) keyboard case adds RGB backlight to the keyboard
    - Roshambo retro-game console case with matching controllers and carts available in Pine Store soon
    - PineDio LoRa gateway will be available in the Pine Store soon; already has a feature complete OS
    - DSI LCD output works on the Quartz64
    - An article by dsimic about the Pinebook Pro
- PineBuds Pro
    - Available this month for $69 \[last min edit - available in Pine Store Dec 2nd\]
    - PineBuds Pro Wiki is being built up with resources - you are welcome and invited to contribute
    - Will ‘just work’ for people people who want wireless IEMs; world of hacking opportunities for tinkerers - UART exposes both buds
    - 3 Pieces of software: closed firmware, open firmware and open SDK; Ben (Ralim) working on Linux flashing tool - available in ‘few weeks’ 
    - Extensive tuning of the hardware for sound quality - favorable performance compared against competing products; Ben impressed by the buds 
- Ox64
    - A lot of excitement for the Ox64 in the community
    - Already in production and we expect to be delivered soon; in-store availability very soon, perhaps this month
    - Two versions - $6 and $8
    - Linux booted on the Ox64 by Marek 
    - Add-on boards planned allowing connecting camera, LCD, audio out and Ethernet
- Star64
    - Available soon, likely in December before next community update 
    - Two hardware configurations: 4GB and 8GB of RAM for $69.95 and $89.95 respectively
    - Linux at a good starting point with solid early support of most core features of the SoC
    - Expect support announcements for the Star64 soon after the board launches 
- PineTime
    - InfiniTime 1.11 released; read the dedicated post if you missed it
    - Resource package containing data is needed to enable the 2 new watch faces in InfiniTime
    - Currently supported companion apps that can upload resource packages are Amazfish and ITD
    - Devs already taking advantage of the new InfiniTime feature - pull request for new watch face and a gallery application to display text & QR codes

## Housekeeping

Let me begin by reminding you that we’re holding the community Q&A this month, November 25 at 20:00 UTC. This is your chance to ask us questions live in [IRC](https://www.pine64.org/web-irc/), Matrix, [Telegram](https://t.me/pine64QA) and [Discord](https://discord.gg/pine64). We’ll be streaming the Q&A session on Youtube, Peertube as well as on the Discord live stage. We usually issue a reminder via social media and in the chats some 15 minutes prior to the event starting. The Q&A takes an hour and we do our best to answer all incoming questions during this time. Following this, however, we usually hang out in the voice chat and keep answering questions over a beverage for another hour - we encourage you to join in. In case you won’t be able to make it, the Q&A sessions are recorded and uploaded in an unedited state to [YouTube](https://www.youtube.com/c/PINE64inc), [Odysee](https://odysee.com/@PINE64:a) and [PeerTube](https://tilvids.com/accounts/pine64tilvids/video-channels). I hope to see many of you there. 

You may have noticed that the PINE64 community website hasn’t received an update since early in the year. There is a reason for this, namely we’re working on a complete redesign. And this is a deeper-going redesign than just a page overhaul - we’re working towards separating out, and setting boundaries for, the PINE64 community and the Pine Store’s competences. To this end the .org website will now focus on the community aspects - the individual projects, this blog, the PineTalk podcast, in-person meetups, virtual hang-outs and everything else you can think of that is directly related to the community. In turn, anything and everything related to PINE64 hardware will be moved to the Pine Store’s website, which too will be receiving an overhaul at some point later in the year. We’re still working out the details but the new site is already starting to take shape - we can’t wait to show it with you.  

![](/blog/images/Restock-November-768x432.jpg)

**Pinecil stock will regularly be added throughout November and December**

[PINE64 EU](https://pine64eu.com) is having a full restock this week, with PinePhone, PinePhone Pro, Pinebook Pro PinePower, PineTime, the Pinecil V2 and various accessories available again. The reason why it took longer to restock than in the previous months is related to changes in the customs process - more specifically, the paperwork related to the Low Voltage Directive and Radio Equipment Directive is now more complex. I’ll compensate for this in the future to avoid periods where multiple items are out of stock. The good news is that the store’s stock, bar the Pinecil, should last until Christmas. As for the Pinecil, the first sub-batch will be available immediately on the day of the restock (it is difficult to provide an exact date as I am writing well in advance, but likely on November 15th) following which additional stock will be added on the following dates: November 19, November 24,  November 29, December 4 and December 9 

## Newsflash 

**_Foreword:_** _This is a new section of the community update and one I’m particularly happy about. Newsflash is effectively a quick descriptive summary of things happening in the project - things which would otherwise not get exposure on the monthly blog. These are often developments which are either too small to warrant their individual section, simply do not fit an existing part of the update, or are not a natural fit for housekeeping. Until now, omission of such news was effectively dictated by the scope and time-constraints of the monthly update. Writing the update takes approximately 5 evenings from start to finish, and this is all the time that can realistically be allocated to the writing process. It is simply impossible to report on everything in the PINE64 realm during such a short time span. As a result, many cool projects and information pertinent to the community was lost in the past. The contents of Newsflash will range from cool community projects and interesting software developments to small announcements by the Pine Store or partner projects. On occasion, I may also include commercial products designed for PINE64 hardware if I find them particularly interesting (as I did this month). Anything goes really, and there is no strict structure or order to this section. I should also mention that we’re really happy to accept contributions to this section - all it takes are a few short lines about what you want to report on and links to further reading. Please ping the mods to have the content spotted and delivered to Marek or me_

Community member Andrew, going by the handle [RuShan](https://twitter.com/RuShan_EE) on Twitter and @ahall#7894 on Discord, created a light attachment for the Pinecil V2 allowing you to work on projects in dim environments. The ring attachment is fitted at the base of the tip’s shaft where it meets the body of the iron. The ring features two little LEDs which are powered directly from the Pinecil V2 - more specifically from the 4.6V source on the PCB. It looks like a really fun project that could prove quite useful to many in the community - especially those who sometimes use their iron on-the-go. Andrew writes that the light will work with the V1 and V2, albeit the implementation differs on both models. If you want to make this modification yourself then head over to [Andrew’s GitHub](https://github.com/Herushan/Pinecil_LED_Ring) and download the KiCad file. Be warned, however, this voids your warranty. Andrew wrote a very detailed article about the process behind creating this mod, which I am [linking here](https://files.pine64.org/blog/Pinecil_LED_Ring_writeup.pdf) and I encourage you to have a read.

![](/blog/images/lights1-1.png) ![](/blog/images/lights2.png)

**Could be used as a flashlight in a pinch ;) - images via [RuShan](https://twitter.com/RuShan_EE)**

A Pinecil accessory I came across and think is pretty cool is a dedicated external DIY battery, the components for which are detailed and available in a [small online store](https://notyouraverageshop.com/products/pinecil-battery-pack). What I like about this battery pack, aside from the 4 cell 14.8V LiPo 1300mAh battery with a high discharge-rate, is the custom designed holder for the Pinecil for when you travel. I don’t really have much more to say about this one as it is what it is - a DIY battery - but I find the execution and compact size of this dedicated Pinecil battery rather nifty.

![](/blog/images/Pinecil-LiPo-battery-pack-from-not-your-average-store-768x576.jpg)

**Pretty cool little battery pack via - [Not Your Average Shop](https://notyouraverageshop.com/products/pinecil-battery-pack)**

Another mod that has completely blown my mind is a custom PCB for the PinePhone (Pro)’s keyboard case. This mod comes from Adam Honse, perhaps better known to some of you as [CalcProgrammer1](https://github.com/CalcProgrammer1). In short, Adam transformed the keyboard case into a per-key RGB backlit keyboard with [OpenRGB](https://openrgb.org/) compatibility. I must admit that every aspect of this modification is downright awesome - indeed, this may very well be one of the coolest PINE64 hardware hacks I’ve seen to date. It is an extensive modification which requires a new PCB and will likely need multiple parts to be replaced; I should mention that this is an in-progress project, at least from the looks of it. I am linking a video in which CalcProgrammer offers detailed information about the modification - including the custom PCB - and discusses some of the design process. I strongly encourage you to watch this one. More information can be found by following [this link](https://gitlab.com/CalcProgrammer1/PinePhone-Keyboard-RGB).

{{< youtube id="9DGIwjaXMeI" >}}

**A comprehensive overview of the mod by its creator - [by CalcProgrammer1](https://www.youtube.com/channel/UCggoDHmJCZ5j9OIdRCxfI9A?feature=emb_ch_name_ex)**

The Roshambo retro-game console case capable of housing PINE64 SBCs will be making its appearance in the Pine Store in the coming weeks. If you’re into retrogaming, then the Roshambo case features fully functional on/ off and reset switches, a SATA disc connector, and IO pass-through. You can also pick up a pair or matching controllers and a 128GB SSD that imitates a cart. 

![](/blog/images/Roshambo-01_large.webp) ![](/blog/images/roshambo-02.jpg)

**I can attest that these SSD carts and the controllers are really cool**

The PineDio product-range has been long in development and pushed back on more than two occasions for a variety of internal and external reasons. I am therefore glad to announce that the first and arguably most important part of the PineDio ecosystem will be available in the Pine Store this week. The PineDio gateway will be available later this month and is now fully supported by a custom Armbian-based OS. The PineDio Gateway is based on the Pine A64 LTS V2 and a RAK5146 from RAK Wireless and the documentation for the gateway on [our Wiki](https://wiki.pine64.org/wiki/Pinedio) is already very extensive. You can also expect other PineDio hardware, such as the USB adapter with CH341 chip, to follow soon. To learn more about PineDio hardware I suggest you read the [dedicated post I wrote](https://www.pine64.org/2021/05/06/lets-make-mirakles-happen/) about it last year.

I don’t have a dedicated section on the Quartz64 this month (and for good reason, as there are some things in the works which I’m sure you’ll be excited about in December), but one development I felt needed highlighting this month is that DSI video output now works on the Quartz64 model-A. This news comes via DieselNutJob on Discord, who’s picture of the default 7” PINE64 LCD panel running on the Quartz64 I am linking below.  

![](/blog/images/DSI-LCD-with-Quartz64-model-A-768x1024.jpg)

**LCD connected to the Quartz64 model-A - image via DieselNutJob in the chats**

Lastly, Dragan ([dsimic](https://github.com/dragan-simic)) whom many of you know from his work on both the PinePhone and Pinebook Pro - as well as peripherals for both of these devices - has written an article about the new production run of the Pinebook Pro for a long-standing computer magazine in Serbia. I’m [attaching](https://files.pine64.org/blog/Dsimic-PBP-article.pdf) an automatically translated version of the article for you to read. 

## PineBuds Pro

The PineBuds Pro were first revealed in an [April fools joke](https://www.pine64.org/2022/04/01/introducing-the-pinebuds-and-pinepod-seriously/) earlier this year - they are a pair of wireless in-ear headphones with ambient sound passthrough (sometimes also called transparency mode), environment noise cancellation and a long battery life. Each bud has a two-tone black finish, 3 microphones on each bud, a set of replaceable silicone tips and features touch controls. They also sport a small PINE64 pinecone logo on the touch-control surface, which we hope strikes a balance between being discrete and giving the buds a sense of belonging in the PINE64 product-line. The charging cradle features a two-tone finish similar to the one of the buds, a sliding cover, a LED battery status indicator as well as a USB-C port. The outer portion of the chassis is glossy while the inner part is more matte. The top of the sliding cover features PINE64 branding, while detailed product information can be found on the bottom of the cradle’s lid. I think that the pictures linked below speak for themselves. 

![](/blog/images/pbuds1-1024x769.jpg) ![](/blog/images/pbuds2-1-1024x769.jpg) ![](/blog/images/pbuds3-1024x769.jpg) ![](/blog/images/pbuds4-1024x769.jpg)

**Thanks to [Ralim](https://twitter.com/RalimTek) for the pictures :)**

The PineBuds Pro have been designed to ‘just-work’ for those who simply want a pair of wireless IEMs while, simultaneously, offering hackers and tinkerers everything they need from the get-go. The cradle has a built-in throughpass for UART used for firmware flashing. Each of the buds is exposed individually so two UARTs are present when the cradle housing both buds is connected to a computer. There will be three different SDKs available for you to play with - one of which should [already be available](https://files.pine64.org/SDK/PineBudsPro/PineBudsPro_SDK-20220916.7z) for download. The SDKs have already been tested and I’ve been told they work - more on this later. In time, we should see community firmware that allows for altering the touch controls, buds core behaviour and possibly also allowing for inclusion of new features. Most importantly, however, custom firmware will allow you to flash custom sound signatures adjusted for your individual ear canal resonance frequencies. The BES2300 - the chips at the heart of the PineBuds Pro -  was seriously considered for hearing-aids, so there is a potential that the PineBuds Pro could serve as over-the-counter (OTC) hearing-aids for people with very limited hearing impairment. 

I should also mention that the [PineBuds Pro Wiki](https://wiki.pine64.org/wiki/PineBuds_Pro) is already up, with datasheets and schematics. In the coming weeks the Wiki will be edited to include other pertinent documentation and resources; you are welcome to contribute content to the Wiki - indeed, you are asked to do so if you’re an early adopter of the hardware.

![](/blog/images/PbudsWiki-1024x732.png)

**Contribute to the [Wiki](https://wiki.pine64.org/wiki/PineBuds_Pro) if you're thinking of tinkering with the PineBuds Pro** 

I managed to get hold of [Ben (Ralim)](https://twitter.com/RalimTek), known for his work on [IronOS](https://github.com/Ralim/IronOS) powering the Pinecil, who just received his early production PineBuds Pro units earlier this week. Ben has been a part of the project since its inception, so I reached out to learn more about the software status. There are currently three pieces of software for the PineBuds Pro: closed firmware that ships with the buds by default, open source firmware (that has some bugs at present) and an open source minimal SDK. I should make it clear that ‘open’ in this context doesn’t mean that the firmware is completely blob-free, as there are closed-source components for parts of the hardware and radio. Ben says that some of these components will be rewritten or simply removed. Ben is also actively working on a Linux programming tool, which he’ll likely also port to Windows and MacOS in the future - he found the default programming tool somewhat clunky. He hopes to have a tool ready in ‘a week or two’.

Aside from the software status information, Ben also offered up some early impressions of how the hardware actually sounds. I’ll quote much of what he wrote verbatim - _“In terms of performance of the headphones, I've only used the shipping firmware so far, (...) but performance is very good to my ears \[although\] I'm not a professional audio user” He adds that the “ (...) the audio response feels fairly ‘normal’ without excessive EQ being used on the base.”_ 

I also had an opportunity to ask Ben about the function of the ANC and passthrough mode on the PineBuds Pro running the default firmware - _“The ‘normal’ ANC is great for general use reducing most ambient noise below what I notice but not being as aggressive as some headphones where it can cause headaches. The higher powered ANC definitely blocks more noise but I find it can cause slight headaches/discomfort similar to some other ANC headphones.”_ This is obviously something subjective - I too am very sensitive to ANC and quickly get a sense of pressure in my ears with ANC IEMs, but I suspect that many may find the stronger ANC setting perfectly fine in noisy surroundings. Ben also writes that “_the passthrough mode works noticeably better than other headphones_ \[he has\]_, with sound passing through without sounding like it's a phone call_”.

I should mention that the PineBuds Pro had extensive sound tuning - the hardware was tested and molded to provide the best-possible sound. We reached out to professionals in the field to tune the plastics and the speaker to offer what we believe to be the best sound signature. I am not exactly well versed in the process nor do I have any real insight into what good frequency responses are for this type of IEMs, but for those of you who are in-the-know I am including a graph below which you are welcome to study. If you’re an audiophile, please share in the comments what this graph means to you. 

![](/blog/images/Pbuds-response-curve-1024x581.png)

**PineBuds Pro frequency response curve**

PineBuds Pro will be available later this month \[edit confirmed date December 2nd\]  - likely the week following this blog post going live - and will cost $69. For the past 2 months the PineBuds Pro have been undergoing testing and were submitted for both FCC, CE, and CE RED evaluation and have now received the above-mentioned certificates (these certificates should also find their way up on the Wiki in the coming weeks). The default sound signature has been tuned for those users who are not interested in tinkering with their units or in custom firmware, and from what I hear their default sound signature is really pleasant - Marek got to experience the default tuning during Akademy last month and said he was pleased with how they turned out. I believe that the PineBuds Pro has a good chance of becoming a device similar to the Pinecil and PineTime in terms of their scope within the community - they will work well out of the box and offer an easily-accessible playground for those who wish to dig deeper.  

## Ox64

We were really pleased to see the positive reaction to last month’s announcement of the Ox64. Those of you who missed it, I suggest you read [last month’s community update](https://www.pine64.org/2022/10/15/october-update-an-ox-no-bull/) for details about the hardware. In a nutshell, the Ox64 is a tiny RISC-V single board computer with 64MB of RAM capable of running either Linux or RTOS - it can effectively be used as either a microcontroller or a tiny PC. At the core of the board you’ll find a BL808 SoC with 3 cores - a 64bit RISC-V core, a 32bit RISC-V core and a low power RISC-V core. It will be available in two hardware configurations, the first of which has 16Mb flash and no microSD socket and the latter 128Mb and takes microSD cards, which can be either used for storage or to boot a Linux OS. 

On the heels of last month’s announcement I get to bring more good Ox64 news. I’m sure you’ll be thrilled to know the board should be available in the Pine Store in the near future - we currently expect the date to be November 25. The production is already underway and we ought to receive first units from the production-line any day now. That said, the current COVID19 situation in China makes it difficult to predict with certainty when delivery will take place - everything related to production and logistics is currently unpredictable. Please keep an eye on our social media and the chats for more information coming soon; an announcement concerning availability will be issued on Twitter, Mastodon and in the chats. On launch, two versions of the board will be available and will sell for $6 and $8. The first SKU is geared towards RTOS while the latter towards Linux development.

![](/blog/images/Linux-on-Ox64.png)

**Linux on Ox64 - via [Marek Kraus on Twitter](https://twitter.com/gamelaster/status/1583916501400068096)**

Speaking of Linux development, the second portion of the good news I have for you is that Linux on the Ox64 has already been successfully booted. Our very own [Marek Kraus](https://twitter.com/gamelaster) managed to get the board to boot a buildroot installation. The flashing process and connecting UART is currently a bit unintuitive, but this is also something that will be greatly improved in coming weeks. Marek has already made an open source flasher which will hopefully support the Ox64 soon, and this is bound to help the process of getting the board up-and-running as easily as we’re all accustomed to. Marek adds that following some additional work it should be possible to boot Linux from a microSD card, making the process even simpler than booting from Ox64’s internal storage. Obviously we expect to see much development on this platform as developers and early adopters get their hands on units later this month or in early December. 

![](/blog/images/Flashing-Ox64-and-UART-768x578.jpg)

**UART connected to Ox64 (a bit messy setup currently) - via** [**Marek Kraus on Twitter**](https://twitter.com/gamelaster/status/1583916501400068096/photo/2)

I should also note that there are 3 add-on boards in the works for the Ox64. The first will be a camera module using either USB UVP or MiPi CSI. This will be a great addition which may allow you to transform the Ox64 into a security or nanny cam - I’m sure you can think of other uses too. The second add-on board will allow you to connect an LCD panel with a touchscreen as well as an i2s audio DAC with headphone amp and a headphone jack. A tiny retro-handheld (surely it’ll emulate NES), a small DAP, a DIY alarm-clock? - I think there’s plenty of cool things that can be achieved with such an add-on board. The last add-on currently planned will break-out the Ox64’s Ethernet - which is something I imagine many who’ll want to hack on the thing will be excited for. Stay tuned for more Ox64 news in the coming months as the add-ons take shape.  

## **Star64** 

We initially hoped to have Star64 available today but some last minute production issues have pushed the release date back to next month. While this is a bit of a disappointment - as it would make for an awesome surprise to have the hardware drop alongside the update - but it is ultimately good news that the issues were identified and addressed prior to any hardware shipping. We currently expect to have the Star64 available at some point in December, potentially prior to the December community update, but please note that this date may be pushed back further due to the COVID situation in China. As I’ve written in the previous section on the Ox64, things are a bit up in the air currently when it comes to hardware production and deliveries.   

Just as a recap, the Star64 is a RISC-V single board computer StarFive JH7110 64bit RISC-V CPU sporting quad SiFive FU740 cores clocked at 1.5GHz. The SOC is equipped with BXE-4-32 from Imagination Technologies. The IO is similar to the Quartz64 and the board’s footprint follows our model-A form-factor, with some notable differences however: the Star64 is fitted with a USB 3.0, 2X USB 2.0 ports, a PCIe slot as well as two native Gigabit Ethernet NICs. If you are interested in learning the details of the hardware spec then I invite you to read the [August update](https://www.pine64.org/2022/08/28/august-update-risc-and-reward/) in which Star64 was announced. Even more information about the board can be found on the [official Wiki page](https://wiki.pine64.org/wiki/STAR64), to which I strongly encourage you to contribute. 

![](/blog/images/Star64-1024x453.png)

**Front and back of the Star64 - note the double Ethernet ports next to the digital audio out**

On launch, the Star64 will be available in two hardware configurations - with 4GB and 8GB of RAM for $69.95 and $89.95 respectively. There will be competent software on launch as a good starting-point for developers and early adopters. I wrote about how [much progress has been achieved in September and October](https://www.pine64.org/2022/10/15/october-update-an-ox-no-bull/), with AOSC having been successfully booted on the board with all key features already working, and we’ve seen further developments on the software front since. I am not really in the position to make announcements for other projects but you can expect to hear declarations of software support for the Star64 coming soon. I am really excited to see Star64 launching soon and I am glad that it is highly anticipated by the community. I dare say, bar the Ox64, the Star64 is the board our base is most excited about since the launch of the RockPro64. 

## PineTime \[by JF\]

Last month, just a day following the October community update, [InfiniTime 1.11](https://github.com/InfiniTimeOrg/InfiniTime/releases/tag/1.11.0) was released. In case you missed it, I wrote a [dedicated blog post](https://www.pine64.org/2022/10/18/infinitime-1-11/) about this new version of the firmware. Feel free to have a read if you want to learn more about the new watch faces and functionalities featured in InfiniTime 1.11.

![](/blog/images/infineat.png) ![](/blog/images/g7710.png)

**Two new InfiniTime watch faces**

We received a lot of feedback since the release and been asked many questions, most of them about the new resource package. I would like to take this opportunity to answer some of them in this post.

As a reminder, the resource package containing data (fonts and pictures) is needed to enable the 2 new watch faces (Infineat and G7710) in InfiniTime. These watch faces make use of the external flash memory of the PineTime to store this data that would be too big for the main memory of the watch. As this data is not built into the firmware, it needs to be flashed into the watch separately. Flashing this package requires a companion app which supports this new feature. At this time, [Amazfish](https://github.com/piggz/harbour-amazfish/releases/tag/2.1.0) and [ITD](https://gitea.arsenm.dev/Arsen6331/itd/releases/tag/v0.0.9) already support this functionality, and other companion apps will hopefully follow soon. Let’s take the time to thank companion apps maintainers and contributors for their great job! 

So, does it mean that you cannot upgrade to InfiniTime 1.11 if you don’t use the particular companion apps? Of course not! You can still use your PineTime running InfiniTime 1.11 with any other companion app. The only thing you won’t be able to do is to upload a new resource package and enable the new watch faces. You can always temporarily switch to Amazfish or ITD to upload the packages and then continue using your favorite companion app as per usual.

Many users also asked if the resource feature would allow them to install new applications in the PineTime without the need to flash a whole new firmware. Unfortunately, not (yet). Currently, the resource feature only supports “static assets” like fonts and pictures. Executing code coming from the resource package is obviously not impossible, but it’ll require you to take a few additional steps.

Since this new release went live I’ve already spotted at least two pull-requests that built something new on top of the resource feature: [a new watch face - Horizon](https://github.com/InfiniTimeOrg/InfiniTime/pull/1396), and a [new gallery application](https://github.com/InfiniTimeOrg/InfiniTime/pull/1384) that displays pictures, QR codes and text files. I’m really happy to see contributors leveraging this new feature in their contributions!

![](/blog/images/horizon.gif) ![](/blog/images/gallery.gif)

**New [Horizon watch face](https://github.com/InfiniTimeOrg/InfiniTime/pull/1396) pull request (left) and [gallery application](https://github.com/InfiniTimeOrg/InfiniTime/pull/1396) (right)** 

This month I would also like to highlight this tweet from [@octoshrimpy](https://twitter.com/octoshrimpy), showcasing a re-design of the UI from InfiniTime based on the Catppuccin theme. And, to be honest, I think it looks very good!

![](/blog/images/infinitime-redesign1.png) ![](/blog/images/infinitime-redesign2.png)

**Redesign of IntiniTime elements - via [Octo Jones on Twitter](https://twitter.com/octoshrimpy/status/1587694142305411072?s=20&t=99kzwWJV0MnWo2jVHrTWyQ](https://twitter.com/octoshrimpy/status/1587694142305411072?s=20&t=99kzwWJV0MnWo2jVHrTWyQ))**

That’s all for this month, tune in December for more PINE64 news.
