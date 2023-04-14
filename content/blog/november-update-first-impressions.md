---
title: "November update: first impressions"
date: "2021-11-15"
categories: 
  - "cluster"
  - "community"
  - "news"
  - "pine64-community"
  - "pinedio"
  - "pinephone-pro"
  - "pinetime"
  - "soquartz"
tags: 
  - "keyboard"
  - "pinephone"
  - "pinephone-pro"
  - "soquartz"
cover: 
  image: "NovUpdateHeader.jpg"
---

![](/blog/images/NovUpdateHeader.jpg)

Is it truly November already? Is it just me, or is this year flying by at warp speed? This month’s update focuses on initial impressions of the PinePhone Pro and production keyboard. We're also going to take a look at the SOQuartz Blade hostboard and discuss InfiniTime 1.7 release. 

But before we get into it; next month I plan on doing a recap of the year 2021, similar to the one from [last year](https://www.pine64.org/2020/12/15/december-update-the-longest-one-yet/), so make sure to stay tuned for that.  

You can watch the synopsis of this month’s community update on YouTube (embedded below) as well as on [Odysee](https://odysee.com/@PINE64:a) and [PeerTube](https://tilvids.com/accounts/pine64tilvids/video-channels). To stay up-to-date with PINE64 news make sure to subscribe to this blog (subscription widget at the bottom of the webpage), follow [PINE64 Telegram News channel](https://t.me/PINE64_News), the [announcements channel in Discord](https://discord.gg/pine64) as well as our [Twitter](https://twitter.com/thepine64) and [Mastodon](https://fosstodon.org/@PINE64).

I’d like to thank [JF](https://twitter.com/codingfield), [Alex](https://twitter.com/AlexRob12252696) (clover), [Brian](https://mastodon.online/web/accounts/61817) (33YN2) and [PizzaLovingNerd](https://www.youtube.com/channel/UCmGcm7dhEjS9CIOsOOv8y6w) for their contributions to this community update.

N.B. Comments on the blog post need to be in English and follow our [Community Rules and Code of Conduct](https://forum.pine64.org/showthread.php?tid=13209).

{{< youtube id="Ta2y6v7AnKw" >}}

**Community update video synopsis**

**TL:DR** 

- Housekeeping
    - We’ve made efforts to curb spam in the chats, you should be seeing less of it from now on
    - We’re considering making an in-person PINE64 community meetup mid-2022, would you attend? 
- PinePhone Pro
    - Dedicated this month’s section to first impressions of the PinePhone Pro 
    - A look at small previously undiscussed design changes from OG PinePhone
    - SoC does run warmer than OG PinePhone’s, but heat doesn’t transfer to person using the phone
    - Its fast, very fast 
    - Packaging from recycled cardboard and plastic 
- PinePhone (Pro) keyboard
    - Available next month for $49.85
    - We’re fixing membranes (again) following feedback from early production units
    - Initial impressions of hardware - quite a few things changed since prototypes
    - Open firmware works out-of-the-box on OSes that support it
- SOQuartz
    - In case you missed it, the SOQuartz launched last month
    - Introducing the third SOQuartz hostboard - the Blade 
    - Blade hostboard to be used in 1U server racks; can be stacked for clustering
- PineTime
    - Release of InfiniTime 1.7 
    - New motion sensing allows for faster wake-on-lift 
    - New motion sensing can be used as a motion controller; someone interested in making a game?  
    - Step data now being tracked in Amazefish and other apps; and many other optimizations
    - New members joins the team
- PineDio
    - Ongoing development report - a dev update
    - New OS image with Chirpstack LoRaWAN stack and TTN support available 
    - New PineDio STACK prototypes on the way 

## Housekeeping

Not unlike most other online communities, we’ve been waging war with spammers for some time. Spam is, and likely will always be, a part of chats and forums, and while it is always annoying (and sometimes offensive), until recently it was merely a nuisance rather than a plague. These past 8 weeks, however, the volume of spam across different chats significantly intensified, which resulted in [Matthew (fire219)](https://twitter.com/fire219_SIMPL) spending much time on dealing with the situation. We now have a fairly robust multi-faceted system on each of the platforms, which insofar seems to be doing a good job at keeping automated spam and unwanted accounts out of our community. While no system is 100% foolproof, you will see much fewer spam in the chats from now on.  

As most of you know, we usually make FOSDEM our yearly PINE64 community get-together. This year FOSDEM has once again made the decision to make the event virtual, which has prompted us to consider scheduling a dedicated PINE64 meetup in 2022. We’re thinking about the May-July timeframe, somewhere in the heart of Germany. How many of you would / could attend this event? Please let me know by answering [this forum poll.](https://forum.pine64.org/showthread.php?tid=15335&pid=102803#pid102803) If enough of you declare interest, then by next month I’ll try to schedule something together with [TL Lim](https://twitter.com/TLLim888). Before anyone asks - the meetup will surely also have a virtual component for our community members in Asia, North/ South America and Oceania; I know that pancontinental travel is still difficult or outright impossible for some. 

Lastly, I’m aware most of you read the [October update](https://www.pine64.org/2021/10/15/october-update-introducing-the-pinephone-pro/) introducing the PinePhone Pro, but some of you have likely missed the [follow-up](https://www.pine64.org/2021/10/29/october-update-follow-up/) I wrote late last month. I suggest you go back and read it as it contains some information that will contextualize a few of the things I write in this community update. The follow-up also included news about the PineDio, the PineNote and an announcement that the SOQuartz compute module is now [available for sale](https://pine64.com/product-category/soquartz/) - give it a read. 

## PinePhone Pro

First, a quick note for developers. We closed the PinePhone Pro pre-orders two weeks ago since the number of applications far exceeded available dev units. We’re hoping to start issuing coupons this week. The reason for the delay in issuing coupons was a mainboard layout issue with the pogo pins, which was identified during QA. A fix for this was quickly found, but all PCBs had to be returned to the factory - hand soldering on all units would be too time consuming. This should not affect our December shipping time-frame, nor the _Explorer Edition_. This does, however, limit your pre-order coupon validity window - from the moment you receive the coupon you’ll have 3 days to finalize your purchase. I’ll notify everyone when coupons start going out, so you know to check your email inbox regularly. Keep an eye on the Telegram/ Discord news channels and our Twitter/Mastodon accounts. 

This month, I have dedicated this section to my first impressions of the PinePhone Pro. At the time of writing I’ve only had the device for two days, the first of which I spent debugging an issue with the touch controller. Megi was able to patch the issue quickly however, and I haven’t been able to put the device down since. Obviously everything I am about to write is fundamentally biased, but I will stand by every word I write - no PR-speak, I promise. The device is fast, very fast when compared to the original PinePhone and other similar devices. I haven’t tried Linux on a recent mid-to-high end Android smartphone, and I am curious how the experience stacks up against something like the One Plus 6 in the UI. Judging [Caleb](https://twitter.com/calebccff)’s videos of the OnePlus 6T, the UI’s responsiveness is indistinguishable from the PinePhone Pro. I’m sure they’ll confirm or rectify my observation once dev units ship.

{{< youtube id="46khsEjkqPU" >}}

**A quick look at PinePhone Pro's performance**

UI animations are perfectly smooth, applications open nearly instantly (Firefox opens in under 4 seconds on an OS running from SD card), scrolling in the web browser or interacting with elements of an application results in an immediate input reaction. For a lack of a better word, everything feels instant on the PinePhone Pro. Something as trivial and mundane as interacting with the interface suddenly becomes fun. Since there is always someone asking about this - playing 720p Youtube videos works flawlessly and the videos load instantly (1080p will also work fine at 30FPS on an external display). Speaking of videos, there are now a handful of recordings showcasing PinePhone Pro’s performance if you want to verify what I say with your own eyes. Obviously we’re just the very beginning of development, so you can expect the experience to further improve in months to come as software matures and becomes more refined. 

I am also happy to report that my device doesn’t run hot. Warm, circumstantially yes (mostly in the top quarter of the LCD display), but at no point did I feel it reached uncomfortable temperatures. Indeed, it is my impression that the PinePhone Pro runs cooler than the original PinePhone. I verified this with [Justine](https://twitter.com/JustineSmithies) and Phillip (from [Manjaro](https://twitter.com/ManjaroLinux)) who also received their PinePhone Pros in recent days. Justine told me that “(..) _\[it\] does run cooler than my previous \[PinePhone\] even when compiling packages on it_”. I also checked the internal temperature of the device after running an artificial load on all cores for 10 minutes - the SoC reached the temperature of, and remained at, approx. 68\*C. The temperature dropped to 58\*C after a minute of cool-down time. It then hovered at 47\*C after 10 additional minutes of inactivity with just the web browser open and the screen on. It appears that ~55\*C is the SoC’s average operating temperature when browsing the web, installing packages, etc. and the temperature is dissipated well by the chassis without one spot becoming exceedingly hot. So, in conclusion, the SoC does get hotter than on the A64 on PinePhone, but it doesn’t feel like it to the person using the device.

![](/blog/images/Thermals-load-1mincooldown-10mincooldown.png)

**From left to right: Temps under load, after one minute and after ten minutes of cool-down** 

I am not going to write about battery life just yet, since the battery and charging kernel driver as well as various settings still need tweaking. [Megi](https://xnux.eu/) told me that the current software will “_happily charge out of spec_”, which also means that charging to (what the kernel thinks is…) full battery capacity isn’t a great idea. Besides, any numbers I’d provide at this point would be meaningless in 3 months time. Since I already started listing things that need work, here’s the rest of things that currently do not work fully or partially: 1) sound (which also means no…) 2) phone voice calls, 3) cameras, 4) USB for data, video or OTG 5) torch/ camera flash. Some of these are already worked on and will be resolved quickly, while others may take longer. While we need to acknowledge that there is a lot of work ahead of developers, we simultaneously have to appreciate how far development on the original PinePhone has gotten us.

![](/blog/images/pppguts-1.jpg)

**PinePhone Pro with back case and battery removed**

Returning to the subject of the hardware, I have a few observations that pictures or renders cannot convey. The panel is really bright and the colours are rich; the vibration motor is much more powerful than on the original PinePhone; 5Ghz WiFi connectivity has been exceptionally good even when compared with my 2 year old flagship Android phone; and the phone has some heft to it, which is a good thing. There are also a handful of other external changes from the original PinePhone’s design. I’ll omit the big and obvious things that you can read about on the [PinePhone Pro’s main page](http://pine64.org/pinephonepro), and instead focus on some tiny details I previously omitted to mention. The thermal pad on the back case is much larger and appears to distribute the heat well. The battery is different and is labeled with the new phone model. The sim card and SD slot are slightly different as are the buttons at the leading edge of the phone (they have a more distinct actuation point). Lastly, the WiFi / BT antenna layout on the midframe has been altered for 5GHz connectivity. 

Before moving onto the next topic, the packaging is made out of recycled material, including all of the cardboard and most of the plastics. I know that it matters to many of you in the community, so I felt it is worth a mention.  

Lastly, as always, I suggest you follow [Megi’s blog](https://xnux.eu/log/) for software-related and other PinePhone Pro news. 

## PinePhone Keyboard

The keyboard has now been scheduled for release next month, in December. The delay is caused by a fix that will need to be applied to the keyboard’s membrane following feedback from developers who received production samples earlier this month. I know that many of you have been waiting for the keyboard for a long time, and I understand that the wait is annoying, but we want to make sure to both account for developers' feedback and to deliver the best possible PinePhone (Pro) keyboard that is possible. Notification about the keyboard going on sale will be made on Telegram/Discord news channels, the official forums news section, on our official subreddit as well as Twitter and Mastodon. **The keyboard will be priced at $49.95**.   

![](/blog/images/pppkeyboard.jpg)

**PinePhone (Pro) production keyboard fully extended laying flat**

I've now had a couple of days of hands-on time with the production version and figured I’ll share my experience with it. Despite having already written about the keyboard in the past, covering the production model in depth is warranted since surprisingly many changes have been made since the final pre-production model. This applies to both surface-level and electronic changes. The keyboard received a final layer of polish and it shows - there are no more sharp edges and I no longer can make out mold lines no matter how close I look. The production case finish is best described as semi-soft and very smooth, making it a joy to hold. On the downside, as compared to the pre-production units that featured a matte finish, it has a tendency to attract more oily fingerprints. If you wipe it down after use, however, it will look as good as new.

Once opened, the most obvious difference from the prototypes are the keys. The font is now thick and very legible - the key caps pop even in low light. The keys themselves have a matte black finish. The combination of the glossy case and matte keys is very nice, it really does look great. The rubber domes for the keyboards are black as opposed to white on the final prototypes, making the gaps between keys less apparent. The travel and wobbliness of the enter key has also been significantly improved. But this isn’t all, additional structural changes to the top portion of the keyboard where the PinePhone (Pro) is inserted have also been made. The pogo pin connectors have been slightly raised, assuring that connection is maintained between the keyboard and phone even as the top of the chassis flexes when opening or closing. Speaking of flexing, the top section is now firmer and, in conjunction with the well tuned hinges (they are truly great), the whole contraption feels just right.

![](/blog/images/left-final-right-prototype.jpg)

**Can you spot the difference? Left: production keyboard / right: prototype**  

As for electrical under-the-hood changes, a concern raised by developers following Megi frying his prototype a couple of weeks ago,  resulted in a fix preventing overcharging of the battery. The chip that blew on the prototype was analysed closely and it was established that electrical over stress was to blame. As a result a low dropout regulator, acting as a current limiter, was added to the circuitry. If you didn’t understand any of the above then here is what it boils down to: there is now a counter measure in place so your keyboard or phone do not get electrically damaged. A number of other improvements suggested by the devs have also been implemented - I wrote about this at length in the [September community update](https://www.pine64.org/2021/09/15/september-update-hurdles-and-successes/), so I suggest you (re)read it for more details. 

Finally, the keyboard’s open firmware worked out of the box on my Manjaro Plasma Mobile and Arch Phosh installations, and I found no firmware-related issues. I haven’t tried the keyboard with postmarketOS, but that should work too out-of-the-box. The keys on the keyboard needed a few minutes of break-in time. Initially some keys would require more pressure to actuate than others; it took a couple of firm presses on all keys to have the membrane settle in for a lack of a better word. Having done the above I experienced no further issues. Following this feedback, and similar experiences reported by developers, we chose to push back the release of the keyboard to improve the membrane so that end-users do not experience such issues when they receive their units. I cannot wait until you receive your PinePhone (Pro) keyboard and share your experience with it. 

## SOQuartz

I already spent much time on the SOQuartz and two of its hostboards in [last month’s follow-up](https://www.pine64.org/2021/10/29/october-update-follow-up/) post, so in this section I’ll be focusing on a new hostboard for the module - the Blade. If you missed the announcement of SOQuartz’s launch, please read the previous blog entry. The Blade hostboard is designed to fit into a 1U server rack and, in a sense, brings the legacy of the [SOPine and SOEdge Clusterboard](https://www.pine64.org/clusterboard/) to the next generation of PINE64 modules. More than a dozen Blade hostboards can be housed in a standard server rack, making any cluster compute project highly scalable depending on set requirements. Using the hostboard, new modules can also be easily added ad-hoc to the cluster setup. 

![](/blog/images/Soquartz-blade.jpg)

**SOQuartz Blade hostboard (2x) prototypes (Gigabit Ethernet unpopulated in this photograph)**

The Blade features a Gigabit Ethernet connection, a micro SD card slot, a USB 2.0 header, digital video output, 40x GPIO header, UART output, power barrel jack port and a M.2 PCIe slot for storage. All IO is located at the short leading edges of the blade, allowing for tight stacking inside the rack. Blade’s layout makes for an IO feature rich setup in a very compact form factor. We believe that the Blade, along with the model-A and small form-factor hostboards introduced last month, will offer sufficient versatility to early early adopters for their desired use case. The blade is, however, not the last Quartz board we’re working on - stay tuned. 

## PineTime and InfiniTime (by JF)

The InfiniTime team released version [1.7.0 "Jackfruit"](https://github.com/InfiniTimeOrg/InfiniTime/releases/tag/1.7.0) a few days ago. This new version brings a feature many of you were asking for: the possibility to manually set the date and time without the need of a companion application. It is now possible! InfiniTime 1.7 also adds a new "motion and step" BLE service. This service allows a companion app to fetch the number of steps counted by the watch. To my knowledge, this feature has already been integrated by [itd](https://gitea.arsenm.dev/Arsen6331/itd), [InfiniLink](https://github.com/xan-m/InfiniLink) (previously Infini-iOS) and [Amazfish](https://github.com/piggz/harbour-amazfish).

![](/blog/images/amazfish-1024x768.jpg)

**Step-count synced from PineTime to Amazefish on Linux PC**

This brand new motion service also exposes raw X/Y/Z values from the accelerometer. When I implemented this feature, I wasn't sure how useful it would prove but Petterhs proved the potential of the feature showcasing a 3D cube moving based on PineTime’s position. Who knows, maybe someone will come up with a game that would use the PineTime as a controller?Of course, this isn’t everything that InfiniTime 1.7 has to offer, there are many other features and improvements, make sure to read [the release notes](https://github.com/InfiniTimeOrg/InfiniTime/releases/tag/1.7.0) for more details. 

{{< youtube id="QR5NhzcqyKA" >}}

**Controlling a 3D object using the PineTime**

I'm also happy to welcome [Riku](https://github.com/Riksu9000) aka Riksu9000 to the team! Riku has already made contributions to many features in InfiniTime and I'm really happy he accepted the invitation to join us. Finally, I would like to highlight [Nico's](https://twitter.com/cartron) [blog](https://www.ncartron.org); Nico writes a lot about SailfishOS as well as PineTime and InfiniTime. On his blog, you'll find many articles about the different releases of InfiniTime, [including 1.7 "Jackfruit”](https://www.ncartron.org/infinitime-17-jackfruit---motion-service-buttonhandler-and-new-torchlight.html), as well as a nice recap of all of the project’s [release history](https://www.ncartron.org/pinetimes-infinitime-firmwares-history60.html).

## PineDio by JF

We are still working hard on enabling software support for the PineDio (LoRa based) devices. [Lup Yuen](https://lupyuen.github.io/) is writing a thorough [article](https://lupyuen.github.io/articles/gateway) about the PineDio Gateway. This article introduces the gateway, explains how we tested it, the setup and how to connect to TheThingsNetwork (TTN) LoRaWAN public network.

  
In the meantime, [RTP](https://twitter.com/TvPrivacy) provided us with a [new image for the PineDio gateway](https://politictech.wordpress.com/2021/11/09/new-pinedio-image-automatic-grow-to-disk/). This new image comes preinstalled with Chirpstack LoRaWAN stack, supports TTN and automatically resizes the filesystem according to the SD card’s capacity. Finally, I've been told that new prototypes for the PineDio STACK development board were ready and will be sent to me very soon. Stay tuned!

![](/blog/images/PineDioSTACK-1024x768.jpg)

**Sneak peak at PineDio STACK cassing fitted with a PineTime display**

That is all for this month, thank you for your attention!
