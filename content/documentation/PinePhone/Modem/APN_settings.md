---
title: "APN settings"
draft: false
menu:
  docs:
    title:
    parent: "PinePhone/Modem"
    identifier: "PinePhone/Modem/APN_settings"
    weight: 
---

The [APN](https://en.wikipedia.org/wiki/Access_Point_Name) setting is the gateway between your carrier’s cellular network and the **public Internet**. The APN setting - if not set automatically by the user’s OS - has to be set by the user to enable the use of the mobile Internet on the phone.

## Setting the APN

The location of the APN setting depend on the user interface the distribution is using.

### Gnome

One of the biggest actively maintained open (Creative Commons Public Domain) database of mobile broadband service providers and their APN settings is maintained by the Gnome project, and is available in their [serviceproviders.xml](https://gitlab.gnome.org/GNOME/mobile-broadband-provider-info/-/blob/main/serviceproviders.xml). It is a rare case, when you don’t find your own provider in that list, but if it happens, then please consider contributing to it upstream. If your provider is in that database, then for setting up the APN, you only have to select your provider from the list under ` Settings > Network > Network Dropdown > Add new connection`.

Further details are [described by the Gnome help](https://help.gnome.org/users/gnome-help/stable/net-mobile.html.en).

### Phosh

The APN settings are either located under `Settings > Mobile > Access Point Names` or `Settings > Network > Network Dropdown > Add new connection`.

### Plasma Mobile

The APN settings are located under `Settings > Cellular Networks > SIM 0 > Modify APNs`. While this is an auto-detect button, some cell providers may be detected incorrectly. Additionally, the settings for MMS are located under `Spacebar > Settings > Multimedia Messages (MMS)`.
