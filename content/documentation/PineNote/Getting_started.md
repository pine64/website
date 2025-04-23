---
title: "Getting Started"
draft: false
menu:
  docs:
    title:
    parent: "PineNote"
    identifier: "PineNote/Getting_started"
    weight: 2
aliases:
  - /wiki/PineNote:_Getting_Started
---

## Important note for buyers after October 2024
{{< admonition type="note" >}}

Dear new PineNote users, you may have noticed that suspend/resume is not working on your new PineNote! You may also noticed that using rkdeveloptool is not possible because you cannot trigger maskrom mode using the magnet method.

These issues are caused by differences in testing procedures of the shipped Debian-based image, and factory flashing procedures. Namely, the factory used a Windows-based flashing system, and it turned out that this system does overwrite crucial parts of the u-boot bootloader with same only-partially working data. The effect is that the PineNote will boot, but not suspend.

### Fixing the issue

Fortunately the PineNote ships with a complete set of bootloader files and fixing the issue is a matter of a few shell commands:, which are flashing a working U-Boot to get MASKROM with magnet working on PineNote:

1. Login via UART-adapter or ssh, or use the Gnome-Terminal (found in the quick slots of the dashboard - switch to BW+Dithering mode for faster screen responses):
    * username: `user`
    * password: `1234`

2. Gain root access by executing `sudo su - root` (the password is: `1234`).

3. Execute the following (two) commands (as root):

```console
cd /root/uboot

bash install_stable_1056mhz_uboot.sh
```

4. Turn off the PineNote by executing `init 0`

5. Done. The pinenote should now have a proper U-Boot installed, with rkdeveloptool-support and suspend.

---

The output of step 3 should read:

```console
root@pinenote:~/uboot# bash install_stable_1056mhz_uboot.sh
568+0 records in
568+0 records out
290816 bytes (291 kB, 284 KiB) copied, 0.00419942 s, 69.3 MB/s
8192+0 records in
8192+0 records out
4194304 bytes (4.2 MB, 4.0 MiB) copied, 0.447542 s, 9.4 MB/s
If not errors were reported, then the 1056 MHz u-boot/ram-blob was installed
Please reboot
root@pinenote:~/uboot# init 0
```
{{< /admonition >}}

## What's inside the PineNote package

Included in the box are:

* **PineNote**
* **Stylus**
* **USB-C to USB-A cable**
* (only pre 2024 PineNotes) **USB-C to Micro-USB cable** - specifically for the stylus
* **UART Dongle** - for [UART](/documentation/PineNote/Development/UART/) connectivity
* **Foldable cover**

## Installing the foldable cover

The foldable cover can be applied to the PineNote in these simple steps:

**Step 1:** Remove the protective plastic from the adhesive strip.

![Step 1: Remove the protective plastic from the adhesive strip](/documentation/PineNote/images/step1.png)

**Step 2:** The black adhesive strip should now be exposed.

![Step 2: The black adhesive strip should now be exposed](/documentation/PineNote/images/step2.png)

**Step 3:** Carefully place the PineNote on top of the side with the adhesive strip, ensuring that the corners and edges are properly aligned with the device.

![Step 3: Align the PineNote and then place it on top of the stip.](/documentation/PineNote/images/step3.png)
