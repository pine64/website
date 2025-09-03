---
title: "Modem"
draft: false
menu:
  docs:
    title:
    parent: "PinePhone_Pro"
    identifier: "PinePhone_Pro/Modem"
    weight: 6
---

The PinePhone Pro uses Quectel EG25-G as modem. AT commands are used to communicate with the modem.

## AT commands

A list of documented AT commands can be found for example in this [AT commands documentation](https://wiki.pine64.org/wiki/File:Quectel_EC2x&EG9x&EG2x-G&EM05_Series_AT_Commands_Manual_V2.0.pdf) from Quectel. Further undocumented AT commands found by the developer megi, who reverse-engineered parts of the modem and its firmware, can be found on megi’s website [here](https://xnux.eu/devices/feature/modem-pp-reveng.html#toc-un-der-documented-at-commands).

To send AT commands to the modem under Linux, `minicom` or the often-preinstalled `atinout` utility can be used.

_atinout_ example:

    echo "AT+<command here>" | sudo atinout - /dev/ttyUSB2 -

_minicom_ example:

    minicom -D /dev/ttyUSB2

## VoLTE

The PinePhone and PinePhone Pro modem supports VoLTE and comes with a few VoLTE profiles preloaded. Most operating systems try to set the correct profile automatically.

To list the available VoLTE profiles:

```
AT+QMBNCFG="list"

+QMBNCFG: "List",0,1,1,"ROW_Generic_3GPP",0x0501081F,201901141
+QMBNCFG: "List",1,0,0,"VoLTE-ATT",0x0501033C,201909271
+QMBNCFG: "List",2,0,0,"hVoLTE-Verizon",0x05010141,201911251
+QMBNCFG: "List",3,0,0,"Sprint-VoLTE",0x05010205,201908141
+QMBNCFG: "List",4,0,0,"Commercial-TMO_VoLTE",0x05010505,201811231
+QMBNCFG: "List",5,0,0,"Telus-Commercial_VoLTE",0x05800C43,201912031
+QMBNCFG: "List",6,0,0,"Commercial-SBM",0x05011C18,201904021
+QMBNCFG: "List",7,0,0,"Commercial-DT",0x05011F1C,201905311
+QMBNCFG: "List",8,0,0,"Reliance_OpnMkt",0x05011B38,201910161
+QMBNCFG: "List",9,0,0,"TF_Germany_VoLTE",0x05010C1B,201909201
+QMBNCFG: "List",10,0,0,"TF_Spain_VoLTE",0x05010CFA,201909261
+QMBNCFG: "List",11,0,0,"Volte_OpenMkt-Commercial-CMCC",0x05012071,201904281
+QMBNCFG: "List",12,0,0,"OpenMkt-Commercial-CT",0x05011322,201911081
+QMBNCFG: "List",13,0,0,"OpenMkt-Commercial-CU",0x05011505,201807052
```

To select a profile manually, select the best fitting one or a generic one if none fits:

    AT+QMBNCFG="select","ROW_Generic_3GPP"

Then enable Voice over LTE using:

    AT+QCFG="ims",1

And reboot the modem to apply the settings:

    AT+CFUN=1,1

To check the status of VoLTE during a call, the AT command `CLCC` can be used:

```
AT+CLCC

+CLCC: 1,1,0,1,0,"",128
+CLCC: 2,1,0,1,0,"",128
```

In the fourth item of the list, "0" means voice and and "1" means data. If both rows have "1" then the voice call is being carried over VoLTE.

## APN settings

The APN setting is only required for a public Internet connection ("data") on the phone. For tested APN settings and how to apply them see [APN settings](/documentation/PinePhone/Modem/APN_settings).

## Carrier support

The page [Carrier support](/documentation/PinePhone/Modem/Carrier_support/) contains information about the frequency support of different carriers and hints on setting up cellular network connectivity.

## Documents

Detailed information about the modem can be found on the [page of the developer megi](https://xnux.eu/devices/feature/modem-pp.html#toc-modem-on-pinephone), including reverse-engineered parts of the firmware and its functions. There is also a document about using the modem from January 18th 2020 by megi [here](https://megous.com/dl/tmp/modem.txt). A script at the end of the document showcases a way to power off the modem before powering off the phone, which is integrated into most of the available operating systems.

## Firmware update

There is a (nearly) free custom firmware and the stock firmware available for the PinePhone Pro. Both can be updated to a newer version with new features and bug fixes.

### Custom firmware

There is a (nearly) free custom firmware for the PinePhone and PinePhone Pro modem by the developer _biktorgj_, which can be found [here](https://github.com/the-modem-distro/pinephone_modem_sdk).

The custom firmware has various advantages (and zero disadvantages) over the stock firmware, including:

* Signal tracking support with checks against the OpenCelliD database
* Persistent storage is optional and unexpected shutdowns don’t mess up the modem
* A lower energy consumption due to the lower minimum clock frequency
* And many more, see [Features not available on stock firmware](https://github.com/the-modem-distro/pinephone_modem_sdk#features-not-available-on-stock-firmware)

The custom firmware can be flashed using [fwupd](https://wiki.postmarketos.org/wiki/Fwupd#Upgrading_Modem_Firmware_on_the_PinePhone_.28Pro.29) or a [flashing script](https://github.com/the-modem-distro/pinephone_modem_sdk/blob/kirkstone/docs/FLASHING.md).

### Stock firmware

{{< admonition type="tip" >}}
The following instructions are directed towards professional users. It is highly recommend to make sure the update process is not interrupted to prevent the modem from bricking.
{{</ admonition >}}

The stock modem firmware can be updated to a newer version if it is outdated. The firmware version can be checked using the following AT command (at the example of `atinout`, alternatively `minicom` can be used to communicate with the modem too):

```shell
echo 'AT+QGMR' | sudo atinout - /dev/ttyUSB2 -
```

**Pre-update checklist:**

Please make sure all requirements of the checklist are fulfilled. If the update process is interrupted it will lead to a corrupted firmware of the modem, causing it to brick. Recovering a bricked modem is exponentially more complicated and requires the user to boot a special mode by physically bridging test points on the modem.

* The battery needs to be charged sufficiently
* The phone needs to be plugged into a charger
* Deep sleep is recommended to be disabled as it can interrupt the update process
* It is recommended to close all other running applications
* Use common sense while doing the update, don’t do the update while being impaired in any way

To get the latest firmware, clone the repository of user Biktorgj on the phone:

```shell
git clone https://github.com/Biktorgj/quectel_eg25_recovery
```

After cloning the directory, open it with cd:

```shell
cd quectel_eg25_recovery
```

Then run qfirehose, which starts the flashing process:

```shell
sudo ./qfirehose -f ./
```

The modem will automatically reboot after the update process is done. The boot process takes around 30 to 60 seconds. After that it is highly recommended to reboot the device.

## Firmware modifications

See [PineModems](/documentation/General/PineModems) for more information regarding modem bootloader unlocking, building a custom modem firmware and modem recovery.

## GPS / GNSS

The GPS engine in the modem supports mutli-GNSS reception from GPS, GLONASS, BeiDou, Galileo and QZSS independent of a cellular connection. The operation of the GNSS subsystem can be controlled via a separate set of AT commands, or via qmi. The A-GPS data upload uses the file management AT commands, which also have their own manual. These are linked in the documentation section.

As with most smartphones, the PinePhone Pro has a small antenna and has difficulty getting a first fix without assistance data, a cold start can take 15 minutes under good conditions. The _eg25-manager_ is configured to upload A-GPS data by default (see [here](https://gitlab.com/mobian1/eg25-manager/-/merge_requests/15)).

Basic testing of GNSS reception can be done by using the AT command interface (_/dev/ttyUSB2_) from a terminal program like _minicom_ and the data output interface (_/dev/ttyUSB1_) to feed NMEA data into gpsmon or some other program that can parse standard NMEA sentences.

{{< figure src="/documentation/images/Gpsmon_eg25g.png" caption="gpsmon decoding GPS data from _/dev/ttyUSB1_" width="400" >}}

To check if GNSS data output is enabled, you can

```shell
cat /dev/ttyUSB1
```

this should display a stream of NMEA sentences

```
$GPVTG,,T,,M,,N,,K,N*2C
$GPGSA,A,1,,,,,,,,,,,,,,,,*32
$GPGGA,,,,,,0,,,,,,,,*66
```

Further details can be found under [Sensors and navigation](/documentation/PinePhone/Further_information/Sensors_and_navigation).

## Voice mail

The operating systems of the PinePhone Pro may not have support for accessing your voicemail by holding down the 1-key. Carriers might support accessing the voice mail via an external number however.
