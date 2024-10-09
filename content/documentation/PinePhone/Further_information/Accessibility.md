---
title: "Accessibility"
draft: false
menu:
  docs:
    title:
    parent: "PinePhone/Further_information"
    identifier: "PinePhone/Further_information/Accessibility"
    weight: 
---

Although most accessibility support for the [PinePhone](/documentation/PinePhone) and [PinePhone Pro](/documentation/PinePhone_Pro) is implemented in software, the underlying hardware is still relevant. This page discusses some issues and options.

## Input

### Braille

Various portable devices, such as Apple’s iPhone, support braille input.
This uses multi-touch capability on the device’s capacitative touch screen.
The gating factors for this input mode are the dimensions of the screen
and the number of contact points that can be distinguished.

The PinePhone screen has 1440 × 720 pixel resolution and measures 5.95" diagonally.
Assuming that the pixels are square, the screen dimensions should be about 2.68" by 5.37".
This should provide plenty of room for four fingertips on each of the long sides.
Indeed, there is a bit of space left over for control functions, etc.

### Keyboard

The PinePhone can support either Bluetooth or USB keyboards.
So, a device such as the
[Jelly Comb Foldable Bluetooth Keyboard B003](https://www.jellycomb.com/Foldable-Bluetooth-Keyboard-B003-p798959.html)
might be a reasonable input device.

### Speech

The PinePhone should be able to accept speech input using either Bluetooth or its built-in microphone.
According to
[this page](https://www.seeedstudio.com/blog/2020/01/23/offline-speech-recognition-on-raspberry-pi-4-with-respeaker),
Mozilla’s DeepSpeech ASR (automatic speech recognition) engine works pretty well on a Raspberry Pi 4,
using only a single core.
Assuming that the PinePhone’s more limited (2 or 3 GB) RAM isn’t a constraint,
the phone should be able to produce similar results.

## Output

### Speech

The PinePhone’s processor should have plenty of capacity to generate clear speech.
This can be output using either the 3.5 mm audio jack or a Bluetooth connection.

## See also

* [postmarketOS wiki: Accessibility](https://wiki.postmarketos.org/wiki/Accessibility)
