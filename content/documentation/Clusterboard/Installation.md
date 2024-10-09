---
title: "Installation"
draft: false
menu:
  docs:
    title:
    parent: "Clusterboard"
    identifier: "Clusterboard/Installation"
    weight: 3
---

To install a cluster it is important to know the IP addresses of each module, so the remote login sessions do not get mixed up.

Each module may be plugged into the Clusterboard individually or consecutively, which makes it easy to assign a hostname to each module separately. It is also possible to manually edit the hostname in the OS image of each module before the first boot.

**💡 TIP**\
The board has no hotplug functionality, so make sure you only plug/unplug the modules while the power is disconnected from the clusterboard.

**💡 TIP**\
No management features are available on the switch ship, so there is no VLAN support.

## Serial console

To boot use the serial console connect the pins to UART0 on the GPIO header and connect using baud 115200

* Pin 6: GND
* Pin 7: RTX
* Pin 8: TXD

The pinouts are available in [this forum thread](https://forum.pine64.org/showthread.php?tid=8058).

**💡 TIP**\
Do not connect the GND connector until the power is on as it can provide power and prevent the board from booting.
