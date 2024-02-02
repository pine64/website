---
title: "June Update: postmarketOS CE PinePhone, Shipping & PINE64 Cluster"
date: "2020-06-15"
categories: 
  - "community"
  - "news"
  - "pinephone"
  - "pinetab"
  - "pinetime"
tags: 
  - "pine64"
  - "pinephone"
  - "pinetab"
  - "pinetime"
cover: 
  image: "pmosedition1.jpg"
images:
  - "/blog/images/pmosedition1.jpg"
---

![](/blog/images/pmosedition1.jpg)

Hello everyone! It has been a really busy time for us here at PINE64 as we’re working hard to deliver outstanding PinePhone _UBports Community Edition_ and Pinebook Pro shipments. The big news of this month is that we’re excited to announce that a postmarketOS _Community Edition_ PinePhone will be available for pre-order early next month. 

There are a lot of topics to cover this month, so let's get to it.

**This month’s TL;DR**

- All PINE64 services on our own hardware; the cluster move report
- Shipping delays and Pinebook Pro QA issues addressed
- Shipping status update & where to find up-to-date information
- An apology for PineTab pre-orders delay & no heads-up on blog
- PineTab pre-orders sold out in under 72 hours
- PineTab to ship late July 2020; more batches coming 
- PineTab add-on board reengineered for LoRa and RTL-SDR modules; available for next pre-order batch
- PinePhone postmarketOS Community Edition announcement; pre-orders start early July
- Check out postmarketOS announcement blog post!
- PinePhone CRUST advanced power management status
- A community initiative; a PinePhone pogo pin breakout board
- PineTime; Lup Yuen Lee will write a series of PineTime articles for our blog!  
- Solve the riddle! 

#### Housekeeping 

We’re proud to announce that starting this month all our community services, including this very website you’re currently visiting, are all running on our PINE64 cluster of 24x ROCKPro64 single board computers. The process of migrating services to the cluster began on June 5 and finished on the 10th without any major dowtimes or hiccups. As of right now the cluster hosts the main PINE64 website, the Wiki, forum, IRC server (and chat bridge) as well as all our Matrix channels. To our knowledge we’re the only organization in this neck of the woods to dogfood hardware in this way. I like when things speak for themselves, and so I hope and trust that this is a testimony to our faith in our own hardware.   

I know many of you are very keen to learn more about the cluster, so I already have asked Matthew (fire219) and Marek (gamiee) to write a technical blog post about it once the dust settles. I know that there are at least two other services that the guys want to host on the server, and once that's done you can expect a progress report directly from the people involved in making it happen. What I can tell you is that the cluster is running mainline Debian and the nodes are network booted from a 1TB NVMe SSD. All databases are backed up and mirrored to another 1TB SSD. We’re currently using 8 of the 24 nodes at our disposal so there is plenty of room to grow in the future. We’re also aware that not everything is working 100% flawlessly just yet, but we’re going though the bugs list and hope that the minor issues will not detract from our systems’ overall usability.

![](/blog/images/bootingNode-1024x576.jpg)

**Network boot node with 1TB storage via Gamiee**

#### Shipping Status and Pinebook Pro QA

As many of you are already aware, we ran into shipping problems which resulted in delays. We are presently approximately 2 weeks behind our original schedule (NB. this only relates to some shipments, since a fourth of all PinePhones _UBports CE_ and half of Pinebook Pro laptops already went out). It is important to note that the reasons for the shipping delays are different for the two devices, so I’ll take a minute to explain the situation. The Pinebook Pro shipments have been put on halt since additional and more stringent QA of the devices is now underway. This follows an abnormal amount of issues reported from the first two shipments. I feel like I owe you an explanation, so here it goes: the higher-than-normal number of Pinebook Pro issues reported is, by and large, a case of the factory not doing their job properly. A cascading number of events underpin this situation, and I won’t get into all the details, but the starting point of these issues is the COVID19 pandemic, which effectively prevented us overseeing the work done at the factory.

We have now taken steps to make sure this doesn’t happen again. Factory workers have been better instructed on how to perform some of the error-prone tasks, the factory has agreed to improve their QA protocols and we’ve set up an independent review of the laptops as they leave the factory. Regardless, I am now happy to let you all know that the remaining Pinebook Pro laptops will clear our warehouse this week and that shipping resumes today. This means that the grand majority of those still waiting for their Pinebook Pro will have their units by late-next week. I’d like to apologize once more to everyone who received a faulty unit - we’re working as fast as we can to resolve reported problems. 

As for PinePhone shipments, the cause of the delay is Asendia’s inability to fulfill shipment at this time. Unlike DHL - which has a fleet of aircraft and local couriers at its disposal throughout the world - Asendia relies on third-party logistics and national postal services to fulfill orders. Seeing as many borders are still closed and, at times, carriers or postal services Asendia  cooperates with have not returned to normal operation, it is simply impossible to accept our shipment. Earlier this month we gave everyone the option to change their shipping from Asendia to DHL, and we have now reached the required number of orders to commence a DHL ‘upgrade’ shipment in a matter of days. Those who have not yet changed their Asendia shipment orders to DHL still have [the option](https://store.pine64.org/product/pinephone-shipment-upgrade/) to do so. 

If you want to receive your PinePhone UBports CE this month then I strongly recommend you switch your Asendia shipping to DHL. However, if you’re not in a rush then you are welcome to stick to Asendia - borders around the world are slowly opening up and logistics chains are slowly returning to normal. Just today the service resumed operation to two more countries - Brazil and Australia. In result, I suspect that the more Asendia shipments will commence in a matter of 3-4 weeks, as more shipping destinations become available. If you wish to stay up-to-date on PinePhone and Pinebook Pro shipping, you can find a [shipping update thread](https://forum.pine64.org/showthread.php?tid=9942) on the forum, where I post new information as it becomes available to me. 

#### PineTab

Pre-orders for the PineTab pilot batch went live on June 10th - 12 days later than we initially planned. We apologize for this delay. The delay in launching pre-orders was caused by two factors: the PinePhone and Pinebook Pro shipping situation, as well as migration of our services to the PINE64 cluster. We initially planned for the pre-orders to go live well before the migration of services, but with aforementioned shipping problems the date slipped and we deemed a pre-order launch right in the middle of moving services to our cluster too risky. I’d also like to personally apologize to all those who waited for a heads-up post on the forums and the blog; I know this is something I promised, but forgot about it due to high workload. If you missed out on placing a pre-order rest assured - this is just the beginning. Once we receive feedback from early adopters, we’ll produce a much larger PineTab batch and everyone who wants a PineTab will surely be able to get one.

![PineTabwkeyboard](/blog/images/PineTabwkeyboard.png)

![PineTabstandalone](/blog/images/PineTabstandalone.png)

![keyboard](/blog/images/keyboard.png)

Previous Next

**Production PineTab and keyboard (not renders)**

Speaking of sales, the pilot batch sold out in under 72 hours, which means that multiple hundred units were sold daily. I’m not going to lie, I am surprised by the sheer volume of traffic and general level of interest in the PineTab, and I am curious if the fast sale rate is a result of the extensive media exposure that the PineTab received or a genuine need for this type of device (or a combination of both). Feel free to share your thoughts about this - I am really interested to hear what you make of it. Regardless, it was a real pleasure to see so much positivity and excitement around the PineTab online at the time the pre-orders dropped. The numbers speak for themselves, the PineTab video Marius recorded last month has now received 26k. 

https://www.youtube.com/watch?v=Ii6lAjgfW3c

**If you missed the video last month - here's the PineTab Running Ubuntu Touch**

Seeing as PineTab pre-orders sold as well as they did, we’re now looking into ways to extend this production run or start another one in the immediate future. We cannot promise that this will happen for certain, but if our production request will be accepted by the factory then I will make sure to let you all know on Twitter, Mastodon, the forum, the chats and also on this blog. I promise I’ll remember about making a blog entry this time.

The shipping date for the PineTab is late July, which means that we’re internally aiming to start sending out units in the latter half of July. As the shipping date draws nearer we keep on improving and polishing the device so it will be the best it can be when it lands in early-adopters hands. I have already written at length about some improvements already made to the device in [April’s community update](https://www.pine64.org/2020/04/15/april-update-ce-fcc-software-update-and-diy-router/), so I won’t be repeating myself here, but just because we addressed all known issues doesn’t mean we stopped researching our options to improve the PineTab yet further while preserving the $99 price-tag. In example, we just managed to secure a higher quality battery for the PineTab; something that will be a major benefit 2 or 3 years after your Pinetab purchase.

Lastly, I see a lot of questions concerning the PineTab  add-on adapter [announced last month](https://www.pine64.org/2020/05/15/may-update-pinetab-pre-orders-pinephone-qi-charging-more/). In its original inception, the adapter only allowed for LTE and SSD storage, while now it will also have to accommodate LoRa and RTL-SDR modules. Seeing as we already have our hands full with other equipment and the abnormally difficult shipping situation, the process of re-engineering the adapter will take a few weeks longer. In result, the adapter will first be available in the PINE Store when the second production-run of PineTabs becomes available for pre-order. I’ll make sure to keep you up-to-date on this topic in future updates. 

#### PinePhone

We’re happy to announce that the next _Community Edition_ of the PinePhone will ship with postmarketOS. The pre-orders will start in early July and we currently aim to have the pre-order window open for at least a month and a half. I am sure that many of you are thrilled to see another _Community Edition_ of the PinePhone available so soon and branded with one of PinePhone’s flagship OSes. Similarly to our friends at UBports, postmarketOS developers have been with us since the very start of the PinePhone project and their OS has been instrumental to our hardware production process. For those who don’t know, the [factory test image](https://images.postmarketos.org/pinephone/pine-pinephone-20190921-factorytest.img.xz) used for handset QA at the factory runs postmarketOS with a custom UI. It will therefore, in a sense, be the second time we ship postmarketOS on the PinePhone - as some of you will recall, _Braveheart_ _Edition_ PinePhones shipped with the aforementioned factory test image. It is probably evident but I’ll write it anyways; unlike the factory test image that shipped with _Braveheart_ phones, the _postmarketOS Community Edition_ will feature a fully fledged postmarketOS mobile system.

![](/blog/images/pmOSCE.png)

**Render of postmarketOS _Community Edition_ PinePhone**

I expect you will also be glad to learn that production of this _Community Edition_ has already been scheduled at the factory, and we’re hoping for record turn-around time for this production-run. In general, I feel like we’re just getting into the manufacturing stride after the long downtime which began in January with the Chinese New Year and was followed by the now dwindling COVID-19 pandemic. This is obviously good news for you, the end-users, but it is also good news for postmarketOS developers who will benefit from the donation we’ll be making on your behalf to their project. I have already stated this many times in the past but I’ll write it again - the principal goal of the PinePhone as a project is to give Linux on mobile a chance to grow and prosper. Early on we recognized that donating to our partner-projects was a key component in helping Linux on mobile flourish. The team behind postmarketOS has just  recently set up a financial back-end to their project. The donation we’ll be making - for those who don’t know - will come in the sum of USD $10 for each unit sold during this PinePhone campaign. You can learn more about our partner-project donation scheme by clicking [here](https://www.pine64.org/2019/08/19/its-time-to-start-giving-back/).   

I am sure many are curious to find out more about the hardware and software that will accompany the postmarketOS edition of the PinePhone. More information will be available in the coming days, but in the meantime I strongly encourage you to head over to [postmarketOS announcement on their blog](https://postmarketos.org/blog/2020/06/15/pinephone-postmarketos-community-edition/), which offers a detailed look at the software set to ship with this edition of the phone. As for the hardware, we will be making an announcement closer to date; presently we are working on the assumption that the PCB to ship with this edition will still be version 1.2. We may, however, decide to make some further tweaks to this PCB design. We will, of course, document and inform you of any changes to PCB 1.2 there may be in the future. Lastly, as you have surely already spotted, the postmarketOS edition of the PinePhone will feature the project’s branding on the phone’s caseback. Subjectively, I must say I love the render of the caseback and think it will turn out looking fantastic.  

![](/blog/images/pinephonewcrustGPS.jpg)

**PinePhone running Ubuntu Touch with GPS and CRUST enabled**

In other PinePhone news, we’re seeing a lot of progress across all software distributions. So much in fact, it would be impossible for me to cover it all. The one thing that the various PinePhone projects are working towards collectively, however, is implementing CRUST advanced power management in such a way that modem events, e.g. as phone calls and SMS messages, would wake the phone up from the deep sleep state. Just recently, Marius from UBports has [managed to achieve just](https://twitter.com/thepine64/status/1271252134781222912) this in Ubuntu Touch. Perhaps most importantly, his implementation allows both _Community Edition_ and _Braveheart_ PinePhones to wake up from deep sleep. This is something others have speculated may prove very difficult on _Braveheart_ phones due to GPIO assignment, so I figured it is important to underline - once again - that if you have a _Braveheart_ phone, you shouldn’t feel like you’re missing out on upcoming software features. CRUST on the PinePhone, at least in its current state when coupled with an active LTE modem connection, allows for approximately 14 hours stand-by time. For most people, this will be just enough to get you through a work-day. This number will eventually be extended by another 10 hours as developers tweak the modem to enter a lower power mode. 

I know that developers from other projects are already looking into how they can implement this solution in their distributions, but for now you can try it out on Ubuntu Touch by switching over to the _Developer_ channel under system settings. I have started a [thread on the forum](https://forum.pine64.org/showthread.php?tid=10165) with instructions on how to enable some of the more experimental features on Ubuntu Touch. In the coming weeks you can see this feature, as well as many others, to be incorporated into what was meant to be the day-one OTA update. As is customary in software development, the day-one OTA has been delayed by a few weeks, due to bugs which need to be worked about before a new stable build is deployed. If you’re not one to tinker or keen on experimenting with work-in-progress features, then stay on the _Stable_ Ubuntu Touch branch and wait for the update to drop.  

![](/blog/images/PinePhone-with-Beakout.jpg)

**pogo pins breakout board for the PinePhone via [SMR404 GitHub](https://github.com/SMR404/PinephonePogoBreakout)**

Lastly, I’d like to showcase a community hardware initiative I found quite ingenious, namely a breakout board for the PinePhone’s pogo pins. The board makes it easy to access I2C pins and to interface with the protocol in a convenient manner. I hope and trust that someone will create a caseback for the PinePhone which could also house this breakout board. The STL for this project is available on [SMR404’s GitHub](https://github.com/SMR404/PinephonePogoBreakout), and I’d like to encourage others interested in hacking and tinkering with the PinePhone to actively contribute.  

**PineTime** 

It feels to me that the PineTime, as a project, has greatly matured in the past couple of months and is now entering a new stage. As I have mentioned on many occasions in the past already, I am not the best person to bring you coverage of the PineTime seeing as I do not fully understand the complexities of its software and development process. To this end, I’ve asked [Lup Yuen Lee](https://twitter.com/MisterTechBlog) to post PineTime development updates on this blog on a need-be basis, and I am happy to report that he agreed to do so. I’d also like to point you to his [Medium blog](https://medium.com/@ly.lee), which is a treasure trove of PineTime articles. I am more than certain that having Lup Yuen cover the PineTime from now on is for the better, and I cannot wait for his first post on PINE64’s blog.  

**The Riddle**

Before we start, consider the following just a bit of fun. Let me give you the border context first however; I have been tasked with teasing an upcoming device due to be announced next month. I have been thinking for some time how to make this a fun community exercise and came up with a rhyming riddle for you to solve. The first person to solve this riddle will be rewarded with the mystery device. Just to make it clear - even if you solve the riddle correctly, I will not acknowledge the answer until July 15th when the official announcement will be made. You get bonus points (which translate to beer if I meet you at a convention) if you correctly identify clues embedded in the poem. Lastly, I have not written a word of poetry since highschool, so please spare my fragile ego. And yes, I’m aware it breaks at least one convention of writing Quintets.

**_Pinecil_**

With the Pinecil we take a risk   

Spelling the latter with the letter c   

Breaking with current conventions

And having the device run hot 

As hot as it will ever be

This may be too perplexing 

So for the sake of simplicity 

What does 82 and 26 have in common

As defined by a man 

Born North-East of Caspian Sea?
