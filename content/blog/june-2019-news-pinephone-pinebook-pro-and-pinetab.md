---
title: "June 2019 News: PinePhone, Pinebook Pro and PineTab"
date: "2019-06-06"
authors: ["Lukasz Erecinski"]
categories:
  - "news"
  - "pinebook-pro"
  - "pinephone"
  - "pinetab"
tags: 
  - "pinebook-pro"
  - "pinephone"
  - "pinetab"
cover:
  image: "/blog/images/PinePhoneID.jpg"
images:
  - "/blog/images/PinePhoneID.jpg"
---

![](/blog/images/PinePhoneID.jpg)

#### Bullet Points:

- Forum is done, next up: chats and Wiki
- PinePhone prototype in August ; software coming along
- ANSI keyboard for Pinebook Pro ; new features / upgrades ; pre-orders this summer
- PineTab M.2 optional adapter ; 64GB eMMC ; pre-orders this summer
- New boards in the pipeline ; AI SBC/SOM of interest to us

###### Housekeeping

As many of you have probably noticed the forum has gotten an update. We’re still tweaking things now that the new layout and features are live, and we’ll continue to monitor your feedback and update things on a need-be basis. With the webpage and forum done, the chats and Wiki are next on our agenda. Both of these undertakings present their own set of challenges, hence may take some time to complete. If any of you wish to volunteer your time, especially with regards to improving the Wiki, then please let me know in the comments section below or the forum. Thanks!

###### PinePhone

Last month I began with (and spent most time on) the Pinebook Pro, so it's just fair that I open this month’s update with the PinePhone news section. A lot has happened in the short period of one month, so the best I can do is to try to summarize the most important aspects pertaining to hardware and software progress. I’ll pay more attention to hardware developments in this post, simply because I am not competent in providing an up-to-date report on every projects’ software status (you can reach all the devs in the chat and follow the progress live using the chat log if you wish to stay up-to-date). For what it's worth, I am happy to give you a short resume of my experience with the few OS images I’ve tested at the end of this section.

Let’s start with the end-user PinePhone developments. With the case selected and approved, the phone’s PCB was commissioned a couple of weeks ago and submitted to the design house with detailed instructions on the required feature set. The first of the things we settled on was the battery capacity and physical dimensions; the battery will be the same capacity as the Samsung J7 SM-J700H/ BJ700BU (3000-3400 mAh), which can be had for under $10 from amazon and eBay. So in the event you need replacement or spare batteries, getting hold of them will be easy and affordable. We also settled on the number, and the implementation of, privacy switches on the phone - there will be 4 switches in total: for the i) BT/Wifi module, ii) the modem, iii) cameras (front/back) and iv) lastly for the microphone. They will be located on the PCB, under the back-cover, to prevent them from being toggled by accident, e.g. in your pocket or purse.

After a chat with developers, we also came up with a way to expose I2C using 6 pogo pins. These pogo pins will be located directly on the PCB. The idea behind this implementation is that entire back-covers with add-on components can be created (even 3D-printed) with additional functionality to enrich the phone’s functionality. The implementation only requires that the custom back-cover with additional hardware has the same dimensions and position of plastic latches as the original - and obviously that the component in question uses I2C (contact pads). I expect that a back-cover with a keyboard - perhaps one similar to that found on the Nokia N900 - will be something a considerable number of people may be interested in creating. To this end, we’ll make sure to have detailed documentation on this feature. I really hope that the hackers and tinkerers among you will embrace and make use of I2C for new cool implementations.

![](/blog/images/PinePhone1.png)

**Mainboard Front**

![](/blog/images/PinePhone2.png)

**Mainboard PCB Back**

![](/blog/images/PinePhone3.png)

**Slaveboard PCB**

Rounding off the hardware-side of things - I don’t want to jinx it, but as you can probably tell from what I’ve already written, the PinePhone project is coming together really nicely. As things stand today, we expect a fully functional prototype in August. Once we have the prototype, it will then have to undergo functionality and durability testing before production of a pilot batch can commence. More on this in future updates. I’ll also note that the final dev kit (2.0), which incorporates fixes for all the issues found in dev kits 1.0, 1.1 and 1.2 as well as alignes all functionality (e.g. HDMI out via USB-C) with the production PinePhone, will be produced at the same time as the prototype.

Things are also progressing well on the software-front. The core phone functionality - calling and sending messages - has now been enabled in a number of OS’. It took a little while to get the mobile networking working due to an error with SIM slot wiring on dev kits 1.1 and 1.2; that has now been fixed using an adapter, and the aforementioned dev kit 2.0 will no longer require the adapter. I’ve tried PostmarketOS (Plasma mobile / XFCE / Weston demos), Maemo Leste and LuneOS in recent weeks and they’ve all made significant progress in a very short amount of time. The functionality highlights for each OS differ - which makes for interesting testing of these early OS images. For instance, Maemo Leste has messaging etc., enabled, while PostmarketOS has managed to get the camera working (Martijn from PMOS even ran a ~2hrs stream live from the dev kit), and LuneOS offers an extremely smooth UI experience with many applications working, including browsing the web. Morover, all sensors and even the speakers now work too, so things are really comming together at a rapid pace. As I’ve already mentioned in the May news update, developers from all the different OS’ work together, and so all the newly enabled functionality quickly finds its way into all OS images. I am still waiting to try a number of the OS’, including Ubuntu Touch and Sailfish OS; once I get my hands on these builds I’ll make sure to record a compilation demo, showcasing functionality and performance.  

https://www.youtube.com/watch?v=3SyqbI24qu0https://www.youtube.com/watch?v=UlrIqAwHRXY ![](/blog/images/Sailfish.jpg) ![](/blog/images/pinephonesway.jpeg) ![](/blog/images/LuneOS.jpg)

###### Pinebook Pro

We listen to your feedback and take it to heart. For those of you who have not read my edit to last month’s post: there will be both an ISO and ANSI keyboard available for the Pinebook Pro. I do not have more information about when the ANSI keyboard will be available at this time - but I am getting an evaluation unit with the ANSI keyboard soon - I’ll edit this update accordingly to let you all know how I find this candidate keyboard. Wrapping up the keyboard discussion, I’d just like to make it clear - the first Pinebook Pro batches will most likely only ship with the ISO keyboard. Let me also address all those of you who are asking about regionalised layouts - there is currently no plan to support any other layouts except for standard ISO and ANSI.

![](/blog/images/PInebookPro_ANSIISO.png)

**ANSI and ISO Keyboard Variants**

The choice of keyboards isn’t the only update to the Pinebook Pro since its announcement. In fact, there are some really awesome features coming that we haven’t talked about yet - largely since they need to be properly tested first - which I expect to discuss in next month’s update. I think many of you will be thrilled. That said, there are another two small updates to the Pinebook Pro that deserve some spotlight too. The first of these is that Pinebook Pro has been upgraded with a BT/WiFi module that supports Bluetooth to 5.0 (vs announced BT 4.1) and secondly we’ve asked for improvements to the firmware of the trackpad. As with many things in life, the devil is in the details, and on a laptop that means the input methods, which really makes or breaks the experience. The trackpad on the current prototypes is already very solid, but we are talking to the hardware vendor to further improve precision and reduce accidental inputs of the trackpad. Lastly, we decided not to have any branding on the Pinebook Pro, since it seems this is what users prefer. So you get to decorate it yourself using stickers or keep it smooth and black - up to you.

I also have good news for all developers hoping to get their hands on the Pinebook Pro. If the aforementioned Pinebook Pro unit I’ll be receiving soon addresses all, or at least most, of my initial feedback I submitted to TL to be forwarded to the factory, then the manufacturing process for a developers batch will start shortly. This means that by the time end-users get their hands on the Pinebook Pro there will be a number of Linux, and possibly even \*BSD, options to choose from.

Speaking of software, I am also happy to say that the state of software tailored for the Pinebook Pro is already superb. The last major outstanding issue with the Linux test builds (PCIe locking up in desktop use) has been resolved as of May 27th and all other features required for laptop functionality now work. Just for the sake of diligence, let me list some of the key components for desktop use that ayufan and mrfixit2001 got working in their builds over the past few months: BT/WiFi; PCIe (M.2) ; LCD panel including brightness ; suspend/ resume from suspend ; sound (speakers+headphone jack) ; USB-C (data, charging + video out) ; accelerated desktop (xorg glamor or armsoc) ; 4K video acceleration of local media ; 3D and video acceleration in browser (including: webgl 2.0 & widevine) ; support for a number of peripherals. More info on the respective builds can be found [here](https://github.com/ayufan-rock64/linux-build/releases) and [here](https://github.com/mrfixit2001/debian_desktop/releases).

Many of you have been asking about Pinebook Pro availability and when pre-orders will start. The answer is “this summer”, as we still need to evaluate the pre-production units for fit-and-finish and functionality. I trust you can appreciate that this is an important step and cannot be rushed. If it turns out that everything is OK with these units, then right after the pilot batch for developers regular production will start. Regarding when and how you find out about the Pinebook Pro pre-orders - chat and forum members will be alerted slightly ahead of time since we want our core users to get a small heads-up. Then we’ll send out notifications via social media (Twitter and Mastodon) and make an announcement on the website. This will likely be picked up by relevant media outlets too. In the future, there will be a newsletter sign-up that will alert you to new Pinebook Pro batches being available.

![](/blog/images/underthehood.jpg)

**Here is a peek under the hood of the pre-production (post-prototype) Pinebook Pro**

###### PineTab

I know that the PineTab news are well overdue, but once you’re done reading this section I hope you’ll agree that the wait well worth it. Long story short, the delay in PineTab production was due to us being unsatisfied with the digitizer panel; this has now been sorted and evaluation units of the tablet are now being built.

This delay was, however, not a waste of time. The extra time gave us space to think and consider what else can be improved on, and added to, the current design. We ran a poll some time back asking about the desired storage capacity for the PineTab, and the majority of users showed a strong preference for increasing the eMMC storage capacity to 64GB. After some considerations, we decided to honour the community vote and we’ll be including this larger eMMC with the PineTab.

We have also decided to include an option for a M.2 adapter on the PineTab. This will allow a number of expansion options that users and developers can explore - the most obvious applications being LTE and storage, but I am sure that you can think of other ones too. We hope that you’ll agree that the time it took us to bring the PineTab to fruition, since its announcement earlier this year at FOSDEM 19, has not been wasted despite the delay in selecting a suitable digitizer panel.

Granted we’ll be happy with pre-production units delivered to us and developers, then you can expect the PineTab to be available late this summer. More information on the PineTab and its new pricing will follow soon.

###### Future Single Board Computers

As I’ve already written in the May update, SBCs are and will remain PINE64’s bread-and-butter. They will always be the basis for any new devices - such as laptops or phones - that PINE64 will develop. It’s a part of us striving for software compatibility between the different types of hardware, reducing the workload of developers porting their OS’ to a new devices. To this end, I’d like to assure everyone that new (and exciting) boards will be coming in the future. It is too soon to talk about these boards however, since some of them are in concept or layout stages whilst others are still in our heads. What I will say, however, is that one field we wish to explore is AI, and we hope to bring both AI-focused boards and modules to the Pine Store in the future.

That's it for this month’s update, chat away below or on the forum / in the chats.
