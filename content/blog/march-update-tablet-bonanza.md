---
title: "March Update: Tablet Bonanza!"
date: "2023-04-01"
authors: ["Lukasz Erecinski"]
categories: 
  - "community"
  - "pinebook-pro"
  - "pinenote"
  - "pinetab"
  - "quartz64"
  - "risc-v"
  - "star64"
tags: 
  - "pinenote"
  - "pinetab-v"
  - "pinetab2"
  - "quartz64"
  - "unicorn"
cover: 
  image: "Verygood.jpg"
images:
  - "/blog/images/Verygood.jpg"
---

![](/blog/images/Verygood.jpg)

We end the first quarter of the year with news that Star64 will be available for purchase on April 4th and that the PineTab2 and PineTab-V(ery good!) will launch the following week  on April 11th. In this month’s update we also cover PineNote development (I know many of you have been waiting for this) and discuss how software on the device has really taken off in recent months. Finally, CounterPillow - a key RK3566 community developer - sets the expectations for the PineTab2 with some real-life performance examples. Strap on your unicorn horns because there’s much ground to cover this month - let's get to it.  

You can watch the synopsis of this month’s community update on YouTube (embedded below) as well as on [Odysee](https://odysee.com/@PINE64:a) and [PeerTube](https://tilvids.com/accounts/pine64tilvids/video-channels). To stay up-to-date with PINE64 news make sure to subscribe to this blog (subscription widget at the bottom of the webpage), follow the [PINE64 Telegram News channel](https://t.me/PINE64_News), the [announcements channel in Discord](https://discord.gg/pine64) as well as our [Twitter](https://twitter.com/thepine64) and [Mastodon](https://fosstodon.org/@PINE64).

I’d like to thank [Alex](https://twitter.com/AlexRob12252696) (clover), [CounterPillow](https://github.com/CounterPillow) and [Maximilian Weigand](https://gist.github.com/m-weigand) and [PizzaLovingNerd](https://www.youtube.com/channel/UCmGcm7dhEjS9CIOsOOv8y6w) for their contributions to this community update.

N.B. Comments on the blog post need to be in English and follow our [Community Rules and Code of Conduct](https://forum.pine64.org/showthread.php?tid=13209).

{{< youtube id="SujNfkegedM" >}}

**Video synopsis of this month's update**

## TL;DR

- Housekeeping
    - We held our 5th community Q&A session mid-March; thank you to all those who showed up; you can watch the recorded live-stream on Youtube, PeerTube and Odysee
    - The PineStore has been targeted by DDOS and hacking attacks recently, which caused page time-outs and general inconvenience; rest assured nothing was compromised
    - The reworked community site is taking shape and its looking great - help us test it starting April 15
    - PINE64 EU Pinecil restock on April 1st instead of March 31st
- Newsflash
    - Star64 will be available on April 4th in two configurations: 4GB and 8GB LPDDR4 memory for $69.99 and $89.99 respectively
    - Spike in demand for Quartz64 model-A led to temporary lack of stock; more is on the way
    - NotKamui is working on some sweet looking 3D printed back cases for the PinePhone (Pro)
    - yaky-dev has created a 3D printed Samsung Galaxy S20 ultra adapter cover for the PinePhone allowing it to be fitted with a large external battery
    - Despite there not being a dedicated PinePhone (Pro) section this month there are some interesting PP(P) news: QT6 on the PinePhone, Lup emulates the PinePhone and Ubuntu Touch is finally available for the PinePhone Pro
    - delipunch fitted the Pinebook Pro with a Peltier module and saw some good results
    - Salvador showcased old-school PC games running on the Pinebook Pro in BOX86; this included UnrealTournament 1999 - one of my favorite games
    - Jedikaal has written up instructions on how to run Klipper - a popular 3D printing firmware - on the og Pine A64
- PineTab-V
    - PineTab-V launches at the same time as the PineTab 2 - on April 11th
    - Powered by unicorns and candyfloss 
    - Unicorn syncs seamlessly with pen and features intercompatible with both PineTab2 and PineTab-V
    - V…ery good section - must read 
- PineTab2
    - PineTab2 will be available for pre-order on April 11th
    - Ships with DanctNix Arch Linux with KDE Plasma Desktop (software for early adopters)
    - CounterPillow talks about PineTab2’s performance: video decoding, watching Youtube, browsing the web and working with PDF documents 
    - Tested on Plebian - a vanilla Debian for RK3566 devices 
- PineNote
    - Linux is finally taking shape on the PineNote and flashing Linux OSes is now simpler than in the past 
    - There is now a dedicated Debian with GNOME image with tailored settings for grayscale
    - Other OSes and desktop environments are being worked on too (SWAY and postmarketOS)
    - The e-paper panel now performs well (still WIP) under Linux and Xournalpp has been worked on allowing for very good pen input
    - No promises made at this time but certainly now it looks a viable Beta product for early adopters

## Housekeeping

Earlier in March we held the fifth community Q&A session and I’d like to thank everyone who joined in asking questions in the chats. I felt like this was one of the best Q&As thus far, not in the least because we didn’t run into any major technical issues and managed to successfully stream to Peertube this time around. Following the Q&A, Marek and I spoke about extending the sessions up to 2 hours. As things stand, we usually end up running out of time and many questions remain unanswered. Let me know in the comments whether you’d like us to make the Q&A sessions longer. I am also interested in learning whether moving the Q&A session to the weekend - ideally a Sunday - would suit the community better. We currently don’t have a firm date for the next Q&A but it will likely be held at some point in June. That said, due to Marek’s and my summer vacation plans the Q&A may be moved to either late May or early July  - we’ll let you know closer to the date. You can watch the last Q&A session below. 

{{< youtube id="N9_nOjAtsmw" >}}

**Community Q&A live stream recording**

The Pine Store and community website have been targeted by DDOS and hacking attempts this past month, which resulted in the sites being placed in maintenance mode at times. A it will likely come as no surprise to the majority of you, both sites are frequent targets of malicious parties but this most recent attack has been the biggest to date. It has also shown signs of coordination, effort and skill. But you can rest assured that steps have been taken to cull the DDOS attack and that no data has been compromised. The reason why I’m mentioning this in the update is because the Wiki and forums were also affected, causing sluggish response times and server time-outs, and I’ve been told that users experienced problems accessing community services over the course of two days. Things should be working as normal from here on; we are actively monitoring both sites and cluster-based services.           

Speaking of the PINE64 website, in [December of last year](https://www.pine64.org/2022/12/15/december-update-merry-christmas-and-happy-new-pinetab/) I reported that we started on a complete community website redesign. This redesign is much more than a new coat of paint - in fact it takes this website in a completely different direction. The goal is to make the site a hub that ties together all the existing community services while simultaneously exposing key community-driven elements of the project. For instance, clicking the _community_ tab presents you with all the relevant links to chats and other communication platforms, while new blog posts, podcast episodes and news take center stage on the main page. Another part of the redesign, and one that I absolutely love, is the incorporation of all documentation on the actual website. The page is also much cleaner and significantly more light-weight - it is really snappy and a pleasure to visit. We are planning on initially launching the site for testing alongside the current webpage - those willing to help us test and offer feedback are welcome to visit the site starting April 15, here’s the page: `beta.pine64.org/`.

![](/blog/images/Pine64-community-new-page-1-1024x720.png) ![](/blog/images/Pine64-community-new-page-2-1024x716.png)

**Here's a sneak peek at the upcoming community website**

Lastly, the PINE64 EU store will be restocking the Pinecil V2 on April 1st instead of the planned March 31st. However, subsequent Pinecil V2 restocks in April will land on Fridays, with the first scheduled for April 8th. I also want to let you know that due to the upcoming Easter Holidays there won’t be any shipping from PINE64 EU between April 6th - 13th. The PinePhone BE2 has now also restocked. I also know that many of you have asked about PinePhone Pro’s availability in PINE64 EU - I currently hope to have a batch in the latter half of April. If you want to keep track of PINE64 EU’s hardware availability and restock then I invite you to follow [Twitter](https://twitter.com/pine64eu), [Mastodon](https://fosstodon.org/@pine64eu) and [Telegram](https://t.me/pine64eu).  And no, none of the above is an April fools joke :)  

**Newsflash** 

I come bearing great news for everyone waiting for Star64 - the SBC will be available for purchase on April 4th. Due to some last-minute logistics issues we failed to make the March launch date announced in February - our apologies for the slight delay. The boards have now finally been delivered and getting packaged and ready for dispatch. Let me just quickly reiterate the Star64 features: Quad core 64bit RISC-V, HDMI video output, 4x DSI and 4x CSI lates, i2c touch panel connector, dual Gigabit Ethernet ports, dual-band WiFi and Bluetooth, as well as 1x native USB3.0 port, 3x shared USB2.0 ports, PCIe x1 open-ended slot and GPIO bus pins (i2c, SPI and UART). The board also features 128M QSPI flash and eMMC and microSD card slots. The board will be available in two different RAM configurations - with 4GB and 8GB LPDDR4 memory for $69.99 and $89.99 respectively. The [Star64 store page](https://pine64.com/product-category/star64/) ought to already be live when you read this, but will be listed as out of stock until the 4th. 

![](/blog/images/Star64-in-PineStore-1024x595.png)

**Star64 will be available in the Pine Store on April 4th, it will be listed as 'out of stock' until then**

In other SBC news, we’ve seen an increase in Quartz64 interest recently (which is awesome!) - the model-A in particular - which caused the board to go out of stock temporarily. I wish to let you know that a new production-run is already underway and the next batch's delivery is expected soon. Indeed, it may already be available at the time this community update goes live, but no promises. Please visit the Pine Store [Quartz64 page](https://pine64.com/product-category/quartz64/) to learn of the SBC’s availability.  

User NotKamui in the Matrix PinePhone chat has been working on some incredibly cool looking back cases for the PinePhone. While there have already been many community-designed replacement 3D cases made in the past, this design stands out as one of the absolute best. Not in the least because the case is transparent and features an embedded Tux. NotKamui is currently traveling (at least from what I gathered) and hasn’t had the time to complete the design nor upload the STL files, but hopefully we'll get a chance to print our own version of the back cases soon. Once files find their way onto an online STL repository I’ll make sure to revisit this topic and offer up relevant links. 

![](/blog/images/Pine64-community-made-back-covers-1024x768.jpeg)

**These are some really awesome looking cases** 

Staying on the subject of the PinePhone and 3D printed cases for a moment longer, user [yaky-dev](https://www.thingiverse.com/yaky-dev/designs) created a 3D printed Samsung Galaxy S20 ultra adapter cover for the PinePhone. This adapter allows you to use S20 Ultra accessories with your PinePhone or PinePhone Pro. Most notably, you can outfit the PinePhone (Pro) with the S20’s battery case, which adds a whopping 7500mAh to your device. For those interested in the case adapter here is the link to the [Thingiverse website](https://www.thingiverse.com/thing:5867739) - I think this is a very cool community project.

![](/blog/images/PinePhone-S20-adapter-2.jpeg)

**Has anyone ever said 'no' to more battery life?**

There is no dedicated PinePhone section in this month’s community update - instead I decided to squeeze the most noteworthy phone developments into the Newsflash section. The first piece of news relates to KDE Plasma Mobile: [Seshpenguin](https://social.sineware.ca/@seshpenguin) tooted images of the PinePhone running QT6 which, at least according to them, may be the first instance of the software running on real hardware. This is obviously important news in light of [KDE’s recent announcement](https://mail.kde.org/pipermail/kde-devel/2023-February/001699.html) that they’re gearing up to launch its next release with QT6 only. The second piece of PinePhone news relates to [Lup’s](https://twitter.com/MisterTechBlog) efforts to emulate the Unicorn Emulator. His [lengthy blog post](https://lupyuen.github.io/articles/unicorn) on this subject provides a complete walkthrough of the process and includes very detailed information about getting started with emulating the platform. It is worth a read for those interested in alternative software development on the PinePhone, something which I touched upon last month. Last but certainly not least, we’ve received word that it is now possible to run [Ubuntu Touch on the PinePhone Pro](https://ubports.com/blog/ubports-news-1/post/pinephone-and-pinephone-pro-3889). Be warned, however, that this is an introductory build which has a number of PinePhone Pro-specific quirks, such as upgrading via apt. Some key features are missing in the build too (such as camera functionality). I am really happy to finally see Ubuntu Touch available for the PinePhone Pro and I’m sure many in the PINE64 community will be too - thank you UBports team!  

![](/blog/images/QT6-on-PP-2-768x1024.jpeg) ![](/blog/images/QT6-on-PP-768x1024.jpeg)

**QT6 on the PinePhone**

Reddit [user delipunch](https://www.reddit.com/user/delipunch/) shared a cool Pinebook Pro mod, in which they replaced the default passive cooling solution used in the Pinebook Pro with a Peltier module. For those who do not know, the Peltier module achieves cooling by running current through a thermocouple rather than moving air or liquid over a surface to dissipate heat. Prior to the mod, with all cores under full load, the Pinebook Pro would throttle at 75\*C, but with the new cooling solution it doesn’t. This is a very cool mod and while it does look rather complex, and thus unlikely as something many of us could attempt, I’m sure there are some in the community with the technical know-how who will attempt to replicate it.

![](/blog/images/pltier-cooling-PBP.webp)
![](/blog/images/Peltier-cooling-PBP-2-results.webp)

**Peltier module in the Pinebook Pro does appear to help with SoC throttling under full load**

[Salvador Liébana](https://twitter.com/salva_lieb) has showcased a number of popular retro-PC games running well on the Pinebook Pro using [BOX86](https://github.com/ptitSeb/box86). If you don’t know - BOX86 allows you to run x86 Linux programs on 32bit and 64bit Arm systems. Some of the games showcased by Salvador included Miami Heat, Raptor: Call of Shadows and the legendary Unreal Tournament from 1999. It is impressive how far the open source driver has gotten since the initial launch of the Pinebook Pro in 2020. I have recently gotten back into retro-gaming as a weekend activity and will surely be testing this out.    

{{< youtube id="2el2JViu6sQ" >}}

**The year 1999 gave us the Matrix, Eminem's 'My Name is' and Unreal Tournament**

Lastly, [Klipper](https://www.klipper3d.org/) - a popular 3d printing firmware - has been shown to run on the original Pine A64. The reddit user [Jedikaal](https://www.reddit.com/user/Jedikaal/) has written up a very comprehensive set of instructions on how to get the software running. While the instructions pertain to the Pine A64 in particular there is no indication that they wouldn’t also work on other PINE64 SBCs such as the Quartz64. I have recently seen a number of questions pertaining to PINE64 boards and 3D printing (I think I even answered one during the community Q&As), so I’m looking forward to seeing more contributions such as this from members of the 3D printing community. 

## PineTab-V

Here’s the big news: both the **PineTab2 and PineTab-V** **will be available for pre-order on April 11th**. ‘The PineTab-V, what?’ - I hear some of you asking, why yes, have we failed to mention that we’re working on two new PineTabs? What does the ‘V’ in ‘PineTab-V’ stand for? The ‘V’ stands for ‘very early’ or ‘vaguely functional’ and potentially even ‘Vociferously viperous’ (yeah, I bet you had to look it up even if you’re a native speaker, and no, it doesn’t make sense - I’m aware). Honestly, we haven’t decided ourselves yet. It was meant to be a surprise, but given the fact that the update goes live on April 1st and we’re only a few days away from the PineTab2’s launch, I figured I may as well just spill the beans. Those of you keenly following our project may already have guessed that we will be introducing a Linux device based on V(ery good!)-architecture at some point this year. I suppose you didn’t really have to guess, I spelled it out for you in December, so all you really needed to arrive at this conclusion was a pair of eyeballs and a rudimentary ability to read. In a nutshell, here’s what I wrote at the time: we’re very keen on creating new and innovative RISC-V devices as well as RISC-V counterparts to existing and upcoming Arm devices. Not sure if I could have written it any plainer than this.

![](/blog/images/Not-PineTab2-1024x969.jpg)

**Here's a picture of the PineTab-V, seriously. Picture taken on January 2025.**

So here we are - the PineTab-V is identical to the PineTab2 in all ways but the SoC. It features the same chassis, LCD panel, memory and storage configurations and even SKU price-points. Seriously, the picture I inserted above isn’t actually the PineTab-V, it's the PineTab2. Hadn’t I said anything you would be none the wiser. Overall, It’s really low effort and truly as lazy as it gets. If you’ve read the [December](https://www.pine64.org/2022/12/15/december-update-merry-christmas-and-happy-new-pinetab/) and [February](https://www.pine64.org/2023/03/01/february-update-things-are-taking-shape/) community updates, then you already know just about everything there is to know about the physical characteristics of the PineTab-V despite never actually having read a thing about the PineTab-V. Confusing, I know. Regarding the pricing: we did consider charging more for the PineTab-V, since it actually costs more to manufacture than the PineTab2 (seriously), but given that it is effectively a glorified paperweight at this point in time it just didn’t feel right. 

Ok, so I suppose there is one more thing you should know about the PineTab-V after all - while it walks and quacks like PineTab2, it sure as heck isn’t an Arm machine. You are basically buying into an idea, a vision, a dream \[note to self - insert more inspirational words here to motivate them to pick one up\]. Indeed, unlike its Arm brethren it doesn’t even boot Linux as of today - at least not as far as I know. So if you are in the market for an open, high-quality and sexy looking tablet that doesn’t work since the software for it is a-way-of from pre-Alpha then you’ll be thrilled to know we’ve got you covered! On the plus side, it does come bundled with the unicorn with a mic stuck to its head we promised [last year](https://www.pine64.org/2022/04/01/introducing-the-pinebuds-and-pinepod-seriously/). The unicorn has already been confirmed to sync with the PineTab-V via BT LEL and interfaces directly with the PineNote’s pen. Top-tier stuff this, seriously. Ok, time to wrap this up - here’s what I want you to take away from this section: if you want a working Linux tablet then go with the PineTab2. However, if you already completed your Picasso collection and no longer take pleasure in neatly arranging your sports cars in the garage, but you have an interest in things ending with the letter ‘V’ and some money to burn, then I feel like the PineTab-V is a prime-candidate pick-up option for you. Go on, do it, I dare you.

## PineTab2 (By Lukasz and CounterPillow)

Much of this month’s section on the PineTab2 has been written by CounterPillow who is one of the developers who tirelessly worked on the RK3566 platform since last year. I think that I have covered everything I wanted to say about the PineTab2 in the [December announcement](https://www.pine64.org/2023/03/01/february-update-things-are-taking-shape/) and [last month’s update](https://www.pine64.org/2023/03/01/february-update-things-are-taking-shape/) already, so it is for the best that someone working on the actual software gets a say now. There are, however, two bits of important information I wish to share with you before I hand this section off: firstly, the PineTab2 will ship with a build of [DanctNix Arch Linux](https://github.com/dreemurrs-embedded/Pine64-Arch/releases) for Arm with KDE Plasma Desktop. Arch Linux is what we [demoed at FOSDEM](https://www.pine64.org/2023/03/01/february-update-things-are-taking-shape/) earlier this year and felt that it performed rather well for such early-state software. Obviously the build that ships with the PineTab2 will be newer than than the FOSDEM demo, but you should be warned that it won’t include any critical new functionality (at least not out-of-the-box - improvements and additional enablement are obviously possible, and even likely, between the time units get flashed at the factory and when end-users receive their units). 

![](/blog/images/pinetab2-running-Arch-KDE-plasma-Desktop-909x1024.jpg)

**DanctNix Arch PineTab2 build in action**

I chatted briefly with Danct12 earlier this week and he wishes for you to know that the PineTab 2 software is still a work-in-progress, so you should always check for updates as things are likely to progress even quicker once people get their hands on the hardware. If you have any questions concerning the build and current status of the software then you are welcome to join the #archlinux-pinephone:kde.org channel on Matrix or [@archmobile](https://t.me/archmobile) on Telegram. Danct12 also wanted me to let you know that the Wi-Fi is disabled on the PineTab2 by default due to driver stability issues, so you'll have to run modprobe bes2600 to get it working. Now, the second, and perhaps the most important thing I wanted to write before CounterPIllow shares their insight is that the PineTab2 will be available on April 11th… bundled the unicorn with a mic on its head, of course.  

\[**Quick note:** I have taken the liberty to edit CounterPillow’s contribution for style solely - none of the written contents were altered. CounterPillow’s section starts below.\]

I've seen some talk about how the RK3566 in the PineTab2 won't perform well for its intended purpose. While it is true that the RK3566 system-on-chip is optimised for low power draw rather than raw performance, this does not mean it's a bad SoC for a tablet. First off, yes, it is obviously slower than a RK3399 (Pinebook Pro, ROCKPro64) running at its full clock speed. The 4 Cortex-A55 cores in the RK3566 are in-order cores, meaning they do not reorder instructions for higher performance. This makes them comparable to the four Cortex-A53 cores found on the RK3328 (ROCK64) or A64 (PineTab1), but much faster and more efficient as it is a newer core.

But will it be enough for watching YouTube? Well, if we assume hardware decode is working and we're rendering the video through hardware scalers, we can naturally reach the advertised 4K@30 video output. But on mainline kernels, i.e. kernels that are what sits in Linus Torvalds' git tree, we're currently missing a driver for the "rkvdec2" hardware decode block, and even if we had such a driver, the support for its v4l2-request user space API (the interface between programs and the kernel) is still not great.

So let's look at pure software decoding. That is, video decoding performance without fixed function hardware acceleration, just what the CPU cores can do with their vector instructions. Anyone without a PineTab2 can do this, so long as they own some other RK3566 device. I ran these tests on a Quartz64 Model A, running [Plebian](https://plebian.org/). For this test, I kept things simple. I decoded 1080p and 720p videos fetched from YouTube with yt-dlp at the maximum speed the CPU could muster, using an FFmpeg build from Debian Bookworm's repositories, also built against the libdav1d from Debian Bookworm. In essence, this means FFmpeg 5.1.2-3 and dav1d 1.0.0-2. The video used for the test were the various video streams YouTube offers for [https://youtu.be/Lwk8e2q4qHo](https://youtu.be/Lwk8e2q4qHo), a 25 fps video. Five minutes of the video were decoded as fast as possible with the command ffmpeg -i videofile -to 5:00 -f null - -benchmark and the achieved average framerate was calculated with 300 seconds / rtime \* 25.

We arrive at the following results:

|   |av1 (dav1d)|h.264/avc|vp9 (ffvp9)|
|---|---|---|---|
|1080p|50.50 fps|75.34 fps|63.09 fps|
|720p|105.74 fps|200.16 fps|146.49 fps|

Keep in mind that the PineTab2 comes with a 1280x800 panel, meaning you'll be consuming 720p content unless you have an external monitor connected. For 720p content, we're above real time speeds even for theoretical 60 fps content on the newest and most complex video codec (AV1). Even at 1080p, software decoding is still well in the realm of playable for most content, with just 60 fps AV1 not being real time. In short, from a decode perspective, the PineTab2 will play the youtubes fine, even in the absence of fixed-function hardware video decode acceleration. The performance for video rendering is another question however, and depends heavily on the indirections the buffers take before arriving at the display. From personal experience, I can attest that at 1280x720 even mpv's gpu shading pipeline based video output will work fine for 60 fps content under kwin on Wayland. 1080p 60fps content is looking less rosy with mpv though, where the same configuration (kwin wayland, gpu shading pipeline rendering, software decode) is dropping frames. This may be avoided once we have a hardware decoder driver, as we can then pass the dmabuf buffers from the hardware decoder directly to the output with mpv's new dmabuf-wayland video output.

A more common use case is web browsing. For this test, I used Chromium with a few flags enabled (wayland, experimental performance stuff) on a 1080p display on a kwin wayland plasma session, again on a Quartz64 Model A, which has the same SoC as the PineTab2. You can see that we get quite a smooth web browsing experience from this video capture (Ignore the crunchy looking text rendering, that's an artifact of my $9 HDMI capture device's 4:2:2 downscaling.):

{{< youtube id="c-YSLLiUxRQ" >}}

**Here's a glimpse at the type of performance you can expect from the PineTab2**

Firefox will be slower as it really doesn't want to do GPU rendering on Panfrost and its JS engine isn't as optimised for ARM. Compared to PineTab1, this is a night-and-day difference. You can _actually browse the web!_

Another task many want to use a tablet for is to browse through documents like PDF files. One particularly heavy workload for this is tabletop gaming rule book PDFs. They're usually richly illustrated, taking a few seconds even on x86 computers to do a page flip with some reader software. Out of curiosity, I tried the "Warhammer Fantasy Roleplay" 2nd Edition core rule book, which is my heaviest PDF file, on the Quartz64 Model A. I can't show you an HDMI capture of the experience for copyright reasons (Games Workshop, if you wanna allow this use hit me up, I swear we'll treat your IP with dignity, unlike some game studios), but I can describe the results in text form.

Using Okular to browse through the PDF was terrible. While Okular works fine for richly illustrated scientific papers and other such content, the might of Sigmar brought it to its knees, resulting in 5+ second page loads. MuPDF, a more minimalist document viewer, copes well however. Flipping to the next page takes about 1 second from key press to the next page being rendered. This is more than usable enough for quickly browsing to the right page during a sweaty tabletop gaming night.

The RK3566 SoC found in the Quartz64 and SOQuartz line of devices has gotten fairly good mainline support in Linux. To showcase this, me (CounterPillow) and diederik banded together to create [Plebian](https://plebian.org/), an installer- free Debian image for Quartz devices based on Debian Bookworm, using its unmodified kernel package.

## PineNote

I know that many of you have been eagerly awaiting to hear news of the PineNote and I am happy to finally bring you an update on the device. Before I start, however, I should make it clear that everything I write regarding the software status of the device is based on information collected by [Maximilian Weigand](https://gist.github.com/m-weigand) - a developer working on the PineNote, who was kind enough to detail all the information for me. Perhaps the biggest news about the PineNote is that finally, after many months of development, Linux on the device has reached a reasonably mature stage and there are even two sets of very promising and user-friendly software options being designed for it. In the words of Maximilian _“the PineNote is now in pretty good shape for basic linux use; it can be flashed with only a USB connection, (...) the factory test Android is not required for any of the linux installation steps (...) \[and\] u-boot images can be flashed via rkdeveloptool with no UART debug connector required anymore (...)”._ From the get-go, this addresses some of the biggest problems that the PineTab2 development faced from the start - it is now possible for end-users to flash OSes of their choice on the PineNote relatively pain-free. 

Indeed the entire boot sequence has received major boons in recent months, making the process of powering on the device and starting an operating system much more streamlined. Originating in the downstream rockchip u-boot sources, an u-boot version is now available that displays pre-prendered images for boot entries and can be controlled using the power button, with touchscreen support for the u-boot menu in a proof-of-concept status. Importantly this u-boot version comes with an [e-ink-enabled devicetree](https://github.com/talpadk/u-boot-pinenote) and does not require any android partitions or files anymore. 

So then, what can the PineNote boot? For starters, thanks to the support by, and encouragement from, [diederik](https://forum.pine64.org/member.php?action=profile&uid=23798) there is now a working linux [6.2 branch for the PineNote](https://github.com/m-weigand/linux/tree/pinenote_6-2_v3), which is shared by those working on complete OS images of the device. One of the options now available, and one that ships with the above-mentioned u-boot, is a refined build of Debian with GNOME. This tailored build includes some modifications to the GNOME desktop environment and a custom extension to control epd display settings  looks and performs well on a grayscale screen. It uses a theme developed by user [MichiMolle](https://github.com/MichiMolle/PNEink/commits?author=MichiMolle). This theme removes shadows and animations, adds gray-scale icons and improves the performance of GTK 3 and 4 on the PineNote. However, this isn’t the only desktop environment option being currently developed - a comprehensive collection of configurations and instructions for using Sway with the PineNote was collected by user [hmpthcs](https://github.com/hmpthcs). I should also mention that a dedicated postmarketOS build for the PineNote is actively worked on by [Phodina](https://gitlab.com/phodina). 

This is one of those instances where an image, or a video in this particular case, is worth a thousand words - so I invite you to marvel at the short clip showcasing Linux on the PineNote.

{{< youtube id="_U6V5B37_l0" >}}

**This looks pretty awesome doesn't it?**

One of the biggest selling points of the PineNote is obviously its display. In the past I’ve reported on the iterative work that developers had to endure to reverse engineer and subsequently enable PineNote’s e-paper panel; we can now finally see what this painstaking work has resulted in. Much of the hard work on the panel was done by [pgwipeout](https://github.com/pgwipeout) and [smaeul](https://github.com/smaeul) - they did the majority of the hard upbringing and driver work, and hence it is largely thanks to them that the panel is now in a functional state. Thanks to a collective development effort the panel went from being buggy and very sluggish to really crisp, detailed and responsive. All this in just one year. Reading and browsing on the device is one thing but functional pen input is a whole different can of worms. To this end I hope you’ll be just as pleased as I am to hear that user [hrdl](https://gitlab.freedesktop.org/hrdl) has been continuously working on improving the drawing performance of [xournalpp](https://github.com/xournalpp) on the PineNote and shared a video of the pen’s input performance. While the pen’s input latency is certainly not perfect, it is nonetheless impressively fast and I could imagine myself using it without the input delay tripping me up while writing. Take a look for yourselves and let us and the developers know your impressions in the comments section. 

{{< youtube id="-m0TWhK8D8g" >}}

**I don't know about you but this looks pretty pretty smooth to me!**

So, then, what does this mean for the future of the PineNote? - I don’t want to jump the gun and promise anything at this time. What I can say, however, is that I’ll talk to TL and Marek about these developments in the coming days and explore the viability of bringing the PineNote to more people. I also want to say that I am completely blown away by how much work has been poured into the device in the recent months. It is incredible to see all the passion and raw effort that has gone into making the vision of an e-paper device running full-fledged real Linux a reality. Thank you to all those who have worked on the PineNote for the past year, I take my hat off to you. 

This is it for this month’s update, I hope you all thoroughly enjoyed it. I’ll catch you next month if the unicorn doesn’t get me in my sleep.
