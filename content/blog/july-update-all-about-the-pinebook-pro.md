---
title: "July Update: All about the Pinebook Pro"
date: "2019-07-05"
categories: 
  - "news"
  - "pinebook-pro"
tags: 
  - "news"
  - "pinebook-pro"
cover: 
  image: "Pinebook_July.png"
images:
  - "Pinebook_July.png"
---

![](/blog/images/Pinebook_July.png)

As I’ve mentioned in last month’s update post, the PinePhone prototypes are currently being manufactured (due in August) and the PineTab dev kits are rolling off the factory line to be shipped out to developers. With both the PinePhone and PineTab currently in-transition to their respective next development stages, I’ll devote this month’s update solely to the Pinebook Pro pre-order announcement, the last unannounced feature of the laptop as well as a hardware and software status update. 

There is plenty to get to so let's run though the points.  

#### Bullet points: 

- Pinebook Pro pre-orders start July 25
- Pinebook Pro gets privacy switches 
- Pinebook Pro OS builds 
- Battery life & ‘magical’ kernel
- PINE64 key cap

#### Pinebook Pro pre-orders start July 25

**\[edit\] 26/07/2019**

Those asking about the pre-order system, coupons and shipping timeline please read the following forum threads:

[https://forum.pine64.org/showthread.php?tid=7725](https://forum.pine64.org/showthread.php?tid=7725)

[https://forum.pine64.org/showthread.php?tid=7752](https://forum.pine64.org/showthread.php?tid=7752)

Thank you!

This is the announcement many of you have been waiting for. The Pinebook Pro production has been green-lit and pilot batches have been scheduled for production. With the remaining hardware issues identified and resolved (side-note, huge thanks to the the key devs - ayufan and MrFixit - as well as the community for all the help sorting things out!), we’re now feeling confident that we can to proceed full steam ahead. A countdown for Pinebook Pro is now live and ticking away, so no one PM or email me saying they didn't know or hear about it - this is plenty of heads-up time. If you follow us on Twitter, Mastodon, are a member of the forum, check the web-page or read the Linux press regularly, then you’re unlikely to miss the moment the pre-order system become accessible.

As [we’ve promised from the very start](https://forum.pine64.org/showthread.php?tid=7093), **community members who registered on the forum prior to July 1, 2019 are eligible for a 128GB eMMC upgrade as well as pre-order priority**. The eMMC capacity upgrade is a **limited-time offer**, available only for the first batch of Pinebook Pro laptops. 

I’d also like to include a quick word of caution; **pilot batches are aimed at enthusiasts**. We do diligent testing of the hardware and create numerous prototype iterations to make sure that we deliver the best possible product on launch day. However, we cannot emulate thousands of people using the device, it is simply not possible, and as a result minor issues (usually fixable with some tinkering) may be present in the pilot batch. If you’re not the sort of person who likes to actively engage in development or issue-solving, or simply is not willing to take the risk, then it may be a good idea to wait for the second or third batch. I am not saying that issues are expected, but it's the nature of pilot batches that they are effectively a chance for us to get feedback on the hardware from a large sample of users. I thought I'd get this out there are there is a lot of interest in this device.

Lastly, I realize that making a purchase decision is often dependent on what reviewers and notable individuals from the Linux world say about the product. Since reviewers will be getting their Pinebook Pros at the same time as end-users or even later, I figured I’ll reach out to the relevant people in my neck of the woods and give them hands-on time with the prototype. Now, I obviously cannot make anyone cover the Pinebook Pro, nor do I want to make it sound like it is an expectation on my end, so I am leaving the names of the people and their shows out of this post if they choose not to talk about it. But keep an eye out (and an ear out - is that even an expression?), since some of them may decide to discuss their experience with the prototype online.

#### Pinebook Pro Privacy Switches

Privacy switches on the Pinebook Pro are the last unannounced feature I was dying to talk about for some time now. I had to hold back my excitement and keep my mouth shut because we first had to make sure that our implementation of the switches would work reliably and as intended. The reason we kept this information back wasn’t to be secretive, but rather not to disappoint you if the implementation wouldn’t pan out and the Pinebook Pro would ship without this feature. With that out of the way; we’re very pleased that the implementation worked out because we’re very well aware that a part of the draw of the Pinebook Pro is its core FOSS nature, which means respect for both users’ choice as well as privacy.

![](/blog/images/privacy-switches.jpg)

Back to the subject at hand. There are three privacy switches mapped to the F1, F2 and F3 keys on the Pinebook Pro keyboard. They deactivate the following: 1) the BT/WiFi module; 2) the webcam; and 3) the microphones. I’ll give you a broad overview of how the switches work and answer the inevitable questions about their security. The keyboard has a special firmware that lives on, and operates separately of, the operating system. In a nutshell, it detects if F1, F2 and F3 keys are pressed for 10s. Once one of the keys get pressed for the set duration, the keyboard firmware cuts power to the chosen aforementioned peripheral. The implementation is no different to cutting a peripheral power mechanically via a physical switch, and the power state settings for each is stored across reboots.

This is privacy switch implementation is highly secure since the firmware that dictates if peripherals get powered is not a part of the Pinebook Pro’s operating system. The power state value for each peripheral also cannot be overridden from the operating system. In fact, the keyboard firmware itself cannot be accessed from the operating system. I have been told by a hardware engineer that, under particular circumstances, this particular privacy switch implementation may be safer than mechanical switches. If you’re really tech-savvy, and want to know how the firmware works, then I am afraid you’ll have to ask someone smarter than me (which means pretty much everyone in our IRC / Discord); I may get someone technical to write up a short piece about the privacy switch implementation if many of you request it specifically. 

So there you have it, the Pinebook Pro is a FOSS laptop with privacy switches built from premium components that now also features privacy switches for peripherals relevant to security and privacy. Freedom of choice and openness has always been a core tenet of our projects, and now with the Pinebook Pro and PinePhone we’re starting to tackle the other vital component that the community cares about - the privacy and security hardware features.   

#### Pinebook **Pro OS choices on launch day**

I expect that there will be three OS types available for device on day one: 1) different flavours / distros of Linux (discussed in past month’s update); 2) Chromium OS; and lastly 3) Android 9. Two quick notes before we proceed, firstly I’ll skip discussing Android in this update as I expect few people care about or/and want Android on a Laptop. I just wanted to let people know that there is a build for it and it works. Secondly, you probably already spotted the notable absence of \*BSD on this list. This is largely our fault, stemming from the philosophy we adopted for building up early software support for the Pinebook Pro. That said, we cannot wait to see \*BSDs on the Pro once it gets into developers hands. 

###### Linux

Let’s talk a bit about the state of Linux for the Pinebook Pro. As far as _Linux on ARM development_ goes, I can say with confidence that we’re in what I like to call the luxury territory. What I mean by this is that everything works - some things better than others, but it’s all there - and there are no deal-breaking issues in any of the builds. Developers have effectively moved from ‘making things work’ to ‘making things work better’ in the past two months. Improvements are literally done daily, if not hourly, and everything from desktop acceleration to trackpad settings  and battery-life is being continually tweaked. Regarding the custom Debian build that will ship with the Pinebook Pro - at the time of writing we still have about two weeks to continue tweaking things so they work their best. You will, of course, likely want to hit the update icon when you get your laptop, which will update the kernel and numerous other things, as well as run your regular apt updates and upgrades.  

![](/blog/images/Linux_Debian.jpg)

Let me reiterate very quickly on the state of the Debian build that will ship with the Pinebook Pro. It features an accelerated Mate desktop, allows for 3D applications and you can play back videos locally up-to 4K at 30fps. Youtube as well as Netflix and Amazon playback work well at 1080p resolutions in the Chromium browser. Video out via USB-C works flawlessly too, so you’ll be able to use the Pinebook Pro for presentations, media, etc., For the record, the very same functionality is available in ayufan’s Ubuntu with Mate image, which also runs on the RockPro64, and can be [downloaded directly from his github](https://github.com/ayufan-rock64/linux-build/releases/tag/0.8.3). At the risk of repeating myself, by the time you receive your Pinebook Pro there may already be other alternatives from partner projects; if not at launch then soon thereafter you’ll surely see the Pinebook Pro supported by the usual suspects (and newcomers to PINE64 hardware realm we’ve been talking to as well!). The one piece of functionality that we’re still working on is charging via USB-C - it works, but requires a very specific mode of charging at this time. We hope to improve this by the time the first units ship to end-users. I’ll make sure to update everyone on the state of this matter in due time.

Let’s talk battery-life. Developers are currently working at getting the optimal values for the battery into the device tree. In result we will need to wait a little bit longer to have a full picture of how well the battery performs during daily usage. That said, cool things have been done to improve battery life on the kernel level. MrFixit2001 has managed to make the governor monitor activity, so that not only does it set the frequency of the cores but also automatically turns the cores on and off on a need-be basis. We expect that this will see a significant improvement to battery life as well as thermals whilst having a relatively small impact on performance. From my testing, relative to all cores being active and the default interactive governor settings being applied, running webGL demos and playing simple games the observable performance difference is really negligible (for reference, 5 FPS difference running Aquarium WebGL demo). This is a very cool trick and one will be further improved upon and find its way into the majority, if not all, OS’ for the Pinebook Pro. Lastly, I think its worth noting that you can also turn individual cores on and off manually from the userspace for cores cpu0-5 (exchange value for X), which comes in handy if all you're doing is terminal work or taking notes in class: _echo 0 > /sys/devices/system/cpu/cpu0/online._ This applies to all current Linux builds.  

###### Chromium OS

Some of you will probably write Chromium OS off as a daily-driver option, whilst others will be excited about it. Regardless of your personal views on the subject matter, there is no denying that having the choice to run it on the Pinebook Pro is a great option to have. Speaking of running Chromium OS, I cannot stress enough that the OS runs absolutely great on the Pinebook Pro. Even this early release is exceptionally smooth. There is no denying that ayufan has done a heck of a job, in a short amount of time, getting this build shipshape. For those of you who have a RockPro64 - you can already [download and try it out](https://github.com/ayufan-rock64/chromiumos-build/releases/tag/R76-12239.4.100.gf2199d0). For the most part everything in Chromium OS seems to ‘just work’ on the Pinebook Pro; movies (online and local) play perfectly smoothly, 3D applications are perfectly responsive and the few web-apps I tested ran as they are supposed to. The build also comes with at Linux VM, which can be enabled under the settings menu. This allows you to install and run regular Linux applications on Chromium OS pretty much as if they were native Linux applications. So if you don’t want to use Google Docs, you can always install LibreOffice as you’d do on any Linux laptop. Apart from occasional and very minor glitches the build is highly usable and exceptionally polished. 

If you have kids in school in Europe (or US/Australia), or other places were a lot of schools use Chromebooks as default teaching devices, then the Pinebook Pro may just be something to consider. For starters, it’s sturdy enough to be tossed carelessly into a school backpack and even slammed down on a desk now and then … not that I recommend it. Secondly, once your child outgrows Chromium OS and will want to explore a bit more, you can just load up a Linux distro for them. Not to mention that you’d be supporting a small FOSS company rather than one of the many large Chromebook manufacturers. I trust this comes across as a genuine idea to consider and not a sales pitch, for it is not. 

![](/blog/images/Chros1.jpg) ![](/blog/images/chros2.jpg)

###### A quick note on \*BSDs

So I said I won’t be talking about the BSDs, but I feel like I should at the very least give you a general overview of the RK3399 \*BSD functionality. I’ll make it quick. I’ve spoken to \*BSD devs whom worked on the RockPro64 and from what I’ve gathered (despite the different \*BSDs having varying degree of support for the RK3399 SOC) many of the core features are already supported, which bodes well for \*BSD on the Pro. That said, some of the things you’d require on a functional laptop - such as the LCD (using eDP) for instance - will not work on the Pinebook Pro using \*BSD as of today. So clearly a degree of work is yet needed for a BSD to run on the device. However, keep in mind that \*BSD developers will be receiving their units soon and by the time you receive yours some basic functionality may be available. 

#### PINE64 logo on Pinebook Pro key cap

It never ceases to amaze me how passionate people can be about the stuff were doing. Before I get to the meat of this (admittedly very minor) story, let me give you some background. There are two factors that underpin it and explain its origin; the first of which is that I genuinely do not like the hamburger (three horizontal lines) menu icon on the regular Pinebook. Sure, it's better than having a Windows key cap, but it just seems very impersonal to me. The second factor stems from feedback in a [recent OMG! Ubuntu! Article](https://www.omgubuntu.co.uk/2019/06/june-pinebook-pro-update) relating to our choice to not brand the Pinebook pro, that I’ll quote here:

“_Although this is a nice move_ \[not to brand the Pinebook Pro\] _on Pine64’s part, it’s also a little sad. The company is busting their posteriors on all this tech, so it’d be nice to see their efforts rewarded with a bit of awareness.”_ 

Now to the meat of the story. With the two aforementioned factors in mind, I threw out a question in the chat the other day asking people if they think that a PINE64 pine-cone logo would be a good substitute for the current menu icon. My thought behind this was to see if we could have this tiny piece of branding on the device and at the same time potentially improve the functionality of the key. I tossed the question out and went to make myself a cup of coffee. When I returned to my computer screen I was greeted with backlog of dozens of replies. As it turns out, people really do care about how their keys look and what they do. 

The overwhelming majority of people welcomed the idea of the little PINE64 pine-cone logo on the key cap and, as is the case when you ask a thousand people about their opinions, offered up many different ideas as to what the key cap can do. As things stand, I am happy to say that the menu logo will be substituted by the PINE64 logo, but it will take us some time to figure out its final functionality. If you have ideas of your own, make sure to post them below or on the forum.

That wraps it up for this month’s update! 

**\[edit July 16, 2019\]** Finally had some time to sit down and give a short, unstructured, overview of the build that will ship with the Pinebook Pro. I know that many of you have asked for another video detailing how the Pinebook Pro performs in a real-life scenario, and I feel this is a pretty fair representation of what you can expect.

https://www.youtube.com/watch?v=F-Yh8uiA2TY&t=0s
