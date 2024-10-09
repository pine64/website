---
title: "Using the optional NVMe adapter"
draft: false
menu:
  docs:
    title:
    parent: "Pinebook_Pro/Guides"
    identifier: "Pinebook_Pro/Guides/Using the optional NVMe adapter"
    weight: 
---
	
The optional NVMe adapter allows the use of M.2 SSDs that support the NVMe standard (SATA is not supported).  The adapter supports **M** and **M**+**B** keyed devices, in both 2242 and 2280 physical sizes, which are the most commonly available. In addition, 2230 and 2260 sizes are also supported, though NVMe devices that use those sizes are rare.

Make sure to read the notes in [Accessory compatibility](/documentation/Pinebook_Pro/Accessory/Compatibility) before selecting an M.2 SSD for your Pinebook Pro, because there are certain limitations.  Once you have fitted and tested your NVMe drive, please consider adding a note to that page  

Please see [a separate section](/documentation/Pinebook_Pro/Troubleshooting#nvme_ssd_issues)  that describes reported issues with the NVMe drives in Pinebook Pro.

## Installing the adapter

The V2.1-2019-0809 SSD adapter that shipped with the initial Pinebook Pro batches had significant issues. A repair kit will be shipped to address those issues.
(If necessary, it can be modified to work. There is [an unofficial tutorial on the forums](https://forum.pine64.org/showthread.php?tid=8322&pid=52700#pid52700) describing these modifications.)

The updated SSD adapter, labeled V2-2019-1107, takes into account the prior problems with touchpad interference. New orders as of Feb. 22nd, 2020 will be the updated adapter.

This is the link to the Pinebook Pro accessories in the store: https://pine64.com/?v=0446c16e2e66

Actual installation instructions are a work in progress. Unofficial instructions for installing V2-2019-1107 can be found [here](https://eli.gladman.cc/blog/2020/06/23/pine-book-pro-nvme.html).

## Post NVMe install power limiting

Some NVMe SSDs allow reducing the maximum amount of power. Doing so may reduce the speed, but it may be needed in the Pinebook Pro to both improve reliability on battery: Some NVME may be stable with default settings when runnning on AC power but cause frequent kernel panics (system freeze with power LED blinking red/green) when running on battery. Reducing NVME power drain solves this in some cases. And reducing power used gives better battery life.
Here are the commands to obtain and change the power settings. The package 'nvme-cli' is required to run these commands. The example shows how to find the available power states, and then sets it to the lowest, non-standby setting, (which is 3.8 watts for the device shown):

```console
$ sudo nvme id-ctrl /dev/nvme0
NVME Identify Controller:
...
ps    0 : mp:9.00W operational enlat:0 exlat:0 rrt:0 rrl:0
         rwt:0 rwl:0 idle_power:- active_power:-
ps    1 : mp:4.60W operational enlat:0 exlat:0 rrt:1 rrl:1
         rwt:1 rwl:1 idle_power:- active_power:-
ps    2 : mp:3.80W operational enlat:0 exlat:0 rrt:2 rrl:2
         rwt:2 rwl:2 idle_power:- active_power:-
ps    3 : mp:0.0450W non-operational enlat:2000 exlat:2000 rrt:3 rrl:3
         rwt:3 rwl:3 idle_power:- active_power:-
ps    4 : mp:0.0040W non-operational enlat:6000 exlat:8000 rrt:4 rrl:4
         rwt:4 rwl:4 idle_power:- active_power:-
```

```console
$ sudo nvme get-feature /dev/nvme0 -f 2
get-feature:0x2 (Power Management), Current value:00000000
$ sudo nvme set-feature /dev/nvme0 -f 2 -v 2 -s
set-feature:02 (Power Management), value:0x000002
```

Some NVMe SSDs don’t appear to allow saving the setting with "-s" option. In those cases, leave off the "-s" and use a startup script to set the non-default power state at boot. If you want to test performance without saving the new power setting semi-permanantly, then leave off the "-s" option.

On systemd based distributions like Manjaro, a non-default power state for an NVME can be set using a systemd service. This is useful in cases where the NVME drive does not save the power state and/or uses APST. An example systemd service, nvme-throttle.service, is shown below:

    [Unit]
    Description=Throttles NVME to lesss power hungry mode
    After=suspend.target hibernate.target hybrid-sleep.target suspend-then-hibernate.target

    [Service]
    Type=oneshot
    ExecStart=/usr/bin/nvme set-feature /dev/nvme0 -f 2 -v 1

    [Install]
    WantedBy=multi-user.target suspend.target hibernate.target hybrid-sleep.target suspend-then-hibernate.target

Here the value after "-v" is the maximum power state that you want your SSD to use. This will be executed at system startup, and every time your system exits any suspend mode that might reset the SSD to default values.

This file needs to be placed in the /etc/systemd/system directory. Afterwards, to activate the service, run:

    systemctl daemon-reload
    systemctl enable --now nvme-throttle.service

There is another power saving feature for NVMes, APST, (Autonomous Power State Transitions). This performs the power saving & transitions based on usage. To check if you have a NVMe SSD with this feature:

```console
$ sudo nvme get-feature -f 0x0c -H /dev/nvme0
```

Information for this feature, (on a Pinebook Pro), is a work in progress. It is enabled by default in latest Manjaro kernels and reported to work.
On some NVME SSDS (WD), APST is compatible with limiting NVME maximum power: APST will work and not exceed maximum power state defined using
previous method.

## Using as data drive

As long as the kernel in use has both the PCIe and NVMe drivers, you should be able to use a NVMe drive as a data drive. It can automatically mount when booting from either the eMMC or an SD card. This applies to Linux, FreeBSD, and Chromium, using the normal partitioning and file system creation tools. Android requires testing.

## Using as OS root drive

The SoC does not include the NVMe boot code, so the NVMe is not in the SoC’s boot order. However, using the [U-Boot update script](https://github.com/mrfixit2001/updates_repo/blob/v1.1/pinebook/filesystem/mrfixit_update.sh) from the mrfixit2001 Debian or [Arglebargle’s modified script](https://pastebin.com/raw/EeK074XB), and [the modified u-boot images](https://github.com/pcm720/rockchip-u-boot/releases) provided by forum user pcm720, you can now add support to boot from an NVMe drive. Binary images are useable with SD, eMMC, and [SPI flash](/documentation/Pinebook_Pro/Features/SPI). For OS images using the mainline kernel, there are a few variants of U-Boot available that also support NVMe as the OS drive. Though these may require writing the U-Boot to the SPI flash for proper use of the NVMe as the OS drive.

The current boot order, per last testing, for this modified U-Boot is:

* MicroSD
* eMMC
* NVMe

For more information, please refer to [the forum post.](https://forum.pine64.org/showthread.php?tid=8439&pid=53764#pid53764)

It is also possible to initially boot off an eMMC or SD card, then transfer to a root file system on the NVMe. Currently, it is necessary to have the U-Boot code on an eMMC or SD card. (A forum member [posted here](https://forum.pine64.org/showthread.php?tid=8439) about using a modified version of U-Boot with NVMe drivers, that uses **/boot** and **/** off the NVMe drive. So this may change in the future.)

Please see [Bootable Storage](/documentation/Pinebook_Pro#bootable_storage).
