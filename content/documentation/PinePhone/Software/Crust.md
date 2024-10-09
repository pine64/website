---
title: "Crust"
draft: false
hidden: true
menu:
  docs:
    title:
    parent: "PinePhone/Software"
    identifier: "PinePhone/Software/Crust"
    weight: 4
---

As per the README.md on [the crust github](https://github.com/crust-firmware/crust):

Crust improves battery life and thermal performance by implementing a deep sleep state. During deep sleep, the CPU cores, the DRAM controller, and most onboard peripherals are powered down, reducing power consumption by 80% or more compared to an idle device.

For this to work, Crust runs outside the main CPU and DRAM, on a dedicated always-on microprocessor called a System Control Processor (SCP). Crust is designed to run on a specific SCP implementation, Allwinner’s AR100.

To build crust manually with U-Boot you can find instructions [Here](/documentation/General/U-Boot).

## RTC wakeups

It is possible to set the device to wakeup at a specific time or after a certain number of seconds using rtcwake: `rtcwake -m mem -s 10`

This example will put the device to sleep for 10 seconds and then wake it up. More information on the rtcwake command can be found in the [man pages](https://linux.die.net/man/8/rtcwake)

## Manual suspend

For manually suspending the device on distributions with Systemd you can use the following command with super user permissions: `systemctl suspend`

On non-systemd distributions you can directly echo: `echo mem > /sys/power/state`
