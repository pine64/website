---
title: "History of hardware changes"
draft: false
menu:
  docs:
    title:
    parent: "Pinecil/Further_information"
    identifier: "Pinecil/Further_information/History_of_hardware_changes"
    weight: 
---

**Pinecil V2**

* On Aug. 2, 2022, Pinecil V2 was released with improved hardware & accessories. It retains the same ergonomics and design as the original Pinecil, and will work with any accessories you already have including existing handles, cases, and tips. It comes with a green color silicone grip versus the light blue finger grip from Pinecil V1. It also includes one of PINE64’s newly designed shorter 6.2 ohm tips. By reducing the tip length and resistance from 8 to 6.2 ohms, it allows greater performance and and faster heating (short tips are potentially 64W @ 20V compared to 8ohm normal tips which allow a max of 50W to Pinecil). Pinecil V2 is _officially_ rated for 12V-24V.
* Key changes in V2: new processor (BL706), higher maximum input voltage (24V versus V1’s 21V rating), support for measuring tip resistance, allows automatic detection of 6.2 vs 8 ohm tips. A notable improvement is the new BL706 RISC-V processor from Bouffalo. It is similar to the BL602 in the Pinenut. The BL706 features Bluetooth Low Energy (BLE / Zigbee); future IronOS firmware releases will expose features over BLE. This is not trivial work, but as people contribute to the opensource code of GitHub/IronOS, BLE options will expand. There is also tentative support for USB-PD3.1 EPR (28V, 140W chargers), Ralim’s IronOS supports V2 running with USB-C EPR-28V. EPR/PD3.1 is not officially acknowledged yet by the Pine Store. Many brands of EPR USB-C chargers are confirmed by members to work on Pinecil V2 at 28V and this results in faster heating performance over PD 20V chargers [see short test here](https://www.youtube.com/watch?v=nTC-ah4f0hg).
* Things staying the same in V2: it still uses a RISC-V processor, but adds noticeable upgrades to the hardware. GPIO is broken out on USB-C for creating your own projects, same pinout as Pinecil V1, same great feel, including the rubber grip, works with all existing tips, same DC input + USB-C input connections, and compatibility with existing clear or black handles.
* In the V2 handle’s side label, the 88W figure comes from a 6.5ohm tip calculation. The reason for using 6.5 instead of 6.2 for the new short tips calculation is due to tolerance during manufacturing, and leaving a conservative margin of error (actual tips appear to be 6.2 ohms). V2 set max voltage is listed as 24V because this was the value used during design and component selection.

**Pinecil V1**

* For the first manufacture batch (October 2020, order number 158xxx) of the Pinecil, the copper ring connecting the earth screw to the tip was omitted as the engineering team found the TS100 design lacking. For the second round onward, an improved design copper ring has been included as standard, and is also included with the replacement clear and black handles. For normal operation of the iron, omission of the ring does not impact it’s operation. **If you are working with ESD components, you will need it in order to ground the iron tip via the earth screw at the back of the iron.**
* Programmable with [tools from Gigadevice](https://doc.nucleisys.com/nuclei_sdk/design/soc/gd32vf103.html)
* The first batch of Pinecils were rated 12-24v @ 65W. After some heated discussion on the discussion group, it was decided that it would be downgraded to 12-21V @ 60W, due to concern over the connection of the DC jack to the USB-PD chip, which has a recommended maximum of 21v, and absolute maximum of 28v.
