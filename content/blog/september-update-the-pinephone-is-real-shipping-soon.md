---
title: "September Update: The PinePhone is real & shipping soon"
date: "2019-09-05"
authors: ["Lukasz Erecinski"]
categories:
  - "news"
  - "pinebook-pro"
  - "pinephone"
tags: 
  - "pinebook-pro"
  - "pinephone"
  - "release"
cover:
  image: "/blog/images/acutal-pinephone.jpg"
images:
  - "/blog/images/acutal-pinephone.jpg"
---

![](/blog/images/acutal-pinephone.jpg)

**Picture of a PinePhone prototype running Plasma Mobile** 

Let’s start with a quick recap of last month’s events: the Pinebook Pro went into production, software development on the PineTab started, we announced the SOEdge AI module and introduced our initiative for giving back to PinePhone Linux developers during the community meetup in London. This, however, is hardly everything. Let me segue into the core topic of this month’s update, namely the PinePhone. Behind the scenes prototype PinePhone PCBs and chassis have been produced and undergone extensive testing. With the testing now completed, we made the decision to manufacture a small batch of PinePhones for developers. We have also scheduled two larger production-runs, which will be open to early adopters later this year.

So, without further ado, I am hereby happy to announce that the first PinePhones have now entered production and will start shipping to developers this month. As you probably already gathered from this brief introduction there is a lot to cover, so let's get started. 

#### Bullet Points

- Donating to PinePhone devs ; contributing to solving digital divide 
- Pinebook Pro shipping schedule ; engineering notice ; privacy switches & ‘PINE64’ logo key 
- PinePhone prototypes ship to developers this month ; 8 months since announcement, years in planning
- PinePhone shipping timeline for 2019 & beyond ; “Brave Heart” editions ; 2020 large-scale production
- PinePhone hardware overview ; PinePhone vs dev kit; new LCD+ TP ; aluminium alloy infusion ; quick charge
- PinePhone software status & progress report 

#### Housekeeping

We recently announced that we'll be donating $10 from each PinePhone sold to Linux-on-Phone projects working with us. If you haven’t done so yet, I strongly suggest you read the [original announcement](https://www.pine64.org/2019/08/19/its-time-to-start-giving-back/). In short, we intend to have OS-specific campaigns - complete production-runs with a particular OS pre-installed as well as stylised phones - but also a permanent system allowing users to select directly which project we should donate to. We wish for the donation process to be both transparent and, in the spirit of our community, also completely open. This means having the donations software hosted on GitHub/ GitLab for anyone to view, review and contribute to. If you’re interested in helping out in making this happen then please reach out to [fire219](https://forum.pine64.org/member.php?action=profile&uid=606) on the forum or in the chats. 

During the meetup we also announced that we’ll do our share to contribute to closing the digital divide. Let me give you a short run-down of how it will work: money from the sales of soft cases for the PinePhone will be funneled into production of original 11.6” Pinebooks for those in need of a computer. I’ll be speaking to people in the community as well as notable persons in the broader Linux universe in the coming months to set up a panel that will put forth proposals, discuss them and subsequently vote on where the Pinebooks should be donated to. This initiative will start with the first public production-run of PinePhones; more information will follow once I have members of the panel lined up. I’d like to note this is a community initiative and therefore also completely open for all to participate in by sending in proposals, interacting with the panel as well as having insight into the panel's workings.

![](/blog/images/Mr-Kracy.jpg)

**Community meetup - sunny day in London 18 August, 2019**

#### Pinebook Pro: Shipping dates, ‘PINE64’ logo key and software updates 

Before proceeding to discuss the PinePhone there are some Pinebook Pro news, which I think ought to be covered first. Let’s start with the shipping dates; the first community pre-orders will start shipping mid-September, followed by the public pre-orders in October. Please note that these dates are subject to change - if something changes you’ll be notified ASAP. A wide range of things can affect production at this early stage - as an example, we recently discovered that the Pinebook Pro does not power on from mains with the battery disconnected from the mainboard. Whilst this will not affect the great majority of users, a suitable workaround still had to be determined and implemented to mitigate the issue. Working out such things takes time and results in shipping dates slipping - thankfully, in the case described above, everything got sorted in a matter of a couple of days. A bypass cable, disconnected by default, has been added to the mainboard. In the event the laptop is required to run on mains power with the battery disconnected the cable needs to be joined; [please read the engineering notice](https://pdfhost.io/v/eCtjbXwCJ_ECN_20190828PRP01_1pdf.pdf)**.** 

Onto the ‘PINE64’ logo key and its functionality. Before the community pre-orders began in July we announced that the Pinebook Pro will include privacy switches. In the same post I discussed the feedback we received regarding our decision not to brand the laptop, which prompted us to include a subtle touch in the form of a ‘PINE64’ logo key on the keyboard. Since then there was a lot of back-and-forth discussion regarding the functionality of the key. Eventually we put 2 and 2 together and reached a logical decision - the ‘PINE64’ logo key now functions as a regular Super key unless pressed down with F10, F11 and F12 key for 3 seconds. Pressing the combinations above will disable/ re-enable the laptop’s microphones, the WiFi/BT module and the webcam. We feel that this is a natural fit for the ‘PINE64’ logo key and its function, and we hope you feel the same way. Since we’re already talking about changes to hardware, and I have nowhere else to fit this piece of information, I am happy to let you know that the Pinebook Pro’s webcam has been updated to a 1080p cam; I’m sure that some of you will appreciate this.  

Lastly, I want to discuss software related things. In the recent weeks ayufan has pushed a number of OS images for the RockPro64, the Rock64 and also the Pinebook Pro, which includes a very [long list of improvements](https://github.com/ayufan-rock64/linux-build/releases) that result in great functionality and performance. A choice of Ubuntu with MATE desktop or LXDE as well as a great-performing build of Chromium OS will be available for you to try on day one. The default Debian with MATE desktop, which ships with the Pinebook Pro has also received a lot of development hours since the OS image was shipped to the factory. The list of improvements is quite lengthy so if you're interested make sure to read the [update-log here](https://forum.pine64.org/showthread.php?tid=7830). The one truly vital improvement made is a patched U-Boot (pending feedback from early adopters), which alters the Pinebook Pro’s default boot sequence. This means that now the Pinebook Pro will boot OS images on the SD card and USB 2.0 / USB 3.0 ports prior to the onboard eMMC. It’s a simple way to try out other OS’, such as those offered by ayufan, without committing to wiping your current installation. To get this and the numerous other features please make sure to update your system using the included utility on first boot (please reference the update-log).

![](/blog/images/PBP-Keyboard.jpeg)

**The 'PINE64' logo key and privacy F-row keys**

#### The PinePhone now exists

It has only been 8 months since we [announced the PinePhone at FOSDEM 2019](https://forum.pine64.org/showthread.php?tid=7093), but the idea of creating a FOSS Linux phone has been with us for years. Indeed the phone topic was first discussed in 2017 over a pint of beer at a pub in Brussels during FOSDEM of that year. I remember TL brought with him a tablet chassis and talked about how we could have an A64-based device ecosystem: a SBC, a SODIMM module, a laptop, a tablet and a phone, all of which would run mainline Linux on a common platform. Soon after, however, the creation of a phone was deemed too complex and expensive. Looking back I think we felt it would be an undertaking that would deplete all of our energy and resources, which at the time were being pumped into Rock64 and RockPro64 development. The phone discussion resumed last year once all SBCs that were in the pipeline hit the market. Having done some research on mobile Linux operating systems, on October 2018 I joined UBPorts and started talks with the project developers. It wasn’t long after that I wrote to TL: _“These guys seems really friendly and (...) I think they are up for it”_. We have since established contact and welcomed into the fold all major Linux-on-phone projects, whom are now collectively working towards making the PinePhone the best device it can be. Only 11 months after committing to creating a mobile phone, the first PinePhones are now being assembled at the factory. I dare say, this is no small feat for a reasonably small and community driven project.   

Developer pre-orders are now live and it won’t be long before core enthusiasts get their hands on the PinePhone too. This is just the start of our journey with the PinePhone, but with both software and hardware progressing at Warp 10 speed I am confident that in early 2020 everyone interested in a Linux phone will be able to purchase one.

![](/blog/images/PP_back_bat.jpg)

**PinePhone with battery inserted**

![](/blog/images/PP_back.jpg)

**PinePhone without battery + back cover off**

#### Developer pre-orders September 2019

These PinePhones are prototypes and are aimed solely at developers. More specifically, we intend for these early units to find their way into the hands of developers with extensive Linux experience and an interest in Linux-on-phone. Sorry app developers, tinkerers and end-users, you will have to wait a little longer. Due to the very limited number of these prototype phones available at this time, the pre-orders will be made on a bespoke basis. In this way we can ensure that each and single unit goes out to someone who can contribute to the project at its current stage and help us deliver the software for the first public production-runs. 

Regarding the actual hardware; the phones are nearly identical to units that will ship later this year and in early 2020. I write ‘nearly identical since the antenna calibration hasn’t been completed as of yet and there may be additional tweaks to the PCB design based on the feedback we’ll receive in the coming weeks. As for the software, this edition of the PinePhone will ship with a custom OS built for debugging hardware on the PinePhone. It is meant as a reference point which can be used during development. All relevant information pertaining to the build will, of course, also be available for those interested. The greatest resource of all, the developers themselves, are readily available in the chats and we expect to see the owners of these early PinePhones joining them in the near future. 

![](/blog/images/PP_preorders.png)

**Main page dev pre-order widget at the time of writing**

#### “Brave Heart” editions in October 2019 and beyond

We are planning on having two early adopter production-runs this year. We chose to call these two batches the “Brave Heart” editions, since no complete OS images will be available at the time of shipping. So, in other words, these production-runs are only for those of you whom are brave enough to buy a device without a fully functional OS. Rest assured that we will make sure information about the state of software is front-and-center at the time of shipping. These two production runs will be geared towards the bleeding edge enthusiasts who also wish to contribute to development by debugging, testing builds and offering feedback. These phones will ship without an OS preinstalled - we expect that people who will pick up a Brave Heart edition will want to hold off from flashing any OS to the eMMC in favor of trying out weekly or daily builds on SD cards. A pre-flashed OS would be significantly outdated by the time it would end up in users hands anyways. The turn-over time for builds is presently quite fast and I expect this pace will keep up for quite some time, especially with detailed bug reports from early adopters pouring in. 

We are planning on starting the production line on mid-October, just over a month from now. Pre-orders for the Brave Heart edition will start around the same time and will be open to all. This batch of PinePhones is scheduled to be delivered in November. The second batch will be built the following month, on 15 November, and will be delivered to end-users some time before Christmas. Please keep in mind that these dates are tentative and we may instead opt to pool together the two production-runs into a larger batch in early-to-mid October. This schedule depends on the feedback we receive from developers and their experience with pre-production units. A commercial-scale production of PinePhones has currently been scheduled for March 2020. By this point in time we expect to have - at the very least - one end-user ready OS image with all core functionality. 

#### PinePhone Hardware

I’ll divide this section into a discussion on the PCB and the body of the phone. I’ll also touch on the notable differences between the development kits and the PinePhone. Let me get the differences between the phone and the dev kit out of the way first. The things that I’ll list may seem obvious to many of you, but I will go over them anyways, since I’ve recently been made aware they aren’t immediately apparent to everyone interested in the project. As I already mentioned, the form factor of the kit and phone PCBs is different as the design had to be shrunk down to something that would fit inside a phone chassis. The dev kit is also modular, with the individual parts being detachable from the mainboard, while the phone has most of the key components permanently soldered onto the PCB. While a modular phone is conceptually very cool, it is rather impractical and significantly increases the manufacturing complexity, and thus also the cost of the device. Lastly there is the question of physical space that components take up; phone chassis are rather cramped, so having a modular design effectively means having a thick phone. For the same reason, the full-sized Ethernet and HDMI ports found on the dev kits didn’t find their way into the actual handset either. I’d like to note, however, that both video-out and Ethernet functionality is achievable via the USB-C port on the phone. The last and most important difference is the touchscreen used on the actual phone. The LCD display is slightly larger at 6” and the touch panel includes a drastically better high-precision driver.

![](/blog/images/pinephonekit.jpg)

**Left PinePhone  // Right development kit (v1.2)**

We have also made some significant improvements to the phone’s chassis since the original design was publicly unveiled. The inner section of the plastic body has since been infused with an aluminum alloy and tooled to be compatible with an existing 3000mAh big-brand battery. Having the body infused with an aluminum alloy serves two purposes: it significantly strengthens the core structure of the phone and improves component heat dissipation. With metal now being an integral part of the assembly, the PinePhone also feels considerably more sturdy in the hand. The entire inner construction of the phone, and most of the components, are held in place using standard Phillips-head screws. Very little adhesive is used on components that are not soldered onto the main PCB such as the cameras, so removing these parts is also pretty straightforward. The detachable back panel - which covers the privacy switches, pogo pins and the removable battery - is made of a durable soft-touch plastic. Subjectively speaking, it's nice to the touch and attract fewer greasy fingerprints than glass or metal. Taking the phone apart is achievable by anyone and should take no longer than 5 minutes from start to finish. This time estimate excludes the LCD+touch panel, which I suggest end-users do not attempt to disassemble; it is possible, but requires some finesse.

![](/blog/images/PP_case_infusion.jpg)

**Case with aluminum alloy infusion (prototype)**

![](/blog/images/mainboarddb.jpeg)

**PinePhone mainboard + daughterboard (prototype)**

Onto the last point on my list, namely the PCBs used in the phone. The mainboard is an 8-layer Blind Via PCB, and it is the most complex PINE64 design to date. There is also a smaller daughterboard, which is connected to the mainboard using a ribbon cable, that houses the microphone and USB-C port. The USB-C port on the PinePhone does not only support alternate mode video out and data, but also 3A 5V quick charge (follows USB PD spec) when using a compatible charger. The Allwinner A64 SOC, powering the PinePhone, and Quectel EG25-G modem are placed on opposite sides of the mainboard, with the A64 facing inwards. The A64 makes contact with metal on the LCD back-plate via a thermal pad. This solution provides ample heat dissipation, even under load. All components on the mainboard are covered by a removable metal shroud (not in picture above), which is similar to those found on the Pinebook and Pinebook Pro. The mainboard is covered and held in place using the internal structure of the phone’s body, but leaves the following components and ports exposed: I2C pogo pins, privacy switches, SIM card as well as micro SD card sockets. Access to all the above is fast and easy, and only requires you to pull off the back cover of the PinePhone, which pops easily using a fingernail or the edge of a credit card.

Compared to modern big-brand smartphones the PinePhone is remarkably simple, and we trust this is a good thing. Repairing and maintaining the phone is straightforward and achievable by anyone with a screwdriver and patience. Batteries for the phone can be had for under $10 online throughout the world and we’ll be stocking replacement parts as soon as larger-scale production starts next year. Before we move onto software, let me say that this isn’t the end of updates to PinePhone hardware; as it has always been the case with PINE64, we’re continually looking to improve currently listed specs. More surprises are in the store for this device so make sure to check the PinePhone spec-sheet closer to public-release date.

#### PinePhone Software 

I am happy to report that a tremendous amount of progress has been made on the PinePhone software in the past month. Most notably perhaps we’ve got our first glimpse at the Ubuntu Touch build on the PinePhone, which I know many of you have been looking forward to seeing. As I’ve mentioned in the past - and on more than one occasion - I am not the most competent person to assess software. That said, even I can tell when something is running well; and yes, the Ubuntu Touch build that I’ve gotten to experiment with runs really quite smoothly. The animations are fluid, applications now launch and the overall experience is massively improved over my past experiences. Moreover, mobile and wireless connectivity are now also functional. Below is a clip from Marius (UBPorts) showing the UI running snappily as he toggles between the different GUI elements. That isn’t to say that the build is production ready, but it's coming along very quickly and will likely be one of the launch OSs. I will wait for another month or so, and give Marius and Nikita a bit more time with the build before I showcase it on the PINE64 youtube channel. It will, however, be the first thing I load up on my pre-production PinePhone when I get it next month.

https://vimeo.com/357951065

**Video by [Marius Gripsgard](https://twitter.com/Mariogrip/status/1169049411231637505) from UBPorts**

Similarly, the PostmarketOS Plasma Mobile build also works quite well. Animations are smooth, applications start as they should and even little things such as the brightness slider are functional. Sadly the build currently suffers from an issue allowing it to only run properly on the first boot - on subsequent reboots the UI errors out and only displays a black screen. I am told this is a problem which is not isolated to the PinePhone dev kit, but affect all supported devices. Apart from this error, there are also a few lesser issues, most of which are related to the Lima GPU driver. This build too has undergone very significant improvements over the course of last two months. Until very recently, many of the UI elements were incorrectly rendered as transparent and applications did not launch. If you are interested in seeing Plasma run on the PinePhone then please make sure to check out [Martijn Braam’s youtube channel](https://www.youtube.com/watch?v=8phE4wanhfM), where he demos WIP builds.

https://www.youtube.com/watch?v=8V711Iordo4

**PostmarketOS running Plasma Mobile by Martijn Braam**

I also had a chance to get my first hands-on experience with SailfishOS this month, and I was very positively surprised by how well it runs. My surprise stems from the fact that the UI has always appeared to me to be quite intricate and complex, which had me believe that it was more resource hungry than other OSs. It also uses experimental Lima drivers as opposed to the (currently faster) mali blob. Thankfully when swiping between tabs, opening applications and scrolling through the settings menu I was greeted by smooth OS functions. Adam and Dylan have posted videos showing the performance of the OS that I am including in this post for you to check out. It is my understanding that most of the functionality already available in other OS builds is also present in SailfishOS. I now have high hopes for SailfishOS on our platform, and I hope that the large and thriving community behind this OS will appreciate the unique feature set that the PinePhone brings to the table. 

https://vimeo.com/357952216https://vimeo.com/357952026

**Videos by Adam Pigg and Dylan Van Assche from SailfishOS**

I did not try out LuneOS this month, in part because I’ve already done so recently and know that it runs very well on our hardware. I spoke to Tofe, the LuneOS developer behind the builds, and he told me that a lot of progress has been made recently. LuneOS currently expects to have an early release available within a month’s time. Functionality of this early release will have to be confirmed on the developer PinePhone, but LuneOS ran well on the dev kit hardware and so any negative performance changes are unlikely. I also reached out to Wizzup from Maemo Leste asking for a development progress report. Maemo Leste has been working on their phone and cellular support in recent months. Below is a screenshot showing off their cellular status applet (showing signal strength and access technology) and operator name applet (showing the operator name - KPN).  Setting up a cellular data connection, which is automatically provisioned is now also possible. Sending and receiving SMSes also works using Empathy and Telepathy-ring - the attached screenshot shows the PinePhone-side of the affairs with Maemo Leste receiving SMS messages. Maemo Leste also have a (long) update post of the various software improvements I suggest you read [here](https://maemo-leste.github.io/maemo-leste-ninth-update-march-till-august-2019.html).

![](/blog/images/MeamoLeste1.png)](/blog/images/es/MaemoLeste2.png)

**Screenshots by Merlijn (Wizzup) Wajer. Left UI with visible networking // Right SMS on PinePhone development kit** 

I get the sense that everything is coming together in a rather fast and orderly fashion. Modem functionality is also coming along very well. Developers are planning on debugging remaining modem-related issues - some of which prevent phone calls from working properly - this month and they are positive that everything will be working soon. Phone calls aside, both GPS and LTE data already work, and SMS messages have already been sent and received from the development kit on most OSs. I have tested WiFi myself on more than one build and it functions properly, as do a number of sensors on the development kit, including the gyro and ambient light sensor. For those keen to learn of all the details, you can check the [PMOS bug tracker](https://gitlab.com/postmarketOS/postmarketos.org/issues/110) that details what has already been implemented and confirmed as working. I am not certain if this bug tracker is representative of the majority of PinePhone OS images, it may very well not be, but it certainly gives you an idea about overall progress and state of software. In a nutshell, software is getting close but it still has some way to go. 

That’s all for now, stay tuned to this blog as well as [Twitter](https://twitter.com/thepine64) + [Mastodon](https://fosstodon.org/@PINE64) for more news in the coming weeks!
