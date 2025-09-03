---
title: "Camera"
draft: false
menu:
  docs:
    title:
    parent: "PineCube/Tuning"
    identifier: "PineCube/Tuning/Camera"
    weight:
---

## Focus

The focus of the lens can be manually adjusted through rotation. Note that initially, the lens could be tight.

## Low light mode

To get imagery in low-light conditions you can turn on the infrared LED’s to light up the dark area and also enable the IR cut filter using the commands below. Note that these were performed on Armbian using the instructions from here [https://github.com/danielfullmer/pinecube-nixos#enablingdisabling-ir-cut-filter].

```
# Run these as root

# Turn on the IR LED lights (note that you can see a faint red glow from them when it’s low light)
# Turn them off with echo 1 instead (this may be inverted depending on the version of the kernel you have)
echo 0 > /sys/class/leds/pine64\:ir\:led1/brightness
echo 0 > /sys/class/leds/pine64\:ir\:led2/brightness

# Export gpio, set direction
echo 45 > /sys/class/gpio/export
echo out > /sys/class/gpio/gpio45/direction

# Enable IR cut filter (note that you can hear the switching noise)
# Disable with echo 0 instead
echo 1 > /sys/class/gpio/gpio45/value
```

## Camera controls

It is possible to adjust the camera using certain internal camera controls, such as contrast, brightness, saturation and more. These controls can be accessed using the v4l2-ctl tool that is part of the v4l-utils package.

```
# List the current values of the controls
v4l2-ctl -d /dev/v4l-subdev* --list-ctrls

User Controls

    contrast 0x00980901 (int)    : min=0 max=255 step=1 default=0 value=0 flags=slider
    turation 0x00980902 (int)    : min=0 max=255 step=1 default=64 value=64 flags=slider
         hue 0x00980903 (int)    : min=0 max=359 step=1 default=0 value=0 flags=slider
    utomatic 0x0098090c (bool)   : default=1 value=1 flags=update
    _balance 0x0098090e (int)    : min=0 max=4095 step=1 default=0 value=0 flags=inactive, slider
    _balance 0x0098090f (int)    : min=0 max=4095 step=1 default=0 value=0 flags=inactive, slider
    exposure 0x00980911 (int)    : min=0 max=65535 step=1 default=0 value=4 flags=inactive, volatile
    utomatic 0x00980912 (bool)   : default=1 value=1 flags=update
        gain 0x00980913 (int)    : min=0 max=1023 step=1 default=0 value=20 flags=inactive, volatile
    tal_flip 0x00980914 (bool)   : default=0 value=0
    cal_flip 0x00980915 (bool)   : default=0 value=0
    requency 0x00980918 (menu)   : min=0 max=3 default=1 value=1

Camera Controls

    auto_exposure 0x009a0901 (menu)   : min=0 max=1 default=0 value=0 flags=update

Image Processing Controls

    pixel_rate 0x009f0902 (int64)  : min=0 max=2147483647 step=1 default=61430400 value=21001200 flags=read-only
    st_pattern 0x009f0903 (menu)   : min=0 max=4 default=0 value=0

# Set the contrast controls to the maximum value
v4l2-ctl -d /dev/v4l-subdev* --set-ctrl contrast=255
```

You can see which flags can be changed and which ones cannot by looking at the flags. The inactive flag indicates that it is currently disabled. Some of these flags are disabled when other flags are turned on. For example, the gain flag above is inactive because gain_automatic is enabled with a value of "1". 

{{< admonition type="note" >}}
 At the current time the auto_exposure flag is inverted, so a value of "0" means on, while "1" means off. Maybe the auto_exposure flag will get changed someday. You’ll need to turn off auto_exposure (value=1) if you want to manually set the exposure flag.
{{</ admonition >}}
