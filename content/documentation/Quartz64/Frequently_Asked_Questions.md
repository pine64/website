---
title: "Frequently Asked Questions"
draft: false
menu:
  docs:
    title:
    parent: "Quartz64"
    identifier: "Quartz64/Frequently_Asked_Questions"
    weight: 4
---

## Do I Need A Fan/What Heatsink Do I Need?

You don’t need a fan. The [20mm medium heatsink for Model A is plenty enough](https://pine64.com/product/rockpro64-20mm-mid-profile-heatsink/). For Model B, the [fan type heatsink](https://pine64.com/product/small-fan-type-heatsink/) will do fine.

## Can This Run A Minecraft Server?

Yes! Sort of. Testing on an 8GB Model A with PaperMC, User:CounterPillow was able to out-row world generation in a boat with just one player online, but aside from the slow world gen (which can be pre-generated) the server handled things like TNT explosions and mobs fine. It’ll probably do okay with 1-3 players.

## Do I Need The 5A Power Supply For Model A?

You only need the 5A power supply for Model A if you plan on connecting hard disk drives to the 12V header on the board.

## How Much Power Does It Consume?

For Model B, it’s &lt;2W in idle (powertop tunables not set), and &lt;5W under full CPU load (`stress-ng -c4`). Model A will be similar as it’s the same SoC.
