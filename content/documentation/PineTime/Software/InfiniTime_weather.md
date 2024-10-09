---
title: "InfiniTime weather"
draft: false
menu:
  docs:
    title:
    parent: "PineTime/Software"
    identifier: "PineTime/Software/InfiniTime_weather"
    weight: 
---

Infinitime features a weather subsystem which stores weather data on the watch in a timeline which can be queried by apps or watchfaces. It can store many different types of data (see [here](https://github.com/InfiniTimeOrg/InfiniTime/blob/main/src/components/ble/weather/WeatherData.h)) and each entry includes a timestamp and an expiry time. When entries expire they are removed from the timeline automatically.

## Sending weather data to the watch ==

Weather data must be sent to the watch via a companion app. Currently, [ITD](https://gitea.elara.ws/Elara6331/itd) and [Gadgetbridge](https://www.gadgetbridge.org)  have this functionality implemented. 

### ITD ===
ITD is the easiest option as the feature simply needs enabling in the config file with a location specified. It uses data from MET.no and provides one hour of data at a time.

### Gadgetbridge ===
Gadgetbridge is slightly more difficult to set up as it requires a separate app to fetch the weather data. Details are available on the [Gadgetbridge website](https://gadgetbridge.org/basics/features/weather/).

## Displaying weather data ==

Currently there are 2 ways to display weather data on the watch, a debug app  which is disabled by default, and the PineTimeStyle watchface. To enable it, press and hold on the watch face, tap the settings icon and enable weather.

The easiest way to enable the debug app is to change the entry for the navigation app in DisplayApp.cpp to load the weather debug app instead:

```
    case Apps::Navigation:
      //currentScreen = std::make_unique<Screens::Navigation>(this, systemTask->nimble().navigation());
      currentScreen = std::make_unique<Screens::Weather>(this, systemTask->nimble().weather());
      break;
```
