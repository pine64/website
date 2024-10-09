---
title: "Security camera with Motion"
draft: false
menu:
  docs:
    title:
    parent: "PineCube/Projects"
    identifier: "PineCube/Projects/Security_camera_with_Motion"
    weight: 
---

It’s possible to use the PineCube as an inside or outside security camera using [motion](https://motion-project.github.io/index.html). For outside, you’ll need an enclosure with a transparent dome to protect from the weather. One suggestion is to mount the camera with the lens as close as possible to the dome to avoid reflection.

The Motion package can be installed in a variety of Linux flavors. There’s a package in the standard Ubuntu and Debian repositories and works with Armbian. It provides a very simple web interface for live viewing of the camera feed and also has motion trigger capabilities to store either still pictures or in later versions videos. Note that it is also possible to build hooks to automatically process or upload those recordings.

To get things working quickly with motion you can set the following in the /etc/motion/motion.conf and start it with "sudo /etc/init.d/motion start"

    v4l2_palette 14 # UYVY8
    width 640
    height 480
    framerate 15

This mode and resolution works fine with Motion and works well with video motion capture (Motion version >= 4.2.2). However, if you want different modes and resolutions you’ll need to set the camera to those modes with the media-ctl tool that comes with the v4l-utils package. That will need to be set before the motion service starts. A simple method to ensure that it gets set before motion starts every time, even across reboots, is to make a small modification to the /lib/systemd/system/motion.service

```
[Service]
Type=simple
User=motion
ExecStartPre=/usr/bin/media-ctl --set-v4l2 '"ov5640 1-003c":0[fmt:UYVY8_2X8/1280x720@1/15]' # <=- Add this line here with the mode that the camera will use
ExecStart=/usr/bin/motion
```

Note that you must modify /etc/motion/motion.conf to match the v4l2_palette, width, height and framerate to match the mode you set with media-ctl. See the [Motion documentation](https://motion-project.github.io/motion_config.html#v4l2_palette) to match the v4l2_palette to the mode. Here are a list of modes that have been tried so far.

```
UYVY8_2X8/640x480@1/30
UYVY8_2X8/640x480@1/15
UYVY8_2X8/1280x720@1/15  # This one seems to be fine for live viewing, but causes performance problems when using Motion to capture videos
JPEG_1X8/1280x720@1/15
```
