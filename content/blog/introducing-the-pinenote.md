---
title: "Introducing the PineNote"
date: "2021-08-15"
authors: ["Lukasz Erecinski"]
categories:
  - "community"
  - "pinebook-pro"
  - "pinedio"
  - "pinenote"
  - "pinephone"
  - "pinetime"
  - "quartz64"
tags: 
  - "pinedio"
  - "pinenote"
  - "pinephone"
  - "pinetime"
  - "quartz64"
images:
  - "/blog/images/Introducing-thePineNote.jpg"
---

![](/blog/images/Introducing-thePineNote.jpg)

This month brings news that many of you have been waiting years for - we’re introducing the PineNote, a high-end e-ink device based on the powerful Quartz64 single board computer. But the good news doesn't end here, the PinePhone keyboard has entered production, developers have begun work on PinePhone’s back cases, PineDio development is moving forward and we’ve seen a new firmware release for Pinebook Pro’s touchpad. There’s a lot of ground to cover this month, so let's get to it.

You can watch the synopsis of this month’s community update on YouTube (embedded below) as well as on [Odysee](https://odysee.com/@PINE64:a) and [PeerTube](https://tilvids.com/accounts/pine64tilvids/video-channels). To stay up-to-date with PINE64 news make sure to subscribe to this blog (subscription widget at the bottom of the webpage), follow [PINE64 Telegram News channel](https://t.me/PINE64_News), the [announcements channel in Discord](https://discord.gg/pine64) as well as our [Twitter](https://twitter.com/thepine64) and [Mastodon](https://fosstodon.org/@PINE64).

I’d like to thank [JF](https://twitter.com/codingfield), [Alex](https://twitter.com/AlexRob12252696) (clover), [Dylan](https://twitter.com/DylanVanAssche) (from postmarketOS), [Peter](https://twitter.com/linmobblog) (LinMob), [Alfred](https://twitter.com/fredldotme) (from UBports), [Chris](https://gitlab.com/kop316) (kop316), [Brian](https://mastodon.online/web/accounts/61817) (33YN2), [gamiee](https://twitter.com/gamelaster) and [PizzaLovingNerd](https://www.youtube.com/channel/UCmGcm7dhEjS9CIOsOOv8y6w) for their contributions to this community update.

**N.B.** Comments on the blog post need to be in English and follow our [Community Rules and Code of Conduct](https://forum.pine64.org/showthread.php?tid=13209).

{{< youtube id="AwMKfQtSXPE" >}}

**Community update video summary by [PizzaLovingNerd](https://www.youtube.com/channel/UCmGcm7dhEjS9CIOsOOv8y6w)**

**TL;DR**

- Housekeeping: DHL sent all PinePhones to NZ, so we had to reship all orders (sorry for the delay)
- Housekeeping: Building a temporary cluster to complete and maintain hosting cluster; build log and updates incoming
- PineNote: Announcing the PineNote, one of the most powerful devices of its kind on the market
- PineNote: Quartz64 based; specs include - fast refresh e-ink panel with multiple frontlight settings, RK3566, 4GB LPDDR4 RAM and 128GB eMMC flash storage
- PineNote: Wacom panel compatible with many EMR pens: we will offer our own
- **PineNote: Available this year for $399; early adopters batch includes EMR pen + magnetic cover (later sold separately)**
- PinePhone Hardware: PinePhone keyboard feels great and enters production this month
- PinePhone Hardware: PinePhone keyboard available in September or early October
- PinePhone Hardware: good news re: back cases - fingerprint reader and wireless charging add-ons sorted out, and should be entering production shortly
- PinePhone Software: Ubuntu Touch mirclient support and trust prompts on the PinePhone; 20.04 upgrade Ubuntu Touch coming to the PinePhone
- PinePhone: handsfree and car kit for the PinePhone allowing to answer calls without interaction with phone; will also allow synchronising contacts
- PinePhone Software: LinMobApps features 300+ applications for Linux smartphones
- PinePhone Software: Work on MMS progressing well and work on Visual Voicemail is underway
- Pinebook Pro: New firmware solves many outstanding touchpad issues; majority of people now find the touchpad’s performance nearly perfect
- Pinebook Pro: we’ll see Vulkan support for the RK3399 in Mesa 21.2; it also includes OpenGL 3.1  
- Pinebook Pro: 64bit Box86 AMD64 architecture emulator now available, runs on Arm64 natively 
- Pinebook Pro: Availability late this year looks more likely with decreasing LCD prices; good chance a large batch will be produced at end of the year
- PineTime: InfiniTime 1.3 release brings new watch face and LittleFS integration, paving way to accessing internal 4MB storage for additional apps & functionality.
- PineTime: WaspOS gets new alarm application and frees up 10% of memory; updated micropython
- PineTime: Two iOS companion apps in development for all you iPhone users
- PineDio: JF and Lup received PineDio Stack and PinePhone LoRa back cases; a closer look at the devices and discussion development challenges

### Housekeeping

I know most of you want to get straight into reading about the PineNote but there are two housekeeping items that we need to address first. Gamiee and I will keep it short, we promise. Late last month DHL accidentally shipped all PinePhone orders (bar those dispatching from the EU warehouse) to New Zealand instead of their intended destinations. We initially hoped to quickly retrieve the shipping pallet and have it returned to Hong Kong, but DHL informed us that this will only be possible when an appropriate flight (allowed to carry battery-operated equipment) becomes available. Given these circumstances we made the decision to reship all orders from our Hong Kong warehouse, so you don’t have to wait until the misplaced pallet is returned to us. Those of you waiting for your PinePhones should have received tracking numbers by the time this post goes live, or shortly thereafter. We’re obviously very sorry for the situation, please accept our apologies. As always, you can follow shipping updates [here](https://www.pine64.org/availability-and-shipping-status/). 

[**Gamiee**](https://twitter.com/gamelaster)**:** It is now more than a year since we moved all our services such as the official forum, Wiki and this webpage to a hosting cluster made out of 24 RockPro64s. During this time the cluster faced various challenges, such as for instance nodes freezing up - an issue which was solved by using iSCSI instead of NFS for root filesystem sharing. But except for such relatively minor issues, the cluster has now been running nonstop for 354 days! After we got the cluster up and running, we promised to write an article about it. This never happened however, as the write-up was kept being postponed until we felt the cluster was completed (in its final form). This still holds true: the cluster is still missing some things we’d like to add to it, like power cables for remote reset of the nodes, as well as other things that are hard to implement without shutting down our entire infrastructure. For this reason, we decided to build a small temporary cluster, which will house nodes with the most important services, so that we can finish our hosting cluster without a major disruption to our community services. In the coming weeks I (gamiee) will publish a community post about building this temporary cluster, and I will keep providing updates about the deployment as well as the next steps for the hosting cluster in weeks to come. More information will follow shortly, stay tuned.

![](/blog/images/uptime-cluster.png)

**A screenshot of system uptime on one of the nodes**

### PineNote

You’ve been asking us to create an e-ink device for years, and indeed we actually looked to make one as early as 2017. I even remember publicly ping-ponging ideas with the community members at the time and researching which SoC would be the best fit for such a device. At the time we were looking to create an alternative to the entry-level Kindle and other such big-brand e-readers. We quickly learned, however, that big brands heavily subsidize their e-readers via book sales and even if we sold an open e-reader at cost (or a loss), we still couldn’t possibly match popular devices' price tag. Thankfully, the technology landscape and what is achievable using e-ink has significantly changed since 2017. Since the announcement of Rockchip’s RK3566 we knew our opportunity to create an open e-ink device had arrived. Early this year we made the decision to create the PineNote. 

![](/blog/images/PN_Open-1024x576.jpg)

**The PineNote in the flesh (prototype)**

The PineNote is one of, if not _the,_ most powerful e-ink device available on the market. It shares in much of the Quartz64’s pedigree, sporting the same RK3566 quad-core A55 SoC paired with 4GB of LPDDR4 RAM and 128GB eMMC flash storage. The PineNote is also fitted with two microphones and two speakers, a USB-C port for fast charging and data, as well as 5Ghz AC WiFi. Suffice to say, there is more than enough power in the device to serve its intended purpose (more on that later). The inner frame - the midsection - of the PineNote is made out of a magnesium alloy (similar to the Pinebook Pros outer chassis), making for a sturdy construction, while the back features a pleasantly ‘grippy’ plastic back cover with speaker cut-outs. The e-ink panel is covered by scratch resistant and glare reducing hardened glass. The entire assembly comes in at just over 7mm thick, which is approx. 1mm thinner than the Kindle Oasis 3, if you ever held one of those.

![](/blog/images/PN-PCB.jpg) ![](/blog/images/PN-Open-1024x560.jpg)

**A closer look at the PCB (left) and internal layout (right) (images of engineering prototype)**

With the base-specs out of the way, let’s talk about the e-ink panel, which is indisputably the most important part of the device. The 10.3 inch, 3:4 panel has a resolution of 1404x1872 (227 DPI), can display 16 levels of grayscale. It features a frontlight with cool (white) to warm (amber) light adjustment. What this means in practice is that you can illuminate the panel in dim or dark spaces to your liking. For those of you who don’t know, warm light is usually preferable in very dim spaces since it may significantly reduce eye-strain. I am also sure we’ll eventually see an automatic frontlight implementation, similar to KDE's ‘Night Color’ or GNOME’s ‘Night Light’, which allow the OS to reduce the monitor's (in this case the e-ink panels frontlight) blue light based on time of the day. Atop the e-ink panel sit a capacitive glass layer - for finger touch-based input - and a Wacom electromagnetic resonance layer (EMR) for EMR pen input. We will be selling a EMR pen for the PineNote, but in the event you don’t like it or already have a pen you’re accustomed to, then you can use it with the PineNote (granted it is compatible with the [Wacom EMR standard](https://www.lamy.com/en/emr/)).

_Edit August 16 00:09 UTC_: A previous version of this post listed the e-ink panel's refresh rate at 60Hz. This number requires much more context. It takes multiple frames to display most images on an e-ink panel. The visual performance of the panel also depends on the method of converting the screen image to data the panel understands. We will be unable to make estimates of the panel's true performance in frames per second without much more testing and development. So we've removed the 60Hz figure for now. We apologize for any misunderstanding.

Wrapping up the hardware description section, the EMR pen (recommended by the vendor we’re working with) features a faint LED power on/off indicator, a previous/ next page button as well as an eraser button. I cannot say much more about the chosen pen at this time since I haven’t held it myself yet, but once I get some hands-on time with it I’ll be sure to share my initial impression. And while we can’t guarantee compatibility with any other pens on the market, we’re sure that people will test out their EMR pens and report back on the wiki so everyone can have a buyer’s guide.

We will be making the PineNote available for early adopters later this year for $399. The early adopter’s PineNote batch will ship with a magnetic cover (working with an on-board hall sensor, putting the device to sleep) as well as the EMR pen. Following the early adopter’s batch, both the cover and the pen will be sold separately. 

![](/blog/images/Case_w_Pen-699x1024.jpg)

**PineNote in the magnetic cover and the EMR pen attached**

As far as software is concerned, much of the work to run a mainline Linux installation on the PineNote has already been completed thanks to development done on Quartz64. However, the e-ink panel driver will most likely not be functional at the time of the device’s release in mainline Linux. So initial batches will probably ship with Manjaro built atop of BSP kernel 4.19, unless devs can get the driver to work with 5.XX kernel in the next few months. Time will tell. As for the actual user interface, we’re currently talking to the good folks at KDE and trying to figure out whether Plasma Mobile or regular Plasma (with panel-specific tweaks of course) will be the best fit for this particular device. As you can probably tell, this is an uncharted territory for all parties involved, but we’ll figure it out. Needless to say, the software isn’t finished - indeed, we don’t really even know yet what will work well with this technology and what won’t. It is just the beginning of our journey with e-ink technology, and it will take a long time and much effort to make the PineNote end-user worthy. This is very much an active-development development device at this time, and you should expect it to retain this status for quite some time.

_Edit for clarity, August 15 19:38 UTC:_ We're seeing a lot of excitement and "shut up and take my money, I'll throw out my other e-ink devices tomorrow!" responses to this post, but remember that we are a community of developers first and foremost. If you're looking to buy a PineNote in the first batch, you must expect to write software for it, not to write notes on it. The software shipping from the factory for the first batch will not be suitable for taking notes, reading e-books, or writing your dissertation. It may not even boot to a graphical environment. However, we are excited for what you'll create with this device and we're ready to take the journey with you. We'll be posting more updates on software progress on this blog as they come in.

![](/blog/images/Itsalive-1.jpg)

**Its alive! Pretty impressive, given that [Peter](https://twitter.com/pgwipeout) (pgwipeout) has only had it for 48hrs - picture by [pgwipeout](https://twitter.com/pgwipeout)**

As I see it, the PineNote will eventually not only make for a great device to read books, comic books, sketching, taking notes and productivity in LibreOffice (as someone who does a lot of typing, I am looking forward to connecting a keyboard up to it and not having my eyes burn at the end of the night), but also for browsing the web or listening to internet radio or podcasts. I’m sure some of you lunatics will also use it for terminal work and other such applications - godspeed and have fun with it, you’ve got our blessing. But jokes aside, an open e-ink device such as this really holds a lot of potential and opens multiple avenues to explore. Don’t think of it as an e-ink notepad or an e-reader, it is much more than that. I am looking forward to seeing what people will use it for outside of its core intended purpose. Schematics and other details will be up on PINE64 Wiki sometime between now and launch. 

\[edit 2:50 UTC, October 16\] A preliminary PineNote Wiki site is now up with early schematics (v.1.0) and component list - [click here](https://wiki.pine64.org/wiki/PineNote).

What sort of peripherals would you like to see for the PineNote? As I already mentioned, I’d personally like us to explore creating a dedicated keyboard for it, converting the PineNote into a quasi-laptop device. What else do you think would be an interesting peripheral, expansion or add-on? Please feed us some good ideas, we’ll surely consider them.  

**You can chat about the PineNote on [our forum](https://forum.pine64.org/forumdisplay.php?fid=171) and:**

**[Discord](https://discord.gg/DmGh9PWntT)** 

**[Matrix](https://matrix.to/#/#pinenote:matrix.org)**

**[Telegram](https://t.me/PineNote)**

[**IRC**](https://www.pine64.org/web-irc/)

I talked to the good folks over at Destination Linux about the PineNote and our vision for this new hardware. During our chat we also talked about other PINE64 gear, including the PinePhone keyboard and much more. If you haven’t done so yet, follow [this link](https://destinationlinux.org/episode-239) to listen to the episode.

Before I wrap this section up let me clear one more thing up: I know that the introduction of the PineNote will lead people to think that other RK3566-based devices will follow shortly, but this isn’t the case. This isn’t the best time to introduce new devices in general, and certainly not ones based on a brand new SoC that is just undergoing a mainlining process. Just putting it out there to kill any unnecessary rumours.  

### PinePhone: hardware

This month’s good hardware news doesn't end with the announcement of the PineNote. The PinePhone keyboard has entered production and we expect to have it available in the Pine Store in late September. I’ve now had extensive hands-on time with the latest keyboard prototype and I am thrilled to let you know that it feels amazing. You know that I am always cautious and try to avoid ‘hyping’ our devices - but my choice of words here is quite deliberate, the keyboard feels _amazing_. The keys are sturdy, easy to plunge and have a satisfying amount of key travel. The pressure needed to plunge the keys is also equal across the entire keyboard. The product team and vendor really deserve a pat on the back, they’ve done a great job. I have a few small form-factor devices with keyboards, and I can say with confidence that this is the best I’ve felt; thumb typing on it is pure heaven.

![](/blog/images/keyboard-with-PlaMo-1024x730.jpg)

**I've been using the keyboard with Plasma Mobile for a couple of days and it has been a great experience so far**

The keyboard has also received a lot of overall polish - the hinges have great resistance without feeling overly stiff (as was the case with previous prototypes), molding quirks have been worked out and the fit and finish is now great. The keyboard now also has a really nice matte black (and slightly textured) finish that doesn’t attract fingerprints. One notable difference from previous prototypes is the removal of LEDs in the upper right corner of the chassis. Personally I welcome this development, the LEDs were bright and given the small size of the keyboard they were quite prominent for a lack of better word. But I understand that some may feel otherwise about their removal. Under the hood the PCB has been significantly reworked: we tried to implement all the feedback we received from developers, last of which have been received hours before final PCB layout submission. I’d like to thank [Megi](https://xnux.eu/), [Martijn](https://twitter.com/braam_martijn), [smaeul](https://github.com/smaeul), [dsimic](https://github.com/dragan-simic/) as well as others who spent time reviewing the hardware and suggesting improvements. Thanks guys!

{{< youtube id="lf-E6Sw4V6U" >}}

**A video showing the keyboard prototype in action - video by [Martijn Braam](https://twitter.com/braam_martijn)**

We have now also sent out back case samples to developers, settled on a wireless charging solution and managed to figure out a reliable way to flash the fingerprint-reader firmware at the factory. In result you can expect an introduction of the fingerprint reader and wireless charging back case in a matter of a few weeks, probably sometime in early October. The wireless charging chip is compatible with both Air Fuel and Qi Wireless charging solutions, and follows the [Wireless Charging Consortium](https://www.mouser.com/pdfDocs/An-introduction-to-the-Wireless-Power-Consortium.pdf) standard. This means that not only will the PinePhone charge (as you’d expect), but the chip will also allow us to have a charging rate read-out and control over the charging process itself via i2c. As for the fingerprint reader, the firmware and open software have now been sorted out, and it ought to be rather trivial to implement this functionality in existing PinePhone Linux distributions. As I mentioned in [last month’s update](https://www.pine64.org/2021/07/15/july-update/), the LoRa back case add-on will need to wait a little bit, because we need software to work via i2c. But the good news is that both JF and Lup have received sample units to take a look at. 

![](/blog/images/PCB_wireless_2-461x1024.jpg) ![](/blog/images/PCB_wireless_3-461x1024.jpg)

**Near final version of the wireless charging module (left) installed in the add-on back case (right)**

Before I wrap this section up I wanted to ask: what other back cases would you like to see for the PinePhone? Any suggestions (barring NFC which we discarded for the time being) are welcome. We have some ideas of our own about what to explore once the current back case add-ons are released, but before I share with you what we’re considering I would appreciate hearing your ideas first - leave them in the comment section below.

### PinePhone: Software

This section of the update was written by partner project developers and community contributors:_ [_Alfred_](https://twitter.com/fredldotme) _(UBports),_ [_Dylan_](https://twitter.com/DylanVanAssche) _(postmarketOS),_ [_Peter_](https://twitter.com/linmobblog) _(aka LinMob, the former PineTalk host and LINMOBapps maintainer),_ [_Chris_](https://gitlab.com/kop316/) _(aka. kop316, working on MMS and Visual Voicemail functionality_) and [_Brian_](https://mastodon.online/@BrianA) _(aka. 33YN2, PINE64 moderator and community contributor)_.

_Images and videos by authors / projects._

[**Alfred**](https://twitter.com/fredldotme)**:** Let me start with Mirclient support. Ubuntu Touch on the PinePhone has always used Wayland for displaying app contents.This was quick to do for an initial bringup and the right step for future developments, but meant that certain functionality needed deep thought and reimplementation to allow the same experience across all supported types of devices and GPU driver stacks.

Due to the fact that we wanted to bring the same experience to PinePhone users as quickly as possible, we decided to bring Mirclient support to the PinePhone as an addition to Wayland. This practically means that Ubuntu Touch based on Ubuntu 20.04 will feature support for both apps that integrate well into the overall system as well as allowing Wayland-only apps to continue functioning properly. Wayland support will not go away and going full-on Wayland will be tackled after the Ubuntu 20.04 transition. This is a short-term solution to bridge the gap between the past and the future for both users and developers.

The next subject I want to tackle are trust prompts. The addition of Mirclient support in Ubuntu Touch 20.04 allowed us to bring one crucial feature to PinePhone users: Trust prompts. Trust prompts are a mechanism on Ubuntu Touch to securely ask a user for permissions to certain functionality, on behalf of the application. They slide up, stick above the application and wait for user interaction. If a user doesn’t want to allow an app recording audio then they are able to decide and change it later on. Integration into certain subsystems was necessary, from adapting almost-there Mir code to applying integration patches onto PulseAudio.This means that users can have a bit more trust in the platform as well as having their applications work properly.

![](/blog/images/UT-trust-prompt-512x1024.jpeg) ![](/blog/images/convergent-sheel-2004-1024x576.jpg)

**Example of a trust prompt on Ubuntu Touch (left) and PinePhone running Ubuntu Touch 20.04 in convergence mode (right)**

Ubuntu Touch 20.04 images should be available for the PinePhone soon and users will be able to switch to it either via the command line without losing their data or by reflashing their device.

[**Dylan**](https://twitter.com/DylanVanAssche)**:** Almost every phone over the last two decades can be used in a car's handsfree kit to make calls. Some of these handsfree kits also allow you to synchronize your contacts to the handsfree kit. This way, you can call your contacts through the handsfree kit without even touching your phone. However, that's not the case with the PinePhone as it doesn't support the required Bluetooth profile [Phone Book Access Profile PBAP](https://en.wikipedia.org/wiki/List_of_Bluetooth_profiles#Phone_Book_Access_Profile_(PBAP,_PBA)) to achieve this. Fortunately, Bluetooth PBAP is supported by the [BlueZ bluetooth stack](https://www.bluez.org/) using the OBEX daemon, but the PBAP code hasn't been touched in almost 10 years!

I revived the BlueZ backend in the OBEX daemon to access the Evolution Data Server phonebook of the PinePhone (Phosh UI only) and submitted some patches upstream which will be [available in the next BlueZ release](https://patchwork.kernel.org/project/bluetooth/list/?series=520361&state=*). After applying these patches, your PinePhone can synchronize your contacts with any Bluetooth handsfree kit which can be found in cars!

See [Address book synchronization over Bluetooth on the Pine64 PinePhone running Phosh](https://tube.tchncs.de/videos/embed/e6663f96-3703-4886-aeff-7a79b3c2c8ac).

**Car handsfree working with the PinePhone, how cool is that?**

[**Chris**](https://gitlab.com/kop316/)**:** While I have been steadily working to help finalize MMS support in Phosh, I am excited to show off another phone feature I have been working on: Visual Voicemail (VVM). For those not familiar with Visual Voicemail, it is a way to download and “view” voicemails instead ofdialing a number to listen to them.

I added support with two applications: Visual Voicemail Daemon ([VVMd](https://gitlab.com/kop316/vvmd/)) and Visual Voicemail Player ([VVM Player](https://gitlab.com/kop316/vvmplayer/)). VVMd is a user daemon that retrieves/stores Visual Voicemails from your carrier. VVMd is desktop environment neutral, so it should work with the desktop environment of your choice! While VVMd only has a plugin that works with the ModemManager telephony stack, I am happy to work with someone to add a plugin to support other telephony stacks, such as oFono. VVM Player is the GTK3 front end to VVMd. You can see screenshots [here](https://gitlab.com/kop316/vvmplayer/-/raw/main/data/metainfo/screenshot.png?inline=false) and [here](https://gitlab.com/kop316/vvmplayer/-/raw/main/data/metainfo/screenshot2.png?inline=false). You can also see a video of it in action below.

{{< youtube id="D-OCx5uoJqs" >}}

**A demo of Visual Voicemail on the PinePhone**

Right now, Visual Voicemail on the Pinephone is confirmed to work on T-Mobile USA, T-Mobile USA MVNOs (Mobile Virtual Network Operator), and AT&T USA. If you want to keep up with the development (or help out), feel free to join the Matrix Room (#opensourcemms:matrix.org) or the IRC channel (#opensourcemms on OFTC), which is bridged to Matrix. 

[**Peter**](https://twitter.com/linmobblog)**:** [LINMOBapps](https://linmobapps.frama.io) now lists more than 300 apps for Linux smartphones now. Note that not all apps are packaged for your distribution, nor are they all what you would consider feature-complete. Also, the current technical implementation of the app list does not perform particularly well on the PinePhone (the performance is actually getting worse with every additional app), which is why I am looking to replace it with another solution. You can follow, join and help out the development on [GitHub](https://github.com/linuxphoneapps/) or wait for an early alpha version of the new implementation, which should be out later this month on [alpha.linux phone apps.org](about:blank).

![](/blog/images/linmobapps-1024x474.jpg)

**Maybe its falls a bit short of the PlayStore selection, but boy is it an impressive and well documented list of Mobile Linux compatible apps**

[**Brian**](https://mastodon.online/@BrianA)**:** For those of you missing a way to share recordings of your PinePhone's interface, or a way to share a recording from your camera, user [u/UJC\_theguy](https://www.reddit.com/user/UJC_theguy/) on the official PINE64 subreddit has shared his discovered method of recording video on the Pinephone at 1280x720 resolution and 30 fps. While it's definitely not perfect, this is an excellent step towards video-recording on the PinePhone. Click [here](https://www.reddit.com/r/PINE64official/comments/olyqor/how_i_record_video_on_my_pinephone_in_tolerable/?utm_source=share&utm_medium=web2x&context=3) to learn more.

### Pinebook Pro 

Pinebook Pro owners have a reason to rejoice: a new and much improved firmware for the trackpad has been released. The Pinebook Pro’s trackpad is, or rather was, the main complaint people always voiced about the laptop. It lacked precision, there was delay between the input and the cursor movement, and at times it would act up completely - causing the cursor to skip from one part of the screen to another. All these issues are now gone, and you don’t have to take my word for it - 77% of people who performed the update on their Pinebook Pro and filled in [**dsimic**](https://forum.pine64.org/member.php?action=profile&uid=18910)’s questionnaire rated the firmware as “_feels nearly perfect_”. 

![](/blog/images/tocuhpadimprovementstats.png)

**The new touchpad firmware is a major improvement, and don't take our word for it**

The update process can be performed on any OS distribution and instructions for flashing are available for both Manjaro and Debian (and derivatives). I’d like to thank [dsimic](https://forum.pine64.org/member.php?action=profile&uid=18910) for his hard work on getting the new firmware bundled with the existing tools and writing up flashing instructions. He is currently also working on making the entire process more streamlined for end-users by making an attempt to package the firmware for fwupd. This will, hopefully, make the process trivial in the future. However, the current flashing process can be performed by just about anyone who is capable of following written instructions. So if you have a Pinebook Pro, I strongly advise you to carefully read dsimics [firmware flashing thread](https://forum.pine64.org/showthread.php?tid=14531) on the forum and have a go at it. 

In other Pinebook Pro related news, graphics on the RK3399 might be seeing some major improvements in the next few months. Merged back in June and now released in [Mesa 21.2 is a new Vulkan driver for Arm Bifrost](https://docs.mesa3d.org/relnotes/21.2.0.html) and Midgard graphics called PanVK, and the new Mesa release now also includes OpenGL ES 3.1 support for Panfrost. It should be noted that PanVK is not yet conformant, and that the work on it is still in its early stages, but it is nevertheless very promising and with it being included in Mesa it should see more contributions.

Back in July Box64 was released as the new x86\_64 emulator for ARM64. While the Pinebook Pro community did previously have Box86 for running x86 software on ARM, it only supported ARM32, meaning you had to run it within a container or on a multilib system. With Box64 however, it is now possible to run software compiled for desktops on ARM devices such as the Pinebook Pro without having to use containers or other trickery. Of course, this technology is not magic, and there is a loss of performance through such a layer, even with the technology that Microsoft (WoW64) or Apple (Rosetta 2) use in their operating systems.

Lastly, I want to give a quick update regarding Pinebook Pro availability (we know that many of you are waiting to get one): IPS panel prices have finally started to come down, but their price-point hasn’t yet reached a level where we could manufacture a new production run. That said, we’re hoping to see prices decrease further in the coming weeks, at which point we’ll start exploring the potential for producing another batch. In other words, there is a good possibility that we’ll see another large batch of Pinebook Pros produced before the end of this year. Keep your fingers crossed.

![](/blog/images/gameonbox64-1024x576.jpg)

**Box64 opens up many opportunities on the Pinebook Pro, such as playing X86 games - picture via [Kirfkin on Twitter](https://twitter.com/Kirfkin/status/1420894418857508864)**

### PineTime \[By** [**JF**](https://twitter.com/codingfield)**\]

The activity around the PineTime project is still going strong: InfiniTime released version 1.3 (and many new features are awaiting review), WaspOS features a new advanced alarm application, Siglo is available on Flathub, FitoTrack supports the PineTime out of the box and we have two iOS companion apps in the work.

Let's start with InfiniTime. As announced in the last community update, the [release of version 1.3](https://github.com/JF002/InfiniTime/releases/tag/1.3.0) came with a new watch face named PineTimeStyle. It's a nice and stylish watch face, which is directly inspired by a popular watch face from the Pebble smartwatches. Another new interesting feature from this version is the battery level notification - the watch periodically sends the battery level to the companion app. Gadgetbridge uses this feature to draw a nice graph representing the history of battery usage. Another great feature of this release is the integration of LittleFS. While not apparent to the end user, this small file system in the \*huge\* (4MB) external memory is the first step to new features requiring persistent storage: fitness data, more graphical content, more fonts, more languages, etc.

![](/blog/images/infinitime1_3_1.jpg)

**New watchface (which some of you may recognize from the Pebble) and improvements to existing applications in InfiniTime 1.3**

While development has been slower these past few months, [WaspOS](https://github.com/daniel-thompson/wasp-os) has again still seen a few big improvements. Most notably Micropython was updated to 1.16, and the merging of the previously mentioned Advanced Alarm application has finally happened. The new alarm application will allow you to set multiple alarms on specific days of the week, and it also adds a snooze option. There was also a major memory improvement that frees up 10% more RAM in applications.

There is also good news concerning different companion apps for PineTime. First, [Siglo](https://github.com/alexr4535/siglo), the GTK app allowing InfiniTime to sync the watch with mobile or desktop Linux, [is now available on Flathub](https://flathub.org/apps/details/com.github.alexr4535.siglo). This means it'll install and run easily on any Linux distro that supports Flatpack, such as Fedora.

[FitoTrack](https://codeberg.org/jannis/FitoTrack) is a privacy oriented fitness tracker for Android in which you can log and view your workouts. It records GPS positions, speed, distance, kcal and displays nice stats and graphs about your workouts. It can also connect to BLE heart rate monitors to record your heart rate while you're doing sports. The good news is that it implements the Heart Rate Profile standardized by the Bluetooth SIG, the very same protocol InfiniTime implements to expose heart rate data to the companion app. This allows FitoTrack and Infinitime to work together out of the box without needing any further work on either project. If you were looking for some motivation to exercise this is probably welcome news.

![](/blog/images/fitotrack1-768x1365.jpg)

**FitoTrack app for Android now works with InfiniTime on the PineTime**

A couple weeks ago I [posted a call for Apple/iOS developers](https://github.com/JF002/InfiniTime/issues/486). PineTime and InfiniTime have a growing user base, and some users would like to sync the watch with an iOS device. It seems that my call has been heard as I've recently learned that there are not one but two iOS applications in the works: [Comosus Time](https://gitlab.com/benzmac16v/comosus-time) by [Jim](https://gitlab.com/benzmac16v/) and [Infini-iOS](https://github.com/xan-m/Infini-iOS) by [xan-m](https://github.com/xan-m). These apps are still in early development stages but they already have features like time synchronization, battery level and heart rate monitoring and firmware update (OTA). Let’s us wish Jim and xan-m best of luck with their projects!

![](/blog/images/benzmac16v4-473x1024.png) ![](/blog/images/xanm1-473x1024.png)

**iOS companion apps for the PineTime are in the works - _Comosus Time_ (left) and _Xan-m_ (right)**

Finally, I would like to share this demo from TT-392 showing _Bad Apple_ playing on the PineTime! I was blown away when I saw this 3 minutes and 40 seconds video playing on the limited hardware of the watch. It reminds us how limitless a hackable device can truly be.

https://www.youtube.com/watch?v=RqL8V3xWmxg

### PineDio PineTime \[By** [**JF**](https://twitter.com/codingfield)**\]

Last month we announced the PineDio Stack, an all-in-one development platform based on the BL604 RISCV MCU and the SX1272 Lora module, along with a LoRa back case for the PinePhone and many other LoRa devices.

A couple of days ago I received a nice parcel from Pine64 containing prototypes of these new LoRa devices: the PineDio Stack with a display, another PineDio Stack in a solar enclosure with a bigger battery, a LoRa USB adapter and a LoRa back case for the PinePhone. I'm sure you're as excited as I am about these new devices, so let's have a closer look at them!

The PineDio Stack is a development kit built around the Bouffalo BL604 MCU. This RISC-V processor is really similar to the BL602, except it has more I/O pins available. It runs at 192Mhz, has 2MB or flash memory, 278KB or RAM memory and supports Bluetooth Low Energy (BLE) 5.0. The PineDio Stack also provides LoRa connectivity via a SX1262 LoRa module. Finally, the stack is equipped with a display, a heart rate sensor, a motion sensor, a USB to Serial adapter, a USB-C port, a GPIO port, a JTAG port and a battery charging chip - basically all you need for your embedded and IoT project in 3.5cm2. I haven't been able to check this board yet, but I plan on porting InfiniTime, the FOSS firmware for the PineTime on this board Soon®.

![](/blog/images/pinediostack-front-768x1024.jpg) ![](/blog/images/pinediostack-back-1024x768.jpg)

**PineDio Stack front (left) and back (right) with JTAG, a battery and a PineTime display attached**

The next item I want to show you is the solar enclosure for the PineDio Stack. It consists of a big solar panel, a large battery and the PineDio Stack with its LoRa module. With this device, in example. you will be able to build an autonomous LoRa base station

![](/blog/images/pinediostack-solar1-768x1024.jpg) ![](/blog/images/pinediostack-solar3-1024x768.jpg)

**PineDio Stack solar panel case outside (left) and the internal component arrangement (right) (images of a prototype unit)**

Last month, we also mentioned that the LoRa back case for the PinePhone was taking shape (but we still need an I2C driver to be able to use it from the Pinephone). Here's a closer look at the back case and the LoRa adapter itself:

![](/blog/images/lora-pinephone1-1024x768.jpg) ![](/blog/images/lora-pinephone2-768x1024.jpg)

**PinePhone add-on back case disassembled (left) and the PineDio LoRa add-on module (right)**

From what I can tell, it's based on the SX1262 LoRa module and an ATtiny64, acting as a bridge between the I2C bus of the Pinephone and the SPI bus for the LoRa module.

Finally, let me show you the Pine64 LoRa USB adapter. It's also based on the SX1262 LoRa module and relies on a CH341 USB to Serial adapter to connect to a computer

![](/blog/images/lora-usb1-1024x768.jpg) ![](/blog/images/lora-usb2-768x1024.jpg)

**USB PineDio LoRa adapter**

In the next couple of weeks I'll experiment, develop projects and provide feedback to PINE64 and to the community about these really exciting new devices.

That is all for this month. We'll catch you all in September with more news, updates and announcements.
