---
title: "FOSDEM 2020 and Hardware Announcements"
date: "2020-02-03"
authors: ["Lukasz Erecinski"]
categories:
  - "community"
  - "cube"
  - "hardrock64"
  - "soedge"
tags: 
  - "cube"
  - "hardrock64"
  - "soedge"
cover: 
  image: "dinnerfosdem20.jpg"
images:
  - "/blog/images/dinnerfosdem20.jpg"
---

![](/blog/images/dinnerfosdem20.jpg)

**PINE64 get-together with community devs and partner-projects at FOSDEM 2020**

Sorry for the delay in delivering FOSDEM news and announcements to you - I was too occupied with great company, splendid beer and shouting at hundreds of people across our stall table. It was awesome to see so many familiar faces, meet new ones and socialise with projects we usually don’t get an opportunity to talk with. 

Some of you may have already seen pictures or videos of our stall at FOSDEM overflowing with people; I am happy to say that we were one of the most - if not _the_ most - besieged stall at FOSDEM this year. There literally was a wall of people at the stall at all times, and if not for our community members and partner-project devs we’d probably not cope. This also had the effect of being as much our booth as that of Manjaro, UBports, Nemo mobile, KDE, postmarketOS, Aurora,  Meamo Leste and others :)

![](/blog/images/fosdem20stall.jpg)

**Crowd at the PINE64 stall FOSDEM 2020**

In the January community update we announced that if you are attending FOSDEM, and already had a PinePhone on order or with you, then we’d have a surprise piece of swag for you. As some of you already know, the swag in question was a choice of a hard or soft PinePhone case. Over the course of ~8 hours that we were at the stall we gave well over 100 cases. It was really exciting to see so many PinePhone early adopters at FOSDEM.

![](/blog/images/PinePhone-Cases.jpg)

**Soft (silicone) case left, hard case right**

Apart from our cramp little corner of FOSDEM, you could also check out PINE64 devices at the KDE and OpenHAB stalls. There was also a talk by [Merlijn Wajer and Bart Ribbers](https://www.youtube.com/watch?v=JfxZ7Dl00mE) (youtube video linked) concerning Linux phones as well as a joint BOF with Purism (my thanks go out to Dalton and Bhushan for taking the lead on this), where a significant portion of the time was dedicated to the PinePhone in particular. In other words, there were many PINE64 accents all over FOSDEM, which made me realise how much we’ve grown in the past two years.  

![](/blog/images/KDE-stall.jpg)

**KDE stall FOSDEM 2020**

However, to us, FOSDEM means getting together, talking about how our current projects are coming along, nagging Bhushan about the KDE Neon image, and meeting with all the amazing developers making all this happen. But it is also the time of the year when we announce new devices. This year we’ve decided to tackle announcements slightly differently. What we’re announcing now relates only to our plans for Q1 and Q2 of 2020 and not the entirety of this year. That is to say, we have more exciting things coming in the second half this year, but we’re holding off from announcing these things at this time. 

Let me explain. We’ve learned a lot from last year’s experience with Pinebook Pro and PinePhone production delays, which effectively means we understood that it is better to tackle fewer things at a time. In Q1 and Q2 we are yet to review PinePhone and PineTime status, release the PineTab early adopter edition and make good on our promises to deliver the upgrade-kit for the original Pinebook. That is a lot of work left over from last year. So at this point we’re only announcing things we’re confident we can deliver by early May. Once we clear everything we currently have on our table, we’ll be announcing plans we’ve got for Q3 and Q4. This is the pace of announcements will likely follow in the future too.

With that out of the way, let us talk about what we’ve got coming soon.

##### The HardROCK64

![](/blog/images/HRock64-1.jpeg)

**HardROCK64 (top)**

It has been a little while since we did a single board computer (SBC). For the past year I kept on telling people that whilst we have now a wide range of devices (that you guys are clearly both excited and happy about) we’re still going to make SBCs, since that is our bread and butter. Therefore I am super happy to announce the HardROCK64 - a small form-factor SBC with a lot of umph. 

The board features:

- The RK3399 hexa-core SOC found in the Pinebook Pro and on the ROCKPro64
- 2xUSB 3.0
- 2xUSB 2.0 
- WiFi AC and BT 5.0
- Gigabit Ethernet  
    
- Full GPIO pins 
- SPI flash
- eMMC socket 
- mSD card slot
- Fan & RTC headers
- Heatsink mount
- CSI connector
- DSI connector
- IR receiver 
- 5V barrel jack for power
- Digital video out 

The board will ship in 3 LPDDR4 RAM configurations (tentative $ pricing): 

- 1GB ~ $35
- 2GB ~ $45
- 4GB ~ $55

Tentative release date: April 2020

![](/blog/images/hrock64bottom.jpeg)

**HardROCK64 (bottom)**

The board will run all ROCKPro64 OS images with little or no tweaks (we checked) and probably most Pinebook Pro OS with a ‘simple’ device tree tweak. In other words, if you don’t need all of the ROCKPro64’s functionality - e.g. PCIe or USB-C - then this may just be the board for you.

The board does run hot so a heatsink is pretty much mandatory. A couple different options will be sold by us to match your needs and expected the SOC load. 

##### SOEdge AI Module

![](/blog/images/soedgeusb.jpeg)

**SOEdge in USB 3.0 Adapter**

The other thing we’ve been known for in enthusiast, industry and custom embedded device circles are our SOPine compute modules. The SOEdge is a 3TOPS compute module that can be paired with the SOPine base board or USB 3.0 and PCIe adapters for development. It can connect to a SBC, such as the ROCKPro64 or a regular PC. We initially planned the release of the SOEdge module last year, but Pinebook Pro and PinePhone delays pushed it back to this year. 

Features:

- Rockchip RK1808 dual-core Cortex-A35 processor with a 3.0 TOPS  Neural Processing Unit
- 2GB DDR4 PC-2133 RAM
- 16GB eMMC flash
- PMIC – Rockchip RK809-2
- 204-pin SO-DIMM connector (same as the SOPine modules)

Tentative price: ~ $30

Tentative release date: ~ April/May 2020

![](/blog/images/soedgepcie.jpeg)

**SOEdge in PCIe Adapter**

![](/blog/images/cluster.jpeg)

**Clusterboard with 4 SOEdge and 3 SOPine modules**

The SOEdge can be used in a variety of scenarios and is compatible with current and future SOPine boards, including the clusterboard which can host up-to 7 modules clustered via Gigabit Ethernet. I can imagine that mixing SOPine and SOEdge modules in the Clusterboard can yield results in various applications. I’ll leave it up to your imagination :)

##### CUBE IP Camera 

[It was a year ago, pretty much to the day](https://forum.pine64.org/showthread.php?tid=7093) (except then I was more diligent and released information on time), that we announced that we’re working on the CUBE FOSS IP camera. We then encountered issues with the SONY camera implementation, and with the big devices such as the Pinebook Pro and PinePhone in the works, the project got shelved until further notice. 

So, here is the notice, we’re working on the CUBE again. I’ll have more news regarding the CUBE, including what necessary changes were made to the camera, in the February community update on February 15. 

That's it … for now. As I’ve already stated, these are the new devices that we will strive to get in the PINE Store by May. But there many other product ideas that we have in the pipeline, and you’ll be hearing about them once all the PinePhones, early adopter PineTabs, HardROCK64s and SOEdges start shipping. Hope you’ll agree this is a better approach for this year. 

Thanks once again to everyone who made it out to see us at FOSDEM and, of course, FOSDEM organisers and volunteers. 

![](/blog/images/cubecam.jpeg)

**Original CUBE IP camera prototype (image from 2019)**

**N.B.** _All pictures of devices depict product prototypes; final version of device may, and likely will, differ in appearance or / and functionality._
