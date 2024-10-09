---
title: "Hardware wishlist"
draft: false
menu:
  docs:
    title:
    parent: "PineTime/Development"
    identifier: "PineTime/Development/Hardware_wishlist"
    weight: 
---

This page contains a list of things people wish PineTime did differently

## Hardware

* Other display technology could be explored.
  * E-ink
    * Still images require no power to maintain
    **[//en.Wikipedia.org/wiki/Transflective_liquid-crystal_display A transflective LCD]
    * Increased readability in bright daylight
    **[//en.wikipedia.org/wiki/OLED OLED]
    * Self-emissive display (pixels emit their own light)
    * Allows for lower power usage with mostly black screens
    * Allows for low power visual notifications (imagine an always-on small red square in the corner to indicate a notification)
* Touchscreen with configurable sensitivity
  * Ideal for gloved fingers and water droplet resistance
  * Preferably it should remain capacitive, as a resistive touchscreen would have too many trade-offs.
* A slightly bigger 256×256 pixel display
  * This resolution is preferable for its binary alignment for low-level simplicity
  * It has the property that its X and Y coordinates are each addressable with a single byte, with no bounds checking
  * Its total number of pixels is a power of 2 (65536), and each pixel is addressable with exactly 2 bytes.
  * The [IBNIZ (Ideally Bare Numeric Impression giZmo) virtual machine](http://Pelulamu.net/ibniz), designed for minimalist demoscene graphics, has chosen 256×256 for its virtual display specifically for code efficiency.
    * If PineTime also chose 256×256 then it would be a target platform for unclipped IBNIZ demoscene programmes, which would be really fun to play around with on one’s wrist!
* Full screen refresh is very slow
  * A full 16-bit redraw on the display takes at worst 120ms, which is 8Hz
  * Modest optimization is possible by adopting 12-bit color
  * A smooth scrolling/usage/animation experience would be 30Hz minimum, preferably 60hz
  * Display redraw is currently bottlenecked by the nRF52832 maximum SPI clock (8MHz).
  * The nRF528(33/40) has one high speed SPI master which supports 32MHz, still well below the ST7789 maximum
  * Parallel data transfer could be an option, but using more GPIOs (which don’t look available)
* Some sort of scroll wheel (and possibly button combination) would be nice as an additional input method
* Changed GPIO assignment so more functionality is available (i.e. NFC and VSYNC)
* Wireless charging, or Qi Charging capability
* Different MCU with more RAM and ROM, higher clock
  * nRF5840 update
    * 32MHz HS SPI, QuadSPI
    * CryptoCell + Secure Key Storage
    * More RAM, a coprocessor
    * The possibility to expose USB through power pins
  * Ox64/BL808
    * Open hardware RISC-V based MCU
    * Significant jump in performance
    * Significant jump in memory and storage, allowing for more features and better UI’s
  * Possibly a pre-certified MCU module with a ceramic antenna
* Version without sensors but maybe bigger battery
* Pins on the programmer connector to allow UART while developing (currently there is a TX test point on PCB). (Note: There’s ARM SemiHosting, ITM and Segger RTT that fulfil this purpose for most)
* Connect SDO of ST7889 LCD controller to MCU
  * Allows MCU to execute READ commands
  * Possibility of leveraging ST7889 RAM to save MCU RAM?
* LCD must be centered on case. Currently is not and watchfaces seems different when clock is put on the other wrist.
* A NFC antenna around the case, connected to the NFC pins.
* Used sensors should be NDA-free and preferably also blob-free for easier development
  * Possibly replace BMA421 accelerometer with a magnetometer + gyroscope + accelerometer combination
    * The BMA421 doesn’t have a public datasheet
    * Special attention should be paid to advanced features, such as step counting integration or flick detection.
* PineTime SoC could support USB or have a FTDI chip with the relevant pins exposed
  * It could allow flashing a sealed device, just like Arduinos work.
  * Alternatively, an USB-C port could be added that provides these features.
* A bigger pulldown resistor for the power button
  * 100k still leaks a noticeable amount of power when the button is always on.
* Ceramic Bluetooth antenna for better signal reception
* An external RTC circuit
  * Allows the main MCU go to deep-sleep while retaining time.
  * Allows time retention through MCU reset.
* Ultra low quiescent current PMIC
  * In theory could provide a hard reset capability based on button press
  * Better deep sleep/shipping/storage/off lifetime
    * A nano-power system timer IC could in theory provide a RTC, MOSFET-controlled deep sleep, watchdog timer and button-controlled reset
  * Built-in "fuel gauge" for better estimation of battery capacity
* Improved haptic or audible feedback
  * E.g. small Piezo buzzer
  * Use case would be for very short beeps (think old-school casio watch) as notification.
  * Of course developers can PWM other frequency to make it sing, but piezos tend to be shrill.
* A built-in microphone
  * Would allow phone call functionality to be built into the watch.
  * Could potentially allow for speech recognition for text input.
  * Direct access to the external (flash) storage
  * Only a small jump in price
