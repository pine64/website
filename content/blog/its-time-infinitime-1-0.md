---
title: "It's Time: InfiniTime 1.0"
date: "2021-04-22"
categories: 
  - "pinetime"
tags: 
  - "community"
  - "pinetime"
cover: 
  image: "Infinitime.jpg"
images:
  - "Infinitime.jpg"
---

![](/blog/images/Infinitime.jpg)

_When we announced the PineTime in late 2019 we couldn’t have imagined how popular of a project it would end up becoming. From the very start, it was evident that this will be a project like no other in our lineup. Following 18 months of intense development, the InfiniTime has now reached a release version, and the development community has made a decision; the Pinetime will be introduced to the Pine Store as an enthusiast-grade end-user product. Future production-runs (succeeding the one currently available) will ship with InfiniTime 1.0 and will be considered ready for daily use. This is a monumental achievement not only for PINE64 and the PineTime development community, but also for the open source at large. I’d like to thank all of you who made this a reality, my mind is blown._

_~Lukasz Erecinski_

Today I'm thrilled to announce the release of [InfiniTime 1.0](https://github.com/JF002/InfiniTime)!

Before we go into more details about this release, let me introduce you to the PineTime project and its history.

### A brief history of the PineTime project

The PineTime was first introduced in [October 2019](https://www.pine64.org/2019/10/05/october-update-pinetime-delays-and-shipping-news/) as a completely community driven side-project, and positioned as a complementary device to the PinePhone. PINE64 decided on a simple hardware platform - a square body and a FOSS-friendly SoC, to make the developers life a bit easier.

At the time, PINE64 was just tossing a bottle into the sea and waiting to see what will happen. Will the community like the idea? Will developers be interested in working on such a project?

Well, we now know how the story unfolded; prospective users and developers turned out to be very interested in the idea of a FOSS smartwatch. I too was really excited about this project the moment I read about it in an article, and I was really happy to be one of the first developers to [receive a PineTime](https://twitter.com/codingfield/status/1187437471702888448?s=20) development kit.

It wasn’t long before a significant community of users and developers gathered in the community chat rooms. People from all around the world joined the chat to discuss the PineTime, their projects, their experiments, their progress and their ideas.

The project reached its first milestone in September 2020, when PINE64 chose InfiniTime as the default firmware for sealed and development kits PineTimes. And today, 7 months later, we reached a new important milestone: InfiniTime’s first release.

{{< youtube id="1MlTjq4jz1s" >}}

_Video version of this post by [PizzaLovingNerd](https://www.youtube.com/channel/UCmGcm7dhEjS9CIOsOOv8y6w)_

### InfiniTime origins

I started InfiniTime as a personal project. I wanted to experiment with the hardware and the embedded software with the vague idea of integrating it in my home automation. However, a lot of work was needed before I could even imagine using it for switching on the lights in my house: writing low-level drivers, working on the user interface, integrating the Bluetooth Low-Energy (BLE), working on Over-The-Air updates (OTA), just to name a few things that needed to be resolved and implemented.

Initially I called the firmware "My project", and then "Pinetime-JF", which quickly became popular in the PineTime community. It wasn’t long before people, users and developers alike, joined in and contributed new firmware features and bugfixes. They helped testing new releases and built the project from the ground together with me! Seeing all these people contributing, I decided I wanted my firmware to be a community project and therefore renamed it to InfiniTime.

Soon thereafter we were joined by other projects like [Gadgetbridge](https://gadgetbridge.org/) and [Amazfish,](https://github.com/piggz/harbour-amazfish) as well as more recently [Siglo](https://github.com/alexr4535/siglo). These projects deliver companion apps which run on Android and Linux smartphones respectively. They added support for the PineTime very early on, and we are still working closely together on providing more features to our common users.

### PineTime and InfiniTime 1.0: an enthusiast-grade end-user product

A few weeks ago I was talking to Lukasz about the new features we just added to InfiniTime. During the conversation we both realized that InfiniTime already provides a solid set of features, and that very few are missing before the PineTime running InfiniTime could be considered an enthusiast-grade end-user product. With this realisation, the race to releasing InfiniTime 1.0 was on, and here we are today at the finish line.

What did we achieve? InfiniTime is a fully-featured open source firmware for the PineTime, built for the community by the community.

Its main features include:

- 2 clock faces - digital and analog
    
- Multiple apps (stopwatch, music control, navigation, heart rate) and games (Paddle and 2048)
    
- User settings (display timeout, time format, wake up conditions)
    
- OTA upgrades with the help of a FOSS bootloader based on MCUBoot
    
- Heart rate monitoring and step counting
    
- 3 - 5 days of battery life
    
- And much much more!
    

The project reaching version 1.0 does not automatically mean that it's completely bug free nor that it can compete with mainstream commercial products. I see InfiniTime 1.0 as a firmware version that enthusiasts (people who like to discover new things, use cutting-edge technology, and maybe also contribute to FOSS projects) can use as a daily driver without needing experience in software development. In result, InfiniTime 1.0 is also the first version of the firmware which allows PINE64 to sell sealed PineTimes as an enthusiast-grade end-user product!

![](/blog/images/PineTimeHR-1024x1024.jpg)

_InfiniTime has a functional heartrate monitor app capable of displaying heartrate on the default watchface_

![](/blog/images/PineTimeOptions-1024x1024.jpg)

_There are many options to tailor your experience, including waking the display on wrist tilting or tapping the display  
_

### InfiniTime is only one of your options

As any true open source project, the PineTime does not rely solely on one community or a single firmware. There are [many other projects](https://wiki.pine64.org/wiki/PineTime_Development) available that are currently under development and all of them deserve attention from the user base.

The most advanced firmware among those on the list is probably [Wasp-OS](https://github.com/daniel-thompson/wasp-os) - the Micropython firmware. It provides many functionalities and is really easy to use and program for thanks to the Python language.

I would also like to highlight [Pinetime-Lite](https://github.com/joaquimorg/PinetimeLite/), a fork of InfiniTime by Joaquimorg. Joaquim added a lot of nice features and improvements, and has already contributed a lot of his work back into InfiniTime.

![](/blog/images/WaspOS.jpg)

_[Wasp-OS](https://github.com/daniel-thompson/wasp-os) is a popular alternative firmware to InfiniTime, with a lot of functionality and great features_

![](/blog/images/PinetimeLite.jpg)

_[Pinetime-Lite](https://github.com/joaquimorg/PinetimeLite/) is an InfiniTime fork with many watchfaces, advanced features and complete end-user functionality_

**Acknowledgements**

I would also like to thank everyone who participated, directly or indirectly, in the development of this project. This is an open source project with a strong community emphasis, and every contribution counts. A typo correction in the documentation, a major feature to be merged into the firmware, helping others debug issues or just words of encouragement on the chat and social media - we built this together, and it is something we can be proud of.

And I would also like to thank PINE64 for initiating the PineTime project and for trusting the community to build such an amazing firmware for it.

[Download InfiniTime](https://github.com/JF002/InfiniTime/releases/) [Buy the PineTime](https://pine64.com/product-category/smartwatches/?v=0446c16e2e66)
