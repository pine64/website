---
title: "November Update: Something Borrowed Something New"
date: "2024-11-21"
authors: ["Caffeine"]
categories: 
  - "community"
  - "news"
  - "pine64-community"
tags: 
  - "avaota-a1"
  - "pinetab-v"
  - "pinecam"
  - "pinenote"
  - "pinedio"
  - "ox64"
cover: 
  image: "NovemberBanner_2024.png"
images:
  - "/blog/images/NovemberBanner_2024.png"
summary: "This month we are announcing a couple of new products including a SBC and a successor to the PineCube. We have updates to share about the PineNote and the PineDio USB adapter this month along with a talk by one of our community members Dsimic."
aliases:
  - "/2024/10/18/november_2024/"

---

Welcome back to a new monthly Pine64 community update! This month we are announcing a couple of new products including a SBC and a successor to the PineCube. We have updates to share about the PineNote and the PineDio USB adapter this month along with a talk by one of our community members Dsimic.

![](/blog/images/NovemberBanner_2024.png)

{{< toc >}}

---

## PineCam

{{< credits "Authors: Lukasz, Caffeine" >}}

![PineCam prototype render](/blog/images/November_2024/pinecam_1.jpg)

The first new device we will be introducing this update is the PineCam! The PineCam is a successor to the PineCube IP camera, but with a much more polished design, better specifications and more features. While the PineCube didn't achieve the success the project had hoped for, we believe it wasn't due to a lack of interest in such hardware, but rather the way it was executed. We've gathered feedback, learned from what went wrong, and have gone back to the drawing board. This time, the PineStore have decided to take a different approach, using a System-on-Chip (SoC) already in our hardware lineup. The device includes more RAM (compared to the PineCube's 128MB), and utilizes a camera interface that "just works".

The PineCam is based on the oz64 single board computer which is powered by the SG2000 system on a chip found in the new Oz64. The SOC includes two RISC-V cores (C906 @1Ghz + C906 @700Mhz) and one ARM core (Cortex-A53 @1Ghz). You can find more information on the specifications of the Oz64 and the SOC it's using [here](https://pine64.org/documentation/Oz64/). The device features 512MB of RAM, providing just enough memory to run a full Linux-based OS such as MotionEyeOS, a popular surveillance camera operating system.

Specific to the PineCam now, the device includes a 2MP camera module which is the same one found in the PineTab 2/-V (the GalaxyCore GC02M2), it is connected via a MIPI CSI connector. Additionally, the camera and body can be separated from each other to be used as a USB-C UVP wired camera, so it may be used as a desktop webcam. The camera’s PCB also comes equipped with IR LEDs for low-light application use-cases. The mainboard is equipped with GPIO, a microphone, speaker, and USB-C power input located on the right-hand side of the device (when viewed from the front). The GPIO pins share Oz64’s layout and can be accessed by removing a small flap at the front of the PineCam. If you don't need to tinker with the GPIO, the flap can be reinstalled and screwed in place permanently. The PineCam comes with a convenient tripod, which can be folded or removed from the body of the device.

![PineCam prototype render](/blog/images/November_2024/pinecam_2.jpg)

The PineCam is currently in early prototyping stages, with the plastic body and final PCB having just arrived in recent weeks. However, the hardware is taking shape quickly and the printed circuit board assembly stage is currently on track for around the end of October. The first batch will be making its way to developers soon.

I can see the PineCam being used in countless scenarios, ranging from a truly private nanny or security camera, to a 3D print or drone camera. I’m sure you can think of your own, better use-case examples for the Pinecam. The PineStore hasn’t zeroed-in on a price point just yet, but the device will cost less than $30 upon release.

## Yuzuki Avaota-A1

{{< credits "Author: Caffeine" >}}

![Yuzuki Avaota-A1 board image](/blog/images/November_2024/Avaota.jpg)

The second device we will be announcing this update is a collaboration between PineStore and hardware manufacturer Yuzuki, the Avaota-A1. 

The device includes an Allwinner A527 SOC with 4 cores @ 1.8Ghz and 4 cores @ 1.42Ghz, a Mali-G57-MC1 GPU that supports the open source Panfrost driver, supports a 4K 60Hz display via HDMI as well as a 2.5K 60Hz display via DisplayPort, 802.11 B/G/N/AX WiFi (Wifi 6) and BlueTooth 5.4 connectivity. 

You can purchase it in a 4GB of memory and 32GB of storage configuration or a 2GB of memory and 16GB of storage configuration. 

You can find more information about this device on [Yuzuki's website](https://docs.avaota.fun/en-US/category/avaota-a1) for schematics and OS downloads and [on Pines store listing](https://pine64.com/product/yuzuki-avaota-a1-single-board-computer-4gb-32gb/). We plan on continuing this relationship with Yuzuki with another board in a couple of months, so stay tuned!

## PineNote

{{< credits "Author: Caffeine, Lukasz" >}}

# Attention to all users who have ordered/received a PineNote
The version of Debian-based Linux distribution shipped with the second PineNote batch contains some issues that prevent suspend-to-RAM from working correctly and make entering MaskROM mode using a magnet not possible. This was caused by the unfortunate timing, so the factory ended up installing version of the operating system image that contains these issues. The required fixes are already available in the shipped Linux distribution, but they need to be [installed manually](https://gist.github.com/m-weigand/efb1bef6097611d327533ab67b76903b) by the users.

## For general users wanting to purchase a PineNote
We would like to affirm that the PineNote Community Edition is still aimed at Linux developers with an extensive knowledge of embedded systems and/or experience with mobile Linux. Although the software has improved, we still want more testing done with this new batch to make sure we can start to aim this at general users. Now back to the blog post.

## PineNote News

The PineNote is one of the more ambitious projects undertaken by PINE64 and the PineStore since the original PinePhone. The main goal behind developing the PineNote was to create an open-source alternative to popular e-paper readers and note-taking devices, with nearly infinite software customization, free from advertisements and subscriptions. It runs standard Linux, adapted for a grayscale display, with preinstalled tools and extensions included to help make use of the device easier. From the outset, we understood that software would be key to building a true alternative for the FOSS community, and that achieving this goal would take time. This was a project we chose not to rush. 

The groundwork for the PineNote as well as the PineTab2 began with the Quartz64 single-board computer, followed by a three-year development period for the PineNote itself. The last thing we as a project wanted was to release a half-finished piece of hardware that might dissuade people from embracing an open e-paper reader and notepad.

Delaying the PineNote’s broader release has proven worthwhile. The factory image is based on Debian Trixie and includes the GNOME desktop by default. While the software is still best described as a "beta," it’s already quite impressive and will further improve with time as more people get their hands on the device. As things stand, all core functionality of the device has been implemented and enabled, with nothing missing, and each feature has been integrated thoughtfully. This includes everything from a custom grayscale GNOME theme to convenient quality-of-life features, like the ability to control both blue and yellow backlight under brightness settings, a widget that allow users to refresh the display on demand, and even a quick drop-down in the task-manager panel to adjust the drawing mode. I should also mention that there is an initial boot screen with documentation included in GNOME's Help app, which opens upon first boot. All this, running on mainline Linux. 

Maximilian and other contributors have done an incredible job, making the PineNote feel like a true FOSS counterpart to established commercial platforms.

![Image of PineNote help screen](/blog/images/November_2024/pinenote.jpg "PineNote help screen")

The PineNote production and flashing stages have finished and we are currently shipping to users (some are even receiving them as we speak!). The PineNote retains its initial price of $399 from the developer batch, with no major hardware changes; the only difference being a change from an active to a passive stylus, so it no longer requires charging, and yet the buttons on it remain functional (pretty cool right?).

The PineNote's potential is substantial. It shows that an e-paper device running Linux and open software can meet the needs of the enthusiast community—and, in some respects, even rival or surpass more mainstream devices that often lock users into proprietary ecosystems or subscription models. More importantly, it demonstrates that existing software can be adapted to work seamlessly on a grayscale e-paper display. We’re excited for tinkerers and developers to finally get their hands on the PineNote and the e-paper technology, which offers a fantastic experience for reading, note-taking, and the benefits of better battery life thanks to the e-ink display. We will be looking forward to your feedback and are keen to see how you use, change and improve the PineNote over the coming weeks, months and years. As always, we encourage you to contribute to the development process; you don’t need to write code (although, this is also obviously welcome) as testing, writing or translating documentation or even just offering feedback to developers means a lot to all engaged in the project. 

## PineTab-V

{{< credits "Author: Caffeine" >}}

Last month the PineTab-V part was completely missed on accident (whoops, sorry :<) and missed some important details for the new batch. 

The hardware changes made to the PineTab2 will be trickling down the the PineTab V as well in this new batch. After listening to community feedback we added an accelerometer along with a status LED for notifications and charging (similar to the PinePhone) to the Pintab2/PineTab-V. Some fixes were also made to resolve the slow charging issue while the device is turned off and a proper PineTab-V ID was added to the EEPROM.

This is a great revision with fixes and new hardware features, the device is currently in production and should hopefully be available in the next month.

## BarCamp Talk About Pine64 and Ox64 Handout

{{< credits "Author: Dsimic" >}}

Almost exactly a year ago, I delivered a talk about single-board computers and Pine64 at a local [BarCamp](https://en.wikipedia.org/wiki/BarCamp).  One of the intended goals was to produce a write-up for one of the Pine64 monthly community updates, which is obviously long overdue, but better late than never.

The primary goals of the talk were to raise the awareness of the local people about single-board computers in general, and more specifically about the Pine64 community and products.  Both areas are rather blurry to the proverbial Joe Average, so providing some kind of an introduction can only be helpful.  Alas, it turned out that the things were much more blurry than expected.

The intended talk audience consisted of, in general, software developers of all kinds, with various levels of knowledge and skill.  There were about 50 people attending the event; we'll need this number later, while drawing some of the conclusions.

A few weeks before the talk I reached out to TL Lim, asking if he could donate a few Ox64 128 Mbit boards, with the intent to hand them out right after the talk. To my delight, TL Lim responded with great news: a total of six Ox64 128 Mbit boards were on the way for my doorstep!  Thank you once again for that, TL, I really appreciate it!  It goes without saying that I was really happy to hear that, and I imagined happy people receiving the free Ox64 boards and enjoying them, while also contributing in different ways down the road.  Oh, was I wrong. :(

![Six Ox64 128 Mbit boards received from TL Lim](/blog/images/November_2024/barcamp.jpg)

*Six Ox64 128 Mbit boards received from TL Lim*

---

Unfortunately, the Ox64 boards didn't arrive before the talk, missing it by just a few days, so I was unable to hand them out exactly at the end of the talk, as planned originally. Instead, I intended to collect the contacts of the lucky winners and deliver the boards later. I thought that would make the talk audience a bit impatient, maybe even a bit sad, but as it turned out, I was wrong once again.

The talk itself, whose slides in English are available for [download](/blog/files/November_2024/barcamp-banjaluka-0x06-talk-single-board-computers-slides.pdf), unfortunately went without sparking particularly strong excitement among the audience, despite even being the opening talk, and despite the clearly mentioned handout of free Pine64 hardware.  I didn't want to make some kind of a lottery out of the handout, so I just asked that anyone who wanted a free Ox64 board had to describe briefly what they would use it for.  Thus, someone basically had to produce a couple of meaningful sentences, and a free Ox64 board would've been theirs.  Such an approach seemed fair to me, because the intent was to put the donated Ox64 boards into good use, but to my surprise and despair, when it was the time to hear the use-case proposals, all that was audible were the proverbial crickets.  Believe it or not, nobody proposed anything, while I expected at least a few people out of about 50 BarCamp attendees to be interested in the whole thing, and to come up with some interesting uses or projects.  A couple of people asked for some more details about the Ox64, but that was it.  It was satisfactory to at least see that the talk audience weren't greedy, so they didn't ask for something they wouldn't actually use. 

Obviously, the outcome made me rather disappointed, but as always, there's something to learn even from the things that turn out really bad.  Quite importantly, I was left with the Ox64 boards that I promised to hand out, but surprisingly, nobody wanted.  Thus, I had to "force feed" the boards to a few friends of mine, who actually didn't ask me to receive them.  Luckily, one of them eventually expressed some interest in using his free Ox64 board for some project in robotics, but sadly, his enthusiasm eventually proved not to be strong enough. To my unpleasant surprise, I've heard back nothing about the handed-out Ox64 boards in the last
year or so, which presumably means that the above-mentioned friends of mine haven't done much
with them, including the one who had some robotics project in mind.  Such an unpleasant and
truly unexpected outcome may make the whole talk endeavor look muck like a total waste of time,
effort and money, but I think we should actually try to learn something from this failure, which
is sometimes the best way to learn.

After thinking a lot about the whole thing, and after talking a bit to one of my friends, who received the last of the donated Ox64 boards a few months ago (for the record, I kept one out of six boards for myself), my conclusion is that much more "built-in" user-friendliness is required to make the Pine64 products understood better and, hopefully, more widely accepted.  To put it simply, we need to make blinking the proverbial LED very easy, which hopefully can we make some people interested to learn and do more.  Though, we shouldn't fool ourselves by expecting huge numbers of new people to suddenly become low-level software developers, because that's simply not realistic.  Very few people are interested in that, and out of those who show some interest, very
small percentage is actually willing to put some effort into it.  It's just hard and mentally not rewarding enough to most people who are already software developers of some kind.  Not to mention that most people just want to repeat some "cookie cutter" recipes found in various tutorials, which is absolutely fine, but such an approach unfortunately doesn't bring a lot of new value to the Pine64 community and its members.

I've already got some plans about how to make the Pine64 products more user-friendly, and only time (and some future community updates) will tell how much I'll actually do about that.

## PineDio

{{< credits "Author: Caffeine" >}}

![Image of PineDio USB Adapter](/blog/images/November_2024/pinedio.jpg)
Things have been moving quickly in the PineDio space as of late. Community manager Gamiee has been working with developers over at Meshtastic to get the PineDio USB adapter working with the Meshtastic firmware. Work has been completed to port the SX1262 to RadioLib which is a requirement for the firmware. 

At the moment, support for Meshtastic is seeming likely, but some issues could be attributed to hardware faults and it's possible a small hardware revision could be made sometime in the future. The issue has been found to be attributed to the TXCO, this issue stops the device from sending long packets via Meshtastic.

We would like to personally thank the people over at Meshtastic for the work they have done for the device so far. We have interest to continue collaborating with the Meshtastic project and we hope to work together to make new devices in the future. 

## Community content

### Monthly community updates

{{< credits "Author: Caffeine" >}}

As most of you know, the past two years has not been the best for community updates as nobody has been able to write consistently.
I am happy to announce that I will be stepping up to continue producing community updates monthly alongside our community members and developers.

Last months post was a bit of a doozy to write due to the 6 months of information needed to be inquired and written about, originally the update was slated for August, but unfortunately that never happened. For that I'd like to thank everybody's patience with our updates, things should be easier now that the last update is out of the way, so expect updates every month starting from now. 

Thanks again,
Camden.

## Want to contribute to the next community update?

Do you have a cool project that you're working on you'd like to be mentioned? Is there something you're interested in that you'd like to write about related to Pine64? If you're interested, please contact us!

- Camden/CarbonatedCaffeine: 
    - @carbonatedcaffeine (Discord)
    - @endernightlord:matrix.org (Matrix)
