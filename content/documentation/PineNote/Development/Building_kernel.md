---
title: "Building Kernel"
draft: false
menu:
  docs:
    title:
    parent: "PineNote/Development"
    identifier: "PineNote/Development/Building_kernel"
    weight: 1
---

This page contains information on how to build a linux kernel for the PineNote.

## Available Kernel Repositories

The following (incomplete?) PineNote-specific kernel repositories are available:

* https://github.com/m-weigand/linux/ (based mainly on the repository from smaeul, with additional patches pulled in from other sources, Debian packages available)
* https://gitlab.com/pgwipeout/linux-next/
* https://github.com/smaeul/linux/tree/rk35/pinenote-next

## Building the kernel

{{< admonition type="note" >}}
 These following instructions need to be cleaned up and updated, and OS-specific information and tweaks should be moved elsewhere
{{< /admonition >}}

After following [Dorian’s directions](https://github.com/DorianRudolph/pinenotes#starter-guide) to get Arch installed you’ve seen someone [playing DOOM](https://github.com/m-weigand/mw_pinenote_misc/blob/main/videos/20220808_bw_dither_mode_picture_doom_video_small.mp4)  and you want to learn how to get the features that enable that kind of performance. To get your PN running this smoothly, we’ll need to build our own kernel. There are two kernel efforts underway right now:

1. pgwipeout: https://gitlab.com/pgwipeout/linux-next
2. smaeul: https://github.com/smaeul/linux/tree/rk35/pinenote-next

We’ll be using smaeul’s kernel + some additional patches provided by DorianRudolph, pgwipeout, Maximilian Weigand, occam_razor, and hrdl. Thanks so much to them, and all the other users who have worked on piecing together drivers, twiddling configs, answering questions, and sharing their work in other ways. Brava!

Perhaps the main component of the kernel is the DRM driver. You can read more about the driver by reading [Smaeul’s RFC](https://lore.kernel.org/linux-rockchip/20220413221916.50995-1-samuel@sholland.org/T/).

### A small warning

This guide is completely based off of the scripts provided by Maximilian. We’ll be cloning and running them, but he owns them and he -- or others -- might change them. It’s smart to have a look at what’s going on, check when this page was last updated vs when his scripts were last updated, etc. Be nimble!

Additionally, as Maximilian warns [here](https://github.com/m-weigand/mw_pinenote_misc/tree/main/rockchip_ebc/patches), these changes are all experimental and may damage your panel.

{{< admonition type="note" >}}
 If anyone reading this has recommended reading for how we can understand what may damage our panels (IE is the risk in fast updates? The types of updates? something more complicated?), please add it here!
{{< /admonition >}}

### What you should have already done

It is assumed you’ve already got an operating system installed on your Pinenote other than the stock Android. Doing this isn’t trivial, but it is well understood - you will be following the footsteps of many others. Dorian Rudolph made a guide for doing this, available [here](https://github.com/DorianRudolph/pinenotes#starter-guide).

### Steps to build

1. Clone Maximilian’s scripts:

   ```console
   $ git clone https://github.com/m-weigand/mw_pinenote_misc.git
   ```
2. Make a separate directory for patching the kernel. Then run Maximilian’s _clone_and_prepare_git.sh_. This will clone smaeul’s kernel and a number of patches. Read the script to see which patches it is using. Feel free to open the patches too -- it’s helpful to get a slim idea of what’s going on, if only looking at the commit messages in them:

   ```console
   $ cd ../
   $ sh mw_pinenote_misc/custom_kernel/clone_and_prepare_git.sh
   ```
3. Compile the kernel:

   ```console
   $ sh ./mw_pinenote_misc/custom_kernel/compile.sh
   ```
4. Next we want to perform the work captured in **install_to_pn.sh**, but the work may vary slightly from person to person. As long as you put them somewhere and configure your **extlinux.conf** to point at it, things will be okay. Looking at **install_to_pn.sh**, we can see that there are three pieces to installing the kernel: the kernel image (called _Image_), the device tree (_rk3566-pinenote-v1.2.dtb_), and the modules. All of these files have been compiled and placed into the **linux/pack** folder. The easiest way to send these over is by using _scp_ or _rsync_ - read the script and decide how you would like to get your files in the correct location. You may need to install _rsync_ on your PineNote if it doesn’t already have it.
5. DTB was installed like this: `$ scp rk3566-pinenote-v1.2.dtb root@pinenote:/boot/dtbs/rockchip/`
6. After installing the DTB as above, the file **/boot/extlinux/extlinux.conf** may be updated to point to this new file
7. (Perhaps not necessary?) The last step is to generate a new initrd image (see [Wikipedia](https://en.wikipedia.org/wiki/Initial_ramdisk) for an explanation about initial ramdisk). This is done on the PineNote itself. Send Maximilian’s installation script over and run it. Then place the generated image (from the last step of the shell script) into your boot partition and update **extlinux.conf** if needed to point at this new file.

   ```console
   $ scp initrd/gen_uboot_image.sh root@pinenote:/root # Do this part on local to put script on PN
   $ ssh root@pinenote # Or use UART, the dongle + picocom, and change to root
   $ cd /root
   $ ./gen_uboot_image.sh
   $ mv initrd.img /boot/initrd.img
   $ vim /boot/extlinux/extlinux.conf # Update this to reference this new initrd image
   ```
8. At this point your kernel is in place!However, there are a few more steps you may need to complete to ensure the display and networking continue to work:
   * For display, you may need to change **/lib/firmware/waveform.bin** to **/lib/firmware/rockchip/ebc.wbf** (TODO: is this a difference between PG and smaeul’s kernel or a patch?)
   * For networking, you may need to change **/lib/firmware/pinenote.bin** to **/lib/firmware/pinenote-v1.2.bin**
9. This part technically isn’t kernel specific, but we need to install a patched version of Mesa. If you are running an Arch based system, you’re in luck!occam_razor provides prebuilt patched packages (say that 5 times fast) [here](https://github.com/0cc4m/pinenote-misc/releases). Simply extract these files, send them to PN, and install them using the package manager. You can also patch it yourself by looking at Maximilian’s [compile_mesa.sh](https://github.com/m-weigand/mw_pinenote_misc/blob/main/compile_mesa.sh).

{{< admonition type="note" >}}
 If you frequently update your system with _pacman -Syu_, you will end up updating these packages and losing the patches. Add this line to your `/etc/pacman.conf` to prevent them from being updated: `IgnorePkg = libva-mesa-driver mesa mesa-debug mesa-vdpau opencl-mesa vulkan-mesa-layers vulkan-broadcom vulkan-panfrost vulkan-radeon vulkan-swrast`
{{< /admonition >}}

1. To ensure the GPU stays on, we need to use Maximilian’s [mweigand_eglinfo.service](https://github.com/m-weigand/mw_pinenote_misc/blob/main/systemd/mweigand_eglinfo.service). The _Readme.md_ in that same directory has instructions for how to install this, but basically we need to copy it to **/etc/systemd/system/**, run `sudo systemctl daemon-reload` to make sure systemd knows it exists, then execute `sudo systemctl enable mweigand_eglinfo.service`.

## Next steps

### Configuring the driver
The driver has several options that can improve performance. These can be read about [here](https://github.com/m-weigand/mw_pinenote_misc/tree/main/rockchip_ebc/patches#new-features-as-of-2022august08). `rockchip_ebc.bw_mode=1 rockchip_ebc.default_waveform=1 rockchip_ebc.refresh_threshold=30 rockchip_ebc.auto_refresh=1` may be used to make the image lower quality, but much faster to update. The auto_refresh setting is also essential to clear ghosting which will otherwise accrue on screen. The _APPEND_ line in the **extlinux.conf** might be added to make sure they are applied on boot.

### Fixing suspend

If you’re using a logind system, edit your **/etc/systemd/logind.conf** config. More information on what to do [in Arch’s documentation](https://wiki.archlinux.org/title/Power_management#ACPI_event).

### Configuring your apps

See [Apps](/documentation/PineNote/Development/Apps).

### Booting Linux instead of Android

[PineNote Development/Booting Linux](/documentation/PineNote/Development/Booting_Linux)

### Fixing Bluetooth

See [PineNote Development/Software Tweaks](/documentation/PineNote/Development/Software_tweaks)
