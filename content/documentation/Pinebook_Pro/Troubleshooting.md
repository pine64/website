---
title: "Troubleshooting"
draft: false
menu:
  docs:
    title:
    parent: "Pinebook_Pro"
    identifier: "Pinebook_Pro/Troubleshooting"
    weight: 5
---

## Tips, tricks and other information for troubleshooting your Pinebook Pro

If something has gone wrong, the key thing is remain calm and not do anything hasty and make things worse, particularly when flashing the eMMC or firmware. Try and make a record of all the things you did in the run-up to the problem (even to the point of using a camera to take a note of errors on the screen, this record can be vital later).

## Manjaro Updates Fail With 404

If you have an old Manjaro installation then it will have the wrong repositories/mirrors set up and they won’t work. Set up new repositories by following these instructions: https://archived.forum.manjaro.org/t/another-mirror-transition-manual-intervention-required/132302

## Power And Boot

### New from the factory - Pinebook Pro won't boot / power on

* Some Pinebook Pros came from the factory with the eMMC switch in the disabled position. It should be switched towards the back / hinge to enable the eMMC.
* The eMMC may have come loose during shipment. [Open the back](/documentation/Pinebook_Pro/Guides/Disassembly_and_Reassembly) and verify that the eMMC is firmly seated.
* You may want to try unplugging the SD card daughterboard ribbon cable and see if it powers on (remove the battery and peel off a bit of the tape before unplugging it to avoid damage). If it does, try reseating it on both sides. It might have come loose during shipping.
* It’s possible that your eMMC is empty from the factory. Simply create a bootable [SD card](/documentation/Pinebook_Pro/Software/Releases) and see if your Pinebook Pro [Getting started](/documentation/Pinebook_Pro/Troubleshooting).

### Pinebook Pro will not power on after toggling the eMMC enable/disable switch

* This may happen if you meant to toggle the UART/Headphone switch (9) towards touchpad for headphone use and instead you toggled the eMMC enable/disable switch (24).
* After reenabling eMMC by toggling switch (24) towards hinge, if Pinebook Pro does not turn on then press the RESET button (28). It is clearly marked 'reset' on the PCB board.

### Pinebook Pro will not power on after removing and replacing EMI shielding

* Closely inspect that the shielding is firmly seated in the clips on all sides. You can be seated in the clips on one axis, and have missed on an another axis.

### Pinebook Pro won't boot when using UART console cable

* If you’re using the UART console cable from the Pine Store, you may want to see if it boots after you disconnect it. Some users report that custom-made cables based on FTDI UART adapters do not cause this issue.
* Make sure your USB to serial UART device is 3.3v. Many are 5v and some even +-12v. Pinebook Pro’s only support 3.3v and may act eratically when using higher voltage. Further, higher voltage could permananetly damage the Pinebook Pro’s SoC.

### Pinebook Pro will not sleep with lid closed

A problem with the positioning of the lid magnet has been identified by several forum users in mid-2020 models of the Pinebook Pro. The magnetic field from the lid magnet operates a hall effect sensor located on the daughterboard (smallboard), which causes the Pinebook Pro to sleep when the lid is closed. If the magnet is not positioned correctly, the Pinebook Pro will not sleep when the lid is fully closed, but may sleep if the lid is open about an inch. If you experience this problem, repositioning of the magnet may be necessary.

#### Lid Magnet Repositioning Step-by-Step

Read these steps thoroughly before starting. This is a somewhat laborious process involving fragile parts!

1. Remove bottom cover.
2. Disconnect LCD and webcam ribbon cable from main board. Flip the small black strip on the connector upward and the ribbon cable can be easily removed. Do not pull the cable out without first raising the black retaining mechanism.
3. Remove the small black plastic standoffs on each hinge and set aside.
4. Remove the three screws from each hinge on the display assembly.
5. Move the hinges upward to a 90 degree angle independently from the main body. Then lift the main body to the same 90 degree angle and you should be able to separate the display assembly from the main body. Set the main body aside.
6. Remove the plastic hinge cover on the display assembly. There’s not really an easy way to do this, just work slowly and deliberately so as not to damage the sensitive cable inside. Start from either end and work your way inward. Use a small flathead screwdriver or similar tool to get started.
7. Remove the hinges from the display assembly.
8. Remove the rubber bumpers at the top corners of the display assembly to expose two screws. Remove the screws.
9. Starting at the corners, separate the bezel from the lid. The clips that hold it in place are similar to those found on the hinge cover. Again, slow deliberate work will get it done. Work from the top down. Take care not to damage the cables in the bottom.
10. With the bezel separated from the lid, feed the cable through the slot and set the bezel aside.
11. Without removing the LCD panel completely, lift and move the panel slightly to the left, taking care not to damage the cable running underneath up to the webcam. This will give you room to remove the magnet without risking damage to the panel.
12. The magnet is a silver colored bar near the bottom right side of the lid. Pry the magnet out with a small flathead or similar tool and set it aside. There is some adhesive but it’s not very strong.
13. Put the LCD panel back where it belongs. Note the foam pads on either side of the panel. The magnet is the same width as the foam pad that keeps the panel in place, and should fit perfectly in the same channel.
14. The magnet should be placed about 1 to 1.5cm lower than where it was originally. There should be no need for adhesive, as the magnet will stick to the LCD panel. For reference, the hall effect sensor that the magnet interacts with is in between the USB port and audio jack.
15. Reassemble using these steps in reverse order.

Your Pinebook Pro should now sleep properly when the lid is closed.

#### Alternative Non-Invasive Lid Magnet Repositioning Method

* This method only takes a few seconds, and doesn’t require disassembling your Pinebook Pro:
  1. Turn on your Pinebook Pro so you can easily test when the internal magnet is in the correct position.
  2. Open the lid.
  3. Take a tiny 1/8" neodymium magnet, and place it along the right edge of the front bezel (LCD side) to locate the internal positioning magnet and discover the correct polarity. There should be one spot where it has the most attraction. Mark that spot.
  4. Using a very strong neodymium magnet(s) oriented with the same polarity you discovered using the tiny magnet, carefully place it on the spot you marked, and slowly slide it down the bezel until the internal magnet is pulled into the proper position. I successfully used four 1/2" cube neodymium magnets stacked on top of each other each having 20lbs of pull force to accomplish this.
  5. The internal magnet should be placed about 1 to 1.5cm lower than where it was originally. There should be no need for adhesive, as the magnet will stick to the LCD panel. For reference, the hall effect sensor that the magnet interacts with is in between the USB port and audio jack.
  6. Remove all external magnets, and test that the internal magnet is positioned correctly by slowly closing the lid while watching the LCD screen to make sure it stays suspended when closed, and wakes up when opened.

Your Pinebook Pro should now sleep properly when the lid is closed.

## WiFi And Bluetooth

### WiFi issues

* First, check the privacy switches to make sure your WiFi is enabled. They are persistant. See [Privacy Switches](/documentation/Pinebook_Pro/Keyboard/#privacy_switches)
* Next, you may have to modify the `/etc/NetworkManager/NetworkManager.conf` as root user, and replace `managed=false` with `managed=true`. Then reboot.
* If that doesn’t work, and if `dmesg | grep brcmfmac` reports missing firmware, you will need to manually add the brcmfmac43455-sdio.* firmware files. This is due to a quiet change in the 2022 hardware revision. This [repo](https://github.com/reMarkable/brcmfmac-firmware) has been tested and confirmed to work by no112.
* For connections that drop and resume too often, it might be due to WiFi power management from earlier OS releases. Later OS releases either removed WiFi power management, or default to full power. (Power management can be turned off via command line with `iw dev wlan0 set power_save off` or `iwconfig wlan0 power off`, although it is not persistent through re-boot.)
* For connections that drop under load on the default Debian, remove `iwconfig wlan0 power off` in the file `/etc/rc.local`.
* If WiFi is un-usable or often crashes when using an alternate OS, then it might because its WiFi firmware is not appropriate for the WiFi chip in the Pinebook Pro. Try the latest firmware patch from [https://gitlab.manjaro.org/tsys/pinebook-firmware/tree/master/brcm](https://gitlab.manjaro.org/tsys/pinebook-firmware/tree/master/brcm)
* After re-enabling WiFi via the privacy switch, you have to reboot to restore function. There is a work around for the default Debian, (and may work with others);
&nbsp; &nbsp; &nbsp; &nbsp; `sudo tee /sys/bus/platform/drivers/dwmmc_rockchip/{un,}bind <<< 'fe310000.dwmmc'`
* On extremely rare occasions, the WiFi antenna connection is loose. To fix, simply open up the bottom, re-connect the WiFi antenna cable. This may show up as any of the following symptoms:
  * Can’t connect to any network, but the network manager software sees the WiFi device, (so it has not been disabled by the Privacy Switch)
  * Very limited range, meaning you can make a connection if the Pinebook Pro is next to the WiFi router. But not the next room.
  * Unreliable connections, that are also limited by range.
* Every once in a great while, the kernel will just fail to detect the wifi hardware (symptom: `ip link`` shows no wlan0). Only solution found so far is to hard-reset the machine (complete power-off then on again).

### Bluetooth issues

* When connecting a Bluetooth device, such as a Bluetooth mouse, it does not automatically re-connect on re-boot. In the Bluetooth connection GUI, there is a yellow star for re-connect on boot. Use that button to enable a persistent connection. It can be changed back later.
* Bluetooth-attached speakers or headset require the **pulseaudio-module-bluetooth** package. If not already installed, it can be installed with a package manager or using the following: `sudo apt-get install pulseaudio-module-bluetooth`
* When using Bluetooth-attached speakers or headset and 2.4Ghz WiFi at the same time, you may experience stuttering of the audio. One solution is to use 5Ghz WiFi if you can. Or you may try using a different 2.4Ghz channel, perhaps channel 1 or the top channel, (11 in the USA, or 13/14 in some other countries).

## Sound issues

* Many reports of no sound are due to the OS, incorrect settings, or other software problems (eg. PulseAudio). So first test to see if it is a software or hardware problem, by trying another OS via SD card. (For example, if Debian is installed on the eMMC, try Ubuntu on SD.)
* If you cannot get sound from the headphone jack, but can get sound from the speakers, then the headphone / UART console switch may be set to the UART mode. You can open the back and check the position of the switch. If set to UART mode, switch it to headphone mode. See the parts layout for the location and correct position of the switch.
* When using the USB C alternate DisplayPort mode, it is possible that the audio has been re-directed through this path. If your monitor has speakers, see if they work.
* See [manjaro-arm/pinebookpro-post-install /var/lib/alsa/asound.state](https://gitlab.manjaro.org/manjaro-arm/packages/community/pinebookpro-post-install/blob/master/asound.state) for some ALSA tweaks.
* See [manjaro-arm/pinebookpro-audio](https://gitlab.manjaro.org/manjaro-arm/packages/community/pinebookpro-audio) for how to handle 3.5mm jack plug/unplug events with ACPID.
* Serveral users have reported that one internal speaker had reversed polarity. Thus, sound from the speakers is like an echo effect.
  * There is a software fix using alsamixer and then enable either "R invert" or "L invert", however, now the headphones have incorrect audio.
  * The permanent fix is to re-wire one speaker, though this requires soldering small wires.
* Sound playback may be affected by the "mirroring" between the right and left channels, which results in distorted sound image. The root cause is the [ALSA mixer](https://linux.die.net/man/1/alsamixer) setting named "DAC Stereo Enhancement", which needs to be changed to 0% to fix this issue. Please see [this forum post](https://forum.pine64.org/showthread.php?tid=12631&pid=87372#pid87372) for further information.

## NVMe SSD issues

Many Pinebook Pro users have reported issues with M.2 NVMe SSD drives, including random Linux lockups and crashes. Some of these issues are related to the [RK3399’s errata](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=712fa1777207) that disables Gen2 (5&nbsp;GT/s) speed for the PCI Express link used by the NVMe SSD, reducing it down to Gen1 speed (2.5&nbsp;GT/s). However, Linux distributions that use Linux kernels older than version 5.12 still configure the PCI Express link to run at Gen2 speed, which requires [manual reconfiguration](https://forum.pine64.org/showthread.php?tid=11683) to Gen1 speed in case system instability is experienced. See also this [related discussion](https://patchwork.kernel.org/project/linux-rockchip/patch/20200423150510.6216-1-pgwipeout@gmail.com/). This issue does not affect distributions with recent (newer than May 2021) kernels such as Manjaro ARM which seem to work with no modifications.

Some Pinebook Pro users have reported issues with the default settings for the APST (Autonomous Powe State Transition) power saving, which cause an NVMe drive to disappear from the system or lock up after a certain period of time. Please see [this forum thread](https://forum.pine64.org/showthread.php?tid=11337&pid=87711#pid87711) for further information.

The output of the 3.3&nbsp;V regulator inside the Pinebook Pro, which powers the M.2 SSD, becomes very noisy when the battery voltage drops below 3.9&nbsp;V or so. This is a hardware issue of the Pinebook Pro that cannot be corrected without extensive hardware modifications, and it causes many M.2 SSDs to lock up under load and cause operating system crashes. The real trouble is that for some M.2 SSDs it takes a couple of hours of heavy I/O to lock up under these conditions, which may make them appear to be working reliably, while they eventually fail.

## Keyboard and trackpad

### Random Duplicated Key-Presses

Whether caused by an error in the Hailuck Keyboard firmware, or a physical defect in the membrane, the Pinebook Pro keyboard may randomly register some key-presses twice. The solution to this problem is trivial. Simply run the following command:

`xkbset bouncekeys 20`

If this return the following error:

`bash: xkbset: command not found`

Or some other similar error, you will need to install the command. It can most likely be found in your distro’s repository.

You may substitute some other value for 20 - this number denoting the time in milliseconds during which successive, duplicate key-presses will be rejected - with any value of your choice. If you are still receiving duplicates, consider increasing the number - perhaps by half. If you are consistently writing "aple", try decreasing this number - perhaps by 25%.

### Keys not registering / missing keys when typing

This issue occurs when your thumb or edge of the palm makes contact with left or right tip of the trackpad when you type. This is due to the palm rejection firmware being too forceful. Instead of only disabling the trackpad, so your cursor does not move all over the screen, it disables both the trackpad and the keyboard.

Using Fn+F7 to disable the touchpad will keep it from also disabling the keyboard.

A [firmware update](/documentation/Pinebook_Pro/Further_information/Datasheets/) has been released to address this.

### Key mapping

* See this [/etc/udev/hwdb.d/10-usb-kbd.hwdb](https://gitlab.manjaro.org/manjaro-arm/packages/community/pinebookpro-post-install/blob/master/10-usb-kbd.hwdb) for some key mapping tweaks

### Pinebook Pro gets stuck after first reboot in Trackpad Firmware Update

This refers to the firmware update shown here: https://github.com/dragan-simic/pinebook-pro-keyboard-updater#update-all-firmware-images

* If the system is not responding after the 1st reboot, it might be easiest to do a system restore or boot an sdcard-only OS, and follow up by running the second step of the trackpad firmware update with a USB keyboard and mouse plugged in
* System restore https://forum.pine64.org/showthread.php?tid=8229
* Firmware update https://github.com/dragan-simic/pinebook-pro-keyboard-updater#update-all-firmware-images

### ANSI Fn + F keys wrong for F9, F10, F11 and F12

There appears to be a minor firmware issue for ANSI keyboard models of the Pinebook Pro. Some discussion and fixes have been proposed;

* Discussion thread [ Fn + F keys screwy for F9, F10, F11 and F12](https://forum.pine64.org/showthread.php?tid=8744&pid=57678#pid57678)
* Proposed fix [(ANSI) Fn + F(9-12) has wrong assignment after firmware update #14](https://github.com/ayufan-rock64/pinebook-pro-keyboard-updater/issues/14#issuecomment-576825396)

## USB docks & USB C alternate mode video

The Pinebook Pro uses the RK3399 SoC (System on a Chip). It supports a video pass through mode on the USB C port using DisplayPort alternate mode. This DisplayPort output comes from the same GPU used to display the built-in LCD.

Here are some selection criteria for successfully using the USB C alternate mode for video:

* The device must use USB C alternate mode DisplayPort. Not USB C alternate mode HDMI, or other.
* The device can have a HDMI, DVI, or VGA connector, if it uses an active translater.
* If USB 3 is also desired from a USB dock, the maximum resolution, frame rate and pixel depth is reduced to half the bandwidth. For example, 4K @ 30hz instead of 60hz.
* USB docks that also use USB C alternate mode DisplayPort will always have USB 2 available, (480Mbps, half-duplex).

## Screen

Also see above about external screen using USB-C adaptor

### After changing builtin LCD resolution, blank screen

Some people find that the text or icons are too small, so they attempt to change the resolution of the built-in display. Afterwards, the display is blank.
Use the following to fix when logged into a text console as yourself, pressing Control-Alt-F1 through F6. After listing the resolutions, select the native resolution, (1920x1080 aka 1080p).

    export DISPLAY=:0.0
    xrandr -q
    xrandr -s [resolution]

Once the screen resolution is restored, try using the software settings to configure the desired screen scaling.

If the above fix did not work, you can try this:

* Using a text console, (Control-Alt-F1), login with your normal user ID
* Edit the file `nano ~/.config/monitors.xml`
* Change the "width" value to "1920"
* Change the "height" value to "1080"
* If there is more than one monitor configuration listed, edit that one too. Be careful to make no other changes. If needed, exit without saving and re-edit.
* Save the file and exit.
* Login using the GUI and test
* If you are still loggied in via the GUI, you will have to reboot using `sudo shutdown -r now`. After the reboot, you should be able to login to the GUI login and have the resolution back to normal.

After restoring the usability of your Pinebook Pro’s graphical screen, also see [this section](/documentation/Pinebook_Pro/Software/Tuning/#improving_readability) on improving readability and usability.

## Outer Shell

### Cracks in the plastic

There have been multiple reports of cracks in the plastic keyboard and trackpad part of the case. These are generally near:

* Hinges
* USB ports
* Top side, around the corners

This seems to apply to the first batches in 2019. Later versions of the keyboard and trackpad have used better plastic. With replacements now in the Pine64 Store, it’s possible to simply order a replacement.

There have been a few reports of cracks in the plastic around the LCD display, but these appear to be less common. There are replacement LCDs with top cases available in the Pine64 Store.

Be extra careful if you open the PBP, the plastic parts of the shell, around the back corners or the hinges are really tiny and break easily.
