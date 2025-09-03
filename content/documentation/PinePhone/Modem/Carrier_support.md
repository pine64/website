---
title: "Carrier support"
draft: false
menu:
  docs:
    title:
    parent: "PinePhone/Modem"
    identifier: "PinePhone/Modem/Carrier_support"
    weight:
aliases:
  - /wiki/PinePhone_Carrier_Support
---

{{% docs/construction %}}

This page contains hints on setting up cellular network connectivity for specific carriers.
For more general information, see the carrier support section of [PinePhone](/documentation/PinePhone/Modem). For the APN settings see [APN settings](/documentation/PinePhone/Modem/APN_settings).

## Check compatibility

To check if the PinePhone is supported on your carrier:

Search for your carrier on [frequencycheck.com](https://www.frequencycheck.com/) and compare the carrier’s LTE/GSM/WCDMA frequencies to the PinePhone’s supported frequencies (listed in the https://wiki.pine64.org/wiki/File:Quectel_EG25-G_LTE_Standard_Specification_V1.3.pdf modem specification sheet).

It is likely that there will be a few frequencies that your carrier uses which are not supported by the PinePhone. Not all of the carrier’s frequencies need to be supported by the PinePhone for it to work - as long as _most_ of them are supported, you will still get good coverage.

{{< admonition type="note" >}}
 Some providers may allow only certain known devices identified by their [Type Allocation Code](https://en.wikipedia.org/wiki/Type_Allocation_Code).
{{</ admonition >}}

## MMS workarounds

These scripts allow partial MMS support on a [PinePhone](/documentation/PinePhone) in distributions without working MMS support:

* JMMS: https://git.sr.ht/~amindfv/jmms
* silvermms: https://gitlab.com/5ilver/silvermms
* MMS via Matrix with mmmpuppet: [MMS with Matrix](/documentation/PinePhone/Software_tricks/MMS_with_Matrix)

There is a Haskel MMS client. MMS can also be manually composed with mmsd on the command line.
