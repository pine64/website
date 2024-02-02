---
title: "January Update: More News"
date: "2022-01-15"
categories: 
  - "news"
  - "pinedio"
  - "pinenote"
  - "pinephone"
  - "pinephone-pro"
tags: 
  - "pinenote"
  - "pinephone"
  - "pinephone-pro"
  - "pinetime"
cover: 
  image: "January_update.jpg"
images:
  - "/blog/images/January_update.jpg"
---

![January_Post_Banner](/blog/images/January_update.jpg)

Welcome to the first update of the year. The year just began but much has already happened. These past 2 weeks saw the release of the highly anticipated PinePhone keyboard case and the PinePhone Pro Explorer Edition. And there is more good news: the PineNote’s e-paper display now works, and is now available for purchase without the need for a coupon. 

We have many things to cover, so let's get to it.  

You can watch the synopsis of this month’s community update on YouTube (embedded below) as well as on [Odysee](https://odysee.com/@PINE64:a) and [PeerTube](https://tilvids.com/accounts/pine64tilvids/video-channels). To stay up-to-date with PINE64 news make sure to subscribe to this blog (subscription widget at the bottom of the webpage), follow [PINE64 Telegram News channel](https://t.me/PINE64_News), the [announcements channel in Discord](https://discord.gg/pine64) as well as our [Twitter](https://twitter.com/thepine64) and [Mastodon](https://fosstodon.org/@PINE64).

I’d like to thank [JF](https://twitter.com/codingfield), [Alex](https://twitter.com/AlexRob12252696) (clover), [Lukasz](https://twitter.com/LukaszErecinsk1), [PizzaLovingNerd](https://www.youtube.com/channel/UCmGcm7dhEjS9CIOsOOv8y6w), and [Samuel](https://github.com/smaeul) (smaeul) for their contributions to this community update.

N.B. Comments on the blog post need to be in English and follow our [Community Rules and Code of Conduct](https://forum.pine64.org/showthread.php?tid=13209).

{{< youtube id="RMSKXtkoZRU" >}}

**Video synopsis of this month's update**

**TL;DR**

- Housekeeping
    - We’re running a PinePhone community poll - it takes 2 min to answer, please fill it in
    - We’ll be hosting quarterly Q&A sessions allowing you to ask any questions related to PINE64 - first Q&A on Friday, January 21 at 21:00 UTC 
    - Chinese New Year starts February 1st; production, shipping and support members are off on holidays until Late February 
    - Once Chinese New Year is over, we’ll investigate Pinebook Pro and PineTab production opportunities
- PinePhone Pro
    - PinePhone Pro Explorer Edition is available for pre-order for $399
    - PinePhone Pro orders placed before January 18th ship late January; orders placed on and after January 18th ship in late February, after Chinese New Year
    - A quick review of PinePhone Pro’s software state - a list of things that need to be enabled or fixed before the phone is daily-drivable 
    - New OSes to choose from: Gentroo, LuneOS were already ported, while openSUSE and Fedora ports are in the works
- PinePhone
    - OpenBSD now boots on the PinePhone; much work is needed to enable core functionality 
    - From Jolla’s community news blog we learn that the PinePhone port of SailfishOS accounts for more than 40% of all installs 
    - Pico 8 Raspberry Pi port works on the PinePhone - yes, it does run DOOM
- RK3588
    - Many of you have seen the announcement - the RK3588 will be made available to vendors (in bulk) later this year 
    - It is a very powerful and complex SoC - full Linux functionality will take time, likely a long time
- PineNote
    - If you are a developer or an enthusiast, you can now order the PineNote without a coupon 
    - Support for PineNote’s e-paper display has now been enabled in mainline-based Linux; we now have a functioning DRM (Direct Rendering Manager) driver for the device's e-ink controller and panel
    - Next release of the mainline-based kernel enabled USB OTG functionality; this will make development much easier moving forward
- PineTime
    - Infinitime 1.8.0 released with new features for end-users such as BLE secure pairing, and prep work for future features.
    - New version of GadgetBridge adds step counter support
- Pinedio
    - LoRa USB adapter brings LoRa connectivity to any computer or SBC equipped with a USB port
    - LoRa addon for the PinePhone has very rudimentary software support for now
    - Lup Yuen Lee has been experimenting with Apache NuttX on the PineDio STACK

## Housekeeping

Let’s start with a quick reminder that [we’re running a poll](https://www.pine64.org/2021/12/29/pinephone-community-poll/) to learn more about the PinePhone community. If you are a PinePhone user and haven’t filled in the questionnaire yet, then I kindly ask you to do so. The more people take part, the more complete the picture we have, and the better the poll results are. It is a short, 9-question survey and it takes no more than 2 minutes to fill it in. The poll will close at the end of the 24th of this month, at which point we’ll crunch the numbers and generate a report. I initially thought we could have a report included in the next community update, but now I’m thinking it may be a better idea to spend more time on the data and to write a more substantial stand-alone report. I haven’t made up my mind yet, I need to see the numbers first. I’ll keep you posted. 

We’re going to be hosting quarterly Q&A sessions using the stage feature on [our Discord server](https://discord.gg/pine64). This will give people a chance to ask questions about current and future projects, or anything else PINE64-related. I want these Q&A sessions to be casual, so rather than having questions submitted beforehand I’ll be picking queries from the chat and inviting people onto the stage for a talk. The first Q&A session will take place next Friday late evening (UTC), January 21st. As for why we’re using Discord, the answer is simply: it has the functionality we need and works flawlessly, and 2) there are now over 10,000 people on Discord, which is twice the number of the next biggest PINE64 chat protocol. The Q&A session will be recorded and uploaded to Youtube, Odyssey, and Peertube at a later date if you don’t make it or do not use Discord.

Chinese New Year (CNY) begins February 1st, at which point all production, shipping, and related activities will come to a halt. Pine Store sales, info, support, and product teams are off to spend time with their relatives and enjoy a well-deserved vacation. All factories will also stop production during this period. The Pine Store will keep taking orders over CNY, but shipping will first resume in the second half of February. Any queries submitted over this period will also be answered first after activity resumes in the latter part of the month. There will be a big build-up of emails and support tickets over this period, so it may take longer than usual to receive a response - thank you in advance for your patience. Do note that if you order hardware very late in January it is more than likely that it will ship in late February. 

Lastly, once factories start up again, one of the first things on the product team’s agenda is exploring the viability of Pinebook Pro and PineTab production. We know that many of you are waiting to get your hands on a Pinebook Pro or a PineTab; granted that prices of LCDs reach a reasonable price point after CNY, we’ll be scheduling a production run for March. I’ll make sure to update you on production-related matters closer to the date. 

![](/blog/images/Screenshot_20220114_170404.png)

**Quarterly Q&A voice channel in the official PINE64 Discord**

## PinePhone Pro

Speaking of the PinePhone, there’s a lot to unwrap for this month. The PinePhone (Pro) [keyboard case is now on sale](https://pine64.com/product/pinephone-pinephone-pro-keyboard-case/), as many of you may have seen, and the PinePhone Pro _Explorer Edition_ is now also [available for pre-order](https://pine64.com/product-category/smartphones/pinephone-pro/). The first production-run of keyboard cases should have already shipped by the time this post is live, and shipping will continue right after the Chinese New Year. As for the PinePhone Pro, orders placed by January 18th will ship out this month, while orders placed after this date will be dispatched as soon as the team returns from their holidays. While the PinePhone Pro’s software is progressing extraordinarily fast, and we’re in a much better position than with the original PinePhone Braveheart and Community Editions, there is still much work needed to bring full functionality to the device, and this will take time. Please also note that while the keyboard addon will support the PinePhone Pro, it likely will not yet be functional by the time you receive your units, as software support is still being worked on.

![](/blog/images/pppordersgoinglive.png)

**PinePhone Pro [pre-orders are now live](https://www.pine64.org/pinephonepro/)**

Reassuringly, however, the Mobian team is confident of the PinePhone Pro being daily drivable before 2022 ends in their recent PinePhone Pro status [blog post](https://blog.mobian-project.org/posts/2021/12/28/pinephone-pro/). Other partner project developers share the sentiment; the phone performs very well in all mobile environments and no hardware design flaws have been uncovered in the development batch. As things stand today, there are four major software shortcomings that prevent the PinePhone Pro from being truly daily-drivable (by end-users already acquainted with Linux smartphones). I’ll list them in the order of significance: the PinePhone Pro doesn’t wake from suspension, battery level reporting is poor, cameras do not work and, lastly, audio call quality is poor. Out of the four, the first issue directly impacts PinePhone Pro’s daily drivability, since without functional suspension the phone is limited to a short run-time. However, once waking from suspend gets sorted, we estimate that the PinePhone Pro will be able to remain dormant, while receiving SMS/MMS and calls, for as long as the original PinePhone (18-24hrs). These issues will eventually be sorted, but they are something that early adopters picking up a phone today need to be aware of. 

Finally, LuneOS and Gentoo have been ported to the PinePhone Pro, and ports of openSUSE and Fedora are already in the works. You can see all OSes currently available for the PinePhone Pro under the [_software releases_](https://wiki.pine64.org/wiki/PinePhone_Pro_Software_Releases) section of the device sub-Wiki (although it appears the Gentoo port hasn’t been added yet - please see the [original Tweet](https://twitter.com/gjdijkman/status/1480443124837142528)). Speaking of the Wiki, earlier this month the PinePhone Pro was granted FCC certification (which can be [viewed online](https://apps.fcc.gov/oetcf/eas/reports/ViewExhibitReport.cfm?mode=Exhibits&RequestTimeout=500&calledFromFrame=N&application_id=YWJeyjpCtOcbC4gx%2BHhyVQ%3D%3D&fcc_id=2AWAG-PINEPHONEPRO)), which follows on the heels of the CE RED certification granted in November. Both certifications will be uploaded to [the Wiki](https://wiki.pine64.org/wiki/PinePhone_Pro) alongside production schematics and part datasheets this month. There is now also a dedicated [_Explorer Edition_](https://wiki.pine64.org/wiki/PinePhone_Pro_Explorer_Edition) subsection on the Wiki, and it is currently void of content. Anyone with a forum or Wiki account is welcome to contribute to the page. 

The Maui Project (part of the KDE ecosystem), recently announced that they are working on a simple and unobtrusive desktop environment intended to adapt to different form factors, including desktops, tablets, and phones. While in a very early testing release simply intended for feedback, it shows quite a lot of promise thanks to its many features and clean user interface. You can expect an Alpha release in March of this year according to their current roadmap shown at the bottom of the [announcement post](https://nxos.org/maui/introducing-maui-shell/).

## PinePhone

With regards to the base PinePhone, OpenBSD has been demonstrated to boot, although much work is needed to get it to a functional state. Among the issues encountered by Crystal in his [mailing list](https://marc.info/?l=openbsd-arm&m=164051770925457&w=2); errors flood the console, the various sensors of the device are read incorrectly, powering off the device does not fully work, and the CPU is run at the wrong clockspeed. It is however extremely promising to see this kind of progress!

A recent [Jolla community news](https://forum.sailfishos.org/t/sailfish-community-news-30th-december-what-a-year/9797) post disclosed that the most popular SailfishOS port of the last year was for the PinePhone. This in and of itself may not be super surprising, but the fact that the PinePhone port accounts for nearly 40% of all installations and has _“(...) over double the installs of the other devices in the top ten list combined”_ is noteworthy. It is always exciting to see how our hardware impacts other communities and I cannot but think that this is a prime example of the PinePhone shaping a different community. Perhaps with sufficient interest from Jolla’s community members and contributors, we’ll see a port for the PinePhone Pro too - time will tell.

![](/blog/images/Jolla_stats-1024x868.png)

**Sailfish OS port statistics - picture via Jolla**

Lastly, Danct12 has tested Pico 8 on the PinePhone (running [DanctNIX Phosh](https://github.com/dreemurrs-embedded/Pine64-Arch/releases)) with the keyboard add-on. Although his pre-production keyboard has some stuck keys (production units will not have this issue), this video of him playing a Pico 8 port of doom on the keyboard is still very cool to see. I’ll leave you with his video:

https://www.youtube.com/watch?v=YHIj3mCnQZ0

**Pico 8 port of Doom running on the PinePhone with a Keyboard -**

![Tic-80 on the PinePhone](/blog/images/IMG_20211228_050619-1024x576.jpg)

**For those of you who wish to run an open-source alternative, he has also taken a photo demonstrating Tic-80 running on the PinePhone with the keyboard addon - via Danct12**

## RK3588

With the announcement of the RK3588 at the Rockchip Developer Conference of 2021, we are able to talk more freely about the RK3588 SoC. No doubt many of you have already read about this new chip, and know that it is far more potent than the current RK3399 we use in the Pinebook Pro, RockPro64, and PinePhone Pro, seeing as its GPU, in particular, is [10 times faster](https://www.cnx-software.com/2021/12/16/rockchip-rk3588-datasheet-sbc-coming-soon/). With that said, we will have chips delivered to us in the second half of the year, and rest assured no one else will have them before us. It is unlikely that there will be complete mainline Linux support or working GPU drivers within at least a year from the time that the chips start being delivered. We do not have any plans currently to put these chips into our devices until after progress has been made by others in this space. Here is the takeaway: the RK3588 is a very powerful SoC, with heaps of potential, but it is also a highly complex chip. It is, therefore, more than likely that it will take a long time for all its core features to be brought up and properly supported under Linux. We’ll be watching the development of the RK3588 closely, and once all the core functionality is in place we’ll be bringing great hardware built upon the architecture. 

![](/blog/images/rk3588.jpg)

**RK3588 block diagram**

## PineNote

Due to the progress made on the Quartz64 and PineNote platforms in recent weeks (more on this later) the PineNote can now be purchased without the need for a coupon. That said, the PineNote is still to be considered a developer and enthusiast-only device at this point in time. There is no default operating system or user interface for the PineNote and it ships with only the bootloader installed. If you intend to purchase one, at present time you’ll have to install, and likely also build from scratch, your own Linux system to run on the device. If this doesn’t scare you off and sounds like a fun challenge, then please read the Pine Store’s PineNote [product page](https://pine64.com/product/pinenote-developer-edition/) description as well as Samuel’s report below prior to picking up a unit.  

Much progress has been made over the past month toward getting Linux up and running on the PineNote. During December, most developers received their PineNote units, and began familiarizing themselves with the device, getting their favorite Linux distribution to run alongside the Android factory test image. Folks are running Alpine and Debian in various configurations, with a NixOS port in progress, and more distributions are on the way. Out of that effort came critical tool and documentation improvements, which helped to get later folks up to speed quite a bit faster. There were some great hardware projects as well, like irrenhaus's sturdy 3D printed case for the PineNote's UART Adapter:

![](/blog/images/IMG_0897-768x1024.jpg)

**PineNote UART Adapter - via irrenhaus on Discord**

After the new year came some major kernel milestones. The largest one was the release of a functioning DRM (Direct Rendering Manager) driver for the device's e-ink controller and panel.

![](/blog/images/IMG_20220101_225848-1024x768.jpg)

**PineNote Eink panel working - via Smaeul**

This accomplishment is important for two reasons. First, it proves the viability of the product as a mainline-first Linux e-reader. Second, it allows developers to start testing and optimizing their graphical applications for e-paper displays. Similar to how Linux apps had to be modified (or new ones had to be written) to work well on a PinePhone-sized touchscreen, applications will also need changes to function smoothly on a slow-updating, grayscale e-paper display. For example, developers will need to remove animations, maximize contrast, and avoid conveying information through color. While making these updates is no small task, it is only a matter of time now that the process has already begun.

To be clear, the display driver is not yet complete. Currently, it only uses the basic grayscale waveform. More work will be needed to support the optimized anti-ghosting waveforms, the fast monochrome waveform used for low-latency pen input, and the dithering waveform necessary for watching videos. Still, it is exciting to see what people are already doing with the panel. Folks have been working on several desktop environments, including GNOME and XFCE:

![](/blog/images/0d55b1485f3b118e-1024x768.jpeg)

**XFCE on the PineNote with Arch Linux Arm - via Danct12**

The next release of the mainline-based kernel enabled USB OTG functionality, which means development can now happen directly on the PineNote using a physical keyboard. Further updates brought support for the touch screen and audio playback. That leaves the microphone array and Bluetooth as the remaining unsupported hardware.

The PineNote shares most of its hardware with the Quartz64, so most of these changes benefit that board as well, just like the PineNote effort is built on top of earlier Quartz64 development \[done by pgwipeout and others\]. For example, the e-ink panel now works on the Quartz64 board, too:

![](/blog/images/20220104_104507-1024x768.jpg)

So, now that developers have devices in hand, and the e-paper display and other hardware is up and running, the pace of activity should only accelerate over the next few months.

## InfiniTime \[by JF\]

We released InfiniTime 1.8.0 a few days after New Year celebrations. This is an interesting release as it brings new features for the end-users and also prepares the ground for future functionalities.

InfiniTime “Fuzzy Kiwi” now supports the “secure pairing with a passkey” for BLE connection contributed by [James](https://github.com/evergreen22). I talked about this feature [in the last community update](https://www.pine64.org/2021/12/15/december-update-a-year-in-review/). When enabled by the companion app, the BLE connection is protected by a passkey: a PIN code is displayed on the PineTime and is requested by the companion app. This ensures that only your phone or computer can connect to your watch. It also encrypts the communication, so that no one will be able to intercept the notifications sent from the companion app to your watch, for example. And, last but not least, the secure pairing (bonding) allows the companion app to reconnect faster and more reliably to your watch!

This feature is optional for now, and we hope companion apps developers will enable this feature by default, so we can remove the unsecured connection mode in a future release.

![](/blog/images/infinitime1-8.jpg)

**InfiniTime 1.8.0 BLE secure pairing - via JF**

This new release brings many other new features and improvements: Chimes by [SteveAmor](https://github.com/SteveAmor) that notifies every hour or half-hour with a vibration, ShakeWake by [Tim](https://github.com/geekbozu) to wake your watch by shaking your wrist, a trip meter in the Step app by [Stephanie](https://github.com/stephanie-eng), and more. Some features are more complex and need more time to implement than others. In that case, we often choose to split the feature into smaller steps that are more easily achievable in a reasonable timeframe. That’s what we did for the Weather service and the BLE file system API!

Ultimately, the weather service will allow InfiniTime to display weather data (temperatures, forecasts, etc) sent by the companion app. The first step to this goal was done by [Avamander](https://github.com/Avamander/) as the BLE API required is now implemented. We decided to merge this feature even if there’s no weather app available (yet) to give companions app developers the opportunity to integrate this API in their app while we are working on a nice weather app and/or the integration of the weather data in watchfaces. Work is already in progress as [Adam](https://github.com/piggz) has already integrated the weather service in [Amazfish](https://github.com/piggz/harbour-amazfish) and [Kieran](https://github.com/KieranC) is currently working on extending the PineTimeStyle watchface to display the weather data!

![](/blog/images/pts-weather-5-768x1024.jpg)

**InfiniTime 1.8.0 with upcoming weather widget on PineTimeStyle watchface - via JF**

As you already know, we are very constrained by the memory available in the PineTime: 64kB of RAM and 512kB of flash memory. The available memory fills quite quickly as we are adding new features so we must take great care when allocating memory to ensure we keep its usage under control. For example, I’ve recently analyzed the RAM memory usage and managed to [free no less than 9kB (14%) of RAM](https://github.com/InfiniTimeOrg/InfiniTime/pull/911).

The flash memory contains the code of InfiniTime and also all the static assets (pictures, fonts, etc). This data takes a lot of space, and the relatively small flash memory space prevents us from adding nicer pictures, new fonts, and additional languages. Fortunately, the PineTime is also equipped with an additional flash memory of 4MB! Our long-term goal consists in using this additional memory to store all our static assets and free some space in the main flash memory.

The first step was taken a few months ago when we implemented a file system in this additional memory. A new step was recently taken by [Tim](https://github.com/geekbozu) with the implementation of a BLE API that allows companion apps to read and write files from/to this storage! This will be the channel of choice companion apps will use to send and update those fonts and bitmaps! There is still quite a lot of work to do before users are able to send custom graphics to their watch, but we are making progress! Check [the last community update](https://www.pine64.org/2021/12/15/december-update-a-year-in-review/) to see an example of custom background in InfiniTime!

A new version of Gadgetbridge that integrates the step counter of InfiniTime was recently published. I think this is a nice addition to the companion app, that now displays the count of steps and also displays the historical data in graphs.

![](/blog/images/gb-step1-768x1707.jpg) ![](/blog/images/gb-step2-768x1706.jpg)

**Screenshots of the new Gadgetbridge version -  via JF**

## PineDio \[by JF\]

Great news for the LoRa community: Pine64 announced the availability of the [PineDio Lora USB adapter](https://pine64.com/product/pinedio-usb-lora-adapter/) and of the [LoRa addon case](https://pine64.com/product/pinephone-pinephone-pro-pindio-lora-add-on-case/) for the PinePhone!

![](/blog/images/pinedio.jpg)

**LoRa Add-on and Adapter found in the [store](https://pine64.com/)**

The LoRa USB adapter brings LoRa connectivity to any computer or SBC equipped with a USB port (a PinebookPro or a RockPro64, for example). The LoRa addon for the Pinephone is an addon case that embeds the LoRa radio and antenna, and connects to the Pinephone using the pogo pins on the back of the phone.

Software support is very rudimentary for now, but I’m happy to announce that I’ve recently [published the source code of my driver for both devices](https://codeberg.org/JF002/pinedio-lora-driver). This driver is still very basic and allows to send and receive raw LoRa messages. The repository contains a chat demo application ”Communicator” that allows you to send and receive text messages over LoRa. In the following video, you’ll see a simple chat between my desktop computer, the Pinephone, and a Lopy board: video:

{{< youtube id="vaNbeMbY17c" >}}

**LoRa communication between desktop using USB adapter and PinePhone LoRa add-on - via JF**

[Lup Yuen Lee](https://lupyuen.github.io) continues his experiments with Apache NuttX on the PineDio STACK and wrote [a very comprehensive article](https://lupyuen.github.io/articles/lorawan3) on running LoRaWAN on NuttX. You’ll probably be interested in this article even if the PineDio STACK is not available yet, as it contains a lot of interesting information about embedded software, NuttX, and LoRaWAN.

That's it for this month!
