---
title: "Armbian LCD and Camera"
draft: false
menu:
  docs:
    title:
    parent: "SOPINE/Software"
    identifier: "SOPINE/Software/Armbian_LCD_and_camera"
    weight: 99
---

Guide on how to get the camera and the LCD working on the [SOPINE](/documentation/SOPINE) on Armbian.

## LCD

* DD the Armbian SOPINE image to the microSD Card and run on the board
* Login through the terminal
* `vi /boot/armbianEnv.txt` (Change _off_ to _on_): `pine64_lcd=on`
* `vi /etc/modules` (Add following line): `gt9xxf_ts`
* `reboot`

Then the display will be on LCD and not HDMI

## Camera

1. DD the Armbian SOPINE image to the microSD Card and run on the board
2. Login through the terminal
3. Install Ubuntu Xenial Mate with ayufan’s script

       cd ~
       wget https://github.com/longsleep/build-pine64-image/raw/master/simpleimage/platform-scripts/install_desktop.sh
       chmod +x install_desktop.sh
       ./install_desktop.sh mate
4. `vi /boot/armbianEnv.txt` (Set to "s5k4ec" or "ov5640" depending on your camera module)

       camera_type=s5k4ec
5. `vi /etc/modules` (Add the following depending on your camera_type "s5k4ec" or "ov5640" above. Note that "vfe_v4l2" has a small letter 'L'2 not 12)

       s5k4ec
       vfe_v4l2
6. reboot
7. Following https://github.com/avafinger/pine64_camera  (Change "s5k4ec" to "ov5640" depending on your camera module)

       apt-get update
       apt-get upgrade
       apt-get remove --purge guvcview
       apt-get remove --purge libguvcview-1.1-1
       modprobe -r -f vfe_v4l2
       modprobe -r -f s5k4ec
       modprobe s5k4ec
       modprobe vfe_v4l2
       ls /dev/video0
       dmesg | grep OK
       sudo apt-get install libmp3lame-dev libx264-dev libpulse-dev libv4l-dev libsdl1.2-dev libgtk-3-dev portaudio19-dev libpng12-dev libavcodec-dev libavutil-dev libudev-dev libusb-1.0-0-dev libpulse-dev libgsl0-dev libv4l-dev
       cd ~
       wget https://raw.githubusercontent.com/avafinger/pine64_camera/master/libguvcview-1.2-1_2.0.3%2Bdebian-1_arm64.deb
       wget https://raw.githubusercontent.com/avafinger/pine64_camera/master/guvcview_2.0.3%2Bdebian-1_arm64.deb
       dpkg -i libguvcview-1.2-1_2.0.3+debian-1_arm64.deb
       dpkg -i guvcview_2.0.3+debian-1_arm64.deb
8. For testing, use Xenial Mate -> Applications -> Sound & Video -> guvcview
OR command line

       guvcview -d /dev/video0 -x 640x480 -r sdl -f yu12
       guvcview -d /dev/video0 -x 640x480 -r sdl -f nv12
