---
title: "FOSDEM 2026 Update"
date: "2026-03-24"
authors: ["Caffeine"]
categories: 
  - "community"
  - "news"
  - "pine64-community"
tags: 
  - "pinenote"
  - "pinetab2"
  - "fosdem"
  - "pinetimepro"
images:
  - "/blog/images/FosdemBanner_2026.jpg"
summary: "Hey again RSS readers (love y'all). In this update we share what we discussed at FOSDEM (PinePhone 2, community editions, DRAM shortage), what we demoed at our stand at FOSDEM and details on the PineTime Pro. Next month will have the main community update."

---

![The April 2025 community update banner](/blog/images/FosdemBanner_2026.jpg)

{{< toc >}}

## Housekeeping
Hey everyone! So long no talk. It’s been a long time since a proper community update, but rest assured a "full size update" update is coming sometime in April (Charlie the Pinecorn returns!). 

We are still planning to migrate to Codeberg for primary git hosting and committing to the move from mediawiki to our documentation site created by community member Funeral. We hope to make this happen sometime this year. 

And a message to the team over at Genode, yes I did read your book :) - Caffeine 

## What happened at FOSDEM 2026
FOSDEM 2026 was a very productive meetup for members of the PINE64 Community, aside from the occasional shenanigans. We had the opportunity to work on the PineVoice (formally PineVox) and PineTime Pro in person which helped push forward bring-up. There were additional discussions on potential new products and the effect of the DRAM chip shortage. 

![The group of peeps that went to FOSDEM](/blog/images/March_2026/TheBros.jpg)

![Top view of the Pine64 stand](/blog/images/March_2026/ImLiterallyStanding.jpg)

## Demos
### PineNote
The PineNote was shown off at FOSDEM with a few demos featuring hrdl’s Arch image and a pre-release image of QuillOS using hrdl’s kernel tree. With a massive thanks to Tom.K, Phantomas and hrdl for staying around and helping demo with his PineNote. Some demos included smoothly playing videos, playing doom (you had to be there to believe it!) along with its capabilities as an actual ebook reader. 

![Photo of PineNote and PineTab2](/blog/images/March_2026/DoomNGloom.jpg)

![Photo of two PineNotes, one running Arch and one running QuillOS](/blog/images/March_2026/QuillOS-hrdlArch.jpg)

![](/blog/images/March_2026/QuillOS.png)

### PineTab 2 
Danct12 put together an image for FOSDEM with camera and support for h264 video decoding. The demo also included a copy of big buck bunny and a razor1911 demo. 

![](/blog/images/March_2026/cool.png)

## DRAM shortage impact
Currently the DRAM shortage will impact the production of devices like the Pinetab2, PineNote and PinePhone. PineStore founder TL Lim has stated that he doesn’t wish to increase the price of hardware significantly so production is halted for the time being. Any remaining stock will be sold and that will be it for now. 

This will not impact devices such as the PineTime, PineBuds, Pinecil or PineVoice. 

## PineTime Pro

The new device is an improvement on the original with an AMOLED display, GPS, a custom chip, a digital crown which also features an extra button and new sensors including a blood oxygen sensor. Power to individual components can be cut unlike the non pro watch which will improve battery life. 

There has been discussion on if we do fund raising by baking in a small offset cost into the devices; or if we do a service with costs for fund raising. This decision has not been made yet. 

More information to come!

![](/blog/images/March_2026/PTP-Comparison.jpg)

## Future of community editions
Discussions were had concerning compensation and payment for work of developers working on PineStore devices. 

### Why can’t community editions exist for already released devices?
Creating a community edition device requires PineStore to create a new SKU for a device, this means that the community needs to agree on purchasing a device at an extra cost as the price of the device will go up (which represents the portion that is going to be donated).

Devices like the PineNote or PineTab 2 are likely not going to get community editions due to this, and we’re very much at PineStores discretion in this regard. As long as a price is organized before a new device reaches production, it is okay. But this process can be difficult if a bulk of the development happens after release hardware production begins.

### Challenges
Donations are messy, sending money overseas is messy, deciding who gets how much is messy. It’s a mess. 

* Tax: Taxes can significantly reduce the amount of funds developers end up receiving. Which makes everyone unhappy.
* Donations to groups of individuals rather than projects: For the PinePhone community edition devices donations were sent to projects. In the case for some devices where the factory firmware was made possible by the contributions of a number of individuals (not under a project), the problem arises of where to send donation funds. 
  * Fund allocation: How are funds shared between individuals and who actually gets a share (the people who worked on the shipped firmware, what about the people who worked on components like the kernel that the firmware relies upon?). In this situation the individuals would have to agree on how funds are split. 

## Where is the PinePhone 2?
The PinePhone 2 is a common topic within the community and was a hot discussion at FOSDEM in 2026. Aside from the current chip shortage, PineStore has determined that it is too high of a financial risk to release another phone. This is because the interest of the mobile Linux community has shifted to porting cheaper and more powerful Android devices to mobile Linux projects such as Sailfish and PostmarketOS. 

This will inevitably create a gap in the Linux phone space as the PinePhone is one of the few devices that a user can flash their own bootloader and modem firmware. 

However, potential components for another phone were discussed during the trip. A RK3572/6 as a potential SOC and a RedCap 5G modem which has an identical command set to the Quectel EG25-G modem found in the PinePhone/Pro. **Though note** none of these components are locked in for an actual device. 

So to conclude, the PinePhone 2 is currently in limbo for a number of reasons (financial riskiness, DRAM shortage, old Android devices make cheaper and more powerful Linux phones). But hopefully PineStore will eventually bring out another model. 

## To conclude
FOSDEM was a great turnout this year and we had a lot of fun meeting and catching up with people in the FOSS space. Thanks to everyone who came to FOSDEM and to those who came to say hi at our stand. Thanks to those who stuck around the stand with us, it made it a lot more enjoyable having you guys around. And of course, A special thanks to TL Lim from PineStore for sponsoring a group of our community members to visit FOSDEM. 

If all things go alright (touch wood), a full community update should be out sometime in April (time/motivation permitting :P). See you in a tick!

![Fosdem at night](/blog/images/March_2026/FosdemNight.jpg)

## Do you have something to share?
Do you have news to share with the community? You can have your news posted on this blog by heading over to [this tutorial and following the template](https://pine64.org/documentation/Introduction/Writing_a_blog_post/). All community updates are written in markdown which you can learn how to write [here](https://www.markdownguide.org/basic-syntax/).

If you get stuck, feel free to ask the folks in chat by finding your respective chat platform at https://pine64.org/community/.

## Contact 
### Community
Feel free to contact me if you have any concerns about community related topics. This can be about getting project support, sharing project updates, concern about prolonged wait times for support from PineStore (anything after 1-2 weeks) and any general feedback that could help improve the community. 

Community manager: camden.b@pine64.org

### PineStore
**If you have quality control issues with your device once you receive it, don't wait, contact PineStore support.**

* For general queries and information from the Pine Store: info@pine64.org
* For queries regarding support from the Pine Store: support@pine64.org
* For sales/wholesale related questions: sales@pine64.org