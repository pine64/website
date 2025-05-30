---
title: "Overclocking"
draft: false
menu:
  docs:
    title:
    parent: "General"
    identifier: "General/Overclocking"
    weight:
aliases:
  - /wiki/Overclocking
---

{{< admonition type="warning" >}}
 There is the possibility of damaging your equipment by overclocking. Do so at your own risk!
{{< /admonition >}}

{{< admonition type="note" >}}
This page is incomplete, you’re welcome to improve it.
{{< /admonition >}}

{{< admonition type="note" >}}
All information regarding clock speeds, voltages and more are stored in the DTB (Device Tree Blob). You can learn more about it [here](https://elinux.org/Device_Tree_Reference).
{{< /admonition >}}

Overclocking is a way to get more performance out of the system by running it at higher clock speeds than the factory default, usually while putting out more heat and using more power (You can also downclock to possibly reduce power consumption and thermals at the cost of performance). It is highly recommended that you avoid overvolting the device, as that has a high risk of damaging the hardware, hence the warning at the beginning of this page. However, just some slight overclocks without the added voltage can not only improve performance, but not carry as much risk (Still: Do at your own risk!). It should be noted however that overclocking can cause instability, so you will need to test and see what values work best with your device (There is a silicon lottery for the PinePhone’s hardware).

## A64-based devices

{{< admonition type="important" >}}
 These instructions are targeting the PinePhone to simplify the explanation, however they can be used to also overclock other devices such as the Pinetab if you modify the proper DTB files.
{{< /admonition >}}

### Editing the PinePhone DTS

In order to overclock the PinePhone you will have to first convert the DTB file in `/boot/dtbs/allwinner/` to a DTS file. You will see `sun50i-a64-pinephone-1.2.dtb`, and also two other files with different PinePhone mainboard revisions (1.1 and 1.0). You will want to select the correct file for your PinePhone (Only choose 1.1 if you have a Braveheart, As all other consumer PinePhones use the 1.2 DTS).

Once you’ve found the file, you can run the following command to convert the DTB to DTS:

    dtc -I dtb -O dts /boot/dtbs/allwinner/sun50i-a64-pinephone-1.2.dtb -o /boot/dtbs/allwinner/sun50i-a64-pinephone-1.2.dts

Finally, modify the newly converted .dts file and change the clockspeeds you wish to modify. You can simply use a text editor to do so.

To convert back to DTB:

    dtc -I dts -O dtb /boot/dtbs/allwinner/sun50i-a64-pinephone-1.2.dts -o /boot/dtbs/allwinner/sun50i-a64-pinephone-1.2.dtb

Afterwards you can simply reboot and check with `sudo cat /sys/kernel/debug/clk/clk_summary` to see if the changes have correctly applied.

{{< admonition type="important" >}}
 In the future it is possible that someone may make a driver to adjust clockspeeds of the A64 from userspace (using a config file) without the need to recompile. However, currently the only way to overclock is to either compile your own kernel, or modify just the DTB (instructions above).
{{< /admonition >}}

### GPU

Open `/boot/dtbs/allwinner/sun50i-a64-pinephone-1.2.dts` (You will have to find the source of the kernel used by your distribution. There is the Pine64 kernel, and Megi’s) in a text editor following the PinePhone overclocking instructions.

Look for `mali: gpu@1c4000 {` and within that block search for `assigned-clock-rates = <432000000>;`

The `assigned-clock-rates` line should be set to `432000000`, this means that the GPU is clocked at 432MHz by default. So if you want 500MHz, set the value to `500000000`.

Save the DTS file, and recompile the DTB. In order to check if the overclock was successfully applied you can run: `sudo cat /sys/kernel/debug/clk/clk_summary`.

{{< admonition type="important" >}}
 The file may be slightly different and you may need to enter the values as hexadecimals
{{< /admonition >}}

{{< admonition type="note" >}}
The GPU appears to run stable overclocked to 540 Mhz, however more testing with a wider group of devices is needed.
{{< /admonition >}}

{{< admonition type="note" >}}
Remember to run a benchmark tool (such as glmark2-es2) to help check stability.
{{< /admonition >}}

### CPU

The stock speed of the A64 is 1.152 GHz. The A64 can be overclocked significantly, it is highly advisable not to do this unless you can also drop the voltage at the same time.

If the CPU is undervolted and overclocked at the same time, it is possible to reach similar thermals and power consumption to the stock configuration but with better performance.

Power consumption at different voltages and frequencies:

| Configuration | Frequency | Voltage | Power (Screen 50%) |
| --- | --- | --- | --- |
| Stock | 1.152GHz | 1.30v | ~4.35w | 
| Stock + Undervolt | 1.152GHz | 1.18v | ~3.65w | 
| Overclock + Undervolt | 1.344Ghz | 1.28v | ~4.60w |

The table above contains measurements created in postmarketOS (SWMO/SXMO - postmarketOS 21.12 SP1) with the screen on (set to 50% brightness) under a threaded load.

AXP803 PMIC voltage steps on DCDC2:

| Voltage range | Step size |
| --- | --- |
| 0.50V-1.20V | 10mV |
| 1.22V-1.30V | 20mV |

The table above shows the valid voltages provided by the AXP803 PMIC on DCDC2 (used to power the cores). For example, setting the voltage to 0.60V is valid, but setting it to 1.23V is not. When overclocking, ensure that you only use valid voltages at each operation point (otherwise it will simply be dropped and ignored). You can use (after installing) cpupower to display all valid frequencies after boot.

{{< admonition type="important" >}}
 The user _somefoo_ was able to undervolt the PinePhone at each frequency operation point by at least -100mv. The A64 set to 1.152Ghz runs at 1.18v instead of the standard 1.3v, dropping the power usage by ~0.7w under full single threaded load|The silicon lottery will dictate how well you can undervolt.
{{< /admonition >}}

{{< admonition type="note" >}}
The exact voltages and frequencies that you can achieve will depend on your device. Make sure to run stress tests (such as _stress-ng_) to ensure stability.
{{< /admonition >}}

### DRAM

{{< admonition type="warning" >}}
 It is not recommended to exceed 667 MHz clockspeed on the DRAM. 648MHz is likely the upper limit.
{{< /admonition >}}

{{< admonition type="note" >}}
Make sure to set your DRAM to a multiple of 24.
{{< /admonition >}}

{{< admonition type="note" >}}
The current frequency your DRAM is running at can be found using this command: `cat /proc/device-tree/memory/ram_freq`
{{< /admonition >}}

When overclocking the GPU, it is a good idea to also overclock the DRAM, as the main bottleneck of the A64 SOC is the memory. The A64’s maximum ram clockspeed falls just short of 667MHz. This may be unstable on your device however.

Around 600 MHz (PC-1200) should work fine, however some people have reported instability at lower clockspeeds. Arch Linux Arm uses a default clockspeed of 552MHz, with U-Boot builds available to easily switch out for a higher (624) or lower (492) DRAM clockspeed.

It is possible that by reverse engineering the DRAM driver from Allwinner that auto tuning can be accomplished to get the best performance.

Setting the DRAM clock is accomplished by modifying pinephone_defconfig in U-Boot (https://gitlab.com/pine64-org/u-boot/-/blob/crust/configs/pinephone_defconfig)

You can find simple instructions on doing so here: [U-Boot](/documentation/General/U-Boot)

### VPU

In order to allocate more VRAM for the GPU you can add `cma=256` to your kernel (or use kconfig with CONFIG_CMA_SIZE_MBYTES=256) cmdline in boot.scr which you will have to compile using mkimage. By default the kernel allocates only 64MB, and the maximum value is 256MB.

In order to compile boot.scr you can run `mkimage -C none -A arm64 -T script -d boot.cmd boot.scr`

{{< admonition type="important" >}}
 You may not have a boot.cmd file in your boot directory and instead you may instead have a boot.txt
{{< /admonition >}}

### Cedrus

Overclocking cedrus is achieved by modifying the kernel source code: https://elixir.bootlin.com/linux/latest/source/drivers/staging/media/sunxi/cedrus/cedrus.c#L507

{{< admonition type="important" >}}
 User _33yn2_ is not particularly sure if this makes any difference, or if it might in fact have a negative impact. Probably not worth messing with.
{{< /admonition >}}

## RK3399-based devices

The RK3399 clocks are found in [arch/arm64/boot/dts/rockchip/rk3399-opp.dtsi](https://github.com/torvalds/linux/blob/master/arch/arm64/boot/dts/rockchip/rk3399-opp.dtsi)

More optimised voltages and clocks can be found in [arch/arm64/boot/dts/rockchip/rk3399-op1-opp.dtsi](https://github.com/torvalds/linux/blob/master/arch/arm64/boot/dts/rockchip/rk3399-op1-opp.dtsi)
These include a slight overclock and undervolt, they are intended for the OP1 CPU found in many Chromebooks but have worked fine in all recorded cases on regular RK3399 SoCs in other devices.

### GPU

Any clock speeds can be added for the GPU in `gpu_opp_table`

The highest recommended voltage for the GPU is 1.2V as specified in the RK3399 schematic from Rockchip.

Segfault has found that the RK3399 in his Pinebook Pro can reach 950MHz on the GPU while being stable.

The stock speed for the GPU is 800Mhz.

Note that the GPU in the RK3399 is already bottlenecked by the memory bandwidth available to it, so overclocking generally yields no improvements.

### CPU

A set of available clock speeds that can be added to the CPU clusters can be found in `drivers/clk/rockchip/clk-rk3399.c` under `rk3399_cpuclkl_rates` for the little cores and `rk3399_cpuclkb_rates` for the big cores.

These clock speeds can be added to `cluster0_opp` for the small cores and `cluster1_opp` for the big cores respectively.

The maximum limit is 1.8GHz on the little cores and 2.2GHz on the big cores.

The highest recommended voltage for the little cores is 1.2V and for the big cores is 1.25V.

Segfault has found that the RK3399 in his Pinebook Pro can reach 1.7GHz on the little cores and 2.08GHz on the big ones.

The stock speed for the little cores is 1.4GHz and on the big cores it is 1.8GHz, the OP1 speeds default to 1.5GHz and 2.0GHz instead.

## ROCK64

DTB is in `/boot/dtbs/rockchip/rk3328-rock64.dtb`. CPU clock rates are inside `opp_table0` as hexadecimal numbers in the `opp-hz` field.

Check the achieved clock speed with `sudo cat /sys/kernel/debug/clk/clk_summary | grep armclk`.

Thanks to [Ayufan](https://github.com/ayufan-rock64)'s work (with their [overclocking recipe](https://github.com/ayufan-rock64/linux-build/blob/master/recipes/overclocking.md)), we know we can add a <strong>1.392GHz</strong> operating point, and a <strong>1.512GHz</strong> operating point (you should ensure you have a large heatsink for this last one). You can do so by adding the following in the `opp_table0` object, after the `opp-1296000000` operating point:

    opp-1392000000 {
            opp-hz = <0x00 0x52f83c00>;
            opp-microvolt = <0x149970>;
            clock-latency-ns = <0x9c40>;
    };

    opp-1512000000 {
            opp-hz = <0x00 0x5a1f4a00>;
            opp-microvolt = <0x162010>;
            clock-latency-ns = <0x9c40>;
    };

GPU needs investigating, but current mainline device tree does not try to clock up the GPU at all.
