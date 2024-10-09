---
title: "How-Tos"
draft: false
menu:
  docs:
    title:
    parent: "Quartz64"
    identifier: "Quartz64/How-Tos"
    weight: 6
---

## Connect Debug UART

The easiest way to get debug output is to connect a 3.3V 1.5mbaud capable UART adapter to the board.

To connect it, connect the ground lead to pin 6, and the RX/TX leads to pins 8 and 10 (consider swapping them if you get no output, things are often mislabeled). These pins are "UART2" in the above GPIO table.

Open a serial terminal at 1500000 bauds, e.g.

```console
$ picocom -b 1500000 /dev/ttyUSB0
```

## Disable Heartbeat LED (Linux)

The flashing LED is called the "heartbeat LED", it blinks in a heart rhythm like fashion once the kernel is running. To disable it, you can run

    # echo none > /sys/class/leds/user-led/trigger

On model A LED device is called "diy-led", not "user-led".

On a system with systemd, you can do this as soon as the system is ready to be logged in with a systemd unit like this:

    [Unit]
    Description=Turn off heartbeat LED
    Wants=multi-user.target
    After=multi-user.target

    [Install]
    WantedBy=multi-user.target

    [Service]
    Type=simple
    ExecStart=sh -c 'echo none > /sys/class/leds/user-led/trigger'

Place it in _/etc/systemd/system/user-led.service_, and run

    # systemctl daemon-reload
    # systemctl enable user-led.service

Upon rebooting, you will now notice that the heartbeat LED will blink during boot-up, but stops blinking as soon as the multi-user target is reached (i.e. the user can log in).

## SATA on model A

On model A USB 3.0 and SATA ports are using the same I/O line and can’t be used simultaneously. By default USB 3.0 is enabled in Linux device tree and SATA is disabled. FDT modifications are required to turn SATA on.

Following script is tested on Manjaro but should work on the other distributions with minimal changes. Device tree compiler package usually provides fdtput command (on Manjaro run: `pacman -S dtc`)

    # cp /boot/dtbs/rockchip/rk3566-quartz64-a.dtb /boot/dtbs/rockchip/rk3566-quartz64-a-sata.dtb
    # fdtput -t s -v /boot/dtbs/rockchip/rk3566-quartz64-a-sata.dtb /usb@fd000000 status disabled
    # fdtput -t s -v /boot/dtbs/rockchip/rk3566-quartz64-a-sata.dtb /sata@fc400000 status okay
    # sed -i 's#^FDT /dtbs/rockchip/rk3566-quartz64-a.dtb$#FDT /dtbs/rockchip/rk3566-quartz64-a-sata.dtb#' /boot/extlinux/extlinux.conf
    # systemctl reboot

## Using a PCF8574 on Model A

See [Model A: Using a PCF8574](/documentation/Quartz64/How-Tos/Using_a_PCF8574).

## Using a battery on Model A

See [Model A: Using a battery](/documentation/Quartz64/How-Tos/Using_a_battery).

## Connecting a MIPI-DSI display

See [Connecting a MIPI-DSI display](/documentation/Quartz64/How-Tos/Connecting_a_MIPI-DSI_display).
