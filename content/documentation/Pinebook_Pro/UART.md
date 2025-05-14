---
title: "UART"
draft: false
menu:
  docs:
    title:
    parent: "Pinebook_Pro"
    identifier: "Pinebook_Pro/UART"
    weight: 6
---

{{< figure src="/documentation/images/PinePhone_Serial_Cable.png" caption="This shows signals from the Pinebook Pro’s point of view, so connect the adapter’s RX to ring 1, and TX to the tip. See also the [Pine64 official document](https://files.pine64.org/doc/pinebook/guide/Pinebook_Earphone_Serial_Console_Developer_Guide.pdf) describing this." width="400" >}}

Serial console UART is enabled by flipping the UART switch to the ON position (item 9). To do so, you need to remove the Pinebook Pro’s bottom cover by following the disassembly and reassembly guidelines. The OFF position is towards the touchpad, while the ON position is towards the display hinges.

With the UART switch in the ON position, the console is relayed via the headset jack, on which the audio output is no longer available. Please ensure that you are using a 3.3&nbsp;V UART interface (such as the CH340, FTDI-232R, or PL2303, which are available in both 3.3&nbsp;V and 5&nbsp;V variants) to avoid damage to the RK3399 SoC. Older version of the serial console cable sold by the Pine Store used wrong voltage level and should not be used, see [this forum thread](https://forum.pine64.org/showthread.php?tid=9367) for further information. Recent version of the same cable uses the right voltage level, which can also be checked by measuring the voltage on the TX ring.

Insert the USB plug of the cable into a USB port on the machine that you will use to monitor the Pinebook Pro’s serial console, ensuring that the audio jack of the serial cable is be fully inserted into the Pinebook Pro’s headphone port. Run <code>lsusb</code> in a terminal and you should see a line similar to this:

    Bus 001 Device 058: ID 1a86:7523 QinHeng Electronics HL-340 USB-Serial adapter

Serial console output should now be accessible on the respective machine using a terminal emulator, such as screen, picocom or minicom. Here are a few examples of how to invoke a terminal emuator:

* `screen /dev/ttyUSB0 1500000`
* `picocom /dev/ttyUSB0 -b 1500000`
* `minicom -D /dev/ttyUSB0 -b 1500000`
