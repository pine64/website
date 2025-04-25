---
title: "Bluetooth and WiFi"
draft: false
menu:
  docs:
    title:
    parent: "Pinebook_Pro/Features"
    identifier: "Pinebook_Pro/Features/Bluetooth_and_WiFi"
    weight:
---

{{< figure src="/documentation/images/PinebookPro_WirelessIC_Location.jpg" title="The Pinebook Pro’s AP6256 wireless module" width="400" >}}

## Hardware Overview

The Pinebook Pro contains an AMPAK AP6256 wireless module to provide Wi-Fi (compliant to IEEE 802.11ac) and Bluetooth (compliant to Bluetooth SIG revision 5.0). The module contains a Broadcom transceiver IC, believed to be the BCM43456, as well as the support electronics needed to allow the Wi-Fi and Bluetooth modes to share a single antenna.

The wireless module interfaces with the Pinebook Pro’s system-on-chip using a combination of three interfaces: Bluetooth functionality is operated by serial UART and PCM, while the Wi-Fi component uses SDIO. It is unknown if the module’s Bluetooth capabilities are usable under operating systems that do not support SDIO.

The module’s RF antenna pin is exposed on the mainboard via a standard Hirose U.FL connector, where a coaxial feedline links it to a flexible adhesive antenna situated near the upper right corner of the Pinebook Pro’s battery. As the RF connector is fragile and easily damaged, it should be handled carefully during connection and disconnection, and should not be reconnected frequently.

## Issues

Problems have been reported with the Wi-Fi transceiver’s reliability during extended periods of high throughput, especially on the 2.4 GHz band. While the cause of this has yet to be determined, switching to the 5 GHz band may improve stability.

Since the Bluetooth transceiver shares both its spectrum and antenna with 2.4 GHz Wi-Fi, simultaneous use of these modes may cause interference, especially when listening to audio over Bluetooth. If Bluetooth audio cuts out frequently, switching to the 5 GHz band – or deactivating Wi-Fi – may help.

## Wi-Fi Capabilities

Wi-Fi on the Pinebook Pro is capable of reaching a maximum data transfer rate of approximately 433 megabits per second, using one spatial stream. The transceiver does not support multiple spatial streams or 160-MHz channel bandwidths.

The Wi-Fi transceiver supports the lower thirteen standard channels on the 2.4 GHz band, using a bandwidth of 20 MHz. At least twenty-four channels are supported on the 5 GHz band, spanning frequencies from 5180 to 5320 MHz, 5500 to 5720 MHz, and 5745 to 5825 MHz, with bandwidths of 20, 40, or 80 MHz. This might vary depending on the country you specify in the wireless settings, see `iw reg get; iw list`.

Maximum reception sensitivity for both bands is approximately -92 dBm. The receiver can tolerate input intensities of no more than -20 dBm on the 2.4 GHz band, and no more than -30 dBm on the 5 GHz band. Maximum transmission power is approximately +15 dBm for either band, falling further to approximately +10 dBm at higher data transfer rates on the 5 GHz band.

With current available drivers and firmware, the Wi-Fi interface supports infrastructure, ad-hoc, and access-point modes with satisfactory reliability. Monitor mode is not presently supported. Wi-Fi Direct features may be available, but it is unclear how to make use of them under Linux.

Be aware that Linux userspace utilities, such as _iw_, may report inaccurate information about the capabilities of wireless devices. Parameter values derived from vendor datasheets, or direct testing, should be preferred to the outputs of hardware-querying tools. That said, if a certain feature is not reported by _iw_ it means the currently running kernel driver plus firmware combination doesn’t support it, even when the hardware is capable.

WPA3 PSK support should be possible with _iwd_ but not _wpa_supplicant_, see [this ticket](https://github.com/raspberrypi/linux/issues/4718#issuecomment-1279951709) for details.

## Bluetooth Capabilities

Bluetooth data transfer speeds have an indicated maximum of 3 megabits per second, but it is unclear what practical data rates can be expected. Audio streaming over Bluetooth is functioning normally, as is networking. Bluetooth Low-Energy functions, such as interacting with Bluetooth beacons, have not yet been tested conclusively.

The Bluetooth transceiver supports all 79 channel allocations, spanning frequencies from 2402 MHz to 2480 MHz. Reception sensitivity is approximately -85 dBm, with a maximum tolerable reception intensity of -20 dBm. Bluetooth transmission power is limited to +10 dBm.

## Disabling Bluetooth

To disable Bluetooth under Linux once:

    sudo rfkill block bluetooth

To confirm if Bluetooth under Linux is disabled:

    rfkill

To disable Bluetooth on boot (NOTE: for distributions such as Manjaro XFCE see the step below):

    sudo systemctl enable rfkill-block@bluetooth

To disable Bluetooth on certain distributions, such as Manjaro XFCE, right click on the Bluetooth panel icon, select _plugins_, then _PowerManager_, then _configuration_ and then deselect the _auto power on_ option
