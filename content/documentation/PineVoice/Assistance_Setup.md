---
title: "Assistance Setup"
draft: false
menu:
  docs:
    title:
    parent: "PineVoice"
    identifier: "PineVoice/Assistance_Setup"
    weight: 4
---

PineVoice implements the open-source [Wyoming](https://github.com/OHF-Voice/wyoming) protocol for voice assistants. Any assistance application supporting this protocol can communicate with PineVoice.

## Before starting

Complete [WiFi Setup](/documentation/PineVoice/WiFi_Setup/) first. After PineVoice has joined the Wi-Fi network, the center ring LED should slowly breathe in a dim magenta color. This means that PineVoice is connected to Wi-Fi and is waiting for an assistance application to connect through the Wyoming protocol.

## Adding PineVoice to Home Assistant

Home Assistant supports Wyoming Protocol devices through the [Wyoming Protocol integration](https://www.home-assistant.io/integrations/wyoming/). Home Assistant must also have a working Assist voice pipeline. Follow the [Home Assistant Assist](https://www.home-assistant.io/voice_control/) documentation if Assist has not been configured yet.

### Automatic setup

PineVoice supports mDNS auto-discovery. If Home Assistant can see mDNS announcements on the same network, PineVoice should appear automatically as a discovered Wyoming Protocol device.

1. Open Home Assistant.
2. Go to **Settings** -> **Devices & services**.
3. Look for a discovered **Wyoming Protocol** device.
4. Select **Configure**.
5. Follow the on-screen instructions to finish adding PineVoice.

After setup completes, PineVoice should be available as an Assist satellite in Home Assistant.

### Manual setup

If PineVoice does not appear automatically, add it manually through the Wyoming Protocol integration.

1. Find the IP address of PineVoice in the client list of your Wi-Fi router or access point.
2. Open Home Assistant.
3. Go to **Settings** -> **Devices & services**.
4. Select **Add integration**.
5. Search for and select **Wyoming Protocol**.
6. Enter the PineVoice IP address as the host.
7. Enter `10700` as the port.
8. Follow the on-screen instructions to finish adding PineVoice.

### Troubleshooting

{{< admonition type="important" >}}
If following bugs occurs:
* PineVoice is stuck in listening state or Home Assistant does not react to start of Assist - restart PineVoice.
* Device add failed - press Retry / Try Again, or try to add the PineVoice again.

Following bugs are being investigated and will be fixed in update of PineVoice firmware or Home Assistant Core.
{{</ admonition >}}

If Home Assistant cannot connect to PineVoice, check the following:

* PineVoice and Home Assistant are on the same network or VLAN.
* The center ring LED is breathing in dim magenta.
* The IP address entered in Home Assistant is the current IP address of PineVoice.
* TCP port `10700` is reachable from the Home Assistant system.
* mDNS is allowed on the network if using automatic discovery.

For more information, see the Home Assistant [Wyoming Protocol integration](https://www.home-assistant.io/integrations/wyoming/) documentation.

## Testing

After PineVoice is properly added to an assistance application, assist can be triggered in the following ways:

* Say the wake word: "Hey Jarvis"
* Press the center button in the LED ring

After triggering assist, say a command supported by the assistance application. The assistance application should then reply accordingly.
