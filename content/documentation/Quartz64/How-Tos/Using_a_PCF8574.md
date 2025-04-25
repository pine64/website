---
title: "Model A: using a PCF8574"
draft: false
menu:
  docs:
    title:
    parent: "Quartz64/How-Tos"
    identifier: "Quartz64/How-Tos/Using_a_PCF8574"
    weight:
aliases:
  - /wiki/Quartz64_Model_A_using_a_PCF8574
---

In this article, we’ll go over how to hook up a PCF8574 I^2^C I/O extender to a [Quartz64](/documentation/Quartz64) Model A single-board computer, including what device tree changes to make and how to control it.

## Introduction to the PCF8574

The PCF8574 is a fairly ubiquitous GPIO extender that communicates through the I^2^C bus. You can find modules featuring it from many vendors on the usual marketplaces for cheap. It exposes 8 additional GPIO lines, and can be daisy chained to up to 8 devices, giving you an additional 64 GPIO outputs. Combining it with 8 PCF8574A modules will actually push this to a total of 128 GPIO outputs added to your board!

The PCF8574 has a mainline Linux driver, meaning that you do not need to use I^2^C directly to control it; it will just appear as another `/dev/gpiochip_<n>_` device. A lot of Raspberry Pi focused guides for this chip get this precise thing wrong actually, and have the user manually fiddle with the bus.

## Device tree changes

To control the chip, you’ll need to modify your board’s device tree&mdash;a description of its hardware for devices that don’t automatically enumerate&mdash;so that the kernel knows how to load the driver.

There are two ways to edit your device tree. Either you can manually edit the base tree, or use device tree overlays.

### Device tree overlays

On images/distributions which support device tree overlays in their build of u-boot and the device tree blobs, you can very simply write a device tree overlay. This means your base tree can still change as you update your OS, and there’s no manual intervention needed on your part to have your modification be carried forward.

Your overlay will look something like this:

    /dts-v1/;
    /plugin/;

    &i2c3 {
    	#address-cells = <1>;
    	#size-cells = <0>;
    	status = "okay";

    pcf8574: pcf8574@20 {
    	compatible = "nxp,pcf8574";
    	reg = <0x20>;
    	gpio-controller;
    	#gpio-cells = <2>;
    };
    ;

You can compile it with ***dtc -O dtb -o pcf8574.dtbo -@ pcf8574.dts***, assuming your input file is called _pcf8574.dts_.

Installing the overlay depends on your distribution. On Plebian, see [DT_OVERLAYS.md](https://github.com/Plebian-Linux/quartz64-images/blob/main/DT_OVERLAYS.md).

If you want to use constants and includes in your device tree overlay, you’ll need to pass the file through a C preprocessor with the appropriate include directories. For an example of a build system that does this, please consult [the Makefile of CounterPillow’s overlay-examples repository](https://github.com/CounterPillow/overlay-examples/blob/main/Makefile).

### Manually editing the base tree

{{< admonition type="important" >}}
 You will need to install ***dtc*** for this.
{{< /admonition >}}

The easiest way to go about this is to get a copy of the Linux kernel source code from https://kernel.org that matches your kernel version (`uname -a`), as the device tree definitions live in the Linux kernel repository. Technically, device trees should be compatible across kernel versions, but I wouldn’t gamble on it.

Once you have the kernel source, you can use your local configuration: run `zcat /proc/config.gz > .config` inside the top-level directory of the Linux kernel source tree to use your running kernel’s configuration. Then run `make xconfig` (or one of the other non-graphical alternatives, like `nconfig` or `menuconfig`), save the configuration to set any new options to their default values, and then also ensure that `CONFIG_GPIO_PCF857X` (a.k.a. "PCF857x, PCA{85,96}7x, and MAX732[89] I2C GPIO expanders") is either set to "M" or "Y".

In ***arch/arm64/boot/dts/rockchip/rk3566-quartz64-a.dts***, add the following section:

    &i2c3 {
    	status = "okay";

    pcf8574: pcf8574@20 {
    	compatible = "nxp,pcf8574";
    	reg = <0x20>;
    	gpio-controller;
    	#gpio-cells = <2>;
    };
    ;

This lets the kernel know that there’s a PCF8574 hanging off the third I^2^C controller, and is listening on slave address `0x20` (decimal: 32). Be sure to use tabs of size 8 for the indentation, this is the style the kernel uses.

Now run `make dtbs` to compile the device tree. This should give you a ***arch/arm64/boot/dts/rockchip/rk3566-quartz64-a.dt*b*****, which you can then copy into your ***/boot/dtbs/*** as for example **quartz-with-pcf8574.dtb*** or something like that. Then, in your ***extlinux.conf****, either add a new boot label or modify your existing boot labels `FDT` line to point towards this dtb file, with the path being relative to ***/boot** and not to ***/***.

## Daisy chaining

As previously stated, you can hook up multiple of these modules onto the same bus. Here’s how the device tree changes for this will look like:

    &i2c3 {
    	status = "okay";

    pcf8574_1: pcf8574@20 {
    	compatible = "nxp,pcf8574";
    	reg = <0x20>;
    	gpio-controller;
    	#gpio-cells = <2>;
    };

    pcf8574_2: pcf8574@21 {
    	compatible = "nxp,pcf8574";
    	reg = <0x21>;
    	gpio-controller;
    	#gpio-cells = <2>;
    };
    ;

Notice how the labels (the part before the colon) have been differentiated, and the address (number after the @ and number in the reg field) has changed for the second module.

{{< admonition type="note" >}}
 be sure to change the A0, A1 and A2 pins accordingly to set the addresses of the daisy chained modules! For example, for the second module, pull A0 high and leave A1 and A2 low. The address pins work like a binary counter, so 000 -> 001 -> 010 -> 011 -> 100 -> ...
{{< /admonition >}}

## Interrupts

The PCF8574 will pull its ***INT*** pin low when one of its inputs changed. We can use this to generate an interrupt:

    &i2c3 {
    	status = "okay";

    pcf8574: pcf8574@20 {
    	compatible = "nxp,pcf8574";
    	reg = <0x20>;
    	gpio-controller;
    	#gpio-cells = <2>;
    	interrupt-parent = <&gpio0>;
    	interrupts = <RK_PC1 IRQ_TYPE_EDGE_FALLING>;
    	interrupt-controller;
    	#interrupt-cells = <2>;
    };
    ;

In this case, we use GPIO0 Pin C1 (***RK_PC1*** with ***interrupt-parent*** gpio0), a.k.a. UART0_TX, a.k.a. pin 12, as the interrupt pin. (**Note:** You cannot use pin 7 here, as it’s pulled high.)

To know which ***RK_PXX*** and which ***interrupt-parent*** correspond to which pin on the board, consult the schematics.

## Hooking up the module

Hook up SDA to pin number 3 of your board, and SCL to pin number 5. Connect GND to ground, e.g. pin number 9, and VCC to 3.3V, for example pin number 1. If you plan on using interrupts, connect the ***INT*** pin to whichever GPIO you defined as the interrupt pin.

**TODO:** Put photo of hooked up module here.

## Using the GPIOs

Upon booting your board with your modified device tree blob, you should have an additional ***/dev/gpiochip_<n>_*** device, most likely ***/dev/gpiochip5***. You can verify this by running libgpiod’s `gpioinfo` utility, which should now show you an additional GPIO chip with only 8 lines.

    gpiochip5 - 8 lines:
            line   0:      unnamed       unused   input  active-high
            line   1:      unnamed       unused   input  active-high
            line   2:      unnamed       unused   input  active-high
            line   3:      unnamed       unused   input  active-high
            line   4:      unnamed       unused   input  active-high
            line   5:      unnamed       unused   input  active-high
            line   6:      unnamed       unused   input  active-high
            line   7:      unnamed       unused   input  active-high

If you are daisy-chaining the modules, you’ll see an additional gpiochip with 8 lines for each additional module.

### Testing the pins as outputs

To test whether this is working, you can connect an LED between a pin (in this example, 4) of your PCF8574, and ground. Then (assuming your chip number is 5) you can use `sudo gpioset -B pull-down 5 4=0` to turn off the pin and set its bias mode to be pulled down, and use `sudo gpioset 5 4=1` to turn it on and `sudo gpioset 5 4=0` to turn it off. Connecting an LED with no resistor in-line should be fine because the pins deliver like 100mA current at most.

### Programmatically driving the pins

**TODO:** Expand this section with how to control the pins programmatically using libgpiod or whatever.

### Adding a button to send a key code

In this example, we’re adding a button that’s hooked between the input pin 0 and ground, and making it type W whenever it’s pressed.

    / {
    	...

    *keyboard {*
    	*compatible = "gpio-keys";*

    *w_key {*
    	*gpios = <&pcf8574 0 GPIO_ACTIVE_LOW>;*
    	*linux,code = <17>;*
    	*label = "W_KEY";*
    *};*
    };*

    ...
    ;

The label here isn’t the defining bit but the [input event code](https://github.com/torvalds/linux/blob/master/include/uapi/linux/input-event-codes.h) is. 17 is for W. You can also include the header file on top and use the symbol name ***KEY_W***

Note that you will need to have your PCF8574 set up with interrupts for this.
