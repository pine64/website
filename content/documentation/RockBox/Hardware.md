---
title: "Hardware"
draft: false
menu:
  docs:
    title:
    parent: "RockBox"
    identifier: "RockBox/Hardware"
    weight: 3
---

## LEDs

The blue LED can be controlled with via the sysfs (_/sys/devices/platform/leds/leds/power/brightness_):

To turn off the blue LED: `echo 0 | sudo tee /sys/devices/platform/leds/leds/power/brightness`

To turn on the blue LED: `echo 1 | sudo tee /sys/devices/platform/leds/leds/power/brightness`

Note: the maximum brightness is defined as 255, it doesn’t support dimming however, so 0 and 1 as brightness is sufficient. Turning off the blue LED will turn on a weak red LED. Trigger can be changed via _/sys/devices/platform/leds/leds/power/trigger_.
