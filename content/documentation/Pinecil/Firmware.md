---
title: "Firmware"
draft: false
menu:
  docs:
    title:
    parent: "Pinecil"
    identifier: "Pinecil/Firmware"
    weight: 6
---

This document provides a step-by-step guide on how to update the firmware of the Pinecil soldering iron, applicable to both V1 and V2 models. Keeping your firmware up to date ensures that you have the latest features, improvements, and bug fixes.

## Overview

{{< admonition type="tip" >}}
Pinecil is designed to use **only 1 power port** at any time. Only the USB-C cable should be plugged in during firmware updates. Never attempt to use both rear ports at the same time or the PC and Pinecil will be damaged.
{{< /admonition >}}

{{< figure src="/documentation/images/Pinecil-V1andV2.png" width="400" >}}

The firmware that comes with the Pinecil is [open source Ralim’s IronOS](https://ralim.github.io/IronOS/). It’s a good idea to check for updates regularly as development is very active and there may be enhancements or bug fixes.

Depending on whether you have a Pinecil V1 or V2, they are updated using different flashers since they have completely different MCU chip (brains). The V1 is any Pinecil sold up to July 2022 (has a blue thumb grip). The V2 is any Pinecil sold after Aug 1, 2022 (has a green thumb grip). If you don’t have the two models mentioned, then you might not have an [authentic Pinecil](/documentation/Pinecil/Authenticity). This aritcle is designed and tested on authentic Pinecils only.

* Go to the appropriate section below depending on if you have a V1 or V2 model.
* Long hold down `[-]` to see the current firmware version installed.
* It is very hard to brick a Pinecil doing a firmware update because of the firmware is in ROM. Usually, just re-flashing it fixes it. Even if the other firmware caused the screen to go black, one could connect, put the Pinecil into flash mode, and flash again to an older or newer version of firmware or a beta version.
* Pinecil V1 only uses *.hex files for both firmware and boot logo art.
* Pinecil V2 uses only *.bin files for firmware.

{{< admonition type="note" >}}
 Loading boot logo art onto the V2 (BL706 MCU chip) is not yet possible. Volunteers are looking into this on both GitHub Blisp and GitHub IronOS. If you would like to see the progress or help with the code see [Boot Logo Art ticket](https://github.com/Ralim/IronOS/issues/1373#issuecomment-1414925011)
{{< /admonition >}}

## Flash Mode

{{< admonition type="important" >}}
 Do not use the DC barrel jack while updating firmware or you may destroy your PC and Pinecil.
{{< /admonition >}}

Both V1 and V2 connect to the PC/laptop and enter the Flash mode the same way for updating purposes:

1. Plug one end of the USB cable to the PC/laptop.
2. Long hold the `[-]` button _before plugging_ the USB-C cable into the back of the Pinecil. Keep holding down the `[-]` for ~10-15 seconds after plugging in the cable, then release the button.
3. Screen should be black/empty which means Pinecil is in Flashing Mode. If you have issues, try again, do not plug the USB-C cable into Pinecil until you first press & hold the `[-]` button. Flip the cable over or try another port/cable/PC if you still have issues.
4. Unlike irons from other brands, Pinecil will **not** show in the PC as a USB data drive. On Windows, you will hear a single beep when connected in flash mode.
5. Then use one of the flasher methods below based on the OS you have in order to flash new firmware ([older V1 instructions are lower down here](/documentation/Pinecil/Firmware/#update_v1)).

## Update V2: Windows

{{< admonition type="important" >}}
 Do not use the DC barrel jack while updating firmware or you may destroy your PC and Pinecil.
{{< /admonition >}}

### Option 1: PineFlash

The PineFlash is a GUI updater it’s an all-in one app that downloads firmware and flashes.
	
* Download the easy premade binary installer for Windows [here](https://github.com/Spagett1/PineFlash).
* If PineFlash doesn’t work try the Blisp terminal app.

### Option 2: Blisp

1. Blisp is a CLI (command line interface or terminal) and needs a program like the Powershell, which is already installed on most Windows PCs. For using Blisp only a couple basic terminal commands are needed, such as `cd` to change directories (folders).
2. If you prefer to use "command" terminal over Powershell, see instructions for Command in [Troubleshooting and then skip to #8 here](/documentation/Pinecil/Firmware/#troubleshoot_v2_flashing)
3. Can install newest Powershell [from here](https://learn.microsoft.com/en-us/powershell/scripting/install/installing-powershell-on-windows?view=powershell-7.3).
4. Rick click and run Powershell as administrator.
5. Enter this command `C:\> Set-ExecutionPolicy RemoteSigned` to enable powershell permissions. It only needs to be done one time and should persist on reboots.
6. Check that Powershell has correct permissions,enter `Get-ExecutionPolicy -list`
7. LocalMachine should be RemoteSigned.
8. For V2, download the [Blisp Flasher here](https://github.com/pine64/blisp#how-to-update-pinecil-v2).
9. Next download the newest firmware, [release here](https://github.com/Ralim/IronOS/releases/). Scroll down to the bottom of the page, under Assets, get the Pinecilv2.zip.
10. Right click on all zip files > properties, and check "Unblock" if present to unblock them, then extract the Blisp zip and the Pinecilv2 zip [screenshot of Unblock here](https://github.com/builder555/PineSAM/discussions/106#discussion-4960445). If you don’t see "Unblock" then keep going.
11. From the Pinecilv2 folder you extracted above, copy the `Pinecilv2_EN.bin` (English) file into the Blisp folder (same place as the Blisp.exe). Other languages are available, substitute the `Pinecil_EN.bin` file for the language file desired (follow 2-letter international language code). The Pinecil Zip can now be deleted, only the single BIN file in the language you want is used.
12. Run powershell as administrator.
13. Now, connect the Pinecil V2 to the PC: hold down the [-] **Before** plugging the cable to the back of Pinecil. See ([Flash Mode section for details](/documentation/Pinecil/Firmware/#flash_mode)).
14. Screen on Pinecil should be black/empty before proceeding; it means you are in the correct Flash mode. If you are curious, it will connect as a PORT COM device in Device Manager. If your screen is not black, then repeat the connect to PC above. If necessary, change cables or ports, or try a different PC/laptop.
15. Use `cd` to change to the Blisp folder (location of blisp.exe and Pinecil_EN.bin).
   1. `#example change to location of blisp folder`
   2. `PS C:\> cd G:\Users\name\Downloads\blisp\`
16. Execute this line (can replace the **EN** file name with the language bin selected).
   1. Type the `.\` (dot and slash) or it will fail to find the files!
   2. `.\blisp.exe write -c bl70x --reset .\Pinecilv2_EN.bin`
17. After update, unplug and reboot it, then hold down `[-]` for ~3 seconds to see the new version.
18. See [troubleshooting](/documentation/Pinecil/Firmware/#troubleshoot_v2_flashing) down below if it does not flash.

## Bluetooth (BLE) Apps

* Must have newer Pinecil V2 model (green thumb grip).
* First, update firmware to **Ralim’s IronOS 2.21** or higher. 2.21 is the first stable release that has BLE support built-in for Pinecil V2.
* Get the [PineSAM app here](https://github.com/builder555/PineSAM) or try [Joric’s BLE website here](https://joric.github.io/pinecil/). These BLE apps are also listed in [Development projects](/documentation/Pinecil/Development_projects)
* [Joric’s BLE API](https://joric.github.io/pinecil/) may be the easiest to get started with as it does not require anything to be installed. It runs off Chromium based browsers (since they are capable of BLE GATT) and shows a graph of Temperature/Watts (MacOS/iPhone and firefox don’t work bc they do not have BLE GATT). Hint: some Chromium browsers like Vivaldi, may need to check `chrome://flags/` and enable bluetooth options.
* [PineSAM](https://github.com/builder555/PineSAM) is BLE Settings and Menus and will run on any major OS. It allows change of all settings, and can be controlled from Mac, Linux, Windows, iPhone, Android and more; needs python script running as back end. For easy phone connection just open a browser address `http://<ipaddress of PC running script>:8080/` (see PineSAM website for details)

## Update V2: Linux and Mac

{{< admonition type="important" >}}
 Do not use the DC barrel jack while updating firmware or you may destroy your PC and Pinecil.
{{< /admonition >}}

### Option 1: PineFlash

PineFlash is a GUI updater that downloads firmware and flashes. Download the easy premade binary for [Linux here](https://github.com/Spagett1/PineFlash#desktop_computer-install-options).
	
* For MacOS, currently there is a 2-step script that will build PineFlash.
* If you have issues with Pineflash, then use Blisp below.

### Option 2: Blisp Flasher
This is a CLI that runs in a terminal console. Get the latest zip file for Linux or Mac. The main page has background info and there are instructions if you want to [build it from code](https://github.com/pine64/blisp/wiki/Update-Pinecil-V2) instead of using the easier premade executable.

1. Extract the Blisp zip, and using a terminal, `cd` to the blisp folder.
2. Download the latest [stable Pinecilv2.zip release](https://github.com/Ralim/IronOS/releases/) (scroll down to the Assets section, get the Pinecilv2.zip).
3. Extract the zip file and put `Pinecilv2_EN.bin` (for English) into the Blisp folder (same place as the Blisp executable). Other languages are available, substitute the *EN.bin file for the language file desired (use the 2-digit international language code). If you have the Pinecil Zip, the rest could be deleted, only the single BIN file is needed. Select the appropriate two-letter code for your language. If you accidentally flash *.dfu file on your Pinecil, it will not boot or work - be sure to only use the BIN file.
4. Connect the V2 to the PC and enter Flash mode: hold down the [-] before plugging the cable to the back of Pinecil. See (Flash Mode section for details). If you are curious on Linux, it will connect as a serial _ttyACM_ USB ACM type device.
5. Screen on Pinecil should be black/empty before proceeding or you are not in Flash mode.
6. **Blisp must have executable permission set.**
7. `cd` to the Blisp folder and `ls -l` to check permissions of blisp.
8. Make blisp executable: `chmod +x ./blisp`
9. Then execute:

       sudo ./blisp write -c bl70x --reset Pinecilv2_EN.bin
10. After a successful update, unplug and reboot it, then hold down `[-]` for ~2 seconds to see the new version.
11. See [troubleshooting](/documentation/Pinecil/Firmware/#troubleshoot_v2_flashing) down below if it does not flash.
12. To use V2 with BLE Apps, see [here](/documentation/Pinecil/Firmware/#bluetooth_ble_apps).

## Troubleshoot V2 Flashing

1. Double check that the command is typed exactly, e.g., in Windows, the dot\slash ` .\ ` can not be skipped in Powershell.
2. For Windows, instead of PowerShell, try the **cmd.exe** (right click, run as administrator) and move into the blisp folder; [example commands to move to folders](https://www3.ntu.edu.sg/home/ehchua/programming/howto/CMD_Survival.html#zz-2.1).
3. Two different samples work when the cmd.exe is run as administrator. First move into the folder you have both blisp.exe and Pinecil_EN.bin. Then execute one of the following:

       C:\Users\yourName\Downloads\blisp1>blisp.exe write -c bl70x --reset Pinecilv2_EN.bin
       C:\Users\yourName\Downloads\blisp1> .\blisp.exe write -c bl70x --reset .\Pinecilv2_EN.bin
4. Often, updating issues are related to the USB cable, or the port on the PC does not support a connection to Pinecil, try:
   * flipping the cable over, different cables. Try both use-C to C cables and also USB-C to USB-A cables (your cable may be power-only and not able to do firmware data transfers). All working USB-C to USB-C cables can do data transfer but some USB-A cables can only do power and will not work for firmware updates because they can not do data transfers.
   * Try other ports on the PC/laptop, or a different machine. There have been issues with some laptop USB-C ports not negotiating correctly, but the flashing worked using the USB-A port. Try a different OS if you can access one, some people who had issues on Linux for example were able to flash on Windows. Note that some virtual environments might have an issue with flashing to USB ports.
   * Don’t use a hub, connect directly to a port, ports on the back of a PC may sometimes be better as they are directly connected to the motherboard.
5. Follow the Flash mode instructions and make sure the [-] button is held down BEFORE plugging in the cable to the back of the Pinecil. And don’t release for ~10 seconds.
6. If that doesn’t work try holding down the `[-]` the whole time (don’t let go of the button).
7. Blisp flashers are from Gamiee’s open source [Blisp code here](https://github.com/pine64/blisp). It is only an updater for the BL706 MCU on the Pinecil V2. It is separate from the firmware files needed which are in located in GitHub Ralim’s IronOS. The firmware contains all the menus, functions, and languages, and the flasher is the tool to push the firmware onto the MCU chip (the brain). Different MCU’s need different flasher tools.
8. If you have issues completing the update, try joining the live [Pinecil community chat](/documentation/#_community_and_support) to get tips from volunteers.
9. If there was any special work-around you had to do to get the Blisp Flasher to work, or could not get it to work at all, post an [Issue in Github Blisp](https://github.com/pine64/blisp/issues).
10. If you are running Windows in a virtual machine and the process fails, make sure you have _Microsoft Visual C++ 2015-2022_ installed.
11. All firmware releases and betas are located in the GitHub [Ralim’s IronOS here](https://github.com/Ralim/IronOS). If you would like to add enhancements/features to the IronOS (firmware that runs the Pinecil) or have an issue, please look at the GitHub documents or submit an issue ticket. It is recommended to read through all the GitHub [IronOS documents](https://ralim.github.io/IronOS/) first as they may have the answers. Screen menus and troubleshooting is documented as well on IronOS and maintained by volunteers.

## Build the Blisp Flasher from Code

1. If there is a problem with the Blisp flasher, or you have a different Linux architecture like ARM, the Blisp can be built from code.
2. See directions at [GitHub Blisp Wiki page](https://github.com/pine64/blisp/wiki/Update-Pinecil-V2#-build-blisp-flasher-from-code).
3. Blisp will only work on Pinecil V2 or devices with Bouffalo BL70x MCU chips and does not work for older Pinecil V1 that was sold before Aug. 1, 2022.

## Update V1

{{< figure src="/documentation/images/Pinecil-V1andV2.png" title="right" width="400" >}}

1. Pinecil V1 uses a *.dfu file type for firmware. The newer Pinecil V2 only uses *.bin firmware type files.
2. Pinecil V1 models were sold until July 2022 and then discontinued.
3. Boot logo art: the same flashers used to install IronOS firmware can be used to install the art. Boot logo art will not overwrite the firmware, it resides in a separate space on the chip.

{{< admonition type="important" >}}
 Do not use the DC barrel jack while updating firmware or you may destroy your PC and Pinecil.
{{< /admonition >}}

### V1 Windows or Mac

1. Follow these instructions on GitHub and download the easy GUI updater app [Pine64 Updater](https://ralim.github.io/IronOS/Flashing/Pinecil%20V1/).
2. Install the app, and follow the screen prompts which requires connecting the Pinecil to the PC.
3. Connect the Pinecil to the PC by holding down the [-] **before** plugging the cable into the back of Pinecil. Keep holding down the [-] button for about ~10 seconds even after plugging in the cable.
4. Screen on Pinecil should be black/empty before proceeding or you are not in Flash mode. Repeat the steps if needed. If that does not work, flip the cable, try a new cable, or port or different PC, then see the Troubleshooting section.
5. The app will automatically fetch the latest stable Ralim’s IronOS firmware, pick the language desired from the drop down list.
6. The app also allows browsing to a local folder to install a specific beta firmware file or a boot logo that you may have downloaded or created.
7. If multiple firmware flashing is done, the app must be closed and reopened.

### V1 Linux or Mac

1. Option 1 for Linux, the simple command line DFU-Util can be used per [IronOS instructions](https://ralim.github.io/IronOS/Flashing/Pinecil%20V1/#bleeding-edge-latest). Make sure to update to the newest DFU-Util to prevent issues that some members reported with older versions of DFU-util.
2. Option 2 works for both Linux or Mac. Download the alternative [Pineflash GUI App](https://github.com/Laar3/PineFlash) for Linux and Mac.
3. Connect the Pinecil to the PC by holding down the [-] **before** plugging the cable into the back of Pinecil. Keep holding down the [-] button for about ~10 seconds even after plugging in the cable.
4. Screen on Pinecil should be black/empty before proceeding or you are not in Flash mode. If that does not work, flip the cable, try a new cable, or port or different PC, then see the Troubleshooting section.
5. PineFlash app will automatically fetch the latest stable Ralim’s IronOS firmware, pick the language desired from the drop down list.
6. Pineflash app also allows browsing to a local folder to install a specific beta firmware file or a boot logo that you may have downloaded or created.

## General Firmware Details

* Do not use the DC barrel jack while updating firmware or you may destroy your PC and Pinecil. Pinecil is designed to only use one power port at a time and never both at the same time.
* [Get the beta and release firmware from GitHub with update instructions](https://ralim.github.io/IronOS/GettingStarted/)
* To submit a feature request, or help Ralim enhance the code, create a ticket or start a discussion at [Ralim’s IronOS](https://github.com/Ralim/IronOS/issues)
* Ben (ralimtek) supports IronOS out of love for the IronOS creative open community. He volunteers countless hours coding, debugging, and enhancing IronOS with all the feature requests submitted.
  * To give some love back, donate to IronOS; [buy Ralim a coffee/kofi](https://ko-fi.com/ralim) or [donate here](https://www.paypal.com/paypalme/RalimTek).
* One advantage of Pinecil (V1/V2) over other irons (i.e., Miniware) is you can not really brick them since Pinecil’s bootloader is in ROM. If there is a problem, just flash the firmware again or a different version. This empowers people to experiment and do forks of the main IronOS firmware without as much risk.
* Problems with IronOS firmware? - read [documents here](https://ralim.github.io/IronOS/). If the answer is not found, open a [ticket here](https://github.com/Ralim/IronOS/issues) or join the [live Pinecil community chat](/documentation/#_community_and_support).

## Boot Logo Art

{{< figure src="/documentation/images/Boot-logo-dogbone.jpg" title="Dog bone by River M." >}}

### Get Art

* Boot logo art is art that you custom make or download from IronOS Meta. It displays when you initially power on the Pinecil (boot up).
* Currently only older Pinecil V1 models which use DFU files can flash boot logo art. 
* Download and extract all the premade Boot logo art from this [pinecil.zip file here](https://github.com/Ralim/IronOS-Meta/releases).
* Note that for Pinecil V1, only the images with filename "dfu" will work, you can delete all other formats from the extracted zip.
* Sample images of [premade free art](https://github.com/Ralim/IronOS-Meta/tree/main/Bootup%20Logos#logos-preview).
* To make custom art, [follow instructions here](https://github.com/Ralim/IronOS-Meta).
* Some art is animated: the very small file size limit for boot logos prevents too many frames from being possible.

{{< figure src="/documentation/images/IronOS.gif" >}}

### Install
	
* If you have Windows or Mac, you can use this GUI [Pine64 flasher](https://github.com/pine64/pine64_updater/releases/).
* If you have Linux  or Mac, use this GUI [Pineflash](https://github.com/Spagett1/PineFlash/releases/).

{{% admonition type="info" %}}
For Pinecil V2 model, Ralim has started work on this ([reference](https://github.com/Ralim/IronOS/issues/1373#issuecomment-1414925011)). Please watch this ticket, give Ralim support and encouragement. This is all volunteer work.
{{% /admonition %}}