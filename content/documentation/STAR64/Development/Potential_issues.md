---
title: "Potential issues"
draft: false
menu:
  docs:
    title:
    parent: "STAR64/Development"
    identifier: "STAR64/Development/Potential_issues"
    weight: 2
---

If you get the following error in U-Boot (or your 8 GB board is only detected as 4 GB) the possible cause is an empty or corrupted EEPROM:
 
```
Not a StarFive EEPROM data format - magic error
EEPROM dump: (0x100 bytes)
00: FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF 
10: FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF 
20: FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF 
30: FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF 
40: FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF 
50: FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF 
60: FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF 
70: FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF 
80: FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF 
90: FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF 
A0: FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF 
B0: FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF 
C0: FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF 
D0: FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF 
E0: FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF 
F0: FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF 
```

To address this, execute the following commands from within U-Boot:

```
mac initialize
mac product_id <PRODUCTID>
mac write_eeprom
```

Set ProductID to either:

* For 8 GB Models: STAR64V1-2310-D008E000-01234567
* for 4 GB Models: STAR64V1-2310-D004E000-01234567
 
You can replace the last 8 digits with a random number if you wish. 

If these commands fail, please join the #star64 channel in the Pine64 community for more assistance.
