---
title: "InfiniTime 1.11"
date: "2022-10-18"
authors: ["JF"]
categories: 
  - "pinetime"
tags: 
  - "pinetime"
cover:
  image: "/blog/images/infinitime11-1230x692.jpg"
images:
  - "/blog/images/infinitime11-1230x692.jpg"
---

We released [InfiniTime 1.11](https://github.com/InfiniTimeOrg/InfiniTime/releases/tag/1.11.0) a few days ago. The timing of the release did not align with the monthly community update, so we decided to write a small blog post to highlight a few new features and provide new about the PineTime community!

InfiniTime 1.11 is the result of three and a half months of work from many contributors. 59 pull request have been merged with changes ranging from new watch faces to small bug fixes passing by improvements in multiples area of the project.

I’ll highlight a few of these new changes in this post, and feel free to read the whole [release note](https://github.com/InfiniTimeOrg/InfiniTime/releases/tag/1.10.0) for more information!

![](/blog/images/shooting_1-682x1024.jpg)

InfiniTime 1.11 brings 2 new watch faces!

## External resources

As you may know, InfiniTime is currently quite constrained by the memory space available in the PineTime. Both RAM and flash memories are quite well packed, and we have to ensure that the changes we include in the project will actually fit in the remaining memory available.

But we are not doomed to save any byte in memory forever, and we have multiple options to give InfiniTime a bit of fresh air!

If you read the Pine64 monthly community updates, you may have noticed that I wrote about the usage of the external flash memory of the PineTime for some time now. Remember the blog post from December 2021 [where I teased a few watch faces with custom backgrounds](https://www.pine64.org/2021/12/15/december-update-a-year-in-review/) ? Nearly a year, that’s the time it took to put all things together to make this happen : InfiniTime can now use the external flash memory to store fonts and pictures and make them available to applications and watch faces!

![](/blog/images/custom-backgrounds-300x300.png)

Testing custom backgrounds back in December 2021

This feature will bring a lot of possibilities in the future : the external memory is a 4MB flash memory. It’s really huge compared the the 512KB available in the main memory of the PineTime. In the future, we’ll be able to move more and more data from the internal to the external memory, which will free very precious space to add more and more features to InfiniTime!

What did it take to build this feature? Things started with the integration of LittleFS, a file system designed for embedded systems, in [InfiniTime 1.3.0](https://github.com/InfiniTimeOrg/InfiniTime/releases/tag/1.3.0). At first, this file system would only be used to store user settings and BLE bonding information, but we knew it would be the basis for other functionalities in the future.

Then, the BLE FS API was added in [InfiniTime 1.8](https://github.com/InfiniTimeOrg/InfiniTime/releases/tag/1.8.0). It provided companion apps with an access to the internal file system of the PineTime. It was not that useful at that time, but once again, we knew we would need it in the future.

Now that we know how to store and access files from the external memory, we can focus on the next step : extending InfiniTime so that applications and watch faces can actually access to the images and fonts stored in the file system! This step took a lot of time with many trials and errors until we finally reached a point where we were satisfied by the performances of the system. Indeed, the external memory is far slower, and we wanted to provide the best user experience no matter what. Most of the work done in this step is documented in [this page](https://github.com/InfiniTimeOrg/InfiniTime/issues/321).

![](/blog/images/external-resources-history.png)

And we are not done yet : we need to provide the users with an easy way to install the resources. And for this, we need the support of companion apps. [ITD](https://gitea.arsenm.dev/Arsen6331/itd) and [InfiniSim](https://github.com/InfiniTimeOrg/InfiniSim) added support for the external resources very soon in the development process. I also implemented the upload procedure in [Amazfish](https://github.com/piggz/harbour-amazfish/pull/236) which allowed me to test that the procedure actually worked!

Now, everything is in place to release this new feature to the wild!

## New watch faces

Contributors to the InfiniTime project work on many great features, apps and watch faces, and keeping up with this constant stream of pull-requests is probably the most difficult part of our job as project maintainers. I’ve been eyeing the watch faces [Infineat](https://github.com/InfiniTimeOrg/InfiniTime/pull/1024) and [G7710](https://github.com/InfiniTimeOrg/InfiniTime/pull/1122) for quite some time now, but couldn’t merge them because of their memory usage.

It turns out they were great candidates to be the first watch faces to leverage the resources feature in InfiniTime!

Infineat is a very stylish, colorful and customizable watch face that displays the battery level using an animated Pine64 logo. The big font makes it very easy to read.

![](/blog/images/infineat.png)

The Infineat watch face

The G7710 watch face is designed to mimic the interface of LCD watches. It displays the week number, day of the year, days until the end of the year, date, time, step count, battery level and heart rate.

![](/blog/images/g7710.png)

The G7710 watch face

To enable those watch faces, you’ll need to install the resources package provided in [the release note of InfiniTime 1.11](https://github.com/InfiniTimeOrg/InfiniTime/releases/tag/1.11.0). Please check the release note and [the documentation](https://github.com/InfiniTimeOrg/InfiniTime/blob/develop/doc/gettingStarted/updating-software.md#updating-resources) for more information about this. Note that for now, only ITD and Amazfish support this feature, but I hope other companion app will integrate the upload procedure for external resource very soon!

## Other additions and improvements

External resources and the new watch faces are obviously not the only changes we make to the project! On the UI side, we made many improvements in the UI to improve the consistency of the interface and make it more readable. We also created a new ‘counter’ widget to make settings like the date, time and alarm easier.

![](/blog/images/counter-widget.png)

The new Counter widget in the time setting screen

A new Sleep mode is available via the Quick Settings menu. This mode disables notifications, chimes and all automatic wake up options (touch and motion) and will prevent the watch from waking itself (and the user) up during the night.

![](/blog/images/sleep-mode.png)

The new sleep mode in the quick settings menu

I would also like to mention that the Core Developers team worked on [a new document that describe the vision of the project](https://github.com/InfiniTimeOrg/InfiniTime/blob/develop/doc/InfiniTimeVision.md).

You’ll find the complete list of additions, improvements and bug fixes in the [release note](https://github.com/InfiniTimeOrg/InfiniTime/releases/tag/1.11.0).

## InfiniSim

[InfiniSim](https://github.com/InfiniTimeOrg/InfiniSim), the InfiniTime simulator, evolves alongside InfiniTime. Its main developer [NeroBurner](https://github.com/NeroBurner) takes a great care to make necessary changes in the simulator to adapt to changes in InfiniTime.

![](/blog/images/infinisim-1-1024x337.png)

Infineat running in InfiniSim. Did you know that InfiniSim provides an easy way to take screen shots?

InfiniSim was also extended to support all the features related to the external SPI flash memory, the file system and the external resources. A new tool "littlefs-do" allows to easily manage the simulated SPI flash memory : list files, read and write files and even load the external resources package in a single command! Please check [the documentation](https://github.com/InfiniTimeOrg/InfiniSim#littlefs-do-helper) to see what littlefs-do is capable of!

## Wrap up

That’s it! Enjoy InfiniTime 1.11 on your PineTime! Feel free to join us in the [community chat rooms](/community/#chat-platforms) if you have questions, need help or just want to talk about your favorite smart watch ever!
