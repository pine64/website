---
title: "Upgrade PineTime to InfiniTime 1.0.0"
draft: false
menu:
  docs:
    title:
    parent: "PineTime/Software"
    identifier: "PineTime/Software/Upgrade_to_InfiniTime_1_0_0"
    weight: 
---

**Devices shipped before July 2021 were pre-installed with InfiniTime 0.7.1, and an older bootloader. This features green text 'PINE TIME' on boot, and should be updated to the new bootloader as described below.**

**Devices shipped after July 2021 were pre-installed with InfiniTime 1.2 and the new bootloader, which can be identified by the green Pinecone image on boot. The instructions below are unnecessary for these devices.**

Congratulations on receiving your new PineTime!

So now you’re probably wondering exactly how on earth do you go about upgrading your watch to the latest and greatest version of InfiniTime - you know, that version you’ve seen all those great pictures, videos and reviews of. To those of us that are developing stuff for it, it’s pretty easy and straightforward, but like with all technology, it is a bit tricky.

{{< admonition type="warning" >}}
 Some people ran into issues during the update process that would temporarily make their watch unusable (display frozen or blank). The only know workaround consists of waiting for the battery to drain completely and try again. With the display off, and battery fully charged, you can expect a wait of 5-7 days so it is best to not fully charge it. If it freezes with the display on, it will likely be flat by the end of the day. We’ve never heard of any PineTimes that were permanently bricked (were not recoverable), though. 
{{< /admonition >}}

In a nutshell, you need to:

1. Charge your watch, but **not** to 100% - keep it at approximately 50% - for the reason described above.
2. Update InfiniTime
3. Update the bootloader
4. Install the recovery firmware

## Update Process

So how do you do this? Where do you start? Well, with a sealed PineTime, your only easy option is via Over The Air (OTA) Device Firmware Update (DFU), which is done via Bluetooth. There are a couple of different ways and apps you can use to do this. If you have an Android device, you can use [Gadgetbridge](https://f-droid.org/en/packages/nodomain.freeyourgadget.gadgetbridge/) or [NRFConnect](https://play.google.com/store/apps/details?id=no.nordicsemi.android.mcp) (NRFConnect is available on iOS devices as well). Otherwise, if your laptop or desktop computer has Bluetooth and runs Linux, you can use [Siglo](https://github.com/alexr4535/siglo) or [Amazfish](https://github.com/piggz/harbour-amazfish). You can also use these applications on your Pinebook Pro or Pinephone if you happen to have those devices.

The reason for installing the updates in the specified order is because newer versions of InfiniTime have a more robust Bluetooth update process, and since we’re updating everything over Bluetooth, the fewer retries and failures from that you have the better. It will still sometimes disconnect mid update, meaning you’ll need to try again, and possibly restart the watch a few times as well. And since the recovery firmware is new to the 1.0.0 version of the bootloader, it’s best to update that last.

[This video](https://video.codingfield.com/videos/watch/831077c5-16f3-47b4-9b2b-c4bbfecc6529) shows the bootloader and recovery firmware installation procedure.

[This video](https://video.codingfield.com/videos/watch/f7bffb3d-a6a1-43c4-8f01-f4aeff4adf9e) shows the bootloader installation and firmware update using Amazfish.

You can also read a [detailed installation procedure in the documentation of the bootloader](https://github.com/JF002/pinetime-mcuboot-bootloader/blob/339224cf5ed21f4e8b2d22eaeab9869120f7f752/docs/howToUpdate.md).

### Update InfiniTime

To update the main InfiniTime app, you want to flash [pinetime-mcuboot-app-dfu-1.0.0.zip](https://github.com/JF002/InfiniTime/releases/download/1.0.0/pinetime-mcuboot-app-dfu-1.0.0.zip).

After updating InfiniTime, ensure that you validate the firmware to prevent it from being automatically reverted/rolled back if your watch is reset/restarted. To do this, swipe right to access the quick actions panel, press the gear/settings icon, swipe up once to show the second page, press on the 'Firmware' option and then on 'Validate'.

[Video showing validation process](https://youtu.be/-5lwBd60k0Q)

#### Gadgetbridge

1. Connect your PineTime to GB
2. Download the aforementioned file to your phone
3. Find the file in your file manager
4. 'Open With' Gadgetbridge F/W Installer (method varies by device) - on my phone, it is press and hold, select the file, and then choose 'open with app' from the more options menu
5. Confirm that you wish to apply the update
6. Wait for the update to complete

[Video showing how to start the update](https://youtu.be/nAaaC7D5sVo)

#### NRFConnect (not recommended)

**The app is closed source and versions after 4.24.3 don’t work with the PineTime. We recommend you use GadgetBridge instead.**

1. Download the aforementioned file to your phone.
2. Open NRFConnect
3. Scan for your device
4. Connect to it
5. Choose the DFU option at the top right of the screen
6. Ensure the 'Distribution packet (ZIP)' option is selected, and press OK
7. Select your previously downloaded file
8. Wait for the update to complete

[Video showing how to start the update](https://youtu.be/jnX7WwYDiDE)

#### Siglo

1. If your device was not detected upon start, press "Rescan" to find it.
2. Select the "1.0.0" tag
3. Select the aforementioned file/asset.
4. Select "Flash It!"

#### Amazfish

1. Run Amazfish (service + UI)
2. Pair with you device:
   1. Unzip the DFU file to extract the .bin file.
   2. Click on "pair with watch" on the top
   3. Select "PineTime" (if your device is running InfiniTime 0.7.1 or lower) or "InfiniTime (if it’s running InfiniTime 0.8+) and choose your device in the list
3. Click on "Download file" on the top
4. Click on "Choose file" and select the .bin file you extracted from the DFU file
5. Click on "Send file"
6. Wait for the update to complete.

[See it in action!](https://video.codingfield.com/videos/watch/41cfcf5d-b0e6-4323-8056-b0a6682d1f25)

### Update the bootloader

To update the bootloader, you want to flash [reloader-mcuboot.zip](https://github.com/JF002/InfiniTime/releases/download/0.14.1/reloader-mcuboot.zip).
Once the bootloader is updated, you should notice that the boot logo has changed. Previously, it was a green "PineTime" logo, and now it is a large pinecone that is progressively drawn in green.

[Video showing what the InfiniTime 1.0.0 bootloader looks like](https://youtu.be/fvHQ8ZeqnOo)

#### Using Gadgetbridge

Same process as before, but with the file for this step.

#### Using NRFConnect

Same process as before, but with the file for this step.

#### Using Siglo

Same process as before, but select the "0.14.1" tag, and the file/asset for this step.

#### Using Amazfish

You may need to re-pair with your device by selecting "InfiniTime" (since you’ve already upgraded to InfiniTime 1.0) in the device type list. Then follow the same process as before, but with the file for this step.

### Install the recovery firmware

{{< admonition type="warning" >}}
 Don’t do this before updating the bootloader, otherwise your PineTime will freeze at the end of the process, and you will need to wait for the battery to go flat 
{{< /admonition >}}

To install the recovery firmware, you want to flash [pinetime-mcuboot-recovery-loader-dfu-0.14.1.zip](https://github.com/JF002/InfiniTime/releases/download/0.14.1/pinetime-mcuboot-recovery-loader-dfu-0.14.1.zip). You will know when this is running when it shows an InfiniTime logo with a progress bar running across the bottom whilst it is installing the recovery firmware.

#### Using Gadgetbridge

Same process as before, but with the file for this step.

#### Using NRFConnect

Same process as before, but with the file for this step.

#### Using Siglo

Same process as before, but with the file/asset for this step.

#### Using Amazfish

Same process as before, but with the file for this step.

## Troubleshooting

Sometimes during the update process, the connection will drop, and the update will fail. Your PineTime isn’t broken, most likely the Bluetooth link dropped for a moment, so just try again. Try rebooting your phone, if it keeps failing, try restarting the watch by holding the power button down for approximately 8 seconds. Try to **avoid** holding down the button with the screen off. Or try with another device, just in case there are compatibility issues.

Version 1.0.0 of InfiniTime is merely the first version that was considered sufficiently feature-complete and stable enough for daily use. This isn’t to say there aren’t still bugs present ('cause there are!). So there are a few bugs still present in the update process and the bootloader. One unfortunate bug appears to be that sometimes when the watch tries to restart after an update, the bootloader locks up, and the watch won’t turn on. In this case, you will need to wait until the watch battery goes flat, to force the watch to reset. This will most likely involve waiting for a week, and then when you put the watch on the charging cradle, it will power up and you should be right to try again.

If you get stuck or have any questions, join us on your preferred [chat platform](/documentation#Chat_Platforms) or the product [forum](https://forum.pine64.org/forumdisplay.php?fid=134). There’s usually someone available who can help, or will get back to you in a few hours.
