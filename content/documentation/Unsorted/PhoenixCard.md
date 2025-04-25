---
title: "PhoenixCard"
draft: false
menu:
  docs:
    title:
    parent: "Unsorted"
    identifier: "Unsorted/PhoenixCard"
    weight:
aliases:
  - /wiki/PhoenixCard
---

## How to Create MicroSD Card Android Image for Pine A64

### What do I need?

1. The PhoenixCard software from Allwinner.
2. You can download it [here](https://drive.google.com/file/d/0B0cEs0lxTtL3VmstaEFfbmU1NFk/view?usp=sharing)
3. A firmware image (.img files)
4. A SD-Card (best Class 10 with 8GB or more SD-Card) - backup everything first, the Card will be formatted!
5. An external SD-Card Reader
6. A Windows PC

### Step to create the SD-Card

{{< figure src="/documentation/images/PCard_Main.jpg" width="750" >}}

1. Extract the PhonixCard-xx.rar file into an empty directory.
2. Navigate into the directory where you installed PhoenixCard and start PhoenixCard.exe.
3. Click **DiskCheck** and choose the drive with your SD-Card
4. Click **Img File** and choose the file you want
5. Write Mode must be set to **Startup**
6. Press **Burn**
7. Wait until the burning process is finished (you will see the progress in the progress bar and the notification window)

### Booting Up the SD-Card

1. Insert the SD-Card into the Pine64 and Power-up
2. On the first time boot-up, it might take up to 5 minute for the system to get ready
3. On the sub-sequence boot-up, it will only take about 40 to 60 second for the system to get ready

## Related Reference

* [Easily Create an Android Bootable SD Card for Allwinner A80 Devices with PhoenixCard Tool](https://www.cnx-software.com/2015/01/06/easily-create-an-androidlinux-bootable-sd-card-for-allwinner-a80-devices-with-phoenixcard-tool/)
* [PhoenixCard Tutorial YouTube Video](https://www.youtube.com/watch?v=eKo82AUgbFM)
