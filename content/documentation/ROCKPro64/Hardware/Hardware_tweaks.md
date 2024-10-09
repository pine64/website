---
title: "Hardware tweaks"
draft: false
menu:
  docs:
    title:
    parent: "ROCKPro64/Hardware"
    identifier: "ROCKPro64/Hardware/Hardware_tweaks"
    weight: 1
---

## Enabling PCIe 2.0
{{< admonition type="warning" >}}
 The downgrade to Gen1 speed came [straight from Rockchip](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=712fa1777207), as a result of an undisclosed RK3399 hardware errata. Thus, enabling Gen2 back may cause system instability or data corruption under certain circumstances. Also, the limitations of the RK3399’s internal interconnects prevent the enabling of Gen2 speed from producing some measurable performance gains, unless using specific PCI Express hardware.
{{< /admonition >}}

By default, the RockPro64 runs the PCIe slot at gen 1 speeds because there might be stability issues with gen 2 speeds. The port can be switched back to gen 2 speeds by adding the following device tree overlay.

1. Copy and paste the device tree overlay file below into a new file (you could name it `pcie-2.0.dts`):

   ```
   // Pulled from: https://forum.armbian.com/topic/23574-howto-enable-pcie-gen2-to-get-max-speed-of-nvme-rockpi-4b/
   /dts-v1/;
   /plugin/;

   &pcie0 {
           max-link-speed = <0x03>;
   };
   ```
2. Compile the device tree into a binary file. Note that you will need `dtc` installed.

   ```
   dtc -I dts -O dtb -@ pcie-2.0.dts -o pcie-2.0.dto
   ```
3. Copy or move the device tree from the current directory into the boot partition (in this case into the `/boot/dtbs/overlay/` folder). If you haven’t yet created the `/boot/dtbs/overlay/` folder, then create it with `sudo mkdir /boot/dtbs/overlay/`

   ```
   sudo cp pcie-2.0.dto /boot/dtbs/overlay/
   ```
4. Add the device compiled tree overlay file to the list of files u-boot needs to load. If you are using ManjaroARM (or ArchLinuxARM with a `extlinux.conf` file), then add the following line to the file `/boot/extlinux/extlinux.conf`:

   ```
   FDTOVERLAYS /dtbs/overlay/pcie-2.0.dtb
   ```

If you already have an `FDTOVERLAYS` line, then add a space at the end of the current line, then add this overlay file after that.
See here for details on this process: [Device Tree Overlays on Mainline](/documentation/ROCKPro64/Software/Device_Tree_Overlays_on_Mainline)

The resulting `/boot/extlinux/extlinux.conf` file might look like below after adding this dtb file:

```
LABEL Manjaro ARM
KERNEL /Image
FDT /dtbs/rockchip/rk3399-rockpro64.dtb
FDTOVERLAYS /dtbs/overlay/pcie-2.0.dtb /dtbs/overlay/cpu-overclock.dtb
APPEND initrd=/initramfs-linux.img console=ttyS2,1500000 zfs=zroot rw rootwait audit=0 cpufreq.default_governor=schedutil
```

## Overclocking (and undervolting)

{{< admonition type="warning" >}}
 Please note that changing the maximum operating frequency or the supply voltage may cause system instability or data corruption under certain circumstances. There is even the possibility of damaging your equipment permanently.
{{< /admonition >}}

The RK3399 can be overclocked. See here for details: [Overclocking/RK3399-based devices](/documentation/General/Overclocking/#rk3399_based_devices).
By overclocking, you do risk damaging your hardware, however, it is possible to achieve small, but measurable improvements in performance with an overclock. The overclock can be applied with a device tree overlay file.

Below is an example device tree overlay for CPU overclocking on the RockPro64. It may or may not work well on your device, but some have found that these speeds are stable.
The example below bumps the little cores up to 1.608GHz from 1.416GHz and bumps the big cores up to 2.088GHz from 1.8GHz.

1. Copy and paste the device tree overlay file below into a new file (you could name it `cpu-overclock.dts`):

   ```
   // Pulled from: https://github.com/torvalds/linux/blob/master/arch/arm64/boot/dts/rockchip/rk3399-op1-opp.dtsi
   /dts-v1/;
   /plugin/;

           &cluster0_opp {
                   opp00 {
                           opp-hz = /bits/ 64 <408000000>;
                           opp-microvolt = <800000>;
                           clock-latency-ns = <40000>;
                   };
                   opp01 {
                           opp-hz = /bits/ 64 <600000000>;
                           opp-microvolt = <825000>;
                   };
                   opp02 {
                           opp-hz = /bits/ 64 <816000000>;
                           opp-microvolt = <850000>;
                   };
                   opp03 {
                           opp-hz = /bits/ 64 <1008000000>;
                           opp-microvolt = <900000>;
                   };
                   opp04 {
                           opp-hz = /bits/ 64 <1200000000>;
                           opp-microvolt = <975000>;
                   };
                   opp05 {
                           opp-hz = /bits/ 64 <1416000000>;
                           opp-microvolt = <1100000>;
                   };
                   opp06 {
                           opp-hz = /bits/ 64 <1512000000>;
                           opp-microvolt = <1150000>;
                   };
                   opp07 {
                           opp-hz = /bits/ 64 <1608000000>;
                           opp-microvolt = <1200000>;
                   };
           };
           &cluster1_opp {
                   opp00 {
                           opp-hz = /bits/ 64 <408000000>;
                           opp-microvolt = <800000>;
                           clock-latency-ns = <40000>;
                   };
                   opp01 {
                           opp-hz = /bits/ 64 <600000000>;
                           opp-microvolt = <800000>;
                   };
                   opp02 {
                           opp-hz = /bits/ 64 <816000000>;
                           opp-microvolt = <825000>;
                   };
                   opp03 {
                           opp-hz = /bits/ 64 <1008000000>;
                           opp-microvolt = <850000>;
                   };
                   opp04 {
                           opp-hz = /bits/ 64 <1200000000>;
                           opp-microvolt = <900000>;
                   };
                   opp05 {
                           opp-hz = /bits/ 64 <1416000000>;
                           opp-microvolt = <975000>;
                   };
                   opp06 {
                           opp-hz = /bits/ 64 <1608000000>;
                           opp-microvolt = <1050000>;
                   };
                   opp07 {
                           opp-hz = /bits/ 64 <1800000000>;
                           opp-microvolt = <1150000>;
                   };
                   opp08 {
                           opp-hz = /bits/ 64 <2016000000>;
                           opp-microvolt = <1250000>;
                   };
                   opp09 {
                           opp-hz = /bits/ 64 <2088000000>;
                           opp-microvolt = <1250000>;
                   };
           };
   ```
2. Compile the device tree into a binary file. Note that you will need `dtc` installed.

   ```
   dtc -I dts -O dtb -@ cpu-overclock.dts -o cpu-overclock.dto
   ```
3. Copy or move the device tree from the current directory into the boot partition (in this case into the `/boot/dtbs/overlay/` folder). If you haven’t yet created the `/boot/dtbs/overlay/` folder, then create it with `sudo mkdir /boot/dtbs/overlay/`

   ```
   sudo cp cpu-overclock.dto /boot/dtbs/overlay/
   ```
4. Add the device compiled tree overlay file to the list of files u-boot needs to load. If you are using ManjaroARM (or ArchLinuxARM with a `extlinux.conf` file), then add the following line to the file `/boot/extlinux/extlinux.conf`:

   ```
   FDTOVERLAYS /dtbs/overlay/cpu-overclock.dtb
   ```

If you already have an `FDTOVERLAYS` line, then add a space at the end of the current line, then add this overlay file after that.
See here for details on this process: [Device Tree Overlays on Mainline](/documentation/ROCKPro64/Software/Device_Tree_Overlays_on_Mainline)

The resulting `/boot/extlinux/extlinux.conf` file might look like below after adding this dtb file:

```
LABEL Manjaro ARM
KERNEL /Image
FDT /dtbs/rockchip/rk3399-rockpro64.dtb
FDTOVERLAYS /dtbs/overlay/pcie-2.0.dtb /dtbs/overlay/cpu-overclock.dtb
APPEND initrd=/initramfs-linux.img console=ttyS2,1500000 zfs=zroot rw rootwait audit=0 cpufreq.default_governor=schedutil
```

## Getting WiFi working (new WiFi module)
{{< admonition type="warning" >}}
 The information presented in this section may be obsolete because of [this commit](https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/commit/?id=d11ae98478d52548172918511f949aa92193f2c6) in the linux-firmware upstream repository  Moreover, the suggested modifications to the configuration file should be resolved in the upstream repository, to fix any identified issues, instead of suggesting local changes to be performed.
{{< /admonition >}}

Manjaro ARM and Arch Linux ARM (and probably others) provide the NVRAM file needed to initialize the Wi-Fi module in the linux-firmware package, but it is listed under the generic name `brcmfmac43455-sdio.AW-CM256SM.txt`.
You can copy this file to the new name (that the driver looks for) with the following commands:

```
cd /usr/lib/firmware/brcm/
sudo cp brcmfmac43455-sdio.AW-CM256SM.txt brcmfmac43455-sdio.txt
```

Then, reboot and WiFi should start working. Details for this method are here: https://forum.pine64.org/showthread.php?tid=16635&pid=117061#pid117061

However, on a 5GHz network with `wireless-regdb` installed and the regulatory domain set to 'US', the adapter is almost unusable. Speeds are usually 0 bits per second. Sometimes a few packets can get through every few seconds, but that is it. On a 2.4GHz network, this is not an issue. This "can" be resolved by setting the regulator domain to 'GB' or 'CN', but this isn’t a solution for you if you are in the USA, for instance. There are various other `brcmfmac43455-sdio.txt` files online that one can try. Some work better than others. Since these are text files where each line represents a property value, one can combine parts of these files to generate new firmware files for testing. One such combination yields decent results. This can be achieved by applying the patch below to the default `brcmfmac43455-sdio.AW-CM256SM.txt` file. With this firmware file, it is possible to get about 140Mbps up and down with this patch (with the regulatory domain set to 'US').

```
--- brcmfmac43455-sdio.AW-CM256SM.txt   2023-04-27 19:16:47.000000000 -0500
+++ brcmfmac43455-sdio.txt      2023-05-21 11:42:22.058517093 -0500
@@ -21,19 +21,18 @@
ltecxpadnum=0x0504
macaddr=00:90:4c:c5:12:38
manfid=0x2d0
-maxp2ga0=64
-maxp5ga0=80,82,76,77
-mcsbw202gpo=0x99355533
-mcsbw205ghpo=0x99855000
-mcsbw205glpo=0x99755000
-mcsbw205gmpo=0x9df55000
-mcsbw405ghpo=0xd9755000
-mcsbw405glpo=0xb8555000
-mcsbw405gmpo=0xed955000
-mcsbw805ghpo=0xd9555000
-mcsbw805glpo=0xc8555000
-mcsbw805gmpo=0xe9555000
-muxenab=0x10
+maxp2ga0=70
+maxp5ga0=73,74,73,73
+mcsbw202gpo=0x99333322
+mcsbw205ghpo=0x8a875444
+mcsbw205glpo=0x8a875444
+mcsbw205gmpo=0x8a875444
+mcsbw405ghpo=0xda844333
+mcsbw405glpo=0xda844333
+mcsbw405gmpo=0xdb844333
+mcsbw805ghpo=0xda555444
+mcsbw805glpo=0xdb555444
+mcsbw805gmpo=0xda555444
nocrc=1
ofdmlrbw202gpo=0x0033
pa2ga0=-112,6296,-662
```

To use this patch, copy it off into a file and use the `patch` command. However, it might be easier to apply the patch by hand. To do this, open the file `/usr/lib/firmware/brcm/brcmfmac43455-sdio.txt` (after completing the copy step above), delete the line with `maxp2ga0=64` through the line with `muxenab=0x10`.

Then add the following in its place:

```
maxp2ga0=70
maxp5ga0=73,74,73,73
mcsbw202gpo=0x99333322
mcsbw205ghpo=0x8a875444
mcsbw205glpo=0x8a875444
mcsbw205gmpo=0x8a875444
mcsbw405ghpo=0xda844333
mcsbw405glpo=0xda844333
mcsbw405gmpo=0xdb844333
mcsbw805ghpo=0xda555444
mcsbw805glpo=0xdb555444
mcsbw805gmpo=0xda555444
```

Reboot and the Wi-Fi (at least for 5GHz networks) should work well. It is not exactly clear what these fields do, so the impact this has on the Wi-Fi module or your ability to operate it legally in your country is not certain. It seems that this file is passed directly to the hardware, where it is interpreted by the Wi-Fi module itself. However, given that this file is simply a combination of other existing files for similar hardware, it might be fine to use.
The patch above only pulls in lines from the following firmware file: https://github.com/reMarkable/brcmfmac-firmware/blob/master/brcmfmac43455-sdio.txt.
This code comes with the following license - which is not replicated here because it will fill this wiki with text - see the link here for the license: https://github.com/reMarkable/brcmfmac-firmware/blob/master/LICENCE.

## Stabilizing the system (underclocking the RAM)
<dl><dt><strong>⚠️ WARNING</strong></dt><dd>

As pointed out by CrystalGamma, "normal accesses should simply work, though with higher access latency than necessary (since it uses the same number of cycles as would be necessary for a higher frequency), but I’d be slightly worried about refresh, since it also issues refresh based on number of cycles as would be used for a higher frequency, instead of actual time elapsed". In other words, "the risk is refreshes coming to late, though it’s probably within tolerance with this little of a frequency diff".

To put it simply, the suggested changes to DRAM configuration may actually cause system instability or data corruption under certain circumstances.
</dd></dl>

By default, it seems that the some RockPro64 devices are not stable. This seems to manifest as gcc segfaulting randomly. Usually, this can be "fixed" by starting the build again and hoping gcc doesn’t crash. If the build finishes or crashes at a different point, this is a good indicator that the system is not stable. The issue seems to be that the RAM is running a little too fast and some bits are getting randomly flipped. Other frequencies are possible, but the highest officially supported frequency below 800MHz is 666MHz, which is still a big step down from the default frequency of 800MHz provided by ManjaroARM. It is also possible to set arbitrary frequencies in u-boot. Frequencies that have been tested with this method are 702MHz and 752MHz. It seems that there is only a slight performance decrease at 752MHz compared to 800MHz.

By default, this PKGBUILD uses the default RAM speed of 800MHz. Uncomment the line that begins with "patch" to enable the 752MHz patch. Details are in the comments at the top of the PKGBUILD. If you would like to try out other frequencies, follow the instructions in the comments at the top of the PKGBUILD.

After building and installing, the install hook will prompt you on if you want to install the new build of U-Boot to EMMC. If you want to, press Y, otherwise, hit N and then copy and paste the printed `dd` commands and modify them to write to the correct device (change the `/dev/mmcblk` part).

After installing U-Boot and rebooting, U-Boot should print out that it set the RAM to 400MHz (initially). Then a few lines down, the RAM should be set to 752MHz.
