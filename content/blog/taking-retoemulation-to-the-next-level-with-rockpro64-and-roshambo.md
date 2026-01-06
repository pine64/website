---
title: "Taking RetroEmulation to the next level with RockPro64 and Roshambo"
date: "2019-05-13"
authors: ["JimmyRustles"]
categories:
  - "rock64"
  - "gaming"
  - "news"
  - "rockpro64"
tags: 
  - "gaming"
  - "rockpro64"
  - "rock64"
cover:
  image: ""
images:
  - ""
---

Retro Emulation is all the rage these days. What's old is now new again. Game Emulation has been around for awhile, but the recent resurgance into making mini consoles spearheaded by the release of the NES Classic has opened up new possibilities for making our own NES or SNES classic's.

Now Roshambo has released their own Gaming Case to compliment a few Single Board Computers, including the powerful RockPro64!

There are two separate models, one with compatibility for the rock64 and raspberry pi, and a Pro version specifically designed for the RockPro64.

In this review, I used the model for the RockPro64.

## The RoshamboPro Retro Gaming Case

![](/blog/images/RoshamboPro.jpg)

First off, the case is quite well built. It feels solid sturdy, and everything fits in as it should. If you get the case designed for the RockPro64, you will be getting a heatsink and fan included that can be controlled via software.

There is a recalbox image specifically for the RockPro64 that also enables the unique capabilities of this case. To start, let's go over those features:

1. It has a reset option, as well as a power-on/power-off mode.
2. It has two usb ports in the front where the controllers go, as well as a separate usb port in the back of the case, and an extra usb type-c adapter.
3. The most unique feature of all, the SATA adapter at the top where you can install a ssd that will allow you to load up all the games you'd like. You can get these special SSD's in 120gb, 256gb, and 512gb which look like little SNES carts.  You can purchase them [here](https://www.cloudmedia.com/?product=roshambo-ssd-cartridge).

![](/blog/images/Roshambo-SSD-2.jpg)

A picture of the SSD.

## The RockPro64

The RockPro64 is the star of the show.

It's more powerful than a Rock64, and far more powerful than a Raspberry Pi 3B+. 

![](/blog/images/ROCKPro64-SBC.jpg)

You can buy one [here at pine64.com](https://pine64.com/product-category/rockpro64/)

The RockPro64 comes in two flavors, a 2gb and 4gb version. The RoshamboPro Gaming kit for $99 will include the 2gb version, which should be all that's required.

Gaming performance wise, the RockPro64 just decimates the Raspberry Pi in raw-power. Games that were not playable on the Raspberry Pi will play on the RockPro64.

For example, the RockPro64 will play arcade games like Primal Rage (which is a fun fighting game with dinosaurs and huge gorillas) which the Pi3b will struggle with. The RockPro64 will even play PSP games! The RockPro64 should have no issues with Playstation or N64 games either, something that the Raspberry Pi will struggle with (especially with N64 emulation.)

You will need the included Fan though, as the RockPro64 can and will run pretty hot, especially in that case.

The RockPro64 includes a USB-Type C adapter, as well as a USB 3.0 port, and two USB 2.0 ports. You can use a MicroSD Card or a optional EMMC card for booting as well.

## Gaming on the RockPro64

The RockPro64 (and Rock64) both currently support the following distro's dedicated to gaming.

[Recalbox](https://github.com/mrfixit2001/recalbox_rockpro64/releases)

[Batocera Linux](https://batocera-linux.xorhub.com/)

[Lakka](http://le.builds.lakka.tv/Rockchip.ROCKPro64.arm/)

In this review, I used Recalbox, which combines Retroarch along with Emulationstation in a very easy to use Distro where you can do practically everything you need straight from the GUI.

Batocera is also very similar to Recalbox with some minor changes in UI.

While Lakka is different in that while it uses Retroarch, but does not use Emulationstation as a frontend.

When using the RockPro64, you will need to add in a Wifi Adapter.  You can get a Wifi/Bluetooth module, or use a usb wifi adapter. I myself used my old trusty Linksys Wireless G usb adapter. You can load roms by mounting the SMB Share via Windows.

Click Start > This PC > Right click "This PC" and click on "Map Network Drive" > Type in the IP address of the rockpro64 like \\\\192.168.x.x or \\\\RECALBOX

You should be able to then find the ROMS share and just drag and drop the roms.

After you're done, open up the Recalbox menu and select Ui Settings > update games list.

And your games should show up on Recalbox.

If you want to add in pictures and data about the games, you can use the built in scraping tool or you can use a tool on your PC called Skraper.

If you want to learn more about RetroGaming on a RockPro64, Rock64, or even other Single Board Computers, please join us at the /r/sbcgaming subreddit and discord.

### Useful Links and Resources

[Subreddit: /r/sbcgaming](https://www.reddit.com/r/sbcgaming)

[/r/sbcgaming Discord](https://discord.gg/5dSUjmk)

(Use these to talk about RetroGaming on the RockPro64, the Rock64, or any other Single Board Computer! We'll be glad to have you there! And please stop in and say hi!)

[Pine64 Discord](https://discordapp.com/invite/DgB7kzr)

(Talk about the Rock64, Pine64, or RockPro64 here!)
