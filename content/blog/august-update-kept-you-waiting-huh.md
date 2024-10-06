---
title: "August Update: Kept You Waiting, Huh?"
date: "2023-08-15"
authors: ["Marek Kraus"]
categories: 
  - "community"
  - "news"
  - "pine64-community"
tags: 
  - "community"
cover: 
  image: "community-update-8-2023-thumbnail.jpg"
images:
  - "/blog/images/community-update-8-2023-thumbnail.jpg"
---

![](/blog/images/community-update-8-2023-thumbnail.jpg) 

We apologize for the lack of regular community updates during the past few months. In short, the people who usually wrote them became very busy. However, we have a new way to write and publish these updates, involving you: the community.

Let's talk about it, and about so much more of what's been happening.

This community update consists of contributions by Caffeine, CounterPillow, Funeral, gamiee, JF002, and mpreditor.

N.B. Comments on the blog post need to be in English and follow our [Community Rules and Code of Conduct](https://forum.pine64.org/showthread.php?tid=13209).


## TL;DR

* Housekeeping
    * Community updates are now written collaboratively by several members of the community
    * The public is invited to contribute to the monthly update posts
    * Rework of the community website and logo
* Newsflash
    * megi released rk2aw: a loader for your bootloader
    * Progress on the PineTab2 and PineTab-V
    * A PinePhone Pro connected to a thermal imaging camera
    * Oren Klopfer's progress on Ubuntu Touch
* Quartz64 and SOQuartz
    * U-Boot improvements thanks to Kwiboo and CounterPillow: USB, NVMe, and soon PXE
    * Improved SOQuartz CM4 baseboard compatibility
    * Improved PCIe devices compatibility
* QuartzPro64
    * What it means to "mainline" things, and why it takes time
    * Things that have been mainlined: SATA, PCIe, USB, AV1, and more!
    * Things still being worked on: cpufreq, GPU, video output
* InfiniTime 1.13 and other PineTime news
    * Heart rate monitoring improvements thanks to Ceimour!
    * Did you know that InfiniTime has a BLE weather service feature?
    * Improved memory management
    * Huge improvements to battery life (with help from Ayke!)
    * InfiniSim UI update
    * Improvements to ITD, the InfiniTime daemon
    * Ayke is developing a brand new firmware for the PineTime


## Housekeeping

You might have been wondering why nothing new has been posted on the PINE64.org community blog in quite a few months. As was already revealed in the opening section, the reason is that previously blogs were mainly authored and edited by one person (Lukasz) and said person is extremely busy these days.

Going forward, these monthly community update posts will be written collaboratively by the community for the community. To that end, there is now a [Git repository](https://github.com/pine64/community_updates) through which this work happens. You don't need to be a good writer to contribute, you can submit links or short bullet lists and the editors will take care of the rest.

The plan is to have a post out on the 15th of every month. Whether or not this deadline will be met each month is another question, but now you can keep an eye on what's happening behind the curtains and help out if necessary.

Speaking of deadlines, this update didn't have a very long time in the proverbial oven despite the long period of silence preceding it, so it may be a little short or not cover all developments in the community equally well. Just because something is not covered in this post doesn't mean it hasn't been worked on.

### Rework of the community website and logo

If you missed the announcement, an initial rework of the community website was announced. The announcement blog post can be read exclusively on the new beta site: https://pine64.org/2023/04/13/a_new_design/

The overall idea of the reworked community website is to move away from a WordPress site and to open up the site to contributions from all community members. This is done by hosting the website on Git and by generating the contents using the blazing-fast framework *Hugo*. Large parts of the website are created from simple markdown files, which are easy to understand and to edit. Alongside the rework of the community website, there was also a challenge launched, which has the goal of improving the appearance of the community logo. The details can be read under https://pine64.org/contests/the-logo-challenge/. Bring in your best ideas if you haven't done so yet. Ideas are best submitted to https://github.com/pine64/website/issues/12.

Since the last blog post, there has been various improvements made to the beta community website. The improvements include changes to the style of various sites, improvements to the front site slider and inclusion of more slides, rewrite of pages as markdown files (such as the index page), creation of more board graphics and many more changes.

![PineTime slide](/blog/images/beta_impr_1.png)
![PineNote slide](/blog/images/beta_impr_2.png)

The documentation for all PINE64 devices is also constantly improving. While there are large construction zones left, the overall look of the documentation is already quite clean and constantly improving:

![PineNote slide](/blog/images/beta_impr_3.png)

The changes can be viewed on the repository under https://github.com/pine64/website. Give it a try by cloning the repository and previewing the page using Hugo:

```
git clone https://github.com/pine64/website.git
cd website
hugo server
```

## Newsflash

### megi released rk2aw: a loader for your bootloader

First up, long-time contributor megi [has released rk2aw](https://xnux.eu/rk2aw/), a sort of bootloader for your bootloader on Rockchip-based platforms. Instead of having to deal with the default boot order of SPI to eMMC to SD, rk2aw sits in your SPI flash and changes the order to prefer the SD card for booting from first, which is more tinkerer-friendly. Additionally, a simple LED flashing and button interface allows the user to choose which storage device the bootloader should be loaded from. The software also comes with some nifty additional features, like suppressing power-on when the PinePhone Pro is plugged in.

Of PINE64's devices, rk2aw supports the PinePhone Pro, Pinebook Pro, PineTab2, QuartzPro64, Quartz64 Model A and ROCKPro64, though it can theoretically be made to work on any RK3399/RK3566/RK3588-based device.

### Progress on the PineTab2 and PineTab-V

Since the PineTab2 and PineTab-V tablets have been shipped, the community has been tirelessly at work, propelling the software landscape forward and unveiling an array of new software and bootable images for both tablet models.

The [software releases section of the PineTab2](https://wiki.pine64.org/wiki/PineTab2_Releases) already lists Arch Linux ARM, Mobian, NixOS, postmarketOS, Rhino Linux, Ubuntu Touch and others, with more to come. The [software releases section of the PineTab-V](https://wiki.pine64.org/wiki/PineTab-V_Releases) lists a Gentoo overlay, as well as a KDE Plasma Yocto build from the community member Fishwaldo, with even more in the pipeline.

There is also progress on the WiFi driver of the PineTab2. Some releases already ship with an initial support for the on-board WiFi chip. It is however important to note that the work on the driver is ongoing and has not reached a software maturity yet. 

These software releases are a testament to the vibrant collaboration within the PINE64 community. Developers, enthusiasts, and users alike have come together to cultivate a thriving ecosystem that empowers PineTab2 and PineTab-V users with an array of choices. 

### A PinePhone Pro connected to a thermal imaging camera

The user *yomboprime* coupled a PinePhone Pro with the thermal imaging camera Topdon TC-001. Check out their nice video here: https://www.youtube.com/watch?v=lJhgZve9xSA

### Oren Klopfer's progress on Ubuntu Touch

Another mention deserves maintainer Oren Klopfer, who is working on Ubuntu Touch support on numerous devices, including the PinePhone and PinePhone Pro, the PineTab and PineTab2.

Check out the supported devices under https://devices.ubuntu-touch.io/.

## Quartz64 and SOQuartz

The RK3566 SoC that's on the Quartz64 and SOQuartz line of PINE64 devices hasn't had great mainline U-Boot support for the longest time. Technically, there was some vestigial support and an EVB (evaluation board) device tree, but it was far from optimal.

For those not in the know: U-Boot is somewhat of a mix between platform firmware ("BIOS" on your common x86 PC) and bootloader. It initializes the device's hardware, and loads a kernel (usually Linux, though not necessarily so) to which it then hands control off to.

[Kwiboo](https://github.com/Kwiboo) took it upon himself to improve the situation. Over the past few months, he's enabled U-Boot on the RK3566 and RK3568 SoCs to load kernels and device trees off USB2, USB3 and NVMe. While U-Boot itself still has to be flashed to either SPI, eMMC or SD, it can now load your kernel and device tree from a wider range of storage devices.

He also submitted device trees and board configurations to mainline U-Boot for, among other things, the Quartz64 Model A, Model B, and SOQuartz. This will land in U-Boot version 2023.10, meaning with the next stable U-Boot release, distributions no longer need to carry around their own forks (unless they want to.)

Meanwhile, [CounterPillow](https://github.com/CounterPillow) has submitted an U-Boot driver for the YT8511 ethernet PHY that's present on the Quartz64 Model A and SOQuartz. This, together with work Kwiboo is doing on a GMAC driver for the RK3566 and RK3568 SoCs, will allow users to [PXE boot operating systems over the network](https://source.denx.de/u-boot/u-boot/-/blob/master/doc/README.pxe). U-Boot's default boot flow for these boards already tries PXE, so provided you have an U-Boot flashed to one of the supported storage mediums with all the moving pieces (GMAC and PHY driver) in place, PXE will work out of the box.

There are still some small changes needed to make U-Boot initialize a random seed for KASLR on these boards. KASLR (Kernel Address Space Layout Randomization) is a security hardening technique that randomizes the locations of code in memory, making it harder for attackers to execute a successful exploit. For this to work, kernels such as Linux require that the firmware passes it an initial source of randomness. The hardware random number generator on RK3566 already has a driver in U-Boot, it just needs to be enabled for all the boards.

It's also worth pointing out that there is now improved compatibility on two fronts: CounterPillow [wrote about fixing SOQuartz compatibility with some CM4 boards](https://fratti.ch/articles/posts/fixing-soquartzs-support-for-orateks-tofu-board/), and furthermore finally submitted a small fix to Linux to improve the RK3566 and RK3568's PCIe device compatibility. There is some work left to be done, but many devices should just function as expected now.

One of the benefits of all this work is that if you've got U-Boot installed on your board, you can now simply boot generic aarch64 UEFI Linux distribution installers. Consult [the wiki for more information](https://wiki.pine64.org/wiki/Quartz64_UEFI_with_U-Boot) if this piques your interest.


## QuartzPro64

There hasn't been much talk of the QuartzPro64 on update blogs since it's been sold to developers, but that doesn't mean developers haven't been busy. The SoC used on the board, the RK3588, has been making waves in SBC communities for its performance; CounterPillow can say from personal experience that it compiles Linux kernels 7 times faster than the Quartz64's RK3566 processor.

The entirety of the work has in fact been focused on the RK3588 SoC (and associated chips, such as the RK806 PMIC), rather than the specific board PINE64 produced for developers. One of the main drivers of development are Collabora, a contracting firm specializing in open-source development. But you might be wondering what there is to even do, surely Rockchip did all the work, right?

Not quite. There's two different kinds of kernels, downstream vendor kernels and the upstream mainline kernel. The mainline Linux kernel is the Linux that sits in Linus Torvalds' git tree. Patches landing in this tree need to undergo code review by the respective subsystem maintainers, and rarely is a new driver merged without a few iterations of reviews and changes. Meanwhile, a downstream vendor kernel is (usually) forked off an LTS (Long Term Support) kernel release, and the hardware vendor then piles on patches to add hardware specific drivers and hacks. These vendor kernel change sets don't undergo the upstream kernel's review.

As you might have guessed, this often leads to less-than-ideal code being present in vendor kernels, not to forget they often don't port it to newer LTS kernel releases as they become available. So what contributors like Collabora et al do is pick up code from the vendor kernels, clean it up (or write new code entirely, as is the case with multimedia or the GPU) and submit it to mainline Linux for review and inclusion. This takes a lot of work and a lot of time, as solutions only acceptable for vendor kernels often have to be generalized into solutions that work for all sorts of systems.

Despite the odds being stacked against mainline contributors in this, significant amounts of work have already been completed. Today a mainline Linux kernel can be booted on RK3588 hardware with all 8 CPU cores (4x Cortex-A76 + 4x Cortex-A55) working, though not at their maximum frequency. Serial output works, as does the SD card thanks to new support for the often accompanying RK806 power management chip. eMMC has been working for a while, however new additions are SATA, PCIe2, PCIe3 and USB2. USB3 support is still undergoing review as of the time of writing. Smaller but still noteworthy recent additions are support for OTP (reading of one time programmable values fused into the silicon at the factory) and ADC (analog-to-digital conversion).

The most high profile recent addition would be the new driver for hardware video decoding of the AV1 video codec, of which most has been merged in Linux 6.5-rc1. This is an entirely from-scratch driver, implementing the v4l2-requests userspace API. The hardware implementation on the RK3588 processor supports decoding of up to 3840x2160 pixels in resolution video for this codec at 60 frames per second. With AV1's complexity making software decoding strenuous on CPU resources, a hardware decoder driver for this more and more widely adopted codec is essential for multimedia capabilities for future Pine products potentially based on the RK3588 System-on-Chip.

Speaking of such products, the reason why we haven't seen a consumer version of the QuartzPro64, or another RK3588 based Pine Store product, has likely been all the things missing from mainline Linux still. As already mentioned, the CPU cores with mainline Linux currently don't run at their full potential. This is because no cpufreq driver has been submitted to mainline yet, which is required for reclocking the CPU. Unlike with some green colored products however, there is no technical reason as to why reclocking wouldn't be possible, it's just a matter of someone having to do the required work to create a driver that's up to mainline's standards.

Also missing is support for video output. This is separate from the 3D GPU, as the video output processor is a Rockchip-specific hardware implementation. This means that for the time being, serial and networking are still the only ways to interact with the board.

Speaking of the 3D GPU though, the RK3588's GPU is a licensed design from Arm. Collabora is working hard on adding support for it in an open-source driver in Linux, which includes writing a new kernel driver. You can read about this driver, called pancsf, in [Collabora's blog post on the matter](https://www.collabora.com/news-and-blog/news-and-events/pancsf-a-new-drm-driver-for-mali-csf-based-gpus.html). The new architecture of the Mali-G610 GPU will allow for a fully featured Vulkan driver to be written for it in the future, something older generations of Mali GPUs had to awkwardly emulate parts of.


## InfiniTime 1.13 and other PineTime news (by JF)

The InfiniTime team released InfiniTime 1.13 at the end of June. If you haven't updated your PineTime yet, I strongly suggest you do it ASAP since it brings many nice features: a new heart rate algorithm, weather integration in PineTimeStyle (PTS) watch face, new memory management, and a (much) improved battery life! Let's dive into the details of this release!

The heart rate sensor is integrated in InfiniTime for quite some time now (since [0.11.0](https://github.com/InfiniTimeOrg/InfiniTime/releases/tag/0.11.0), actually). It worked but fine but... we had the feeling that it could work better if someone had the opportunity to have a look at the code. [Ceimour](https://github.com/Ceimour) did a great job redesigning and mostly rewriting the whole heart rate processing algorithm. I'm not experienced enough in digital signal processing to explain all the internals of this new algorithm, so, if you are interested in the details, please see the explanations Ceimour provided in the PR [here](https://github.com/InfiniTimeOrg/InfiniTime/pull/1486#issuecomment-1353695831https://github.com/InfiniTimeOrg/InfiniTime/pull/1486#issuecomment-1353695831) and [here](https://github.com/InfiniTimeOrg/InfiniTime/pull/1486#issuecomment-1377673396). All in all, it now takes less time to display the first measurements, and they are now updated much faster than previously. 

Here's a video I shot when I was testing this PR. It compares the HR implementation of InfiniTime 1.11 (sealed PineTime on the left) with the new one (devkit on the right).

{{< video id="/blog/images/hr-comparison.mp4" >}}

Did you know that InfiniTime implements a BLE weather service since [InfiniTime 1.8.0](https://github.com/InfiniTimeOrg/InfiniTime/releases/tag/1.8.0) ? This service allows companion apps to send weather forecast to the watch. Since then, all we were missing was a nice UI to display those information. Thanks to [Kieran](https://github.com/kieranc), the author of the PineTimeStyle watch face, weather forecast can now be displayed in PTS.

![PTS settings](/blog/images/pts-weather-settings.jpg)![PTS weather](/blog/images/pts-weather.jpg)

This integration currently works with [Gadgetbridge](https://codeberg.org/Freeyourgadget/Gadgetbridge/) and [ITD](https://gitea.elara.ws/Elara6331/itd). You'll find documentation about the PTS watchface [here](https://wiki.pine64.org/wiki/PineTimeStyle) and about the weather integration [here](https://wiki.pine64.org/wiki/Infinitime-Weather).

*However, since the release, several users reported that the new weather feature might cause some instabilities in InfinITime: crash, unexpected reboot and font corruption. You can read more about this issue [here](https://github.com/InfiniTimeOrg/InfiniTime/issues/1788). If you are impacted, I would suggest you disable the weather feature from your companion app until we implement a fix.*

Memory management is a important topic for the InfiniTime developers. The PineTime only has 64KB of RAM memory available and we have to use it wisely. We also try to optimize the memory usage of the firmware so that we can continue to add new features in InfiniTime. And the new memory management aka "the heaps unification" is one of these optimizations.

Without going into [too much details](https://github.com/InfiniTimeOrg/InfiniTime/discussions/1569), we figured that the RAM memory in InfiniTime was split into 4 parts: the memory that is statically allocated at build time, and 3 regions that are used to dynamically allocate memory at runtime. Those 3 regions (or heaps) are managed by LVGL (the UI library), FreeRTOS (the OS InfiniTime is based on) and the standard C++ library. The goal of this change was to unify those 3 heaps into a single one (the one managed by FreeRTOS). This allows to reduce the overhead generated by those 3 heaps and it also give us a better overview of how the memory is actually used and how much memory is still available.

![memory.jpg](/blog/images/memory.jpg)

PINE64 advertise the PineTime with a "week-long battery life" and they are correct: the hardware is perfectly capable of achieving that. And InfiniTime isn't too far off the mark: in my use case (BLE and wrist wake option enabled), I usually need to recharge my PineTime every 3 to 5 days, and the battery life can be extended by disabling wake options and BLE.

We were however pretty sure that we could achieve [better results](https://github.com/InfiniTimeOrg/InfiniTime/issues/53) with some optimizations that consist mostly in disabling most of the parts of the MCU when it's idle. 

Recently, Ayke ([GitHub](https://github.com/aykevl), [Mastodon](https://hachyderm.io/@ayke)) shared their findings and measurements regarding power usage of the PineTime on [the wiki](https://wiki.pine64.org/wiki/PineTime#Reducing_power_consumption) and with [the InfiniTime community on GitHub](https://github.com/InfiniTimeOrg/InfiniTime/issues/53#issuecomment-1511657606): they optimized their firmware to reduce the power usage down to 66µA. With such power usage, the PineTime could run for more than 3 months on a single charge! Obviously, to reach such power consumption, most of the device is put in sleep mode, but that's a great achievement knowing that, for example InfiniTime uses [1.1mA in sleep mode with BLE enabled](https://github.com/InfiniTimeOrg/InfiniTime/discussions/1420#discussion-4542610)!

So we tried to apply Ayke's suggestions in InfiniTime, and the results were also really good: we went from 890µA in sleep mode down to ~200µA with BLE enabled! And a bit less with BLE disabled!

![](/blog/images/infinitime-power-usage.png)

Most of those changes are now integrated in InfiniTime 1.13, and a many users have already reported between 10 days and nearly 20 days of battery life (depending on the features that are enabled: wake up options, BLE, display timeout,...)! My PineTime worked for just over 16 days in my normal use! I'm honestly impressed by those results, and I hope you'll also notice an nice increase in the battery life of your PineTime!

![](/blog/images/battery-report.png)

### Other news from the PineTime community

Since we haven't been able to publish a PINE64 community update for quite some time now, let me share a few other news from the PineTime community!

[InfiniSim](https://github.com/InfiniTimeOrg/InfiniSim), the InfiniTime simulator, recently got a UI update that makes the status window much easier to understand: it displays the status of the (simulated) BLE connection, display brightness, charger, battery and alarm.

![infinisim-ui.gif](/blog/images/infinisim-ui.gif)

[ITD, the InfiniTime daemon](https://gitea.elara.ws/Elara6331/itd) also got a nice update in version [1.1.0](https://gitea.elara.ws/Elara6331/itd/releases/tag/v1.1.0) which, among other things, brings a new UI theme, an improved protocol between the daemon and the clients and the support for FUSE. This new feature is quite amazing in my opinion: it allows you to mount the file system of your PineTime into your computer file system. You can now browse the content of the 4MB external memory using your file explorer, for example!

![itd_fuse.png](/blog/images/itd_fuse.png)

Ayke is not only working on power optimizations : they are building [a new firmware written in Go](https://github.com/aykevl/things/tree/master/watch). They focus on power usage obviously, and also on fast and responsive UI. The project is at its very beginning, [but it's already very promising](https://hachyderm.io/@ayke/110339967077932472)!
