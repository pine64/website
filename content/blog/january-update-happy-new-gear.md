---
title: "January Update: Happy New Gear!"
date: "2021-01-15"
categories: 
  - "community"
  - "news"
  - "pine64-community"
  - "pinebook-pro"
  - "pinecil"
  - "pinephone"
tags: 
  - "community-edition"
  - "pinebook-pro"
  - "pinecil"
  - "pinecube"
  - "pinephone"
  - "pinetime"
cover: 
  image: "JanuaryHeader-1024x594.jpg"
---

![](/blog/images/JanuaryHeader-1024x594.jpg)

Happy New Year everyone! Let us all hope that the difficulties brought about by the COVID-19 virus are now waning and that more aspects of our lives will return to normal soon. 

We start this year with announcing the last community edition of the PinePhone, an update on the Quartz64 single board computers, and with some good news regarding PineTab and Pinebook Pro production.  

You can watch a synopsis of this month’s community update on Youtube (embedded below) but also on [LBRY](https://lbry.tv/@PINE64:a) and [Peertube](https://tilvids.com/accounts/pine64tilvids/video-channels). Stay up-to-date with PINE64 news and make sure to subscribe to this blog (bottom of the webpage), follow [PINE64 Telegram News channel](https://t.me/PINE64_News) as well as our [Twitter](https://twitter.com/thepine64) and [Mastodon](https://fosstodon.org/@PINE64).

I’d like to acknowledge [JF](https://twitter.com/codingfield), [Marek](https://twitter.com/gamelaster) (gamiee), [Alex](https://twitter.com/AlexRob12252696) (clover), 33YN2 and [PizzaLovingNerd](https://www.youtube.com/channel/UCmGcm7dhEjS9CIOsOOv8y6w) for their contributions to this community update. Thank you.

Let's get to it.

{{< youtube id="QEBcueElZGE" >}}

**January Community Update Video Synopsis by [PizzaLovingNerd](https://www.youtube.com/channel/UCmGcm7dhEjS9CIOsOOv8y6w)**

**TL:DR**

- New website it up!
- Chats have been reworked and IRC bridged back up; more work on chat infrastructure soon
- Thank you to those who’ve been making documentation for Wiki
- PinePhone KDE CE slightly delayed but shipping soon; issues shipping to the UK
- PineTalk podcast starts next month! Hosted by Ezra from [Elatronion](https://www.youtube.com/channel/UCLN0SPhQo4jAPpTFNsxUnMg) and Peter from [LINMOBnet](https://www.youtube.com/user/EtlamRetep)
- Pinebook Pro and PineTab LCD panel availability looking better; production to resume after CNY
- Pinebook Pro OpenMandriva and AOSC Linux builds are now available
- Pinebook Pro FreeBSD 13 build brinds a lot of functionality to the platform
- Pinebook Pro alt DP display mode available in Manjaro & coming to other distros. Enables DockingDeck and other USB-C dongles
- Pinebook Pro to get Panfrost GPU driver with OpenGL 3.0
- Quartz64 is the name of our next SBC line
- Quartz64 model-A detailed spec and availability roadmap 
- PineTime important work done on the bootloader and release of InfiniTime 0.10.0 
- PineTime InfiniTime fork brings colourful icons, multiple watchfaces and additional functionality (HR + step count)
- PineTime GPS navigation via Amazfish App; Amazefish app has now been ported to Manjaro Linux for the PinePhone
- PineTime WaspOS improvements including theme engine and much more
- **PinePhone Mobian CE available on January 18. Two hardware configurations 2GB RAM/ 16GB eMMC & 3GB RAM/ 32GB eMMC + USB-C dock (Convergence Package)** 
- PinePhone’s modem runs kernel 5.10; first step in open-sourcing
- PinePhone keyboard update and keyboard layout; projected availability April this year
- PinePhone major improvements to KDE Plasma Mobile improvements
- PinePhone - a new OS join the pack; OpenMandriva is now available for the PinePhone
- Pinecil - new firmware is available; Pinecil gets a dedicated update utility
- Pinecil - a red shell version available exclusively in China; you can get the red shell for your Pinecil from the Pine Store
- Pinecil - next production batch before CNY
- PinePower - desktop PinePower details and availability; addressing generic design 
- PineCube - software updates and first attempts at streaming video 

### Housekeeping 

As I’m sure you’ve already noticed, we’ve got a new website. Let me start by thanking Marek (gamiee),  Lucia Zverkova, Chris (Funeral) for getting the page into shipshape for today. Getting it done in time over the holidays was a sprint, but the final result is a page that will serve us well for many moons to come. If you find any typos or broken links, make sure to report them to us - thanks. 

Over the holidays we also completed work on the chat protocol bridge. It is my understanding that all issues concerning the transfer of messages from one protocol to another should now be resolved. However, the entire chat infrastructure will see further alterations in the coming weeks, as developers requested a higher granularity of conversation options. More specifically, we’ll create separate chats for development, so that end-user support questions and general conversation don’t get in the way of dev chat. A dev-chat for PineTime has already been set up and will be bridged to other platforms shortly. More device-specific dev chats will follow shortly. 

I also want to take this opportunity to thank everyone who did their share in tidying up, editing information and adding resources to the Wiki in the past few weeks. Documentation is a vital part of any open source project, and I am very pleased to see many people now actively contributing to the maintenance of existing development resources. 

![](/blog/images/Wiki-1024x551.jpg)

**The Wiki really looks nice and tidy now**

PinePhone KDE Community Edition should start shipping shortly following a two week delay due to a component shortage. This means most of you who pre-ordered a unit should receive your smartphone at the end of this month. That said, we’re facing issues with delivering the PinePhone to the United Kingdom following Brexit. If you live in the United Kingdom and have pre-ordered a PinePhone KDE CE make sure to check your email - we have given you two options to resolve the situation, which we’ll need you to act on now. We apologize for the inconvenience.

![](/blog/images/pinetalk-transparent-1-300x160.png)

**PineTalk Podcast Logo**

Lastly, I am happy to announce that Ezra from [Elatronion](https://www.youtube.com/channel/UCLN0SPhQo4jAPpTFNsxUnMg) and Peter from [LINMOBnet](https://www.youtube.com/user/EtlamRetep) will be hosting the PineTalk - a PINE64 podcast by community members for the community. Episodes of the podcast will be available bi-weekly - as in, available every other week - and will be available on Youtube, Peertube, LBRY, Spotify and Apple Podcasts. Peter and Ezra are working out the details at this time, but you can expect the first episode to drop sometime in February. Make sure to check out the [PineTalk page](https://pine64.org/pinetalk) for more details. 

### Pinebook Pro 

I finally have some good news to report concerning Pinebook Pro and PineTab availability. LCD availability is looking better now, and that means we’re confident that both the Pinebook Pro and PineTab will be back in store shortly after the Chinese New Year. That said, LCD prices are currently very high. 

Because we have always avoided increasing the price point of PINE64 devices, we will do our best to avoid a Pinebook Pro/PineTab price point increase. However, if the choice is between no stock or a slightly higher price point, the latter may be the only way out. This will likely not happen, but I want people to be aware of some choices that might be made down the line. I do not have a specific date for when the production will resume at this point in time, but I’m sure the situation will crystallize over the coming weeks. 

I’d like to put the spotlight on a few Pinebook Pro releases. For starters, we’re happy to announce OpenMandriva Lx 4.2, a Linux distribution using the package manager urpmi which installs .rpm binaries. This will be available for download shortly from the project’s [sourceforge repository](https://sourceforge.net/projects/openmandriva/files/release/4.2/). It ships with KDE Plasma desktop environment and offers a wide range of default apps to get you going. Please visit [OpenMandriva’s website](https://www.openmandriva.org/#omfooter) for more information about the distribution.  

https://dev.pine64.org/wp-content/uploads/2021/01/FreeBSD.mp4

**FreeBSD on the Pinebook Pro via [SleepWalker on Twitter](https://twitter.com/S199pWa1k9r/status/1346180912577454082)**

I am also certain that many of you who have been waiting for a new FreeBSD OS image for the Pinebook Pro will be thrilled to hear that a recently released preview image (FreeBSD 13) fixes a keyboard issue that plagued the system on the Pinebook Pro. My knowledge about FreeBSD is highly limited, so rather than me trying to convey the current state of development I strongly suggest you [read through the thread](https://forums.freebsd.org/threads/freebsd-desktop-for-pinebook-pro.78269/) on FreeBSD’s forum prior to downloading the image. From what I gathered, the thread includes instructions on enabling audio and enabling external networking cards. The first entry in the thread includes the download link. 

Lastly, I’d like to bring everyone’s attention to AOSC Linux, a Debian-based distribution that supports most PINE64 single board computers and devices, including the Pinebook Pro. The reason I wish to highlight this distribution is the wide range of default desktops it offers for the Pinebook Pro, including but not limited to GNOME, Cinnamon, MATE and XFCE. Needless to say, the OS images are mainline and run open GPU drivers, just like the default Manjaro KDE image. I have actually spent some time with the Cinnamon edition of the AOSC build, and I am happy to report that it is snappy and I experienced no apparent issues. You will find the complete list of OS images featuring the various desktops in the [AOSC download section](https://aosc.io/downloads/#aosc-os) on their website.  

![](/blog/images/aosc-1024x576.jpg)

**AOSC on the Pinebook Pro via [PizzaLovingNerd](https://www.youtube.com/channel/UCmGcm7dhEjS9CIOsOOv8y6w)**

Ending this section of the update I’d like to notify you of two other important developments related to the Pinebook Pro. Firstly, USB-C alt DP mode has now been merged in Manjaro’s default OS image for the Pinebook Pro. This means that the Docking Deck and other USB-C docking stations and dongles should now output video, at resolution up to 4K, via USB-C. So if you’re running Manjaro KDE on the stable branch, all you need to do is upgrade your installation via terminal or the GUI package manager. If you want to try Manjaro KDE, then you’ll find up-to-date builds [here](https://osdn.net/projects/manjaro-arm/storage/pbpro/kde-plasma/20.12/).  

The last thing which I find worthy of reporting is that [OpenGL 3.0 will be enabled on the open source Panfrost GPU driver](https://gitlab.freedesktop.org/mesa/mesa/-/merge_requests/8125?commit_id=8a9b2ef82d65132a9c3321d138f2838da8cdf34d) used by most OS distributions on the Pinebook Pro. It will obviously take some time before these patches find their way into every single distribution, but you can rest assured that OpenGL 3.0 will be available on your distribution of choice in the foreseeable future.

### Quartz64

Let me start by congratulating Sundog on being the first to correctly [solve the riddle](https://www.pine64.org/2020/12/18/i-owe-you-a-riddle/) I uploaded last month. He correctly deciphered that “Quartz64” will be the name of our next line of single board computers. It took him just a few minutes from the moment I posted the riddle to submit the correct answers, which tells me I need to step up my game and create more complex riddles in the future. Sundog will be receiving the first production board once those are ready. For those of you who want to learn more about PINE64 products riddles, I opened a [thread on the forum](https://forum.pine64.org/showthread.php?tid=12585) to discuss the topic at length. 

![](/blog/images/RK3566-RIDDLE-1-1024x594.png)

**Still can't believe how quickly this riddle was solved**

Back to the subject on hand; Quartz64 will be the first RK3566 board on the market, and the model-A prototype of the board is already being evaluated internally. We aren’t quite ready to show it off just yet, as there are some design decisions which may need reworking before it gets shipped to devs, but we promise that the reveal is coming soon. We do, however, have some information to share - please keep in mind that all the following refers specifically to the model-A Quartz64. The board will be available in two configurations, more specifically a 4GB and 8GB RAM variant. You will be able to fit the model-A Quartz64 with one of the heatsinks designed for the ROCKPRo64, as both single board computers share both the footprint as well as IO layout. The board will feature multiple USB 3.0 and a USB-C ports, as well as: 4x PCIe, eDP and MIPI display output options alongside a standard GPIO header you’d come to expect. Some of you will surely be excited to learn that the Quartz64 model-A will also feature a dedicated e-ink panel interface capable of supporting a capacitive pen. We will have a 10” e-ink display available in the Pine Store at the time the Quartz64 boards launch. 

Let me say a few words about the roadmap; at present time we aim to have a limited run of both model-A and model-B versions of Quartz64 in a matter of weeks, so that developers can get their hands on the board and start the bringing-up process sometime after the Chinese New Year. We expect that both versions of the Quartz64 will be available more broadly to developers sometime in late Q1 or early Q2 2021. We are also working on a system to fast-track established developers to get their hands on a Quartz64 board. I suspect that, in short, developers interested in getting their hands on the Quartz64 SBCs early will be asked to send an application email similar to the process for acquiring PinePhone development units in November 2019.   

### PineTime (by JF and 33YN2)

In December I finally got some time to work on the bootloader. The bootloader is the first piece of the software that is run on PineTime as it boots. It is responsible for loading the application firmware (InfiniTime, for example) and also safely applying upgrades, once the OTA update transfer is finished. The current version of the bootloader was written mainly by [Lup Yuen Lee](https://twitter.com/MisterTechBlog). Lup is also the one who hand drew the greenish PineTime logo you see when the bootloader is running. Since last September, we also detected and fixed a few bugs and wanted to add a few additional functionality, such as recovery firmware and a more refined user interface.

![](/blog/images/PTupdate-1024x585.jpg)

**Video of the upgrading process on [JF's PeerTube](https://video.codingfield.com/videos/watch/5b70cc41-2e14-49cc-a631-0aa466957169)**

As this is the most critical part of the software, we [requested the help of the community](https://forum.pine64.org/showthread.php?tid=12626) to test it, and received a lot of positive feedback and reports of successful upgrades of the bootloader, which is very promising!

Earlier this month I also released [version 0.10.0 of InfiniTime](https://github.com/JF002/Pinetime/releases/tag/0.10.0). This is a special release because it is mainly composed of contributions from other developers. Additions which will be most apparent to end users are the 2 games which have been added: Paddle, a solo Pong game, and Two, a 2048 clone.

![](/blog/images/gamept-947x1024.jpg)

**2048 clone via [JF on Twitter](https://twitter.com/codingfield/status/1346181120568815616/photo/1)**

Recently, a new [fork of InfiniTime](https://github.com/joaquimorg/Pinetime) appeared on GitHub. This fork, named JoaqTime by the chat community, created by [joaquimorg](https://github.com/joaquimorg/) includes a complete overhaul of the UI, which includes nice and colorful icons, multiple watchface, a step counter as well as a functional heart rate monitor. 

https://www.youtube.com/watch?v=TiiajWmhpfQ

**A video of "JoaqTime" in action**

WaspOS has been on a roll, having many new commits in the past few weeks. A major change is the new theming engine, which has been added to WaspOS recently, allowing you to change the colors of the different components of the UI to your liking. Moreover, something many of you will enjoy is the addition of a software toggle in the menu that lets you dynamically disable/enable applications which could make development much easier. You will also find the two new applications; a haptic alarm application, and a calculator application, which are quite the addition. Expect much more on the horizon with WaspOS, as for example there has been discussion about optimizing the display rendering for a smoother experience.

https://www.youtube.com/watch?v=nps8Kd2qPzs

**Showcase of WaspOS features on the PineTime**

In last month's update, we talked about Amazfish, and announced that [Adam](https://twitter.com/adampigg) has been working on making Amazfish easily portable on other Linux distros and devices. This is now done with Amazfish 1.8.5, and I really hope we'll see Amazfish built and packaged for many Linux distro in the near future. Indeed, it has already landed in Manjaro, and will likely appear in some of the most popular PinePhone distributions in a matter of weeks. 

Adam did not stop there, however, and is now working on a navigation app for the PineTime, based on Amazfish and PureMaps. [Here's](https://twitter.com/codingfield/status/1349097320013582343/photo/1) a picture of navigation working. 

### PinePhone

![](/blog/images/pinephone_mobian_whirl-1024x687.png)

We’ve thrilled to announce that the last PinePhone Community Edition will feature the Mobian Project. Mobian is a Debian distribution tailored to work on smartphones which came into life on our platform, and has now grown to become one of the community favorites. The operating system ships with the Phosh user interface and a mainline Linux kernel with the necessary patches. This edition of the PinePhone supports all core functionality, including phone calls, 4G LTE, WiFi and Bluetooth, deep-sleep suspend state, both cameras as well as GPS. The convergence feature, which turns the PinePhone into a pocketable computer when a monitor, mouse and keyboard are connected via USB-C dongle, also works great on this distro. Lastly, it features an on-device installer, allowing you to determine your username and password, as well as the option to encrypt your installation. 

![](/blog/images/Mobiandocked-1024x768.jpg)

**PinePhone running Mobian in convergence mode via** [**LINMOB on Twitter**](https://twitter.com/linmobblog/status/1328741209691590659/photo/1)

Despite the relatively high level of software maturity, the shipped build should be considered pre-release grade software, with known bugs and issues. In other words, this is still very much a work-in-progress. By the time you receive your Mobian CE PinePhone a long time will have passed since the phone left the factory floor, and many improvements will have been made to the system. Make sure to update your PinePhone the moment you receive it. 

Pre-orders for the Mobian Community Edition PinePhone will open in three days time, on **January 18, 2021**. This community edition of the PinePhone will be available in two hardware configurations: 

**$149** – 2GB RAM + 16GB eMMC

**$199** – 3GB RAM + 32GB eMMC Convergence Package with an included USB-C dock

You can expect a blog post entry on the day this community edition goes live, followed by information on [Twitter](https://twitter.com/thepine64), [Mastodon](https://fosstodon.org/@PINE64), our [Telegram News Channel](http://t.me/PINE64_News), the [PINE64 forum](https://forum.pine64.org/) and elsewhere. As was the case with all previous community editions, we will be donating $10 per unit sold to the Mobian project, to support development of mobile Linux on all platforms. Now head over to [Mobian’s blog and read](https://blog.mobian-project.org/posts/2021/01/15/mobian-community-edition/) what they’ve got to say about the state of their operating system and development for the PinePhone. 

I’d like to thank all projects who participated in the community edition scheme: [UBports Foundation](https://ubports.com/), [postmarketOS](https://postmarketos.org/), [Manjaro Linux](https://manjaro.org/), [KDE Community](https://kde.org/) and the [Mobian Project](https://mobian-project.org/). Thanks to your efforts we’ve managed to breathe new life into the dream of Linux on mobile and started something completely extraordinary. We’ve on track to ship a staggering number of PinePhones, and fully appreciate that the success of the PinePhone is as much yours as it is ours. Congratulations on a job well done! 

For a change, I will start with discussing software news this month. There is much to write about since important progress has been made in the past 30 days, but the most important development of all (at least in my view) is that the PinePhone’s modem is now capable of running mainline Linux. Thanks to work by [Biktor](https://github.com/Biktorgj) and [Konrad Dybcio](http://twitter.com/konradybcio) the first step in opening up the modem has begun. I spoke to Konrad, who asked me to emphasize that presently this is very much a proof of concept, but that an effort is being made to have a community-built mainline Linux which will equal the modem’s proprietary firmware in terms of functionality. This means that users will, eventually, be able to replace the modem’s firmware with a community-built one on their own. Be aware, it is unlikely that we’ll be able to ship it on the device due to various legal constraints. Some parts of the modem, such as DSP firmware, will most likely have to remain closed. Regardless, these implications are obviously massive. At the time of writing this, you can install an operating system, such as postmarketOS, on the modem and even run a Minecraft server on it! 

![](/blog/images/Modem510-936x1024.jpg)

**The news of the modem running mainline kernel made quite the splash**

We also saw a new OS release for the PinePhone this month - OpenMandriva Lx 4.2 is now available for download. The OS uses a package manager called urpmi, which makes it easy to install .rpm binaries on your system. It ships with a slightly older build of KDE Plasma Mobile on kernel 5.10. I have not had an opportunity to test it myself, but it is my understanding that all core functionality found on other Plasma Mobile OS builds is also functional in OpenMandriva Lx. The release candidate image is now available for [download](https://sourceforge.net/projects/openmandriva/files/release/4.2/RC/Pinephone/) from the project’s sourceforge repository. 

![](/blog/images/om-768x1024.jpg)

**OpenMandriva LX 4.2 running on the PinePhone by 33YN2**

On the subject of Plasma Mobile, we’ve seen a lot of developments of this particular user interface in the past weeks. The team behind Plasma Mobile lists all the user experience improvements in a dedicated [blog post](https://www.plasma-mobile.org/2020/12/16/plasma-mobile-update-november-december.html) (which I highly suggest you read), so I will not reiterate platform-agnostic changes here but rather focus on PinePhone-specific improvements. Aside from the quality-of-life and usability improvements, the most important change is responsiveness. While it may not be instantly apparent at the desktop, a significant performance boost can be felt in all default applications. This includes browsing using Angelfish browser, the Discover store and, in more general, when scrolling through long lists or pages. I’ve been testing this Plasma Mobile extensively recently and it's been a great experience all-around; even convergence now works as expected with my monitor, although I’ve heard reports that others still experience issues. If you haven’t tried Plasma Mobile in recent months, I strongly suggest you give it another go. You can download the newest Manjaro KDE development images by [clicking here](https://kdebuild.manjaro.org/images/dev/). 

https://www.youtube.com/watch?v=qkOVWh6WDww

**Performance of KDE Plasma Mobile has been significantly improved recently - by Bhushan from Plasma Mobile team ([original video on Twitter](https://twitter.com/thepine64/status/1347241731801178113))**

Before moving onto hardware, I also need to let you know about the excellent new Manjaro OS images with Lomiri. The Manjaro team, in cooperation with Marius Gripsgard from UBports, have released the next preview OS image, with many more functional elements as well as support for traditional X11 applications! This Lomiri UI is certainly one of the most polished experiences for the PinePhone and the new additions of GPS navigation, GPU accelerated browser, functional Bluetooth (just to name a few) on Manjaro as a base make for a compelling experience. Just yesterday [Dalton Durst from UBports also announced](https://foss2go.com/ubuntu-touch-release-candidate-update-for-pinephone-and-pinetab/) the release of a new Ubuntu Touch RC update for the Pinephone that fixes automatic 3G call switching.

In terms of hardware, we’re well on our way to build the keyboard prototype. We’re currently exploring and prototyping options for including a large battery into the body of the keyboard. In short, we’re working on squeezing in as large of a battery as possible into the keyboard body. We have also finally been given a time-frame for delivery from the design-house and factory; as things stand today, the PinePhone keyboard should be available in April this year. As most of you already know, the keyboard will interface with the PinePhone using the pogo pins, which means that it will attach and replace the back case. We realized that this will be cumbersome to remove and insert SD cards, so we’ve sourced a breakout board for SD cards that will make the task easier with the keyboard attached. For the time being, I leave you with render of the keys and a suggested keyboard layout. Please let us know what you think in the comments section. 

![](/blog/images/KeyboardPP-1024x563.png) ![](/blog/images/Keyboard-keys_render-1024x638.jpg)

**Picture of the key layout (top) and render of the keys (bottom) on the PinePhone keyboard**

Closing off this section, we’ve made the decision to alter the design of the Qi charging case so that it will also be able to accommodate the fingerprint reader. Rather than making two separate back-cases - one for the fingerprint reader and another for the Qi coil, we will spare money and time creating a single mold to host both. Now, I am aware that some people will only want one and not the other additional piece of functionality, so we’re exploring a way to give you an option to choose. Regardless, working this out will take a little time. Hold tight - more information is coming in the next two months.  

### Pinecil

For Pinecil news, we have new firmware available for the Pinecil. Instructions for flashing the new firmware is available on the Pine64 Wiki page. We also now have a new red Pinecil case available in the Pine64 store for $6. The reception from early adopters has been very good, as have reviews from sites such as Hackaday, and we opened a second production run on January 6th although this second run has already sold out. This was a large production-run, and we were not prepared for it to sell out quite as quickly. As a result we’re in the process of producing an even larger production run of the Pinecil, which should be available for purchase in early February. 

![](/blog/images/UpdateUtil.png)

**Picture of the Pinecil update utility by Gamiee**

For those of you who already got a Pinecil, you can now update your firmware to the newest iteration of [IronOS](https://github.com/Ralim/IronOS/releases/). The newest firmware brings multiple bug fixes over the firmware which shipped from the factory, so we highly recommend you upgrade. The process of upgrading is [straightforward](https://wiki.pine64.org/wiki/Pinecil#How_to_update_a_firmware) and has been outlined on our Wiki. Moreover, thanks for the work by Marek (gamiee) the Pinecil now has its own [firmware update utility,](https://github.com/pine64/pinecil-firmware-updater/releases/latest) which even features multiple language options. Pretty nifty! 

![](/blog/images/ChinaEdition-768x1024.jpg)

**Pinecil Chinese special edition**

We also announced that we’ll have an exclusive version of the Pinecil for the Chinese market. The body and packaging on this version of the Pincil are red, but otherwise no different in form of function to the Pinecil available in the West. We do realise, however, that people like to tinker and personalize all their electronics, including their soldering irons, so we’re making the red shell available for everyone to buy in the Pine Store. I am including a video by Peter Feerick - a PINE64 old-timer and a professional kangaroo wrangler - in which he swaps out the Pinecil shell for the red one. 

https://www.youtube.com/watch?v=QXSRw1YoMSI

**Peter exchanges the default black Pinecil shell for a red one**

Lastly, the break-out board is also available for purchase in the Pine Store alongside the default black shell, a small and portable stand as well as the two tip sets. Since many of you asked, we’ve also added some high-quality USB-C to USB-C cables to the store; those can be found in the [_Makespace_ section](https://pine64.com/product-category/pinepower/?v=0446c16e2e66) of the Pine Store, alongside the PinePower PSUs.  

### PinePower

Both the portable and desktop PinePower power supplies are now [in the Pine Store](https://pine64.com/product-category/pinepower/?v=0446c16e2e66). I’ve described the portable PinePower extensively in l[ast month's update](https://www.pine64.org/2020/12/15/december-update-the-longest-one-yet/), so this month I’ll instead focus on the desktop power supply. We made the decision that the desktop PinePower will also include Qi wireless charging, since some may wish to use that for their PinePhone in the future. The desktop PinePower contains two 65W switching power supplies, one of which serves USB-C power delivery port while the other delivers power to the 18W QC3.0 USB-A port, 3 individual 5V 3A USB-A ports as well as 10W wireless QI charging. In other words, it is capable of delivering power to all your PINE64 devices, and even capable of powering the Pinecil while charging the Pinebook Pro, PinePhone and the PineTab simultaneously. 

![](/blog/images/PinePower-Desktop-1.jpg)

**PinePower front view showing output values**

Let me also address comments that I’ve seen online inquiring whether we used existing power supply unit designs. Indeed, as I wrote [last month](https://www.pine64.org/2020/12/15/december-update-the-longest-one-yet/) _“both PSUs are based on reference designs, but we have made significant improvements to the internals so they are more performant than existing offerings”_. Despite both designs being generic, the PSUs have had improvements made to their performance and undergone certification. For instance, the generic design experiences a component failure after 2 hours of sustained full load; we’ve made significant adjustments to this PSU, and it can sustain a full load for over 12hours, based on lab testing.  

### PineCube (by 33YN2)

For the PineCube there has been some progress in the form of a new Community-made Armbian build available which has the Motion daemon preinstalled. Further, a community member has said that they were able to get Motioneye to run on the board at 1-2 FPS. While that low of a framerate is perhaps disappointing, motioneye is a heavy software. There will likely be more luck in regards to something lighter such as Moonfire-NVR or a PineCube-specific software solution that likewise can better leverage the hardware. Last thing regarding the PineCube which is small, but nevertheless interesting is that there is now wiki documentation on how to interface with it using an Arduino Uno (And other Single Board Microcontrollers) as the USB serial connection. Seeing as the Pinecone is simply a Risc-V microcontroller board, it is likely that a PineCone could also be used as a serial interface by jumping the ground and reset pins exactly like you would on an Arduino to isolate the microcontroller.

![](/blog/images/ArduinoSerialPinecube-1024x768.jpg)

**PineCube connected to Arduino by 33YN2**

That's all for this month! I'll catch you all online.
