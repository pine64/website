---
title: "April Update: New Developments"
date: "2021-04-15"
categories: 
  - "community"
  - "news"
  - "pinecil"
  - "pinephone"
  - "pinetab"
  - "pinetime"
  - "quartz64"
tags: 
  - "community"
  - "lora"
  - "pinebook-pro"
  - "pinecil"
  - "pinephone"
  - "pinetab"
  - "pinetime"
cover: 
  image: "AprilUpdate-1024x594.jpg"
---

![](/blog/images/AprilUpdate-1024x594.jpg)

Before we start, I’d like to acknowledge that this community update was written collaboratively, with contributions from 7 developers. I hope that moving forward we maintain this dynamic and more developers, as well as community members, partake in the write-up process. If you’d like to participate in the next update then please make sure to reach out. 

Now, let’s get to this month’s news. 

You can watch the synopsis of this month’s community update on YouTube (embedded below) as well as on [Odysee](https://odysee.com/@PINE64:a) and [Peertube](https://tilvids.com/accounts/pine64tilvids/video-channels). Stay up-to-date with PINE64 news and make sure to subscribe to this blog (subscription widget at the bottom of the webpage), follow [PINE64 Telegram News channel,](https://t.me/PINE64_News) the [announcements channel in Discord](https://discord.gg/pine64) as well as our [Twitter](https://twitter.com/thepine64) and [Mastodon](https://fosstodon.org/@PINE64).

I’d like to thank [JF](https://twitter.com/codingfield), [Alex](https://twitter.com/AlexRob12252696) (clover), [Bhushan](https://twitter.com/BhushanNShah), [Dalton](https://twitter.com/UnivrsalSuprBox), [Peter](https://twitter.com/pgwipeout) (pgwipeout), [Biktor](https://twitter.com/biktorgj), [Konrad](https://github.com/konradybcio), [Brian (](https://mastodon.online/web/accounts/61817)33YN2) and [PizzaLovingNerd](https://www.youtube.com/channel/UCmGcm7dhEjS9CIOsOOv8y6w) for their contributions to this community update.

**N.B.** Comments on the blog post need to be in English and follow our [Community Rules and Code of Conduct](https://forum.pine64.org/showthread.php?tid=13209).

{{< youtube id="rbgSrUjxqtE" >}}

**Video synopsis of this month's update**

**TL;DR** 

- Housekeeping - PinePhone BE & Pinebook Pro orders prior to April 12th ship out this month & orders made after the 12th mid-May; follow the shipping update thread
- Housekeeping - we’re giving 100+ OG Pinebooks to a good cause; thank you for all the suggestions!
- Housekeeping - we’re Linux App Summit sponsors (again) this year. 
- Quartz64 - a close look at Quartz64 model-B; feature run-down and more
- Quartz64 - model-A delayed by a month+, as GbE PHY chip cannot be sourced and will therefore be replaced
- Quartz64 - incredible software progress; board boots both BSP and Mainline Linux now!
- PinePhone Hardware - keyboard back April 16th, I’ll cover it separately later this month
- PinePhone Hardware - wireless charging + fingerprint reader back case in production - prototype shown
- PinePhone Hardware - LoRa back case entering production
- PinePhone Software - Plasma Mobile status & day 1 patch for PinePhone BE
- PinePhone Software - Ubuntu Touch on the PinePhone, a look at the progress made
- PinePhone Software - Further work on the modem; better thermals + GPS now works in custom firmware, and progress with mainline Linux on the modem 
- PineTime - motion sensor now works in InfiniTime; wake on wrist rotate & pedometer
- PineTime - InfiniTime UI overhaul underway and new features, including CNC
- PineTime - working towards 1.0 release later this month - keep an eye out for blog post
- PineTime - WaspOS progress report 
- Pinebook Pro and PineTab - production outlook for the year, hurdles and uncertainty
- Pinecil - The Hammer was an April fool’s joke, but it is actually real 
- Pinecil - Thermal resistant USB-C cable & mat coming 
- Pinecil - We hear ya’ a see-through case will be available soon
- LoRa - PINE64 LoRa gateways now with developers; a look at the hardware 
- LoRa - We’ve got big plans for LoRa - a list of end-nodes and add-ons already with devs

## Housekeeping

Let’s start with some good news. As many of you are surely aware, we have both PinePhone and Pinebook Pro production-runs currently on pre-order. We don’t expect any major delays in the production and dispatch roadmaps of either device, and by the time the next community update goes live we’ll be seeing many new faces in our community. Granted nothing happens in the final days of production, and nothing unforeseen happens during dispatch, the first round of laptops and smartphones should be departing Hong Kong late this month or early in May. Those of you who pre-ordered prior to April 12th will receive your units in early-to-mid May. The second round of shipments will start in mid-May. Under normal circumstances, reporting on production and shipment is pretty mundane, but given the current circumstances it's something that has taken center stage. As always, [I’ve opened a shipping update thread](https://forum.pine64.org/showthread.php?tid=13616) on the forum, which I’ll update regularly. I look forward to welcoming all of the new Pine64 device owners to the community.

I’ll provide detailed production outlooks for individual devices in their respective sections, but here I wish to give you a general overview of how the silicon shortage will affect us, and consequently also you, moving forward. Frankly, we don’t expect production circumstances to improve prior to Q1 2022 - in other words, we’ve got a challenging 8 months ahead of us. Last month we [explained our strategy](https://www.pine64.org/2021/03/15/march-update/) for only taking pre-orders for the PinePhone, PineTab and Pinebook Pro once production is securely underway. We’ll maintain this strategy moving forward - likely for the rest of the year. As a result, the gaps between pre-order windows are going to be longer than they were in 2020. At the same time, due to the pre-order windows being effectively ‘squished’, I expect the time from the moment an order is placed until the device ships will be reduced. 

Devices which can be bought outright will frequently drift in and out of availability in the Pine Store. This is because highly popular devices, such as the Pinecil or the SOPine, will only be added to store inventory once they are physically received from the factory; given current production uncertainties, only units in physical possession of the store will be sold. I’ll do my best to keep you all updated on availability throughout this year - make sure to follow the various news sources, listed at the beginning of the update, to receive updates. 

![](/blog/images/Givingbacktothesociety-1024x596.jpg)

**The original Pinebook - my kid loves her's**

We also have some awesome community news to cover. As you may know, Pine64 has a commitment to giving back to society at large. To reflect this, we announced that we’ll be [donating 100+ original Pinebooks](https://www.pine64.org/2021/04/03/help-us-help-others/) to an established nonprofit (or more than one). Since the announcement earlier this month, we’ve been thrilled to see such an enthusiastic response from many community members. Thank you all for the great suggestions. We have now selected a few prospective candidate organizations, some of which I’ve already been in touch with, and will be making our final decision in the coming weeks. Once again, I would very much like to thank all of you who took the time to submit a suggestion. 

![](/blog/images/LASSponsorPINE64-1024x576.jpg)

**Via Linux App Summit [Twitter](https://twitter.com/LinuxAppSummit/status/1380430285280579584)**

Lastly, we’re once again sponsoring this year’s [Linux App Summit](https://linuxappsummit.org/), taking place May 13-15. It is a virtual event co-hosted by the GNOME Foundation and KDE Community, which spans multiple time zones and features some of the industry’s and open source community’s brightest minds. The purpose of LAS is to help grow the Linux application ecosystem by bringing together people from various segments of the Linux world. The conference features talks, panels, Q&A sessions in which attendees share their ideas on how to build a sustainable and competitive Linux app ecosystem. Attendance is free of charge and everyone is welcome to participate; [registrations are now open](https://linuxappsummit.org/register/). I hope to see many of you there! 

## Quartz64: Hardware 

Before we move onto all the good news concerning development as well as the unveiling of Quartz64 model-B, we need to get some bad news out of the way. During the model-A production we learned that the Gigabit Ethernet PHY we intended to use is completely out of stock, with a projected lead time of 12 months. Moreover, the price per unit has increased by 850% (yes, that’s right, that isn’t a typo) making it unviable. We obviously have no intention of waiting a year for the PHY to become available again, nor to pay nearly 10 times more for the chipsets, so we will be replacing the original PHY with a different chip. We are currently weighing in on our options and collecting opinions from developers. As a result, the launch of the model-A will be pushed back by a month or more. By the time the next update goes live I’ll surely have a much clearer picture of Quartz64 model-A production status, so for the time being I have to ask you to be patient and to stay tuned.

As you probably gathered from this and the past community updates already, all things related to production remain in a constant state of flux. Last month I wrote that the [Quartz64 model-B won’t be seeing a release](https://www.pine64.org/2021/03/15/march-update/) anytime soon, and now here I am a month later showing off the model-B and announcing that we intend to bring it to the market at around the same time as the now-delayed model-A. This roadmap is, of course, based on our current understanding of available parts and present production circumstances, and therefore subject to change. Next month, when more is known, I’ll make sure to provide a joint model-A and model-B production update. If you haven't checked out model-A yet, then make sure to read the [February community update](https://www.pine64.org/2021/02/15/february-update-show-and-tell/) where I showcase and discuss it at length.

![](/blog/images/modelBbackandfront-1024x759.png)

**Top and bottom of the Quartz64 model-B single board computer**

Now that I’ve given you a general insight into the production schedule, let’s overview the model-B itself. The board shares the ROCK64’s footprint and features all of its I/O, so for those of you using the ROCK64 in your projects, or in an industrial setting, the Quartz64-B will surely be a nice upgrade. The engineers did, however, manage to squeeze more I/O into the model-B than the ROCK64 offers; apart from the full GPIO, Gigabit Ethernet, micro SD, eMMC slot,  2xUSB 2.0, a single USB 3.0 port, IR R/X, digital video and an audio jack, you also get DSI, CSI and an M.2 (PCIe). The Quartz64 model-B also features onboard wireless connectivity. We’ll be offering the board in two versions: with a Realtek Bluetooth/WiFI chipset and a BL602 from Bouffalo, the latter of which is undergoing open-sourcing in our very own [Nutcracker Challenge](https://www.pine64.org/2020/10/28/nutcracker-challenge-blob-free-wifi-ble/). For more details, you can find the schematics for the Quartz64 model-B (and A) on the respective [subsection of the PINE64 Wiki](https://wiki.pine64.org/wiki/Quartz64). 

![](/blog/images/modelBcloseup2-1024x999.jpg)

**Nice little board, isn't it?**

Closing this section off, I have some excellent news concerning software development. Thanks to the work of many people, notably pgwipeout, gamiee and Xalius as well as [ezequielg](https://discord.com/channels/463237927984693259/815289130358538271/831959303215775855) and [ndufresne](https://twitter.com/ndufresne) from [Collabora](https://www.collabora.com/), we now have the board booting both mainline and BSP Linux. The fact that they collectively achieved this in just a short month’s time is very impressive. I’ve asked Peter (pgwipeout) to write a short but detailed development-status update for you, to which he kindly agreed. 

## Quartz64: Software \[by Peter (pgwipeout)\]

We are currently using the public facing development branches of Rockchip’s repositories. For Quartz64, this means Rockchip’s heavily customized U-boot-2018 and Linux-4.19 customized for Android. We are presently stuck using the pre-built SPL and Trust binaries from Rockchip-Android until mainline ATF is released. The boot system has changed significantly from earlier Rockchip generations - the new system is simpler, but will require retooling the mkimage tool to compensate for the new format. Here is what works as of today: for starters, U-boot allows booting from micro SD cards as well as eMMC, although the latter hasn’t been tested. We can load kernels, device-trees and initrd images. USB-OTG works partially too. As for Linux itself, we are now able to boot both BSP Linux 4.19 as well as mainline Linux. 

![](/blog/images/Q64-kernel512.png) ![](/blog/images/Q64-kernel419.png)

**Top:** ****Quartz64 booted into mainline Linux** / Bottom: Quartz64 booted into BSP 4.19 Linux**

Linux 4.19 boots into userspace and some core I/O is functional, including the GbE controller, USB 2.0 and serial. It is noteworthy that GbE performance is above that seen on the RK3399. USB 2.0 works, albeit it is unstable with long cables, and Serial works only though FIQ-Debugger. As for mainline Linux, as of today we’ve got working clocks, GPIO, micro SD, eMMC (although it hasn’t been tested) USB 2.0, USB 3.0 and the GbE controller. Similar to the Rockchip provided BSP, USB 2.0 only works with short cables and USB 3.0 currently doesn’t function when cables are plugged in. 

This is a very promising start, but much is yet to be enabled. For instance, PCIe interrupts are broken at this time. Using downstream Linux-4.19, PCIe cards are eventually detected through polling, but they are not functional; mainline detects the problem beforehand and doesn’t permit the driver to probe. It's a mapping problem, see above. The USB3.0 problems are possibly related to the USB2.0 issues, as this appears to be a PHY problem. Lastly, reboot - which is handled through PSCI, that is provided by the ATF binary, is currently not functional. Everything else is untested as of now.

![](/blog/images/compilingliveonQuart648GBRAM-1024x556.png)

**Compiling Linux kernel on an 8GB RAM Quartz64**

There are significant challenges still ahead of us. We are working off the rk3568 documentation, which the rk3566 is a watered down version of. Unfortunately there are differences that take a bit of trial and error to trace out. The rk3568 GIC-V3 required Rockchip to implement significant changes in the irq driver due to architectural limitations. These changes will have to be ported to mainline Linux in a way that will be accepted. The Rockchip Linux drivers are incomplete and the mainlining effort has only just begun. We also need the source code for ATF to fix the reboot bug as well as work out other issues.

## PinePhone Hardware

Let me start with some good news. We have the PinePhone production under control, at least for the foreseeable future, and despite the component shortages we’ve managed to secure at least 3 more large production-runs this year. Keep in mind that each pre-order and shipping cycle takes approx. 2 months. Hopefully, by the tail-end of the year the component availability will improve somewhat, and extensive logistics gymnastics will no longer be necessary to assure product availability. There may, of course, be some hiccups along the way, but here is the take-away: there shouldn’t be any issues with getting a PinePhone this year. 

I’ve also got some good peripheral hardware news for you. For starters, the last parts of the PinePhone keyboard should be back from the factory tomorrow. This, obviously, means that the keyboard will not be featured in this update. But stay tuned, I will keep you informed on the keyboard later this month via another blog post or a thread on the forums - I haven’t decided yet. Regardless, we are finally going to see the keyboard fully assembled soon, and I know that many of you are very excited to see it in its completed form. 

In other hardware news, I have an update regarding LoRa as well as the combined fingerprint reader and wireless charging back cases. Both back cases have been shipped off to be manufactured now, which means that we’ll see the finished versions in the near future. The lead time on the chosen fingerprint sensor is currently 6 weeks, so that plus the manufacturing time means we should see the built prototype this summer. The LoRa module will enter assembly shortly after, but may become available for purchase at about the same time as the fingerprint and wireless charging back case.

![](/blog/images/fingerprint-576x1024.jpg) ![](/blog/images/FingerprintChargingCase-576x1024.jpg)

**Left: fingerprint reader / right: wireless charging coil and circuitry**

But let me back-track slightly; the new custom back case can house the wireless charging circuitry or the fingerprint reader. Both already work with the PinePhone. The wireless charging coil works because it is a ‘dumb’ peripherial, which doesn’t reqire any code to function, while the fingerprint sensor works thanks to the work by Zachary Schroeder. As some of you may remember, Zachary is the person who built the [original prototype](https://www.reddit.com/r/PINE64official/comments/jurehy/pinephone_fingerprint_scanner_update/) back case featuring a fingerprint scanner. [The code](https://github.com/zschroeder6212/tiny-i2c-spi#tiny-i2c-spi) already works and you are able to unlock the phone using your fingerprint. I suspect that this case will prove highly popular in the community. Also, since I know someone will ask, we will likely make it possible for you to obtain both the charging coil and fingerprint reader without purchasing two separate cases. The beauty of the PinePhone is that it allows for this sort of functioning. Lastly, I can well imagine that someone will probably find a way to cram both peripherals into the single case, but we do not officially support such a combination. 

{{< youtube id="zkhFI3HmWKw" >}}

**PinePhone opened using fingerprint reader**

## PinePhone Software \[by Bhushan, Dalton, Biktor and Konrad\]

_Plasma Mobile - by Bhushan_

After the image was shipped to the factory several important changes were made in Plasma Mobile upstream. For one, Jonah Brüchert removed the workarounds added for angelfish, as a result the angelfish browser performance was improved quite a lot. Moreover, Devin Lin and Marco Martin made several changes in the user interface, like the top sliding panel that can be opened in 2 stages, and various other visual improvements.

{{< youtube id="ubP6VDwxZr0" >}}

**The performance of Angelfish is really quite impressive**

On the low-level side, there's an ongoing effort to improve the modem stability from the kernel side - you can read more about this in the [bugtracker](https://invent.kde.org/teams/plasma-mobile/issues/-/issues/3). There is also pending work in progress [patch](https://gitlab.freedesktop.org/NetworkManager/NetworkManager/-/merge_requests/773/) from NetworkManager, which allows to connect to Mobile data easily when using Ofono based systems like Plasma Mobile and Ubuntu Touch. 

![](/blog/images/PlaMo-half.png)

**You can now pull down the top sliding panel partly (pictured) or fully**

If you want to stay up-to-date with Plasma Mobile news, you can follow [Plasma Mobile blog](https://www.plasma-mobile.org/blog), and if you would like to provide a feedback or report issues to Plasma Mobile team, the please create an issue at https://invent.kde.org/teams/plasma-mobile/issues or head to o[ur chat rooms](https://www.plasma-mobile.org/join/). 

_Ubuntu Touch - by Dalton_

I've seen some sentiment in the community that Ubuntu Touch for the PinePhone is not being worked on -- and that could not be further from the truth!

Our big project at the moment is updating from the pine64-org kernel that many projects maintained for 5.6 to megi's 5.10 or 5.11 kernel. This has been months coming, but we can see the light at the end of the tunnel. We've almost got all of the phone's hardware working on the new kernel as well as or better than the old kernel. There are some great improvements coming with this update:1) Improved mobile network reliability; 2) Hardware-accelerated camera viewfinder -- it's no modern Android phone, but it's much improved! 3) Call audio works much more reliably.

There are still some things to take care of, though. For example, it fails to boot very occasionally, instead sitting at the splash screen. This has caused many users to reflash their devices, expecting it to be broken when really they just needed to reboot. Obviously not in a releaseable state.

{{< youtube id="ZgkSSVS2OYU" >}}

**Performance with the updated kernel is really good**

If you want to try out the new shiny after the more extreme issues are resolved, you should switch to the "Development" or "Release Candidate" channels in Ubuntu Touch. If you'd like to test out the absolute newest, though, join us in the "kernelupgrade" channel! You can switch update channels on your device by browsing to Settings -> Updates -> Update Settings (at the bottom of the screen or a gear in the top right corner, depending on your current Ubuntu Touch version) -> Channels. Select a new channel there and give your device some time as it downloads the new update. If the Settings app seems stuck, make sure the screen stays on and it stays in focus. Once the download has finished, you will be able to browse back to the Updates page and click Install on the downloaded update.

_Modem part 1 - by Biktor_ 

Work on the open source user space side of the modem had led to three milestones these past few weeks: better power handling and thermals, and reliable AT interface as well as GPS.

As for the prior, first of all credit where it's due, the modem is already quite optimized in terms of power consumption, but being inside of a phone wasn't it's primary purpose. While the modem stays in low power mode when the Pinephone is asleep, it gets out of that mode when you turn on the screen. Latest changes to the userspace and kernel turn down CPU clock to 100MHz from stock's minimum of 400MHz, but also try to keep it at that frequency even when the phone is active. This means the modem now produces less heat and consumes less power in any scenario, while maintaining the same data transfer speeds.

As for the AT interface, the modem has two ways of communicating with the Pinephone - the QMI protocol and the AT interface. While the primary communication channel with the modem happens through QMI, userspace daemons also need AT commands to adjust some parameters, so this needs to be done to ensure all the different applications receive the responses they're expecting, and to provide additional functionality in the future. At this point most of the commands only emulate the expected response from factory firmware, but work is being done to reimplement all the needed commands and add some new ones that can be helpful.

Last but not less important, standalone GPS now works in the open source firmware, which brings feature parity with the stock firmware, allowing to direct the efforts to optimize and fix the remaining bugs.

![](/blog/images/PinePhoneModemMediaInterest-1024x718.jpg)

**The news of the modem running an open stack got media's attention - [article in screenshot](https://linuxsmartphones.com/hackers-develop-open-source-firmware-for-the-pinephone-modem-use-it-to-make-phone-calls/)**

_Modem part 2 - by Konrad_

My previous work on mainlining the modem has found its way into the now  released PMMS (PinePhone Modem Mainline Suite) - a set of scripts gathered from both other community members and created by myself. These scripts allow for quick deployment of the mainline kernel onto the modem. It is a non-destructive process, as the image is only "fastboot booted" and not written to the NAND. PMMS provides a set of prebuilt binaries, including a modified postmarketOS ramdisk, so that developers can quickly confirm whether it works on their devices and play around with the hardware via telnet. It's obviously not production-grade, but should things go well, the modem will be able to run the same - if not a newer - kernel version than the PinePhone itself... eventually. Presently it is only meant for development purposes and regular users should not attempt to run it.

## Pinebook Pro & PineTab

I am devoting the entirety of this section to discussing the Pinebook Pro and PineTab production outlook this year. If you’re interested in learning about Pinebook Pro software developments then please read the Pinebook Pro section in [last month’s update](https://www.pine64.org/2021/03/15/march-update/), where I listed some of the more notable recent developments. Back to the subject on hand; as many of you are probably aware, the [Pinebook Pro is currently available for pre-order](https://pine64.com/product/14%e2%80%b3-pinebook-pro-linux-laptop-ansi-us-keyboard/?v=0446c16e2e66) on the Pine Store, with an estimated shipping window late this month. Production is currently proceeding well and, unless we encounter unforeseen issues with assembly or dispatch in the next two weeks, many of you will be receiving your Pinebook Pros around this time next month.  

Moving forward, following the current batch, the production of the Pinebook Pro does look quite difficult. Many of the key components we require to assemble the laptops have either skyrocketed in price or are nowhere to be found. This forces us to actively monitor and evaluate production viability, and given the constantly changing market situation it is very difficult to predict when we’ll be able to schedule the next production-run. It could be as early as in two month’s time or much later in the year, or even early next year. There simply is no saying. Moreover, further price increases may occur, although we are very aware that the Pinebook Pro makes for a less attractive option at a much higher price-point.  

![](/blog/images/Mobian-PT1-1024x759.jpg)

**Don't worry, we know many of you want the PineTab back in stock**

The good news is that the current production-run is quite sizable, and there are still many units available (which I expect will last us for quite some time). That said, If you’re on the fence, but think you may want a Pinebook Pro eventually, then I strongly suggest you get one now. 

As for the PineTab, we’ve made it no secret that we’re prioritizing PinePhone production at this time. With very few available components, including the A64 SoC itself currently in short supply, we are opting to produce the much more popular device. Furthermore, if we were to open PineTab pre-orders at this time, it would have to be at a much higher price-point, which I believe makes for a far less attractive proposition. With all that said, we will seek to seize a window for a production opportunity opening this summer, and we will attempt to produce another batch of PineTabs. At present time it is impossible to tell if we will succeed in securing all the necessary components, negotiate sensible pricing, and ultimately offer the PineTab at an attractive price-point. 

Before I close this section off, I want to make it abundantly clear that while this is the outlook as of today, April 15th 2021, and it is a subject to change. While the situation may seem less than ideal, it may change any day. The situation is so dynamic that everything I wrote above may be completely invalid in a day, week, or month’s time. Stay tuned for updates.

## PineTime \[by JF & Brian (33YN2)\]

The activity on the InfiniTime project was quite intense these last couple of weeks. Firstly, we've finally [enabled the motion sensor](https://github.com/JF002/InfiniTime/pull/255), which allows to add step-counting and wake up on wrist rotation functionality, both of which are long-awaited features in InfiniTime. This is a major milestone as the motion sensor was the last part of the PineTime hardware that wasn't integrated into InfiniTime.

![](/blog/images/wrist_wake_up.gif)

**PineTime waking up on wrist rotation**

Once these features were finally enabled, we quickly realised that there is a need to allow users to enable and disable the wake up on wrist rotation, and for some kind of "Do Not Disturb" mode, where the vibrations of the notifications could be disabled. It took only a couple of days for [Joaquim](https://github.com/joaquimorg/) to contribute to these functionalities and... a lot more! His pull-request named [BigRewrite](https://github.com/JF002/InfiniTime/pull/258) is basically a major rewrite of the UI, which adds a lot of functionality, settings as well as apps to InfiniTime. Here's a summary of his work: 1) Visual changes and improvements; 2) New UI navigation - swipe up to open the notifications, swipe right to open the new "quick action" menu, swipe down to open the applications menu; 3) The quick action menu allows the user to set the display brightness, disable notification vibrations and enter into the settings menu; 4) This settings menu allows users to configure the display sleep timeout, how the device can be woken up, the time format (12/24h), the default watchface and much more; 5) The watch can be woken up by a single or double tap on the display, or by wrist rotation; 6) The settings are saved in flash memory so they can be restored every time the watch reboots

This pull request is pretty big, but it brings so many features and improvements that we will work  to merge it as soon as possible.

![](/blog/images/bigrewrite-1024x773.jpg)

**A sneak peek at the new user interface**

Now, there is no need to rush to the release page to find a new version of InfiniTime to flash on your device, as those changes have not yet been released. All these changes mean a lot of modifications to the code, and we are still in the process of fixing integration issues and bugs, as well as ensuring users will be able to install this new version without any issue on their devices. This will take some time, but we'll do our best to release a new version by the end of the month. I’ll make sure to notify you all, here on PINE64’s blog, once our first firmware release goes live - so stay tuned for that. 

In the meantime, I would like to thank everyone who's helped with these developments. Joaquim did a tremendous job with the UI refactoring, and many other people helped testing the new features, fixing I²C bugs, measuring power consumption, and also encouraging the whole team to continue their hard work - it really shows how helpful and dedicated our community is!

Companion apps developers were also busy these past few weeks. In the last community update, I introduced [Siglo](https://github.com/alexr4535/siglo), a GTK based companion app for the PineTime which, at the time, was able to sync the time of the watch. Now, [Siglo 0.6.0](https://github.com/alexr4535/siglo/releases/tag/v0.6.0) supports multi-device functionality, allowing the user to choose which PineTime it should connect to (useful for people working on multiple dev kits and sealed devices). Moreover, you can now easily update your PineTime thanks to the integration of the OTA (Over-The-Air updates) and the Quick Deploy Mode, which allows users to query github releases and let them choose, pull and flash assets all from within the app!

{{< youtube id="mVz-ivOosOs" >}}

**Siglo v0.6.0 by Alex Robinson - [original video](https://twitter.com/AlexRob12252696/status/1381789518790033408)**

We also welcome a newcomer in the PineTime ecosystem - the [PinetimeFlasher](https://github.com/ZephyrLabs/PinetimeFlasher) is a GUI app to help flash firmware into the PineTime using OpenOCD on Windows. It's written in Python using PyQT5. This project is at its very beginning, but I trust Electr0Lyte to continue working on this app in the near future.

![](/blog/images/PineTimeWindows-1024x625.jpg)

**Flashing PineTime on Windows 10 - via [Sravan Senthiln](https://twitter.com/SravanSenthiln1/status/1379734867089399810?s=20)**

Last but not least, [WaspOS](https://github.com/daniel-thompson/wasp-os) has seen some recent interest from developers, with work in progress feature pull requests such as a screen timeout setting, weather application, and a new phone application for showing incoming calls. Aside from that, two notable features that managed to be merged include a new word clock application, and the ability for wasptool to read battery levels. There's also been a few minor bug fixes and improvements.

## Pinecil

It is safe to say that the Pinecil has reached an unprecedented level of success - no matter how many we produce — and trust us, we produce many units — they immediately get snatched up. In terms of volume of units sold per day, the Pinecil is only second to the SOPine - and that is an industry-oriented device where orders frequently range in 10k+ units per order. To this end, we’ll strive to produce large batches of the Pinecil at regular intervals - at least for as long as the necessary components are available. The next production run of the Pinecil should be available any day, and many of you will surely be glad to hear that a number of cool accessories will be available at check-out this time around. 

Those of you who visited the Pine Store on April 1st were likely amused to find the Mjolnir hammerhead tip for the Pinecil in the inventory. This was obviously an April fools joke, but there is the plot twist - a Pinecil hammerhead has been in the works for some time now and will be available for purchase soon. The accessory offers a large surface area capable of heating a sizable area of a PCB. The primary function of the hammerhead is desoldering surface mounted PCB components, but I can imagine it also being used for a number of other applications. I don’t currently have an ETA for the hammerhead, but it should find its way into the Pine Store this month. 

![](/blog/images/PinecilHammer-1024x766.jpg)

**See, we told you, it is real!**

Many of you will also be thrilled to learn that a transparent Pinecil case will be available once the new production-run becomes available for purchase. Many of you have requested a transparent case for some time now, and we are happy to finally make it happen. That said, we haven’t yet decided if the transparent case will become a permanent addition to the store’s offering - so if you really want one, then I suggest you get one now. 

![](/blog/images/SeethuPinecil-1024x643.jpg)

**The transparent silicon grip is a nice touch, don't you think?**

Lastly, we will also offer a thermal isolation mat (pictured above) and a high quality heat-resistant USB-C power cable capable of delivering 4A power. The mat and cable are both capable of withstanding exposure to a temperature of 350\*C, and I personally think both are great accessories for anyone doing substantial amounts of soldering with their Pinecil. The cable is particularly interesting, as it is completely custom made to our spec and will be the first cable with such heat resistance on the market (at least to our knowledge - but we first attempted to source a cable such as this, and came up empty handed). I don’t presently know when exactly these items will be available in the Pine Store - possibly at the time of publishing or sometime soon after. 

## LoRa 

As I mentioned in the February community update, and as I’ve been alluding for nearly 6 months, we’re very interested in using LoRa and LoRaWAN for connectivity in PINE64 products. I invite you to read the [February update](https://www.pine64.org/2021/02/15/february-update-show-and-tell/) to learn about some of the things we’ve envisioned for the future. At this stage we internally already have a detailed and extensive roadmap for our LoRa implementation, which you can expect to unfold over the course of next 6 months. I’ll be sharing details as things start taking shape; there are other parties than just ourselves, so as much as I’d like to explain everything outright I also need to consider others who are involved. I trust you all understand. 

Above you see a picture of an open PINE64 indoors LoRa gateway. Before moving onto discussing what’s actually there in the picture, let me just quickly mention that an outdoors version will also be available with an aluminium, rugged and water resistant case. As a base for the gateway we use the PINE A64-LTS, fitted with a purpose built hat (adapter) which choses the LoRa module by RakWireless. If you’re a LoRa aficionado, you’ll be happy to hear that the chosen chipset is the modern SX1302, offering increased range and speed over its predecessors. The module interfaces with the PINE A64 LTS via the SPI interface, and as you can tell from the picture we have two leads to the outside of the casing - one for LoRa the other for GPS.

![](/blog/images/InsideLoRaGateway2-921x1024.jpg) ![](/blog/images/InsideLoRaGateway.jpg)

**Internals of PINE64 LoRa gateway prototype**

Over this past month we built up a handful of these prototype LoRa gateways and shipped them to (sometimes unsuspecting) developers with an interest in the field of communications. While they work on getting the gateways up-and-running, we’ll be turning our attention to the end-nodes. I have already mentioned the LoRa back case for the PinePhone earlier in this update, but we’re also working on a standalone USB dongle-type end-node adapter, a PineTab adapter as well as a SPI module, which can also be configured as a USB LoRa dongle. We will also be releasing a LoRa stick powered by a single 18650 battery. It will use the BL602 WiFi/BLE RISC-V module (currently being open sourced in the [Nutcracker Challenge](https://www.pine64.org/2020/10/28/nutcracker-challenge-blob-free-wifi-ble/)), and can be fitted with GPS, an low-power OLED panel and additional sensors.  All the end-nodes will be using the SX1262 chip. 

![](/blog/images/USB-LoRa-1024x655.jpg) ![](/blog/images/LoRa-something-839x1024.jpg)

**Left: USB LoRa end-node / Right: SPI, breadboard compatible end-node**

But this is just the beginning. We’ve got more LoRa-related products in the pipeline. In the meantime, I am attaching a video by [Privacy & Tech Tips](https://www.youtube.com/channel/UChVCEXzi39_YEpUQhqmEFrQ), who made an overview of the kit we sent him earlier this month. Lastly, [Discord](https://discord.gg/pine64), [Telegram](https://t.me/pine64lora) and [Matrix](https://matrix.to/#/#pinelora:matrix.org) chats for LoRa on the PINE64 platform should be added at the time this community update goes live, or shortly afterwards.

Lastly, we're looking for a name for the LoRa project and we're open to ideas; please leave them in the comments section below.

{{< youtube id="cJ0wpANpbyc" >}}

That's all for this month’s update, I’ll catch you next month!
