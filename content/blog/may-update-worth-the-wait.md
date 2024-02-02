---
title: "May Update: Worth The Wait"
date: "2022-05-31"
categories: 
  - "news"
  - "pinebook-pro"
  - "pinebuds"
  - "pinephone-pro"
  - "pinetime"
tags: 
  - "pinebook-pro"
  - "pinephone-keyboard"
  - "pinephone-pro"
  - "pinesound"
  - "pinetime"
  - "quartz64"
  - "soquartz"
cover: 
  image: "May-Update.jpg"
images:
  - "May-Update.jpg"
---

![](/blog/images/May-Update.jpg)

Hello everyone! This month we’re announcing production of the Pinebook Pro resuming and introduction of Quartz64 model-B. I had an opportunity to meet with TL earlier this month, and got some ear-on time with the Pinebuds, so I dedicated a section to my early impressions from the time spent with the prototype. This update also brings news of SOQuartz Blade hostboard production, camera enablement on the PinePhone Pro and a guest write-up by dsimic addressing issues some users have been experiencing with their PinePhone (Pro) keyboards. There is truly a lot to get to this month, so let’s get into it. 

You can watch the synopsis of this month’s community update on YouTube (embedded below) as well as on [Odysee](https://odysee.com/@PINE64:a) and [PeerTube](https://tilvids.com/accounts/pine64tilvids/video-channels). To stay up-to-date with PINE64 news make sure to subscribe to this blog (subscription widget at the bottom of the webpage), follow the [PINE64 Telegram News channel](https://t.me/PINE64_News), the [announcements channel in Discord](https://discord.gg/pine64) as well as our [Twitter](https://twitter.com/thepine64) and [Mastodon](https://fosstodon.org/@PINE64).

I’d like to thank [JF](https://twitter.com/codingfield), [Dylan](https://fosstodon.org/@dylanvanassche), [dsimic](https://github.com/dragan-simic), [Alex](https://twitter.com/AlexRob12252696) (clover), [Brian](https://mastodon.online/web/accounts/61817) (33YN2), and [PizzaLovingNerd](https://www.youtube.com/channel/UCmGcm7dhEjS9CIOsOOv8y6w) for their contributions to this community update.

**N.B.** Comments on the blog post need to be in English and follow our [Community Rules and Code of Conduct](https://forum.pine64.org/showthread.php?tid=13209).

{{< youtube id="wQaUaP2s130" >}}

**Video synopsis**

**TL;DR**

- Housekeeping
    - Update moved to 28th of the month
    - PINE64 in-person meeting
    - Pinebook donation to school with kids in need of laptops
    - We’re going though QuartzPro64 dev pre-orders
    - PINE64 EU store; addressing delay 
- Quartz64 & SOQuartz
    - Model-B released - available for $60
    - SOQuartz Blade hostboard enters production 
- Pinebook Pro
    - Pinebook Pro is making a return after months of absence
    - Expected in Pine Store late June early July
    - Price stays the same as do most specs 
    - Highlight of selected new released for the Pinebook Pro
- PinePhone (Pro)
    - PinePhone Pro restock expected late June early July
    - PinePhone Pro camera enablement underway; look at first pictures
    - Mobile Linux has gained support for Bluetooth HFP
    - User-made script to easily install Waydroid
- PinePhone (Pro) keyboard
    - Dsimic writes at length about PP KB issues identified by community and developers 
- PineSound
    - First PineSound dev boards allocated to devs
    - PineBuds prototype early impressions 
- PineTime
    - InfiniTime development progress 
    - New InfiniTime fork exposes high frequency accelerometer data; fork receives a dedicated companion app

## Housekeeping 

Let me start by addressing the delay in the publication of this month’s community update. I’ve been really busy with the EU store this past month (more on this later) and ill for the better part of last week, which left me with very little spare time to do the write-up. As a result, for the first time in years, this update is published at the end of the month rather than on the 15th. I have given some thought to the situation and arrived at the conclusion that we’ll make the 28th of the month the new update publication date. So be on the lookout for the next update on June 28th. Consider this publication tentative - in two-three months I will reevaluate if changing the publication date to the end of the month was a good decision.  

Earlier this month we held our first in-person meeting since FOSDEM 2020. It was a small get-together, primarily aimed at discussing the PINE64 progress and PINE64 EU’s launch. It was a pleasure to see the people who make the cogs turn in person again. Thank you guys for paying me a visit!  

![](/blog/images/meetup.jpg)

**From the left: Lukasz, Gamiee, Lynx, TL and Ayufan**

As some of you may recall, last year we made a [pledge to donate Pinebooks](https://www.pine64.org/2021/04/03/help-us-help-others/) to a charitable cause. It may come as a surprise but, as it turns out, donating hardware is actually not simple. One would think that it is a case of establishing a suitable cause and shipping the hardware, but nothing could be further from the truth. I’ll spare you the detail of the hurdles we had to overcome, but suffice to say finding a suitable recipient of the Pinebooks proved difficult. It is therefore with great pleasure that I bring you news that the first batch of Pinebooks have found a new home at a school where kids were in need of a laptop. I would like to take this opportunity to sincerely thank [_One Laptop Per Child_ (OLPC)](https://laptop.org/) for helping us in finding the right recipients of the laptops. May the Pinebooks serve their new owners well.  

![](/blog/images/PB-donation.jpg)

**We are looking forward to dispatching more Pinebooks to schools and charities this year**

We have started going through developer pre-orders for the QuartzPro64. Allocation of the boards was initially delayed (in part due to my absence this past month), but with units now rolling off the factory floor we’ll move swiftly to issue first coupons. We have decided to send the boards out in smaller batches rather than all at one time - this will allow us to monitor progress and developer engagement. So if you filed an application to pick up a QuartzPro64 at a reduced developer price of $150, and won’t hear from us in the coming weeks then don’t worry, we’ll send out units for the months to come. At the same time, I’d like to remind you that the developer pre-orders are still open and that there is still time to [file a coupon request](https://preorder.pine64.org/). To learn more about QuartzPro64, I invite you to read the [March community update](https://www.pine64.org/2022/03/15/march-update-introducing-the-quartzpro64/) where I detailed the board’s specs and explain our decision to subsidize the initial production run. 

![](/blog/images/QuartzPro64-PCBA-final-front-920x1024.jpg)

**Final QuartzPro64 PCBA**

Lastly, I wish to address the PINE64 EU store’s launch delay. For the past month I’ve been cutting through layers upon layers of red tape - as it turns out, it is one thing to ship to the EU and a whole different thing to have permanent representation here. Since the situation is ongoing I will refrain from discussing the specifics at this time - what I will say is that I have now gotten a lawyer to help the process along. I hope that all outstanding legal paperwork can be sorted out in the next 2-3 weeks. As always, I’ll keep you posted on the PINE64 EU’s [Twitter](https://twitter.com/pine64eu) and [Mastodon](https://fosstodon.org/@pine64eu).  

## Quartz64 & SOQuartz

Earlier this month we [released the Quartz64 model-B](https://pine64.com/product/quartz64-model-b-4gb-single-board-computer/) that sports the same RK3566 SOC found on its larger sibling as well as the SOQuartz compute module. Model-B comes in a familiar form factor and is available in a 4GB LPDDR4 RAM configuration for $60. While the model-A is geared more towards the development community, the model-B is meant as an easy-to-integrate option for industry partners and regular end-users. It does offer fewer IO options than the model-A but still manages to deliver a solid connectivity selection including 2x USB, 1x USB 3.0, and Gigabit Ethernet with PoE. You also get AC WiFi, Bluetooth 5.0, MIPI CSI, and DSI as well as a mini PCIe slot.

![](/blog/images/Model_A-Front-1024x1024.jpg) ![](/blog/images/Model_B-Back-1024x1024.jpg)

**Quartz64 model-B top and bottom**

I had the opportunity to try out the new board earlier this month, and I was very happy with both how well it is supported and with how well it performs. I tried Manjaro with Plasma and, to my surprise, the board performed really well running at my monitor’s native 4K resolution. Running the desktop under Wayland I would describe the experience as perfectly smooth; it is clear that Plasma Desktop benefits from [Panfrost](https://docs.mesa3d.org/drivers/panfrost.html) (FOSS GPU driver) acceleration at 4K resolution. I will go as far as to say that the model-B would be a great candidate for a 4K kiosk running a dedicated application or a browser-based app. As someone who enjoys playing retro games, I also think it would make for a great small emulation box. I hope we’ll get a LAKKA image for it eventually. 

I’ve spoken briefly with [pgwipeout](https://github.com/pgwipeout), one of the contributors who laid the software foundations for the Quartz64 device lineup, and asked about software progress. He told me that model-A and B, as well as the SOQuartz, have found their way into kernel 5.19. He added that the VOP2 driver was accepted into kernel 5.19 for HDMI output, but the DTS changes will first find their way into kernel 5.20. Now that we’ve got a solid software foundation in place, we need the board to offer a wide diversity of OS choices. Manjaro has done a great job, and their OS images are really well maintained, but I am well aware that many need a Debian-based or specialized (e.g. LAKKA) operating system to meet their requirements. So, If you are associated with a project who would like to support the Quartz64 devices, make sure to reach out to me or one of the admins.   

![](/blog/images/Blade_final-Version-1024x264.jpg)

**SOQuartz and SSD in the Blade hostboard**

The SOQuartz compute module, which is based on the same hardware configuration as the model-A and model-B, has already been released for some time, and the first pre-release OS [images for the module](https://github.com/manjaro-arm/soquartz-cm4-images/releases/) are now available. With the software taking shape fast, the SOQuartz host boards have entered production and should be available in the Pine store soon. Aside from the model-A type host board - which is basically an IO breakout board - we will soon also be offering the Blade hostboard. The Blade has been designed for clustering, and fits inside a standard 1U server rack: 12 or more Blade hostboards can fit into a single rack. I wrote at length about the Blade in [November last year](https://www.pine64.org/2021/11/15/november-update-first-impressions/), but here is a short recap of the IO the Blade exposes: Gigabit Ethernet, a micro SD card slot, 1x USB 2.0 header, digital video output, 40x GPIO header, UART output, power barrel jack port and an M.2 PCIe slot for storage. The Blade has been designed to have IO located at the short leading edges, allowing for easy access and cable management as well as tight stacking inside a server rack. More information about the Blade and SOQuartz model-A host board will be coming soon. 

## Pinebook Pro

  
It has been a year since we were able to ship the Pinebook Pro, and ever since the last batch sold out we have been continually asked to bring it back. Today I am pleased to let you know that the Pinebook Pro has now re-entered production and will be available for purchase at some point in late June or early July. You will surely also be happy to learn that we are re-introducing the laptop at an unchanged price of $219 - the price it sold at prior to all the disasters which at first made production difficult and eventually impossible. The hardware remains largely unchanged from the 2021 version of the laptop. This includes the PCBs, keyboards, metal and plastic parts, etc. For those who haven't followed the [Pinebook Pro production hurdles](https://www.pine64.org/2021/03/15/march-update/) over the past months: the main reason for production stalling was our inability to acquire reasonably priced and vendor-insured high-grade IPS panels. We did, however, already have much of the remaining parts lined up and ready to go. The new panel ought to deliver identical performance to those used previously. The only other change concerns the battery - the new battery is marginally smaller at 9600mAh, which is 400mAh less than in previous iterations.

![](/blog/images/kali-pinebook-pro-1024x707.png)

**Kali Linux on Pinebook Pro - image via [Kali Linux](https://www.kali.org/blog/kali-linux-2020-1a-release/images/kali-pinebook-pro.png)**

I feel like it is a great time to pick up a Pinebook Pro - those of you looking to get a unit should know that the laptop is now a very mature platform, with many available OS options and a thriving community. It is also a platform that benefits from developments on the PinePhone Pro. I’ve seen an array of updates to Pinebook Pro OS images over the time that the laptop was unavailable - this includes the [default Manjaro with Plasma](https://forum.manjaro.org/t/manjaro-arm-22-04-released/108311) desktop, which I’ve been using for the past 3 years on my laptop. The excellent [postmarketOS with GNOME](https://images.postmarketos.org/bpo/edge/pine64-pinebookpro/plasma-desktop/) build has just received an update this past week; if you are partial to the GNOME desktop and enjoy Alpine Linux then you absolutely should give it a go. One other OS I’d like to mention is Kali Linux, since a popular application for the Pinebook Pro is using it as a dedicated pen-testing device. Kali Linux has recently made it possible to [use the Kali kernel and u-boot](https://www.kali.org/blog/kali-linux-2022-2-release/?utm_source=twitter&utm_medium=&utm_campaign=5735ed88-f8b0-4c25-ad0b-04ee415dc835) instead of compiling your own, thereby greatly simplifying the installation process. Those of you seeking Debian and Fedora installations will be happy that these are also available. All OSes and documentation for the Pinebook Pro can be found on the [PINE64 Wiki](https://wiki.pine64.org/wiki/Pinebook_Pro) - information relevant to the new panel and battery will be uploaded to Pinebook Pro’s Wiki next month. 

Keep a lookout for more information on the Pinebook Pro in the coming weeks. 

## PinePhone (Pro) \[by Lukasz, Dylan and Brian\]

Before we get into the software news, I want to quickly touch upon PinePhone Pro’s availability. The PinePhone Pro is currently out of stock, but it won’t be long before more units arrive. The next batch is expected to land in the Pine Store sometime in late June or early July and should last for months to come. I will notify the community as soon as more units become available, so keep an eye on our social media and news channels.  

Let’s dive into software. Earlier this month a breakthrough was achieved in getting the cameras to work on the PinePhone Pro. [Megi](https://xnux.eu/) brought up support for the rear (main) camera, forward-ported the BSP driver for the front-facing selfie camera, and integrated it into the kernel tree along with device tree changes. For those of you interested in the details, details of the process can be found in his recent [blog post](https://xnux.eu/log/#067) which I obviously encourage you to read. As he writes, this is just the beginning of the journey, and developers will now need to integrate userspace support of the cameras in applications such as [Megapixels](https://git.sr.ht/~martijnbraam/megapixels). For the time being, [to snap a photo](https://wiki.pine64.org/wiki/PinePhone_Pro/IMX258_Camera_Debugging) you’ll need to open CLI and jump through numerous hoops. While it may take some time before capturing photos on the Pro will become convenient, the recent development brings us one step closer to reaching parity with the original PinePhone’s functionality. I can only hope that implementing Megi’s work into userspace applications will proceed at a good pace and won’t get bogged down with any major obstacles. I am including pictures from both the front and rear camera below; please note that both images are completely raw without any post-processing applied. I’m not an expert in mobile photography, but those pictures look pretty darn good to me. 

![](/blog/images/PPP_cam2-1024x768.jpg)

**Picture taken using PinePhone Pro’s selfie (front) camera - image from Megi**

![](/blog/images/PPP_cam1-1024x768.jpg)

**Picture taken using PinePhone Pro's main (rear) camera - image from Megi**

[**Dylan**](https://twitter.com/DylanVanAssche)**:**

Mobile Linux has gained support for [Bluetooth HFP](https://www.bluetooth.com/specifications/specs/hands-free-profile-1-8/) (Hands-Free Profile) - a Bluetooth specification that allows you to make hands-free phone calls. This specification has already existed for a decade and is supported by all kinds of phones. I submitted a [series of patches to PulseAudio](https://gitlab.freedesktop.org/pulseaudio/pulseaudio/-/merge_requests/693) to support Bluetooth HFP in ModemManager, which will allow you to manage calls through

Bluetooth HFP devices. This includes accepting, rejecting, hanging up calls. Some devices can also display the current network operator, service status, phone battery level, etc. This is also implemented by this patch series. [postmarketOS](https://postmarketos.org) users will soon benefit from my patches. A detailed [explanation can be found on my blog](https://dylanvanassche.be/blog/2022/bluetooth-hfp-linux-mobile/).

<iframe title="Enhanced Bluetooth HFP support in ModemManager &amp; PulseAudio" src="https://tube.tchncs.de/videos/embed/fc79ddac-40ba-4206-b14b-007667fe6af1" allowfullscreen sandbox="allow-same-origin allow-scripts allow-popups" width="560" height="515" frameborder="0"></iframe>

**Bluetooth HFP demo - via Dylan**

[**Brian**](https://mastodon.online/web/accounts/61817)**:**

Lastly, but certainly useful to many of you who may not know or have struggled to setup Waydroid, a community member - [Cara (FOSSsingularity)](https://twitter.com/FOSSingularity) - has recently created an easy to use [script for configuring and managing Waydroid](https://github.com/MadameMalady/Manjaro-Waydroid-Manager). This script includes the ability to set up a custom rom to run in the container, and the ability to enable or disable gapps support. In a similar vein, the same contributor has also created a Maui Shell installer script for Manjaro, for those of you who wish to test out the Alpha of the new shell without having to manually configure it to launch. Awesome stuff!

## PinePhone (Pro) Keyboard \[by [dsimic](https://github.com/dragan-simic)\]

**_\[NB:_** _This is a community blog and we are always delighted to host content by members of the community, especially when said written material is submitted by noteworthy contributors. We never alter or edit written material submitted to us (unless necessary - e.g. for clarity, typos, composition, structure, etc). Please consider the following as an opinion piece, which does not necessarily reflect the position of the Pine Store Ltd. or PINE64 community’s management team.\]  
_

Let's face it, there are a few well-known issues with the PinePhone (Pro) Keyboard Add-On (PPKB) that have been identified since its launch. Even more importantly, there have also been a few complaints about the lack of official transparency and openness regarding these issues, which this write-up will attempt to remedy by providing a long-overdue official summary of the issues. Perhaps this write-up will be a bit long and filled with more technical stuff than is usual in the community updates, but in this case, there is no point in oversimplifying things or in beating around the bush. If you do not have the time to read this section in its entirety, here is a TL;DR - when the PPKB is attached to a PinePhone (Pro), please treat the phone's USB port as if it did not exist.

In this write-up I'll refer to both the PinePhone and the PinePhone Pro collectively as ‘the phone’, where the same applies to both variants, for the sake of brevity. Using ‘PPKB’ as the abbreviation for ‘PinePhone (Pro) Keyboard Add-On’ has already been established. It is also good to point out that the PPKB is internally made of two independent parts, the charging part, and the keyboard part. As visible in the [PPKB schematic](https://files.pine64.org/doc/PinePhone/PinePhone%20Keyboard%20Schematic%20V1.0-20211009.pdf), the former is based on the [IP5209](https://files.pine64.org/doc/datasheet/pinephone/IP5209.pdf) which charges the PPKB battery and provides the 5V boost output to power the phone, and the latter is based on the [EM85F684A](https://files.pine64.org/doc/datasheet/pinephone/EM85F684A.pdf), powered independently by the phone.

Alright, let's get into more details. There are three primary issues with the charging part of the PPKB, which were both identified very early during the development of the PPKB, but the issues were partially dismissed because the limited testing that was possible during the development was unable to prove that the issues are real and capable of inflicting actual damage to the equipment. However, putting the PPKB into the hands of so many people effectively resulted in lots of testing, with wildly different environments, which unfortunately resulted in two issues surfacing as real issues and capable of damaging the equipment. An unfortunate side issue is that, for a yet unknown reason, no printed manuals were included in the retail cardboard boxes in the first PPKB batch, which caused unnecessary confusion among the owners.

The first issue with the charging part of the PPKB comes from the fact that the PPKB is connected to the phone in a way that makes it act as some kind of an invisible USB charger that is plugged into the phone's USB port all the time when the PPKB is attached. Of course, it does not look like that from the outside, but that is the way one of the pogo pins found under the back cover of the phone is wired internally. That pogo pin is electrically the same as the 5 V pins found inside the phone's USB Type-C port, to which an external USB charger connects to. Thus, connecting a USB charger to the phone's USB port while the PPKB is attached is effectively the same as splicing two USB chargers together, which usually does not result in anything bad due to the construction of the chargers, but it also sometimes causes damage to the chargers (let's remember once again that the PPKB is an invisible charger). Unfortunately, a few PPKB owners had to discover all that on their own, and we had a few PPKBs releasing the magic smoke.

To be fair, it is possible to turn the PPKB's 5 V boost output off, both in software that talks to the battery charging IC inside the PPKB and by using the physical button on the PPKB itself, but it was concluded empirically that the inactive status of the charging part of the PPKB achieved that way simply cannot be trusted, because the charging part may become active again unexpectedly. Moreover, nothing gets electrically disconnected that way, which still ends up in a USB charger plugged into the phone's USB port feeding power into the charging part of the PPKB, which in this case may be even worse for the health of the charging part, because there is now no power coming out of the PPKB to "fight against" the power coming in from the USB charger. Not good at all.

To sum it up so far, you must never use the phone's USB port for charging when a PPKB is attached to it. As we know, the official [PPKB manual](https://files.pine64.org/doc/PinePhone/USER%20MANUAL-KEYBOARD-V2-EN-DE-FR-ES.pdf) already says that a USB charger must never be connected to the phone's USB port when the PPKB is hanging off its back, so it has all been about old news so far, but with the additional, hopefully helpful, descriptions of how it all works together.

The second issue with the charging part of the PPKB comes from the fact that the phone, among other things, acts as a 5V source for the bus-powered USB devices connected to its USB port; in the USB Power Delivery (PD) lingo, the phone can act as a PD power source. The 5V boost regulator inside the phone, which provides that 5 V power source when needed, may also be seen as another invisible USB "charger" connected to the same point where the PPKB and the external USB charger are connected -- the 5 V pins found inside the phone's USB Type-C port. Of course, appropriate mechanisms exist to prevent the phone's 5 V power source from becoming turned on while a USB charger or a self-powered USB device is plugged into the phone's USB port, but those mechanisms are unfortunately not perfect, and the existence of the PPKB as another power source throws all that off.

In particular, the internal 5 V power source in the PinePhone is controlled at the hardware level by the closed-source firmware blob that runs inside the [ANX7688](https://www.analogix.com/cn/system/files/AA-002281-PB-6-ANX7688_Product_Brief_0.pdf), which handles some of the functions of the PinePhone's USB Type-C port. As a result, relying on the ANX7688 firmware to keep the PinePhone's internal 5 V power source turned off is simply impossible when a bus-powered USB device is plugged into the PinePhone's USB port. Moreover, it's possible for the battery voltage to become present as the power supply for bus-powered USB devices, instead of the boosted 5 V voltage, which may actually put the circuitry inside the PinePhone at even higher risk of damage. On the bright side, the internal 5 V power source is controlled entirely by software in the BraveHeart revision of the PinePhone, which puts BraveHeart owners in a much better position, but I'm not aware of the required software support actually being available. As the final result, we can effectively again have two ‘invisible USB chargers’ spliced together when a bus-powered USB device is plugged into the PinePhone's USB port. Again, not good at all.

When it comes to the PinePhone Pro's internal 5 V power source, things are luckily a bit better. The internal 5 V power source is controlled by the [RK818](https://rockchip.fr/RK818%20datasheet%20V1.0.pdf) PMIC, which according to its datasheet should react properly whenever externally supplied 5 V is detected, turning the PinePhone Pro's internal 5 V power source off.  Though, some issues may still be present, such as not knowing for sure what happens when the PPKB's boost output is turned off while a bus-powered USB device is plugged into the PinePhone Pro's USB port, at which point the internal 5 V power source should become turned on automatically, possibly glitching the connected USB device and effectively starting to feed power into the PPKB, etc. In a few words, things can quickly become exactly the same as having two "invisible USB chargers" spliced together, as described above. None of this has been tested or confirmed yet, which means that the PinePhone Pro is getting the same treatment as the PinePhone in this regard, at least for now. Not good, once again.

The third issue with the charging part of the PPKB, which is completely independent of the first two issues, is that a bus-powered USB device plugged into the phone's USB port can draw power directly from the PPKB's 5V boost output, with no additional current limiting in place. As a result, a misbehaving USB device can end up drawing up to 2.4 A from the PPKB, through the phone's USB port, regardless of the actual power negotiation that took place. In general, this should not cause any permanent damage to the phone or the PPKB, because they were both designed to handle such currents during regular charging. However, it may end up causing damage to a misbehaving bus-powered USB device, because it may not be designed to withstand up to 12 W going into it in case of some failure. To be fair, this scenario with a misbehaving USB device that draws a lot of power and burns itself down should be very rare, at least in theory. These are hopefully not the famous last words. :)

Finally, to sum it all up, it is not only that the phone's USB port must not be used for charging, but it must also not be used to connect bus-powered USB devices. To put it differently, when a PPKB is attached to your phone, please treat the phone's USB port as if it did not exist at all.

I will also create a couple of new pages in the PINE64 Wiki that will provide even more details about the PPKB issues, together with the relevant excerpts from the PinePhone and PinePhone Pro schematics, etc. Those Wiki pages will provide further explanations, so please feel free to check them out once they become available.

## PineSound

The first PineSound development boards have already been allocated, and I got some hands-on time with both the board and PineBuds prototype earlier this month. There isn’t much I can say about the PineSound dev board that I haven’t already said in [last month’s update](https://www.pine64.org/2022/04/15/april-update-no-more-unicorns/), but I wanted to share my experience with the PineBuds. Consider this a first look. Before I get into it, I want to make it clear that it will take (yet undetermined) time before the buds become available, and much will change between now and then. I also won’t write about the feel of the plastic, since this prototype was CNCd (yeah, I didn’t know you can CNC plastic either), and in all likelihood, the final version will end up feeling nothing like this. The buds themselves are nice, really small, and light. They are not the smallest buds I’ve ever seen, but they are certainly among the smaller ones I’ve tried (and I’ve tried quite a few - I’m a bit of a connoisseur). The default tuning sounds good, offering a pleasant V-shaped curve. I wanted to underline this because the V sound signature isn’t something I particularly enjoy. Obviously, a major draw of the PineBuds is that you’ll be able to flash the internal EQ with any sound signature, and I’m certain someone will create a ‘flat’ sound signature for the Buds. 

We’ve gone through a few iterations of renders, trying to figure out how we want the PineBuds to look. I am sharing some ideas below - there is no guarantee they will look like this, these are just some ideas.  

![](/blog/images/PineBuds-render-2.jpg) ![](/blog/images/PineBuds-render.jpg)

**PineBuds concept renders**

The carrying case has some way to go before it reaches a production-ready status. The prototype case we’ve shown last month has no charging or battery LED status indicators, and it is something we’ll want to change. We’ve also decided on a sliding rather than a hinged mechanism for the lid. At present the mechanism leaves much to be desired. Obviously, it is still very early and this unit is just a proof of concept, but even at this stage, it's clear that refining will be needed to deliver a good experience of opening and closing the case. We also haven’t zeroed in on a suitable battery to use inside the case - obviously, the bigger the battery we can squeeze in the better. As I mentioned, the current prototype was CNC milled, so I can’t speak to the feel of the shell, but the shape and size of the case are good if a little bit large. I think that the larger size of the case will be justified by the battery capacity. That's all I have for the time being - as new prototypes are created I’ll make sure to update you on this project’s progress. 

## PineTime

The InfiniTime team is still working steadily on the project! A few improvements have already been merged since the last [release](https://github.com/InfiniTimeOrg/InfiniTime/releases/tag/1.9.0). I won’t go into much detail as they are not released yet, but you can see the overview of what has already been done and what we are working on for the next version by going to the [next milestone page](https://github.com/InfiniTimeOrg/InfiniTime/milestone/10).

![](/blog/images/infinitime-milestone.png)

**Features and fixes already merged for the next release of InfiniTime**

Among other things, we are actively working on leveraging the external flash memory of the watch to store pictures and fonts. This will allow us to free up quite a lot of space in the memory of the PineTime. I’ve recently done [a few performance tests](https://github.com/InfiniTimeOrg/InfiniTime/issues/321#issuecomment-1133959435) of various implementations. I took a lot of inspiration from [PineTimeLite](https://github.com/joaquimorg/PinetimeLite). In this fork of InfiniTime, [Joaquim](https://github.com/joaquimorg) has already done a lot of experimentation with loading resources from this external memory, and I hope that we’ll be able to achieve similar results in InfiniTime soon!

ITD, the InfiniTime daemon and GUI application written in [Go](https://gitea.arsenm.dev/Arsen6331/itd) has recently [released a new version 0.0.5](https://gitea.arsenm.dev/Arsen6331/itd/releases/tag/v0.0.5). This new version adds a new whitelist feature that is very useful when you have multiple PineTimes laying on your desk. It also implements all new functionalities from InfiniTime like the filesystem and weather APIs. Even if those APIs are not usable by the end-users yet, their integrations in companion apps make the lives of the developers easier. For example, I use the filesystem functionality quite extensively right now to implement the resource loading from the external flash memory!

![](/blog/images/itd-fs.png)

**FS API integration in ITD**

[StarGate01](https://github.com/StarGate01), who has already contributed to InfiniTime, has created a new fork of InfiniTime specifically designed to expose [high-frequency data from the accelerometer](https://github.com/StarGate01/p8b-infinitime). They also built [a companion app](https://github.com/StarGate01/PineTimeAcc) to display this data in real time. Those projects will certainly be useful to developers who want to develop advanced algorithms and signal processing based on the PineTime accelerometer!

![](/blog/images/pinetimeacc-1024x576.png)

**High frequency data from PineTime's accelerometer**

That is all for this month. Remember, next community update is scheduled for June 28th. See you then!
