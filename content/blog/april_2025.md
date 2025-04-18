---
title: "April Update: Risc It For A Biscuit"
date: "2025-04-13"
authors: ["Caffeine"]
categories: 
  - "community"
  - "news"
  - "pine64-community"
tags: 
  - "pinenote"
  - "pinetab2"
  - "pinetab-v"
  - "fosdem"
  - "pinetime"
  - "pinecil"
cover: 
  image: "AprilBanner_2025.jpg"
images:
  - "/blog/images/AprilBanner_2025.jpg"
summary: "This month, the PineTab-V returns, PineNote, PineTab2 and PineTime software improvements and a new Pinecil micro soldering tip set. Does anyone even read these descriptions?"

---

Hello and happy April! The past few months have been relatively quiet on the surface, but there is a lot going on behind the scenes. During the past three months we have seen some improvements for the PineTab2, PineTime and PineNote, along with the announcement that the PineTab-V is back in store and the new micro soldering tip set for the Pinecil. Charlie the Pinecorn also makes his yearly appearance in the update banner, artwork made by Caffeine.   

We have been very happy with the feedback after the launch of the PineNote Community Edition. Users coming from the developer edition with Android have been able to successfully move to the new Debian firmware without any major issues (thanks Maximilian, Diederik and hrdl!). 

We'd also like to apologize as we had most of this written up around late February early March and things got busy. Thanks for waiting patiently! We're making sure to focus on getting the word out than increasing the word count from now on. 

![The April 2025 community update banner](/blog/images/AprilBanner_2025.jpg)

{{< toc >}}

## FOSDEM 2025
{{< credits "Author: Caffeine" >}}

Thank you to everyone who came past the pop-up meet-up at FOSDEM, it was fantastic to see everyone and be able to say hello. As mentioned in the previous update we weren't allocated a table this year, but we managed to meet with community members at Bar Campouce. We hope to get a table for next years event. 

![Pine64 community meetup at Fosdem 2025](/blog/images/April_2025/fosdem2025.jpg)

## PineTab-V 
{{< credits "Author: Caffeine" >}}

We are happy to announce that the PineTab-V is back in the store! Last year we reported that the PineTab-V would be going on sale in October, unfortunately this did not happen due to there being no default OS to send to the factory. Thanks to our friends over at StarFive, they have kindly built a working image to send to the factory (thank you!). The image is based on Debian with a Gnome desktop. 

Much of the hardware is working including the cameras, WiFi and GPU acceleration. One thing to note though, when the battery is lower than 8%, some hardware (specifically WiFi) will not be able to function. We suspect this to be a hardware related issue.

The current status of the PineTab-V factory image from StarFive:

* Both cameras working
* Lack of support for HEVC or MJPEG hardware decoding in Firefox.

You can find more details about the factory image [here](/blog/files/April_2025/PineTab-V_StarFive_Build_Debian_Release_Notes_v1.0.0.pdf).

## StarPro64
{{< credits "Author: Caffeine" >}}

The StarPro64 SBC will be in the store sometime in the next two weeks. The device includes an Eswin EIC7700 SoC, 32GB of LPDDR5 memory and a 20 TOPS NPU. The device supports Deepseek 7B LLM out of the box. 

You can find more extended detail on the device [in the September 2024 community update](https://pine64.org/2024/10/02/september_2024/). 

## PineTab2
{{< credits "Author: Caffeine" >}}

It has been many community updates since we have covered any software progress on the PineTab2,  That cycle is broken this month as Danct12 who currently maintains the Arch based DanctNix distribution has made some improvements.

Danct12 added U-Boot display support as well as HDMI on U-Boot. But this is yet to be upstreamed. There is also a new factory image which mainly includes package updates, the latest kernel update fixes WiFi on newer U-Boot versions.

## PineNote
{{< credits "Authors: Caffeine, hrdl" >}}

Since the last community update, there have been significant updates to the default Debian operating system. Notably a [configuration to make the pressure sensitivity and eraser work in Xournal++](https://github.com/PNDeb/pinenote-tweaks/commit/65ebea8a9d4f21741cf22a5f2beec8eb5aca567c), general user version of the [Gnome extension](https://github.com/PNDeb/pinenote-gnome-extension/commit/d8bc36f6b68c3049a5d6862ef9d0d48b6ac0dd7b), [updated kernel](https://github.com/m-weigand/linux/tree/branch_pinenote_6-12_v1) and a [new travel mode](https://github.com/PNDeb/pinenote-gnome-extension/commit/0c3d53261ab081975271a1b56f8a6dd255430fb1). The travel mode stops the PineNote from waking up when the folio case accidentally opens in a bag for example.

For users interested or who have just received their PineNote, [Caffeine](https://github.com/carbonatedcaffeine) has made a series of videos detailing how to enter Rockusb mode using the magnet method, how to flash, upgrade and recover your PineNote, and a full Debian software demonstration. You can find the video playlist [here](https://youtube.com/playlist?list=PLdVTsU3z511czt6WO_w5_MpOW52KkhQCB&si=Zh5xlBHhjuLvje6h).

### Kernel improvements

Community member [hrdl](https://git.sr.ht/~hrdl/) has been improving the overall responsiveness of the PineNote on their Arch based operating system and [improved kernel tree](https://git.sr.ht/~hrdl/linux).

This means goodbye to artifacting due to mode/waveform mismatches and hello to redrawing changes on the display on a per pixel basis thanks to new bit depth and dithering behavior. hrdl has additionally written a Python script which listens for relevant sway events and updates that can be set up per application automatically.

If users are interested in trying the Arch based operating system (which is able to be installed on the OS2 partition) there is a tutorial on [GitHub](https://github.com/hrdl-github/pinenote-arch). Users can install improved kernel on Debian by searching and choosing the latest image using `apt search hrdl`.

### Demos
* [Koreader, improved pen sensitivity and video playback demo](https://files.hrdl.eu/pn_2025-03-23-xpp_koreader_mpv.mp4)
* [Website scrolling demo](https://files.hrdl.eu/pn_2025-03-23-qutebrowser.mp4)
* [Multitasking responsiveness and obligatory bad apple playback demo](https://files.hrdl.eu/pn_2025-03-20_sway_hints.mp4)

## PineTime
{{< credits "Author: Caffeine" >}}

There has been a new update to the WaspOS reloader to add support for the BY25Q32 SPINOR flash chip found in recent batches of the PineTime. This means that the watch will no longer soft-brick. This happened when users tried to switch from Infinitime to WaspOS and back again. This is now fixed. See [our previous blog post about the topic here for more information](https://github.com/wasp-os/wasp-os/actions/runs/13102413879).

Users are able to find the new reloader artifact [here at this actions page](https://github.com/wasp-os/wasp-os/actions/runs/13102413879).

## Pinecil
{{< credits "Author: Ralim" >}}

Continuing on the theme from launching the [threaded insert tool](https://pine64.com/product/pinecil-threaded-insert-tips-set-and-adapter/), we are bringing a new set of tips. This time we are bringing out some [micro soldering tips](https://pine64.com/product/pinecil-micro-soldering-tip-set/).
Watching some of the discussions there has been demand for smaller tips that are more focused on smaller component sizes. 
So after working with the factory, we have made sample test units of the new design. As shown in the picture.

![Pinecil Tip Samples](/blog/images/April_2025/microsoldering.jpg)

These are really focused more on SMD work. Below is the tips with `0603`(Imperial) / `1608`(Metric) sized resistor for a sense of scale.

![Image of tip with SMD components for scale](/blog/images/April_2025/smallcomponents.jpg)

The tips are designed to be plug & play with the Pinecilv2. They are the same 6.2 ohms as the short tips already available for sale.
Due to the significantly smaller thermal mass, the tips heat up faster than the larger tips.

## Community content
### PineNote
Community user [Shom](https://shom.dev/) has been making some helpful and informative content on the PineNote. 

* [Q&A PineNote Review](https://shom.dev/posts/20250308_pinenote-day-one/)
* [Pine64 PineNote - first impressions on MakerTube](https://makertube.net/w/cSDcWZVjFksZsxpPx5yo8j)
* [PineNote - smoothing rough edges on MakerTube](https://makertube.net/w/w3MicEqLiVrpE1FcAvKKae)

*A really well written review with some nice feedback. We are hoping that with the next batch the user won't be required to run any u-boot commands after getting their PineNote. However, the main struggle I've encountered is from flashing the PineNote, this process can be improved in the future along with improved documentation.*

## Want to contribute to the next community update?

Do you have a cool project that you're working on you'd like to be mentioned? Is there something you're interested in that you'd like to write about related to Pine64? If you're interested, please contact us!

- Camden/CarbonatedCaffeine: 
  - @carbonatedcaffeine (Discord)
  - @endernightlord:matrix.org (Matrix)
