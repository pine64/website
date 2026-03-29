---
title: "Introduction to the PineTime Pro"
date: "2026-03-28"
authors: ["JF"]
categories: 
  - "community"
  - "news"
  - "pine64-community"
  - "pinetime"
  - "pinetime-pro"
tags: 
  - "pinetime-pro"
  - "pinetime"
  
images:
  - "/blog/images/PineTimeMarchBanner_2026.png"
summary: "How is your day/night going RSS readers? In this blog post we go in depth on the new PineTime Pro hardware and share some pre-production information from JF."

---

![The PineTimePro announcement banner](/blog/images/PineTimeMarchBanner_2026.png)

{{< toc >}}

## Introducing the PineTime Pro

The PineTime Pro was officially announced at [FOSDEM26](https://fosdem.org) on the Pine64 stand. The demo was a bit modest (more on that later on), but we were delighted to showcase the first prototype of the "next generation PineTime" along with a demo running on a development board!

![PineTime Pro devboard](/blog/images/March_2026/EternalBlue.jpg)

We also mentioned the PineTime Pro in the [FOSDEM 2026 Update](/2026/03/24/march_2026_fosdem/) blog post. In this blog post, we would like to provide a more in-depth look at the PineTime Pro.

## Why "Pro" and not "PineTime 2"

The PineTime project started in [October 2019](/2019/10/05/october-update-pinetime-delays-and-shipping-news/), that's more than 6 years ago! Needless to say, the PineTime has been a great success. The community has been very active in developing firmware for the device, companion apps, tools and more. And, according to PineStore, it sells very well.

The reason the PineTime Pro isn't called the PineTime 2 is because it's not meant to replace the original PineTime. The original watch still has a lot going for it: it is simple, hackable, efficient and already supported by great community projects like InfiniTime and WaspOS. It will continue production alongside this new model.

The PineTime Pro should be seen as a more powerful, more feature-rich sibling rather than a direct successor. If the original PineTime is a solid open smartwatch platform, the PineTime Pro is our attempt to push that idea much further with new and improved components.

## What makes it "Pro"

Compared to the "OG" PineTime, the PineTime Pro brings a significant hardware upgrade.

At its core is a dual-core Cortex-M33 SoC, with one application core running at up to 200 MHz and a dedicated Bluetooth core. It also comes with 800 KB of internal SRAM and 8 MB of PSRAM. 

Around that MCU, the hardware currently includes:

- Bluetooth 5.2 - Classic (BR/EDR) & Low Energy
- A 410×502 AMOLED display with touch support
- A digital crown that also acts as an extra button
- GPS
- A heart rate sensor with blood oxygen measurement capability
- Improved accelerometer -> full 6D Interial Measurement Unit
- An I²C battery charger, which can be configured and monitored by the MCU
- External QSPI 8MB flash memory
- Microphone and speaker
- A vibration motor
- A 4-pin connector for power and debug/programming, with configurable pins for serial output or SWD

Yes, it's still an embedded platform, but much more powerful. Here is a quick comparison between the PineTime and the PineTime Pro:


|     | OG PineTime                | PineTimePro                                                |
|-----|----------------------------|------------------------------------------------------------|
| MCU | 1x ARM Cortex-M4 core      | 2x ARM Cortex-M33 cores                                     |
| RAM | 64 KB SRAM                 | 800KB SRAM + 8MB PSRAM                                     | 
| Flash | 512KB internal + 4MB SPI   | 8MB SQPI                                                   |
| Display | 240x240px, 1.3"            | 410x502px, 2.13"                                           |
| Sensors | Heart rate + accelerometer | heart rate + blood oxygen sensor, 6D IMU                  |
| GPS | No                         | Yes                                                        |
| Debug port | Internal                   | Available on external pin                                  | 

Altogether, this opens the door to much more ambitious software (like PebbleOS ;) ) and use cases than what is practical on the original PineTime: fast, smooth and rich UI, fitness tracker, localization and tracking, external apps and watch faces and more! 

![What the PineTime Pro looks like on an ARM](/blog/images/March_2026/SecondHandShopHand.jpg)

## A long road to get here

The PineTime Pro has been in discussion for quite a while. Community members including JF, Gamiee and Ralim have been exploring the idea for a long time, and from the beginning, one thing was clear: choosing the right MCU would make or break the project.

Earlier iterations were based on a RISC-V MCU. In fact, the demo shown at FOSDEM 2024 was based on that platform. While the idea was exciting, we ultimately ran into issues with power consumption along with the quality of the available documentation and SDK. Those limitations made it difficult to see a good long-term path forward.

Things became much more concrete when PineStore started collaborating with a large smartwatch manufacturer in China that had developed its own chip. That collaboration has been very valuable so far: PineStore and the community have been working together on the hardware design, and documentation and SDK materials have been shared to help software development move forward. All of these resources will also be available to the community once the device enters production.

Along the way, we explored a few extra ideas too. For example, we looked at adding **LoRa**, but that introduced major challenges in terms of PCB space and RF design. A **light sensor** was also considered, but dropped it for similar reasons. On the other hand, adding a **speaker and microphone** turned out to be relatively easy, so those ended up becoming a nice bonus.

## Recent progress

During **FOSDEM 2025**, we received the first two development boards based on the new Cortex-M33 platform. Throughout 2025, PineStore and community members, especially Gamiee and Ralim, continued reviewing the hardware design while JF was experimenting with the development board and the SDK.

Toward the end of 2025, the first two actual watch prototypes were sent to Gamiee and JF. Unfortunately, those boards had hardware issues that left the SWD port (the programming and debugging port) non-functional, which made software bring-up much more difficult than expected.

A second batch of prototypes arrived just before FOSDEM this year. We had hoped to show them running on the Pine64 stand, but another hardware issue got in the way: the flash memory was not working properly, so the demo had to run on the development board instead of the actual watch hardware.

That said, progress is still very real. After several rounds of review between PineStore and the community, a third hardware revision is expected at the beginning of April. We’re optimistic that this revision will finally resolve the remaining blockers and let software development ramp up properly.

![PineTime devkit](/blog/images/March_2026/PineTimePro_Devkit.jpg)

## What about software?

Just like the original PineTime, we expect the community to enjoy this new device and develop many projects on top of it!

The good news is that developers from both InfiniTime and WaspOS are already involved, which gives the platform a strong starting point. The PineTime Pro is exciting not just because it is new hardware, but because it offers much more room for experimentation. Features that are extremely challenging to fit into the original PineTime due to resource constraints may become practical here.

Can it run Doom? Most probably, and I guess someone will take the challenge and make it happen!

On the InfiniTime side, the original PineTime is not being abandoned. InfiniTime is already a fairly mature project, and it will continue to exist. And I guess the same is true for Wasp-OS.

But realistically, the PineTime Pro is likely to keep developers busy for quite some time, simply because it creates so many new possibilities.

Right now, JF is mostly focused on low-level experiments and validation, with the goal of getting basic drivers and a demo application working as soon as possible. Gamiee is also expected to help with OpenOCD integration once he wraps up work on the PineVoice.

## What happens next?

The next major milestone is simple: get the new hardware revision in hand, confirm that the remaining issues are solved, and continue pushing software bring-up forward.

There is still work ahead, and we are not pretending otherwise. But after a long period of exploration and hardware iteration, the PineTime Pro is finally starting to feel real.

We’re looking forward to sharing more as development continues.

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