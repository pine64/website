---
title: "Device Tree Overlays on Mainline"
draft: false
menu:
  docs:
    title:
    parent: "ROCKPro64/Software"
    identifier: "ROCKPro64/Software/Device_Tree_Overlays_on_Mainline"
    weight: 
---

If your U-Boot has been compiled with `CONFIG_OF_LIBFDT_OVERLAY` (which Manjaro’s is), adding device tree overlays the mainline way is very simple and easy.

## Writing Your Device Tree Overlay

First off, you’ll have to write a device tree overlay. In this example, we’ll enable the ROCKPro64’s I2C bus that’s exposed to the pin headers, and declare that a PCF8574 GPIO extender is hanging off it.

    /dts-v1/;
    /plugin/;

    &i2c8 {
    	status = "okay";
    	#address-cells = <1>;
    	#size-cells = <0>;

    pcf8574: pcf8574@20 {
    	compatible = "nxp,pcf8574";
    	reg = <0x20>;
    	gpio-controller;
    	#gpio-cells = <2>;
    };
    ;

We’ll go through this file line by line.

* `/dts-v1/;` specifies that this file is a DTS file.
* `/plugin/;` specifies that this is not just a regular device tree source file, but an overlay.
* `&i2c8 {` references the `i2c8` node in the device tree we’re applying on top of, meaning we’re going to modify this specific part of it.
* `status = "okay";` enables the `i2c8` node. It’s set to "disabled" in the tree we’re applying on top of, specifying the property like this overrides it.
* `#address-cells = <1>;` is already set in the base tree, but since the compiler doesn’t know what the base tree is, it’ll yell at us if we don’t set this.
* `#size-cells = <0>;` same as above.
* `pcf8574: pcf8574@20 {` adds a child node labelled `pcf8574` to the i2c8 node, which is a PCF8574 controller at address ***0x20***.
* `compatible = "nxp,pcf8574";` the compatible string of the node, letting the kernel know what driver it needs to load for it.
* `reg = <0x20>;` the I2C address the device is listening on, in hexadecimal.
* `gpio-controller;` declares that this node is a GPIO controller.
* `#gpio-cells = <2>;` required for GPIO controllers.

Assuming we’ve saved this as ***pcf8574.dts***, we can compile it as follows:

    dtc -O dtb -o pcf8574.dtbo -@ pcf8574.dts

This creates a compiled ***pcf8574.dtbo*** from the ***pcf8574.dts*** input file, and with `-@` we preserve the labels of nodes, which in turn allows something to more easily overlay onto this overlay.

## Loading It

Next, copy your compiled device tree overlay file&mdash;in the previous example ***pcf8574.dtbo****&mdash;somewhere into your ***/boot***, for example ***/boot/dtbs/overlays/**.

Then we modify ***/boot/extlinux/extlinux.conf*** and add the line emphasised in bold to it:

    LABEL Manjaro ARM
    KERNEL /Image
    FDT /dtbs/rockchip/rk3399-rockpro64.dtb
    *FDTOVERLAYS /dtbs/overlays/pcf8574.dtbo*
    APPEND initrd=/initramfs-linux.img console=ttyS2,1500000 root=LABEL=ROOT_MNJRO rw rootwait quiet splash plymouth.ignore-serial-consoles

To specify multiple overlays, simply separate them with space on the same line.

Now after a reboot, the device tree overlay file should be applied, and your kernel will see the new device. You can confirm this by dumping the device tree the kernel uses, and grepping it for whatever you added:

    dtc -I fs /sys/firmware/devicetree/base | grep -A4 'pcf8574'

## Further Reading

* [Linux Kernel Documentation - Devicetree Overlay Notes](https://www.kernel.org/doc/html/latest/devicetree/overlay-notes.html)
* [Embedded Linux Wiki - Device Tree Usage](https://elinux.org/Device_Tree_Usage)
* [CounterPillow’s overlay-examples repository](https://github.com/CounterPillow/overlay-examples)
