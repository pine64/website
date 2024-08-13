---
title: "June Update: Who likes RISC-V?"
date: "2022-06-28"
authors: ["Lukasz Erecinski"]
categories:
  - "pinebook-pro"
  - "pinenote"
  - "pinephone"
  - "pinephone-pro"
  - "risc-v"
tags: 
  - "pinebook-pro"
  - "pinephone"
  - "pinephone-pro"
  - "risc-v"
cover: 
  image: "JuneUpdate-1024x576.jpg"
images:
  - "/blog/images/JuneUpdate-1024x576.jpg"
---

![](/blog/images/JuneUpdate-1024x576.jpg)

This month we reveal that we are working on a powerful and affordable RISC-V single board computer, discuss PineNote’s huge software improvements and provide updates on PinePhone, PinePhone Pro and Pinebook Pro’s availability. I am also taking the opportunity to let you know that, after 6 years of holding PINE64’s community manager post, I’ll be resigning from my position shortly, once PINE64 EU launches next week; Marek Kraus will gradually be taking over my responsibilities.

There is much to cover this month, so let's get cracking.

You can watch the synopsis of this month’s community update on YouTube (embedded below) as well as on [Odysee](https://odysee.com/@PINE64:a) and [PeerTube](https://tilvids.com/accounts/pine64tilvids/video-channels). To stay up-to-date with PINE64 news make sure to subscribe to this blog (subscription widget at the bottom of the webpage), follow the [PINE64 Telegram News channel](https://t.me/PINE64_News), the [announcements channel in Discord](https://discord.gg/pine64) as well as our [Twitter](https://twitter.com/thepine64) and [Mastodon](https://fosstodon.org/@PINE64).

I’d like to thank [dsimic](https://github.com/dragan-simic), [Alex](https://twitter.com/AlexRob12252696) (clover) and [PizzaLovingNerd](https://www.youtube.com/channel/UCmGcm7dhEjS9CIOsOOv8y6w) for their contributions to this community update.

**N.B.** Comments on the blog post need to be in English and follow our [Community Rules and Code of Conduct](https://forum.pine64.org/showthread.php?tid=13209).

**TL;DR**

- Housekeeping
    - Read JF’s post about using the Quartz64 as a NAS
    - QuartzPro64 developer coupons have started going out - devs, check your inbox
    - New PineTalk is out
    - Pinebook Pro available in July - a post on PCB revision coming soon
    - PINE64 EU launching after (over) a month long delay
    - Marek becomes community manager at PINE64
- Who likes RISC-V?
    - We’re making a powerful and affordable RISC-V model-A type SBC
    - SBC in final layout phase 
    - Comparable specs and price point to Quartz64, but with RISC-V SoC
    - Be the first to solve the riddle and receive our first RISC-V SBC
- PinePhone (Pro)
    - PinePhone and PinePhone Pro are back in stock - shipping mid July
    - Installing community modem firmware is now easy
    - You can play Doom on PinePhone (Pro)’s modem!
    - Camera developments and major improvements to Megapixels postprocessing
- PineNote
    - Linux on the PineNote is now in good shape
    - Major developments for the e-paper display - work by Smaeul on the driver detailed
    - It is now possible to write using EMR pen on the PineNote running Linux in a standard Debian installation
    - Showcase of smooth (quickly appearing) handwriting

{{< youtube id="lqERznpxsPE" >}}

**Video synopsis of the June Update**

## Housekeeping

Earlier this month JF wrote a guest post in which he showcased [the Quartz64 model-A’s functionality as a NAS](https://www.pine64.org/2022/06/03/my-diy-low-power-6-ssd-nas-based-on-the-quartz64-arm-board/). The post details retrofitting a standard ATX computer case to fit a Quartz64 model-A and outfitting the setup with 6 SSDs. JF also provides general guidance to reproduce the setup and offers a handful of benchmarks of the NAS’ performance. While JF used Manjaro as the basis for his NAS, I feel this is a good time to let everyone know that [Debian Armbian builds for the Quartz64](https://github.com/armbian/build/releases/) are now available for download. I know that many people are in favour of Debian’s stability when it comes to building something such as a NAS, and therefore I am thrilled to see that now it is available as an option on the Quartz64. I should also mention that I expect to see many more OS builds available for Quartz64 and SOQuartz shortly.

![](/blog/images/case-7-768x1024.jpg)

**JF's NAS - via [guest blog post](https://www.pine64.org/2022/06/03/my-diy-low-power-6-ssd-nas-based-on-the-quartz64-arm-board/)**

Staying on the subject of single board computers, the QuartzPro64 developer edition coupons will start going out shortly. If you’ve signed up to purchase a unit, please keep an eye on your inbox. If you receive an email with a coupon code, you will have limited time to complete the purchase. The email will also include the link to the page where you can complete your QuartzPro64 purchase.

Last month I had the pleasure of bringing the much anticipated news that Pinebook Pro is re-entering production. This month I am glad to confirm that the Pinebook Pro is already in production, and we expect units to be delivered from the factory sometime in July. We will make sure to notify you once stock is available on social media and in the news channels. Dsimic will soon be publishing a guest post about PCB changes made to this production run, so keep an eye out for his impressions in the coming days.

![](/blog/images/DSC01735-1024x768.jpg)

**A peek at the Pinebook Pro's 2022 PCB - via dsimic**

In case you missed it, a [new PineTalk episode](https://www.pine64.org/podcast/) was released at the beginning of this month. In this month’s episode, Brian and Justin covered topics covered in the May community update and discussed their experience with open and security-focused Android ROMs. Justin also talks about an idea he pitched to me concerning a smart-speaker. The duo also promised to read and respond to the audience's questions, so make sure to bombard them with [emails](mailto:pinetalk@pine64.org), [toots](https://fosstodon.org/@talkpine) and [tweets](https://twitter.com/TalkPine). I too think that the show deserves a higher degree of community engagement. If you haven’t yet added PineTalk to your RSS feed, then here is a handy link: [https://www.pine64.org/feed/mp3/](https://www.pine64.org/feed/mp3/).

PINE64 EU is finally ready to open its doors for business. I don’t have a specified launch day yet, but it will be next week - it largely depends on how quickly I manage transport, unpack and inventory everything. I once again wish to apologise for the delay in the store’s opening - I ran into issues with EU regulation that needed to be addressed. Suffice to say, relevant institutions take their sweet time with every piece of submitted paperwork; in my case, it took some 4 weeks for a complete review. Anyways, here is what will be available for purchase on day one: PinePhone Pro, PinePhone, the Pinecil, PinePhone (Pro) keyboard case, protective cases for the phones as well as the PineTime. As I mentioned in the past, this is just the beginning, and the aim is to have the EU store grow its selection to include other hardware in the future. I should also mention that customers will be able to select from Mobian, Manjaro and postmarketOS to be installed on their PinePhone (Pro). I also have a small surprise which will be announced on the day of the store’s launch, so make sure to follow PINE64 EU on [Twitter](https://twitter.com/pine64eu), [Mastodon](https://fosstodon.org/web/@pine64eu) and [Telegram](https://t.me/pine64eu) (news channel, not a chat). 

Lastly, at the beginning of next month, as the EU store’s launches, I will give up my position as community manager at PINE64. But fret not, I am leaving you in very capable hands - [Marek Kraus](https://twitter.com/gamelaster) will be taking on the role of steering the community in the future. Marek has been a part of the project for a long time and played a crucial role in PINE64’s success. He is highly personable, cool headed and, unlike me, also very technically skilled (including hardware and software). This means that not only is he able to communicate with contributors, engineers and partner project developers, but he is also able to speak their language. I am handing down this post to Marek with complete confidence and I know that he’ll do an incredible job. As for myself, while the PINE64 EU will be my core focus from now-on, I will remain a part of PINE64 and the community - I’m not going anywhere. I’ll also keep on writing the updates, hosting quarterly Q&As, engaging with the community, etc. The transition of responsibilities between Marek and I will be gradual and fluid; it will take time. Congrats Marek and take good care of my beloved project :) 

## Who likes RISC-V? 

We have hinted at this for some time, and many of you knew it would become a reality eventually: we’re now in the final layout phase for a powerful, yet affordable, RISC-V single board computer. I need to be a bit cagey about what I write, partly because I want you to solve the riddle at the end of this section, and in part because not all information has been set in stone and disclosed publicly by the SoC vendor. Before I get into some of the details I’ve been allowed to disclose, here’s the spiel: the board will premiere in our signature model-A form factor, feature CPU performance which falls somewhere in the neighbourhood of the Quartz64, offer plenty of IO, and sport a price-tag similar to that of the Quartz64. In a nutshell, a Quartz64 model-A type board but with a RISC-V SoC. Sounds good? Then keep on reading.

![](/blog/images/Ronin-Tanto-.png)

**PCIe is important to industry clients; ROCKPro64 in RoninDojo Tanto - via [RoninDojo](https://ronindojo.io/en/tanto)**

The board will be available in two configurations, with 4GB and 8GB of RAM. Similarly to the Quartz64 model-A, the RISC-V board will feature both USB 3.0 and a PCIe slot. Having an open-ended PCIe slot on a board offers it a high degree of versatility, which we know is something that developers, end-users and industry clients want. The SoC features two native Gigabit Ethernet NICs, but I am not certain if there are plans to expose both of them on the PCB - this hasn’t been determined yet. Regardless, I figured it is worth mentioning it as an available option. The SoC has Imagination Technologies’ BXE-2-32 GPU for which the source code ought to be made available soon. Imagination Technologies have recently come through on their promise of open sourcing their other GPUs, so there is no reason to believe that it will be any different in the case of the BXE-2-32. Since the formal introduction of the board to the market is still a few months away, the code may very well be available on launch day.

![](/blog/images/Q64Main-1-1024x686.jpg) ![](/blog/images/PINEA64og.jpg) ![](/blog/images/ROCKPro64.jpg)

**The model-A SBC form factor should be familiar to everyone (pictured: Quartz64 model-A, PINE A64(+), ROCKPro64)**

The last thing I want to communicate is that the RISC-V platform is something we wish to pursue in parallel to our well established ARM-based hardware. While we don’t have set-in-stone plans regarding the platform, be on the lookout for more RISC-V hardware offerings from now through 2023. We have some candidate devices for a RISC-V conversion and ideas for future iterations of hardware based on the architecture, which is something I believe many of you will find exciting. In short: we have made a decision to commit to the RISC-V platform. 

I’ve decided to keep the name of the board out of this introductory post so that you can decipher the riddle below. As we’ve done in the past, the first person to correctly decipher the name of the board will receive the first unit that rolls off the factory floor. Your guess needs to be filed in the comments section; guesses posted elsewhere don’t count. Don’t worry if your guess doesn’t immediately show up in the comments - it needs to undergo moderation. All comments are time-stamped, so there is no chance of being leapfrogged by someone else submitting their guess after you. I’ll have more information about our RISC-V board for you next month.

**Victoria Line Station**

I sing, act and dance

celebrated by them all

I never climb my stage

but I sometimes fall

  

In the sea I dwell

and in every magic book 

By heaven!

adding 64 is all it took

  

On my stage I shine

and when I feel truly blue

then there’s nothing

This is the final clue

## PinePhone (Pro)

Let me open with a short update on Pinephone and PinePhone Pro’s availability; we currently expect to receive the next production-run in approximately mid July at which point shipping will commence. At the time of publishing this post, both [PinePhone and PinePhone Pro](https://pine64.com/product-category/smartphones/) should now be listed as being in-stock.

As most of you are aware, the PinePhone (Pro)’s Quectel EG25-G modem is effectively its own single-core Arm computer running a closed Linux-based firmware. Over the past 2 years the community put in an immense effort to improve and adapt the IoT modem’s firmware to better serve the PinePhone (Pro). Work by [Biktor](https://twitter.com/biktorgj) and [Konrad](https://twitter.com/konradybcio), as well as that of other contributors, opened the modem up to tinkering and thereby also to alterations and improvements to its software. Before I write another word, I need to underline that it is [PINE64’s and Pine Store’s position](/documentation/General/PineModems#pine64_position_on_alternative_firmware) that the licensed proprietary firmware on the modem should not be tampered with, and it is my duty to notify you that altering the modem’s firmware may violate your local laws, which in turn can have very real consequences. Therefore, please consider the following to be a progress report and a showcase, which I find to be fitting well with the community spirit of this blog, but it is not an enticement to use alternative firmware on your PinePhone (Pro).

Until recently it was very difficult to switch from the closed Quectel firmware to the much more [open firmware by Biktor](https://github.com/Biktorgj/pinephone_modem_sdk/releases/tag/0.6.7). This community firmware contains no binary blobs in the userspace, and significantly reduces the modem’s power consumption and heat output by running the SoC at just 100Mhz instead of the default 400Mhz/ 800Mhz. Until recently, installation of the community firmware required you to have a firm understanding of the command line and ADB. Now, however, the process has been completely streamlined and achievable via fwupd, and from a GUI no less. I decided to try the process on my own hardware running DanctNIX Arch Linux. The process is as simple as opening up the GNOME software centre, searching for “Firmware” and downloading the GUI utility. Upon launching the Firmware utility the Quectel modem is automatically listed as eligible for firmware updates. Tapping the modem provides information about the current vendor firmware, vendor ID as well as many other information. Scrolling down reveals available releases from Biktor. The installation is as simple as tapping the chosen release, reading the precaution popup, and agreeing to proceed with the installation. The installation takes approximately 10 minutes, and at the end of which the phone needs to be rebooted. 

{{< youtube id="aokclNgnIbE" >}}

**Installing modem firmware using GUI - via [Martijn Braam](https://www.youtube.com/c/MartijnBraam)**

I have now run Biktors firmware for a handful of days and I am very pleased with its performance. I can tell that the phone as a whole runs considerably cooler and the additional [quirks it offers](https://github.com/Biktorgj/pinephone_modem_sdk/#todo-in-no-particular-order) are fun to toy with. I also haven’t experienced any issues with LTE, GPS, making and receiving calls nor with sending or receiving SMS. If anything, on the default firmware I would sometimes experience issues with receiving calls (usually after a few days of the PinePhone running) but as of today, my PinePhone running the community modem firmware hasn’t dropped a single call - at least, not to my knowledge. But Biktor’s firmware has another tangible benefit over its closed-source counterpart: namely, it is more secure and not susceptible to the [malware first distributed in December](https://www.pine64.org/2021/12/15/december-update-a-year-in-review/) of last year. This is a major boon, especially to all those who are getting a PinePhone (Pro) strictly for privacy and security purposes.

But an open firmware opens an avenue for doing a wide variety of things, some of which are not necessarily related to telephony at all. Indeed, some applications may not even be useful, and only serve as an illustration of what can be achieved when running open source software. One such example is running Doom on the modem, because, ya’ know, everything needs to run Doom. Biktor put together [a special (pre)release](https://github.com/Biktorgj/pinephone_modem_sdk/releases/tag/0.6.7-Doom) of the firmware which bundles X11, a VNC server and Chocolate Doom for those of you who wish to try this out. Below you’ll find a short video showing Doom running on the PinePhone’s modem. 

https://www.youtube.com/watch?v=GvLlP6BEPPk

**Doom on PinePhone's modem - original video [via Biktor on Twitter](https://twitter.com/biktorgj/status/1538407447873916928)**

While I can neither recommend nor suggest flashing this community-built modem firmware, I privately think that it clearly serves a purpose and has an application if you reside in a region where unlicensed modem firmware is permissible. From what I can tell, the firmware offers many benefits to PinePhone (Pro) users and no obvious drawbacks. I should also mention that if you attempt flashing your PinePhone (Pro)’s modem firmware and something goes wrong, then neither we nor Biktor bear any responsibility for it. Lastly, I know that Biktor would appreciate help developing this firmware further, making it even more secure and its feature-set more robust, so if you are interested in this project then please consider donating via [ko-fi](https://ko-fi.com/biktorgj) or [liberapay](https://liberapay.com/biktorgj/donate), or contribute code.

Lastly I’d also like to mention that the cameras on both the original and Pro versions of the PinePhone have received some major improvements. As I reported [last month](https://www.pine64.org/2022/05/31/may-update-worth-the-wait/), thanks in large part to [Megi](https://xnux.eu/)’s efforts, the camera on the PinePhone Pro’s is now functional - although it will take time for it to be incorporated into an application like [Megapixels](https://git.sr.ht/~martijnbraam/megapixels). For the past month Megi has been working on a calibration application for PinePhone Pro’s cameras. In his [recent blog post](https://xnux.eu/log/#070), Megi writes: _“I started writing a GTK4 based app that connects to the Pinephone Pro over WiFi and allows to modify parameters inside the sensor and ISP, while monitoring the effects of various correction in real time, inspect histograms for various color components, and in general to experiment with the cameras and the ISP fairly painlessly. This should help with the calibration process as much as possible“._ The application also allows live mjpeg streaming over HTTP to as a convenience feature. Megi also explains that he is putting a lot of time into the design of the UI controls and CPU optimisation, so that the application is both cognitively ergonomic and only utilizing a single core for a lag-free experience. Ultimately, the goal of his efforts are to make it easier for end-user applications, such as Megapixels, to properly calibrate and incorporate his code. 

https://www.youtube.com/embed/H-S8F5zAUAY

**Streaming video via the PinePhone Pro application app - via [Megi's blog](https://xnux.eu/log/#070)**

On the subject of Megapixels, Martijn Braam released [a video](https://youtu.be/Ypc3pfzSajo) showcasing new post-processing modes that will soon be included into Megapixels. Users will now be able to manually select from three different post-processing modes: the original mode (currently available), single and stacked. The new post-processing modes are not only much faster, but they also result in much nicer, richer and more natural photographs on the original PinePhone. Taking photographs is one of a smartphone's core features, and the picture quality on the original PinePhone has just received a major ‘bump’. This is something all PinePhone users ought to be looking out for.

![](/blog/images/PP-old-processing-1024x768.jpg) ![](/blog/images/PP-new-processing-1024x768.jpg)

First image: old camera post processing / Second image: new camera post processing - via [Martijn Braam on Twitter](https://twitter.com/braam_martijn/status/1540777306708246528)

## PineNote

It has been some time since I wrote about the PineNote. This is partly because much of the work at this point centers around the e-paper display. But let me back up a little bit. The PineNote has benefited from all the progress made on the Quartz64 platform. In case you missed it, I described Quartz64 progress back [in March](https://www.pine64.org/2022/03/15/march-update-introducing-the-quartzpro64/) and in last [month’s update](https://www.pine64.org/2022/05/31/may-update-worth-the-wait/); much work has gone into making the RK3566 platform functional, and with patches being upstreamed a sizable portion of the core functionality is now available in mainline Linux. In other words, the basis upon which the PineNote is built is in good shape. However, the PineNote is not a single board computer and it also doesn’t rely on a traditional video output. The first breakthrough for the PineNote came in [January of this year](https://www.pine64.org/2022/01/15/january-update-more-news/), when developers managed to initiate the e-paper display under non-BSP Linux. Since January much of the work concerning the PineNote centered around making the e-paper display more usable. Whilst the PineNote could display images for some time now, the refresh rate remained very low thereby limiting its scope of usability. The other issue with a very slow refresh rate is that it makes it impossible to write on the PineNote - negating one of the devices main features and selling points. 

{{< youtube id="PQiHOjIUTiE" >}}

**DOOM on PineNote - via [Danct12](https://www.youtube.com/c/danct12cp)**

But this is about to change. Recent breakthroughs by [Smaeul](https://github.com/smaeul/) and [Maximilian](https://github.com/m-weigand), as well as other developers, bring us much closer to realising the dream of a fully open and well supported e-paper device. The PineNote can now use the A2 waveform which allows for fast transitions between black and white on e-paper; for those who like me are uneducated in this matter, you can think of it as a very fast local refresh rate, for instance just under the tip of the stylus. But that’s not all. Smaeul has also been working on a global refresh mode (entire panel, not local), which only refreshes ‘damaged’, or altered, sections rather than the entirety of the panel. As he explained, this leads to a dramatic reduction in memory bandwidth requirements. Referring to the video I am embedding below, Smaeul writes: _“ Global refreshes with diff mode turned off for clarity (...) I've configured the window registers so only the damaged portion of the screen (the flashing part) gets read from DRAM. (...)_ We could add some heuristic to switch to a global refresh if a large enough portion of the screen is damaged. Since global refreshes only use 2 buffers instead of 3, this would minimize the peak memory bandwidth_”._

{{< youtube id="wDutl2TCEko" >}}

**Video showcasing the A2 waveform in Smaeul's driver - video shared in chat**

I also had an opportunity to talk to Maximilian, who showcased his build of Debian bookworm/sid with GNOME running under Wayland. This build runs a slightly modified version of Smaeul’s e-paper ebc driver with tweaks to the system configuration. Maximilian explained that his tweaks reduce artifacts and auto refresh, and force the driver to only output black and white pixels so that the A2 waveform can be used without dealing with colors and text rendering issues. The result? Smooth pen input and, from what I can tell, near flawless writing tested for example in a default and unchanged LibreOffice, which ships with Debian. 

As you can see in the video from the user _hrdl_ below, writing in a regular Linux on the PineNote (in _Xournal++_ with just two minor patches and configuration tweaks) does not only look viable but downright great. It is one thing to describe it and a different thing to see it, so below I am attaching the example video of handwriting using an EMR Pen in a pretty standard Linux installation on the PineNote.

{{< youtube id="qT81L_lcFEI" >}}

What the PineNote now needs is a default Linux distribution and user interface to ship. The OS doesn’t need to be polished, nor flawless, all it needs to be Linux with all the device’s core capabilities enabled. Marek and I will be talking to PineNote developers and partner projects in the coming weeks in a hope to work out an arrangement so that the PineNote can finally ship with Linux preinstalled. Here is the take-away from this section: we (and by 'we', I actually mean the devoted developers) are getting closer to realising the dream of an e-paper device running regular Linux, with a regular desktop, which allows you to do regular computational things on the device.

That is all for this month’s update, catch you all in July!
