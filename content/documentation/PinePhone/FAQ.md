---
title: "FAQ"
draft: false
menu:
  docs:
    title:
    parent: "PinePhone"
    identifier: "PinePhone/FAQ"
    weight:
aliases:
  - /PinePhone_FAQ
---

A list of frequently asked question.

## Hardware

### Revisions

#### What are Community Editions?
Community Editions of the PinePhone were versions of the PinePhone which came preinstalled with the operating system of a partner project and featured the logo of the project on the back panel. The Community Edition was intended to help partner projects developing these systems: "Community editions are meant to bring exposure to partner-projects operating systems and communities, as well as help finance ongoing development.", [source](https://www.pine64.org/2020/04/02/pinephone-ubports-community-edition-pre-orders-now-open/).

#### Is the Community Edition hardware the latest revision?

The Community Edition program (featuring the mainboard numbers 1.2 through 1.2b and branded back covers) which provided the branded PinePhones has since ended, and a Beta Edition has since been released. The only difference between each Community Edition is the inclusion of crucial bug fixes, with the last issue being fixed with the 1.2b motherboard shipping with the Manjaro CE PinePhones. The 1.2b motherboard is also currently used in the Beta Edition PinePhones, however the Beta Edition units do not ship with any back cover branding. There are currently no plans for further hardware revisions.

Aside from the back cover, the only other difference between each Community Edition is that starting with the postmarketOS PinePhone, a convergence package option was released that adds another gigabyte of ram to the phone and a 32GB eMMC instead of a 16GB eMMC. Convergence packages also included a dock for plugging in USB peripherals and connecting to an HDMI monitor, however you can purchase a generic USB-C dock to use with a 2GB PinePhone.

The predecessor to the Convergence Edition PinePhones was the Braveheart Edition intended for developers to bring up the platform, which had the version number 1.1. For more details about the topic see [PinePhone](/documentation/PinePhone/Revisions).

#### Will there be other Community Editions?

Five Community Editions have been announced: [UBports](https://www.pine64.org/2020/04/02/pinephone-ubports-community-edition-pre-orders-now-open/), [postmarketOS](https://www.pine64.org/2020/06/15/june-update-postmarketos-ce-pinephone-shipping-pine64-cluster/), [Manjaro](https://www.pine64.org/2020/08/31/pinephone-manjaro-community-edition/), [KDE](https://www.pine64.org/2020/12/01/kde-community-edition-is-now-available/), and [Mobian](https://www.pine64.org/2021/01/17/mobian-community-edition/). Since the release of the Mobian edition, the Beta Edition PinePhones have been released and the Community Edition Program has ended.

#### In simple terms, what are the differences between Braveheart and the new Community Edition?

The Braveheart PinePhone was the first public revision of the PinePhone which was intended solely for developers and Linux enthusiasts. The UBports Community Edition was the next revision of the PinePhone with an updated mainboard based on feedback from the Braveheart Edition, see [PinePhone](/documentation/PinePhone/Revisions). All current revisions of the PinePhone continue to be intended for developers and enthusiasts, however, PINE64 will be starting to offer partnered retail units of the PinePhone which will have a better warranty and technical support (keep in mind even then it is not intended for a broader audience at this time, as the software still needs work and the hardware does not hold up well to modern consumer standards).

#### Will there be a newer revision after the Community Editions?

Starting with the UBports Community Edition the PinePhone has gotten CE and FCC certifications, repeating the certification process due to changes in the hardware design is very expensive, so the 1.2b motherboard is viewed as the final revision. The PinePhone (and parts for them) will be produced and sold for at least 5 years.

#### Will there be hardware differences between the Community Editions?

Besides the varied back covers, starting with the launch of the PostmarketOS CE there has been the release of a convergence package option for the PinePhone which includes more ram and storage, and an included dock for convenience. There has also been minor hardware changes with the UBports CE (mainboard 1.2) and the Manjaro CE (mainboard revision 1.2b).

### General

#### How powerful is the PinePhone's hardware?

The PinePhone is about on par with a Raspberry Pi 3 in terms of CPU performance, however it’s Mali 400 MP2 is much weaker than the Pi 3’s VideoCore IV. The Mali 400 was the first mobile OpenGL ES 2.0 GPU on the market back in 2008 when it was released, compared to the much newer Videocore IV released in 2010. The PinePhone has been shown to handle smooth H.264 1440p30 video playback using Cedrus and gstreamer as documented [here](https://xnux.eu/log/#toc-2020-09-17-video-acceleration-experiments-with-pinephone). The device should be more than capable of a smooth phone experience when used in conjunction with well optimized software that makes use of its hardware features. It is also capable of running many light games (including 3D ones such as SuperTuxKart), and retro gaming. Expect further speed improvements over time as the drivers are improved, and in the meanwhile you can look into slightly [Overclocking](/documentation/General/Overclocking) the device (at your own risk).

### Sound

The default ringtone for Mobian Phosh can be found at /usr/share/sounds/freedesktop/stereo/phone-incoming-call.oga

### Bluetooth

For some reason, using pipewire-pulse with bluetooth headphones (In my case, Sony WH1000X-M3) using the default LDAC codec causes the headphones to constantly connect and disconnect until they eventually give up pairing. A work around I’ve found is to quickly go into Sound settings and switch the codec to "SBC".

### Modem

#### The modem isn't working

In order to use the modem and Wi-Fi/Bluetooth, you need to ensure the battery is inside the device and has a sufficient charge. Even when supplying the phone with enough power, the modem and Wi-Fi chip will not work without a connected battery. Further, double check that you have not put the SD card into the sim card slot, or vice versa.

#### Does the PinePhone only wake up from sleep for calls and texts?

Yes. Unless the PinePhone is configured to wake up every few minutes from deep sleep in Crust (At the cost of battery life. However, in the future there may be other solutions), then there is not any way to get any notifications for applications. The modem on the PinePhone will wake the device for incoming calls and texts however, and the real-time clock is also capable of waking the device for alarms.

### Battery

#### The battery is stuck inside the phone

The battery can be stuck in the phone if the screws of the frame are overtightened.

First, try loosening the screws to the left and right of the battery compartment and remove the battery, it should go much easier now. These screws may be the culprit as they seem to make the sides of the midframe grip the battery. Do not tighten them fully and the problem should go away.

If your battery is still stuck inside the PinePhone, completely unscrew all the screws of the midframe. Then pull out the battery (you may have to fully take off the midframe in some cases to get it out). And then rescrew the midframe, but only tighten the screws to the point where they are just barely tight to hold. This should allow you to remove the battery easily.

#### The battery is discharging while the phone is powered off (Braveheart Edition)

The issue is not present on the Community Edition. Due to a hardware bug, after power off, the phone still consumes 20–30mA which drains the battery in 3-4 days. A manual procedure to fix the hardware bug is described [here](https://xnux.eu/devices/pp-pmic-fix.jpg).

#### The battery only charges to ~84%

Some pre-made operating systems using megi’s kernel limit the maximum amount of charge to roughly ~84% in the hope of prolonging the battery life, as repeatedly reaching the upper level of battery charge reduces the battery’s lifetime (this is **not** a safety feature!). The same effect however also applies when repeatedly draining the battery to a low level - users are therefore advised to consider if that setting is reasonable depending on their usage. The setting can be overwritten via Sysfs, to let the battery fully charge (this can lower the replaceable battery’s lifetime considerably depending on the charging behavior!):

{{< admonition type="warning" >}}
 The following instructions are directed towards expert-level users and developers!
{{< /admonition >}}

`echo 4350000 > /sys/class/power_supply/axp20x-battery/voltage_max_design`

### Privacy Switches

#### What are the privacy switches doing?

|     |     |     |     |
| --- | --- | --- | --- |
| Number | Name | Explanation | Description |
| 1 | Modem | Pulls Q1501 gate up (FET disabling modem power) | "On" enables cellular communication and GNSS hardware, "off" disables it. |
| 2 | Wi-Fi / Bluetooth | Pulls up CHIP_EN | "On" enables Wi-Fi and Bluetooth communication hardware, "off" disables it. |
| 3 | Microphone | Breaks microphone bias voltage from the SoC | "On" enables audio input from on-board microphones (not 3.5mm jack), "off" disables it. |
| 4 | Rear camera | Pulls up PWDN on OV5640 | "On" enables the rear camera, "off" disables it. |
| 5 | Front camera | Pulls up PWDN on GC2145 | "On" enables the front camera, "off" disables it. |
| 6 | Headphone | Pulls up IN2 on analog switch BCT4717ETB | "On" enables audio input and output via the 3.5mm audio jack, "off" switches the jack to hardware UART mode. |

### Memory

#### What's the speed difference between the eMMC and SD cards?

Maximum transfer speed of the eMMC is around 85 MB/s, while SD cards are limited to approximately 23 MB/s (even with faster cards).

### GPS

#### GPS doesn't work

Like almost all smartphones, the PinePhone GPS antenna is small and can only get a first fix unassisted if the GPS signal is very strong. To make first fix faster and more reliable, phones download assistance data either from the phone network or from the internet. The GPS in the PinePhone modem supports the internet based assistance method, as detailed in the modem documentation, but this is currently only supported by a few distributions, and a [proof of concept script](https://gist.github.com/alastair-dm/263209b54d01209be28828e555fa6628) that shows it can work.

Until aGPS support becomes standard you’ll have to make some manual changes - see for example [Mobian wiki](https://wiki.mobian.org/doku.php?id=location)

#### GPS can't determine direction

Currently, due to the magnetometer not being hooked up in software at this time, it is not possible for GPS software to use the phone’s compass functionality. This means while you are walking it will not be possible to determine the direction of travel. This is not as much of an issue for vehicles as the faster speeds mean that it is possible to estimate the direction of travel, however it will still be an issue should the vehicle travel through a tunnel and lose GPS signal.

## Software

### Installation

#### How can I install an operating system on the SD card / eMMC?

See [Installation instructions](/documentation/PinePhone/Installation_instructions).

### Booting

#### What's the boot order for SD cards and eMMC?

The PinePhone will automatically boot from microSD if a bootable card is inserted. If no (bootable) microSD is found, it will boot from eMMC.

#### How can I select different operating systems at boot?

There was a project by Danct12 which allowed the user to select different operating systems at boot, but the repository has since been archived: https://github.com/dreemurrs-embedded/Pineloader.

#### I turned on my Manjaro CE PinePhone. The red LED and screen backlight are briefly lit, then both are not and it will not boot.

This can be the result of at least one situation:

1. The eMMC installation became corrupt or otherwise unbootable
2. An SD card is present but not bootable (consider [PinePhone Troubleshooting](/documentation/PinePhone/Troubleshooting))

If there is an installation of Manjaro on both the eMMC & an SD card, the SD card will always boot first on the device. Try taking the SD card out and booting the installation that is on the eMMC. If the problem persists, it is likely there is an issue with both installations and you will need to reinstall your distribution. You may also want to check with your distribution’s maintainers if boot issues are a common problem in a recent update.

#### I did not install an update in Ubuntu Touch and I'm stuck on the PINE64 logo after rebooting.

1. Use a USB A-C cable to plug your phone into your PC
2. Hold the PinePhone’s power button for 4 seconds or more to power it off.
3. Wait 5 seconds
4. Hold the Volume Up and Power buttons on the PinePhone to boot into recovery. You should see the LED light red, then yellow, then green. The "Installing update" screen will appear, but a progress bar to indicate update progress will not. Ignore the "Installing update" part.
5. Your PC may automatically mount the PinePhone’s partitions. If it does, Safely Remove or Eject all of them.
6. Open a terminal on your PC. Type `telnet 172.16.42.1`
7. You should receive the text 'Welcome to Rescue SD Shell|'
8. In the new Rescue SD shell, type `umount /dev/mmcblk2p10; e2fsck -fy /dev/mmcblk2p10 && sync`
9. Once this command pipeline finishes, type `sync && reboot -f`

Your PinePhone should reboot into Ubuntu Touch. Now head to Settings - Updates and install the new update!

If these steps did not solve your issue, please create a new thread here on the PINE64 forums, note what the problem looks like, then say that you’ve tried these steps already.

This is caused by corruption on the userdata partition. Normally this should be fixed by 'e2fsck' in the initramfs, however, an error in image creation means that that version of e2fsck is unable to correct the corruption. This has been fixed in all new PinePhone updates, so if you update from the factory image to any other image available to the PinePhone now, you will not experience this issue any longer.

#### The PinePhone does not boot

Most operating systems on the PinePhone do not boot if the battery is not connected or if it is fully drained. If you received a new PinePhone make sure to remove the battery isolator as explained under [PinePhone Getting started](/documentation/PinePhone/Getting_started).

If you removed the battery isolator and the battery contacts are intact, the battery is either fully drained or there is no valid OS (or a corrupted OS or bootloader) installed on the eMMC or the SD card. Make sure to charge the phone with a compatible charger (500 mAh is not enough for modern phones), as well as the installation instruction under [Installation instructions](/documentation/PinePhone/Installation_instructions). If the OS got corrupted it is highly recommend to simply reflash.

If nothing works please don’t hesitate to contact the community, they are eager to help and booting issues are usually very easy to solve (as they are typically either battery or installation related). The phones itself are all tested individually at the factory. Do not contact PINE64’s support for booting issues.

{{< figure src="/documentation/images/Pinephone_warning.png" caption="A protection foil isolates the battery for the shipping." >}}
{{< figure src="/documentation/images/Pinephone_backside.png" caption="The microSD belongs in the upper slot, the micro SIM in the lower slot." >}}

#### Can I install a different OS on my Community Edition?

Yes. While all the Community Edition PinePhones come with an OS preinstalled, you are free to use any OS on the integrated storage (the eMMC) or an SD card, see [Installation instructions](/documentation/PinePhone/Installation_instructions) and [Operating systems](/documentation/PinePhone/Software/Releases) on how to install them.

### Other

#### How can I enable SSH?

In Ubuntu Touch you can run "sudo start ssh" to get a one-time start, or edit /etc/init/ssh.override and remove the manual line to make it auto-start.

In other distributions you may have to install SSH through its package manager and then proceed to use its init system to enable it. For Manjaro, Arch, and Mobian you can use "systemctl enable sshd" and "systemctl start sshd" command to enable and start the ssh daemon.

#### What works, what doesn't?

For Ubuntu Touch see https://gitlab.com/ubports/community-ports/pinephone#what-works-what-doesnt.

Other distributions will have different levels of functionality. Please refer to the release page of your chosen distribution for further information.

#### I can't connect to a 2.4Ghz Wi-Fi network in Ubuntu Touch.

Reboot your device by holding the power button until the "Power" dialog appears, then pressing "Restart".

If that does not fix the issue, note that all the following conditions must be met to use Wi-Fi on the PinePhone:

1. The plastic tab between the battery and the device’s battery contacts has been removed
2. The battery is installed
3. The Wi-Fi privacy switch (switch number two) on the rear of the device is switched "ON"

Wi-Fi in the PinePhone only seems stable after a warm reboot like this.

#### What's the status of Android for the PinePhone?

Currently, there isn’t any major push to get Android running well on the PinePhone. The developer Icenowy did get a partially working Android image, but it was slow and buggy, lacking some major functions. As of now, use Anbox as an alternative for your android apps, which is currently not included in Ubuntu Touch. In other distributions your millage may vary on what applications will run and how well.

#### Why are my apps loading slower than on my Android phone?

Android has multiple techniques in place to speed up launching applications after the first launch, such as the "Dalvik cache".

Using an alternative filesystem such as F2FS on the eMMC (which is considerably faster than running software on the SD card) may help improve performance slightly. Over time you can expect further optimizations and improvements in various distributions that will help speed up the PinePhone.

#### How can I turn on the backlight?

On some devices the default calibration of the backlight is not sufficient and the minimum setting of the brightness of the used OS can be too low, causing the backlight to completely shut down. In that case it is recommended to connect the phone to a charger and/or to shine a flashlight at the screen to adjust the brightness to a higher setting again.

On many Linux distributions the brightness setting is an integer between 0 and 1000 and available at runtime in /sys/class/backlight/backlight/brightness and stored at shutdown and loaded at boot from /var/lib/systemd/backlight/platform-backlight:backlight:backlight by systemd-backlight@backlight:backlight.service. Changing the brightness setting can be done at runtime, for example over SSH, by executing as root `echo 500 > /sys/class/backlight/backlight/brightness`. The stored brightness setting can be modified using another system, by mounting the root filesystem of the system you want to fix and by executing `echo 500 > [MOUNT LOCATION]/var/lib/systemd/backlight/platform-backlight\:backlight\:backlight`.

#### How can I contribute regarding the WiFi and Bluetooth firmware?

The PinePhone uses [Realtek RTL8723CS](https://files.pine64.org/doc/datasheet/pine64/RTL8723BS.pdf) for its Wi-Fi and Bluetooth connectivity. Unfortunately, just like the other Realtek wireless chipsets _([see more info](https://en.wikipedia.org/wiki/Comparison_of_open-source_wireless_drivers))_ - the RTL8723CS chipset requires proprietary firmware for Wi-Fi and Bluetooth functionality. For those who want to create replacement free software firmware, resources like [this](https://libreplanet.org/wiki/Group:Hardware/research/e-readers/Kobo/Aura_H2O_Edition_2#Firmwares) and [this](https://8051enthusiast.github.io/2021/07/05/002-wifi_fun.html) (different chipsets, but still Realtek) could be a great starting point for further research.

### SMS

#### The phone does not receive SMS

Sometimes incoming SMS messages are not being received, but outgoing ones, phone calls and data are working fine. One cause of this is if ModemManager fails to receive messages from the modem and they build up. These messages are not cleared by either rebooting reflashing the phone.

New versions of the [(mostly) foss community firmware](https://github.com/the-modem-distro/pinephone_modem_sdk) implement a workaround that helps ModemManager receive stuck messages.

Most UIs (at least phosh, plasma, and sxmo) use ModemManager to communicate with the modem including for phone calls, cellular data, GPS and SMS.

You can check for stuck sms messages using the mmcli command:

`$ mmcli -m any --messaging-list-sms
Found 10 SMS messages:
/org/freedesktop/ModemManager1/SMS/0 (received)`

Any messages that are listed have gotten stuck, they can be deleted like this:

`$ mmcli -m any --messaging-delete-sms=77` (Repeat with all listed messages)

For more information on the messaging related actions available in mmcli you can check the help with `mmcli --help-messaging.` This article is also helpful in learning: https://electronproton.com/mmcli-command-examples/.

## Shipping

### I did not receive an order confirmation
Check your "spam" folder. It was reported that some users did not receive an order confirmation. You will also still get a shipping notification when the device ships out, even if you didn’t get an order confirmation email.

### When does the phone ship?

For up-to-date information when the phone’s shipping date is estimated, see the edits in the corresponding forum thread.

### It is shipping day but I did not receive a shipping notification

For shipments with DHL the shipping notification is sent out as soon as the packet reached DHL’s warehouse and scanned (it can take up to 24 hours after scanning after the shipment is added to DHL’s database). For all other shipments (via Ascendia) the notification is sent out sometime after shipment.

### When does my phone ship if I order now?

Orders made after Friday, 22nd May 2020 are shipped after the first bulk of pre-orders has been shipped. The exact date is not known yet due to various reasons, it may be a few weeks after the first bulk shipped. [The forum](https://forum.pine64.org/showthread.php?tid=9942) will be edited with updated information and you will receive a shipping notification when the device was shipped.

### What about import taxes?

Import taxes have to be paid by the buyer depending on the jurisdiction of the country of the buyer. Please check with your local laws if there are import taxes to pay and if so how to do the tax filing.

## Accessories

### Protection

#### Which screen protector should I use?

Protecting your screen is important, especially for devices like the PinePhone that doesn’t have access to the newest glass technology.
The Braveheart and Community Editions of the PinePhone comes with a plastic film screen protector installed, and PINE64 sells a tempered glass screen protector [in their store](https://pine64.com/product/pinephone-tempered-glass-screen-protector/).

You can also buy a third-party screen protector, as the screen protectors for the iPhone 11 Pro Max/XS Max fit the PinePhone pretty well based on [this](https://forum.pine64.org/showthread.php?tid=8458&pid=65409#pid65409) forum post.

### Batteries

#### I want a replacement battery, which one should I buy?

Replacement batteries for US customers are available in the store.

Currently the PinePhone battery is known to be compatible with replacement batteries for the Samsung J700. Specifically, models "EB-BJ700BBC" and "EB-BJ700BBE" are compatible with all PinePhone models, and "EB-BJ700CBE" is compatible with Community Editions [after UBPorts](https://www.reddit.com/r/PINE64official/comments/kcof97/pinephone_replacement_battery_found_and_tested/gfrx4p2/?utm_source=reddit&utm_medium=web2x&context=3) (due to plastic tabs on its bottom which only the newer phones [have tolerance for](https://forum.pine64.org/showthread.php?tid=11901)).

### External hardware

#### Will PINE64 sell other add-ons made for the PinePhone?

Yes, currently there is a keyboard case [with similarities to the Psion 5](https://forum.pine64.org/showthread.php?tid=8537&pid=55396#pid55396) which includes an internal battery, and a [Qi wireless charging](https://www.pine64.org/2020/05/15/may-update-pinetab-pre-orders-pinephone-qi-charging-more/) add-on planned, both of which PINE64 intends to directly sell. There is the potential for future add-ons such as a game pad, however that is currently just an idea and not in any way planned.
