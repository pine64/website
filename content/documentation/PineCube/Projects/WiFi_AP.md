---
title: "WiFi AP"
draft: false
menu:
  docs:
    title:
    parent: "PineCube/Projects"
    identifier: "PineCube/Projects/WiFi_AP"
    weight: 
---

If the PineCube will have a wired Ethernet connection to the main network it is possible to use it as a WiFi access point, possibly extending your existing network to further outside. Here are some steps you can take to do this starting from an Armbian system as a starting point. Note that you may need to upgrade your kernel to 5.13.x for this to work well.

* Install bridge-utils package using apt-get
* Add the following to your /etc/network/interfaces to set up both the eth0 Ethernet interface and the br0 bridge interface (change br0 to manual if static IP is preferred)

      /etc/network/interfaces:
      auto eth0
      iface eth0 inet manual
             pre-up /sbin/ifconfig $IFACE up
             pre-down /sbin/ifconfig $IFACE down
      auto br0
      iface br0 inet dhcp
             bridge_ports eth0
             bridge_stp on
* Edit the /etc/default/hostapd uncommenting the line with 'DAEMON_CONF="/etc/hostapd.conf"'
* Edit the /etc/hostapd.conf to set the SSID, password and channel for your AP.
* Run `sudo systemctl enable hostapd.service` to enable the hostapd service on startup
* Reboot your cube with the ethernet cable connected
