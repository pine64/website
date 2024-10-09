---
title: "Safety"
draft: false
menu:
  docs:
    title:
    parent: "PinePhone/Further_information"
    identifier: "PinePhone/Further_information/Safety"
    weight: 
---

## General recommendations

Due to the greater control the user is having over the device and its software comes also greater responsibility. It is necessary to verify the configuration of the device to make sure that responsible settings are used. The different operating systems may come with non-sane default settings, including SSH with weak password authentication being enabled by default and exposed to the public Internet, the absence of a firewall, default passwords, unencrypted files, too high temperature zones and emergency shutoff values or an enabled root account. The usage of public resources to verify such settings (such as the in case of GNU/Linux, the Arch Linux [security](https://wiki.archlinux.org/title/security) wiki page, or the [general recommendations](https://wiki.archlinux.org/title/general_recommendations)) as well as the corresponding operating system’s or distribution’s resources are strongly recommended.

## Charging safety

The PinePhone supports up to 5V 3A (15W) Quick Charge, it follows the USB Power Delivery specification. Only compatible phone chargers may be used, charging the phone with incompatible chargers (for example laptop chargers with a higher voltage) is prohibited. Charging the phone releases heat, general safety recommendations must be followed, see the section _Thermal safety_.

## Thermal safety

With the Allwinner A64 being an older generation SoC with a large 40nm chip, the phone produces quite some heat with medium or higher use and especially also during charging or when using USB accessories, like a docking station. Measurements to prevent damage to the phone and to its surroundings need to be taken by the user. This includes especially a proper handling of the phone: do not charge the phone in a way where heat builds up around the phone without being able to escape. Especially don’t charge your phone under a pillow, blankets, in pockets or bags. Charging the phone produces heat and charging the phone in a way, where the excessive heat can’t dispose around the phone poses an immediate fire risk.

The user might notice that the phone gets warm under usage, compared to phones with more up-to-date hardware. Under normal circumstances these temperatures don’t pose a risk while being in the levels within the safe operating temperatures (which lay far beyond the point where components can be too hot to touch). Higher temperatures might especially be experienced on the top side of the screen and on the inside of the phone at the RF shield of the modem. The higher temperature of the RF shield of the modem is commonly caused by the SoC on the opposite side of the mainboard, the RF shield of the modem is used to disperse heat of the SoC. In newer mainboard revisions starting from 1.2a there are also thermal pads on the back cover and between the SoC’s RF shield and the screen, dispersing heat on the screen and on the back cover. In the past there has been safety issues regarding thermal safety functions, causing temperature reads to not properly work over an extended period of time, which was causing heat damage in some cases (see the documentation of that issue by the developer Megous [here](http://xnux.eu/log/#018) and [here](http://xnux.eu/log/#017)). While the developers are working hard to prevent such issues, they can’t be excluded under all circumstances. The users are expected to monitor their phones' thermal safety at every point at this state of the software.

It is highly recommend to update the phone on a regular basis to always get the latest improvements. The default settings to throttle the performance and to shut down the phone when reaching critical temperatures might be set to a too high point depending on the specific usage and usage length. Under GNU/Linux the phone’s thermal management behavior can be modified via the Thermal Sysfs driver to achieve lower temperatures and preventing the screen and other components to potentially take damage, see [Thermal tweaks](/documentation/PinePhone/Software_tricks/Thermal_tweaks) for the details.
