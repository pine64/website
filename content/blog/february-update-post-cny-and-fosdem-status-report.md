---
title: "February Update: Post CNY and FOSDEM Status Report"
date: "2020-02-15"
categories: 
  - "community"
  - "hardrock64"
  - "news"
  - "pinebook-pro"
  - "pinephone"
  - "pinetab"
tags: 
  - "community"
  - "pinebook-pro"
  - "pinephone"
  - "pinetab"
cover: 
  image: "Header.jpg"
---

![](/blog/images/Header.jpg)

**Nemo Mobile and Ubuntu Touch on the PinePhone at FOSDEM 2020**

A lot has happened in the past month. PinePhones have finally begun arriving in the hands of their owners, we had a great showing at FOSDEM, and new hardware was announced. If you haven’t yet read [my post about our trip to FOSDEM and the new devices](https://www.pine64.org/2020/02/03/fosdem-2020-and-hardware-announcements/), then I encourage you to do so. Behind the scenes, much work is currently being poured into consolidating and evolving current projects as well as exploring new ones. There are some really exciting months ahead of us! 

In the meantime, we have plenty to discuss. 

**Here is this month’s TL:DR**

- Want to write something for the blog? - contact me
- Production is at a standstill; hard to estimate how things unfold
- CNY shipping backlog of SBCs & PineTime; HardROCK64 & SOEdge release dates
- Expect production / order delay for Pinebook Pro, PinePhone and PineTab
- Pinebook Pro NVMe adapter fix; new adapter manufactured 
- Pinebook Pro OS choice is growing rapidly; custom keyboard firmware
- Pinebook-to-pro upgrade kit delayed (again)
- PinePhone software status - 4 key areas discussed
- PinePhone FCC/CE certification & hardware changes for production units
- PineTab is coming; factory under lockdown, no insight how far along production is

##### Write something for the blog

I’d like to quickly remind everyone that this blog is open to everyone to publish on. If you are working on something exciting and wish to share it with the community then get in touch with me - I’ll set up an account for you. As an enticement I’ll add that this blog gets a lot of traffic, so it is a great way for get exposure for whatever you’re working on. It also provides you with an opportunity to receive detailed feedback on your work or even get people to join your efforts.

##### Housekeeping Part 1: 2019-nCov Pandemic 

There were a couple of things I initially wanted to discuss in this section, but the situation warrants me to focus on the most important topic. And so the main topic on the housekeeping agenda relates to the outbreak of the 2019-nCov Coronavirus and the impact it has on the Guangdong province as well as Hong Kong. For those who do not know, PINE64 devices are produced in the city of Shenzhen located in the Guangdong province, and all equipment with batteries - such as the Pinebook Pro or PinePhone - ships out from Hong Kong.  

As some of you may already know from my [post](https://forum.pine64.org/showthread.php?tid=8956) on the forums, earlier this month Guangdong issued a restrictive order prohibiting work from resuming until February 10th. While, in theory, companies are now allowed to resume business, in practice everything remains at a complete standstill. In other words, our operations and those of our partners as well as factories have not resumed as of today. For a variety of reasons, there is also a limit to how much work our staff can do at the moment. 

Factories producing the PinePhone, PineTab and Pinebook Pro remain closed because they need to undergo a long and complicated procedure that will allow them to resume operation. However, due to the huge volume of such government sanctioned procedures required province-wide, it may yet some time before people can even enter the factory. It's worth pointing out that this issue can also be felt up the entire supply chain - manufacturers of components are also affected by this, and shortages are expected.

Sadly, this isn’t the entire extent of the problem; as I’ve already mentioned, all devices which contain batteries ship from Hong Kong. Earlier this month Hong Kong closed many key crossings to the region from mainland China, including the one which we rely on, and now there is a 2-week long quarantine for anyone arriving from mainland China to Hong Kong. This means that our shipping staff can’t reach the Hong Kong warehouse. 

So, then, what does all this mean in practice? It means that we cannot produce anything this month and, even if we could, there is no way for us to ship any devices with batteries. I will refrain from speculating as to when things will return to normal. Expect shipping dates to slip considerably. I have a suspicion that the extent of this disturbance will be felt across the entire electronics industry for the rest of the year. 

I will keep you updated the best I can in the previously linked thread; the moment I know something I’ll make sure to create a new post and update the original entry.

##### Housekeeping Part 2: Chinese New Year Shipping Backlog 

We’re currently catching up on the Chinese New Year shipping backlog. While we’re unable to produce more devices at this time, we can ship existing single board computers as well as the PineTime dev kit from mainland China. Despite the shipping team being severely crippled by current circumstances and the resulting lack of available staff, I expect parcels to keep on steadily going out throughout next week. As I understand it, the process of clearing out the backlog has already begun a few days ago and should be completed shortly. If you’ve ordered a PINE64 single board computer or PineTime dev kit after January 20th then your order should be en route shortly. 

As for the production and availability of the HardROCK64 and SOEdge AI module announced at this year’s FOSDEM - we already accounted for the disruption caused by the pandemic. We also purposefully provided approximate availability dates as it is literally impossible to predict how the situation will unfold. Regardless, the tentative availability dates of April/May 2020 are unaltered at this time.    

##### Pinebook Pro

There is plenty of good news, but let us start with the bad. The bad news is that we need to postpone the production of the RK3399 upgrade kit for the original Pinebook once again. Don’t worry, we’re not shelving it, we’re just prioritizing other things - such as the newly announced HardROCK64 and SOEdge - due to the limited manufacturing capacity (caused by the aforementioned pandemic in China). Having already postponed the release of the upgrade kit thrice now, I rather not promise something for a fourth time. Instead I’ll say: it's in the works, and as soon as I know something with a high degree of certainty I’ll make sure to let you all know. 

On to better news. We now have a solution to the original NVMe adapter problems, where the adapter with an NVMe SSD would not fit properly in the laptop chassis. The solution was surprisingly simple, but required us to manufacture a custom holder for the SSD. I apologize for not keeping you up-to-date on the status of this solution; I didn’t post anything on the subject because I had no insight into the process. If you have the original NVMe adapter for the Pinebook Pro, please send an email to [info@pine64.org](https://www.pine64.org/info@pine64.org) with the following in the subject field: 

**_Subject: New PBP NVMe adapter holder \[original order number\]_**

We have now also created a new optional NVMe adapter that will ship with all future Pinebook Pro orders. The new adapter is a little longer, but has a lower profile, and is perfectly aligned with the mounting holes inside the Pinebook Pro chassis. I am told that it has been fitted with a variety of popular NVMe SSDs and no issues were encountered. 

![](/blog/images/newadapter.jpeg)

**New NVMe PCIe adapter top / old NVMe PCIe adapter bottom**

The other piece of good news is that the past 30 days have seen many OS releases. We now also have a choice to run Kali Linux, Gentoo, OpenSUSE, Fedora, NetBSD and postmarketOS (Alpine Linux) on the Pinebook Pro. Most of these OSes have been added to the [Pinebook Pro Software Releases](https://wiki.pine64.org/index.php/Pinebook_Pro_Software_Release) subsection on our Wiki. I highly suspect that the coming days will see yet more software releases for the Pinebook Pro, including other \*BSD systems. This is obviously good and welcome news, since broad support for the Pinebook Pro means more people interested in the project. Personally, I have been running Manjaro with KDE desktop in the recent weeks and the experience has been nothing short of great. If you’re considering running Manjaro KDE edition, I suggest you enable OpenGL desktop acceleration via the Panfrost FOSS GPU driver, it makes the installation fly. This can be achieved using [this script](https://github.com/McMarius11/Pinebook-Pro/blob/master/graphics_driver_pf_fb.sh). 

![](/blog/images/OS-List.jpg)

**Growing Pinebook Pro OS List**

Lastly, I’d like to give a huge shoutout to [Jack Humbert](https://github.com/jackhumbert) for his work on the Pinebook Pro’s keyboard firmware. Jack made it possible to [create your own custom keymaps](https://github.com/jackhumbert/pinebook-pro-keyboard-updater/tree/master/firmware/src) for the keyboard, significantly enhancing the potential functionality of the laptop. Just as an example, one user has created and shared theirs [ANSI Dvorak layout](https://forum.pine64.org/showthread.php?tid=8884&pid=59150#pid59150) that supposedly can be used without any problems. It is always exciting to see community members embrace and improve upon implementations which we have given considerable thought to. If you have any questions regarding the process of creating your own custom keymap then I redirect you to the dedicated [forum thread](https://forum.pine64.org/showthread.php?tid=8884&highlight=firmware) discussing the custom firmware implementation. 

Before I move onto the next section let me quickly address the elephant in the room; many of you are asking when the next production-run of the Pinebook Pro will commence. We initially intended for new Pinebook Pros to be produced this month, with pre-orders opening now(ish). As I already explained in the housekeeping section, this will not happen. I can only offer you my guess at this point - and that is that the next pre-order window will open mid-March.

##### PinePhone

Many Brave Heart edition PinePhones, with the exception of those slated for Germany, have already reached their destination. So far the reception from end-users has been very positive, which admittedly makes me rather thrilled. I’d also like to thank those of you who post previews, reviews, quick-looks, etc. online; every single written or recorded piece of content that I’ve seen insofar has rightfully included a mention that the PinePhone is a work-in-progress. This is important since, as I see it, the most important aspect of the project currently is showcasing progress while accurately depicting the current state of the software options. 

Speaking of PinePhone software options and development status, there is so much information to cover that it would require an entire separate post. Not to mention that I am not the most competent person to cover the subject of software development in the first place. So, instead, what I will do in this section is highlight some of the vital developments of the past couple of weeks. 

I want to address 4 main topics: 1) battery life; 2) voice calls; 3) camera implementation; 4) performance. Let’s go down the list one-by-one. There are many things pertaining to battery life that are currently being ironed out. On the one hand, a fair bit of work on the AXP803 power management controller and kernel behaviour. I only understand the latter, so I’ll comment on that. Marius from UBports has started experimenting with having the kernel downclock the core frequency, drop the CPU voltage and turn off 3 cores when the phone’s display is off (in its idle state). This early experimentation has resulted in a stand-by time of approximately 12hrs, which is rather impressive for a first battery-preserving attempt. This will only get better with time, as it becomes paired with more advanced power management. Another developer, Megi, has also managed to dramatically lower the WiFi module’s power consumption, which can buy users as much as another hour of runtime during active use.

![](/blog/images/power.png)

**Picture showing battery drain over ~11 hrs on the PinePhone running Ubuntu Touch**

Megi has also demoed voice calls and camera implementation in the past few weeks. While voice calls already work, they also require manual audio routing (for those interested, [here](https://megous.com/dl/tmp/modem.txt) are the details). Getting voice calls functional with the individual OSes is being worked on, of course, but there is no telling when the functionality will be available. It could be soon or in a few weeks or months. The story is very similar for both the front and back camera. We have seen a successful demo of the cameras being used from the userspace, but this functionality remains to be implemented into the existing OSes. Out of the two highly desirable features, it is my understanding that voice calls will be easier to implement within a short-to-medium amount of time. 

https://www.youtube.com/watch?v=12bsEtUEWbg&t=1s

**Phone call from Arch Linux on PinePhone ~ Megi**

https://www.youtube.com/watch?v=l-Vt8-npTjc

**Camera Test application on the PinePhone ~ Megi**

Last on the PinePhone software agenda is the subject of performance. To be precise, the end-user experience of using the phone - the responsiveness of the UI. This is one area where you can expect a lot of changes from one week to another. As an example, KDE Neon from early February suffered from poor performance, making it borderline unusable. Less than two weeks later, the newest KDE Neon OS image is one of the fastest out there (despite it being highly unstable). Similarly, Ubuntu Touch suffers from a significant amount of slow-down in the main UI. This is caused, funny enough, by the wallpaper; replace the wallpaper (for the one with puppies as an example) and watch the performance significantly improve.  Such performance issues are very much expected at this point in time, but I expect that their root causes will be found and ironed out relatively soon.

Many users have asked why there is little to no dev dialogue in the #PinePhone chat. For those who don’t know, the #PinePhone channel is very active. There are ~2400 users in Discord, ~100 (concurrent) users in IRC, ~800 users in Telegram and ~500 users in Matrix. This makes for an environment where it’s very difficult to hold a frequently complex and technical conversation. Development-related chat is very much ongoing, but it’s mostly taking place elsewhere. This does not mean, however, that you can’t ask devs questions or engage with them - they are still in the main channel if you need them. 

https://www.youtube.com/watch?v=xI6AUFkQJU0

**postmarketOS with Phosh performing rather well in newest OS image ~ [Alexmitter](https://www.youtube.com/channel/UC9LBZMUotYSPsguBkd5eMnA)**

The last bit of information related to the PinePhone I wish to discuss before proceeding to the next section concerns consumer-grade PinePhone changes and CE/ FCC certification. We expect to have the certifications in place later this month, which means that all future PinePhones will ship as certified devices. This is good news, since some places such as Germany require this type of certification on consumer products. As for changes to the hardware, there is a [list of errata](https://wiki.pine64.org/index.php/PinePhone_v1.1_-_Braveheart) on the Wiki. To be clear, most of these issues are imperfect hardware implementations rather than major problems. We’ll work though as many of these errata for the final phone as possible while striving to maintain complete software compatibility with Braveheart phones. 

Similarly to the Pinebook Pro, we initially intended to start the production of the phones this month. As I’ve already explained in previous sections, it is much more likely that production will first begin in March. On the positive side, we have some super exciting things in stock for the PinePhone which we will be sharing with you shortly; we trust that this will more than make up for the pandemic-related manufacturing delays. 

##### PineTab

This section of the update will be rather short since not much has changed since last month. Production of the PineTab early adopter units started prior to Chinese New Year, but due to the factory currently being locked-down and staff unable to access it, we do not know how far along the production process got in January. If we can resume PineTab manufacturing next month alongside the PinePhone and Pinebook Pro, then pre-orders may go live in March. I’ll make sure to amend this post with an edit once we know the state of production. 

The good news is that we have now internally narrowed down OS choice for this early batch to two OSes. We’re in talks with the projects in question to determine which of the two will be the most viable for the first PineTab batch. I expect that we should be announcing what we agreed on next month, so if you’re interested in the PineTab now is probably the right time to subscribe to this blog. At any rate, there are now two good options for us to choose from with sufficient software maturity that early adopters have something to start with when they receive their unit.

This wraps it up for this month’s community update. I hope to be back with better news next month. In the meantime, we have some important and exciting things coming in the next couple of weeks, so make sure to subscribe to the blog and stay tuned for the upcoming announcements!
