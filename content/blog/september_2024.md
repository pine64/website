---
title: "September Update: Check Your Notes"
date: "2024-10-02"
authors: []
categories: 
  - "community"
  - "news"
  - "pine64-community"
tags: 
  - "ironos"
  - "pinecil"
  - "pinephone-pro"
  - "pinephone"
  - "pinetime"
  - "pinenote"
  - "pinetab-v"
  - "bl702"
  - "quartz64"
  - "oz64"
  - "starpro64"
  - "quartz64-zero"
  - "pinedio"
cover: 
  image: "September_Update_Check_Your_Notes.png"
images:
  - "September_Update_Check_Your_Notes.png"
summary: "A new community update! New hardware to announced and previous hardware to return!"
---

Hello and welcome back to another Pine64 community update! The community has been hard at work behind the scenes with development of new hardware along with bringing back some previously manufactured products. Of course, we will also go over the current state of our devices as well. And just before you ask, yes it is October. Most of the work for this update was done last month.

We'd also like to thank you for your patience, it's been difficult with a most of us having limited time to work on these updates. We will continue to write and release these updates as fast as we can and continue to become more consistent again like we used to be. 

Thanks!

![](/blog/images/September_Update_Check_Your_Notes.png)

{{< toc >}}

----

## Updates

### New products announcements

#### StarPro64

{{< credits "Author: Lukasz" >}}

![starpro64](/blog/images/September_2024/starpro64_1.jpg)

![starpro64](/blog/images/September_2024/starpro64_2.jpg)

The PINE64 project and PineStore have been committed to bringing more devices based on the RISC-V architecture since three years ago. Since 2021, several devices including the Pinecil — PINE64's most popular hardware — have adopted this architecture. While the Ox64 may have been the first Linux-capable single-board computer (SBC) technically, the first full-fledged PINE64 RISC-V SBC was the Star64, which laid the foundation for the PINETAB-V tablet introduced last year alongside its ARM sibling, the PineTab2. Although significant development is still needed for the JH7110, interest in the platform and RISC-V development in general remain strong, with new releases from projects like DietPi and NuttX.

However, PINE64 and PineStore's commitment to the RISC-V platform goes far beyond existing products. As a testament to this, we are thrilled to introduce you to the newest RISC-V family member in the PINE64 hardware line-up – the StarPro64. Following the convention of more capable hardware in the PINE64 catalog, the StarPro64 boasts a more powerful system-on-chip (SoC) at its core than its non-Pro older sibling. It is based on the EIC7700X, an upgraded version of the EIC7700. The CPU speed has been increased from 1.4 GHz to 1.8 GHz, while the NPU performance has been boosted from 13.3 TOPS to 19.95 TOPS.

The StarPro64 uses the model-A board format, seen in earlier products such as the Pine A64, the popular ROCKPro64, and indeed also the Star64. The layout of the StarPro64 is very similar to the Star64, with all key I/O ports in the same positions. This includes the dual Ethernet ports, digital video output port, and 12V power input at the rear of the board. The front features a power button, as well as USB 2.0 and 3.0 ports, in their usual model-A positions. Additionally, the board has a full GPIO header, a 4x PCIe lane, an eMMC slot, onboard WiFi/Bluetooth, and heatsink mounting holes matching the layout of the ROCKPro64 one-for-one.

The StarPro64 will be available in three memory configurations: 8GB, 16GB, or 32GB of LPDDR5 RAM. While a firm availability date has not yet been provided yet, it is expected to reach the PineStore sooner rather than later. The first prototype, featuring 32GB of RAM, arrived in late September and we’re pleased with how it turned out. If the early evaluation board passes testing, developers will start receiving their units in the coming weeks. While we’re keen to get production going so you can get your hands on a unit, we’ll patiently wait for developer feedback - positive feedback from the community will lead to full-scale production.

The StarPro64, and more specifically the Eswin EIC7700 SoC, is an exciting platform that may become a foundation for future devices. PINE64 hopes that the development and enthusiast community will embrace this SoC and the StarPro64, as it could be a gateway to a range of affordable RISC-V devices that many of us are eager to see. For instance, you can even connect a PinePhone Pro LCD and touch panel to the StarPro64 — pretty cool, right? For those interested in a deeper dive into the SoC, I encourage you to check out a detailed article on [CNX Software](https://www.cnx-software.com/2024/06/19/eswin-eic7700x-quad-core-risc-v-soc-embeds-19-95-tops-npu-for-edge-ai-vision-applications/).

The StarPro64 board PCB has already been sent out for fabrication along with the prototyping board back in September.

#### Oz64

{{< credits "Author: Lukasz" >}}

![oz64](/blog/images/September_2024/oz64.png)

The StarPro64 is, however, not the only SBC introduced this month. The [Oz64](/devices/oz64/) is a development board based on the **SG2000** MCU and equipped with **OIC8800 Wi-Fi/BT** chip. It's an interesting chip that embeds multiple cores: two main cores (T-Head C906 64-bit RISC-V cores and an ARM Cortex A53 64-bit RISC CPU, only one of them can be used at a time), another T-Head C906 RTOS core and a 8051 8-bit core. They are supported by 512MB of RAM. The board also provides a microSD card slot, an eMMC connector and a USB2.0 type-A host port. It is important to note that the Oz64 is not a replacement for the Ox64, which has proven itself to be popular and will remain in PineStore’s hardware line-up for the foreseeable future. Production of the Oz64 is already completed and it is currently undergoing Q&A testing. Once testing will be completed the SBC will find its way into the Pine Store in the coming weeks or months. Expect an announcement on social media platforms and in the chats. 

The Oz64 is expected to be available in the next few weeks or months.

#### Quartz64-Zero

{{< credits "Author: Lukasz" >}}

Following the two RISC-V centered SBCs there is also an announcement pertaining to our Arm Quartz64 device-line. 
The Quartz64-Zero is a lower cost version of the Quartz64 that is based on the RK3566T (Quad A55 @1.6Gh) and comes with 1GB memory. 

![quartz64-zero](/blog/images/September_2024/quartz64-zero.jpg)

All Quartz64 software options should work right out-of-the box on this board without any major optimizations. Noteworthily, the PCIe port on the Quart64-Zero is the same as the one on the Raspberry Pi 5. As such the PineStore sees this low-cost board as suitable for commercial project applications and guarantees the availability of the board until at least 2028. It is hence an LTS board. 

The Quartz64-Zero is already available for $15 on [the store](https://pine64.com/product/quartz64-zero-single-board-computer/).

### PineNote

{{< credits "Authors: Ralim, CarbonatedCaffeine" >}}

The PineNote is coming back; there are now plans formalized for a production run of these units. I do not (yet) have a launch date target as behind-the-scenes the Pine Store team are still working on all things production.

What has happened behind the scenes has been a very long discussion with TL around if a new batch can happen. There has been huge amounts of work done by Maximilian tireless working away at making a stable Debian distribution to run on these devices. I'm very acutely aware of the silence that has surrounded this device, this was not by design but rather due to lack of updates to share publicly as things slowly progressed. I took my unit to FOSDEM this year to be able to show of the progress that has been made on the OS front, and to be able to talk about the product still continuing.

The PineNote was stuck in a chicken-and-egg situation where because of the very high cost of manufacturing the device (ePaper screens are sadly still expensive), and so the risk of manufacturing units that then didn't have a working Linux OS and would not sell was huge. Maximilian's work in the background has pushed the envelope on this and resulted in not only a bare-bones capable OS but a genuinely daily-usable system that "just works".

This is excellent as it also moves the target audience from _developers_ to every day users. You should be able to power on the device and drop into a working Gnome experience.

The hardware of the PineNote has taken some feedback from the early developer units, we are aiming to have the old pen replaced by a passive (no charging) unit that still features the same buttons. 

#### Operating System Progress

Currently the PineNote firmware is being developed by [Maximillian](https://github.com/m-weigand) and is [based on Debian](https://github.com/PNDeb/pinenote-debian-image/releases/tag/trixie-v20240513_v2).

![pinenote](/blog/images/September_2024/pinenote-1.jpg)

The images are using the Gnome desktop and includes some extensions specific to playing well with e-ink displays. 

![pinenote](/blog/images/September_2024/pinenote-2.jpg)

If you currently own a PineNote, you can find these images [here](https://github.com/PNDeb/pinenote-debian-image/releases/tag/trixie-v20240513_v2). If you have time, any testing and feedback on these will be valuable.

##### Mobian

[Julian Fairfax](https://github.com/julianfairfax/images-build) has created an initial port of Mobian for the PineNote. It currently boots, but it isn't as usable as it could be using Phosh. It's a good starting point. 

##### PostmarketOS

"There were also attempts to port PostmarketOS to the Pinenote. The current state needs to be tested:" 
https://wiki.postmarketos.org/wiki/PINE64_PineNote_(pine64-pinenote)

#### Call For Contributors!

We need help getting the Debian image into best shape for the release.

* Issues: https://github.com/PNDeb/pinenote-debian-image/issues
* Nice videos would be very appreciated
* Join/ask in the PineNote chat if you are willing to help!

### PineTab V
The PineTab V is returning for another production batch in October similar to the PineNote, there are no changes from the original batch.

The device will be in stock around mid/late October. An announcement will be made when it drops in the store.

### PinePhone Pro

{{< credits "Author: CarbonatedCaffeine" >}}

The PinePhone Pro switched its default operating system from Manjaro at the end of 2023 to Adam Piggz's port of Sailfish. There have been a number of updates since the PinePhone Pro was mentioned in a community update. 

During the end of 2023 commits were made to add [functionality to wake the phone using the modems RI pin](https://github.com/sailfish-on-dontbeevil/kernel-adaptation-pinephonepro/commit/e9130550b833bb69c98c80176f1f3dcb3d35e33e). In addition to [adding the config to support usage of Waydroid](https://github.com/sailfish-on-dontbeevil/kernel-adaptation-pinephonepro/commit/da9996ad5077924abe5e0d84a505ad9ba2debbc7). 
Then recently in early 2024 Adam [fixed call audio routing](https://github.com/sailfish-on-dontbeevil/droid-config-pinephone/commit/4cb2796e56063cb04d0493c1afeee87abe4a997e). 

### PinePhone

{{< credits "Authors: JF, CarbonatedCaffeine" >}}

Good news for PinePhone users!

- The WiFi chip used in the PinePhone (rtl8723cs) [recently got mainline support](https://lwn.net/Articles/960633/) in early 2024.
- [Dsimic](https://github.com/dragan-simic) added [trip points for the GPU to the SOC DTSI into mainline](https://git.kernel.org/pub/scm/linux/kernel/git/sunxi/linux.git/commit/?id=89f1a037e97c), preventing possible but unlikely overheating damage to the A64.

Another patch added a mount-matrix for the accelerometer into mainline, which fixes inverted accelerometer behavior. 

### Pinecil / IronOS

{{< credits "Author: Ralim" >}}

1. Stability
2. Timer weirdness
3. BLE quirks
4. New screen driving / GUI handling

#### Stability

IronOS has had a rather slow development cycle on my side of things due to lack of time. The community around the project has been helping immensely however, which has kept things going. One aspect of this for the Pinecilv2 is that the newer release and onwards should have improved stability for the temperature regulation.

#### Timer weirdness

There is a bit of a trifecta of issues going on that caused some of the temperature issues; the timer hardware in the BL702 chip being used _occasionally_ doesn't trigger an interrupt. This causes things to go out of whack as the temperature sensing and the tip drive get out of sync. In the prior release these were occurring fairly frequently but after adjusting some of the timer settings they were reduced.

When investigating this, one of the issues uncovered was that it _appears_ to be related to BLE support, as removing BLE entirely from the firmware does prevent these issues from showing up. I can't conclusively say that the BLE firmware is to blame as there is a fair bit of churn when that is toggled on/off when building the firmware. However its likely something to do with its hardware or software requirements that was the root cause here.

The newer IronOS software detects when this has occurred and recovers more gracefully, so there shouldn't be any real impact to tip temperature.

#### New Screen Driving / GUI Handling

In additional news, this will not effect any users, but the entire UI rendering code has been updated. The code is moving to being a non-blocking style of rendering to allow separating any logic around what is going on from drawing the display.
The goal is that this will allow for full bluetooth remote control of the device if desired (will be Opt-In of course due to safety). This could be used for other devices to be used as a larger display, and using them to start/stop the device.

#### New from Ralim

{{< credits "Author: Ralim" >}}

While I do not have much to say about things I've been working on _yet_ I do want to note that there are projects that I'm working with Pine Store to see if they are viable. Nothing concrete yet as still unsure on financial & technical viability yet but some things are taking shape.

### Quartz64/RK3568

A few patches from [dsimic](https://github.com/dragan-simic) are now merged in Linus' tree:

- [arm64: dts: rockchip: Fix the DCDC_REG2 minimum voltage on Quartz64 Model B](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=d201c92bff90f3d3d0b079fc955378c15c0483cc)
> Correct the specified regulator-min-microvolt value for the buck DCDC_REG2
regulator, which is part of the Rockchip RK809 PMIC, in the Pine64 Quartz64
Model B board dts.  According to the RK809 datasheet, version 1.01, this
regulator is capable of producing voltages as low as 0.5 V on its output,
instead of going down to 0.9 V only, which is additionally confirmed by the
regulator-min-microvolt values found in the board dts files for the other
supported boards that use the same RK809 PMIC.
  
- [arm64: dts: rockchip: Add GPU OPP voltage ranges to RK356x SoC dtsi
](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=2e1fae80023a38ea03dfca3eab65b3b46617ef3b)
> Add support for voltage ranges to the GPU OPPs defined in the SoC dtsi for
Rockchip RK356x.  This is, for example, useful for RK356x-based boards that
are designed to use the same power supply for the GPU and NPU portions of
the SoC
  
- [arm64: dts: rockchip: Update GPU OPP voltages in RK356x SoC dtsi](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=eb665b1c06bcaf16df10018550d8f467ed4b2887)
> Update the values for the exact Rockchip RK356x GPU OPP voltages and the
lower limits for the GPU OPP voltage ranges, using the most conservative
values (i.e. the highest per-OPP voltages) found in the vendor kernel source
  
### PineTime

{{< credits "Author: JF" >}}

When I'm browsing the web or reading chat rooms, I often come across interesting posts and messages: a new version of a PineTime related project, a nice blog post or social media post, a new idea, etc.

I'm happy to share in this post some of the links and information I've curated over the last few months!

#### PineStore announcement: small hardware change

TL informed us recently that the SPI flash memory chip installed in the PineTime (XTX XT25F32B) is EoL (End Of Life) and that it will be replaced by another chip (BY25Q32ESWIG) for the next production batch of the PineTime.

This new chip behaves exactly the same than the old one, so very few code changes are expected. The most obvious change consists in supporting the chip IDs of the new module that are different from the old one. Other than that, both the new and old chip support the same command over the SPI bus.

We've already implemented those changes in [the bootloader](https://github.com/InfiniTimeOrg/pinetime-mcuboot-bootloader/pull/12) [v1.0.1](https://github.com/InfiniTimeOrg/pinetime-mcuboot-bootloader/releases/tag/1.0.1) and in [InfiniTime](https://github.com/InfiniTimeOrg/InfiniTime/pull/2097) [v14.0.1](https://github.com/InfiniTimeOrg/InfiniTime/releases/tag/1.14.1).

I've already provided these versions to the factory so they can start producting PineTime based on this new hardware. Note that you don't need to update your current PineTime to those patch versions since they only bring support for this new chip.

I strongly suggest developers from other PineTime firmware to check if their code need some changes to support this new hardware revision!

#### InfiniLink

[InfiniLink, the companion app for iOS](https://github.com/InfiniTimeOrg/InfiniLink) made a lot of progress since [Liam](https://github.com/liamcharger) took over the project a few months ago.

InfiniLink now provides a new improved UI and supports the external resources (that contain fonts and pictures for watch faces in InfiniTime) and the weather and also integrates with Apple Health.

![infinilink](/blog/images/September_2024/infinilink.png)

InfiniLink 1.0.2 is available on [the App Store](https://apps.apple.com/us/app/infinilink/id1582318814) and the newest version 1.1 is available on [Testflight](https://testflight.apple.com/join/B3PY5HUV), the platform that allows iOS developers to publish beta versions of their software. It'll be made available in the official App Store when a few bugs and crashes will be fixed.

Liam told me he doesn't have specific plans in mind for the future, but definitely would like to create a macOS app that runs on both Apple Silicon and Intel Macs. To be continued !

#### Blog posts about the PineTime

While browsing the web, I sometimes happen to find blog posts about PineTime and its ecosystem. Here are the posts that I would like to mention.

The [first one titled "Programmable watches"](https://decentnet.github.io/blog/20240218-programmable-watches.html) details a few smart watches that can be reprogrammed by the user. The PineTime is mentioned among other hackable smart watches like the Lilygo TTGO T-Watch and the Bangle.js. It's great to see that there are many options when it comes to hackable and open source smart watches!

In [second one titled "Fun with PineTime Smart Watch"](https://wrily.foad.me.uk/fun-with-pinetime-smart-watch) Julian reflects on the idea to use the PineTime as a fun and educative way to introduce children to programming and to FOSS ideas. He also provides many ideas of customizations and applications  in which children can participate.

#### Rework of ITD

[Elara](https://gitea.elara.ws/Elara6331) applied a complete rewrite of the InfiniTime abstraction layer in [ITD](https://gitea.elara.ws/Elara6331/itd). It's based on a different [Bluetooth library](https://github.com/tinygo-org/bluetooth) and allowed to integrate the new weather functionality. This rewrite will also allow to make ITD cross-platform in the future.

![itd](/blog/images/September_2024/itd.png)

Let me also take the opportunity to mention that Elara [accepts donations on Liberapay for their work on ITD and many other FOSS projects](https://liberapay.com/Elara6331/)!

#### Flatpak package for Amazfish

[Jozef](https://fosstodon.org/@jmlich), a great contributor to InfiniTime and Amazfish (among other projects) created [a Flatpak package for Amazfish](https://fosstodon.org/@jmlich/112303505737990399). This will make the installation of this Linux companion app much easier for many users!

The package is available on [Flathub](https://flathub.org/apps/uk.co.piggz.amazfish).

![amazfish](/blog/images/September_2024/amazfish.png)

#### PineTime integration in MyGnuHealth

[MyGNUHealth](https://codeberg.org/gnuhealth/mygnuhealth) is a Personal Health Record (PHR), an application that records and stores the health data and other information related to the care of a patient. MyGNUHealth is open source (GPL) and respects the freedom and privacy of the individual.

[Luis](https://todon.eu/@meanmicio) recently [announced](https://todon.eu/@meanmicio/112265894986557868) they were working on integrating the PineTime in MyGNUHealth. Since this post on Mastodon, the [pull request](https://codeberg.org/gnuhealth/mygnuhealth/pulls/20) was merged in the development branch and released in [MyGNUHealth 2.20](https://codeberg.org/gnuhealth/mygnuhealth/releases/tag/v2.2.0).

![mygnuhealth](/blog/images/September_2024/mygnuhealth.png)

#### The super-power of open source

What is open source? Why does it matter? Those are easy questions, but I honestly have a hard time answering them, especially in English which is not my first language.

Julian (the author of one of the blog post mentioned above) sent the following message in the [PineTime chat room](/community/#chat_platforms) which provides a very simple yet accurate answer to them by describing the *super power* of open source:

  _"Having the power to customize is the super-power of open source and I want to be able to demonstrate that to everyone who sees the watch. (And I think we should work on making customization easier, so everyone can do it.) Awesome to be standing on the shoulders of those who made this possible. Thank you!"_

I think this is a really nice way to define the open source philosophy: users are empowered to customize the software they are using!

Here are the picture JulianF posted in the chatroom to demonstrate that super-power:

![julian](/blog/images/September_2024/julian1.png)![julian](/blog/images/September_2024/julian2.png)![julian](/blog/images/September_2024/julian3.png)

In this case, the customization consists in adding the owner name ("pine time") to the watch faces. It's simple but effective!

Feel free to have a look at [his repo](https://lab.trax.im/gentle/infinitime/-/commits/show-owner-name/) and [his website](https://julian.foad.me.uk/). Thanks Julian for the kind words and for reminding us why open source is important!

#### InfiniEmu

[Felipe](https://github.com/pipe01) introduced [InfiniEmu](https://github.com/pipe01/InfiniEmu) a few weeks ago. InfiniEmu *emulates an ARM Cortex M4 CPU capable of running InfiniTime*.

It basically emulates the hardware of the PineTime smartwatch (the MCU itself - the nRF52832 and its ARM Cortex M4 core and peripherals - the accelerometer, the touch screen controller, the heart rate sensor, the display and the SPI flash) to run the unmodified InfiniTime firmware on your computer and even [in your browser](https://pipe01.net/misc/infiniemu/).

![infiniemu](/blog/images/September_2024/infiniemu1.webp)

I'm really impressed by this project and, even if its description says that it *isn't production ready by any means, and the emulation almost definitely doesn't completely match a real device*, it's already very usable.

To be honest, I don't know how this project achieved such a feat! But it's a great opportunity to learn new things!

Now that I see it running, I can think of many use-cases for InfiniEmu: it could be used to add automatic testing, to provide more runtime information about resources (CPU and memory) usage, help with low level debugging,...

To my knowledge, InfiniEmu is the 2nd project that allows running InfiniTime on other targets (mostly development computers) than the actual PineTime. This is really interesting because both projects follow different approaches.

[InfiniSim](https://github.com/InfiniTimeOrg/InfiniSim) rebuilds most of the InfiniTime code and replaces a few parts so that it runs on a Linux desktop. It's very easy to build and use, and allows developers to very conveniently build new applications and UI elements for InfiniTime.

On the other hands, InfiniEmu emulates the whole hardware so that it runs the very same binary file than the PineTime (it does not need to be rebuilt to target the x86 architecture, for example).  

#### InfiniTime Status

Core developers of InfiniTime are quite busy with their private life, family, work on other projects right now, which is probably the main reason why InfiniTime haven't released a new version these last few months. But don't worry, they are still working on the project, reviewing [pull-requests](https://github.com/InfiniTimeOrg/InfiniTime/pulls) and fixing [bugs](https://github.com/InfiniTimeOrg/InfiniTime/issues)!

I would like to highlight the feature I ([JF002](https://github.com/JF002/), the original author of InfiniTime) am focusing on right now: [the always-on display](https://github.com/InfiniTimeOrg/InfiniTime/pull/1869). This feature, contributed by [John Crawford (KaffeinatedKat)](https://github.com/KaffeinatedKat) and [mark9064](https://github.com/mark9064) implements a new *always on* display mode, which, as the name implies, keeps the display always on. In "sleep" mode, instead of fully switching it off, the display is kept on with a very low brightness. This allows you to have a glance at the time much more easily and reliably than when using other *wake options* like pushing the button or raising the wrist.

![aod](/blog/images/September_2024/aod.png)

This feature obviously comes with a trade-off: the battery life is significantly reduced. According to _Mark9064_ and to my own tests, it lasts for 2 to 3 days in this mode, which is, in my opinion, quite reasonable knowing how much current the display uses when it's powered on!

I can't thank _Mark9064_ enough for their work and patience during the review process: the always on feature is actually the tip of the iceberg. In order to make this feature possible, a few changes in low-level drivers (SPI, display, brightness management) and InfiniTime (refresh management of the UI) along with a few other improvements were needed. All those changes needed to be carefully reviewed and tested. We also experimented with multiple implementations of some changes to pick the one that would use [the least power possible](https://github.com/InfiniTimeOrg/InfiniTime/pull/1869#issuecomment-1950293868).

All those required changes are now integrated in InfiniTime. So now, all we have to do is to review the last pull-request: the one that actually adds the *always-on* feature!

Stay tuned for InfiniTime 1.15. ;-)

### PineDio

{{< credits "Author: CarbonatedCaffeine" >}}

Pine64 has a line of LoRa boards under the "PineDio" name which unfortunately launched at a bad time as the Meshtastic project was in it's infancy at that point around 2020-2021. Now it has become a much bigger project and we have interest in improving support for the PineDio USB adapter on Meshtastic. 

We are looking for people interested in Meshtastic and LoRa to help with the PineDio USB Adapter as it needs a stable driver for users to easily use the device.

If you're interested please come visit the [Pine64 LoRa channels](https://pine64.org/community/) or join the [Meshtastic Discord server](https://discord.com/invite/ktMAKGBnBs). 

## Community Updates

### Infrastructure and Moderation

For a while now, our community manager Gamiee has been taking on the work of keeping all of the community servers an services up and running as well as trying to moderate the online chat's. Due to increased his day-job workload he is handing over the mantle of the community moderation to some others of the community. Namely our new community committee who are slowly transitioning to help look after the community. Gamiee will continue to look after the infrastructure of the Pine64 website and services. 

### Lomiri on PostmarketOS

{{< credits "Author: CarbonatedCaffeine" >}}

![lomiri](/blog/images/September_2024/lomiri.jpg)

Community member [Blume](https://github.com/RoseBlume) has been building PostmarketOS images with Lomiri for various devices like the PinePhone and PineTab and would appreciate feedback and testing. You can find his images [here](https://github.com/RoseBlume/PostmarketOS-Lomiri-Images).

### GTK3 inspired watchface

{{< credits "Author: CarbonatedCaffeine" >}}

![gtkwatchface](/blog/images/September_2024/gtkwatchface.png)

Community member [M​orsMortium](https://codeberg.org/MorsMortium) designed and created a series of watchfaces inspired by the GTK3 interface style. It includes widgets for the weather along with days of the week and numbered battery status among the rest.

You can check it out [here](https://codeberg.org/MorsMortium/GTKWatchFace) along with instructions on installing it on your PineTime in the README. Contributors welcome!

### Want to contribute to the next community update?

Do you have a cool project that you're working on you'd like to be mentioned? Is there something you're interested in that you'd like to write about related to Pine64? Something we'll be doing going forward is a spotlight for projects within the Pine64 community. If you're interested please contact us!

- Camden/CarbonatedCaffeine: 
    - @carbonatedcaffeine (Discord)
    - @endernightlord (Matrix)