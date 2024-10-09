---
title: "SPI"
draft: false
menu:
  docs:
    title:
    parent: "Pinebook_Pro/Features"
    identifier: "Pinebook_Pro/Features/SPI"
    weight: 
---

The Pinebook Pro comes equipped with two non-volatile storage components, the eMMC and the SPI. The capacity of the SPI is 128Mbit (16MiB) and it may be used in the boot process.

Boot data can be written to the SPI via two methods: either from within PBP or from a second machine connected to the PBP by USB.

## Writing to SPI from within PBP

Forum user [pcm720](https://forum.pine64.org/member.php?action=profile&uid=15527) provided an example of writing to the SPI from within Linux in [their self-published version of U-Boot](https://github.com/pcm720/u-boot-build-scripts/releases) that offers boot functionality for NVMe drives. It involves use of `flash_erase` command (available in the mtd-utils package on Arch/Manjaro) and the `dd` command.

However, `flashcp` command should be used instead of `dd`, to make sure all specifics of the underlying flash memory are covered.

## Writing to SPI from a second machine

Writing to the SPI from a second machine is more complicated than the other method, but it is the only option when troubleshooting an SPI flash gone wrong. This method works by bringing the RK3399 SoC into `maskrom mode` and issuing commands on the second machine that download the flash image onto the Pinebook Pro.

Upon entering `maskrom mode`, the power LED on your Pinebook Pro won’t light up and neither will the display. Instead, your second machine, the one connected to your Pinebook Pro via USB, will indicate `maskrom mode` by logging to `journalctl`.

There are two ways to reach `maskrom mode`, but the first tends to be less reliable.

### Maskrom mode (unreliable method)

{{< admonition type="note" >}}
 The recovery button relies entirely on the software support in the boot loader, which makes it unreliable.
{{< /admonition >}}

According to Rockchip documentation, these steps should work; unfortunately, many users have reported them to be unsuccessful. You may need to repeat these steps several times for them to work.

1. Press and hold recovery button.
2. Short press reset.
3. Release recovery button after about three seconds.

In case this approach fails, please see the section below for a more reliable method.

### Maskrom mode (reliable method)

{{< admonition type="warning" >}}
 ***When removing the large RF shield found on the mainboard, to be able to short the pins on the SPI chip, make absolutely sure to align it correctly while putting it back.***  Failing to do so can result in shorting the battery to the ground, due to the close proximity of the solder pads for the bypass cables, which would prevent the normal operation and effectively cause a fire hazard.  It is highly recommended to disconnect the battery before removing the RF shield, and before putting it back.
{{< /admonition >}}

1. Build and install `rkdeveloptool` (see [project repository](https://github.com/rockchip-linux/rkdeveloptool) for instructions)
2. Verify successful installation. Running `rkdeveloptool --version` should output: `rkdeveloptool ver 1.3`
3. Run `journalctl -f` and keep it running. Once the Pinebook Pro is connected and maskrom mode is reached it will produce additional output.
4. Power off the Pinebook Pro.
5. Unscrew the bottom cover.
6. Remove the metal RF shield surrounding the main CPU. The shield is held in place small clamps on the board. The clamps can be released with a pry tool and some force. [This forum post with photos](https://forum.pine64.org/showthread.php?tid=11073&pid=75096#pid75096) shows how it can be done.
7. Disconnect all boot devices, i.e. eMMC, microSD card and USB.
8. Locate SPI flash (component number 29 on [this photo of the Pinebook Pro internals](https://wiki.pine64.org/images/4/45/PBPL_S.jpg)).
9. Connect your Pinebook Pro with USB-C to USB-A cable to second machine (Pinebook Pro on the USB-C side)
10. Short pins CLK and VSS (see chip diagram to the right for the names of pins). This can be done with a pair of tweezers when short on tools. {{< figure src="/documentation/images/Spi.png" title="right" >}}
11. Power on the Pinebook Pro.
12. Press the reset button (component number 28).
13. Check if there is new output from `journalctl` program.
14. Check if the Pinebook Pro is connected by running `rkdeveloptool ld`. If successful, the output should be like: `DevNo=1 Vid=0x2207,Pid=0x330c,LocationID=1401 Maskrom`

### After entering maskrom mode

Now that when the RK3399 SoC is in `maskrom mode`, you can use `rkdeveloptool` to write data to the SPI. To do so you’ll need the binary file you’ll be writing to SPI, which will be referred to as `SPI_new.bin`, and a helper file named [rk3399_loader_spinor_v1.15.114.bin](https://dl.radxa.com/rockpi4/images/loader/spi/rk3399_loader_spinor_v1.15.114.bin).

1. Flash the flash helper db file: `rkdeveloptool db rk3399_loader_spinor_v1.15.114.bin`. If successful, the output should read `Downloading bootloader succeeded`.
2. Flash the new SPI binary: `rkdeveloptool wl 0 SPI_new.bin`. If successful, the output should read: `Write LBA from file (100%)`.
3. Test the installation: `rkdeveloptool td`. If successful, output should read `Reset Device OK`.
4. Run `rkdeveloptool rd` to reboot your Pinebook Pro.

#### Zeroing out the SPI

In case, you wrote something bad to your SPI, it’s helpful to wipe away that data with zeros. To do that, you follow the same steps above to enter `maskrom mode` and then write a binary file that consists of all zeros.

1. Create the binary file `dd if=/dev/zero of=zero.bin bs=1M count=16`
2. Flash the flash helper db file: `rkdeveloptool db rk3399_loader_spinor_v1.15.114.bin`. If successful, the output should read `Downloading bootloader succeeded`.
3. Flash the new SPI binary: `rkdeveloptool wl 0 zero.bin`. If successful, the output should read: `Write LBA from file (100%)`.
4. Test the installation: `rkdeveloptool td`. If successful, output should read `Reset Device OK`.
5. Run `rkdeveloptool rd` to reboot your Pinebook Pro.
