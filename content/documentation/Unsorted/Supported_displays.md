---
title: "Supported Displays"
draft: false
menu:
  docs:
    title:
    parent: "Unsorted"
    identifier: "Unsorted/Supported_displays"
    weight:
aliases:
  - /wiki/Supported_Displays
  - /wiki/MIPI-DSI_Displays
---

{{< admonition type="important" >}}
 Contribute to it by looking for MIPI-DSI panels in `drivers/gpu/drm/panel/` and filling out the table from their data sheets
{{< /admonition >}}

## MIPI-DSI Displays

**MIPI-DSI Displays** are displays that follow the MIPI-DSI standard. Such displays can be connected to various PINE64 Single Board Computers.

### MIPI Channels and Lanes

The MIPI Lanes number is given in a format of `channels`&times;`lanes`. Before buying one, make sure that your SBC has enough channels and lanes to drive the display!

* **ROCKPro64:** 2&times;4
* **Quartz64 Model A:** 1&times;4
* **Quartz64 Model B:** 1&times;2
* **SOQuartz:** 1&times;4 + 1&times;2

### Displays With Mainline Drivers

These displays have free and open-source drivers in the main Linux kernel tree.

|     |
| --- |
| Manufacturer |
| Part Number |
| Size |
| Resolution |
| Panel Technology |
| MIPI Lanes |
| Feiyang |
| ***FY07024DI26A30-D*** |
| 7.0" |
| data-sort-value="614400" |
| 1024&times;600 |
| TN? |
| data-sort-value="4" |
| 1&times;4 |
| Sharp |
| ***LQ101R1SX01*** |
| 10.1" |
| data-sort-value="4096000" |
| 2560&times;1600 |
| TN? |
| data-sort-value="8" |
| 2&times;4 |
| Sharp |
| ***LS060T1SX01*** |
| 6.0" |
| data-sort-value="2073600" |
| 1080&times;1920 |
| ? |
| data-sort-value="4" |
| 1&times;4 |

## LVDS Displays

**LVDS Displays** are displays that follow the LVDS standard.

### LVDS Hardware Support

Only Quartz64 Model A seems to support LVDS panels.

### Displays and Timings

TBD
