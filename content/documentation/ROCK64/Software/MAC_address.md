---
title: "MAC Address"
draft: false
menu:
  docs:
    title:
    parent: "ROCK64/Software"
    identifier: "ROCK64/Software/MAC_address"
    weight: 
---

To set the MAC address on ROCK64 with the "Android eMMC" image:

1. [Windows ADB driver package](http://files.pine64.org/doc/rock64/tools/DriverAssitant_v4.5.zip) installation is required as prerequisite
2. Download and unzip [WNpctool_V1.1.2_1226.zip](http://files.pine64.org/doc/rock64/tools/WNpctool_V1.1.2_1226.zip). Run WNpctool.exe "as Administrator" on Windows OS
3. Press recovery button on ROCK64 and power ON the ROCK64. After 2 seconds release the recovery button
4. Plug the USB Cable from Top USB2 slot of ROCK64 to PC USB slot (WNpctool will show "Found one loader" at the bottom)
5. Fill in LANMAC: with small letter MacAddress (e.g. 01234567abcd) then press on Write button
6. Unplug the USB Cable and reboot the ROCK64 and use DOS command "ping ..." and "arp -a" or [netscan](https://www.softperfect.com/products/networkscanner/) to check the MAC address of the ROCK64
