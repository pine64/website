---
title: "Installation instructions"
draft: false
menu:
  docs:
    title:
    parent: "PineTab2/Software"
    identifier: "PineTab2/Software/Installation_instructions"
    weight: 1
---

The PineTab2 is capable of running different operating systems from the internal flash memory (eMMC) and from microSD card.

## Preparing the microSD card

To write an operating system to the microSD card (typically called "flashing" in the community), you need to first download a compatible image from the [Releases](/documentation/PineTab2/Software/Releases) page.

Next you need to decompress the downloaded image. The images are typically compressed in an archive format such as _xz_ to reduce the download size. If you are using a graphical tool such as _balenaEtcher_ or _Gnome Disks_ it will handle the decompression of the image in the flashing step automatically.

Further you need to flash the image to the microSD card. This can be done using various tools, for example _balenaEtcher_ (recommended for new users), _Gnome Disks_ or command-line tools such as _cp_ and _dd_. Insert the microSD card in a microSD card reader connected to your computer and then choose a tool of your liking.

Graphical applications:

* **balenaEtcher** (Microsoft Windows, macOS, Linux): Click on _Flash from file_ and select the image. Then select the microSD card target device and click on _Flash!_.
* **Gnome Disks** (Linux): Select the microSD card target device on the left side in the _Disks_ list. Then select the three dot menu on the top right and click on _Restore Disk Image..._. Select the image, verify the correct device is selected and then click on _Start Restoring..._.

Command-line tools:

* **cp**: `sudo cp **IMAGE.img** /dev/**[DEVICE]**`
* **dd**: `sudo dd if=**IMAGE.img** of=/dev/**[DEVICE]** bs=1M status=progress conv=fsync`

{{< admonition type="note" >}}
 Make sure to replace **IMAGE.img** and **[DEVICE]** with the filename of the image (double check if it is decompressed and has the file extension _.img_) and the device name. You can use the command `lsblk` to find the device name. Make sure to flash to the whole device instead of partition 1 and that you’re NOT selecting _/dev/sda1_ or _/dev/mmcblk0p1_ as target. Be very careful to select the correct device, as the tools can overwrite your data when the wrong device is selected.
{{< /admonition >}}

Then insert the microSD card into the PineTab2. 

<dl><dt><strong>📌 NOTE</strong></dt><dd>

{{< figure src="/documentation/PineTab2/images/PineTab2_USB_UARTv2.jpg" title="The UART adapter" width="450" >}}

Using the USB UART adapter can be required in some cases as explained in the info box about the boot order. The adapter is shipped with the PineTab2 in the box which is also containing the charging cable. The switch to disable the eMMC and SPI is located on the top right of the image.
</dd></dl>

<dl><dt><strong>📌 NOTE</strong></dt><dd>

**Note regarding the boot order:** The SPI and the internal memory (eMMC) have a higher boot priority than the microSD card. The pre-installed bootloader on the internal memory (eMMC) tries to boot from the microSD card first. **In some cases** it can be required to bypass the bootloader, for example if the bootloader is corrupted or was overwritten by a bootloader with varying settings.

To force the device to boot from the microSD card, the eMMC and the SPI can be disabled by using the debug UART adapter shipped with the device in the box also containing the charging cable. Set the _SD BOOT MASKROM_ switch on the adapter to the position _ON_ and plug it into the USB/PD charging port. Then power on the tablet and **unplug the debug board or set the switch to the position _OFF_ again** when the factory image is started, otherwise the factory image won’t find the eMMC.
</dd></dl>

Power on the device with the microSD card inserted (and optionally with the USB UART adapter inserted and the bypass switch set to _ON_ depending on the software situation, see the info box above). It should now boot the new operating system from the microSD card.

**Something is not working?** Please join the PineTab channel in the community chat, the community is always happy to help. In the page [UART adapter](/documentation/PineTab2/Development/UART_adapter) you can find information about how to connect the USB UART adapter and how to retrieve the boot logs if the device is not booting properly even after the above procudere.
