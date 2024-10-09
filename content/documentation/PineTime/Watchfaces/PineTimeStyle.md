---
title: "PineTimeStyle"
draft: false
menu:
  docs:
    title:
    parent: "PineTime/Watchfaces"
    identifier: "PineTime/Watchfaces/PineTimeStyle"
    weight: 
---

PineTimeStyle is a watchface created for Infinitime and has been included since version 1.3 of Infinitime.

It is based on [TimeStyle for Pebble by Dan Tilden](https://www.dantilden.com/projects/timestyle/) with permission.

{{< figure src="/documentation/PineTime/images/InfiniSim_Watchface.png" title="PineTimeStyle Watchface" >}}

## Layout

The time is displayed on the left in either 12 or 24h format depending on the system setting. An indicator will appear in the bottom left corner if 12h is selected.

In the sidebar on the right there is a battery icon which displays the current charge level, and is replaced by a plug icon when charging. Below it is a bluetooth icon which appears only when bluetooth is connected, and a lower case **i** which indicates unread notifications are available, generally only if notifications are disabled via the quick settings screen.

The current date is displayed in the middle, and at the bottom there is a small gauge which displays the step count, the needle will rotate in a clockwise direction as the step count increases. The gauge scales automatically based on the configured step goal, and the outside of the gauge will turn white when the step goal is reached.

## Customisation

Since version 1.4 of Infinitime, a color picker is available for PineTimeStyle. As of version 1.11, an addition page of customisation has been added which allows the user to customise the sidebar. These settings can be accessed by long pressing on the watchface which will display two buttons, one with a palette icon to access the color settings, one with a cog icon for the sidebar options.

{{< figure src="/documentation/PineTime/images/InfiniSim_Settings.png" title="PineTimeStyle Settings Button" >}}

### The color picker

{{< figure src="/documentation/PineTime/images/InfiniSim_Color.png" title="PineTimeStyle Color Settings Interface" >}}

There are 3 pairs of buttons with left and right arrows which scroll through 17 standard colors. The top pair changes the time text color, middle for the sidebar color and bottom for the time background color.

There is also a 'Rnd' button which randomises all colors, a 'Rst' button which resets the colors to standard teal and black, and a cross which closes the settings interface. It can also be closed using the physical button.

### The sidebar settings

{{< figure src="/documentation/PineTime/images/InfiniSim_SidebarSettings.png" title="PineTimeStyle Sidebar Settings" >}}

As of Infinitime version 1.13, there are 2 options available in the sidebar settings page - Steps style and Weather.

By pressing the 'Steps style' button you can toggle between 3 options, the original full gauge, a half size gauge plus seconds display, or a numerical step count display. The second button, Weather, enables or disables this function. When no weather data is available a ban icon will be displayed with 2 dashes below, and when weather data is available the current temperature plus an icon showing conditions based on the cloud cover and precipitation amount.

To learn more about the sending weather data to the watch, see [InfiniTime weather](/documentation/PineTime/Software/InfiniTime_weather)
