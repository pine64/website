---
title: "May 2019 News"
date: "2019-05-06"
authors: ["Lukasz Erecinski"]
categories:
  - "news"
  - "pinebook-pro"
  - "pinephone"
tags: 
  - "bto"
  - "news"
  - "pinebook"
  - "pinebook-pro"
  - "pinephone"
cover: 
  image: "PinebookProandPinePhone1.jpg"
images:
  - "/blog/images/PinebookProandPinePhone1.jpg"
---

![](/blog/images/PinebookProandPinePhone1.jpg)

The new website is finally online and it is now easier to deliver news to people within and outside the community. Unlike the forum, information in this blog won't easily get lost among the countless other day-to-day threads concerning troubleshooting, new builds and similar topics. In the long run, I trust this will make it easier to find, reference and share information.

And so, with no further ado ...

##### News for May 2019 Run-Down:

- Forum updates incoming
- BTO is going away (for all devices)
- PinePhone Status Report 
- Pinebook Pro Roadmap

##### Forum Updates Incoming

One of the reasons for moving the community services to a new infrastructure was to make it easier to update and improve stuff on the fly and when it suits us. One of the issues we were facing with the previous server setup was the inability to keep the forum up-to-date (as to why that was the case ... it is a long story and not interesting). This is now an thing of the past, and so this week we will clone the forum database, update myBB to a recent version, add services we think / feel the forum deserves and migrate over. We do not expect any major or lengthy blackout because of this but be prepared for some potential forum disturbances this and the next week as we're working on it. 

###### BTO is Going Away (for all devices)

BTO is going away and is being replaced with a pre-order system. This change has already been reflected on the [Pinebook](/devices/pinebook/) store page. All those of you currently waiting in the BTO queue will be serviced, so don't worry - you are not waiting in vain. Initially, when the BTO system was implemented, it was intended to determine interest levels in the Pinebook. In practice however, it failed to work as a reliable indicator of how many people actually want a unit and hence, how many Pinebooks need to be built. It also proved to be very demanding on the shipping team and those who dealt with the system put in place to reissue BTOs when customers decided against purchasing their unit. We also realised that you guys aren't exactly huge fans of the system -  BTO tickets lost in spam folders, people forgetting their BTOs, high volume of 'when will it ship?' emails ... are all an indication that a different system had to substitute BTO. So, for the Pinebook, Pinebook Pro and PinePhone (and potentially other similar devices in the future) a pre-order system will be used instead. There will be a set quota of available units in each batch and the system will work on a first-come first-served basis. You will be notified about the availability of the device via an email; there will also be notifications on social media, such as Twitter and Mastodon. Forum and chat members will always get a short heads-up that the sales are going live. Consider it a nod to those actively taking part in the community. The pre-order page will list the expected shipping date and any other relevant information, which we trust will lessen the degree of confusion of when and what ships. There isn't much else to be said - the functioning of the system will be pretty straight forward. 

###### PinePhone Status Report

Development for the PinePhone is progressing nicely. Before I jump into some of the details, let me say that it is a real treat to see developers from all major Linux on-phone projects working together to achieve support for the PinePhone. The developers also collectively contribute to one repo, which means that they can benefit from each others work and do not have to re-do something that has already been solved or implemented. As things stand, new features and functionality are literally added daily. I hope to have some builds later this month so I can showcase them on youtube and make a post about the progress.That said, I fully understand and appreciate that developers want to take their time so as to have their early work reflect the effort they've put in, so this showcasing timeline may slip a little. Stay tuned. On the hardware front, the design of the PinePhone case is now complete (I'll make a video showing the mockup at the same time as I'll be recording the videos of early dev builds) and work on dev kits 2.0 with numerous fixes as well as the actual phone PCB will begin concurrently and very shortly. We expect to have a working prototype, as well as dev kits v2.0 (expected to be final) which will be fully aligned with hardware in the prototype(s), sometime mid-to-late summer. I dare say, unless something really unexpected happens - we will likely have the PinePhone ready before the end of this year. As we've said numerous times, this does not mean that we will start selling PinePhones the day we get them from factory; we will wait for at least one fully functioning OS build prior to sales commencing. More PinePhone news will follow late this month or early in June.    ![](/blog/images/PinePhoneFront1.jpg)

**Front of the PinePhone Mockup**

![](/blog/images/PinePhoneBack1.jpg)

**Back of the PinePhone Mockup**

###### Pinebook Pro Roadmap

The Pinebook Pro software and hardware is coming together both quickly and well. In terms of software, community developers have all key functionality already working in their respective builds, and partner projects will be getting their hands on dev units sometime this Summer. As of today, there are two builds that have full functionality from the two developers whom have worked to get their kernels ship-shape for partner projects; these two builds are, Ubuntu (with Mate/ LXDE) from ayufan and Debian Stretch from mrfixit2001. In terms of hardware, the Pinebook Pro demoed in a recent (and poorly recorded - sorry about that!) video is probably nearly identical to what you'll be getting when you order your unit. There are still a few outstanding PCB hardware issues in the unit I showed off in the video, which have now been identified and successfully resolved. The new PCBs should be back from the factory shortly, and granted that the PCB has no issues and test well, a pilot production of Pinebook Pros' will commence shortly after. I am assuming that since you are reading this blog, then you must at the very least have an idea about what hardware is in the Pinebook, and what sort of materials it uses (if not, [click here](/devices/pinebook_pro/)). In light of this, here I will focus on the two things that are rarely discussed but probably of vital importance to most users: the keyboard and trackpad. You will be happy to hear that the new ISO keyboard has a nice feel to it, has a soild click-y tactile plunge, the keys have a relatively long key-travel, and in my testing the keyboard has not exhibited any issues - indeed, I am writing this blog entry on the Pinebook Pro as a part of my testing. The trackpad is also a major improvement over the one found on the original Pinebook. For one, it is an actual point-to-point trackpad (and not an emulated mouse) and the coating / material that it is made out of is smooth and feels almost metallic to the touch. Now, if you're coming from a high-end laptop, such as the Macbook or Dell XPS, then the trackpad will probably not going to blow you away; that said, I have compared the trackpad on my prototype up against similarly priced laptops as well as laptops twice the price, and frankly speaking it is on par with just about everything that is out there. More information about the Pinebook Pro will follow next month. ![](/blog/images/pinebookkeyboard.jpg)

**The ISO keyboard layout that will be used on Pinebook Pro production models.**

**EDIT**: Here is a video where I showcase the software functionality on the current prototype. In this video I also discuss some of the design choices made - such as the ISO keyboard.

https://www.youtube.com/watch?v=mj3\_jMBlbxA

##### \[Edit 13/05/2019\] Future ANSI Keyboard Option

Right, ok, we get it - many of you want an ANSI keyboard layout as an option. Understood. We will eventually offer a EU/US keyboard layout option at store check-out.

This may take some time as we need to find a suitable keyboard first, put it though its paces to make sure that its good quality, and also make sure that no extensive retooling needs to be done on the Pinebook Pro case. This means that you can expect the first end-user batch (or two) to ship with the pictured ISO keyboard only, as its unlikely we will find a candidate ANSI keyboard, test it and implement in into the production schedule on-the-fly. I trust everyone understands that these things need to be properly tested and evaluated before going into production.

More Pinebook Pro updates are coming soon - I'll keep you posted.
