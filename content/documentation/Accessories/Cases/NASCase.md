---
title: "NASCase"
draft: false
menu:
  docs:
    title:
    parent: "Accessories/Cases"
    identifier: "Accessories/Cases/NASCase"
    weight:
aliases:
  - /wiki/NASCase
  - /wiki/NASCase-STAR64
  - /wiki/NAS_Case
---

The PINE64 NAS Case is intended for either a Network Attached Storage (NAS) or Desktop application, but it can also be used in a number of other server capacities. It is built from precision-cut and powder-coated aluminum. The physical dimensions are 232.4mm (Width) x 105.0mm (Height) x 145.2mm (Depth).

An exploded view of the NAS Case, illustrating how all the components come together, can be found [here](https://files.pine64.org/doc/rockpro64/ROCKPro64%20NAS%20Case%20Exploded%20View%20Diagram.pdf). Please refer back to this PDF document during assembly to verify correct orientation of individual components.

{{< figure src="/documentation/images/NASCaseMain.png" caption="Front View of the PINE64 NAS Case for the ROCKPro64" width="400" >}}

## What does the NAS Case house?

{{< figure src="/documentation/images/NAS_Case_internals.jpg" caption="Internal Layout of the NAS Case" width="200" >}}

The NAS Case can house the following components:

* A ROCKPro64 Single Board Computer (SBC) with a tall, mid-size or slim/ no heatsink
* A PCIe to dual SATA adapter or a different low-profile PCIe card, e.g. an NVMe adapter
* Either two 3.5 inches OR t incheso 2.5 inches HDDs / SSDs; combination of any two sized drives is accepted
* A 80mm fan with a Ph 2-Pin connector
* Up to three SMA antennas, two of which can be attached to the WiFi/ BT module

## What comes in the box?

When you purchase the NAS Case from the PINE store the following items are shipped to you:

* The NAS Case itself, which consists of a top and a bottom half as well as an internal HDD SSD mount.
* Two SATA cables
* A custom power cable capable of powering two  2.5 inches  inchesr 3.5 inches HDDs /SSDs
* The required screws, fittings and a LED relay

## What other bare-minimum things do I need for a NAS build?

You will need the PCIe to SATA adapter from the PINE64 store to connect your disks to your ROCKPro64 board. <span>https://</span>forum.pine64.org/showthread.php?tid=6932. WARNING: this adapter does not work well with two HDDs, see https://forum.pine64.org/showthread.php?tid=6511:

{{< figure src="/documentation/images/PCIetoSATA.png" width="200" >}}

To assemble a functional NAS in the NAS Case you will require a number of additional parts.

With the exception of HDDs/SSDs, everything you need for a complete build can be purchased from the PINE store:

* A ROCKPro64 2GB or 4GB board
* A 12V 5A power supply
* A PCIe to dual SATA adapter: [**WARNING**, the SATA adapter from PINE64 store is low-quality and](https://forum.pine64.org/showthread.php?tid=6932) [will not function well with two SATA HDD](https://forum.pine64.org/showthread.php?tid=6511).
* One or two 2.5 inche inches/ 3.5 inches HDDs (not sold in the PINE store).
* A class 10 micro SD card and/or eMMC module.

You can purchase all the aforementioned items in the [PINE64 store](https://www.pine64.org/?post_type=product)

## What other things should I consider buying for a NAS build in the NAS Case?

There are a few other things which you may wish to consider purchasing for your NAS. These peripherals, while not necessary from an operational standpoint, may contribute to the longevity and stability of your NAS’ operation OR expand it with additional functionality:

* An eMMC to USB 2.0 adapter
* A tall heatsink (N.B. Any of the three available heatsinks will fit in the NAS Case)
* An 80mm fan
* The WiFi / BT module

(The fan and heatsink are highly recommended)

## Which software should I use?

{{< figure src="/documentation/images/OMVGUI.png" caption="The OMV WebGUI is easy to understand but also very robust. It offers easy installation of plugins, system administration and overview of available services" width="200" >}}

If you are intending to build a home or small company NAS, then we strongly recommend you use [Open Media Vault (OMV)](/documentation/ROCKPro64/Software#openmediavault). OMV is an open source NAS solution that makes setting up user accounts, network shares and services a breeze. It also simplifies installing additional features (called plugins), such as: PLEX media server; Remote Desktop; Encryption; RSync; etc.

Its worth noting that Nextcloud, or other similar Cloud storage solutions, can also be easily installed alongside the OMV OS Image.

Administration and monitoring of OMV is done via an advanced WebGUI, which also allows for updating and upgrading the ROCKPro64.
To learn more about OMV please visit [their website](https://www.openmediavault.org/). 

To download the latest OMV build OR one of the numerous available Linux Distribution OS Images please visit the [ROCKPro64 OS download section](/documentation/ROCKPro64/Software).

## Step-by-Step Assembly Instructions

If you prefer a video tutorial or just want an overview of the process before you start [check out this instructional video](https://www.youtube.com/watch?v=_UeeklKo0Og).

### Step 1. Preparation of the NAS Case for Installation

Remove the top of the NAS Case. It is held together by two screws on either side with the exception of the bottom (left, right, top and back). Once done, the top of the case should lift right off without any resistance.

The next step is to remove the HDD/SSD holding bracket, which is screwed into the bottom of the case. Flip the bottom over and undo the screws which hold the bracket in place.

You should now be left with a bare case ready for installation of the necessary components.

### Step 2. Installing the ROCKPro64 into the NAS Case

{{< figure src="/documentation/images/ROCKPro64inNASCase.jpg" caption="Correct Placement of the ROCKPro64 in the empty case, with Ethernet; Power; and HDMI at the back of the NAS Case" width="300" >}}

{{< figure src="/documentation/images/FrontIO.png" caption="Front IO with IR and LED relay installed" width="300" >}}

Make sure nothing is plugged into your ROCKPro64 - including a micro SD card.
If you intend to use a heatsink with your board then please install it now before proceeding. If you bought the heatsink from the Pine64 store it comes with thermal paste and/or a thermal pad. You can use one or the other (not both!). The thermal pad is easier to apply but the thermal paste should be better at cooling if properly applied.

Place your ROCKPro64 into the case with USB 2.0 and 3.0/C ports facing the front of the case. It should fit snugly and align with the port cut-outs in the case. Do not attempt at installing the board at an angle; insert it while holding it level and lowering it into the case.

Secure the board with 4x screws included in the see-through bag. Make sure that the board is held firmly in the case but do not overtighten the screws.

In the see-through bag you will also find a small semi-opaque plastic cylinder. This is the LED light lead and it should be installed from the outside of the case into the hole right over the reset (RST) switch. Simply press it into the hole until it sits tight.

If you wish to install an IRx receiver into your case then you should also place it into the IR socket at this stage. It should align with the cutout right above the power (PWR) switch.

### Step 3 PCIe to SATA adapter and Cabling

{{< figure src="/documentation/images/DC_Location.jpg" caption="DC header on the ROCKPro64 for the power cable" width="200" >}}

{{< figure src="/documentation/images/PCIeFittedSATAsockets.png" caption="PCIe to SATA installed. Note the SATA connection orientation" width="200" >}}

With the board in place it’s time to set up the PCIe to SATA adapter and do the cabling necessary to attach HDDs / SSDs.

Place the SATA Adapter into the PCIe slot on the ROCKPro64 board so that the holding bracket of the adapter faces the back of the case. In the back of the case there is a cutout for the PCIe adapter; some
variants of the PCIe dual SATA adapter can be configured for eSATA if need be, and the eSATA ports are accessible in the back of the case. By default, the internal SATA connectors are active on the adapter.

Secure the PCIe dual SATA Adapter with a single screw at the top of the bracket, in the back of the NAS Case.

This is the right time to plug in the SATA and custom power cable. The SATA cables plug into the ports on the top or front of the adapter while the power cable plugs into DC header located on the board  - just below the power jack, to the left of the Ethernet port (when viewed from front).

Have the cables hang outside the case or to the side for now so that they do not get in the way until they are needed.

### Step 4. Installing HDDs / SSDs into the Holding Bracket

{{< figure src="/documentation/images/Bracket_Orientation.png" caption="Bracket Orientation in the NAS Case" width="300" >}}

The next step is to install HDDs/ SSDs into their holding bracket; 2.5 inches drives need to be installed at the very bottom of the bracket whi inchese 3.5 inches drives are at the top of the the bracket.

For 2.5 inches drives make sure that the drives are oriented up and their SATA and power ports face the front of the NAS Case.

For 3.5 inches HDDs, make sure they are oriented up and their SATA and power ports face the right side of the NAS Case (towards the fan mounting location).

Each drive you mount in the holding bracket requires 4x screws which come supplied in the see-through bag. Make sure the drives are held in place firmly but do not over-tighten the screws.

Once the holding bracket is assembled and you have your drives mounted, please set it aside and proceed to the next step.

### Step 5. Installing Extras (eMMC; WiFi BT module + SMA Antennas; 80mm Fan)

{{< figure src="/documentation/images/80mmfan.png" caption="The 80mm fan is a worthwhile addition to the NAS Case build" width="200" >}}

If you have additional peripherals, such as an eMMC or WiFi/BT module as well as the 80mm fan, then now is the right time to install them. If you have **none of the above**, please **proceed to step 6** of this guide.

The eMMC and WiFi/BT modules are fitted into their respective placements on the ROCKPro64 board - please consult the diagram for their correct installation.

If you intend to use external u.FL to SMA antennas in the NAS Case then this is also the time to install them into the case. In the back section of the case at the very top you will find three cut-outs where the SMA antennas can be fitted. Don’t plug the u.FL leads antenna leads into the WiFi/BT module just yet - instead wait until after the disk holding bracket is installed into the case (step 6).

The fan should be mounted on the right-hand side of the case. We suggest that the fan is oriented for negative pressure, blowing air out of the case rather than taking air in. (User:AlephNull disagrees and recommends a positive pressure configuration both to allow a filter to be placed over the intake to prevent dust ingress and because the cage on the outlet side of the fan helps keep the wiring for 3.5" disks away from the fan blades). For best cable management results, have the fan power lead face the front of the case so that it can easily be routed to its header located next to GPIO pins on the ROCKPro64.
The fan should be secured using 4x long screws (that fasten into bolts) which can be found in the see-through bag supplied with the NAS Case.
Plug in the fan at this stage of the installation and route the cable at the bottom of the front of the case.

### Step 6. Installing the HDD / SSD Bracket and Routing Cables

{{< figure src="/documentation/images/NASCAsewithdrives.jpg" caption="Complete assembly of the NAS Case" width="300" >}}

{{< figure src="/documentation/images/TopViewAssembly.png" caption="Top view of a complete NAS Case Assembly" width="300" >}}

Installing the HDD/SSD bracket into the case and wiring it up is the last step before closing up the case.

Place the bracket with the disks installed (from step 4) into the case. The bracket should line up with the guiding bolts and screw holes at the bottom of the case. The section of the bracket that holds 3.5 inches HDDs needs to face the left side of the case (when viewed from front) and should overhang the ROCKPro64 board slightly. T inchese 3.5 inches SATA and power ports should face the right side of the case - where the fan mount inches, while 2.5 inches SATA and power ports should face the front of the case.

With the bracket aligned, flip the bottom of the case over while holding the bracket in place. Screw it into place using 4x Phillips head screws that came included with the NAS Case.

The last thing remaining before the NAS Case can be screwed shut is routing SATA and power cables:

For 3.5 inches HDDs we suggest routing power and SATA cables underneath the drives, whe inchese 2.5 inches HDDs/SSDs would otherwise reside.

For 2.5 inches disks you have plenty of routing options as there is much space available. The most obvious route is straight over the disks, where t inchese 3.5 inches HDDs would reside.

### Step 7. Closing the NAS Case and Powering On your NAS

Almost there. All that’s left to do is to screw together the NAS Case. Screw in the top front screws first followed by screws on either side of the case. Do the back screws last. There, you are done.

To power on your new NAS Case and HDDs all you need to do is to plug in power and Ethernet (This is obviously assuming that you are intending to use it as a NAS or a headless server).

## IO accessibility when the NAS Case is assembled

When the NAS Case is assembled and screwed shut these ROCKPro64 IO ports remain accessible:

* Micro SD slot
* USB 2.0
* USB 3.0 and USB type C
* Power and Reset switches
* The headphone and microphone jack
* Gigabit Ethernet port
* HDMI
