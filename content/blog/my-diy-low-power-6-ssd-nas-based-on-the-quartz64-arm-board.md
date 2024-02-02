---
title: "My DIY low-power 6 SSD NAS based on the Quartz64 ARM board"
date: "2022-06-03"
categories: 
  - "news"
  - "quartz64"
tags: 
  - "nas"
  - "quartz64"
cover: 
  image: "Q64-Nas-build-JF-1230x692.jpg"
images:
  - "Q64-Nas-build-JF-1230x692.jpg"
---

ARM SBCs have been around for a few years now. They were made popular and accessible mostly by [the RaspberryPi released in 2012](https://en.wikipedia.org/wiki/Raspberry_Pi).

I've been enjoying building countless projects around these boards : web servers, home-automation, camera recording, IM bots,…

A new trend has recently appeared in the SBC world : the PCIe slot! The RaspberryPi 4 Compute Module exposes it via the [IO board](https://www.raspberrypi.com/products/compute-module-4-io-board/), and the [Pine64](https://www.pine64.org/) [RockPro64](https://www.pine64.org/rockpro64/) is equipped with a PCIe 4x open-ended slot directly on the board.

I haven't had the opportunity to get hold of one of these boards, but I'm lucky enough to have a [Quartz64 model A](https://www.pine64.org/quartz64a/) on hands.  
The Quartz64 is based on the Rockchip RK3566 running @1.8Ghz. My board is equipped with 8GB of RAM. It also has Gigabit ethernet, 1 SATA connector, USB3, and of course, the PCIe port.

I experimented a bit with the PCIe interface by testing a couple of PCIe boards I had on hands at that time : the [SATA controller board from Pine64](https://pine64.com/product/pcie-to-dual-sata-iii-interface-card/) and an Intel 4x GBe board : they worked out of the box! Awesome, isn't it?

![](/blog/images/4nics2-768x1024.jpg)

4xGbe PCIe card installed on the Quartz64

![](/blog/images/sataboard-1024x378.jpg)

2 SSDs connected to the Quartz64 via the SATA controller boad

I had an idea in the back of my mind : create a DIY low-power NAS based on a cheap SBC that can handle more than 2 drives (up to 6, preferably) without using USB. And it looks like this project is now completely possible! So… Let's do it!

## The prototype

The first prototype was very rough : everything was laying on my desk, with all the wires dangling around. It was a bit messy, but it allowed me to check that the drives were working correctly.

![](/blog/images/nas-proto1.jpg)

When I ensured that everything was working as expected, I bought a few more items : the SATA controller with 6 ports and an enclosure for 6 2.5" SATA drives.

![](/blog/images/nas-proto2-1024x635.jpg)

## How to properly power an SBC and 6 drives?

This question haunted me for some time.

For now, the SBC is powered by a 12V power brick via a barrel connector. And the disks are powered by the board using those [specific power cables by Pine64](https://pine64.com/product/rockpro64-power-cable-for-dual-sata-drives/). If I understand correctly, this cable is connected to the 12V power supply from the board and embeds voltage s to provide 12V and 5V/3.3V to the disks.

It works fine with 2 drives but… I want 6 of them! And I'm not sure those voltage regulators would support more than 2 drives.

I could probably find a PSU that outputs 12V, 5V and 3.3V, build the wires and adaptors by finding the correct connectors, etc. Buuut… That looked too difficult for me, and I doubt the result would have been elegant and safe.

The solution I implemented is the PicoPSU. It's a very small yet powerful DC-DC converter that is designed to power embedded PCs. It comes in the forms of small PBC mounted on a standard ATX connector that fits directly in the ATX connector of any standard motherboard.

It looks good but the Quartz64 does not have that ATX power connector! Fortunately, I remember [a blog post on CNX-Soft](https://www.cnx-software.com/2021/07/23/5-board-eases-atx-power-supply-connection-to-single-board-computers/) about an ATX breakout board. It has the ATX power connector on 1 side, a screw terminal for +12V, -12V, 5V and 3.3V on the other side, and a switch and a few fuses in between.

The following picture shows the PicoPSU on the top and the ATX breakout board in the middle. The PicoPSU receives 12V from the black and white connector on the left. The Quartz64 is powered by the red and white wires on the bottom, and the SSDs by the classic red/yellow/black wires on the right.

![](/blog/images/power-supply-1024x783.jpg)

## An SBC in an ATX case

This setup with 2 SSDs ran for a few months. But it's still messy and fragile. I wanted to clean that up!

So I wanted to find a box to secure the whole build and hide all those wires… without breaking the bank!  
The only compatible case I could find was the [NAS enclosure from Pine64](https://pine64.com/product/rockpro64-metal-desktop-nas-casing/) but it supports only 2 drives.

I quickly figured I would need to tinker something based on a case that was not specifically designed to be compatible with the Quartz64! But hey! While I can do a lot of things with my 10 fingers on a keyboard, I'm not that good with my 2 hands and a screwdriver!  
So I did not want to buy a shiny new case that I would certainly break while trying to drill a hole or something!

Luckily, I found an old (Pentium4-era) desktop computer that was going to be thrown to the landfill. I thought I could salvage the case and probably recycle the insides of that prehistoric computer!

![](/blog/images/p4-1-615x1024.jpg)

![](/blog/images/p4-2-1024x950.jpg)

So I emptied the case, cut the I/O shield with my Dremel and cut a thin aluminum plate so that it would fit in the case.

![](/blog/images/case-1-768x1024.jpg)

![](/blog/images/case-2-768x1024.jpg)

![](/blog/images/case-3-768x1024.jpg)

![](/blog/images/case-4-768x1024.jpg)

And I then drilled holes to fit the ATX breakout board, the PicoPSU and the Quartz64 with the SATA board.

![](/blog/images/case-5-768x1024.jpg)

![](/blog/images/case-7-768x1024.jpg)

![](/blog/images/case-11-768x1024.jpg)

![](/blog/images/case-9-768x1024.jpg)

While it's not finished yet, I'm already pretty happy with the result so far! I'm planning on improving this build with an I/O shield for USB and Ethernet, connect the power button, the LEDs,… but that's a project for another day!

## The hardware

Here are more details about the hardware I used in this build:

- [The Quartz64 ARM SBC from Pine64](https://www.pine64.org/quartz64a/) : the brain of the system
- [A 6x SATAIII controller board based on the ASM1166 chipset](https://www.kalea-informatique.com/6x-sata-iii-6gbps-ahci-port-multiplier-aware-low-profile-pcie-3-0-host-adapter.htm)
- [A PicoPSU-150-XT DC-DC power supply](https://www.onlogic.com/picopsu-150/). 150W is probably way too much, it has 2 SATA power connectors, so that will make my setup easier.
- [An Icy Dock ExpressCage MB326SP-B](https://www.icydock.com/goods.php?id=231). This nice enclosure fits in a 5.25" bay and supports up to 6x 2.5" SATA drives.
- 6 SATA SSDs
- An ATX break-out board, SATA cables, various connectors and wires I had on hands or bought for cheap on various web shops.

## Linux distro

I installed [the latest dev image from ManjaroARM](https://github.com/manjaro-arm/quartz64-a-images/releases) on the eMMC flash module. Note that the support for the Quartz64 and the RK3566 is still in early development stage. So I expect a few issues and bugs, and I also expect for the support to improve very quickly in the next weeks and months!

As the PCIe controller is not supported yet in the default kernel (`linux-rc`, currently version 5.18-rc7), I switch to the kernel `linux-quartz64` (version 5.17.0). Full support of PCIe should be added in kernel 5.19. Stay tuned :)

## PCIe and DTS

The proof that the support for the board is still pretty new is that at first, the filesystem on the SSD would corrupt as soon as I copied big files (> 4GB) on the disk.  
This was apparently caused by an issue with the memory allocation for the SATA driver. With the help of the folks in [the chat room dedicated to the Quartz64](https://wiki.pine64.org/wiki/Main_Page?title=Main_Page#Chat_Platforms), we were able to patch the DTS/DTB files to work around this issue.  
Those patches are not applied yet in newer manjaro images so I'll provide these patches here. Use them at your own risks, of course! Neither I or the original author of those patches will be responsible for any issue that could occur when using those files!

- [0001-arm64-dts-rockchip-enable-rk356x-proper-msi-support-1.patch](https://gist.github.com/JF002/c0167cfe8cb90126e78fc064c346659e#file-0001-arm64-dts-rockchip-enable-rk356x-proper-msi-support-1-patch)
- [0001-arm64-dts-rockchip-rk356x-move-to-lower-pcie-address-2.patch](https://gist.github.com/JF002/c0167cfe8cb90126e78fc064c346659e#file-0001-arm64-dts-rockchip-rk356x-move-to-lower-pcie-address-2-patch)
- [0001-arm64-dts-rockchip-fix-rk356x-pcie-large-address-spa.patch](https://gist.github.com/JF002/c0167cfe8cb90126e78fc064c346659e#file-0001-arm64-dts-rockchip-fix-rk356x-pcie-large-address-spa-patch)

Linux 5.19 should bring support for the PCIe controller on the Quartz64 and applying those patches won't be needed anymore!

## Raid : ZFS?

ZFS is very trendy right now, and I wanted to do some experiments with this very popular filesystem. Unfortunately, ZFS is not included in the Linux kernel. So you have to build the kernel module manually. ArchLinux and Manjaro provide the package in the AUR so the installation was not that difficult.

It worked quite well until ManjaroARM updated the kernel to a newer version that is not yet supported by the ZFS driver.  
As I said earlier, the support for the Quartz64 is under heavy development, and Manjaro integrates bleeding edge versions of the kernel to provide the most up-to-date experience.

The Linux kernel is so bleeding edge that the ZFS module was not updated yet when I installed the new kernel on my setup, and it broke my shiny new ZFS filesystem.

I didn't want my system to break randomly each time I ran `pacman -Syu` so… I decided ZFS was not the best fit for me right now.

## BTRFS in mirror mode on 2 SSDs

At the beginning, I could find a good deal for only 2 SSDs. So after ZFS, I decided to test BTRFS. RAID 5 and 6 are not yet production-ready with BTRFS, but RAID 0 and 1 are completely supported. I've finally settled to format them in mirror mode (RAID 1).

This array will host the services I'll run on this service : docker containers, my Matrix home-server and probably many others in the future!

## mdraid RAID-5 for 4 SSDs

I finally found a good deal for the 4 remaining SSDs, and I decided to use `mdraid` RAID 5 for these 4 drives.

I'll use this array as data storage.

## What does it look like?

A screenshot is better than a thousand words!

![](/blog/images/nas-2raid-1024x576.png)

## Benchmarks

As soon as I showcased my project, a lot of people asked about the performances of this setup. So here are a few numbers!

You'll quickly notice that those are not the performances you were hoping for.  
But in my opinion, knowing that everything worked nearly out of the box, those numbers are already quite great. And we'll probably see those performances increase as the support for the board and the CPU improves in the near future!

## Benchmarks with `dd`

- Read directly from the block device:

```
# dd if=/dev/sdc of=/dev/null bs=4M status=progress iflag=direct
15497953280 bytes (15 GB, 14 GiB) copied, 44 s, 352 MB/s^C
3728+0 records in
3727+0 records out
15632171008 bytes (16 GB, 15 GiB) copied, 44.4116 s, 352 MB/s
```

- Read from the BTRFS mirror array:

```
# dd if=bigfile.raw of=/dev/null bs=4M status=progress iflag=direct
31914983424 bytes (32 GB, 30 GiB) copied, 154 s, 207 MB/s
7609+1 records in
7609+1 records out
31914983424 bytes (32 GB, 30 GiB) copied, 154.001 s, 207 MB/s
```

- Write to the BTRFS mirror array:

```
# dd if=/dev/zero of=./temp_zero bs=4M status=progress oflag=direct
6236930048 bytes (6.2 GB, 5.8 GiB) copied, 61 s, 102 MB/s^C
1497+0 records in
1497+0 records out
6278873088 bytes (6.3 GB, 5.8 GiB) copied, 61.5351 s, 102 MB/s
```

- Read from the `mdraid` RAID 5 array:

```
# dd if=bigfile.raw of=/dev/null bs=4M status=progress iflag=direct
31822184448 bytes (32 GB, 30 GiB) copied, 85 s, 374 MB/s 
7609+1 records in
7609+1 records out
31914983424 bytes (32 GB, 30 GiB) copied, 85.2706 s, 374 MB/s
```

- write to the `mdraid` RAID 5 array:

```
# dd if=/dev/zero of=./temp_zero bs=4M status=progress oflag=direct
4123000832 bytes (4.1 GB, 3.8 GiB) copied, 40 s, 103 MB/s^C
983+0 records in
983+0 records out
4123000832 bytes (4.1 GB, 3.8 GiB) copied, 40.0076 s, 103 MB/s
```

## Samba benchmarks

- Read from the BTRFS mirror array : 70Mio/s
- Write to the BTRFS mirror array : 90Mio/s
- Read from the `mdraid` RAID 5 array : 60Mio/s
- Write to the `mdraid` RAID 5 array : 90Mio/s

## Power Consumption

8W (idle) - 12W (load)

## Next steps

On the hardware side, I would like to improve the wiring and cabling by adding an I/O shield for the ethernet and USB ports, add a power button, a reset button, a power led, and maybe paint the case to make it prettier.

I would also like to see how we could improve the performances of the system. There are probably configuration issues or bottlenecks that could be improved.

And finally, I would like to put this new server and NAS to good use! It's already running my Matrix home-server. I would also like to store music and movies for my home theater and probably many other things in the future!
