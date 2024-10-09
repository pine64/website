---
title: "Recovery"
draft: false
menu:
  docs:
    title:
    parent: "QuartzPro64"
    identifier: "QuartzPro64/Recovery"
    weight:
---

In the case you erase the eMMC and are unable to boot the board, you can use rkdeveloptool to recover the board. While you can use the [Pine64 Fork](https://gitlab.com/pine64-org/quartz-bsp/rkdeveloptool), it is recommended to use [cypheon’s Fork](https://gitlab.com/cypheon/rkdeveloptool/-/tree/main?ref_type=heads) until some Pending PRs are merged in to [resolve issues](https://gitlab.com/pine64-org/quartz-bsp/rkdeveloptool/-/merge_requests?scope=all&state=opened&author_username=cypheon) with larger files. This is important when working with the larger 64&nbsp;GB eMMC on the QuartzPro64.

With rkdeveloptool installed, you will also need the rk3588_spl from rockchip to init the memory/flash when in maskrom mode. This can be downloaded from the [rockchip-linux/rkbin repo](https://github.com/rockchip-linux/rkbin/blob/master/bin/rk35/rk3588_spl_v1.12.bin).

Entering maskrom can be done in a variety of ways:

* Hold the maskrom button (little white button labelled "MASKROM" next to SATA socket) during powerup, OR
* Enter rockusb mode, and execute "rkdeveloptool reboot-maskrom".
* Bork your eMMC and SD devices (how? erase?), in which case bootup will fallback to maskrom.

## Dumping the eMMC

Boot the device into maskrom mode, and then verify rkdeveloptool can see the board. ***# rkdeveloptool list***

    DevNo=1	Vid=0x2207,Pid=0x350b,LocationID=503	Maskrom

Once the board shows up, load the rk3588_spl you downloaded earlier, and verify that the eMMC can be seen.

```
**# rkdeveloptool boot ./rk3588_spl_loader_v1.08.111.bin**
Downloading bootloader succeeded.
**# rkdeveloptool read-flash-info**
Flash Info:
 	Manufacturer: SAMSUNG, value=00
 	Flash Size: 59000 MB
 	Flash Size: 120832000 Sectors
 	Block Size: 512 KB
 	Page Size: 2 KB
 	ECC Bits: 0
 	Access Time: 40
 	Flash CS: Flash<0>
```

You can now dump the eMMC using the read command. Note that first you have to calculate the eMMC size, which can be done using the output from the previous flash info command. You need to take the sector count, and times it by the sector size, to get the total number of bytes. So in the above example, 120832000*512 so the total flash size is 61865984000.

Using the calculated size, you can now dump the eMMC. Please note this will take 1-2 minutes.

```
**# rkdeveloptool read 0x0 61865984000 ./quartzpro64_emmc_dump.bin**
Read LBA to file (0%)
...
Read LBA to file (100%)
```

You now have a full dump of the entire eMMC (SHA256 62cb4ae8d02aeacccf231fa1d00087cdc74b599790a274569305693aa205318d). Note that you can also use the list-partitions and read-partition commands to dump specific partitions, but this only shows GPT partitions on the eMMC. Because of this, it will NOT include the spl_loader found in the first 4MB of the eMMC!

## Flasing the eMMC

Boot the device into maskrom mode, and then verify rkdeveloptool can see the board. ***# rkdeveloptool list***

    DevNo=1	Vid=0x2207,Pid=0x350b,LocationID=503	Maskrom

Once the board shows up, load the rk3588_spl you downloaded earlier, and verify that the eMMC can be seen.

```
**# rkdeveloptool boot ./rk3588_spl_loader_v1.08.111.bin**
Downloading bootloader succeeded.
**# rkdeveloptool read-flash-info**
Flash Info:
	Manufacturer: SAMSUNG, value=00
	Flash Size: 59000 MB
	Flash Size: 120832000 Sectors
	Block Size: 512 KB
	Page Size: 2 KB
	ECC Bits: 0
 	Access Time: 40
 	Flash CS: Flash<0>
```

You can now flash the device using either the write command, or write-partition command, depending on what you are trying to do. If you are looking to restore the entire eMMC from a backup you made, you would use the command below to accomplish this.

```
**rkdeveloptool write 0 ./quartzpro64_emmc_dump.bin**
```
