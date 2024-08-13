---
title: "September update: Hurdles and Successes"
date: "2021-09-15"
authors: ["Lukasz Erecinski"]
categories:
  - "community"
  - "cube"
  - "news"
  - "pinenote"
  - "pinephone"
  - "pinetime"
tags: 
  - "devzone"
  - "pinecube"
  - "pinenote"
  - "pinephone"
  - "pinetime"
cover: 
  image: "september-update-banner.jpg"
images:
  - "/blog/images/september-update-banner.jpg"
---

![](/blog/images/september-update-banner.jpg)

In this community update we’ll discuss PinePhone keyboard progress (and hurdles), add-on back cases awaiting developers approval, initial PineNote impressions and early development progress, as well as news of InfiniTime 1.4 release and a guest post about PineCubes as a part of a security system. We also have an announcement for our community developers: we will be introducing bounties to the DevZone. 

We’ve got some exciting things in the works that I am aching to share with you, so if you haven’t done so yet, now is the time to subscribe to this blog.  

You can watch the synopsis of this month’s community update on YouTube (embedded below) as well as on [Odysee](https://odysee.com/@PINE64:a) and [PeerTube](https://tilvids.com/accounts/pine64tilvids/video-channels). To stay up-to-date with PINE64 news make sure to subscribe to this blog (subscription widget at the bottom of the webpage), follow [PINE64 Telegram News channel](https://t.me/PINE64_News), the [announcements channel in Discord](https://discord.gg/pine64) as well as our [Twitter](https://twitter.com/thepine64) and [Mastodon](https://fosstodon.org/@PINE64).

I’d like to thank [JF](https://twitter.com/codingfield), [Alex](https://twitter.com/AlexRob12252696) (clover), [Caleb](https://twitter.com/calebccff), [Martijn](https://twitter.com/braam_martijn), [Danct12](https://twitter.com/RealDanct12), [Chris](https://twitter.com/seeteegee) (newton688), [Brian](https://mastodon.online/web/accounts/61817) (33YN2) and [PizzaLovingNerd](https://www.youtube.com/channel/UCmGcm7dhEjS9CIOsOOv8y6w) for their contributions to this community update.

**N.B.** Comments on the blog post need to be in English and follow our [Community Rules and Code of Conduct](https://forum.pine64.org/showthread.php?tid=13209). 

{{< youtube id="DAyL7dXLM_s" >}}

**Video synopsis of the community update**

**TL;DR**

- Housekeeping
    - DevZone internal testing concluded and roll-out already started
    - DevZone to introduce bounties in near future
    - Hosting cluster maintenance is underway; Gamiee is writing a public log about the process
    - PineTalk podcast is coming back this month! 
    - Permissible usage of the PINE64 logo and brand name; PINE64 merch in the works (by third party)
-  PinePhone 
    - Two years since PinePhone dev units went on sale
    - Keyboard production hurdles - a detailed account of why we don’t have an availability date yet
    - Summary of the keyboard’s production firmware features and capabilities   
    - Back cases awaiting developers to green-light 
    - Waydroid is shaping up nicely \[by Danct12\]
    - Megapixels 1.3 released - the PinePhone now takes much nicer-looking photos \[by Martijn Braam\]
- PineNote
    - Detailed first impressions of the PineNote; very impressive hardware, not much to complain about, perhaps apart from the cover (which will be improved in the future)
    - Early development status report (thanks to Caleb); once Linux boots on the PineNote, there is a good chance for much of core functionality to work  
    - PineNote production is on-track, and dev/ early adopter ought to be available late October
- PineCube 
    - A guest post by Chris (newton688) about using two PineCubes as a part of a security system; detailed information about the setup and functionality
- PineTime
    - Release of InfiniTime 1.4 marks the 1000th project GitHub commit
    - Huge number of infiniTime improvements and bug fixes; end-users can now also customise the look and feel of default watchface
    - WaspOS supports new accelerometer and brings a number of improvements
    - iOS and Ubuntu Touch companion apps compatible with InfiniTime now available; Infini-iOS app now installable via Apple’s Testflight 
- PineDio 
    - Development progress report and debugging of PineDio Stack by FJ and Lup
    - JF managed to get InfiniTime running on the BL604 SoC as well as used an e-paper display with the Stack; Lup successfully connected to a LoRa gateway
    - Debugging revealed some hardware issues; a revised mainboard in the works

## Housekeeping

Late last month we announced that the DevZone was being made ready for internal testing - over the past four weeks we’ve gathered a lot of feedback from developers and improved DevZone’s core systems. The platform has now reached a point where we feel happy to accept more participants aboard: the review process of the applications has already begun, and some developers may already have received invitations to set up their accounts by the time this post goes live. The opening up of the DevZone will be gradual, so if you don’t receive an invitation to set up an account at this time then do not worry. For those of you who don’t know of the DevZone development system platform, and wish to learn about it or are considering [signing up](https://devzone.pine64.org/signup.php), I invite you to read the [July update](https://www.pine64.org/2021/07/15/july-update/)’s housekeeping section for more details. 

But this isn’t the end of DevZone news. Once the system is populated with developer accounts, we will be introducing bounties to the platform. Only developers on the DevZone will be eligible to accept a bounty once it gets posted. There will be both global (open to all developers) and group-specific bounties. Since the vast majority of people reading the community updates aren’t developers, let me provide a two-line explanation of what bounties are: bounties are a way to incentivise development and expedite problem-solving by providing a financial incentive. Such bounties usually apply to things that are difficult to solve, hard to implement or otherwise pose a significant challenge. In short, developers receive a one-time payment for solving a problem or implementing a missing functionality. The Pine Store has committed to putting up a substantial sum of money for the bounties and we hope this will help the DevZone thrive. More information about the bounty system will follow on DevZone's global forum.

![](/blog/images/devzonesignup-1024x520.png)

**DevZone [sign-ups](https://devzone.pine64.org/signup.php) will remain open indefinitely**

In other news, [PineTalk podcast](https://www.pine64.org/podcast/) is coming back after a two-month hiatus! The community-ran show that focuses on PINE64 news and related topics will resume shortly with new hosts and a reworked schedule. As it has been explained to me, the plan is to have an episode dedicated to discussion of news and the following one to community and partner-project topics. PineTalk is available on most popular streaming platforms such as [Spotify](https://open.spotify.com/show/4IXVMkSMAxsuLzIXuKI3IJ) as well as on our [YouTube](https://www.youtube.com/c/PINE64inc) and [Odysee](https://odysee.com/@PINE64:a) channels. A dedicated post announcing the return of the PineTalk and introducing the new hosts will go live shortly - stay tuned to learn more. If you haven’t done so yet, make sure to subscribe to the show’s [RSS MP3 feed](https://www.pine64.org/feed/mp3/). 

![](/blog/images/PineTalk-logo.png)

**New PineTalk logo by [Julius Guthunz](https://github.com/Julius-Gu/pinetalk-artwork)**

Earlier this month Gamiee posted the [first entry in a series](https://www.pine64.org/2021/09/01/clusters-build-log-moving-to-temporary-cluster/) about the maintenance of our hosting cluster. For those of you who don’t know, we self-host all our community infrastructure and services, including this website, on our own hardware - you can learn more about it from the [original post](https://www.pine64.org/2020/06/05/rockpro64-cluster-move-june-5-10/) about the move to the cluster. Gamiee’s first post explains the reasons for the maintenance, discusses the planned upgrades and showcases the temporary setup currently in use. It is a series I know many in the community have been waiting well over a year for, so I strongly suggest you check back regularly to follow the hosting cluster’s journey from the workbench back to its rightful place in BBXNET’s server room.  

Lastly, I want to touch upon a topic that I get asked about on a regular basis - namely, the use of the PINE64 logo and brand name in both community and commercial projects. We have [detailed guidelines](https://wiki.pine64.org/wiki/PINE64_brand_and_logo) for the use of the PINE64 name and logo on the main Wiki page (which also includes a [media kit](https://wiki.pine64.org/images/1/10/Pine64-logos.zip) with assets in .svg format; this too is something I’ve been asked about recently). As a side-note on this topic - we’ve been contacted by community members interested in creating PINE64 ‘swag’ and have agreed to grant them the opportunity to create and sell unique designs. Needless to say, neither PINE64 nor the Pine Store will be profiting in any way from this. I hope you’re as excited as we are to see the ‘swag’ - personally, I am looking forward to starting my day with a cup of coffee in a PINE64 mug. 

## PinePhone

It has now been two years since the very first PinePhones entered production. Shortly thereafter, in November of that year, we shipped PinePhone developer units fitted with the first PCB revision and began preparing for production of Braveheart units. The PinePhone has gotten us - the mobile Linux community as a whole - far in a short amount of time, and made the dream of a mobile Linux possible for tens of thousands of people. I felt this was worth a quick mention on the PinePhone’s second anniversary. If you feel as nostalgic as I do, or simply want to see a very cool transparent PinePhone prototype, then I invite you to read the [September update blog entry of 2019](https://www.pine64.org/2019/09/05/september-update-the-pinephone-is-real-shipping-soon/).  

**PinePhone Hardware**

These past couple of weeks were effectively a race to deliver a finalized revision of the keyboard firmware and have it successfully flashed on the factory floor. The details aren’t important, but suffice to say that getting the firmware shipshape and flashed using a factory programmer proved to be a time consuming undertaking for both [Megi](https://xnux.eu/log/) and the product team. What is important, however, is that it all turned out well in the end, and on September 6th version [1.1 of the keyboard’s firmware](https://xff.cz/kernels/pinephone-keyboard-1.1.tar.gz) was successfully installed using factory tools. When I initially started writing this text, some week ago, I expected to provide you with a timeline for production and the eventual availability date for the keyboard. However, this monday the vendor reported that the keyboard factory test image doesn’t recognize the production keyboard. As it turns out, due to last minute changes made to the firmware, the factory test software (a custom build of postmarketOS by [Martijn Braam](https://twitter.com/braam_martijn)) no longer works. This temporarily stalled the production process. At the time of writing, Martijn and Megi are still trying to figure out a software work-around so that production can get back on-track. When manufacture (re)starts later this month I’ll make sure to provide you all with an update, which will hopefully include an availability date.

![](/blog/images/keyboard-flat-Martijn-1024x327.jpg)

**Did you know that the keyboard can be fully extended for thumb-typing? - [picture by Martijn Braam](https://twitter.com/braam_martijn/status/1425837278757228555/photo/1)**

As for the final version of the firmware that ships on PinePhone’s keyboard, I am happy to say that it is more than we could have hoped for. It allows users to customise their keys, including the modifiers, in nearly unlimited ways via [supporting utilities](https://xff.cz/git/pinephone-keyboard/tree/). This effectively means that users will be able to set their prefered layouts and alter key behaviour without needing to flash a custom version of the firmware to the keyboard’s controller - how cool is that? You can also physically relocate all keys, bar _return_ and _space_, to correspond to your chosen software layout. The reason I advise you to leave the _return_ and _space_ in their respective places is because the tiny hooks that hold onto the metal stabilizers can be finicky and easily broken if not handled properly. Besides, it's not like you can place these keys elsewhere on the board. Lastly, the firmware is now able to report charge status of the internal battery to the PinePhone’s operating system - a critically important feature following the (correct, in my opinion) decision to remove charging status LEDs.    

Before moving onto discussing other topics, I’d like to thank community members who helped translate the [keyboard quick start manual](https://files.pine64.org/doc/PinePhone/USER_MANUAL-KEYBOARD-V2-EN-DE-FR-ES.pdf) into German, French and Spanish. You guys rock.  

![](/blog/images/cases-side-small-1024x384.jpg)

**From the left: stock PinePhone; PinePhone with fingerprint reader; PinePhone with wireless charging; PinePhone with keyboard attached**  

The PinePhone back cases with wireless charging and the fingerprint reader are now ready and awaiting developers approval. As soon as the cases get green-lit you’ll see them appear in the Pine Store. I finally had the opportunity for some hands-on time with both of the cases and I must say I really like how they turned out. For one, they match the PinePhone’s overall aesthetic perfectly: when mounted, they look like a natural part of the assembly. Admittedly, they do add a bit of bulk to the back of the PinePhone (but not the sides) - approximately as much as the hard protective case - but at no point during my few-day-long usage of the PinePhone with the wireless charging case fitted did I feel it was unnatural or too hefty. Something that pictures cannot convey is that the finish on these cases is really nice. They share a similar coating to that used on the PinePhone’s keyboard. What this means in practice is that not only do they feel very sturdy, perhaps due to the internal reinforcement grid, but are also significantly less likely to attract fingerprints than the default back case. The wireless charging case works fine with the desktop PinePower - I’ll likely end-up using it with my phone that isn’t fitted with the keyboard. If you’re interested in picking up a back case as soon as possible, please keep a close eye on our social accounts and news channels. 

**PinePhone Software** 

[_Waydroid_](https://github.com/waydroid/waydroid) _by Danct12_

In the past weeks, I've been working on packaging Waydroid to Arch Linux and I have released one of the test packages to the community (which also ended up in the Manjaro repository). That test package required some fiddling around with boot arguments and, even when you get it to work, it has all kinds of issues such as inverted colors and app stability. Since then the Waydroid team made a lot of progress, making app crashes to be less frequent and color formatting displaying correctly on the PinePhone. The performance is now quite comparable to Anbox - in fact, I find that Waydroid works better than Anbox! Regardless, the project is still relatively new and there is a lot of room for future improvements. Hopefully you'll see Waydroid in our PINE64-Arch repository very soon. I leave you with a short video of the PinePhone running Subway Surfers.

https://www.youtube.com/watch?v=bG0uAQqeqW4

**Android game running under Waydroid on the PinePhone**

[_Megapixels_](https://git.sr.ht/~martijnbraam/megapixels) _1.3.0 by Martijn Braam_

Megapixels had a new release and is now at version 1.3.0 - the major change in this release is more contrast in the post-processing script, which results in pictures with more vivid colors and being more ‘contrasty’. Work is being done to make the amount of this processing being applied configurable through the Megapixels settings.

![](/blog/images/mxpixels13-frompmos-1024x768.jpg)

**Picture taken on PinePhone with Megapixels 1.3 - [image via postmarketOS](https://postmarketos.org/blog/2021/09/13/v21.06.2-release/)**

## PineNote 

In case you live under a rock and missed [last month's announcement](https://www.pine64.org/2021/08/15/introducing-the-pinenote/) of the PineNote, then I invite you to read it before continuing on with this section. PineNote production is on-track, and we expect to have **development and early adopter units in the Pine Store next month.** I’ve now had the PineNote development unit for a little over two weeks, so I thought I’ll start this section by sharing my initial impressions of the hardware. Obviously, I am hardly impartial in my assessment, but I believe my opinions closely echo those of devs who received their units. Also, in full disclosure, I am using a factory test build on my device for testing purposes. The device itself is what most people will probably find ‘just the right size’ - at 10.3” it is plenty large for reading and writing while also being comfortable to lug around in a backpack. It is relatively light and feels natural to hold, and at no point did I feel that it is bulky or unwieldy. The construction is really sturdy and the plastic bevel and back have a good feel to them. One gripe that I have about the plastic back is that it is a fingerprint magnet, which likely won’t matter too much since you’ll likely want to use a cover. The minimalist and industrial look of the entire device makes it look more like a work tool than a gadget, which is a good thing in my book.

![](/blog/images/Priduction-pn-back-788x1024.jpg)

**See the faint circle, right of the PINE64 logo? - placing the EMR pen (or a magnet) down there enables recovery and debugging**

The display is downright great. The contrast is excellent, even when compared against some e-paper industry giants’ offerings. Mind you, such a crisp image is achieved despite the e-paper display being housed under two layers of digitizers (Wacom, for the EMR pen, and a regular capacitive panel for finger input). The white and amber front light is really good; it lights the entire panel evenly and is extremely bright, even to the point of being visible in broad daylight, but it can also be turned down very low for reading in dim or dark spaces. Under the factory build of Android, which I’ve been testing the device with, the EMR pen’s responsiveness is very good - I’d say close to instant. I truly hope that a similar level of pen input responsiveness can be achieved under Linux in the future. Speaking of writing, I like the default stylus - it is really well built, well balanced, has a solid heft and provides a good writing sensation. 

![](/blog/images/PN-screen-1024x576.jpg) ![](/blog/images/PN-backlight-1024x576.jpg)

**Left - PineNote inside without frontlight / right - PineNote amber frontlight in direct daylight**

While I am very pleased with the device, it would be unfair of me not to mention things that I am not thrilled about (thankfully there are only two things to mention). I am not a fan of the cover - it is mechanically perfectly capable, it is light, thin and does the job, but despite looking nice it doesn’t feel good in the hand. It is now too late in the manufacturing process to change the design, but in the future we’ll surely redesign the cover or at least improve the feel of the material it is built from. Secondly, if you aren’t using the cover, which has an embedded magnet corresponding to the one in the EMR pen, the pen doesn’t have a way to attach to the PineNote. Again this isn’t exactly a massive issue, because I suspect most people will always want to house their device in a cover, but I felt that it was worth mentioning regardless.  

I also have an update regarding the current status of Linux development for the PineNote. I’ve spoken to [Caleb](https://twitter.com/calebccff) to get a sense of how things are going, and here is a summary of what they had to say. Work is simultaneously done on the u-boot, the e-paper panel and the Linux kernel. All the above are obviously directly interconnected, but it appears to me that there is an informal division of labour among the devs. Caleb has been looking into u-boot and the e-paper panel (more specifically, how to initiate it on Linux) because they believe that u-boot is responsible for loading the waveform data that enables panels functionality, quote “_I'm currently working on porting over the parts of the e-ink drivers which are open source to mainline, then I'll try to fill in the blanks using u-boot as a guide with the end goal of being able to get basic framebuffer support. I think the downstream u-boot is responsible for loading the waveform data and passing it to the kernel, given CounterPIllow and I have the exact same waveform data, if we can verify that other people do as well (...) then we can instead put the data in /lib/firmware and have the kernel load it like it would any other firmware”._

However, to test whether this will actually work, developers will first need to get Linux booting on the PineNote. As Caleb explained to me, [pgwipeout’s](https://twitter.com/pgwipeout) Quartz64 kernel does work, and even boots, but gets stuck being unable to detect eMMC flash. This is likely a trivial oversight, and I am sure that it will be sorted out swiftly. If Caleb is right in their assumptions about how to initialize the e-paper panel, then there is real hope that we can get an image output soon after the device boots Linux for the first time. This, in combination with Wacom and the capacitive digitizers being already mainlined, means that there is a real chance for a lot of basic functionality being available to developers soon. The road ahead is obviously still very long, but the first steps are highly encouraging and I cannot wait to see how far the project progresses this year. I’ll make sure to bring you a steady stream of PineNote development updates on a monthly basis as I’ve done in the past for our previous devices. 

## PineCube by Chris ([newton688](https://twitter.com/seeteegee))

For the last several weeks we've been busy with the latest PineCube project, which is to set up two and eventually three PineCubes as security cameras both inside and outside the house. As a starting point the first cube was imaged with the pre-built Armbian from the wiki: Linux Kernel 5.11, Motion and GStreamer capabilities. This cube connects automatically to the local WiFi and is powered using a micro USB cable and an off the shelf power supply. Anyone in the trusted local network can see the camera from a web browser through the motion tool at pinecube1:8080. Also, we can put it wherever it is needed, including monitoring the solar panel charge controller status from time to time.

![](/blog/images/solar-monitor.jpg)

**Solar monitor feed**

Motion can be configured to record short MPEG-4 video clips when it detects motion and to save a recording to a file internally. We expanded on this by posting the recordings to a private Matrix channel on a private server so that access can be controlled and notifications can go out to different people on different devices. This setup also serves as an off-site backup. This has turned out to be a versatile indoor unit that serves a variety of purposes. Attention has turned to how to support outdoor units.

Mounting the PineCube outdoors has some unique challenges. How do you get power to the unit? The WiFi may not be as reliable outdoors depending on weather conditions. Also, the weather, such as rain and moisture can affect the electronic components. Using PoE helps to solve the first two problems. Our existing networking equipment has active PoE so we went with that system, but it required an extra PoE splitter dongle to separate USB power from ethernet since the PineCube currently supports only passive PoE. To protect the device from water and humidity the unit needs to be sealed with something transparent that doesn't distort the image. We found an acrylic dome of a large enough size to hold both the PineCube and the PoE splitter and used painted plywood as backing and shelving material. The unit will be sealed completely using a caulking compound that has yet to be sourced, likely a silicon compound. We will be testing the electronics beyond its specified limits in the next six months as the winter could bring temperatures below -30C. Fingers are crossed.

![](/blog/images/outdoor-enclosure-rotated.jpg) ![](/blog/images/outdoor-mounted-768x1024.jpg)

**Left - A look at the internals // right - outside mount on wall**

This second PineCube is accessible from the internal network in the same way as the first using Motion's web interface. The resolution was increased to 1280x720 to provide better detail, but this increased the processing power required to capture videos making them very laggy. The tradeoff was acceptable in our case and so we disabled motion capture on this device. Also, with this device we decided to learn more about Armbian and so this one was installed directly from the official Armbian community supported image and installer, which required access to the console over UART, which can be done with the PinePhone/PineBook Pro USB headphone jack UART devices or other means described on the wiki. The kernel version is 5.10 and the version of Motion is older, but still usable until the next version of Debian brings in the newer software.

![](/blog/images/pool-monitor-1024x576.jpg)

**Image from the PineCube**

There are a number of image controls that can be adjusted using the v4l2-ctl command-line tool, such as horizontal flip, colour balance, saturation and hue. There are also some test patterns built into the sensor that may be helpful in calibrating these.

![](/blog/images/colour-balance-1024x576.jpg) ![](/blog/images/saturation-1024x576.jpg)

**Image adjustments examples using v4l2-ctl**

There's also an infrared filter for the sensor and the PineCube's front board has a deck of four IR LED's. They can work indoors and at close range to pick up objects, but our outdoor unit will require some adjustments before this could be effective at night. The sensor is currently set back from the acrylic dome too far and there is some glare from the LED's. Also, the Green power LED is causing some glare too and that needs to be resolved, perhaps with removal of that one LED. Details of how to enable/disable the IR cut filter and the LED's can be found in the Wiki.

![](/blog/images/infrared-1024x576.jpg)

**PineCube image with infrared**

As we add more cameras to our network, monitoring and managing them will be more time consuming. This is why we installed Prometheus extractors on them so that we can collect all sorts of data and monitor them using Grafana dashboards along with the other machines that we have on our network. Monitoring pending upgrades to Debian will require some more work since the CPU power required to check for packages to upgrade can sometimes interfere with the video capture operation. This might be resolved with a short scheduled daily outage. Meanwhile, this is done manually from time to time.

## PineTime (by JF)

The momentum around the PineTime project does not slow down, quite to the contrary, Wasp-os and InfiniTime keep on receiving much feedback from users alongside contributions from developers. Moreover, the ecosystem of companion apps is constantly growing, and now encompasses most computer and mobile operating systems. It is amazing to see so much activity around this project we started almost 2 years ago. 

Let's start with [InfiniTime 1.4](https://github.com/JF002/InfiniTime/releases/tag/1.4.0), which was released a few days ago. This version is highly symbolic, as the very last commit of the release was exactly the [1000th commit](https://github.com/JF002/InfiniTime/commit/6f9f0e8b0e42a5526d47ca664534fb6b0ccb6ace) to the project!

![](/blog/images/1000th-commit-1024x310.png)

**1000(!) InfiniTime commit**

The release comes with a reworked touch driver, which improves the reliability and responsiveness of the touch panel. I'm really impressed by this contribution by [Riku Isokoski](https://github.com/Riksu9000), which helped reduce the latency of the touch interface to nearly zero, really improved the user experience in many apps: the setting of the timer is now as fast as it should be, the Paddle and Twos games are a lot more pleasant to play, and the whole UI feels snappier and faster than before. Another nice feature of InfiniTime 1.4 _Pink Grapefruit_ which users will surely appreciate is the color picker feature for the PineTimeStyle watchface. You can now unleash your creativity and customize your favorite Pebble-inspired watchface!

![](/blog/images/092021_infinitime14_3-768x1024.jpg) ![](/blog/images/092021_infinitime14_4-768x1024.jpg)

**Left - _Quick Settings_ menu // Right - customization options of the default InfiniTime watchface - [images via Nico's blog](https://www.ncartron.org/infinitime-14-pink-grapefruit-touch-ui-and-battery-level-improvements.html)**

As always this new version brings many other improvements, such as better phone call notifications and better battery level monitoring, as well as bug fixes (we've hopefully fixed the bootloop issue). Nico provides a nice overview of this release in [his article](https://www.ncartron.org/infinitime-14-pink-grapefruit-touch-ui-and-battery-level-improvements.html) if you’re interested for an in-depth look.

WaspOS has also seen a few major changes since last month. Support was added for the new BMA425 accelerometer that is found in newer PineTimes, the weather app has had a fix for crashes and a bug that caused it to show incorrect values, a workaround has been made to prevent gcc-11 from building bricked WaspOS bootloaders, there is a bugfix for the wasptool OTA command, and the values for the heart rate sensor have been adjusted for more accurate readings of the heart rate.

Last month, I announced that 2 iOS companion apps were in the works. This month, I'm happy to announce that Infini-iOS released 2 beta versions 0.8.0 and [0.8.5](https://github.com/xan-m/Infini-iOS/releases/tag/0.8.5), which are now available for testing on iOS. This application is very new but already provides many functionalities like time synchronization, displaying the heart rate value, battery level monitoring, OTA updates and more. This version is available for installation via Apple’s [Testflight](https://testflight.apple.com/join/Z7u1Jxp4) - feel free to try it out and provide feedback to the author if you own an Apple device.

Go developers will be happy to learn that a Go [library](https://gitea.arsenm.dev/Arsen6331/infinitime) and a [daemon](https://gitea.arsenm.dev/Arsen6331/itd) to interact with the PineTime are now available. The "itd" daemon comes with a command line interface (itctl) and a GUI frontend (itgui) which allow users to sync the time, receive notifications, control music playback, get info from the watch and many other functionalities.

Last but not least, I came across a new PineTime companion app for [Ubuntu Touch](https://forums.ubports.com/topic/6127/smartwatch-sync-app). Many UBports community members were requesting such an app, and I'm happy that [jiho](https://forums.ubports.com/user/jiho) started working on [uwatch](https://gitlab.com/jiiho/uwatch) - a smartwatch sync app for Ubuntu Touch that supports the PineTime running InfiniTime. It will work on the PinePhone as well as any other device running Ubuntu Touch. 

## PineDio (by JF)

In July I introduced you to the PineDio Stack, a development kit built around the Bouffalo BL604 RISC-V MCU, which provides many onboard features such as the SX1262 LoRa module, an SPI flash memory, a LCD and touch panel, as well as a motion and heart rate sensor. In my opinion, the Stack is a really nice board that could serve as the basis of many future projects at PINE64!

![](/blog/images/JFssetup-1024x768.jpg)

**JF's PineDio Stack setup looks awesome! - [via Twitter](https://twitter.com/codingfield/status/1437868074879930371)**

Since last month, [Lup Yuen Lee](https://twitter.com/MisterTechBlog) and myself have done many tests on the first prototypes we received a few weeks ago with the goal to provide as much feedback as possible to the PINE64 team so they can design the best hardware for the Stack. And we have some great news to share: [I was able to run an e-ink demo](https://twitter.com/codingfield/status/1431541455210913792?s=20) as well as a [stripped down version of InfiniTime](https://twitter.com/codingfield/status/1436609097344995334?s=20) on that board. Lup, on the other hand, managed to [connect to a LoRa gateway](https://twitter.com/MisterTechBlog/status/1436128755987058691?s=20) using the onboard Sx1262 LoRa module.

{{< youtube id="GWg4BQndVQQ" >}}

**InfiniTime running on the PineDio Stack**

As usual in the engineering world, not everything works the first time, and we've noticed some issues with the JTAG debugging port and the LCD controller. If you are interested in the debugging process of this board, I encourage you to [read this article by Lup Yuen Le](https://lupyuen.github.io/articles/pinedio)e detailing the entire process. Lup provides many details about the techniques and tools we put in place to debug the LCD controller. As a result of this exploration the product team is now preparing a new version of the board, and I hope we'll be able to provide more good news very soon!

That is all for this month!
