---
title: "February update: chat with the machine"
date: "2022-02-15"
categories: 
  - "news"
tags: 
  - "modem"
  - "pinephone"
  - "pinephone-keyboard"
  - "pinephone-pro"
  - "pinetime"
cover: 
  image: "Feb_update_chat_with_the_machine_3.jpg"
images:
  - "/blog/images/Feb_update_chat_with_the_machine_3.jpg"
---

![](/blog/images/Feb_update_chat_with_the_machine_3.jpg)

As the Chinese New Year comes to an end and people return to work, production and shipping return to normal. More units of the PinePhone _Explorer Edition_, the PinePhone (Pro) keyboard case, the PinePhone _Beta Edition_ and all the other popular products will be dispatching in the coming days. In the meantime, we bring you exciting news concerning PineNote development progress, LVFS and fwupd for the PinePhone and PinePhone Pro’s and instructions on how you can modify your Pinecil to increase its performance further (at your own risk, of course).

Let's get to it!

You can watch the synopsis of this month’s community update on YouTube (embedded below) as well as on [Odysee](https://odysee.com/@PINE64:a) and [PeerTube](https://tilvids.com/accounts/pine64tilvids/video-channels). To stay up-to-date with PINE64 news make sure to subscribe to this blog (subscription widget at the bottom of the webpage), follow [PINE64 Telegram News channel](https://t.me/PINE64_News), the [announcements channel in Discord](https://discord.gg/pine64) as well as our [Twitter](https://twitter.com/thepine64) and [Mastodon](https://fosstodon.org/@PINE64).

I’d like to thank [JF](https://twitter.com/codingfield), [Alex](https://twitter.com/AlexRob12252696) (clover), Brian ([33YN2](https://mastodon.online/@BrianA)), [PizzaLovingNerd](https://www.youtube.com/channel/UCmGcm7dhEjS9CIOsOOv8y6w), [biktorgj](https://twitter.com/biktorgj), [Dylan Van Assche](https://dylanvanassche.be/), William Starkey ([ThanosTheTankEngine](https://twitter.com/thanos_engine)), [Caleb](https://twitter.com/calebccff) and [Samuel Holland](https://github.com/smaeul) (smaeul) for their contributions to this community update.

N.B. Comments on the blog post need to be in English and follow our [Community Rules and Code of Conduct](https://forum.pine64.org/showthread.php?tid=13209).

{{< youtube id="zGgt3dGdJzg" >}}

**Video synopsis of this month’s update**

**TL;DR**

- Housekeeping
    - CNY comes to an end; give shipping and support a few days to get back to their routine
    - First community Q&A was great fun; we’ll do better next time and include more chat protocols and potentially stream the event on multiple platforms
    - Malware shared again - do not install software from unknown sources onto your device
    - Beware of flood of counterfeit Pinecils 
    - PINE64 online store - PINE64 EU - opening in April/ May
- PinePhone (Pro)
    - Many orders of PinePhone Pro & keyboard case over CNY - shipping will resume shortly 
    - New keyboard case driver allows to check battery levels and set PinePhone charge rate (Wattage)
    - Plasma Mobile 5.24 released with multiple bug fixes, improvements and a new window / task switcher
    - Chat with the machine: newest community firmware by biktorgj for the modem brings ability to issue commands to the modem via SMS and phone calls
    - The community modem firmware can be now flashed and upgraded via fwupd thanks to work by Dylan
- PineNote
    - Plasma Desktop now runs on the PineNote with a grayscale UI theme; porting of first applications has began – you are invited and encouraged to join and contribute to the effort
    - postmarketOS has been ported to the PineNote; works well with a choice of Phosh or SXMO
    - Although much work is yet needed, we’ve reached the point where all device hardware works (thanks to work by smaeul and pgwipeout); new driver exposes all e-paper modes and EMR pen pressure works in Linux 
    - Work yet needed to enable GPU acceleration on the e-paper display (works with other output modes)
- Pinecil
    - New IronOS makes improvements to temperature regulation, so the Pinecil heats up faster and holds the temperature more precisely
    - A new MacOS and Window update utility for the Pinecil is now available - allows safe and easy flashing 
    - Pinecil VBUS mod allows the device to use 24V input safely
- PineTime
    - Work towards 1.9 release is ongoing; will include airplane mode, a new terminal-themed watchface and bug fixes
    - Documentation is being reworked
    - There is now a fully functional InfiniTime simulator that allows for easy experimentation and debugging on PC rather than hardware; JF is impressed by its capabilities
- PineDio
    - Issues with early PineDio STACK prototypes have been identified and ironed out thanks to work by JF and Lup
    - A new stock firmware for the STACK has been created and sent off to the product team; will not only allow end users a software platform to get started with the STACK but also allow product team to carry Q&A testing

## Housekeeping 

I’d like to start with a quick reminder that the Pine Store is just coming back to life following Chinese New Year. I am writing this a week prior to the update going live, and I have no insight into the support system, but from prior years experience I can make an educated guess that support has a hefty backlog to get through. I keep on getting pinged by people asking why their support tickets haven’t been answered, which leads me to think there are quite a few cases awaiting answers. I am asking you for patience - it will take time for support to work though the tickets, but they’ll get to yours eventually. Thank you for understanding. 

In case you missed it, we’ve held a live Q&A session on January 21. The session turned out to be a success with many people tuning in and asking questions. I was initially unsure how many people would be interested in participating, but it is clear to me now that there is a strong need for such a quarterly event in the community. I know that many questions remained unanswered and that more time for such as Q&A should be allocated next time. The next community Q&A is due in April, and we’ll make sure to do a better job planning the session out, making it more inclusive of other chat protocols and potentially also live-streaming it on multiple platforms. In short, we’ll make sure to be better prepared. You can watch the first community Q&A on [Youtube](https://www.youtube.com/channel/UCs6A_0Jm21SIvpdKyg9Gmxw), [Peertube](https://tilvids.com/accounts/pine64tilvids/video-channels) and [Odysee](https://lbry.tv/@PINE64:a). 

{{< youtube id="tORlxpzmF3U" >}}

**First quarterly community Q&A**

Throughout January we ran a survey asking people about their PinePhone use - now the results are in and published for anyone to view and dissect. Although ‘only’ 3079 people took part in the survey, I think that the results offer a glimpse into the most active portion of our community and offer an understanding of some overarching trends. The things that surprised me the most based on the responses are how many people daily drive their PinePhone, how popular SXMO is, and the relative indifference of a fourth of respondents to UI choice. If you haven’t done so yet, I suggest you head over and read the full [survey report](https://www.pine64.org/2022/01/31/pinephone-community-poll-results/).  

More malware targeting the PinePhone (and other devices) was shared in our chat rooms as well as our partner project chats these past weeks. I will not dwell on this topic as an investigation is already ongoing - I would, however, like to remind everyone to never download any file or archive from unknown origins onto your device. I refer you back to the [December community update](https://www.pine64.org/2021/12/15/december-update-a-year-in-review/) for more details.

Another thing that transpired the past month is an avalanche of counterfeit Pinecil soldering irons on popular internet outlets and shopping sites. As with any device that receives a lot of traction, copycat products are bound to emerge eventually. This is particularly true for conceptually relatively simple devices, such as the Pinecil, which makes them easy to copy. What makes these fakes more than just copies of the original is that they bear our logo on the box and feature inscription identical to that on real Pinecils. This is obviously a trademark violation and an attempt at tricking customers. It is only recently that these counterfeit Pinecils have spread like wildfire across popular online shopping sites, and that's why I’m addressing this issue publicly. There is a limit to how much I can say about this situation right now, but here’s a piece of important information - if you want to get an original Pinecil, make sure to look at the box (often present in online listings), since all Pinecils across all regions are sold in the same exact box as the one on the Pine Store. And no, we do not manufacture blue Pinecils.   

![](/blog/images/fake_pinecil.png)

**It looks like a Pinecil, it quacks like a Pinecil but its not a Pinecil**

Let us end this month’s housekeeping section on a positive note. As some of you have noticed, I’ve been around less these past two months. There are a few reasons for this, but the one of interest to you is that I am in the process of setting up an EU-based PINE64 store – called PINE64 EU. The store will offer EU-based support, mandatory compliance with EU warranty policies, repair services as well as various options, such as selection of pre-flashed OSes on the PinePhone and PinePhone Pro. This is something that has been in the pipeline for a long time but COVID and COVID-related restrictions, as well as a number of other unforeseen events, have forced me to shelve plans of opening a EU regional store until a more suitable time. That time has now come. To be clear, it will take some time for the store to become operational - I am currently planning on launching the business sometime in late April or in early May. I will, of course, let you know when the store launches. In the meantime, you can follow PINE64 EU’s progress reports on its [Twitter account](https://twitter.com/pine64eu). 

![](/blog/images/EU_PINE64_512_2-300x300.png)

**Do you like the PINE64 EU logo?**

# PinePhone (Pro) 

  
The PinePhone Explorer Edition (EE) launch has probably been the smoothest device roll-out we’ve had in years. We announced the PinePhone Pro in October, laid the roadmap for delivering _Explorer Edition_ by January 2022 and made good on the promises. All phones ordered prior to January 18th have been dispatched on time and most, if not all, are now in the hands of their rightful owners. The sales and logistics teams did a mammoth job to make this happen and I’d like to publicly thank them for pulling off this feat so close to the start of the Chinese New Year. Good job, you’ve made a lot of people happy.

![](/blog/images/PinePhone_Pro_whats_inside_the_package-1024x576.jpg)

**PinePhone Pro picture from the production line - this is what you get in the box**

We’ve also managed to get our initial shipment of the PinePhone (Pro) keyboard and add-on cases out the door just before the holidays. While the keyboard and add-on case’s development isn’t quite as much of a success story as that of the PinePhone Pro, I am still very happy to see the add-ons now in peoples hands. The keyboard has received further software improvements just recently and been merged into [Megi’s](https://xnux.eu/log/) kernel tree. The [new driver](https://github.com/smaeul/linux/commits/wip/pp-keyboard), created by [Samuel](https://github.com/smaeul), makes it possible to check battery voltage that can be read from sysfs in the terminal. You can also set what Wattage your keyboard case delivers to the phone. This is particularly useful when pairing the keyboard with the PinePhone Pro, since the default charging Wattage value is too low to allow for sustained charging during use of the smartphone.  

![](/blog/images/i3wm_PP_KB-768x1024.jpg)

**People are really treating the PinePhone / Pro with the keyboard as a tiny computer - picture via [terminal\_junkie on Twitter](https://twitter.com/cons0le_cowb0y/status/1488366665746169858)**

Many PinePhone Pro, keyboard case as well as the other add-on orders have been placed over the Chinese New Year period. We’re aware many of you are eagerly anticipating your devices to ship, but please permit the product and shipping teams a few days to work through all the orders. As always you will be notified of your shipment via email. I also encourage you to check the [shipping, stock and availability webpage](https://www.pine64.org/availability-and-shipping-status/) once in a while. 

**Plasma Mobile \[by** [**33YN2**](https://mastodon.online/@BrianA)**\]**

With the release of Plasma 5.24 comes a new plasma mobile package! There's been dozens of bug fixes and tons of UI improvements in this release. Most notably, the task switcher and the quick settings panel have both been completely revamped. Not only do they look much nicer, but they also run a lot better - and this applies to both the PinePhone Pro and the original PinePhone.

The app drawer has also received improvements so that it runs better and so that apps can finally be removed from it. And the mobile power settings menu has finally received fixes that now allow the phone to properly be set to not go into suspend when set to "Never". Aside from that, you can expect a litany of bug fixes and UI improvements in the Plasma Mobile applications themselves, including a new application navigation design by [Devin Lin](https://ca.linkedin.com/in/espidev). 

{{< youtube id="4DLQWv8P5Hw" >}}

**New swipe-based application / active window switcher - via KDE Plasma Mobile** 

Currently in development is gesture based navigation support, and there are plans for redesigning the homescreen. Overall this new release is a major step forward in delivering a robust, bug-free and enjoyable UI experience. With how much things have shaped up in this release, it sure will be interesting to see what comes in the next one. Make sure to check out the [Plasma Mobile Gear 22.02 release post](https://plasma-mobile.org/2022/02/09/plasma-mobile-gear-22-02) to read the rest of the changes in store.

**Chat with the machine! \[by** [**biktorgj**](https://twitter.com/biktorgj)**\]**

_\[quick foreword by Lukasz\] The work done by Biktor is incredible as is the effort by Dylan to package the firmware into fwupd (read next section). I think that it is clear at this point that, objectively, this is the definitive firmware for PinePhone / PinePhone Pro’s modem - not to mention that it is also the safest. For legal reasons I need to state the following: 1) we do not encourage users to modify their modem’s firmware nor do we encourage it and 2) altering the firmware on the modem does void device warranty._ _This is a community blog, and the views outlined below belong to community contributors and not the Pine Store._   

It's been a year and half since I started working on the custom firmware for the modem. Most of the time I've been just reimplementing things the stock firmware did, and trying to patch and fix the things that didn't work so well.

The Pinephone and the Pinephone Pro are special devices that do not have the modem integrated in the SoC. This causes more difficulties in getting everything to work, but it also presents opportunities to make things no other phone can do. These last weeks I've been implementing messaging and voice calling functionality in the modem's userspace; that is, being able to text the modem itself, calling it, or making it call you and reply to your messages.

{{< youtube id="9fE-qvT_wtE" >}}

**"Hello? Who's this? oh, hi modem"**

At this point it's just a proof of concept. It only works correctly on ModemManager-based distros, and has a limited set of commands you can request via SMS (some as useless as getting a kernel log via SMS), and calls only play a sound file in a loop, but it opens up endless possibilities to develop additional functions ranging from knowing if something is using the GPS without you knowing, to having the modem call you at a predefined time so you can have an excuse to get out of a boring meeting. If you're running the latest release, feel free to send 'help' to the modem at the non-existent number +01 555 01 99 999 and it'll reply back with a list of the currently available functions. 

The latest community-built firmware can be downloaded from [Biktor’s GitHub](https://github.com/Biktorgj/pinephone_modem_sdk/releases/)

**LVFS & fwupd for the modem \[by** [**Dylan Van Assche**](https://dylanvanassche.be/)**\]**

You've been able to install Biktorgj's firmware on your PinePhone and PinePhone Pro modem for a long time. However, installing it required you to use the command line and you had to pay attention that the battery on your PinePhone had enough charge. [postmarketOS](https://postmarketos.org) wanted to make this flashing process more user friendly, secure and easier to upgrade, therefore I have been working with Biktorgj to bring firmware updates on your device through fwupd. [Fwupd](https://fwupd.org/) is the de facto standard on Linux to deliver hardware firmware updates through the Linux Vendor Firmware Service (LVFS) used by Lenovo, DELL, and other hardware vendors.

It took a long time to debug the firmware update process of the modem, since it is not documented and contains various bugs. These were solved and integrated into the fwupd ModemManager and fastboot plugins. Various patches were submitted to fwupd, ModemManager, eg25-manager, etc. to make it all work. After some help from the LVFS and fwupd maintainers we now have the firmware updates available through LVFS which are signed and properly tested by me and Biktorgj. Moreover, you can now upgrade your firmware through GNOME Software, KDE Discover or the fwupd CLI after switching to the community firmware branch. Note that this branch is not supported by the original hardware vendor at all, but it provides stability improvements, enhancements, and protection against the root exploit which is being abused by malware to brick your PinePhone and PinePhone Pro modem.

I [described the whole process on my blog](https://dylanvanassche.be/blog/2022/pinephone-modem-upgrade/) and invite you to have a read.

<iframe title="Updating Pine64 PinePhone modem firmware with fwupd" src="https://tube.tchncs.de/videos/embed/a39ea96e-864d-45bf-a6a5-b9ace8df7df6" allowfullscreen sandbox="allow-same-origin allow-scripts allow-popups" width="560" height="615" frameborder="0"></iframe>

**Demo of the modem's firmware being flashed**

# PineNote 

The PineNote has seen a handful of important developments since last month. The initial successful e-paper enablement on mainline-based Linux, thanks to work by [smaeul](https://github.com/smaeul) and [pgwipeout](https://github.com/pgwipeout), now allows partner project developers to start work on porting their OSes to the PineNote and adapting user interfaces for the grayscale display. Last month we got a handful of units into the hands of our friends at KDE and they’ve started work on adapting Plasma Mobile to work on the PineNote. I spoke to [Aleix](https://twitter.com/aleixpol), KDE e.V. president, last week: he told me that aside from working on a proof of concept UI in grayscale, KDE has also started adding support for apps - “(...) work to support the first apps on the device has started. At this time developers are working on getting Pikasso, a simple drawing app, to properly support the integrated drawing tablet on the device”. Plasma desktop already runs on the PineNote and, when using a modified high-contrast theme, the full desktop environment seems surprisingly viable on e-paper. If you want to join the conversation, help and contribute to the development of Plasma on e-paper or have an application you’d like supported on e-paper then please join [Plasma-Ink Matrix channel](https://matrix.to/#/#plasma-ink:kde.org). 

![](/blog/images/Plasma_on_PN-1024x768.jpg)

**Plasma Desktop with grayscale theme on the PineNote - via KDE dev team**

But Plasma isn’t the only UI that has graced PineNote’s display in the past month. The device now also boots postmarketOS with Phosh UI using the DRM driver display written by smaeul (with pgwipeout’s tweaks). The merge request for initial support has already been [submitted](https://gitlab.com/postmarketOS/pmaports/-/merge_requests/2910) so there is a good chance that we’ll see a PineNote OS image from the postmarketOS team at some point in the near future. I’ve briefly spoken to [Caleb](https://twitter.com/calebccff) from postmarketOS and they told me that Phosh looks great in high-contrast mode. However, they also mentioned the default theme  cannot be modified since various parts of the UI are hardcoded. Noteworthily, [SXMO](https://sxmo.org/) - a mobile UI that came to be on the PinePhone - has now also been ported to the PineNote; I am very much looking forward to seeing how this particular UI works in practice on the PineNote. Regardless, the more choices the better, and having a wide range of desktop and phone UIs available will help us determine the right trajectory forward for the PineNote. 

![](/blog/images/pmOS_on_PN-1024x768.jpg)

**postmarketOS on the PineNote - via [Caleb](https://twitter.com/calebccff)**

Not only have we seen much movement on the UI-side, but many low-level enablements have also been made in recent weeks. Indeed, the functionality of the PineNote is growing by the day and things are starting to look great. Aside from the e-paper display, Wacom and capacitive panels, we now have Bluetooth, WiFi, as well as sound output. Bluetooth was broken on the PineNote until recently but, as Samuel Holland explained to me, it was fixed by using a different firmware. He added that this effectively means all hardware components of the PineNote have now been tested and do work (to various degrees). Even EMR pen pressure sensitivity has now been enabled and works in Linux. Given how little time the PineNote has been in active development, seeing all these efforts slowly start coming together and forming a larger whole is very exciting.   

![](/blog/images/PN_pen_pressure_in_linux-1024x768.jpg)

**EMR pen pressure working in Krita on the PineNote - via Samuel Holland**

That said, there are a number of issues that remain to be resolved and make Linux more usable on the device. As pgwipeout explained to me, GPU acceleration doesn’t work when outputting to the E-Book Controller (EBC) - the display controller for the e-paper display. This means that the UI and all its elements are currently sluggish. But enabling the GPU over EBC is only a part of the issue. There is also a need to create a standard for exposing refresh modes to userspace (different refresh [modes supported](https://www.waveshare.net/w/upload/c/c4/E-paper-mode-declaration.pdf)). Caleb says that creating a daemon will be needed to automatically switch modes depending on what the user is doing - e.g. switch to mode A2 when scrolling or drawing on the PineNote. At present time, the A2 mode doesn’t seem to work properly, so writing on the PineNote in Linux is not viable (the input appears with a delay). Eventually desktop environments such as Plasma Desktop and Phosh as well as individual applications should support the waveform switching feature, so that the display can adapt to the user's activity. 

The good news is that significant progress is being made on this front too. As Samuel Holland explained to me, the mainline-based display driver now supports all of the display controller’s modes. These modes determine the ability to independently update different parts of the screen at the cost of CPU and power usage. Samuel says that previously only the least sufficient software mode was available and that the now enabled “(...) hardware LUT mode allows us to run the panel at full speed. Since the waveforms are designed for a specific refresh rate (...), this means better image quality”.

Displaying an image isn’t everything however and there are multiple other issues that still need addressing. For instance, due to a bug, u-boot currently doesn’t detect the root filesystem automatically, and requires the user's input over UART. Needless to say, this isn’t exactly a viable manner of booting the device into an OS, especially not for regular end-users (but surely it is also an annoying step even if you’re an enthusiast). So, while there is clearly a way to go before we can all enjoy reading and writing content on the PineNote running a traditional Linux desktop environment, let us appreciate how much progress has been made in just a few short months. With the amount of work being done on this particular device, and on the RK3566 platform in general, I am confident that early adopters will get a chance to get their hands on the PineNote late this year. 

# Pinecil \[by William Starkey\]

[IronOS](https://github.com/Ralim/IronOS) 2.17/2.16 changes: the two most recent IronOS updates, 2.16 and 2.17, bring some great new features to the Pinecil, as well as significantly improve some of the existing ones! The major improvements made in 2.16 are upgrades to the temperature regulation, so the Pinecil heats up faster and holds the temperature more precisely, and refactoring & bug-fixes of the USB Power Delivery (PD) stack that fix compatibility issues with some Type-C power supplies, and a myriad of other small quality-of-life improvements.

IronOS 2.17 brings some useful new features, including the ability to check if the iron has had the VBUS mod (explained below) performed correctly, and a new debug menu entry showing raw values from a Hall effect sensor if one was added to the board. It also brings some improvements to the Russian, French, and German translations. The logo conversion tool now outputs a .dfu file directly to make it easier to add a custom logo, and the build tools are all now compatible with Alpine Linux - so you can build and flash IronOS from a PinePhone or PinePhone Pro running PostmarketOS.

PINE64 Updater: a flashing utility designed to make the experience of updating the firmware on your PINE64 products easier is under development by Gamiee, one of the admins of the PINE64 community chat rooms. The software currently supports updating the firmware of your Pinecil and is available on MacOS and Windows. It’s planned to gain support for Linux and allow flashing more Pine64 products in the future. The PINE64 updater is currently available on github at [https://github.com/pine64/pine64\_updater](https://github.com/pine64/pine64_updater) if you want to contribute to the project or use it to flash your Pinecil more easily.

_\[edit from Lukasz\] A quick foreword to the following section - we always allow and encourage users to experiment and mod their devices. But, please, bear in mind any modifications to Pinecil’s hardware does void the warranty._ 

Pinecil VBUS mod: early on in the Pinecil's lifetime, shortly after it was announced, there was some controversy over the voltage rating of the Pinecil. It was rated for 24V, but the chip responsible for handling USB power delivery, FUSB302, was not rated for more than 21V. While the “Absolute Maximum” rating for the chip is 28V, it will still sometimes die when 24V is fed into it. The VBUS mod is a fairly easy permanent fix for this issue. As we found out, the pin on the FUSB302 that connects to the incoming power rail (VBUS) is not actually used by IronOS, and therefore doesn’t have to be connected. The mod is, thus, as simple as cutting the trace going to that pin.

The recommended technique is to use the corner of a razor blade and drag it across the trace highlighted on the picture - at the point between the two arrows. This position will change depending on the version of your Pinecil board, so, when you get the board out of your Pinecil (follow the disassembly instruction on the wiki at [https://wiki.pine64.org/wiki/Pinecil#Disassembly\_steps](https://wiki.pine64.org/wiki/Pinecil#Disassembly_steps) ), compare your board with the visual aids to find the location to cut, press the corner of a razor blade into the board slightly above the starting location, then carefully drag it through the trace, firmly applying pressure so that you cut through the copper. Make sure you do not cut any other traces!

Once the trace is cut, make sure it is no longer connected, using either a multimeter or IronOS’ new VBUS mod detection feature (available in IronOS 2.17). To use the IronOS mod detection feature, plug your Pinecil into any USB-PD-capable Type-C port using a C-C cable, then open the debug menu by holding down the “-” (minus) key after the screen turns on. Press the “+” key in the debug menu until you reach the section labeled “PWR”. It will say “PD No VBUS” after “PWR” if you have properly cut the trace.   

When you have confirmed that the mod was successful, you will be able to use your Pinecil with a 24V power supply without any risk of causing damage to the iron!

![](/blog/images/Pinecil_Mod.png)

**Mod illustration before (left) and after (right)**

# PineTime \[by JF\]

InfiniTime 1.8 was released last month (see the [January community update](https://www.pine64.org/2022/01/15/january-update-more-news/) for more details). According to the feedback we received, BLE connectivity seems to work much better than before thanks to the addition of the secure pairing functionality. If you haven't done so yet, I strongly recommend you update your PineTime to this latest version. The next release is not ready yet, but many contributors and developers are working to add new functionalities and fix bugs. Infinitime keeps getting valuable feedback, interesting feature requests and many many pull requests - thanks to everyone who is contributing to the project!

So what have we been working on? You can get a preview of the features we plan to add to the next release by checking out the [1.9 milestone](https://github.com/InfiniTimeOrg/InfiniTime/milestone/9). This list includes a new [airplane mode feature](https://github.com/InfiniTimeOrg/InfiniTime/pull/888) (to disable the BLE radio when you don’t need it), a new [“terminal” watch face](https://github.com/InfiniTimeOrg/InfiniTime/pull/932) and a [complete rewrite of the documentation](https://github.com/InfiniTimeOrg/InfiniTime/pull/838).

![](/blog/images/terminal_watchface-461x1024.jpg)

**Terminal watchface - pictur by [13werwolf13 on Github](https://github.com/InfiniTimeOrg/InfiniTime/pull/932#issuecomment-1011873394)**

Another project I would like to highlight is the InfiniTime simulator by [NeroBurner](https://github.com/NeroBurner), which has been worked on for a few months now. This [simulator](https://github.com/InfiniTimeOrg/InfiniTime/pull/743) runs the whole InfiniTime UI, allowing developers to easily design new applications and user experiences directly on their PC without needing to test and debug the changes on the actual PineTime. I recently had a look at this application and I have to say I’m genuinely impressed by the amount of work NeroBurner put in. It simulates the whole UI by reusing code from InfiniTime and it “stubs” (replaces) low level code that accesses the hardware so that it can run in a simple window on your desktop. The author opened a pull request on InfiniTime and I’m eager to review it and see how we will integrate it into the project.

![](/blog/images/simulator.gif)

**GIF of InfiniTime simulator - by [NeroBurner on Github](https://github.com/InfiniTimeOrg/InfiniTime/pull/743#issuecomment-1021595295)**

![](/blog/images/weather-simulator.png)

**Upcoming weather forcast functionality in the simulator**

As you can see in the following picture, the integration of weather information in the PineTimeStyle watchface is still ongoing thanks to the simulator!

Stay tuned for the next release and, until then, enjoy your PineTime.

# PineDio \[by JF\]

Remember the PineDio STACK? This is a development kit based on the Bouffalo BL604 RISC-V MCU which embeds many devices like a LoRa radio, a motion sensor, a display and a touch panel. We have already talked about it in previous updates, and [Lup](https://lupyuen.github.io/) has already written extensively about it [LoRaWAN on the STACK](https://lupyuen.github.io/articles/lorawan3), [Rust on Apache NuttX](https://lupyuen.github.io/articles/rust2) [BL602 EFlash Loader: Reverse Engineered with Ghidra](https://lupyuen.github.io/articles/loader) and related topics.

Unfortunately this kit is not yet available in the Pine Store as we still had a few issues with our prototypes: we were unable to make the LCD work and we had a few issues with flashing one of the boards. Fortunately, we were able to fix those issues and now can move onto the next stages of development. I’m currently working on a demo / selftest firmware that implements basic drivers for all onboard devices (LoRa radio, sensors, display,...) to ensure that the firmware is able to communicate with those devices and that they are working properly. This firmware will not only allow future developers to check that their board is working correctly, but it’ll also make it possible for the PINE64 production team to test the boards at the factory before shipping starts!

I’ve just sent the first version of the firmware to the production team. Now, I’m waiting for feedback and I’ll eventually do some changes and improvements if needed.

Here’s a video showing that firmware in action:

<iframe width="560" height="615" sandbox="allow-same-origin allow-scripts allow-popups" src="https://video.codingfield.com/videos/embed/ab40f429-18d0-4827-b2b3-123f74ab8d09" frameborder="0" allowfullscreen></iframe>

Once this firmware will be ready, PINE64 will be able to start the production of the PineDio STACK. 

That is all for this month’s update, if you haven’t done so yet make sure to subscribe to this blog - the subscription widget is at the bottom of this page.
