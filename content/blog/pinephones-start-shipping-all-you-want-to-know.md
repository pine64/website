---
title: "PinePhones Start Shipping - All You Need To Know"
date: "2020-01-15"
authors: ["Lukasz Erecinski"]
categories:
  - "pinebook-pro"
  - "pinephone"
  - "pinetab"
  - "pinetime"
tags: 
  - "pinebook-pro"
  - "pinephone"
  - "pinetab"
  - "pinetime"
cover:
  image: "/blog/images/PinePhonesoldout.png"
images:
  - "/blog/images/PinePhonesoldout.png"
---

![](/blog/images/PinePhonesoldout.png)

Welcome to 2020. I expect this will be a productive year and one of exponential growth for our community. It was a busy beginning to the year and I expect that the pace will remain high with shipments of the Pinebook Pro and PinePhone Braveheart edition as well as FOSDEM announcements. Following this period there will be downtime due to the Chinese New Year. The past 12 months have been so intense that I am genuinely looking forward to this period of relative calm, which will allow everyone to catch their breath and review how things are going. I find that at times a forced downtime is one of the most productive things there can be.

Since I last wrote a lot of developments have taken place, so let's get to it. 

**TL;DR for this month:**

- Community Updates released on the 15th this year 
- We’re at FOSDEM - come chat with us; something special for PinePhone BH owners
- FOSDEM talk on [Linux phones](https://fosdem.org/2020/schedule/event/smartphones/) by Merlijn Wajer (Maemo Leste) and Bart Ribbers (pmOS)
- New HW announcements at FOSDEM; watch out for blog post on Jan 31st
- Pinebook Pro (ISO/ANSI) shipping; patience please - units still going out
- Pinebook Pro OS variety grows; \*BSD options incoming
- OG Pinebook RK3399 upgrade kit coming after Chinese New Year
- Pinebook Pro fun and games! 
- PinePhone Braveheart edition start shipping January 17th 
- Details on what you’ll find in the box; details on what software comes preloaded
- A lengthy list of improvements & changes from dev phones to Braveheart
- Important info regarding PinePhone shipping & tracking
- Little or no staff over CNY; use the community for help and support
- The PineTab early adopters edition production started ; where do we go from here?
- PineTime development update; actual timepiece OSs /UIs emerge

##### Housekeeping

I have made the decision to post community updates mid-month from now on - on the 15th of each month to be precise. If you think this is a bad idea or have some other objections please let me know in the comments. Personally, to me it just seems like a more natural period to post an update than at the beginning of each month. As usual, I’ll also post shorter and more casual community updates when need be (especially when shipments go out) in [the news section on the forums](https://forum.pine64.org/forumdisplay.php?fid=2) too.  

Onto the core topic of this month’s housekeeping; we’re at FOSDEM 2020 and we’ll have a stall on Sunday. We’ll also have all sorts of swag for you to grab at our stall - including stickers of course -  but if you happen to be rocking a Braveheart PinePhone at FOSDEM, then we’ll have something special for you. All you have to do to get the ‘special’ PinePhone accessory is show us your phone or the order confirmation (in the event yours arrives after the conference).  

We'll be showing off our not-yet-announced gear and the devices you already know about: the PineBook Pro, PinePhone, PineTime, and PineTab. If you’re on the fence about any of these devices, this will be your chance to get hands-on with them. I hope many of you will manage to make the trip and that I will get a chance to talk to you in person. Manjaro and UBports guys, along with many other developers from partner-projects, will be hanging out at our stall so make sure to talk to them too. Speaking of our friends from various projects, Merlijn B. W. Wajer from Maemo Leste and Bart Ribbers from postmarketOS will be giving a [talk about Linux phones](https://fosdem.org/2020/schedule/event/smartphones/), which I highly recommend you go and see. If you won’t be attending then a video from the talk will eventually be available on [FOSDEM’s website](https://video.fosdem.org/). 

![](/blog/images/ManjaroUBPorts-1.png)

**FOSDEM 2019: PINE64, Manjaro and UBports**

In the past 2 years I only had time to take a quick walk around the event, so on Saturday I intend to just walk around and, for once, actually see something at FOSDEM. You’re more than welcome to say hi when you see me and I am always keen on company. Last year I also found a great food place nearby if you’re interested to join me for lunch. Later that evening we’ll be heading out to [Tavernier](https://goo.gl/maps/DAKjM8cw1vZTe5SD8) with the rest of PINE64 folks, and we’d be happy to have you join us for beer (or soft-drinks if that's your thing). 

As we do each year, we’ll be making announcements regarding upcoming hardware at FOSDEM. We’ve got some really cool and exciting gear in the pipeline and I cannot wait to share it with you. You can expect a post regarding the announcements on January 31st. You can scroll down to the bottom of this page and sign up to this blog to get a notification once the announcement goes live. 

Last on the housekeeping list is the PINE64 cluster, which will host all our community services. The cluster has arrived at BBXNET’s datacenter and is now undergoing assembly. We’ll gradually be migrating all services to the cluster; I’ll make sure to keep you up-to-date on how things are coming along with it. I expect that the first things to be moved are the chats - I must admit that I am looking forward to a self-hosted Matrix instance. 

![](/blog/images/pine64cluster2.jpeg)

**Some assembly required ;)**

##### Pinebook Pro

The majority of ISO and ANSI Pinebook Pros pre-ordered in the past months have either been delivered or are en route to their new owners. Many more are to be shipped, so if you haven’t gotten your tracking number yet please do not worry. Pinebook Pros that will not make this shipping window - mostly units ordered in December - will be shipped out in February, after PinePhones go out to end-users. Shipping at this time of the year is difficult due to the upcoming Chinese New Year. There are various abnormal logistics issues that need to be overcome, including a shortage of staff. We’re doing our best to ship everything in a timely manner and hope for your understanding. You’ll have your Pinebook Pro soon one way or another. 

With that out of the way - we’re blown away by the sheer amount of positive feedback we’re getting regarding the ISO and ANSI versions. Thank you - it's equally important to hear words of encouragement as it is to get constructive criticism. I too have recently received an ANSI Pinebook Pro for testing from the last production run and I admit that the keyboard (despite ANSI not being my thing) turned out rather nicely. I also find that the fit-and-finish has been perfected at this point, and the unit feels very polished. The one thing that end-users will need to do however, is [update their keyboard and trackpad firmware](https://forum.pine64.org/showthread.php?tid=8407) - the factory failed to apply the necessary fixes in this production run. Moreover, ANSI users will have to change the keyboard layout  to ANSI in the default OS (en\_US) as the default OS layout is ISO (en\_UK). We’ll see to it that this is the last time end-users need to do the firmware update on their end. 

As promised, upgrade kits that convert the original Pinebook into a Pro-esque version are in the works, but we won’t be able to have them ready this month. We know that many OG Pinebook owners are waiting for this upgrade to drop and we’ll make sure that it is ready for production when factories resume operation after Chinese New Year. We apologize for the delay in delivering the pro upgrade kit, but there are still some aspects of this that need to be ironed out and we didn’t want to rush it.  Onto the subject of upcoming software.

https://www.youtube.com/watch?v=DqmFDCZcxM0&t=1s

**DorianDotSlash takes a look at 3 different OSs on the Pinebook Pro (40min)**

With so many Pinebook Pros now in the wild and in the hands of developers, software development has really picked up pace and we’ve seen images posted of numerous builds on forums, social media or elsewhere. Here is a list of OSs - that I am aware of - which are either already out or will be available for the Pinebook Pro in the next weeks and months:

- Arch Linux
- Ubuntu 20.04 w KDE
- Ubuntu MATE
- Gentoo
- Alpine Linux
- NetBSD

- OpenBSD
- Armbian
- RISC OS
- NixOS
- Debian Mainline
- Debian w MATE 
- Recalbox

- Ubuntu 18.04 w MATE
- Manjaro XFCE
- Manjaro KDE
- Q4OS
- Fedora 31
- Void Linux
- LAKKA

A kind request to developers - we’d appreciate if you could post your builds on the [PINE64 forum](https://forum.pine64.org/forumdisplay.php?fid=111) in the form of an announcements as well as add your builds to our wiki so it’s easy for end-users to find them. You can alternatively ping me or one of the moderators and we’ll do the above on your behalf. Thanks!

![NetBSD via Jared McNeil @jmcwhatever Twitter](/blog/images/NetBSD-PBP-1.jpeg)

NetBSD via Jared McNeil @jmcwhatever Twitter

![Nix OS via @fadenb (Twitter)](/blog/images/NixOS-PBP-1.jpeg)

Nix OS via @fadenb (Twitter)

![Gentoo via Jannik2099 (Chats)](/blog/images/gentoo-PBP.png)

Gentoo via Jannik2099 (Chats)

![RISC OS via @RISCOSbits (Twitter)](/blog/images/RISCOS-1.jpeg)

RISC OS via @RISCOSbits (Twitter)

Previous Next

I don’t have the time to cover every and each upcoming OS in detail, nor do I find it necessary—a simple internet search will tell you all you need to know about most of the Linux distributions—so instead I’ll focus on BSD. From the very start we said that the Pinebook Pro a _Linux and BSD laptop,_ but until now I haven’t had much of a chance to talk about the latter. In the [July 2019 update I acknowledged](https://www.pine64.org/2019/07/05/july-update-all-about-the-pinebook-pro/) that a segment of our community is made up of dedicated \*BSD users and I’ll let you all know when I hear of \*BSD developments; so I expect that this will come as a welcome surprise that development is now coming along. Indeed, this month we’ve had our first glimpse at NetBSD booting and running on the Pinebook Pro. It is my understanding that NetBSD is coming along nicely, and while it’s early days for the OS on the Pinebook Pro, this platform is known to the developers; the ROCKPro64 is already well supported by NetBSD. I’ve even seen screenshots of 1080p youtube content being watched in NetBSD on the Pinebook Pro and the WiFi adapter working (the latter being something \*BSD lacks drivers for).

![](/blog/images/PBPNetBSD-Youtube.jpeg)

**NetBSD Youtube playback on the Pinebook Pro via Matthew Green ([@mrgtwentythree)](https://twitter.com/mrgtwentythree)**

Yet another popular \*BSD is OpenBSD. Whilst I have not yet seen the OS running on the laptop, I am happy to report that [development has already started](https://twitter.com/knowmercymod/status/1216860532797591552) on an OpenBSD port. I have written to the developers, asking for a progress-report and an ETA, and hope to get a response shortly. When I do, I’ll surely edit it into this post or include it in the next community update. I too would really like to see OpenBSD on the Pinebook Pro this year as it's certainly one of the more recognizable (due to its long-running heritage) \*BSDs out there. 

As you can surely tell, we’ll soon have quite a selection of FOSS OSs to choose from: multiple Linux distros, \*BSDs as well as Chromium OS and Android. The current growth of the PINE64 community, combined with a very positive reception of the Pinebook Pro, is also an assurance that solid and prolonged support of the device is inbound. I suspect that partner-project developers feel the same way - for instance, the number of [Manjaro ARM 19.12 Pinebook Pro download](https://forum.manjaro.org/t/manjaro-arm-19-12-released/114406) link clicks is twice that of the next popular device. The download rates for all community builds for the Pinebook Pro are through the roof. 

Lastly, I am genuinely happy to see that people are having fun with their Pinebook Pro - and by fun, I specifically mean playing FOSS and retro games. Being an old school gamer myself, I am particularly excited to see Recalbox on the Pinebook Pro; I have tested the alpha build together with a handful of community members and it’s coming together really well. Just as any other OS for the Pinebook Pro, Recalbox can be easily booted from an SD card, so that it can be easily dual-booted with your full-desktop OS on the eMMC. A release is currently scheduled for mid-February, so be on the lookout for that if you enjoy retrogames. If a dedicated gaming distro isn’t your thing, then Astr0baby is [putting together a detailed list of games](https://astr0baby.wordpress.com/2020/01/11/pinebookpro-gaming-part-1/) that you can run on your Pinebook Pro complete with build instructions. As a side-note, and related to games, he also has an awesome guide on [virtualisation on the Pinebook Pro](https://astr0baby.wordpress.com/2020/01/12/pinebookpro-virtualization/), which I suggest you read if you’re interested in this subject matter. Getting back to the topic of games, we have set up our own Open Arena server, you’re welcome to [follow instructions I posted](https://forum.pine64.org/showthread.php?tid=8756&pid=56394) to join for some casual fragging this weekend :)

##### PinePhone

As I’ve mentioned in my [Casual late December community update](https://forum.pine64.org/showthread.php?tid=8645), Braveheart shipments have been pushed back a couple of days so that Pinebook Pro ANSI units could clear from the Hong Kong warehouse. Not that it matters, but in the name of transparency, I believe that the shipping team decided to dispatch Pinebook Pros first simply because they take up more space in the warehouse than the phone pallets. The reason I am including this information in the first place is to put at rest question regarding production status (more on this later). As things stand, we’re now ready and I am happy to confirm that PinePhones will begin shipping in two days time - on **January 17th 2020**. The dispatch process will take a couple of days, however, so **your unit may ship anytime between the 17th and 25th**. At any rate, you’ll have your PinePhone soon.

![](/blog/images/ppproduction-1.jpeg)

**So many PinePhones!**

Let’s talk shipping. As I already mentioned in the past, the PinePhone will ship using [Asendia](https://www.asendia.com/). They offer a balance of solid shipping times (approx. 10-14 days to Northern Hemisphere + Australia and New Zealand), security and shipping cost. Unlike other carriers they also do not file import tax on your behalf, so it will be up to your customs to determine whether the PinePhone needs taxed or not. Without dwelling too much on this subject matter, I can confidently write that there are greater chances you won’t be asked to pay anything extra than with other carriers capable of transporting goods with Lithium Ion batteries. 

One key downside of shipping using Asendia is parcel tracking. Simply put - from my experience and that of developers (sample of ~100) - the tracking isn’t particularly good. Having left Hong Kong, my parcel’s position wasn’t updated until it reached the destination airport and was logged for pickup by the local courier company. From this point, however, I was able to track the parcel in my local delivery service’s system and [17Track](https://www.17track.net/en). This has, by and large, also been the experience of other people. So what does that mean? It means a few things: for starters, don’t worry if you won’t receive shipping updates for a prolonged period of time - this is to be expected. Therefore it also means that you shouldn’t email support, sales or info - it won’t make the shipping any faster and will just make the response times - to people to people we can actually assist - considerably longer. 

Speaking of support, PinePhones ship out just days before the Chinese New Year starts. This means that there will be very few, if any, staff to answer your questions during this holiday. Therefore, more than ever, we will rely on our community members and partner project developers for support during this period. So if you experience problems with your Braveheart PinePhone, regardless of if it’s a software or hardware query, then before you decide to email support please make sure to join the [chats](https://www.pine64.org/web-irc/) or post your question on [PINE64 forums](https://forum.pine64.org/forumdisplay.php?fid=120) and see if there is someone who can offer help. Unless your unit is DOA or damaged, you stand a much better chance of getting answers to your questions from community members in the coming weeks.  

![](/blog/images/communitychats.jpeg)

**Community forums and chat options available from the drop-down menu on this site**

With all the formalities out of the way, let me talk a bit about the PinePhone Braveheart itself. Inside the box you’ll find the PinePhone, a high quality USB-C charging cable and an introductory leaflet in letter form (written by yours truly with the [help of the community](https://forum.pine64.org/showthread.php?tid=8591)). We assume that most, if not all, of you already have a 5V 15W PD charger, and we have no intention of adding more rubbish to the landfill than necessary. The PinePhone will charge just fine at a lower wattage but the charging process will obviously take much longer. If you don’t have a 15W rated PD charger yet, then use whatever charger you have  in the meantime, and I suggest you wait for end-user reports regarding what chargers work best for the PinePhone. Lastly, the packaging which the PinePhone arrives in (as is the case for all our products) is made entirely out of recycled materials. We strongly encourage you to recycle the packaging according to your local standards if you do not intend to keep the box. 

![](/blog/images/PPboxed.jpeg)

**PinePhone Packaging Box**

The PinePhone itself arrives with a polymer (a nice way of saying plastic) screen protector applied at the factory. I’d suggest you keep it on your phone, but I understand that there are some who distinctly dislike plastic screen protectors - if you’re one of those people, then you can peel it off without worrying, the PinePhone features hardened glass. In the future we may partner with some company to deliver a glass screen protector for the PinePhone - stay tuned for more information in the coming months. 

There are a great many aspects of the phone that have been changed, improved upon and polished since the dev phones, which you’ve probably seen have shipped. This includes engineering things, such as tweaks to the antenna layout or PCB improvements and known errata corrections. To most people, however, it's the aesthetical changes that will stand out the most. There are a few things which you may immediately identify as different when compared to a dev phone - especially some of the earlier dev units. The LCD and digitizer are sealed, so there is virtually no gap between the glass and the screen. The LCD used is also pitch black when the device is turned off as opposed to grey-ish or silver. The Lithium battery has now been branded and the back of it facing the PCB contains all necessary warnings and regulatory messages. 

![](/blog/images/pinephoneBHopen.jpeg)

**Braveheart PinePhone with back cover taken off (modem blurred)**

Perhaps most importantly, however, the back of the phone has been significantly improved upon. Both the plastic molding and the applied coating have been considerably refined. I haven’t held a Braveheart phone in hand myself, so I cannot provide a first-hand account of how the coating turned out; that said, those on the team who held one of these PinePhones seem very pleased with the end-result. Lastly, similarly to how we chose to only brand a single key on the Pinebook Pro, we chose to sneak in a small PINE64 logo between the camera and the flash LED. The logo is placed behind glass, so won’t be scratched or eroded from regular wear and tear, and is pretty small in size. This was my idea, and I hope that it is unintrusive enough to satisfy those who hate branding yet prominent enough to make this an unmistakable PINE64 product. It also opens the entire back of the case to partner-project branding; something I expect we'll see in the future as we ship OS-specific PinePhone production-runs ( information on this topic [here](https://www.pine64.org/2019/08/19/its-time-to-start-giving-back/)). Let me know what you think about the little PINE64 logo in the comments.

![](/blog/images/pine64logopp.jpeg)

**Placement of the PINE64 logo** 

As for software, the phone arrives preloaded with a factory test image rather than an end-user operating system. This preloaded factory test suite is running on Linux - postmarketOS to be precise - which allows you to test various features of the phone and run an automated test. The automated test runs through all key sensors, inputs, outputs and the modem (if you have a SIM card inserted - otherwise it will return a modem failure error). The manual tests include the touch panel, modem, speakers, vibrating motor, LED notification light and more. It also includes an option that allows the factory to write the image to eMMC (which has already been done, since the image is running from eMMC). 

![](/blog/images/FactoryOS.jpeg)

**Factory OS - postmarketOS with custom factory UI**

At this point I assume that everyone getting a Braveheart PinePhone understand that it's up to them to find the operating system build they are interested in, flash it and take part in the community discussion and ongoing development. Most builds are available on the [PinePhone Wiki](/documentation/PinePhone/) - which you can and should contribute to (use your PINE64 forum credentials to log in). Some OS builds have to be sought out however; for example, this is the case for Manjaro and Nemo mobile. These builds will, in time, be added to the wiki too, but for the time being the Wiki knowledge base is just getting built up. You will likely want to run the OS you’re interested in from the SD card for now. New builds show up every couple of days - I am currently waiting for Maemo Leste and Nemo mobile for demo purposes - which requires you to reflash the storage medium. It just isn’t very convenient to test new builds from eMMC. 

Finally I wish to briefly discuss future PinePhone production-runs. We will actively monitor and  evaluate software development progress over the Chinese New Year period. This period is quite vital to furthering progress as partner-project developers will shortly have an entire dedicated audience of contributors and testers to work with. Admittedly we expect a lot of progress to be made in the coming two months thanks to community contributions. We have previously stated that larger scale production of PinePhones is scheduled for March 2020, and this is still what we’re aiming for. If production commences in March then I’d expect the next production-run on PinePhones to reach their new owners in late April. But if no Linux phone OS reaches sufficient maturity by that point in time we may decide to hold back a month or two before starting the manufacturing process. After all, we  want it to be the best Linux on mobile experience possible, so as not to discourage people from the idea of Linux as a viable alternative to Android and iOS. Production this year may start with entering into a cooperation with a partner-project that will be able to deliver a daily-driver OS. I have previously described the nature of such a relationship in a [dedicated blog post](https://www.pine64.org/2019/08/19/its-time-to-start-giving-back/), which I encourage you to read. Presently there are a number of candidate OS for this undertaking, and we’ll be talking to them in the coming weeks to determine how much progress can be achieved. I’ll make sure to update you on this topic as development progresses. 

https://www.youtube.com/watch?v=11eObhH8MKA&t=1s

**A quick look at 4 different PinePhone OS**

##### PineTab

With the Pinebook Pros and PinePhones now manufactured and shipping, our attention has turned to the PineTab. Early adopter PineTabs have entered production earlier this month and will likely be delivered to us prior to the Chinese New Year. This does not, however, mean that we feel ready to open pre-orders just yet. We need to test and review the units before making them available for order and need to determine the right OS to pair it with for shipping. As things stand, there are only two viable OS for the PineTab at this point in time - Arch Linux and postmarketOS (XFCE / Plasma mobile). There are other OSs too, but those are PinePhone ports and more of an afterthought rather than a dedicated build. All OS options have their strengths and drawbacks, but I feel like there isn’t a single one that stands out as particularly complete. 

![](/blog/images/PineTabArch.jpg)

**PineTab dev unit running Arch Linux via [@RealDanct12](https://twitter.com/RealDanct12)**

This may very well be a chicken-and-egg situation. The lack of PineTabs in enthusiasts’ hands, in conjunction with developers’ focus on the PinePhone and shelving the project until phones and laptops ship, may be the root cause for no viable software. I am happy to entertain this possibility and in fact find this quite likely. So then, my question to you is: would you rather have us ship the PineTabs to enthusiasts with a clear notice that basically no usable software exists for the platform or wait and see if we manage to build up some support? 

There is nothing else I have to to report regarding the PineTab at this point in time which I haven’t reported before in my [December community update post](https://www.pine64.org/2019/12/05/december-update-thank-you-for-2019/), so if you haven’t read it yet, I suggest you do. We really hope to hear from you regarding what route you think we should pursue with the PineTab. At this point your arguments may be the key deciding factor whether we decide to proceed with the PineTab in the next 2 months or if we decide to hold off, explore our software options with developers further, and release it with a more feature-complete OS build later this year. I am looking forward to hearing from you.

##### PineTime

The PineTime has quickly built up a dedicated development community. from the project’s inception, I’ve expressed how impressed I am by the work done on the device. Each month new FOSS OSs and front-ends become available for the PineTime, and I am now looking forward to showing them off at our FOSDEM stall. Last month I dedicated a portion of the community update to explaining how we interact with the PineTime development community and featured some of the early work. A lot of the software and the development process seen insofar can be vaguely classified as either experimentation and proof-of-theory development (as well as pure fun). It's great to see that developers enjoy working with this device, but at the end of the day the majority of end-users are keen to see UIs that resemble and function as smart timepieces. After all this device is what we all hope to be wearing on our wrists at one point in the future. 

To this end, this month I want to highlight two front-ends that are really starting to take shape as actual timepieces. From what I’ve gathered, both of the two OSs offer similar functionality, synchronizing and keeping time as well as displaying connectivity status. But presently more advanced smartwatch-type functionality, such as pushing phone notifications, is yet to be implemented. My knowledge about PineTime back-ends is, to say the least, highly limited - so I reached out to the developers of the two OSs directly for details. Below are their explanations of what code their PineTimes run and what the front-end can do in the current state.

![](/blog/images/PT1.jpg)

**PineTime Running Koen's Front-End (via Koen in chats)**

The first of the two UIs has been developed by Koen Zandberg:  

_"The application as of now can be used to make the PineTime into a simple timepiece.  Bluetooth LE with a GATT current time service client is used for time synchronization with a_\[n Android\] _Phone companion app. Energy is conserved by only turning the screen on when the button is pressed, it automatically turns off after a few seconds. The display shows the current time and date, the bluetooth connection status and the battery status._

 _The system is based on RIOT as embedded operating system, providing the threading infrastructure, drivers and power management. Nimble is used to provide an open source Bluetooth LE stack. Finally LittlevGL provides the high level graphics on the display supporting partial updates for fast and efficient updates." ~_ [Koen Zandberg (@bergzand)](https://github.com/bergzand)

https://www.youtube.com/watch?v=\_ZrsH783ZLI&feature=youtu.be

**PineTime syncing with Android phone [originally posted by JF](https://twitter.com/codingfield/status/1210598653729091584)**

The second front-end is developed by JF (whose work I already featured in previous updates): 

_"The firmware provides drivers for the display, battery measurement and touch panel. It also supports BLE connection and implements a CTS client that retrieves the current date and time from the device it is connected to._

_The application built on this firmware provides some simple functionalities : it displays the date and time, the battery level and the status of the BLE connection. The display can be switched on and off using the button and the touch screen. As a demo of the touch panel, a colorful square is drawn when it detects a touch event._

_The project is written in C and C++ and is mostly built around the NRF52 SDK and FreeRTOS." ~_ [@codingfield](https://twitter.com/codingfield) / [jf002](https://github.com/JF002/Pinetime)

My thanks go out to both JF and Koen for taking the time to answer my questions. I am excited to see the PineTime software progress over the course of this year and beyond. I appreciate that much work still needs to be done to make this a viable smartwatch - especially since at one point it will have to pair to the PinePhone. This means that PineTime developers will eventually have to cooperate with and receive help from mobile OS developers in getting the PineTime syncing with their Linux systems. I hope that once Braveheart PinePhones ship someone from our community, or partner-project communities, will take it upon themselves to start developing a companion app for the PineTime. Regardless of what the future holds, the PineTime is already a success-story in my book. 

That's all for this month’s update. Remember to sign up for the blog (scroll to the bottom of the page to submit your email address) to receive a notification once we publish our FOSDEM announcements. 

**Many thanks to Dalton (UBports) for proofreading this blog entry.**
