---
title: "May Update: Connection Established"
date: "2021-05-15"
authors: ["Lukasz Erecinski"]
categories:
  - "community"
  - "lora"
  - "news"
  - "pinebook-pro"
  - "pinephone"
  - "pinetime"
  - "quartz64"
  - "soedge"
tags: 
  - "lora"
  - "pinebook-pro"
  - "pinephone"
  - "quartz64"
  - "soedge"
cover: 
  image: "MayUpdate.jpg"
images:
  - "/blog/images/MayUpdate.jpg"
---

![](/blog/images/MayUpdate.jpg)

Let me start by welcoming the newcomers! If you are a new Pinebook Pro or PinePhone BE owner, make sure to pop by the chat or the forum and say hello to the community. 

A quick note before we get into it: we have narrowed the width of the blogpost pages, thereby hopefully making entries easier to read. This caused some issues on mobile Firefox and Opera browsers. We believe the issue is now fixed, but if you run into any problems or oddities please make sure to let us know in the comments section. Thanks. 

You can watch the synopsis of this month’s community update on YouTube (embedded below) as well as on [Odysee](https://odysee.com/@PINE64:a) and [Peertube](https://tilvids.com/accounts/pine64tilvids/video-channels). Stay up-to-date with PINE64 news and make sure to subscribe to this blog (subscription widget at the bottom of the webpage), follow [PINE64 Telegram News channel,](https://t.me/PINE64_News) the [announcements channel in Discord](https://discord.gg/pine64) as well as our [Twitter](https://twitter.com/thepine64) and [Mastodon](https://fosstodon.org/@PINE64).

I’d like to thank [JF](https://twitter.com/codingfield), [Alex](https://twitter.com/AlexRob12252696) (clover), [Peter](https://twitter.com/pgwipeout) (pgwipeout), [Biktor](https://twitter.com/biktorgj), [Martijn](https://twitter.com/braam_martijn) and [PizzaLovingNerd](https://www.youtube.com/channel/UCmGcm7dhEjS9CIOsOOv8y6w) for their contributions to this community update.

**N.B.** Comments on the blog post need to be in English and follow our [Community Rules and Code of Conduct](https://forum.pine64.org/showthread.php?tid=13209).

{{< youtube id="z-MQO7xOemQ" >}}

**TL;DR**

- Housekeeping: shipping ongoing + ideas for shipping updates on the website
- Housekeeping: SOEdge AI module available in the Pine Store & Pinecil hammerhead tip coming soon
- Housekeeping: cluster hosting our services will be moved to a permanent server rack in near future; will affect chats in and forums. 
- Housekeeping: people behind FOSS2go are building PineGuild
- PineTime: big interest in PineTime following 1.0 launch blog post; thrilled about the reception inside and outside community
- PineTime: more PineTimes available in June, will feature InfiniTime 1.0 
- PineTime: many pull requests waiting to be merged; new version of Siglo and improvements to Pinetime support in Gadgetbridge
- PinePhone: rolling production started - you can order the PinePhone any day or any month this year. 
- PinePhone: a close look at PinePhone keyboard internal review units; minor tweaks needed but it will be available this summer
- PinePhone: wireless charging and LoRa back cases available in June 
- PinePhone: Megapixels 1.0 released with many improvements, including accelerated viewfinder and horizontal mode
- PinePhone: ongoing work on modem update and work on VoLTE progress and findings
- PineDio: PineDio official name of our LoRa project; expected to launch PineDio next month inc. getaways and end-nodes
- PineDio: working in partnership with RAKwireless on the project, and the novel text messaging peer-to-peer & group application
- PineDio: report from RTP and JF on gateway status - fully functional
- Quartz64: new hardware revisions with developers; unless something unforeseen happens, available to developers in Pine Store in June
- Quartz64: much software progress! 
- Pinebook Pro: many new faces in the community - welcome!
- Pinebook Pro: Fedora 34 and Manjaro with GNOME available for the PBP
- Pinebook Pro: production placed on halt due to component shortages; will keep you updated. If you want a Pinebook Pro, now is the time to pick one up. 

### Housekeeping

Shipping of Pinebook Pros and PinePhones has gone pretty smoothly and without any major hiccups. That said, PinePhone shipments destined for EU countries have seen a minor delay due to a DHL paperwork mishap, and I know that some of you are still waiting for your devices as a result of this. Everything has now been sorted out, so if you’re in the EU, and you ordered prior to April 15th, then you should be getting your PinePhone BE shortly. As always, I encourage you to follow the [shipping update thread](https://forum.pine64.org/showthread.php?tid=13616) on the forum for the latest information about PinePhone BE and Pinebook Pro shipping status. Speaking of shipping updates: I am considering setting up a dedicated shipping update section on this website. For all intents and purposes it would function the same way as the forum shipping thread. I think it would look neater and the information would be more transparent to end-users, given that there is only so much one can do to edit a forum post nicely. What do you think - am I overthinking it or is this a good idea? Let me know in the comments section. 

The second thing I wanted to touch on is the ongoing global component shortage situation. As you might already know, manufacturing devices has been very difficult in recent months due to a lack of readily available silicon, long lead times and massive price-hikes. We will continue with the strategy I [outlined in March](https://www.pine64.org/2021/03/15/march-update/), and only sell inventory either already delivered from the factory or guaranteed to be manufactured. In short, you’ll see SBCs and devices drift in and out of stock on a fairly regular basis. As always, I’ll do my best to keep you up-to-date on device availability on social media and in the news channels. 

In other news, the [SOEdge is finally available](https://pine64.com/product-category/soedge/?v=0446c16e2e66) for purchase! The SOEdge is our AI module based on the RK1808: it features a 3.0TOPS NPU, 4GB DDR4 RAM and two cortex-A35 cores. The pin-out is compatible with the SOPine, so you can also use the SOEdge with the clusterboard. Seeing as I currently do not have any news concerning software development, nor any additional hardware information to share, I am including the launch notification in this housekeeping section. To learn more about the SOEdge and its current software status (which is pretty solid thanks to [gamiee](https://twitter.com/gamelaster)’s work) please check out the [March community update](https://www.pine64.org/2021/03/15/march-update/). For more information and other resources on the AI module, please make sure to check out the [SOEdge Wiki](https://wiki.pine64.org/wiki/SOEdge) page.

![](/blog/images/soedgeinstore-1024x686.jpg)

**SOEdge and baseboard in the [Pine Store](https://pine64.com/product-category/soedge/)**

On a similar note, the hammerhead tip for the Pinecil has now been delivered from the factory, and will be seeing a release on the Pine Store in the coming weeks. Keep an eye out for an announcement when it becomes available. You can learn more about the hammerhead tip reading the [last month’s update](https://www.pine64.org/2021/04/15/april-update-new-developments/).

![](/blog/images/HammerheadPinecil-578x1024.jpg)

**Hammerheads delivered from factory**

I also have a notice to share regarding the PINE64 cluster hosting all our services. After nearly a year in temporary storage at [BBXNET](https://bbxnet.sk/), the cluster is finally being moved to a permanent server rack where it will live out the rest of its days. This means that we will have to take it offline for a short amount of time. A temporary server, consisting of a small cluster of ROCKPro64 boards, will be used for the duration of the move. While static services such as this website or the Wiki are unlikely to be affected, I suspect that the move will cause a disturbance in the chats (the bridge will go down - and we likely won’t fix it until the move is completed), and we may also resort to temporarily locking the forum to prevent data loss. There currently is no set date for the move, but it could be as early as next month. A heads-up notification will be issued beforehand on Twitter, Mastodon, the Website, etc. I know people like this sort of stuff, so I’ll ask BBXNET folks to take some pictures for us. 

Lastly, I want to give a shoutout to a new website dedicated to PINE64 devices and our community - [pineguild.com](https://pineguild.com/). The website is brought to you by the people behind [FOSS2go](https://foss2go.com/) with the intention to serve as a news and resource outlet for our community. I know that they are also actively seeking contributors, so if you’re eager to do some writing about your PINE64 device then now you’ve got yet another outlet. I like and appreciate initiatives like this, and I really hope to see this portal take off. Go subscribe to their newsletter to show them it is worth their effort. 

### PineTime \[by JF\]

At the end of April, we [announced the release of InfiniTime 1.0](https://www.pine64.org/2021/04/22/its-time-infinitime-1-0/) together with the disponibility of PineTime smartwatches as "enthusiast grade end user product" on [the Pine64 Store](https://pine64.com/product/pinetime-smartwatch-sealed/?v=0446c16e2e66). This is great news for the developers of the projects, who can be proud of the accomplished work, but also for the users who will soon be able to buy a PineTime ready to use (single sealed unit). Advanced users and developers can also buy [a pack of a sealed device and a development kit](https://pine64.com/product/pinetime-smartwatch-dev-kit-sealed-twin/?v=0446c16e2e66)!

I cannot express how happy I am regarding the success of this announcement, which exceeded all my expectations. The article was shared, linked, tweeted and tooted all over the internet, and many popular sites covered the announcement. As a result, a lot of people joined the community chat rooms to ask questions, gave feedback and thanked us for the good work.

To give you an idea of the success of this announcement, here are some stats about it:

- More than 38000 people read the article on the blog. This is the 2nd most popular article on the site. The influx of visitors put a strain on the cluster, but it handled it like a charm!
- More than 300 new users joined our Discord server the day of the announcement.
- The traffic on the Github repo of InfiniTime also quadrupled following the announcement.
- Thousands of units were sold in the next few hours following the publication of the article, and the PineTime sold-out in the next few days!

These numbers show how much people were waiting for this release and how popular this project has become since late 2019. Thanks again to everyone who contributed to this success.

Oh and I have good news to share with everyone: a new batch of PineTime will be produced later this month, and I've provided the production team with new binaries so that those new units will be directly flashed with up-to-date bootloader and InifiTime versions. 

Finally, if you want to have an overview of what's available in InifiniTime 1.0, I recommend you have a look at [this video review](https://youtu.be/9PrhbPlnfBA) by PizzaLovingNerd.

This new release didn't stop the developers from working on the PineTime, in fact quite the opposite. There are already a lot of pending pull-requests that are awaiting review before they are merged into the next releases. These include new and improved features, such as a new step application, new watchfaces, new wakeup features and much more. We are also working on improving the memory usage to make it easier to add new applications and watchfaces in the future.

Developers are also enjoying designing new watchfaces like [this Casio inspired watchface](https://twitter.com/SravanSenthiln1/status/1387697339213701120?s=20) and [this 100% customized watchface](https://twitter.com/PizzaLovingNerd/status/1388718505172684801?s=20) by [@SravanSenthiln1](https://twitter.com/SravanSenthiln1) (do you recognize the avatar of [@PizzaLovingNerd](https://twitter.com/PizzaLovingNerd), who produces the video versions of Pine64 community updates ?).

![](/blog/images/CasioPineTime-1024x768.jpg)

**Casio inspired watchface by [@SravanSenthiln1](https://twitter.com/SravanSenthiln1)**

On the companion app side, [Gadgetbridge](https://gadgetbridge.org/) released version 0.56.2, with many improvements regarding the support of PineTime. This version improves the notifications by sending a title (name of the application that sends the notification, name of the sender of an email,etc.) along with the message, which makes the notifications much more readable on the PineTime. The functionality "find my device" was also added, which is useful if you cannot find your PineTime while it's in range of your phone. Finally, this upgrade displays the battery level in the UI and in the notification area of your smartphone.

![](/blog/images/1024-1820-576x1024.jpg)

**Gadgetbridge now shows PineTime's battery and includes new features**

[Alex](https://github.com/alexr4535) also released [Siglo](https://github.com/alexr4535/siglo) version 0.7, the GTK companion app running on the PinePhone and other Linux devices. This new version can now run in the background and send SMS notifications to the PineTime. It also brings many other bug fixes and improvements.

We talked a lot about software, but not much about hardware. This month, I would like to highlight a hardware hack by [@alvarolsamudio](https://twitter.com/alvarolsamudio), who managed to add wireless charging functionality to the PineTime - pretty cool!

![](/blog/images/Battery-charging-PineTime-473x1024.jpg)

**PineTime wireless charginig hack by [Alvaro Samudio](https://twitter.com/alvarolsamudio)**

### PinePhone: Hardware 

I have some good news to share. For starters, the Pine Store worked really hard to secure PinePhone production this year. All crucial components that make up the smartphone have been sourced, and a portfolio of discrete replacement parts has been built up and secured in the event of an emergency. This will not only get us through this difficult year but also permit a continued rolling production of the smartphone. What this means in practice is that you will be able to pre-order a PinePhone any day of any month in 2021. 

The PinePhone will, however, keep on shipping in batches due to the continued closure of the Hong Kong border with mainland China. I also presently don’t know if the time between shipments will be reduced by the rolling production or not. At any rate, the production of the next batch has already been scheduled and will likely start sometime early-next month. That said, it is obviously possible for unforeseen obstacles to cause manufacturing difficulties down the line (nothing would surprise me given current circumstances) in which case, you can count on me to let you know. 

In other good news, the PinePhone keyboard internal review units have been assembled and shipped out to a select lucky few, including myself. Late last month I shared a handful of pictures alongside a video of an [engineering prototype](https://forum.pine64.org/showthread.php?tid=13684), which lacked some of the polish seen on the review units. As you can see from the pictures below, the keyboard has now taken on its final form. The laser etched keycaps look great in my opinion and I'm told that the texture of the chassis has been matched to the PinePhone’s back case. As you can probably tell from the pictures, the fit and finish of the keyboard has really been tightened up and is looking great.

![](/blog/images/KBnophone-1024x1024.jpg) ![](/blog/images/KBback-1024x1024.jpg) ![](/blog/images/KBdetails-1024x1024.jpg) ![](/blog/images/KBstraight-1024x1024.jpg)

**Internal review unit PinePhone keyboard**

However, it isn't quite perfect just yet. The production team informed me that the keyboard’s membrane will have to be redone, although they didn’t specify why. I suppose I’ll find out soon enough (at the time of writing I haven’t received my unit yet). Regarding availability - at this point it largely depends on three factors: 1) how quickly can the i2c HID driver be made to work on the PinePhone; 2) how fast will new good membranes be created, and; 3) how soon can the mandatory torture testing be completed. Rest assured, we want the keyboard available in the Pine Store as much as you do. In the meantime, keep a lookout for updates - more info will be coming soon, once review units land. 

![](/blog/images/WirelessChargingPCBA-744x1024.jpg) ![](/blog/images/LoRAPCBAPinePhone-624x1024.jpg)

**Left: redesigned wireless charging PCB + coil // Right: LoRa PCB** 

Lastly I have - and you guessed it - more good news. We are planning to start selling the wireless charging and LoRa back cases for the PinePhone next month. The fingerprint reader case will arrive somewhat later, since we’re still working out sensor firmware quirks with the vendor. The wireless charging PCB has been redesigned since you’ve seen it last and the LoRa PCBA has now been delivered. I am attaching pictures of both PCBAs for you to check out. While the wireless charging case will ‘just work’ with any PinePhone right out of the box, since it is a ‘dumb’ periperial, the LoRa case will be marketed strictly at developers. We will make it clear on the Pine Store that the LoRa implementation will require extensive input from developers. Hopefully we’ll get it functional in record time.  

### PinePhone: Software \[Martijn & Biktor\]

**Megapixels 1.0** \[Martijn\]

Megapixels 1.0 has been released. This version of Megapixels switches from GTK3 to GTK4, this is not for the sake of adding newer dependencies, but because this allows having working GPU acceleration in the camera preview. With the toolkit change also comes some UI changes that are now possible because we can now draw GTK widgets over the preview.

This means the custom rendered shutter/exposure settings are now replaced by dropdowns and the preview image now extends below the bottom row containing the camera controls. The blue tint bug has also been located and a workaround has been implemented making the camera usable without switching between the front and rear camera first.

The image post-processing pipeline itself hasn't been changed in this release, but due to a smoother preview it's now a lot easier to take sharp pictures with the PinePhone.

{{< youtube id="kHl3gmugIyc" >}}

**Video showcasing the accelerated viewfinder in Megapixels 1.0**

**VoLTE support** \[Biktor\]

Last month I started testing VoLTE HD support in the modem. Both the Pinephone and the modem support HD audio over VoLTE, and the modem can be run at 8KHz or 16KHz sampling rates for better quality audio. There's two slight problems though, which are:

1. Whatever sampling rate you use on the modem must be matched in the Pinephone's audio subsystem, so if you set at 8K and you're in a call, any other audio stream will have to match that sample rate, reducing sound quality.
2.  The modem doesn't support changing the sample rate at runtime, so it is not possible to dynamically set it.

Turns out 2 is a lie, the modem can actually change its settings at runtime, even during a call, the problem is stock firmware wasn't really designed with that in mind and requires a reboot to use the new settings. Even more, the modem is capable of going up to 48K sampling rate, it's only limited by the closed source binaries and the stock kernel. Right now, with the custom modem firmware, you can select your desired sampling rate to 8/16/48K, by issuing a simple AT command, and it's applied at runtime.

That was the easy part. Now I'm looking for the best possible approach to get the Pinephone side of thing to be able to work in 8K for everyone using the stock firmware, but be able to switch it to 48K if supported by the modem firmware to get better audio quality.

### PineDio

I cannot recall who suggested PineDio (get it, Pine + radio?) to us as a name for our LoRa project, but I’d like to thank whomever it was for the suggestion as it ended up being what we settled on. The PineDio is now officially the name we gave the entire PINE64 LoRA ecosystem of gateways and end-nodes. Today I am happy to announce that we'll be fast forwarding the project with an estimated release date of late June. We will simultaneously release the PineDio indoor and outdoor gateways alongside a USB and SPI end-node, as well as the PinePhone LoRa back case. Once we have all devices built and delivered from the factory I’ll write-up an announcement post that will include pricing. If you’re interested in this project, then I strongly encourage you to sign up to our blog, follow updates on the relevant news channels as well as on our social media accounts. 

![](/blog/images/PineDio_open2-1024x768.jpg) ![](/blog/images/PineDio_open_ext_antanna-576x1024.jpg)

**PineDio outdoor gateway inside**

Earlier this month we announced that we will be [cooperating with RAKwireless](https://www.pine64.org/2021/05/06/lets-make-mirakles-happen/) on the PineDio. [RAKwireless](https://www.rakwireless.com/en-us) is an industry leading IoT solutions provider, producing high-end LoRa® gateways, sensors, kits and modules. Both our indoor and outdoor gateways, which are at the very heart of the system, will be using RAKwireless technology. We’re thrilled that we’re going to have an opportunity to work with RAKwireless and [their community](https://bit.ly/rakstars-discord) on this project. In both the cooperation announcement and in [last month’s community update](https://www.pine64.org/2021/04/15/april-update-new-developments/) I’ve already outlined at length the goals which we will strive to achieve with the PineDio ecosystem. In summary, we are interested in traditional IoT applications as well as a novel implementation of LoRa for peer-to-peer and group text messaging. We have high hopes for bringing an alternative messaging system to all our devices. 

![](/blog/images/LoRaSendingMessages-1024x1024.jpg)

**Sending and receiving messages from PineDio gateway - by [JF](https://twitter.com/codingfield/status/1390378521722331144)**

Developers who have been working on gateway prototypes have already gotten quite far with their endeavours. JF informed me that, indeed, the gateway is already fully operational and both the RAKwireless LoRa module and GPS are already working well after some modifications to RAKwireless software. Both JF and [RTP](https://www.youtube.com/channel/UChVCEXzi39_YEpUQhqmEFrQ) have managed to connect their gateways to The Things Network and Chirpstack, running locally on the gateways. JF also informed that he has already been able to receive messages from a LoRaWAN device on the PineDio. I also spoke to RTP about his work on the gateway. He informed me that sending beacons from the PineDio gateway works well, that the concentrator starts without any errors, and that GPS works accurately for him. 

As such, it would appear that the gateway code is good to go, and most of the work required at this point will concentrate around the end-nodes. We expect that the USB end-node will be made to work swiftly, in part since we’ll have a third party help out with the process. The SPI end-node and the PinePhone back case (using i2c) will, however, require input from the development community. Once all end-nodes work with PINE64 SBCs and devices we’ll start exploring LoRa’s potential for peer-to-peer and group messaging. But one thing at a time.  

### Quartz64: Hardware

Earlier this month we shipped V2 of the Quartz64 model A and B to developers. The new board revisions feature a number of minor hardware fixes as well as a new Gigabit Ethernet PHY; the Realtek PHY chips we use on all PINE64 Single Board Computers (SBCs) is presently nowhere to be found. I wrote about this at length in [last month’s community update](https://www.pine64.org/2021/04/15/april-update-new-developments/) if you’re interested in learning more about the situation. As things stand, we are currently awaiting feedback from developers regarding the new board revision - granted no issues are found in the next 2 weeks then the production will finally commence. As you probably can tell by the fast pace of the hardware’s development, we’re very determined to bring the Quartz64 to the market as soon as possible and usher in a new SoC-era for PINE64 gear.   

![](/blog/images/Q64_v2_onLeft-1024x954.jpg)

**Left: Quartz64 v2.0 board // Right: Quartz64 prototype**

We are currently planning on making Quartz64 available next month. However, given the unpredictability of the manufacturing situation, please consider this a tentative time-frame. Once the production is underway, I’ll publish a dedicated post with additional information and an exact availability date. 

![](/blog/images/Q64_V2_modelA_and_B-1024x761.jpg)

**Quartz64 v2.0 model B and A**

Although the hardware will soon see the light of day, the software is still not ready for primetime. Indeed, despite a truly monumental effort from various parties and lightning fast development progress, Quartz64 is still in early stages of development. This is understandable given how young the SoC is and how few Quartz64 (and other RK3566 boards) are currently available to developers. We will therefore target this initial production-run at developers and technically inclined enthusiasts able to help in the bring-up process. The soon-to-be scheduled batch will be large enough to cover all developers interested in picking up a unit (and then some), but end-users will specifically be asked to wait a little longer. After all, it is in everyone’s best interest that these early boards end up in the right hands at this early stage of development.

### Quartz64: Software \[**By Peter**\] 

A significant amount of patches needed for the rk3568/rk3566 have been submitted to mainline, and a few have already been accepted. As things stand, the GPIO, pinctrl, iommu-v2, thermal, rk817-codec, gmac, PCIe, and power-domain patches have been submitted to mainline for the rk3568 chip series. There is also a basic rk3568 device tree in review.

![](/blog/images/RK3566PatchWorkSubmissions-1024x630.jpg)

**The pace and activity levels are really high**

We now have the V2 board in hand and have begun validating it. We have the new gmac PHY used on the v2 enabled on the new Quartz64 boards. Another piece of good news is that the SATA controller has been validated and works extremely well. The PCIe controller is in good shape, every card we have tested (except GPUs) works out of the box. We have started trying to spin up the Mali GPU using Panfrost open source driver, but the new VOP-v2 driver needs porting over. The new I2S driver will need to be ported as well to enable sound output. We are still waiting on ATF sources and the official errata for the GICv3. Work has started on mainline u-boot but depends on the ATF sources to work properly.

### Pinebook Pro

Many Pinebook Pro units have reached their rightful owners in the past 30 days. Just as with past production-runs, the Pinebook Pro was once again met with a lot of positivity and praise, which was great to witness. I am also happy to see so many new faces in the Pinebook Pro sub-segment of our community - welcome! At the same time, I’d like to thank the veterans among you who have been actively helping out, offering suggestions and pointing new users to resources. Great job. 

This is a really good time for Pinebook Pro owners. The past two months have seen a lot of development and new additions to the platform’s software portfolio. I wish to highlight two new arrivals in the Pinebook Pro’s software lineup: Fedora 34 and Manjaro GNOME. [Peter Robinson](https://twitter.com/nullr0ute), the Principal Architect for Red Hat, wrote up a [complete and comprehensive guide](https://nullr0ute.com/2021/05/fedora-on-the-pinebook-pro/) for getting Fedora 34 workstation up and running on the laptop. Following the instructions will land you a mainline Fedora build featuring accelerated graphics on the GNOME desktop. Peter also links to an interim WiFi/BT driver in his notes, as Pinebook Pro’s WiFi/BT module hasn’t been upstreamed yet. I know many of you have waited for a simple way to run the newest Fedora on your Pinebook Pro, so make sure to let Peter know you appreciate his work on this.

![](/blog/images/Fedora34PBP-768x1024.jpg)

**Fedora 34 on the Pinebook Pro via [Peter Robinson's Twitter](https://twitter.com/nullr0ute/status/1373425123349438464)**

Those of you who prefer GNOME over KDE can rejoice as now you have both an Armbian Focal and a Manjaro 21.04 ready-to-go OS image featuring your favorite desktop environment (I wrote about Armbian with GNOME last month, if you want to check it out). Manjaro 21.04 with the GNOME desktop features full functionality, including working GPU acceleration in the desktop, and a custom U-boot allowing other OSes to boot from SD when Manjaro is installed to internal eMMC flash. I gave the [latest release](https://github.com/manjaro-arm-community/gnome-images/releases) a spin just the other day, and I must say that I am very impressed by the performance - it is really snappy. 

Now I have some bad news. Pinebook Pro production will be placed temporarily on halt. The current component shortages make it very difficult to source the necessary parts to continue with the manufacture. The production team has done a lot of research in an effort to pump out another batch in late Q2 or early Q3, but ultimately chose against proceeding. In short, even if we resorted to work-arounds and use alternative parts and electronics, the end-result would be one of many compromises, which simply wouldn’t be fair to our community. On top of this we would have to significantly increase the asking price for the Pinebook Pro. I know that this is disappointing news but ultimately it is also the right call.

If you are on a fence whether you want to pick up a Pinebook Pro, then I strongly suggest you make a decision fast: the Pinebook Pro stock will last no longer than a few days. At present time I cannot say with confidence how long the Pinebook Pros hiatus will be, but I suspect it will be no less than 3 months before we can even start considering spinning up production again. Mind you, this statement is based on the current market situation. The component availability situation is presently very volatile and highly dynamic. The outlook may change at any time, quite literally.  Rest assured that as soon as production becomes viable again, I'll make sure to let everyone know.

That is it for this month! See you in the chats and on the forum to discuss this month’s update.
