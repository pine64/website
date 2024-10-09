---
title: "LEDs"
draft: false
menu:
  docs:
    title:
    parent: "STAR64"
    identifier: "STAR64/LEDs"
    weight: 4
---

The LEDs can be configured to stop blinking. Under Linux this can be done using the following command (as root):
 
 echo "default-on" > /sys/devices/platform/leds/leds/blue-led/trigger
 
To list possible other triggers for the blue LED:
 
 cat /sys/devices/platform/leds/leds/blue-led/trigger 
 
An example for a trigger is _activity_, where the the blue LED reflects the CPU activity.
