---
title: "March Update: Introducing the QuartzPro64"
date: "2022-03-15"
authors: ["Lukasz Erecinski"]
categories:
  - "news"
  - "pinephone"
  - "pinephone-pro"
  - "quartz64"
  - "quartzpro64"
tags: 
  - "infinitime"
  - "pinephone"
  - "pinephone-pro"
  - "pinetime"
  - "quartz64"
  - "quartzpro64"
images:
  - "/blog/images/March-update-header.jpg"
---

![](/blog/images/March-update-header.jpg)

This month we’re announcing the QuartzPro64 - a new single-board computer based on Rockchip’s powerful RK3588 SoC. This is our first Pro-grade SBC since the introduction of the ROCKPRo64, and I believe it to be a worthy successor to the much revered Pro lineup. I am also happy to let you know that the Quartz64 model-B will be arriving at the Pine Store in the coming weeks, with all of its features supported in the most recent Manjaro OS image. 

We’ve got much to discuss, let's get into it.  

You can watch the synopsis of this month’s community update on YouTube (embedded below) as well as on [Odysee](https://odysee.com/@PINE64:a) and [PeerTube](https://tilvids.com/accounts/pine64tilvids/video-channels). To stay up-to-date with PINE64 news make sure to subscribe to this blog (subscription widget at the bottom of the webpage), follow [PINE64 Telegram News channel](https://t.me/PINE64_News), the [announcements channel on Matrix](https://matrix.to/#/#pine64-announcements:matrix.org), the [announcements channel in Discord](https://discord.gg/pine64) as well as our [Twitter](https://twitter.com/thepine64) and [Mastodon](https://fosstodon.org/@PINE64).

I’d like to thank [JF](https://twitter.com/codingfield), [Alex](https://twitter.com/AlexRob12252696) (clover), Brian ([33YN2](https://mastodon.online/@BrianA)), [Danct12](https://twitter.com/RealDanct12) and [PizzaLovingNerd](https://www.youtube.com/channel/UCmGcm7dhEjS9CIOsOOv8y6w) for their contributions to this community update.

N.B. Comments on the blog post need to be in English and follow our [Community Rules and Code of Conduct](https://forum.pine64.org/showthread.php?tid=13209).

{{< youtube id="BYAmUoQQJ5U" >}}

**Synopsis of this month's update in video format**

**TL;DR**

- Housekeeping
    - A new episode of PineTalk is out - listen to the hosts’ suggestions for future PINE64 devices
    - Improvements to the chats have been made over the last few weeks which should significantly reduce spam
    - PineTab and Pinebook Pro will sadly remain unavailable for a while longer
    - PINE64 EU is on track for May 1st launch
- QuartzPro64
    - We’re introducing the QuartzPro64 based on RK3588 - available in the coming weeks to developers
    - It will cost North of $300 and will initially only be available to developers via a coupon system 
    - With development in mind, the QuartzPro64 exposes as much I/O as possible
    - Equipped with 16GB RAM and 64GB of expandable eMMC
    - Will only be available publicly when BSP releases are in good shape
- PinePhone (Pro)
    - Shipment has resumed post-CNY and most if not all of the backlog has been cleared
    - Suspend now works on the PinePhone Pro - u-boot fix applied by pgwipeout
    - Keyboard case battery capacity reporting in UI is coming - already available in Manjaro’s OS images 
    - Tow-Boot 4th release adds official support for the PinePhone Pro adding mobile-specific elements 
    - SailfishOS and Nemo mobile get GPS support on the PinePhone and work began to start integrating the fingerprint reader back case
    - The original PinePhone can be used to run LibreELEC - and it runs well including 1080p@60 video playback
- Quartz64
    - Quartz64 model-B is coming soon; 4GB version of the board is launching first 
    - Manjaro OS image for model-B if feature-complete, including full support for desktop and UI usage and all I/O present on the board
    - More improvements for the RK3566 and thus also the Quartz64 and derivative devices is coming soon
- PineTime
    - Active development is ongoing with many merge requests awaiting
    - InfiniSim is an InfiniTime desktop simulator, which can be run on a PinePhone (Pro) that allows for easy InfiniTime development and testing
    - InfiniSim is now a part of InifiniTime organization on GitHub

## Housekeeping 

I’m starting with a last-minute edit to this month's update; Shenzhen, the city where PINE64 electronics are manufactured, has just imposed a strict COVID19 testing procedure and issued a ‘stay at home’ order until March 20th. This is due to an increase in COVID19 cases in the region. It remains to be seen how, if at all, this situation will impact our production schedule. However, for the time being, the shipping staff have been sent home, which means that only Hong Kong-based shipments (PinePhone, PinePhone Pro, and PineNote) will be sent out this and the coming week. Once I have an update on the situation I’ll make sure to relay it to the community via social media, on the forum, and in the chats.

![](/blog/images/shenzhen-stay-at-home.png) ![](/blog/images/Screenshot-2022-03-15-at-10-30-00-Translate-text-from-photos-from-English-and-other-languages-–-Yandex-Translate.png)

**Left: original text in Chinese // Right: auto-translation into English ('deep training' to be read as 'thorough testing')**

A new episode of the PineTalk is out. In this most recent entry to our community podcast, Justin and Brian discuss current PinePhone and PinePhone Pro developments, including Tow-boot and improvements to Mexapixels post-processing, as well as their own open-hardware ideas. While I do not think we’ll embark on a journey to create an open Google Glass-type device, as suggested by Brian, an open speaker with a personal assistant is actually a compelling idea (and one we discussed internally all the way back in 2020). A solid idea Justin and one perhaps worth visiting. Have a listen and let us know what you think about the show-hosts ideas for future hardware. The most recent episode can be found on [PineTalk’s page](/podcast/); I also encourage you to subscribe to the [podcast’s RSS feed](/podcast/index.xml). 

During my absence (more on this a bit later), [Fire219](https://twitter.com/fire219_SIMPL) and [Gamiee](https://twitter.com/gamelaster) have done some solid improvements to our chat infrastructure. As I’ve reported [late last year](https://www.pine64.org/2021/11/15/november-update-first-impressions/), and as many of you know from first-hand experience, spam in the chat has been an issue in recent months. A part of the problem is our cross-platform bridge: not all moderators have moderation privileges on all platforms, and those that do aren’t always there to react. Moreover, it is easier to get the moderators’ attention on some platforms than others. Earlier this year Fire219 and Gamiee laid the foundations for automatically removing spam and flagging potential malware. This reduced the number of incidents but hasn’t fully eliminated the issue. Now, however, we’ve got two new weapons at our disposal: cross-platform deletion and a sophisticated and trained AI bot with cross-platform deletion permissions. This means that even if the, rather sophisticated, bot fails to catch the spam any moderator can delete any spam message on any platform. Long story short, the spam problem should be less intrusive moving forward. 

I also promised you an update regarding PineTab and Pinebook Pro’s availability; as may recall, the product team has been scavenging around for a vendor who’d be willing to sell us a batch of LCD panels that are reasonably priced and come with a warranty (so that if they are faulty, do not meet the grading or fail during usage we can RMA them at the source). Unfortunately, as of today, the team has not found a vendor who would be willing to sell such a batch of panels. We’re well aware that it has been a long wait and that many of you are eager to see the production of these devices resumed, but I’m afraid we’ll all have to wait a little longer for the next production run. I’ll make sure to keep you updated if anything changes.

![](/blog/images/PIne64EU-page-1024x468.png)

**[PINE64 EU](https://pine64eu.com) website is coming along**

Lastly, I’ve been away these past few weeks laying the foundations for the PINE64 EU store. The last paperwork to get the EU store off the ground has now been filed, and I even have an office with (mostly) assembled IKEA office furniture. If all goes to plan, and the Polish state’s bureaucracy doesn’t take an eternity to process the application, then I hope to receive the first shipment of hardware sometime in late April. I don’t want to commit to a firm launch date at this stage, but I am currently aiming to have everything ready to go on May 1st. For those who want to learn more about the plans for the EU store, I invite you to read l[ast month’s community update](https://www.pine64.org/2022/02/15/february-update-chat-with-the-machine/).  I’ll be posting progress updates on [PINE64 EU’s Twitter](https://twitter.com/pine64eu) as we get closer to launch.

## QuartzPro64

In January I outlined our plans for the Rockchip RK3588 platform - a powerful Arm SoC with an impressive array of I/O options. Today I am pleased to introduce the QuartzPro64, our single board computer based on the RK3588. Let’s start with a quick recap: the RK3588 is an 8-core SoC, featuring 4x A55 and 4x A76 cores clocked at 1.8GHz and 2.4GHz respectively. This new SoC features the recently introduced Mali G610MC4 GPU with 4 cores, based on the Valhalla architecture. The SoC is capable of driving an 8K display and multiple 4K displays (4 total), has a 6TOPS NPU, an 8K 10-bit decoder as well as an 8K encoder. In our single board computer lineup, the RK3588 SoC is the successor to the very successful RK3399 used in the ROCKPro64. However, while this SoC is the successor to the RK3399, I want to make it clear that it will not be replacing it anytime soon. Thus, the QuartzPro64 will also not be replacing the ROCKPro64 for a very long time either. 

![](/blog/images/QPro64-layout-950x1024.jpg)

**No picture due to the 'stay at home' order affecting the product team, so this will have to suffice for now**

Before I get into discussing the details of the QuartzPro64 I feel that I first need to make two things clear. Firstly, to purchase the board you will need to be a developer - at least initially. We’ll use the same coupon system we used for the first production runs of the PineNote and the PinePhone Pro once these devices launch. The software for the QuartzPro64 is yet to be developed and to say that the device is ‘not end-user ready’ would be an understatement; we both hope and expect to see BSP-based support in the initial months, with mainlining efforts running in parallel to the BSP development. Secondly, this will not be an inexpensive single-board computer. While we haven’t settled on a price-point yet, we expect it to cost North of $300. It will be sold either at cost or we will subsidize it. I think that it is necessary for me to mention the above up-front to align everyone's expectations and tamper with unnecessary hype. Here’s the take-away: this is an amazing platform, but it will take time for it to mature.

![](/blog/images/Component-block-layout-QPro64.jpg)

**QuartzPro64 block diagram**

Now, with that out of the way, the QuartzPro64 will ship with 16GB of LPDDR4X RAM and 64GB of eMMC storage, which ought to be plenty for development and future implementation. With development in mind, we chose to expose as much of the available I/O as possible.

Here’s the core I/O run-down:

- USB-C (with video-alt mode)
- USB0-C (with debug mode)
- USB- 3.0
- 2x USB 2.0 
- HDMI in
- 2x HDMI out 
- PCIe 3.0 
- 2 SATA ports 
- 2x Gigabit ethernet
- 2x SMA Antenna 
- 2x MIPI DPHY
- 2x MPI DPCHY
- Fan header
- RTC battery holder
- An array of switches, including power on/off maskrom and system KEY
- eMMC socket
- SD card slot
- Power in via DC 12V 

The board is 180mm x 180mm in size, features heatsink mounting holes and system KEY buttons on the PCB. We hope this feature set will make QuartzPro64 interesting to its target audience - the development community. In anticipation of people asking about the general availability of the board; at present time it is unclear when the QuartzPro64 will be made available more broadly. This will depend on BSP and Mainline development. As most members of the community I too have high hopes for the QuartzPro64, and more broadly for the RK3588 platform, and I hope to see the SoC implemented in PINE64 devices in the far-off future. For the time being, we’ll be announcing QuartzPro64’s availability on our Telegram, Matrix and Discord announcement / news channels and on social media in the coming weeks. Stay tuned. 

## PinePhone (Pro)

Shipments of the PinePhone and PinePhone Pro have resumed following Chinese New Year’s end, with the first batches of both dispatched earlier this month. I haven’t followed the dispatch process in recent weeks, but I believe that much of the CNY backlog has now already been shipped (and in many cases delivered). On the subject of PinePhone and PinePhone Pro shipments - we’re working on improving the dispatch and delivery logistics. The end goal is to ship smaller batches but more frequently. For the majority of you, this means that your PinePhone and PinePhone Pro order will be delivered much quicker. We are currently trialing a service that would cut down the delivery time significantly - depending on how the trial period goes we may implement this shipping mode permanently, and even expand it to other devices. I’ll return to this topic once the trial period is over and a decision has been reached later in the year.

![](/blog/images/PPP-shipments-767x1024.jpg)

**PinePhone and PinePhone Pro most recent dispatch (I am intrigued by the red broom, you too?)**

On the subject of software, there is much progress to report. Perhaps most importantly of all, suspend now works properly on the PinePhone Pro using u-boot. This enablement, or “fix” to be more accurate, comes courtesy of [pgwipeout](https://github.com/pgwipeout), who found a solution to this problem. I asked pgwipeout what the solution was, here is his response: _“DMA transfers to SRAM always fail, no matter the source. The original fix handled disabling DMA on the SDMMC controller in SPL, but the SDHCI (eMMC) controller still was attempting DMA. I simply created a toggle for DMA in SPL for the SDHCI controller. Thus U-Boot on the eMMC now can load the SRAM bits without corrupting the data in-flight”_. This fix has now found its way into Manjaro’s most recent OS image, which means you’ll be able to suspend/resume from suspend on the PinePhone Pro just like on the original PinePhone. While similar functionality can be achieved via Tow-boot (33YN2 writes more about this further down in this section), for those of you who specifically wish to use u-boot on their device I am glad to let you know that it is now a viable option.    

Battery capacity reporting for the keyboard case now works in the UI on the PinePhone and PinePhone Pro thanks to Megi. This means keyboard case battery levels can be read in Plasma Mobile, Phosh, and SXMO in the same way as the smartphone’s main battery. Prior to this, you needed to read the battery status from the command line, which obviously wasn’t the ideal way to keep track of battery usage. This enhancement has now made its way to Manjaro; if you’re on Arch then you can wait for kernel 5.17 or switch to linux-megi-rc package. I am confident that more distro will follow suit and implement this enablement in their OSes.

![](/blog/images/kb-bat-showing-in-UI.jpg)

**Keyboard case's battery charge displayed in Phosh - picture by [Martijn Braam](https://twitter.com/braam_martijn)**

[Tow-Boot](https://tow-boot.org/), a user-friendly version of U-Boot, has seen a release for the PinePhone and PinePhone Pro. The project page states that Tow-Boot aims to make the process of booting your device “boringly” normal and simple. The goal is to have a standardized booting experience across a variety of Arm-based devices, with no need for board or OS-specific differences in the builds. The most recent version of Tow-Boot introduced a smartphone UI, supporting both touch-input and small screens. In line with the project’s mantra, the project explains on their GitHub that this build of Tow-Boot should “(...) enable users to live the dream of EBBR _but on their phones_.” Tow-boot also allows for a variety of additional functionality, similar to [Jump Drive](https://github.com/dreemurrs-embedded/Jumpdrive), exposing the smartphone’s internal eMMC memory in a way that it can be mounted and flashed from a PC. It also allows the user to select the bootable device (SD / eMMC) via a combination of button presses. To learn more, check out the [project’s website](https://tow-boot.org/).

{{< youtube id="ufzAC4QADvY" >}}

**Video showcasing Tow-Boot installation to PinePhone Pro's SPI flash - via [Martijn Braam](https://twitter.com/braam_martijn)**

[Megi](https://xnux.eu/) has demoed LibreELEC running on the original PinePhone and outputting video to an external display (TV). The KODI UI is accelerated and runs smoothly as does the video playback, which appears to be rock solid. I’m told that 1080p video, including 50fps (and likely also 60fps), plays back really well on the original PinePhone running LibreELEC. There isn’t a dedicated PinePhone OS image but thankfully Megi has put together comprehensive [instructions](https://xnux.eu/log/#062) on how to make one yourself. He also included a guide detailing how to add a LibreELEC entry into his multi-OS p-boot image. I really enjoy the PinePhone being used in non-phone specific ways, and this is certainly a great showcase of the versatility that the device offers. Being a retro-gamer I already asked Megi for a guide on how to port LAKKA to the PinePhone.    

{{< youtube id="oq9m3nn-02M" >}}

**LibeELEC on the original PinePhone - original video by [Megi](https://xnux.eu/)**

Lastly, an alternative X86/X86-64 emulator for ARM64 called [Fex-EMU](https://github.com/FEX-Emu/FEX) (Compared to Box86/64 it aims to be faster), has seen major improvements leading towards the goal of getting full Proton and Steam compatibility. It is great to see further work being done in this space. And although it’s being mentioned here, this obviously not only benefits the PinePhone, but any ARM64 device out there!

## Quartz64

Given QuartzPro64 introduction this month, I would be remiss not to mention all the development that Quartz64 has seen in recent months. I am also happy to announce that the Quartz64 model-B has now entered production and should become available in April (or earlier). Just to recap, the Quartz64 model-B features the same RK3566 SoC that is found on the model-A and on the PineNote. The SoC features 4x A55 cores and the Mali G52-2EE GPU. The model-B will be available in 2 configurations - with 4GB LPDDR4 and 8GBLPDDR4 RAM for $59.99 and $79.99 respectively. Unlike the model-A, model-B follows in the ROCK64’s steps and offers a small footprint. The small footprint means that some of the model-A I/O has been removed, but it retains the USB 3.0 alongside 2x USB 2.0 ports as well as DSI, CSI and RTC. This I/O selection is coupled with a full 40 GPIO pin connector and onboard Bluetooth and WiFi module. You can also outfit it with an eMMC module or a NVMe SSD (via PCIe 1x) located on the bottom of the PCB. It is a versatile little board, geared more towards end-users and industry than the bigger model-A.

![](/blog/images/Q64v1.2-1024x1024.jpg)

**The form factor of the Quartz64 model-B is, in all likelihood, very familiar to most of you**

The model-B arrives at a good time; the software for the platform has matured to a point that distros and projects can develop fully fledged, functional OS images for the Quartz64. As per usual, Manjaro is the first to deliver an OS image with all core functionality enabled. The OS is built upon mainline-based kernel (5.17) and comes in five variations: minimal, with XFCE desktop, Plasma Desktop, GNOME and MATE desktops as well as Sway. The desktops (which support acceleration) are fully accelerated via the open source Panfrost GPU driver and I can attest that the desktop experience on the Quartz64 is excellent as far as SBCs are concerned. Latest pre-release Manjaro OS builds for the Quartz64 can be downloaded from [here](https://github.com/manjaro-arm/quartz64-a-images/releases/).

![](/blog/images/Manjaro-Q64-via-JF.png)

**Quartz64 model-A with 2x SATA SSDs attached and powered directly from the SBC - [picture by JF via Twitter](https://mobile.twitter.com/codingfield/status/1480146632889061383)**

But that's not all. I’ve spoken to pgwipeout and he’s told me that many improvements to end-users' experience are in the works. He also updated me on the mainlining status of the various components: _“Dwc3 support is pretty much ready to land in mainline, with the combophy queued up for 5.18. That also means pcie and sata are coming soon too. I've gotten DSI to work partially with the vop2 driver, but it still needs more work”._ Moreover, the SPI controller has been confirmed to work and that SPL handling of recovery is now supported in mainline u-boot. While some I/O found on the model-A, such as the DSI, still needs some work all I/O on the model-B is already fully functional - “_If you are including anything about model b, it's pretty much good to go out of the box_” pgwipeout told me. I believe that the release of the model-B will lead to a much broader adoption of the RK3566 and, in turn, a much wider range of OS choice. Indeed, I know this to be true, since we’ve already shipped a handful of dev kits to projects interested in supporting the Quartz-line of devices. 

## PineTime \[JF\]

Since last month, the InfiniTime community kept working on the features I wrote about in [last month’s update](https://www.pine64.org/2022/02/15/february-update-chat-with-the-machine/), and some of the features being work on have already been merged in the \*develop\* branch of the project. These new features will be available in the next release of InfiniTime. Just to recap, the new features will include, among others, an airplane mode, the terminal watchface and improvements to the heart rate sensor management.

The community is very active and is creating [pull-requests](https://github.com/InfiniTimeOrg/InfiniTime/pulls) faster than we can possibly review, test and merge them. This is also true for the feature requests - there are currently [91 pending features requests](https://github.com/InfiniTimeOrg/InfiniTime/issues?q=is%3Aopen+is%3Aissue+label%3A%22feature+request%22). I’m really grateful to be surrounded by such an enthusiastic and understanding community whose people understand that we are working on the project in our spare time, and that the features will be done when someone will find the time to work on it.

This month, I’m happy to announce that _InfiniSim_, the InfiniTime simulator, is now its own [dedicated project](https://github.com/InfiniTimeOrg/InfiniSim). [NeroBurner](https://github.com/NeroBurner), the author of InfiniSim, joined the team to develop and maintain the project under the [InfiniTime organization](https://github.com/InfiniTimeOrg) on GitHub. We worked together to create the project and to ensure that all the InfiniTime code modifications needed were applied to support the simulator. InfiniSim allows everyone and anyone to run the whole InfiniTime UI on their computer. It even runs on the PinePhone Pro!

See the [video here](https://video.codingfield.com/videos/embed/f75c378e-bb0e-4b01-965a-64466c40ee36).

**InfiniSim running on the PinePhone Pro**

You can use InfiniSim to easily design and debug new apps for InfiniTime from the confort of your powerful computer without even needing to flash it over (and over again) to the PineTime. I am also planning on using InfiniSim to take screenshots of the menus and apps of InfiniTime and add them to the project’s documentation. Take a look at this impressive mosaic!

![](/blog/images/montage.png)

If you are interested in using or contributing to InfiniSim, please check out [the project page](https://github.com/InfiniTimeOrg/InfiniSim#infinisim). It also provides useful information on how to build and run it.

That's all for now, catch you next month!
