---
title: "Ubuntu Touch design"
draft: true # UNPUBLISHED
menu:
  docs:
    title:
    parent: "PinePhone/Further_information"
    identifier: "PinePhone/Further_information/Ubuntu_Touch_design"
    weight: 
---

## Why this page

Preamble by the author:

As I saw a lot of bad things said about the UBports operating system shipped with their Community Edition, and a lot of people were ready to give up on it, I asked UniversalSuperBox and the rest of the UBports people to help the general PinePhone community out, providing answers to some misunderstandings people have about the reasoning behind the Operating System and the choices they made to make sure it is a robust system to provide to casual users that do not yet see the option to contribute as viable.

I personally think the UBports team has made some very smart decisions to make Linux more secure in a device that is always vulnerable to physical attacks, as it is moving around in the world, as opposed to the traditional Linux machine in a protected serverroom. Linux is very robust, it just does not try to protect against all Threat Models. UBports already provides a lot of devices with their OS, so they have a lot of experience and thought put into the system already, and it would be good to leverage that for other projects as well, once they are ready to look into those. Maybe they will use a different reasoning, but it still is good to learn how the UBports community solved their issues.

Specifically I asked for an answer to the reasoning behind the formatting scheme and creation of the UBports image, which is one of the things a lot of the people seem to struggle with. There are more issues that seemingly stop users from using their OS as a open system to experiment on, but these are for great reasons as well, in my opinion. If we could understand those reasons better, all of our communities could improve.

UniversalSuperBox was willing to provide us with some answers, and as always, presented them very well, and it was very interesting to read. Thank you for that!

As I think it would be sad to leave such valuable info in the backlog of the chat, I would like to post it here as well, and try to make the most sense out of them. I hope many will add their conclusions, so we all learn. Later on, I hope we can look into other differences of the UBports system, and look into the specific solutions other operation systems found for some common problems.

## Chat log

So first, UniversalSuperBox chat log:

    UniversalSuperBox: abcde, there are 10 partitions on the device. Loader, scr, persist, boot_a, boot_b, recovery_a, recovery_b, cache, system, data.
    UniversalSuperBox: loader is the u-boot bootloader. It's not at sector 16 like on most OSes so that a full GPT table can be available at any time.
    UniversalSuperBox: scr stores the boot.scr script which allows the system to boot at all
    UniversalSuperBox: persist is a 5M-ish partition for storing things that need to persist between reboots. Right now that's exclusively the reboot-recovery file which tells the bootscript to boot to the recovery partition (later we'll probably put the selected boot slot there)
    UniversalSuperBox: boot stores the kernel, dtb, initramfs, and kernel modules. There is an A and B boot partition. This is for A/B slot booting someday.
    UniversalSuperBox: recovery stores the Jumpdrive-based recovery image which is used for updating the system and recovering when things go sideways.
    UniversalSuperBox: There is an A and B slot.
    UniversalSuperBox: https://github.com/ubports/jumpdrive
    UniversalSuperBox: cache and system are the same size. System is where the root filesystem is stored. It is mounted as / in a booted system.
    UniversalSuperBox: Cache stores update files which are applied to the system partition by recovery on an update.
    UniversalSuperBox: Cache and system are the same size so that cache can be system_a and system can be system_b someday
    UniversalSuperBox: Data stores all of the writable data on the system.

Unaddressed part:

    UniversalSuperBox: The system is set up on boot by the initramfs at https://github.com/ubports/initramfs-tools-ubuntu-touch/tree/xenial_-_edge_-_pine.
    UniversalSuperBox: Specifically, look at the halium script in the scripts folder
    UniversalSuperBox: I know it's called halium. It is not exclusively for halium.
    UniversalSuperBox: The kernel, initramfs, and such are all pulled together by the scripts inside https://gitlab.com/ubports/community-ports/pinephone
    UniversalSuperBox: As well as u-boot and the rest
    UniversalSuperBox: They are all placed into a device image (.tar.xz) which is applied by the system-image upgrader after the ubports image is applied.
    UniversalSuperBox: All of that logic is inside a script in the jumpdrive repo
    UniversalSuperBox: But you can find the other constituent parts of a single image (or a delta) at https://system-image.ubports.com/16.04/arm64/mainline/devel/pinephone/index.json
    UniversalSuperBox: The system-image client is also https://github.com/ubports/system-image
    UniversalSuperBox: And the server files are built by https://github.com/ubports/system-image-server
    UniversalSuperBox: There are several problems that make me cautious to release a stable image right now. The most important one is https://bugreports.qt.io/browse/QTBUG-85802
    UniversalSuperBox: Which causes the browser to crash for seemingly no reason and it's really annoying. There are also issues with keeping time which are unacceptable and must be fixed.
    UniversalSuperBox: There is ongoing work to enable the camera and GPS is working at least somewhat some of the time now. All in devel.

## Analysis

So we can at first learn some basics, the existence of 10 partitions on the flashable image. This explains the need for the bmaptools use, as if you need to separate things so well, normally you actually have to -time consuming- write the whole image if using dd and then resize the rest to gain usable free space, and bmaptools can write partitions where they are needed, and just mark the empty parts as free. This is why bmaptools is so much faster, and it even uses some checks to secure the image and the flashing process. Dd only provides blind block copying, no regard for tests etc. My conclusion about finding out about bmaptools was that it might be a good idea to move away drom dd wherever we can. That is a lot of info in such a short line

Then there is a list of all the partitions: "Loader, scr, persist, boot_a, boot_b, recovery_a, recovery_b, cache, system, data." Each of the names provides an indication about its function, but let’s try to make a nice list out of it here on the documentation:

### UBports Partition list

#loader
#scr
#persist
#boot_a
#boot_b
#recovery_a
#recovery_b
#cache
#system
#data

It is immediately clear that this is a well thought out system, protecting against a lot of possible mishaps. Some sound like they should clearly be usable to a lot of other distributions. But the next info clears up what each partition does, so lets try to add that to the list.

### UBports Partitions and their functions

* loader: loader is the u-boot bootloader. It’s not at sector 16 like on most operating systems so that a full GPT table can be available at any time.
* scr: scr stores the boot.scr script which allows the system to boot at all
* persist: persist is a 5M-ish partition for storing things that need to persist between reboots. Right now that’s exclusively the reboot-recovery file which tells the bootscript to boot to the recovery partition (later we’ll probably put the selected boot slot there)
* boot_a: boot stores the kernel, dtb, initramfs, and kernel modules. There is an A and B boot partition. This is for A/B slot booting someday.
* boot_b:
* recovery_a: recovery stores the Jumpdrive-based recovery image which is used for updating the system and recovering when things go sideways. There is an A and B slot. https://github.com/ubports/jumpdrive
* recovery_b:
* cache: Cache stores update files which are applied to the system partition by recovery on an update. Cache and system are the same size so that cache can be system_a and system can be system_b someday
* system: System is where the root filesystem is stored. It is mounted as / in a booted system.
* data: Data stores all of the writable data on the system.

We can see immediately that all the partitions have a distinct use case, and from their existence alone we can deduce a lot. there seems to be only one partition that is used for the user to store the data in. It is the last of them, called data, and is expanded after writing the image, to fill the rest of the available space. This is left alone during upgrades, so we can place our personal stuff in there, and backup just our that.

Also there is a lot of talk about A and B partitions. They ensure that even if things go horribly wrong, there are ways to get back in a usable state.
