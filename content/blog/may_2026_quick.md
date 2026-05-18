---
title: "Quick update: May 2026"
date: "2026-05-18"
authors: ["Caffeine"]
categories: 
  - "community"
  - "news"
  - "pine64-community"
tags: 
  - "project update" 
images:
  - "/blog/images/pine64_banners/festival_lights_notext.png"
summary: "The PineVoice HA speaker is in the final stages as production begins, new PineTime revision to replace EOL display part, new PineTime Pro samples have been received by community developers, LoRa hardware development kicks up again along with other important community related updates."

---

![Blog post banner artwork](/blog/images/pine64_banners/festival_lights_notext.png)

{{< toc >}}

## Whats been going on recently?

Hello everyone, we wanted to do a quick update on what's been happening recently. Life has been pretty busy but there's lots of nice things happening in the background that we'd like to share.

## PineVoice
The PineVoice Home Assistant speaker (formally PineVox) is in its final stages. Production begins. Further on this, there will be limited bundle with this device which will include a PineVoice, Zigbee dongle, power supply and two matter modules. Pair it with a SBC of choice and run your Home Assistant instance locally!

## PineTime/PineTime Pro
* The current PineTime LCD is EOL and a new one is replacing it, though it is essentially the same display. These will be shipping in the next PineTime batch.

* New PineTime Pro samples have been received by developers. Shiny! 

## LoRa? (Left-handed operational Radio authority, obviously)
The PineDio USB LoRa Adapter is at the focus of a new effort to begin progress on potential new LoRa devices. [MeshCore](https://meshcore.io) is the current protocol target for the USB LoRa Adapter along with help from the [pyMC_core](https://github.com/pyMC-dev/pyMC_core) library project.  

The current problem with the device is that the crystal oscillator is heating up too much and can cause clock frequency drifting instability. In a nutshell that means your messages come out garbled. This may eventually be fixed with a TXCO (Temperature-Compensated Crystal Oscillator) to maintain a stable clock frequency.

## Important recent community updates:
* [DanctNIX PineTab2 updates (including factory image)](https://social.treehouse.systems/@danctnix/116493536602596537)

* Adam Piggz: PinePhone, PinePhone Pro, PineTab2 all updated to kernel 7.0, and improved USB config. Zypper ref and dup to update. 

* [machaddr@mastodon.sdf.org: with their new Gentoo PineTab-V image](https://social.treehouse.systems/@machaddr@mastodon.sdf.org/116550551558106497)

## Do you have something to share?
Do you have news to share with the community? You can have your news posted on this blog by heading over to [this tutorial and following the template](https://pine64.org/documentation/Introduction/Writing_a_blog_post/). All community updates are written in markdown which you can learn how to write [here](https://www.markdownguide.org/basic-syntax/).

If you get stuck, feel free to ask the folks in chat by finding your respective chat platform at https://pine64.org/community/.

## Contact 
### Community
Feel free to contact me if you have any concerns about community related topics. This can be about getting project support, sharing project updates, prolonged wait times for support from PineStore (anything after 1-2 weeks) and any general feedback that could help improve the community. 

Community manager: camden.b@pine64.org

### PineStore
**If you have quality control issues with your device once you receive it, don't wait, contact PineStore support.**

* For general queries and information from the Pine Store: info@pine64.org
* For queries regarding support from the Pine Store: support@pine64.org
* For sales/wholesale related questions: sales@pine64.org
* If you have hardware defects or any other hardware issues to go: https://pine64.zohodesk.com/portal/en/home