---
title: "April update: no more unicorns"
date: "2022-04-15"
authors: ["Lukasz Erecinski"]
categories:
  - "news"
  - "pinedio"
  - "pinephone"
  - "pinephone-pro"
  - "pinepower"
  - "pinesound"
  - "pinetime"
tags: 
  - "pinephone-keyboard"
  - "pinepower"
  - "pinesound"
  - "quartzpro64"
cover: 
  image: "April-Update-No-More-Unicorns.jpg"
images:
  - "/blog/images/April-Update-No-More-Unicorns.jpg"
---

![](/blog/images/April-Update-No-More-Unicorns.jpg)

This month’s update is packed to the brink with news: the product team is negotiating restarting Pinebook Pro production, QuartzPro64 will be heavily subsidized and developer sign-ups are now open, we’re introducing the PineSound project, and PinePower power supplies will be making a return to the Pine Store soon. I cannot recall the last time I had so many positive things to report on, so let's get to it. 

You can watch the synopsis of this month’s community update on YouTube (embedded below) as well as on [Odysee](https://odysee.com/@PINE64:a) and [PeerTube](https://tilvids.com/accounts/pine64tilvids/video-channels). To stay up-to-date with PINE64 news make sure to subscribe to this blog (subscription widget at the bottom of the webpage), follow the [PINE64 Telegram News channel](https://t.me/PINE64_News), the [announcements channel in Discord](https://discord.gg/pine64) as well as our [Twitter](https://twitter.com/thepine64) and [Mastodon](https://fosstodon.org/@PINE64).

I’d like to thank [JF](https://twitter.com/codingfield), [Peter](https://twitter.com/linmobblog) (LinMob), [Alex](https://twitter.com/AlexRob12252696) (clover), [Brian](https://mastodon.online/web/accounts/61817) (33YN2), and [PizzaLovingNerd](https://www.youtube.com/channel/UCmGcm7dhEjS9CIOsOOv8y6w) for their contributions to this community update.

**N.B.** Comments on the blog post need to be in English and follow our [Community Rules and Code of Conduct](https://forum.pine64.org/showthread.php?tid=13209).

{{< youtube id="hl3lFWzFMco" >}}

**Video synopsis of the April community update**

### TL;DR

- Housekeeping
    - Go back and read the April fool’s post prior to continuing with the update
    - Quarterly community Q&A April 15th, join in and ask your question
    - PINE64 EU launches on May 10th
    - Product team negotiates resuming Pinebook Pro production
- QuartzPro64
    - QuartzPro64 is now in production 
    - Dev order system open for those who want to get their hands on the device early
    - We subsidize the QuartzPro64 for devs - selling it for $150
    - Dev boards do not have CE or FCC 
- PineSound
    - Introducing the PineSound community driven project 
    - PineSound dev board soon to be allocated to devs; will be available broadly at a later point in time
    - PineBuds are the first product based on the dev board; prototype exists and works
    - PineBuds include many common high-end wireless earphone features and allow end-users to flash their own firmware easily
- PinePhone (Pro)
    - Next production run on the PinePhone (Pro) keyboard on the way
    - Many improvements to keyboard driver, particularly with respect to charging
    - postmarketOS and Mobian decide to use Tow-boot
    - Elementary OS is considering porting to the PinePhone Pro (and Pinebook Pro?)
    - PinePhone Pro Wiki documentation gets a major overhaul thanks to multiple contributors
    - Linuxphoneapps.org quietly launched late March; works well when using Firefox on the PinePhone
    - Many tweaks and improvements are landing PlasmaMobile in the coming weeks and moths
- PineTime
    - InfiniTime 1.9 launched with many improvements, fixes and a new watchface. 
    - InfiniSim, now a part of the project, and in sync with InfiniTime 
    - InfiniTime merge requests discussed
    - InfiniLink for iOS is no longer maintained - someone willing to step up and maintain the project? 
- PineDio
    - Improvements to the USB and PinePhone PineDio LoRa case drivers
    - InfiniTime ported to PineDio STACK - a good starting point for further exploration
    - Documentation underway 
- PinePower
    - PinePower desktop and mobile will be making a return to the store shortly
    - PinePower desktop improvement: USB grounding as requested by many Pinecil users
    - Portable PinePower receives a substantial redesign meant to help with staying put in North American main socket 

## Housekeeping

In case you missed it, we ran a little [April fool’s spoof](https://www.pine64.org/2022/04/01/introducing-the-pinebuds-and-pinepod-seriously/) at the beginning of the month. I must admit that I am not a fan of the April fool’s tradition and we, as a project, haven’t really dabbled in pranks before. So, then, why did we publish the post and why am I mentioning it now? - because, as with any good joke, the April fools post contained an element of truth to it. More on this later on the update, seriously. 

It is time for the second community quarterly Q&A. If you’re reading this on the day of the community update’s publication, then make sure to stick around and join in later today/ tonight on [Youtube](https://www.youtube.com/c/PINE64inc), [Discord](http://discord.gg/pine64) or [PeerTube](https://tilvids.com/a/pine64tilvids/video-channels). We’ll be going live at 19:00 GMT/ 12:00 PT. The point of the Q&A is for us to take questions live and answer them then and there. I’ll be taking questions live from the chats - you have a choice of [Discord](http://discord.gg/pine64), [IRC](https://wiki.pine64.org/wiki/Main_Page#Chat_Platforms) and [Telegram](https://t.me/pine64QA). From [previous experience](https://youtu.be/tORlxpzmF3U) I know that the chat will more than likely turn into a wall of text in a matter of minutes - I therefore ask that you ‘at’ me (@lukasz) before writing your question, otherwise I will more than likely miss it. I will likely bring in developers to answer questions too - make sure to ping people you direct questions to. Once the Q&A is over we'll head over to one of the casual voice chats and hang out for the rest of the evening. I hope to see you there.

{{< youtube id="tORlxpzmF3U" >}}

**In the event you missed it, we held the first quarterly Q&A we held in January**

We have upgraded the [main PINE64](https://app.element.io/#/room/#pine64:matrix.org) and [PinePhone](https://app.element.io/#/room/#pinephone:matrix.org) Matrix channels. Both of them previously ran version 1 of the Matrix protocol and this caused us all sorts of headaches, including moderators randomly losing their powers and people who left being forced back into the home server. Needless to say, an upgrade had to happen sooner or later. The new rooms now run version 6 of the Matrix protocol which will alleviate all the aforementioned problems. An unfortunate side-effect of the upgrade is that everyone who was part of the original channels will need to manually rejoin. An invite link is present in the original groups. 

As some of you noticed, there was no new [PineTalk](https://www.pine64.org/podcast/) episode last month. Those involved in the production of the podcast were busy with real-life things and simply didn’t get the chance to record. I’ve spoken to Brian and Justin and they both confirmed that a new episode will be coming later this month. If you haven’t done so yet, make sure to subscribe to [PineTalk’s RSS feed](https://www.pine64.org/feed/mp3/). 

The product team is in advanced talks with a factory regarding resuming production of the Pinebook Pro. As I’ve promised countless times in the past, I’ll keep you updated on the progress regarding restarting the laptop’s production. I’m told the team is etching closer to strike a deal and that the production circumstances will require some alterations to parts of the hardware - keep an eye on our social media and news channels in the coming weeks.

![](/blog/images/PINE64-EU-Bundles-screenshot.png)

**Yes, there will be bundles**

Lastly, I am thrilled to let you know that [PINE64 EU](http://pine64eu.com) will be going live on May 10, 2022. By the time you read this, the Polish state should already have listed PINE64 EU as a registered company and all required paperwork should be in place to start sales. The website and logistics are also all ready to go. However, I am still awaiting approval from the debit/credit card payment gate, which takes a long time. I am also waiting for the hardware itself. With less than a month to go, I’ll be posting frequent updates on the store’s [Twitter](https://twitter.com/pine64eu) and the newly set-up [Telegram news](https://t.me/pine64eu) channel. I don’t foresee any issues at this stage, but should any problems arise (I am thinking about customs in particular) I will make sure to communicate it publicly via social media. Telegram and Twitter is where you will find all future communication from PINE64 EU.

## QuartzPro64

Last month we outlined our plans for the next generation of Pro-grade PINE64 hardware - the QuartzPro64. In case you missed the original announcement, the QuartzPro64 is a powerful development board featuring an 8 core SoC which comes paired with 16GB of RAM and 64GB of expandable eMMC flash storage as well as an impressive array of IO options. I’m not going to repeat the entire spec list below since it was covered in detail last month - if this is news to you, then I suggest you go back and read the [March update](https://www.pine64.org/2022/03/15/march-update-introducing-the-quartzpro64/) and pick up reading this section after.

![](/blog/images/fixed_QuartPro64_PCB_front-min-1024x1019.jpg)

**Unpopulated PCB of the QuartzPro64**

Today I am happy to let you know that the QuartzPro64 will soon be available for order via our developer pre-order system. To get your hands on a unit you’ll need to fill in a short questionnaire, similar to the one PinePhone Pro developers submitted at the end of 2021. This will help us determine if you’re the right person to receive the hardware prior to software running on the new platform. Conversely, it will help keep these development boards out of the hands of end-users and application developers. More on this in a bit later. So, then, if you are a developer with an interest in the RK3588 platform, and wish to get an early start on a board that exposes nearly all of the SoC's available IO, then please make sure to **head** **over to the** [**developer sign-up page**](http://preorder.pine64.org/) **to register your interest**. 

Now let me level with you - the BOM of the QuartzPro64 is north of $300. The price is dictated not only by the (rather pricey) SoC, RAM, and eMMC flash but also by the exhaustive list of the exposed IO. As I’ve explained in last month’s post, we didn’t want to compromise on the IO due to the assumed target audience; it is hard to debug and ultimately enable a feature if said feature isn’t physically present on the PCB. But at the same time, we do have a vested interest in a good uptake of the board among the development community. I’d go as far as to say that we hope for the QuartzPro64 to become _the_ go-to board for RK3588 development. A decision has therefore been made to heavily subsidize QuartzPro64 so that the price of the board doesn’t prevent people who wish to be a part of the development process from getting one. After some deliberation, we decided to sell QuartzPro64 for $150 to developers who file an application. Needless to say, we hope to see many applications in the coming days.

![](/blog/images/Rockchip-RK3588-SoC.png)

**RK3588 block diagram**

Please note that it will take us time to review all applications and issue approvals. Once the first set of candidates has been determined we’ll then send out purchase coupons. Coupons are valid for a period of two days, then they expire. From previous experiences with the PinePhone Pro and the PineNote, I expect that we’ll send out 2-3 rounds of coupons - so if you do not receive one initially then don’t fret, there is a chance you’ll be included in the second or third round of coupon dispatches. Application rejections will be issued after all applications are reviewed and all QuartzPro64 boards have been allocated. 

Before I wrap this section up, I’d like to make it clear that these boards will not be FCC or CE certified. While, technically speaking, single board computers aren’t required to have such certifications in most places, we always make sure to certify our boards when moving into production. However, QuartzPro64 boards aren’t currently produced in a quantity that would warrant us to start such a certification process. They are meant for the development community and should be viewed as prototype hardware. In some countries you need to register with your local authority to receive uncertified prototypes, elsewhere there is no such registration requirement, and yet in other countries you outright cannot receive uncertified electronics equipment; please make sure to check your local regulatory guidelines prior to submitting your application. 

## PineSound

At the end of last year, in the [December community](https://www.pine64.org/2021/12/15/december-update-a-year-in-review/) update, I teased the launch of _(...) a cool small project into our lineup. Let me first clarify what ‘small’ means in this context: a small project is limited in scope and completely community-driven. Examples of such existing PINE64 projects include the Pinecil and PineTime“._ As I’ve mentioned in the _Housekeeping_ section, the [April fool’s post](https://www.pine64.org/2022/04/01/introducing-the-pinebuds-and-pinepod-seriously/) from earlier this month did in fact include some real information. While we won’t be making plush unicorns with mics sticking out their heads anytime soon, we have been prototyping a set of end-user flashable wireless earbuds. But let me backup a bit. Today we’re introducing the PineSound board; a development platform for earbuds and a digital audio player, utilizing the Bestechnic _BES2300_ Bluetooth 5.0 audio chip. We will initially distribute the PineSound dev boards to developers whom we know are particularly interested in non-Linux projects such as this. In time, however, the PineSound dev board will be made available to anyone interested in developing on the platform or even using it in some DIY audio project. The board features 2x coaxial & optical input (left) and output (right), a standard 3.5mm headphone jack, 4.4mm and 2.5mm balanced jacks, an SMA connector, USB-C as well as touch and LCD ports. 

![](/blog/images/PineSound_Dev_board-1024x513.jpg)

**The PineSound dev board (v1.0)**

Before we get into the specifics of the PineSound project I want to explain its placement in our lineup, and talk a bit about the importance of the development community’s interest in the hardware. The approach we’ll be taking is, in a sense, very similar to how we handled the PineTime and the Pinecil. This means that the success will largely depend on whether a community grows around the platform. As we did with PineTime, we will allow the development community to help set the course of the PineSound project. All important decisions, such as moving from development to production, the production itself, opening sales, etc, will be coordinated and discussed with the community. We recognize that working closely with developers and the community is critical in projects such as this - while the PineTime and Pinecil are now hallmarks of PINE64, we need to acknowledge that the PineCube has been largely a failure. The general lack of interest in the PineCube can, at least in some part, be ascribed to a failure on our part to facilitate community building around the device. We’ve learned from this experience and have done everything on our end to assure that PineSound as a whole is a success from the get-go. 

![](/blog/images/PineBuds-prototype-seriously-1024x815.jpg)

**See, they're real. Seriously.**

The first device to be introduced based on the PineSound dev board will be the PineBuds wireless Bluetooth earbuds. What I wrote in the April fool’s post about the buds is accurate - they offer features found on high-end in-ear headphones, such as ambient and environment noise cancellation, and long battery life. They have 6 microphones total, 3 on each bud, as well as touch-based input situated on the external side of each bud. We designed the cradle which houses the earphones so that custom user-created firmware can be flashed. The cradle has built-in UART used for firmware flashing, which is automatically exposed when it is connected via USB to a computer. There will be a wide variety of things developers and (eventually) end-users will be able to do with the earbuds - flash custom sound signatures, determine touch controls, adjust resonance to fit the user’s ear canal resonance and even turn the PineBuds into hearing aids. The last application is particularly interesting - the BES2300 is one of just a handful of chips considered for use in ‘over the counter hearing aids’ by various regulatory bodies. 

![](/blog/images/PineBuds_late_prototype-1024x768.jpg)

**A peak inside - picture of an early engineering prototype**

[Ben (Ralim)](https://twitter.com/RalimTek), probably best known as the creator of [IronOS](https://github.com/Ralim/IronOS), has had his hands on the prototype for some time. Here is what he had to say when I spoke to him earlier this week: 

_“I think of the buds as (...) \[a\] good working device, that the community can hack on and tweak, \[while of\] the Dev board as the experimentation setup for exploring this chip and finding out just how powerful it is. \[T\]here are some binary blobs in the firmware around Bluetooth \[and\] some for voice assistants (but I don't know if we would ship them). But it was in a compilable and runnable state with fairly complete hardware drivers. I see it a bit like the bl602, where we have a working SDK with some blobs, but the hardware is very good for hacking on. The main MCU so far is quite powerful and battery efficient. Flashing is easy over a UART serial port \[too\].”_ 

It is clear that the hardware has a lot of potential from both developers’ and end-users ' perspectives, and I hope that the project garners some interest from the community as a whole. More information about the PineSound will follow next month, so keep a lookout for news.

## PinePhone (Pro) \[by Lukasz, Peter & Brian\]

A new production run of the PinePhone keyboard case is now underway and should be available soon. The keyboard case has proven to be a very popular accessory, and therefore the initial production run sold out quicker than other optional back cases currently offered for the PinePhone and the PinePhone Pro. We expect that the new batch will last us 2-3 months, so if you’ve been eagerly waiting to get your hands on a unit then there should be no problem in obtaining one. On the subject of the keyboard case, the [IP5XXX\_POWER (keyboard power) driver](https://github.com/smaeul/linux/commits/wip/pp-keyboard) by the developer Samuel Holland has now been upstreamed. A handful of fixes are also coming (or have already arrived, depending on distribution) to improve battery operation and charging of the PinePhone (Pro) when paired with the keyboard case. When charging, the new algorithm will strive to charge the phone’s internal battery as fast as possible first, and only then start charging the keyboard case. During operation, the keyboard case will only start charging the phone’s internal battery when it is nearly depleted. It will try to maintain a 20% charge of the phone’s internal battery. The new driver will also provide a set of triggers to notify the user via the phone's LEDs about the status of both batteries. I suggest you read the developer [Megi’s blog post](https://xnux.eu/log/#065) to learn all the details. 

{{< youtube id="9VWoK9oKsw0" >}}

**Keyboard case production - a short video from the factory floor**

![](/blog/images/PP_KB_Charging-1024x501.jpg)

**PinePhone and PinePhone Pro with keyboard case charging - picture by [Megi](https://xnux.eu)**

In other news, postmarketOS and Mobian have made the decision to use Tow-boot as opposed to u-boot with their distributions. In the case of the PinePhone Pro, this means that end-users will be required to flash Tow-boot on their devices prior to using these OSes. I wrote at length about Tow-boot in [last month’s update](https://www.pine64.org/2022/03/15/march-update-introducing-the-quartzpro64/) if you wish to learn more about it and its application on both the PinePhone and the PinePhone Pro. The [Mobian team writes](https://blog.mobian.org/posts/2022/03/30/universal-images/): _“by letting users install the bootloader themselves, either on the SPI flash (...) or the eMMC’s boot partitions (...), we can stop embedding our own copy of the bootloader. (...) Both new and existing users should install Tow-Boot or a similar system to provide updates to their boot firmware. \[Using Tow-boot\] will be required on new installs using images generated after 2022-04-02.”_ 

![](/blog/images/PinePhone_elementary_os-956x1024.png)

**elementary OS on the PinePhone Pro? yes please!**

On the subject of mobile Linux OSes, many of you will be happy to learn that elementaryOS are exploring the possibility of bringing their OS to the Arm platform and, in the future, also the small screen of Linux smartphones. The development is currently targeting the PinePhone Pro - a sample unit was delivered to [Danielle](https://twitter.com/DaniElainaFore) from elementaryOS earlier this month. It is worth noting that the team already has some experience with the RK3399 SoC and our platform as they have - in the past - attempted to bring [elementaryOS to the Pinebook Pro](https://blog.elementary.io/elementary-os-on-pinebook-pro/). As a side-note, elementaryOS on the Pinebook Pro is something I’d still very much like to see - fingers crossed. I spoke to Danielle this week and she had this to say: _“Mobile Linux is coming and the time is now to be planning and developing. PinePhone Pro is a really compelling developer platform and I’m excited to start working with a whole new world of open source apps and operating system.”_ I wish Danielle and elementaryOS contributors the best of luck with this endeavor; we’ll be keeping our fingers crossed for yet another mobile Linux OS option to see the light of day. 

In other news, the [documentation of the PinePhone Pro](https://wiki.pine64.org/wiki/PinePhone_Pro) on the PINE64 Wiki was growing steadily in the last couple of days thanks to the relentless work of multiple community members. In summary, the "State of the Software'' section on top of the PinePhone Pro article now received a graphical overview table of the current software stability and functionality, which makes it easier for users to get an overview of the overall software state without having to collect the information from multiple locations such as bug trackers. The overview also contains notes regarding bugs or details, which might impact the functionality of a specific feature. Of course, this enumeration does not make a claim to be complete in any way but should ease the search for related information considerably. The table can be found under [https://wiki.pine64.org/wiki/PinePhone\_Pro#State\_of\_the\_software](https://wiki.pine64.org/wiki/PinePhone_Pro#State_of_the_software).

![](/blog/images/PPP_Matrix-1024x735.png)

**A functionality matrix has been added to the [PinePhone Pro Wiki](https://wiki.pine64.org/wiki/PinePhone_Pro) section**

The software section of the PinePhone Pro article, which was extended gradually, was rewritten as well to bring a more coherent information section with all relevant information. The section should now be considerably easier to read, especially in the parts, which were causing confusion in the previous instructions. Aside from a large number of improvements, the section now also received a dedicated troubleshooting subsection and numerous new information. The section can be found under [https://wiki.pine64.org/wiki/PinePhone\_Pro#Software](https://wiki.pine64.org/wiki/PinePhone_Pro#Software). As it is often asked where bugs can be reported and how projects can be supported, new articles regarding [where to report bugs](/documentation/Introduction/Where_to_report_bugs) and [how to contribute to projects](/documentation/Introduction/How_to_Contribute) were started as well, which will be gradually improved and extended over time. In this context it can be noted that all community projects are happy about any form of contribution. Knowledge of coding is not required, instead there are various ways to contribute to projects, for example with designs, ideas, translations, documentation, through hardware or with creative work, or by simply being a positive member of the community. On this note, I want to thank everyone for their unremitting help. Without your contributions, the community would simply not be what it is today.

There is one more noteworthy piece of information concerning documentation of mobile Linux software: [LinuxPhoneApps.org](https://linuxphoneapps.org) finally quietly launched at the end of March. It [lists](https://linuxphoneapps.org/apps/) all the apps that were (and still are) listed on LINMOBapps. The list is presented in a way that is more friendly to PinePhone's Firefox browser, preventing it from asking whether it should kill the script that slows things down. The list now has more apps, with more being added slowly but steadily. Note that not all apps are packaged for your distribution nor are they all to be considered feature-complete. If you want to follow, join or help out the further development of the site, check out the [LinuxPhoneApps FAQ](https://linuxphoneapps.org/docs/help/faq/).

On a final note, Plasma Mobile will be seeing several bug fixes, lots of optimizations, and a few new features in the coming releases. The mobile data toggle has been fixed so that the setting is remembered across reboots, a virtual keyboard toggle has been added to the quicksettings panel, the ability to reorder the quicksettings menu has been added, there have been various animation fixes, shrink and grow animations have been added to the shell buttons and homescreen, work has been done to start implementation of custom homescreens (though this is not yet finished), the media widget in the quicksettings panel now supports multiple video/audio sources by swiping left or right, the lockscreen has received a new notification widget, the APN settings menu received several UI fixes, the panel’s opacity logic has been fixed, and spacebar has received several fixes to its UI alongside some bug fixes. Most notably work is planned for a lockscreen shell overlay that would handle incoming calls and alarms, and give users a nice fullscreen overlay to interact with, although this is still in the planning stages.

## PineTime \[by JF\]

The InfiniTime team released a new version of the open-source firmware for the PineTime at the beginning of April. The first new feature you'll notice in [InfiniTime 1.9 "Limeberry"](https://github.com/InfiniTimeOrg/InfiniTime/releases) is the new Terminal watchface! This original watchface displays the date, time, battery level, steps, heart rate, and BLE status as if they were printed on a console terminal. It'll more than likely please the geeks among us.

![](/blog/images/infinitime-terminal-768x1024.jpg)

**The new terminal watchface looks great**

A new feature allowing to disable the BLE connectivity was also added. This feature was requested by many users as it saves a bit of battery and increases the privacy of the PineTime. When BLE is enabled, the watch continuously broadcasts "advertising" messages allowing devices to detect and connect to it. It also allows some kind of tracking; when BLE is disabled, those messages are not sent and the watch is then "invisible" to anyone trying to detect it.

Those of you who use the heart rate sensor will be happy to know that we improved the accuracy of measurements of the heart rate sensor. Thanks to the [wasp-os team](https://github.com/daniel-thompson/wasp-os) for their help with this! The heart rate monitor now displays more sensible and reliable values - it has been [tested and approved](https://twitter.com/cartron/status/1512795875877310479?s=20&t=5zeyBIOgLf5iMJMdbhdLHw) by Nico!

![](/blog/images/PineTime-HR.png)

**The heart rate monitor is now much more accurate**

[InfiniSim](https://github.com/InfiniTimeOrg/InfiniTime#build-flash-and-debug), the InfiniTime simulator, is now also supported by the team and integrated into the CI. Each time a new PR is created and merged, the CI checks that the change builds in InfiniTime and also in the simulator. This will help maintain both projects in sync and ensure we don't break anything when changing something in either InfiniTime or InfiniSim. The new InfiniTime release also brings many improvements to notifications (call notifications won't vibrate forever when receiving a call) and to the Alarm app. The 12-hour time format is now better supported. You can read the whole release note and download the firmware on the [project page](https://github.com/InfiniTimeOrg/InfiniTime/releases/tag/1.9.0).

InfiniTime receives a lot of contributions from many users and developers, and I'm really thankful for that! Unfortunately, for various reasons we cannot merge and integrate each and every one of these features as soon as they are published by their author. One of those reasons is memory usage. As you may know, the PineTime is based on a small-ish MCU with 64KB of RAM memory and 512KB of flash memory. From my experience, this is a very comfortable amount of memory when compared to many other microcontrollers. But still, we have to be very cautious to not hit the memory limit if we want to be able to add new features and improvements in the future. That said, here's a highlight of some of those cool features I hope we'll be able to merge at some point in time. A feature that is often requested is the support for other languages and alphabets. New languages require a lot of memory for storing new fonts, which we cannot afford right now. But InfiniTime is completely ready to handle these, and [yehoshuapw](https://github.com/yehoshuapw/InfiniTime) proves it by maintaining a fork of InfiniTime that integrates Hebrew. A [new version](https://github.com/yehoshuapw/InfiniTime/releases/tag/1.9.0) of this fork was released a very short time after the release of InfiniTime 1.9. Kudos to the maintainer!

Watchfaces also need quite a lot of memory. The Infineat watchface is one of them - it is a very neat and well-designed watchface that uses the Pine64 logo to display the battery level!

![](/blog/images/infineat.gif)

**Infineat looks really neat!**

I also like this [QR Code application](https://github.com/InfiniTimeOrg/InfiniTime/pull/181), which displays 4 QR codes specified by the user via a BLE API. Those QR codes can be links to web pages, online accounts, and even vaccination certificates for COVID-19! Very cool.

![](/blog/images/qrcode-768x1024.jpg)

**An example QR code displayed on the PineTime**

Last piece of information for this month - I've learned that InfiniLink, the companion app for iOS is not maintained anymore. Here's the message its author, [xan-m](https://github.com/xan-m), wrote in the [last commit](https://github.com/xan-m/InfiniLink/commit/58c5caf23d18386e0618948515f7af28dac0b263) ‘Added localizations and goodbye message’:

_“I'm sorry to say that this will be the last update to InfiniLink. I started a new job a couple of months ago and no longer have the spare time to continue development of this project. If anyone is interested in taking over, please let me know and I can transfer everything over. Thank you for all of your support and suggestions along the way!”_

I would like to thank xan-m for their work on InfiniLink. Xan-m created the whole app from scratch and quickly proved that a companion app for iOS is definitely needed in the community and the PineTime ecosystem. Let's wish xan-m good luck in their new job, and I hope we'll meet again soon! So, who will take over the project to maintain the presence of our beloved open smart watch in the iOS world?

## PineDio \[by JF\]

[Lup](https://twitter.com/MisterTechBlog) and I are still actively working on the PineDio STACK with a double goal: check that the hardware is working as expected and to document our development environments. Lup is really good at documenting his experiments. He's currently writing an extensive article about running the [Apache NuttX RTOS on the PineDio STACK](https://lupyuen.github.io/articles/pinedio2?1) which I encourage you to read.

On my end, I'm working on porting InfiniTime to the STACK. This is quite easy as the display and touch panel are exactly the same as the one on the PineTime. I think InfiniTime will be a nice starting point to experiment with the STACK hardware: the RISC-V MCU (BL604), the LoRa radio, the GPS and secure module on the add-on board, etc. As you can see on the video below, the display driver is now functional and even works a bit faster than on the PineTime. It can go even faster when more memory is dedicated to the display driver.

See the [video here](https://video.codingfield.com/videos/embed/7b08f712-350e-4df2-985a-06ce46828bbf).

**InfiniTime now runs on the PineDio STACK - here's a quick comparison to the PineTime**

I've also upgraded my driver for the [PineDio LoRa USB adapter and LoRa PinePhone back case](https://codeberg.org/JF002/pinedio-lora-driver). Some changes were needed to support kernels > 5.10. Note that the driver for the CH341 chip (USB to SPI converter) also needs an update to support kernel 5.16. I [forked the driver](https://codeberg.org/JF002/spi-ch341-usb) to apply the changes until they eventually become approved in the [upstream repo](https://github.com/rogerjames99/spi-ch341-usb).

![](/blog/images/pinedio.jpg)

**The PineDio USB dongle**

## PinePower

Both the desktop and portable PinePower PSUs will be making a return to the Pine Store next month. I am glad to report that since the original units were in stock some improvements have been made to both designs. The desktop unit, often ordered alongside the Pinecil, has now grounding on the USB ports. This is a feature that many users have asked for. Otherwise the desktop power supply looks and functions just as the original iteration. The portable 65W PinePower has seen a more substantial physical redesign - the PSU itself has been shrunk slightly, making it overall more compact, and the overall physical dimensions have been altered along with internal weight distribution. The new design solves a problem that people in the US, using those tiny rectangular prongs for the mains socket; the original portable PinePower would sometimes not stay in place due to its weight distribution when plugged into a wall socket, while the new design does. I’m sure that this is a welcome redesign. 

![](/blog/images/usb-grounded-993x1024.png)

**The USB ports on the desktop PinePower are now grounded**

That’s all for this month, I’ll catch you all in May.
