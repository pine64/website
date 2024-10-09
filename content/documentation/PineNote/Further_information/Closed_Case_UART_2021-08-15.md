---
title: "Closed case UART/2021-08-15"
draft: true # Page is not releasd
menu:
  docs:
    title:
    parent: "PineNote/Further_information"
    identifier: "PineNote/Further_information/Closed_Case_UART_2021-08-15"
    weight: 6
---

Times are in UTC-5

Logs collected from #pinedev on irc.pine64.org

**Sunday, August 15, 2021**

7:42:56 PM &lt;@UniversalSuperBox> Anyone know of an existing standard to route 115200 baud serial over USB-C?

7:43:18 PM &lt;megi> looks like mostly binary garbage, rather than assembly

7:44:09 PM &lt;dsimic> UniversalSuperBox: I don’t

7:44:18 PM &lt;@MartijnBraam> putting the uart on one of the usb-c pairs? :D

7:44:29 PM &lt;@MartijnBraam> or the google pixel standard

7:44:47 PM &lt;@konradybcio> or a separate usb for uart, honeycomb style :D

7:45:08 PM &lt;dsimic> or a magnetic switch :)

7:46:03 PM &lt;megi> or a glass mercury switch

7:46:09 PM &lt;@UniversalSuperBox> Modifying the case is not an option.

7:46:34 PM &lt;@MartijnBraam> your hacking it into a product?

7:46:37 PM &lt;dsimic> there’s some "Debug Accessory Mode" for Type-C

7:46:41 PM &lt;@UniversalSuperBox> No, the PineNote.

7:47:09 PM &lt;@MartijnBraam> https://wiki.postmarketos.org/wiki/Serial_debugging:Cable_schematics

7:47:35 PM &lt;dsimic> https://en.wikipedia.org/wiki/USB-C#Debug_Accessory_Mode

7:48:01 PM &lt;dsimic> "In this mode, all digital circuits are disconnected from the connector, and the 14 bold pins can be used to expose debug related signals (e.g. JTAG interface)."

7:48:17 PM &lt;dsimic> so, it should be possible to route the serial port

7:48:19 PM &lt;@MartijnBraam> that’s probably the best mode

7:48:46 PM &lt;dsimic> or even to route microSD lines :)

7:48:56 PM &lt;dsimic> or both! :)

7:49:08 PM &lt;dsimic> woo-hoo! :)

7:49:19 PM &lt;@MartijnBraam> jumpdrive for pinenote :P

7:49:28 PM &lt;@UniversalSuperBox> microSD was my thought too.

7:49:47 PM &lt;dsimic> problem solved...  maybe :)

7:50:00 PM &lt;@UniversalSuperBox> There is almost definitely a confounding factor that we don’t see yet.

7:50:17 PM &lt;@UniversalSuperBox> I’ve been trying to lower expectations all afternoon, so I’m a bit burnt.

7:51:10 PM &lt;dsimic> there surely needs to be some logic on the host side that allows the "DAM" to work

7:51:13 PM &lt;@UniversalSuperBox> Probably requires a USB-C controller on the motherboard or something.

7:51:26 PM &lt;@MartijnBraam> probably

7:51:29 PM &lt;@UniversalSuperBox> And the anx is basically not an option except for the PinePhone, they can’t be bought.

7:52:03 PM &lt;@MartijnBraam> can’t the rk3599 detect the debug attachment condition and toggle a gpio to control a simple mux?

7:52:23 PM &lt;@UniversalSuperBox> Doesn’t help for debugging a bootloader, does it?

7:52:33 PM &lt;@MartijnBraam> hmm true

7:53:03 PM &lt;@MartijnBraam> the resistors on the connector could be measured with a MCU hooked into it :P

8:13:52 PM &lt;dsimic> with some additional logic, this IC might do the trick: https://www.ti.com/lit/ds/symlink/hd3ss3212.pdf

8:15:58 PM &lt;@UniversalSuperBox> Finding an existing device with such a function would be more useful than finding the building blocks to create it ourselves.

8:16:06 PM &lt;@UniversalSuperBox> Great artists copy, as it were.

8:16:34 PM &lt;dsimic> I agree, but I haven’t been able to find such device yet

8:17:31 PM &lt;@UniversalSuperBox> I’m not sure if SuzyQable is such a use or not

8:22:43 PM &lt;@UniversalSuperBox> Reading the spec, I’m becoming less and less hopeful that the closed-case debugging feature can be enabled through mostly passive components.

8:23:19 PM &lt;@UniversalSuperBox>

8:31:29 PM &lt;dsimic> if all that fails, having an internal microSD card slot and both Linux and Windows applications that can use maskrom mode to flash OS images is still an acceptable solution, IMHO

8:37:33 PM &lt;@UniversalSuperBox> Yes, the SuzyQable is DAM, assuming the offhand comment at https://chromium.googlesource.com/chromiumos/platform/ec/+/HEAD/docs/usb-c.md is true

8:37:41 PM &lt;@UniversalSuperBox> > Debug accessory mode, e.g. Case Closed Debugging (CCD)

8:41:45 PM &lt;dsimic> the PineNote already uses this IC for CC control: https://cdn.datasheetspdf.com/pdf-down/W/U/S/WUSB3801-WillSEMI.pdf

8:42:17 PM &lt;dsimic> which means that it could be replaced with a similar IC that does that and has additional capability to detect DAM

8:42:28 PM &lt;dsimic> TI seems to have such ICs

8:42:46 PM &lt;dsimic> (I know, building blocks again, but do we have anything better?)

8:43:48 PM &lt;@smaeul> dsimic: that chip already has the ability to detect DAM

8:43:59 PM &lt;@smaeul> the WUSB3801

8:44:04 PM &lt;dsimic> I was going to write exactly that :)

8:44:12 PM &lt;dsimic> page 13 in the datasheet

8:46:33 PM &lt;@UniversalSuperBox> Many hands make light work — thanks so much for looking at it folks

8:46:50 PM &lt;dsimic> hm, but it can’t drive an output high/low, which means that a driver would need to select the switch position

8:46:58 PM &lt;dsimic> not an option while booting

8:47:31 PM &lt;dsimic> some TI ICs can drive a DEBUG output upon detecting DAM

8:47:49 PM &lt;dsimic> that DEBUG output can go to HD3SS3212

8:49:07 PM &lt;dsimic> https://datasheet.lcsc.com/szlcsc/2002291210_Texas-Instruments-Texas-Instruments-TPS25810RVCR_C473913.pdf

8:49:08 PM &lt;@smaeul> HD3SS3212 is way overkill. that’s for SuperSpeed lines

8:49:33 PM &lt;dsimic> I’m not saying that it must be HD3SS3212, I’m just giving possible examples

8:50:02 PM &lt;@UniversalSuperBox> Small note that the current parts were selected for availability as much as they were for ergonomics.

8:50:25 PM &lt;@tl_lim> just looking for a way that bring up console UART thru USB-C port so that developer no need to open up the PineNote back cover

8:50:34 PM &lt;dsimic> if we agree upon a solution, finding actually available parts is the next step :)

8:51:02 PM &lt;@tl_lim> Lets not goes wild.

8:51:06 PM &lt;@UniversalSuperBox> UART is the only thing we feel we really need, microSD is a bonus. We’ve only got a week to make schematic changes, and big changes are still a bad idea.

8:51:44 PM &lt;@UniversalSuperBox> It’d be lame, but could we bring 3.3v uart out over SB1 and SB2?

8:52:13 PM &lt;@UniversalSuperBox> Or would USB-IF scream?

8:52:32 PM &lt;@MartijnBraam> just add another magnet :P

8:52:59 PM &lt;@tl_lim> Just a console break-up board

8:53:26 PM &lt;@tl_lim> the trigger UART console signal out from USB-C port

8:53:32 PM &lt;@UniversalSuperBox> If you put the PineNote near a CT scanner, it shorts out because all the reed switches trigger

8:53:54 PM &lt;@tl_lim> s/the/that

8:54:07 PM &lt;dsimic> it shors out and the UART gets routed out :)

8:54:17 PM &lt;dsimic> * shorts

8:54:23 PM &lt;@UniversalSuperBox> Task failed successfully

8:54:24 PM &lt;@UniversalSuperBox> anyway

8:54:48 PM &lt;@tl_lim> any simple proposal welcome.

8:55:06 PM &lt;dsimic> would drilling a hole in the case be an option?

8:55:09 PM &lt;@smaeul> I think we are talking about the same thing: use a cable/breakout board to trigger DAM, which switches some pins to carry the UART

8:55:33 PM &lt;@tl_lim> DAM is too much

8:55:45 PM &lt;dsimic> what other options are there?

8:55:53 PM &lt;@tl_lim> just need two signals, T😆and RxD

8:56:14 PM &lt;@MartijnBraam> No headphone jack on the pinenote?

8:56:20 PM &lt;@tl_lim> no

8:56:24 PM &lt;@smaeul> but how do you know when to enable UART vs normal USB ?

8:57:05 PM &lt;@tl_lim> the UART signal only output when this break-out board plug into teh USB-C connector

8:57:17 PM &lt;@tl_lim> s/output/available

8:58:02 PM &lt;@tl_lim> normal USB-C cable plug in to USB-C connector, then normal USB behavior

8:58:06 PM &lt;@UniversalSuperBox> What you’re describing is DAM. Has the team already replied that it isn’t possible?

8:59:03 PM &lt;@tl_lim> brb in 30m mins, I wil keep wtach the chat. Just need to have a conference call.

9:04:20 PM &lt;@tl_lim> back now

9:05:25 PM &lt;@tl_lim> check out this: https://github.com/ddvk/remarkable2-recovery

9:06:41 PM &lt;dsimic> that still requires additional logic on the host side

9:08:17 PM &lt;@UniversalSuperBox> Mhmm, that’s using both the USB-C port and the pogo pins on the reMarkable for recovery. Seems like they exposed the iMX’s recovery pins on B8 (SBU2) of the USB-C cable. So that step is the same as our magnetic switch.

9:08:24 PM &lt;@UniversalSuperBox> Then UART comes out the pogo pins, which we don’t have.

9:08:40 PM &lt;@UniversalSuperBox> (along with the iMX flash mode)

9:09:44 PM &lt;dsimic> how about this: we must have additional logic on the host side (i.e. some board changes), so the primary question should be whether we want to take the route of doing it in the standard way (i.e. DAM), or we want to invent and implement some non-standard way?

9:10:25 PM &lt;dsimic> yeah, they use pogo pins, which the PineNote doesn’t have

9:10:37 PM &lt;@UniversalSuperBox> I’ve done more careful reading of the USB-C spec: https://www.usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-21

9:10:40 PM &lt;@smaeul> the willsemi chip looks extremely similar to this chip (same pinout), except the FUSB303B also uses the "ROLE" pin as a debug mode output: https://www.onsemi.com/pdf/datasheet/fusb303b-d.pdf

9:10:43 PM &lt;@UniversalSuperBox> See appendix B

9:11:26 PM &lt;dsimic> I can’t access  the spec

9:11:28 PM &lt;@tl_lim> purchase TI chip is a nightmere at current severe chip shortage situation.

9:11:44 PM &lt;dsimic> there might be other ICs that do the same

9:12:23 PM &lt;dsimic> UniversalSuperBox: could you, please, send the spec?

9:13:17 PM &lt;dsimic> ah, got it

9:13:55 PM &lt;@smaeul> tl_lim: any idea about the ON semi chip? it would be pretty close to drop-in compatible.

9:14:43 PM &lt;UnivrslSuprBox> https://usercontent.irccloud-cdn.com/file/PGeULRZK/USB%20Type-C%20Spec%20R2.1%20-%20May%202021.pdf

9:14:44 PM &lt;@tl_lim> That is possible, due to mux chip can be simply has other alternative chip or even using MOSFET

9:15:38 PM &lt;@smaeul> yes, it looks like 3-way (USB 2.0, Audio, UART) switch chips are available

9:15:40 PM &lt;@tl_lim> PineNote only use USB 2.0 signals

9:17:19 PM &lt;@UniversalSuperBox> Or audio

9:17:39 PM &lt;@UniversalSuperBox> But with a three-way switch, our own adapter board would break out UART.

9:17:41 PM &lt;@Icenowy> are you trying to use Debug Accessory mode?

9:17:57 PM &lt;@tl_lim> hi icenoway

9:18:11 PM &lt;@UniversalSuperBox> We’re trying to get closed-case UART on a device with only a USB-C port. If that involves DAM, that’s what we should use. (re @Icenowy: are you trying to use Debug Accessory mode?)

9:18:13 PM &lt;@tl_lim> how to implement UART way?

9:18:27 PM &lt;@Icenowy> well I think DAM too

9:18:46 PM &lt;@Icenowy> but I have no idea what can implement it

9:19:41 PM &lt;dsimic> well, we found a few ICs that can do that, or at least should do that, according to the datasheets

9:19:50 PM &lt;@tl_lim> interest to know more USB-C UART implementation

9:20:07 PM &lt;dsimic> how about this: we must have additional logic on the host side (i.e. some board changes), so the primary question should be whether we want to take the route of doing it in the standard way (i.e. DAM), or we want to invent and implement some non-standard way?

9:21:07 PM &lt;@tl_lim> this is just for console UART, don’t mind standard or non-standard way

9:21:26 PM &lt;dsimic> but we need board changes anyway

9:21:30 PM &lt;@Icenowy> I think there could be some hardware that already utilizes DAM

9:21:36 PM &lt;@smaeul> dsimic: for sure the standard way is safest, so we should do that if at all possible

9:21:38 PM &lt;@Icenowy> e.g. Google Pixels w/o 3.5mm ?

9:21:49 PM &lt;dsimic> smaeul: I agree 100%

9:22:04 PM &lt;@tl_lim> I may not

9:22:07 PM &lt;@UniversalSuperBox> The most well-known DAM device is the Chrome OS SuzyQable. that’s used on the Pixel 2 and up, and Chromebooks after the Pixelbook

9:22:24 PM &lt;@Icenowy> well yes, use the standard way can prevent incompatibility with 3rd party Type-C peripherals (re @p64protocolbot: &lt;@smaeul> dsimic: for sure the standard way is safest, so we should do that if at all possible)

9:22:27 PM &lt;@tl_lim> as stated, I just look for a simple way to bring up UART signal.

9:23:15 PM &lt;@Icenowy> it could be problematic to try to do things unstandardly (re @tl_lim: as stated, I just look for a simple way to bring up UART signal.)

9:23:17 PM &lt;@tl_lim> I want to minimize the change as little as possible

9:23:22 PM &lt;@Icenowy> considering compatibility

9:23:37 PM &lt;dsimic> I also want to make as few board changes as possible

9:24:26 PM &lt;@Icenowy> add a switch like what PineTab does?

9:24:31 PM &lt;@smaeul> UniversalSuperBox: SuzyQable would require a USB&lt;->UART adapter inside the device

9:24:34 PM &lt;@UniversalSuperBox> Case changes are not possible

9:24:49 PM &lt;@tl_lim> if the DMA way is simple, I will consider. If not a good way and then developer just need to open the back case.

9:25:27 PM &lt;dsimic> using DMA would require to add one IC and replace another, basically

9:25:45 PM &lt;@tl_lim> if TI chip, then NO

9:25:46 PM &lt;dsimic> (if we can find the right ICs that are currently available)

9:26:16 PM &lt;dsimic> * DAM

9:26:16 PM &lt;@Diego> ¿is it posible to out uart in usb-c audio adapter mode?

9:26:51 PM &lt;@UniversalSuperBox> It is non-standard so it poses at least a minimal risk to anything plugged in to the PineNote. (re @Diego: ¿is it posible to out uart in usb-c audio adapter mode?)

9:26:55 PM &lt;@smaeul> Diego: that’s the same thing as DAM, just with resistors pulled the other way

9:26:58 PM &lt;dsimic> that would also require some IC to do the switch, and would also be non-standard

9:27:55 PM &lt;@smaeul> I happen to be looking at ON semi’s website at the moment, so there may be other options, but DAM would be doable by replacing the Type-C chip with this: https://www.onsemi.com/pdf/datasheet/fusb303b-d.pdf and the 2-way mux with a 3-way mux like this: https://www.onsemi.com/pdf/datasheet/fsa1153-d.pdf

9:28:02 PM &lt;@tl_lim> when thinking on UART console thru USB-C, there is assumption is not a standard

9:28:36 PM &lt;@tl_lim> FUSB303B is a nightmere chip to purchase.

9:28:55 PM &lt;@smaeul> ok, good to know

9:29:26 PM &lt;@tl_lim> I have no interest PineNote delay for few months due to we try to do UART thru USB-C.

9:30:13 PM &lt;@tl_lim> BTW, Pinecil currently using FUSB303

9:30:44 PM &lt;dsimic> what’s VCC_HALL_3V3 in the schematic?

9:30:52 PM &lt;@Icenowy> I think it’s 302?

9:30:57 PM &lt;@Icenowy> for Pinecil

9:31:01 PM &lt;@Icenowy> (and PBP

9:31:25 PM &lt;@tl_lim> sorry 302, my bad

9:33:48 PM &lt;dsimic> well, here’s a crazy option, if all else fails...  add a magnetic switch that cuts off both VDD and VUSD from WUSB3801 and connects RX and TX to the CC1 and CC2 pins

9:34:21 PM &lt;dsimic> it might even work :)

9:34:48 PM &lt;@smaeul> it would be better to use the SBU pins -- they are already brought to the mainboard but unused

9:34:53 PM &lt;@UniversalSuperBox> Nah, if we were going to do something dumb, we could route it over SBU

9:35:13 PM &lt;@UniversalSuperBox> But even that could end up blowing out a poorly designed device on the other end, or the PineNote itself.

9:35:22 PM &lt;@UniversalSuperBox> If we’re going to dumb options, let’s not do it at all

9:35:38 PM &lt;dsimic> I’m glad that my crazy option is considered dumb :)

9:35:50 PM &lt;@tl_lim> Just FYI, FUSB303 totally no stock :

9:36:28 PM &lt;dsimic> I agree, either in the standard way or not at all

9:36:36 PM &lt;@UniversalSuperBox> Oh, sorry. I should be more careful with my words dsimic

9:37:03 PM &lt;dsimic> oh no, I’m really happy that it was called dumb :)

9:37:10 PM &lt;@tl_lim> PineNote just only USB 2, teh USB 3 signal is not use

9:37:55 PM &lt;dsimic> yeah, but we can’t connect something randomly to the unused pins

9:38:04 PM &lt;@UniversalSuperBox> But the moment some terrible USB hub starts sending 5V over the USB 3.0 pins for "device detection" we kill the RK3566

9:38:12 PM &lt;@tl_lim> we just need a simple way the console break out board can trigger mux circuit and output the UART signals

9:38:55 PM &lt;@UniversalSuperBox> Well, the standard way to do that would be DAM. If both CC1 and CC2 are pulled high (or low), all of the USB-C pins switch to a vendor-specified pinout.

9:39:12 PM &lt;dsimic> yeah, DAM it is

9:39:18 PM &lt;@UniversalSuperBox> It’s not possible to have CC1 and CC2 pulled during normal use because standard USB-C cables only have one of the two connected.

9:40:09 PM &lt;@tl_lim> may be using the DAM way to trigger the mux and teh UART sign output from 2 USB 3.0 pin which current not been used

9:40:17 PM &lt;@smaeul> assuming DAM is not possible, something simpler to control MOSFETs between UART and SBU would work, as long as it didn’t trigger accidentally

9:40:29 PM &lt;dsimic> tl_lim: yes, we could do that with DAM

9:40:29 PM &lt;@UniversalSuperBox> If that detection of both CC1 and CC2 can be done on an external mux circuit, it seems shaky but usable.

9:41:03 PM &lt;@tl_lim> prefer to use USB 3 signal due to not in use at PineNote

9:41:15 PM &lt;@UniversalSuperBox> When DAM is detected, the USB-C port disconnects all standard USB-C signals and connects any signals you want to the specified pins.

9:41:40 PM &lt;dsimic> it’s up to the vendor to use the pins in any way in DAM, but we must not have the UART connected at all when DAM isn’t detected

9:41:42 PM &lt;@UniversalSuperBox> Just like when audio mode is detected, everything is disconnected and the audio stuff is connected.

9:42:03 PM &lt;dsimic> but we can keep USB 2.0 signals conected in DAM, right?

9:42:07 PM &lt;@tl_lim> no need to disconnect, just route uart signal to two unused usb3 pins

9:42:12 PM &lt;dsimic> that’s our OEM spec :)

9:42:26 PM &lt;dsimic> * connected

9:42:53 PM &lt;dsimic> we’re free to connect anything anywhere in DAM, so we can leave the USB 2.0 pins connected, but actually not use them

9:43:03 PM &lt;@tl_lim> when both CC1 and CC2 detected high

9:43:17 PM &lt;dsimic> i.e. in the DAM

9:43:40 PM &lt;dsimic> but we must not have the UART connected at all to the USB pins when DAM isn’t detected

9:43:49 PM &lt;@tl_lim> just 74125 will do

9:43:52 PM &lt;dsimic> switching UART should be very simple

9:44:25 PM &lt;dsimic> so we just need an IC that detects DAM, or a way to implemenent that "by hand"

9:44:39 PM &lt;dsimic> problem solved, right? :)

9:44:48 PM &lt;@tl_lim> when both cc1 and cc2 not in logic hi, the gate is floating.

9:45:35 PM &lt;dsimic> but the existing WUSB3801 must not be affected

9:45:40 PM &lt;@tl_lim> I try to use USB 3 signal due to not use and less compatibility issue

9:46:14 PM &lt;dsimic> using USB 3.0 pins is fine, but the UART must be disconnected from them when DAM isn’t detected

9:46:24 PM &lt;dsimic> and the USB 2.0 bus an remain connected in DAM

9:46:28 PM &lt;dsimic> * can

9:46:41 PM &lt;dsimic> that’s our vendor DAM layout :

9:46:43 PM &lt;dsimic> :)

9:47:01 PM &lt;@UniversalSuperBox> But would we hit an issue where the existing WUSB3801 would get confused in that state?

9:47:03 PM &lt;dsimic> does everyone agree on that?

9:47:06 PM &lt;@tl_lim> no need to flip, the UART console break out board only works one way which component layer face up

9:47:16 PM &lt;@tl_lim> there is no WUSB3801

9:47:22 PM &lt;@UniversalSuperBox> oh, what was it called

9:47:39 PM &lt;dsimic> there is WUSB3801 in the PineNote already

9:47:45 PM &lt;dsimic> U9008

9:47:49 PM &lt;@tl_lim> code name: Dalton Operation 😊

9:48:16 PM &lt;dsimic> anyway, the existing WUSB3801 must not be affected

9:48:46 PM &lt;dsimic> by the additional CC/DAM detection logic

9:48:59 PM &lt;@UniversalSuperBox> Yeah, I’m not crazy. The schematic has a WUSB3801 on it.

9:49:01 PM &lt;@smaeul> The WUSB3801 detects DAM already, so it should be fine as long as our "CC high" detection logic doesn’t mess up Rp/Rn detection

9:49:09 PM &lt;dsimic> right

9:49:46 PM &lt;@tl_lim> just a simple AND logic on cc1/cc2 and 74125 type for Tx and Rx.

9:50:15 PM &lt;@UniversalSuperBox> I would guess that WUSB3801 powers VCC_HALL_3V3 so that in a no-battery case, plugging in power with the magnet switch triggered would still cause the RK3566 to go into maskrom flash mode.

9:50:36 PM &lt;dsimic> VCC_HALL_3V3 is a regulated supply, AFAICT

9:50:54 PM &lt;@UniversalSuperBox> (to answer the earlier question)

9:51:05 PM &lt;@smaeul> yeah, it’s the other way around. VCCHALL3V3 powers the WUSB3801

9:51:33 PM &lt;@UniversalSuperBox> k

9:52:50 PM &lt;@UniversalSuperBox> > just a simple AND logic on cc1/cc2 and 74125 type for Tx and Rx.

9:52:58 PM &lt;@UniversalSuperBox> ^ Will this work?

9:53:27 PM &lt;dsimic> 74152 should work for the UART

9:53:35 PM &lt;dsimic> * 74125

9:54:01 PM &lt;@tl_lim> for MOSFET

9:54:28 PM &lt;@tl_lim> just give teh design engiener an idea and they figure out 😊

9:54:31 PM &lt;dsimic> but for the AND logic on CC1 and CC2, I’m not 100% sure how to do that without affecting the WUSB3801 (U9008)

9:55:09 PM &lt;dsimic> but the board designer should be able to figure that out :)

9:56:10 PM &lt;@tl_lim> the worst case is OTG and uart console cannot works at same time, and I don’t think this is a big issue

9:56:21 PM &lt;@UniversalSuperBox> That would honestly be my expected state

9:57:25 PM &lt;@tl_lim> I just hate to ask developers using tool to open the PineNote backcase when need to access to the console UART. Just think a simple way

9:57:31 PM &lt;@UniversalSuperBox> and if you really want to ruin your engineers' day, tell them to disconnect all the USB pins and route the microSD pins when CC1 and CC2 are both connected 😈

9:58:16 PM &lt;@UniversalSuperBox> But y’know, whatever keeps the cost acceptable works.

9:58:56 PM &lt;dsimic> when the console cable is connected, nothing else works

9:59:05 PM &lt;dsimic> that’s the expected behavior

9:59:17 PM &lt;dsimic> I mean, nothing else on the USB connector works :)

9:59:17 PM &lt;@tl_lim> appreciate and thanks on brainstorming.

9:59:40 PM &lt;@UniversalSuperBox> It is indeed expected that when CC1 and CC2 are shorted, USB stops working. To the spec, that is an acceptable outcome.

9:59:51 PM &lt;@UniversalSuperBox> Sorry, s/shorted/pulled high or low/

10:00:14 PM &lt;@tl_lim> then I just need to create a small breakout board and give away on the first batch PineNote

10:00:46 PM &lt;dsimic> also, when the serial console cable is connected, our vendor-defined DAM pinout becomes effective

10:00:59 PM &lt;dsimic> + some board changes

10:01:04 PM &lt;@UniversalSuperBox> Right. Having UART on it is most important. Having microSD and USB 2.0 as well would be really cool, but not a requirement.

10:01:26 PM &lt;@UniversalSuperBox> Depending on how debug you want the debug cable to be :)

10:01:26 PM &lt;dsimic> we could have microSD as well

10:01:34 PM &lt;@UniversalSuperBox> could, not needed

10:01:41 PM &lt;dsimic> yeah

10:01:53 PM &lt;dsimic> can an internal microSD slot be added?

10:02:08 PM &lt;@UniversalSuperBox> That’s an idea that’s been floated. At least a header on the board.

10:02:37 PM &lt;@tl_lim> microSD needs more pins.

10:02:54 PM &lt;dsimic> can we pull that idea low or high, so it isn’t floating? :)

10:05:11 PM &lt;dsimic> hmm, just a second, please...

10:05:42 PM &lt;@tl_lim> I just focus on UART console route out possibility

10:06:44 PM &lt;@tl_lim> BTW, just lets you knows a lot of cheap USB-C cable in market short cc1 and cc2 together to save a wire.

10:07:04 PM &lt;dsimic> https://en.wikipedia.org/wiki/USB-C#Debug_Accessory_Mode ... yeah, we can use USB 3.0 pins for UART, and we’re left with eight more unused pins to play with

10:07:56 PM &lt;@tl_lim> who provid ethe cable?

10:08:19 PM &lt;dsimic> we can have microSD as well, there are enough free pins :)

10:08:45 PM &lt;@smaeul> ...if you modify the cable connecting the mainboard to the USB board, and the USB board

10:09:06 PM &lt;@tl_lim> too much job

10:09:27 PM &lt;dsimic> those cables are costly to modify

10:09:40 PM &lt;@smaeul> exactly, please consider the scope of what you’re asking for, not just if it’s possible

10:09:50 PM &lt;dsimic> of course

10:09:54 PM &lt;@UniversalSuperBox> Will an internally-mounted breakout cable for microSD  be available in the store @tl_lim?

10:09:58 PM &lt;dsimic> so, UART it is :)

10:10:22 PM &lt;@tl_lim> just UART

10:10:44 PM &lt;@UniversalSuperBox> NOT usb-c, only an internal ribbon cable to a microSD card slot (re @UniversalSuperBox: Will an internally-mounted breakout cable for microSD  be available in the store @tl_lim?)

10:10:48 PM &lt;@tl_lim> the people can use a USB-C breakout board that alreasdy available in market

10:11:35 PM &lt;@UniversalSuperBox> Yes

10:11:44 PM &lt;dsimic> I don’t think that the microSD lines are routed at all on the board

10:11:56 PM &lt;@tl_lim> currently not

10:12:08 PM &lt;@UniversalSuperBox> But that’s something pgwipeout made clear we should really do

10:12:22 PM &lt;dsimic> then we’d have no use of a ribbon cable for microSD, without a board redesign

10:12:30 PM &lt;@tl_lim> the product board will have microSD signal bring to a flex connector

10:12:40 PM &lt;dsimic> ah, that’s fine

10:13:02 PM &lt;@UniversalSuperBox> Were there any other signals coming out to flex connectors on the final revision? (re @tl_lim: the product board will have microSD signal bring to a flex connector)

10:14:36 PM &lt;@tl_lim> other will be easter egg hunting games
