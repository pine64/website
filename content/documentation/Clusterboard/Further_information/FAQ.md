---
title: "FAQ"
draft: false
menu:
  docs:
    title:
    parent: "Clusterboard/Further_information"
    identifier: "Clusterboard/Further_information/FAQ"
    weight: 2
---

**Q**: Are the individual MAC addresses linked to the PHY chips, or the module?

**A**: The MAC address is specific to the SOPINE module; swapping modules within the Clusterboard does not change the MAC address of the module.

**Q**: Why will SOPINE modules not reboot when installed on a Clusterboard, but will when installed on a [SOPINE Baseboard](/documentation/SOPINE_Baseboard)?

**A**: The cause has been determined to be back-EMF, and can be resolved with some relatively easy hardware modifications, thanks to excellent troubleshooting performed by Eric. Please, have a look at the [extensive article](https://ericdraken.com/a64-reset-problem/) he wrote to find out how to resolve this issue. See also [this forum thread](https://forum.pine64.org/showthread.php?tid=5849&page=2) for further information.

**Q**: Do I need heatsinks on any of the components on the Clusterboard?

**A**: According to the datasheets for the RTL8370N switch ASIC and the RTL8211E PHYs, they consume and thus dissipate up to about 3&nbsp;W each. As a result, it would be advisable to properly affix passive aluminum heatsinks onto each of these components. Please note that this explanation does not cover the SOPINE and SOEDGE modules.
