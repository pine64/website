---
title: "January Update: Thinking Out Of The Vox"
date: "2025-01-11"
authors: ["Caffeine"]
categories: 
  - "community"
  - "news"
  - "pine64-community"
tags: 
  - "pinevox"
  - "pinebook-pro"
  - "fosdem"
  - "pinenote"
  - "pinetime"
images:
  - "/blog/images/JanuaryBanner_2025.png"
summary: "Happy New Year! This month we discuss the current state of the PineVox, seeing what the community have been up to with their PineNotes, announcing InfiniTime 1.15 and announcing the end of production of the Pinebook Pro."
---

This month we report on some news concerning the PineVox, what the community have been up to with their PineNotes and the brand-new 1.15 InfiniTime update. We would like to wish our community a happy New Year and hope you all had a good end of 2024. 

But since it's now the beginning of 2025, we'd like to fill you in on what we have planned for the first part of the year. 

We plan to release the PineVox to the public thanks to Gamiee's recent progress and we plan to continue improving the software for the PineNote, thanks to Maximilian, Diederik and our testers in the community. We have some exciting devices coming as well, mentioned in previous community updates. The PineCam and StarPro64 have been sent to developers in our community, so we hope to report on these devices in the coming months. 

Gamiee has also been working with a group of our friends over at Meshtastic on an independent project which will become the second version of the PineDio USB LoRa adapter. We plan to talk more about the progress of that project more in the February update.

![The January 2025 community update banner](/blog/images/JanuaryBanner_2025.png)

{{< toc >}}

## FOSDEM

{{< credits "Author: Caffeine" >}}

Unfortunately, a stand at FOSDEM hasn't been allocated for us this year. But that doesn't mean we won't be there to represent PINE64! Gamiee, Ralimtek, JF, TL Lim and Lukasz will be attending in person this year and will be planning a get-together. We will announce on our social-media when we have confirmed the time and place. 

Of course, our PINE64 community members will still be wandering around the event, we love talking to all our friends at other projects and meeting the members of our community! So we hope we'll see you there!

## PineVox

{{< credits "Author: Caffeine, Gamiee" >}}

Gamiee has been working on the firmware for the PineVox recently (haha, now the title pun makes sense), he has made some significant progress on the usability of the device.

Right now, the device can connect to home assistant, detect wake-up and process commands. Wake-up detection is currently done on the Home Assistant side, streaming audio data through Home Assistant. This will change as work is done to get wake-up detection working locally on the PineVox.

As for what’s next, Gamiee wants to implement a protocol for connection via Wi-Fi. This is much better for devices like smartphones, which in an ideal situation will provide coverage all throughout the home, rather than the small area that Bluetooth LE covers. 

Regarding the release of PineVox, it depends, currently this will depend on when Gamiee considers the firmware for the device to be usable. Only then will manufacturing for the device begin, which is loosely aimed at the end of February (take this with a grain of salt). 

![The PineVox listening to a voice command from Gamiee](/blog/images/January_2025/pinevox.png)

## PineNote

{{< credits "Author: Caffeine" >}}

Users have been enjoying their new PineNotes for a few months now and there has been a lot of good feedback. In fact, the device was used to write most of this community update. 

### Important - Software Update Issue

**"cannot proceed with upgrade" (as of Dec 11, 2024)**

Users running the factory firmware on their PineNote Community Edition will encounter an issue updating their system. This happens because Debian has moved `/lib`, `/lib64`, etc. to `/usr` and because the system still includes a `/lib64` symlink, attempting to update the system results in the `base-files` package failing to install.

You can fix this by removing the symlink by running `sudo rm /lib64` in your terminal (via SSH, UART, etc.). 

### Development updates

Since users have received their PineNote Community Edition devices, [various bug fixes](https://github.com/PNDeb/pinenote-debian-image/issues?q=is%3Aopen+is%3Aissue) and a [kernel update to Linux 6.12](https://github.com/m-weigand/linux/tree/branch_pinenote_6-12_v1) have been pushed. Users can update through the command line (using APT) or through the Gnome Software application. Xournal++ has also since been updated. 

Users wanting audio out (and other USB goodies) using the USB-C port will have to update their kernel manually currently. This can be done with this command in the terminal. **Though this is completely optional, as everyone will eventually get these updates soon.**

`sudo apt install linux-image-6.12.6-pinenote-202412310358-00187-g0aa6f8665258`

### PineNote Community Spotlight

#### Inkput

Inkput is a proof-of-concept software written by [s12wu](https://github.com/s12wu) that allows the user to enter text using handwriting. Inkput uses PellelNitram's handwriting recognition implementation to achieve this.

The program Inkput works by displaying on top of the user's desktop, then the user will write something in the box, select a text input and press predict. This will drop the written text into the text input like in the image below. 

![Image of the inkput demo](/blog/images/January_2025/inkput.png)

Contributions and testing is very much welcome! You can find the Inkput source code on GitHub: https://github.com/s12wu/inkput

#### Pinescreen

Pinescreen is a software whose purpose is to implement the features found in the Gnome extension to configure the e-ink display. Pinescreen is targeted at improving use on KDE Plasma. 

It's currently in early development, testing and contributions welcome! You may find the software here: https://gitlab.com/Poundex/pinescreen.

## InfiniTime 1.15

{{< credits "Author: JF" >}}

InfiniTime released [InfiniTime 1.15 "Ribes rubrum"](https://github.com/InfiniTimeOrg/InfiniTime/releases/tag/1.15.0) earlier this month! This release is packed with new features and improvements that we will take a look at in this section of the blog post.

![GitHub releases page](/blog/images/January_2025/release.png)

This is the first release in almost a year and one might wonder why it took so much time to finalize this new version of InfiniTime. Remember that InfiniTime is designed, built and maintained by "normal" people working on the project with their free time. Maintainers get busy with other projects and changes in their lives. As an example, I became a father a few months ago, and as you can expect, this has had a huge impact on the time I can dedicate to the project.

The team also has a strong focus on reliability and stability: we decided to delay the release by a few weeks to fix a few stability issues and regressions that popped during our testing. This, together with the very limited resources of the PineTime hardware, makes the development of the firmware a bit more tedious (but it's still a lot of fun :)).

Talking about the team: the core developers are happy to welcome [mark9064](https://github.com/mark9064) to the core developers team. Mark has been contributing to the project for many months now and among other things, made the Always-On feature possible in InfiniTime. 

Now, let's take a look at InfiniTime 1.15! A lot of users have been waiting for this feature for a long time now: the Always-On Display (AOD). Implementing this feature on the PineTime was quite a challenge, since the hardware is not designed for it. This is mainly because of the LCD display and its power hungry backlight. [@KaffeinatedKat](https://github.com/KaffeinatedKat) and [@mark9064](https://github.com/mark9064) however managed to make this possible by optimizing low-level drivers, fine-tuning some display settings and improving the state machine of the UI. Without going into too much details, the display is configured to use as little power as possible by reducing the number of colors that are displayed, by reducing its refresh rate and by driving the backlight using a PWM (Pulse Width Modulation) to its lowest visible level.

This was a complex feature to implement and review, but it was worth it: InfiniTime runs for 2 to 3 days in this mode! I'm honestly impressed by how comfortable the InfiniTime feels when this feature is enabled together with the Raise-to-Wake and Lower-to-Sleep features!

You can easily enable this feature in the settings (Settings → Display → Always On).

![Image of the AOD settings](/blog/images/January_2025/aod.png)

A new application was also integrated in InfiniTime 1.15: the weather forecast app. As you can expect, this app shows the weather forecast for the next 5 days in a nice and colorful way. This feature was contributed by [@vkareh](https://github.com/vkareh).

![Image of the new weather app](/blog/images/January_2025/weather.png)

You'll find it in the third page of the application menu.

![Image of the weather app in the launcher](/blog/images/January_2025/weather-menu.png)

The dice rolling app by [@yusufmte](https://github.com/yusufmte) is another new application added in this release. This app generates random numbers according to the number of configured sides. This app will come in handy for table-top players, among others.

![Image of the dice rolling app](/blog/images/January_2025/dice.png)

It's available in the 2nd page of the settings

![Image of the dice app in the launcher](/blog/images/January_2025/dice-menu.png)

Another highly requested feature is the persistent alarm. Previously, your alarm setting would be lost when the watch reboots, after an update for example. Thanks to [@NeroBurner](https://github.com/NeroBurner), the setting is now saved in the configuration file to ensure that the alarm will be restored the next time the watch reboots!

The [list of changes](https://github.com/InfiniTimeOrg/InfiniTime/milestone/15?closed=1) is so long that I cannot detail all of them in this blog post. Let me just mention that the header [README](https://github.com/InfiniTimeOrg/InfiniTime/blob/main/README.md) file was redesigned, the default year (in the date/time) setting is now automatically set to the current year of the build, the color inversion bug is now fixed and that the lower to sleep algorithm has been improved by checking the wrist angle. Please check the [release note](https://github.com/InfiniTimeOrg/InfiniTime/releases/tag/1.15.0) to see the complete list of changes and additions!

![Image of the changes for 1.15](/blog/images/January_2025/changes.png)

I would like to take the opportunity to thank everyone who contributed to this release of InfiniTime. It contains a lot of features and improvements that greatly improves the experience for many users!

## Pinebook Pro

{{< credits "Author: Caffeine" >}}

The Pinebook Pro is no longer in production and will therefore no longer be stocked on the PineStore. This is due to the switch of focus to the PineTab and the PineNote line of devices. 

There are plans to continue the Pinebook series, and it will return in the future when a suitable SOC is chosen. 

## Community content

### PineNote CE first month review

{{< credits "Author: Caffeine" >}}

I recently received my PineNote at the end of November, it's been really nice to use. This month, I wrote the blog post on the PineNote using my Logitech Bluetooth keyboard. 

![Image of my PineNote](/blog/images/January_2025/camdens-pinenote.jpg)

I managed to get everything to work well out of the box, the pen responsiveness is very good, I have had no trouble drawing or writing using the included Xournal++ application. The 4GB of included memory is enough to have many applications open, including a web browser, music player and my document opened in LibreOffice. The included software and changes made to the system help the PineNote to be a usable device. There is a Gnome extension for controlling the display and manually refreshing the screen, along with a custom shell theme to help with visibility. One thing I also noticed is how good the battery life is. I can have it sleeping for nearly a week and I can easily get around three days of usage out of it while writing and browsing the internet.

The big thing for me so far is the fact there is no MicroSD Card slot included with the device. The device has a very specific partition structure right now and I'm afraid to change anything. If I brick my device I feel like I would need a lot of help compared to something with the PinePhone which is easy to flash. The part that makes it difficult is that a user must use the included magnet tool or serial adapter, then flash the device and find the waveform files for your specific PineNote batch. Both devices have different waveform files due to different displays. These are not included in the Debian images if you want to re-flash, so you're required to download them. 
I'm sure things will get better in the future for PineNote recovery, but right now I'm afraid that I'll eventually brick the device. 

Overall, I am happy with the experience of my PineNote so far. The performance is good, the screen is nice and I haven't faced any major issues (that haven't already been fixed ;) ). I will likely be back with a more thorough review in 6 months after I have discovered the quirks of the device and using as my primary note-taking device for a while. 

## Want to contribute to the next community update?

Do you have a cool project that you're working on you'd like to be mentioned? Is there something you're interested in that you'd like to write about related to Pine64? If you're interested, please contact us!

- Camden/CarbonatedCaffeine: 
  - @carbonatedcaffeine (Discord)
  - @endernightlord:matrix.org (Matrix)
