---
title: "LEDs"
draft: false
menu:
  docs:
    title:
    parent: "Pinebook_Pro/Features"
    identifier: "Pinebook_Pro/Features/LEDs"
    weight: 
---

In total, there are four LEDs on the Pinebook Pro, three of which are placed in the top-left side of the keyboard, and one near the barrel port:

1. The red LED next to the barrel port indicates charging, in three ways. First, it will illuminate steadily when either the barrel jack power supply or a USB Type-C charger is connected to the Pinebook Pro, and the charging is active (that means power is supplied to the battery and system in parallel, and if it’s not enough the battery can still be discharging). Second, if the battery is at 100&nbsp;%, the LED will remain turned off regardless of the connected power input (however, this is not possible for more than a split-second when the system is running). Third, this LED will flash at 0.5&nbsp;Hz if there are any problems that prevent charging, such as the battery becoming too hot. To fully understand all the nuances, read the [Power and charging](/documentation/Pinebook_Pro/Power_and_charging) article.
2. The power indicator LED, above the keyboard, supports three different colors: green, amber and red. It is also capable of flashing to indicate eMMC activity, with proper software support. In the default Debian with MATE build, green LED means power and red means suspend (amber is unused).
3. The green NumLock LED, above the keyboard.
4. The green CapsLock LED, above the keyboard.

The NumLock and CapsLock LEDs serve their usual purposes on a keyboard, but they also have a secondary function. When the privacy switches get activated they blink to confirm that the switch has been activated.
