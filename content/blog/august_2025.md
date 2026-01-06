---
title: "August Update: Note-able Tablet Updates"
date: "2025-08-16"
authors: ["Caffeine", "hrdl", "Phantomas", "Danct12"]
categories: 
  - "community"
  - "news"
  - "pine64-community"
tags: 
  - "pinenote"
  - "pinetab2"
  - "pinephone-pro"
  - 
images:
  - "/blog/images/AugustBanner_2025.jpg"
summary: "Hello RSS users! In this update we announce a new community manager, updates to the PineTab2 and PineNote, FreeBSD on the PinePhone Pro, a guide on upstreaming PinePhone Pro patches and a small bit for you Pinecil users."

---

![The August 2025 community update banner](/blog/images/AugustBanner_2025.jpg)

{{< toc >}}

## Housekeeping
Welcome back to another community update! In this update we announce a new community manager, updates to the PineTab2 and PineNote, FreeBSD on the PinePhone Pro, a guide on upstreaming PinePhone Pro patches and a small bit for you Pinecil users.

### PinePhone Pro discontinuation
Recently PineStore has also discontinued the PinePhone Pro which was talked about in the last recent blog post. TLDR, sales were low which lead to the discontinuation of the device. Spare parts will be available for purchase for up to two years depending on if they sell well. If you still want a PinePhone Pro, refurbished ones will be put up for sale on the PineStore around the end of the month, similar to how it worked for the PineBook Pro.

For more details, people can find it at the link below.
https://pine64.org/2025/08/14/august_2025_short_update/

## New community manager
{{< credits "Authors: Caffeine" >}}

Today I would like to formally announce that I have stepped up to take the roll as the community manager. This decision was made a few months ago as life has become a lot busier for Gamiee. We would like to thank him for the work he has done maintaining our community cluster and the countless hours spent on helping the community. Gamiee will continue maintaining the cluster for the foreseeable future. 

### About me
Hello everyone, my name is Camden, but you may also know me by my online alias CarbonatedCaffeine. I am a computing student from New Zealand (that country next to Australia) and I have been an active part of the Pine64 community since 2020, around the time the PinePhone Braveheart was launched. I enjoy playing badminton, tinkering with phones and computers, writing and hiking. 

### My goals as community manager
As I step up, I aim to be a transparent and approachable community manager that community members can easily get along with. I promise to voice the concerns of community members so that important matters can be addressed as quickly as possible. We will continue to work towards bridging the communication gap between the Pine64 community and the PineStore which we hope will get smoother as time goes on.

Bringing back community editions is something that we have personally been asking PineStore to do for a while. This requires compensation to be arranged up front before a device is put up for sale. So while PineStore has continued in it's goal to make cheap hardware that can easily get in the hands of developers, key community members who helped set up the community edition program have gone. This means that there has been nobody to help arrange compensation for those who have worked on software for recent products. If community editions return in the future it will increase the price of new devices, but this sacrifice is something we're sure community members would be willing to pay if it meant supporting the developer(/s). We pledge to keep on PineStore's heels about this and make sure that it will happen in the future so that developers will be paid for their effort. **As of writing, PineStore is open to bringing community editions back for future products as long as proper planning and arrangements are made.**

In terms of quality control and hardware failures I am aware that such issues exist. So to anyone, if these reports sent to Pine via email/tickets don't get a reply for hardware replacements like some have experienced, I will get in touch directly with the PineStore founder to attempt to get the issue solved. Unfortunately I cannot do anything about fixing hardware defects other than report them, but I will do what I can. 

We admit that both PineStore and Pine64 have dropped the ball and it has been very difficult to restart and recover after everything that has happened in the past. We will do our best to rebuild the community and we are going to start by replacing large community updates with smaller more frequent community driven project updates that **anybody** will be able to post onto this blog (not without moderation of course). We are doing this because it is tedious to write large community updates every month (and to keep a schedule). This will give power to project maintainers to announce important updates like new factory image releases through our community blog. I will write a tutorial on how to do so, which will be available on the Pine64 documentation website in the future.  

We have confidence that the future is bright for the community and we hope you will join us in rebuilding our community.

-Camden

## PineNote
{{< credits "Authors: hrdl, Phantomas" >}}

![hrdl's Arch Linux build](/blog/images/August_2025/archpinenote.png)
### Current status
The last community update featured some video demos of another major update of the display controller driver and an integration into a sway-based setup. Since then the kernel sources and integration have been [published](https://git.sr.ht/~hrdl/linux), [packaged](https://git.sr.ht/~hrdl/pinenote-dist), and bundled into an image that can be extracted onto os2, giving users an Arch Linux-based setup that contains hrdl's kernel, their sway/dbus integration, and a functional sway/waybar/gtkgreet/squeekboard setup. 

Phantomas has been improving the [rust-based PineNote dbus service](https://git.sr.ht/~phantomas/pinenote-service) which has just  and has been solving some [long-standing firmware-related WiFi issues](https://lists.sr.ht/~diederik/pine64-discuss/%3Cpq2pwlyaasagyjh3finscwk2baak4uxpg2abfn374z3dzf5am5@cpkqy3bidben%3E). The required firmware will be rolled out once there's clarity on their license. 

hrdl has fixed an outstanding issue with multi-touch inputs. Ten finger touch support has been added by modifying the touch controllers configuration which is [achieved by running a script from userspace](https://git.sr.ht/~hrdl/pinenote-dist/tree/main/item/bin/cyttsp5_update_config.py). This issue occurs because the display controller is flashed at the factory with firmware that only supports two touch inputs at most. A single byte change to this firmware allows a maximum of ten touch inputs to be recognized. The fix will allow the support for 3-4 finger gestures on desktops to switch workspaces or bring up Gnome overview. 

Diederik made some [minor contributions to the mainline kernel](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/log/?qt=grep&q=Diederik+de+Haas). They mostly remove some warnings, and unlike my work these were submitted to and accepted by upstream. He has planned some more work, so he suggested that it might make more sense to wait with mentioning his work until the next community update. dsimic has also upstreamed several patches.

### Operating Systems
There are four new operating system options to choose from, just in case you need some variety. 

#### Arch
As seen in the header image for the PineNote section, hrdl has made a complete Arch installation that can be installed on the OS2 partition next to Debian. It is up to date and includes the latest software improvements. 
* Instructions: https://git.sr.ht/~hrdl/pinenote-dist
* Image: https://files.hrdl.eu/arch.tar.zst
* Signature: https://files.hrdl.eu/arch.tar.zst.sig 

#### PostmarketOS
[Ayakael](https://gitlab.postmarketos.org/ayakael) has made a functional PostmarketOS port based on hrdl's kernel and sway setup. 
  * Merge request: https://gitlab.postmarketos.org/postmarketOS/pmaports/-/merge_requests/6711
  * Installation instructions: https://wiki.postmarketos.org/wiki/PINE64_PineNote_(pine64-pinenote)

#### Nix
Two NixOS setups by werapi (https://github.com/WeraPea/pinenote-nixos) and jzbor (https://github.com/jzbor/nixos-pinenote/blob/main/packages/fs-image/default.nix)

### WiFi Compatibility
Some background, the chip inside the PineNote is an AzureWave CM256SM, which internally uses the CYW43455, which used to be the BCM43455 until Cypress bought Broadcom's IoT division. That chip supports 5GHz WiFi, as well as the 802.11ac (WiFi 5) standard. That being said, WiFi, especially on the 5GHz band is subject to heavy regulations, since the frequency is shared with other tools (weather radar amongst other). This means 5GHz capable devices aren't allowed to emit on most 5GHz channels, as long as they cannot ensure they respect local regulation. Linux's way of managing this is through `wireless-regdb`, but drivers are allowed to disregard that information, which is exactly what `brcmfmac` does. Instead, that driver depend on Country Locale Matrix (CLM) blob being either baked in the firmware, or as a standalone file that the driver load. 

#### The issue
Broadcom/Cypress cannot ship a universal CLM blob for a given chip, because they cannot ensure the regulations will be respected by a final product (e.g. on board amplifiers, internal vs external antennae, etc.), so the one shipped in linux-firmware has a very limited set of features active. On the 2.4 GHz channels 12 & 13 are disabled since they aren't allowed in the US. The 5GHz band is way worse however, being more heavily regulated. On that one, only bands 36, 40, 44 and 48 + some upper bands (> 149) are enabled. However bands > 149 are usually reserved for low emission devices (about the range bluetooth offer), so routers/APs can't use them. The issue is that WiFi 5 compatible router/APs often select the best channel automatically, unless explicitly disallowed, meaning the PineNote could randomly lose 5GHz connectivity if the router picked a higher band. This happens more often in dense urban area, and is highly dependent on the AP/Router in use.

#### Workaround #1
A simple workaround for the user to be able to manage their access point is to disable automatic channel selection and pick one of the supported bands. This can come with a performance hit, but these bands offer the highest compatibility with most devices.

#### Workaround #2
After confirming the chip was actually able to make use of these bands (by retrieving hrdl's blobs coming from the first batch android image), I searched for other firmware/CLM blobs compatible with the `CYW43455` or the `BCM43455`, because while technically working, the android firmware could not be redistributed, and came with an unreasonable performance hit (better than nothing, but still). It turns out that raspberry uses a compatible chip (the `AP6255` module, which internally uses the same `BCM43455`/`CYW43455` chip), and their CLM blob are perfectly working on the PineNote. For the ArchLinux user, I made a PKGBUILD that pulls that firmware and installs it for the PineNote, as a replacement to the one shipped by linux-firmware (I consider it experimental until more people test it.)

#### Some words of warning with this workaround
While I can confirm the blobs to be working, I don't have the hardware to make an EMF measurement and check that the PineNote perfectly respects local regulations. I don't expect this to be an issue when used as a WiFi station because it will passively listen for existing AP before trying to emit, and I dout it has sufficient transmission power to cause interference once it start transmitting on an already authorized channel. 

However, **DO NOT** set it up as an Access Point. We don't know if it can pick low power radars, so it might not be compliant with local regulations. Sometimes the driver fails to load on boot, I'm pretty sure I've seen it happen with the standard firmware, so it could just be some weird dependencies on my side. A reboot fixes the issue so I haven't bothered troubleshooting that yet.

## PineTab2
{{< credits "Authors: Danct12" >}}

There is nothing much with the PineTab 2, but there has been more work on the BES2600 driver.

### Kernel
Suspend and resume bug with the BES2600 Wi-Fi driver has been mostly fixed in v6.15.2-danctnix2. There are still some bugs with the SDIO driver, but they're considered "minor" for now.

On that note, a new driver for Bluetooth is currently being worked on. It is mostly working, I tried pairing a phone, a Bluetooth keyboard, I even tried BLE GATT and they're all working. I haven't tried out BLE audio as I don't have any Bluetooth earbuds that uses it.

Host wakeup is currently not supported, so Bluetooth devices cannot wake the PineTab 2 from sleep mode yet. I'm looking into how that works and I'll implement that to the driver some day.

Unfortunately, sometimes when the BES2600 SDIO driver does a read/write while Bluetooth is turned on, there's a chance that it'll timeout and bring down the WLAN driver altogether while Bluetooth (UART) is still working flawlessly. Because of that, it'll take a while before the Bluetooth driver is ready for public testing.

![PineTab2 Buildroot build](/blog/images/August_2025/pinetab2buildroot.png)

### OS (DanctNIX's Arch Linux ARM port)
A new factory image for the PineTab2 (20250731) has been released: https://echo.danctnix.org:7269/factory_images/pinetab2/20250731/

Flash the image to your SD card using dd or Win32DiskImager, boot with the SPI/eMMC disable switch (optional if the bootloader is working) and follow the instructions using the volume and power key. You may only use this if you need to reset the PineTab2 to factory defaults.

If you're getting an error regarding the linux-firmware package such as:

```
linux-firmware-nvidia: /usr/lib/firmware/nvidia/ad103 exists in filesystem
linux-firmware-nvidia: /usr/lib/firmware/nvidia/ad104 exists in filesystem
linux-firmware-nvidia: /usr/lib/firmware/nvidia/ad106 exists in filesystem
linux-firmware-nvidia: /usr/lib/firmware/nvidia/ad107 exists in filesystem
```

Please read [linux-firmware >= 20250613.12fe085f-5 upgrade requires manual intervention](https://archlinux.org/news/linux-firmware-2025061312fe085f-5-upgrade-requires-manual-intervention/) from Arch Linux news. 

### Mesa (GPU)
[Luigi311 (Luis Garcia) has tested a patch](https://mastodon.social/@Luigi311/114742172122480704) which rearranged texture format to BGRA meaning the GPU driver doesn't have to do format conversion and thus, massively improved performance for certain applications. The patch has merged to upstream mesa and will be available in the next mesa release. You can check out the patch [here](https://gitlab.freedesktop.org/mesa/mesa/-/merge_requests/35678)

## PinePhone Pro
### Mainlining project

The PinePhone Pro is currently running a near mainline kernel, but the PinePhone Pro tree currently requires a number of patches (114 commits to be specific) on top to be usable. 

In light of this, community member [LogicalErzor](https://codeberg.org/LogicalErzor) has created a guide on how to submit patches upstream towards the effort of making the number of patches needed to zero. The guide goes into detail on building, testing and upstreaming patches. If any community members are interested in helping out with this effort you can find the guide below.

https://forum.mainlining.org/t/upstream-pinephone-pro-patches/138

### FreeBSD port
There is a new FreeBSD port for the PinePhone Pro that is being developed by [Toby](https://mastodon.social/@tobykurien) and [Stephan (@hnygd)](https://mastodon.africa/@hnygd). Currently there is an image available for users to test that includes a minimal Xorg desktop environment and an on-screen keyboard. [The latest update](https://github.com/hny-gd/freebsd-doc/blob/main/website/content/en/status/%20%20%20%20report-2025-04-2025-06/pinephone.adoc) includes touchscreen driver support, limited networking support via the headphone jack, drive along with the aforementioned minimal desktop setup. In terms of what's planned in the future, the plan is to bring a working USB and WiFi driver to FreeBSD which will make the device much easier to develop with. Pictured below is a demo of the PinePhone Pro running OS/2 Warp under QEMU on FreeBSD by Stephan (that's a mouthful). 

![PinePhone Pro running FreeBSD](/blog/images/August_2025/freebsd.jpeg)

#### Contributors welcome!
Toby and Stephan are looking for contributors to help with testing, feedback, upstreaming and driver development. If you're interested in this project you can get in touch with them with the links on the repository.

https://codeberg.org/Honeyguide/freebsd-pinephonepro

## Blisp
{{< credits "Authors: Ralimtek" >}}

This is a small note that blisp (used for programming the Pinecilv2 and other Bouffalo IC's) has tagged out and released the 5th release.
Version `0.0.5` has been released. There is a lot of cleaning up and improvements in there, including BL808 support and (basic) hex file support.

## Want to contribute to the next community update?

Do you have a cool project that you're working on that you'd like to be mentioned in these blog posts? Is there something you're interested in that you'd like to write about related to Pine64? If you're interested, please contact us!

- Camden/CarbonatedCaffeine: 
  - @carbonatedcaffeine (Discord)
  - @endernightlord:matrix.org (Matrix)
  - camden.b@pine64.org (email)