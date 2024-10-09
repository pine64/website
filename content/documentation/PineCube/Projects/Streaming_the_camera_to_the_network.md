---
title: "Streaming the camera to the network"
draft: false
menu:
  docs:
    title:
    parent: "PineCube/Projects"
    identifier: "PineCube/Projects/Streaming_the_camera_to_the_network"
    weight: 
---

In this section we document a variety of ways to stream video to the network from the PineCube. Unless specified otherwise, all of these examples have been tested on Ubuntu groovy (20.10). See [this small project for the PineCube](https://github.com/ioerror/pinecube) for easy to use programs tuned for the PineCube.

In the examples which use h264, we are currently encoding using the x264 library which is not very fast on this CPU. The SoC in the PineCube does have a hardware h264 encoder, which the authors of these examples have so far not tried to use. It appears that https://github.com/gtalusan/gst-plugin-cedar might provide easy access to it, however. Please update this wiki if you find out how to use the hardware encoder! 

## gstreamer: h264 HLS

HLS (HTTP Live Streaming) has the advantage that it is easy to play in any modern web browser, including Android and iPhone devices, and that it is easy to put an HTTP caching proxy in front of it to scale to many viewers. It has the disadvantages of adding (at minimum) several seconds of latency, and of requiring an h264 encoder (which we have in hardware, but haven’t figured out how to use yet, so, we’re stuck with the slow software one).

HLS segments a video stream into small chunks which are stored as .ts (MPEG Transport Stream) files, and (re)writes a playlist.m3u8 file which clients constantly refresh to discover which .ts files they should download. We use a tmpfs file system to avoid needing to write these files to the microSD card in the PineCube. Besides the program which writes the .ts and .m3u8 files (gst-launch-1.0, in our case), we’ll also need a very basic web page in tmpfs and a webserver to serve the files.

Create an hls directory to be shared in the existing tmpfs file system that is mounted at /dev/shm:

`mkdir /dev/shm/hls/`

Create an index.html and optionally a favicon.ico or even a set of icons, and then put the files into the /dev/shm/hls directory. An example index.html that works is available in the Getting Started section of the [README](https://github.com/video-dev/hls.js/#getting-started) for [hls.js](https://github.com/video-dev/hls.js/). We recommend downloading the hls.js file and editing the example index.html to serve your local copy of it instead of fetching it from a CDN. This file provides HLS playback capabilities in browsers which don’t natively support it (which is most browsers aside from the iPhone).

In one terminal, run the camera capture pipeline:

```
cd /dev/shm/hls/ &&
media-ctl --set-v4l2 '"ov5640 1-003c":0[fmt:UYVY8_2X8/240x320@1/15]' &&
gst-launch-1.0 v4l2src ! video/x-raw,width=320,height=240,format=UYVY,framerate=15/1 ! decodebin ! videoconvert ! video/x-raw,format=I420 ! clockoverlay ! timeoverlay valignment=bottom ! x264enc speed-preset=ultrafast tune=zerolatency ! mpegtsmux ! hlssink target-duration=1 playlist-length=2 max-files=3
```

Alternatively it is possible to capture at a higher resolution:

```
media-ctl --set-v4l2 '"ov5640 1-003c":0[fmt:UYVY8_2X8/1920x1080@1/15]'
cd /dev/shm/hls/ && gst-launch-1.0 v4l2src ! video/x-raw,width=1920,height=1080,format=UYVY,framerate=15/1 ! decodebin ! videoconvert ! video/x-raw,format=I420 ! clockoverlay ! timeoverlay valignment=bottom ! x264enc speed-preset=ultrafast tune=zerolatency ! mpegtsmux ! hlssink target-duration=1 playlist-length=2 max-files=3
```

In another, run a simple single threaded webserver which will serve html, javascript, and HLS to web clients:

```
cd /dev/shm/hls/ && python3 -m http.server
```

Alternately, install a more efficient web server (`apt install nginx`) and set the server root for the default configuration to be /dev/shm/hls. This will run on port 80 rather than the python3 server which defaults to port 8000.

It should be possible to view the HLS stream directly in a web browser by visiting [http://pinecube:8000/](http://pinecube:8000/) if _pinecube_ is the correct hostname and the name correctly resolves.

You can also view the HLS stream with VLC: `vlc http://pinecube:8000/playlist.m3u8`

Or with gst-play-1.0: `gst-play-1.0 http://pinecube:8000/playlist.m3u8` (or with mpv, ffplay, etc)

To find out about other options you can configure in the `hlssink` gstreamer element, you can run `gst-inspect-1.0 hlssink`.

It is worth noting here that the `hlssink` element in GStreamer is not widely used in production environments. It is handy for testing, but for real-world free-software HLS live streaming deployments the standard tool today (January 2021) is nginx’s RTMP module which can be used with ffmpeg to produce "adaptive streams" which are re-encoded at varying quality levels. You can send data to an nginx-rtmp server from a gstreamer pipeline using the `rtmpsink` element. It is also worth noting that gstreamer has a new `hlssink2` element which we have not tested; perhaps in the future it will even have a webserver! 

## v4l2rtspserver: h264 RTSP

Install dependencies:

    apt install -y cmake gstreamer1.0-plugins-bad gstreamer1.0-tools \
    gstreamer1.0-plugins-good v4l-utils gstreamer1.0-alsa alsa-utils libpango1.0-0 \
    libpango1.0-dev gstreamer1.0-plugins-base gstreamer1.0-x x264 \
    gstreamer1.0-plugins-{good,bad,ugly} liblivemedia-dev liblog4cpp5-dev \
    libasound2-dev vlc libssl-dev iotop libasound2-dev  liblog4cpp5-dev \
    liblivemedia-dev autoconf automake libtool v4l2loopback-dkms liblog4cpp5-dev \
    libvpx-dev libx264-dev libjpeg-dev libx265-dev linux-headers-dev-sunxi;

Install kernel source and build v4l2loopback module:

    apt install linux-source-5.11.3-dev-sunxi64  #Adjust kernel version number to match current installation with "uname -r"
    cd /usr/src/v4l2loopback-0.12.3; make && make install && depmod -a

Build required v4l2 software:

    git clone --recursive https://github.com/mpromonet/v4l2tools && cd v4l2tools && make && make install;
    git clone --recursive https://github.com/mpromonet/v4l2rtspserver && cd v4l2rtspserver && cmake -D LIVE555URL=https://download.videolan.org/pub/contrib/live555/live.2020.08.19.tar.gz . && make && make install;

Running the camera:

    media-ctl --set-v4l2 '"ov5640 1-003c":0[fmt:UYVY8_2X8/640x480@1/30]';
    modprobe v4l2loopback video_nr=10 debug=2;
    v4l2compress -fH264  -w -vv /dev/video0 /dev/video10 &
    v4l2rtspserver -v -S -W 640 -H 480 -F 10 -b /usr/local/share/v4l2rtspserver/ /dev/video10

Note that you might get an error when running media-ctl indicating that the resource is busy. This could be because of the motion program that runs on the stock OS installation. Check and terminate any running /usr/bin/motion processes before running the above steps.

The v4l2compress/v4l2rtspserver method of streaming the camera uses around ~45-50% of the CPU for compression of the stream into H264 (640x480@7fps) and around 1-2% of the CPU for serving the HLS stream. Total system RAM used is roughly 64MB and the load average is ~0.4-~0.5 when idle, and ~0.51-~0.60 with one HLS client streaming the camera.

You’ll probably see about a 2-3s lag with this approach, possibly due to the H264 compression and the lack of hardware acceleration at the moment.

## gstreamer: JPEG RTSP

GStreamer’s RTSP server isn’t an element you can use with gst-launch, but rather a library. We failed to build its example program, so instead used this very small 3rd party tool which is based on it: https://github.com/sfalexrog/gst-rtsp-launch/

After building gst-rtsp-launch (which is relatively simple on Ubuntu groovy; just `apt install libgstreamer1.0-dev libgstrtspserver-1.0-dev` first), you can read JPEG data directly from the camera and stream it via RTSP: `media-ctl --set-v4l2 '"ov5640 1-003c":0[fmt:JPEG_1X8/1280x720]' && gst-rtsp-launch 'v4l2src ! image/jpeg,width=1280,height=720 ! rtpjpegpay name=pay0'`

This stream can be played using `vlc rtsp://pinecube.local:8554/video` or mpv, ffmpeg, gst-play-1.0, etc. If you increase the resolution to 1920x1080, mpv and gst-play can still play it, but VLC will complain `The total received frame size exceeds the client’s buffer size (2000000). 73602 bytes of trailing data will be dropped! ` if you don’t tell it to increase its buffer size with `--rtsp-frame-buffer-size=300000`

## gstreamer: h264 RTSP

Left as an exercise to the reader (please update the wiki). Hint: involves bits from the HLS and the JPEG RTSP examples above, but needs a `rtph264pay name=pay0` element.

## gstreamer: JPEG RTP UDP

Configure camera: `media-ctl --set-v4l2 '"ov5640 1-003c":0[fmt:JPEG_1X8/1920x1080]'`

Transmit with: `gst-launch-1.0 v4l2src ! image/jpeg,width=1920,height=1080 ! rtpjpegpay name=pay0 ! udpsink host=$client_ip port=8000`

Receive with: `gst-launch-1.0 udpsrc port=8000 !  application/x-rtp, encoding-name=JPEG,payload=26 !  rtpjpegdepay !  jpegdec !  autovideosink`

Note that the sender must specify the recipient’s IP address in place of `$client_ip`; this can actually be a multicast address allowing for many receivers! (You’ll need to specify a valid multicast address in the receivers' pipeline also; see `gst-inspect-1.0 udpsrc` and `gst-inspect-1.0 udpsink` for details.)

## gstreamer: JPEG RTP TCP

Configure camera: `media-ctl --set-v4l2 '"ov5640 1-003c":0[fmt:JPEG_1X8/1920x1080]'`

Transmit with: `gst-launch-1.0 v4l2src ! image/jpeg,width=1920,height=1080 ! rtpjpegpay name=pay0 ! rtpstreampay ! tcpserversink host=0.0.0.0 port=1234`

Receive with: `gst-launch-1.0 tcpclientsrc host=pinecube.local port=1234 ! application/x-rtp-stream,encoding-name=JPEG ! rtpstreamdepay ! application/x-rtp, media=video, encoding-name=JPEG ! rtpjpegdepay !  jpegdec !  autovideosink`

## gstreamer and socat: MJPEG HTTP server

This rather ridiculous method uses bash, socat, and gstreamer to implement an HTTP-ish server which will serve your video as an MJPEG stream which is playable in browsers.

This approach has the advantage of being relatively low latency (under a second), browser-compatible, and not needing to reencode anything on the CPU (it gets JPEG data from the camera itself). Compared to HLS, it has the disadvantages that MJPEG requires more bandwidth than h264 for similar quality, pause and seek are not possible, stalled connections cannot jump ahead when they are unstalled, and, in the case of this primitive implementation, it only supports one viewer at a time (Though the RTSP examples on this page perform very poorly with multiple viewers).

Gstreamer can almost do this by itself, as it has a multipartmux element which produces the headers which precede each frame. But sadly, despite various forum posts lamenting the lack of one over the last 12+ years, as of the end of the 50th year of the UNIX era (aka 2020), somehow nobody has yet gotten a webserver element merged in to gstreamer (which is necessary to produce the HTTP response, which is required for browsers other than firefox to play it). So, here is an absolutely minimal "webserver" which will get MJPEG displaying in a (single) browser.

Create a file called `mjpeg-response.sh`:

    #! /bin/bash
    media-ctl --set-v4l2 '"ov5640 1-003c":0[fmt:JPEG_1X8/1920x1080]'
    b="--duct_tape_boundary"
    echo -en "HTTP/1.1 200 OK\r\nContent-type: multipart/x-mixed-replace;boundary=$b\r\n\r\n"
    gst-launch-1.0 v4l2src ! image/jpeg,width=1920,height=1080 ! multipartmux boundary=$b ! fdsink fd=2 2>&1 >/dev/null

Make it executable: `chmod +x mjpeg-response.sh`

Run the server: `socat TCP-LISTEN:8080,reuseaddr,fork EXEC:./mjpeg-response.sh`

And browse to http://pinecube.local:8080/ in your browser.

## virtual web camera: gstreamer, mjpeg, udp rtp unicast

It’s possible to set up the PineCube as a virtual camera video device (Video 4 Linux) so that you can use it with video conferencing software, such as Jitsi Meet. Note that this has fairly minimal (&lt;1s) lag when tested on a wired 1Gb Ethernet network connection and the frame rate is passable. MJPEG is very wasteful in terms of network resources, so this is something to keep in mind. The following instructions assume Debian Linux (Bullseye) as your desktop machine, but could work with other Linux distributions too. It’s possible that someday a similar system could work with Mac OS X provided that someone writes a gstreamer plugin that exposes a Mac OS Core Media DAL device as a virtual webcam, like they did [here](https://github.com/johnboiles/obs-mac-virtualcam) for OBS.

First, you will need to set up the pinecube with gstreamer much like the above gstreamer, but in 1280x720 resolution. Also, you will be streaming to the desktop machine using UDP, with IP address represented by $desktop below at UDP port 8000.

    media-ctl --set-v4l2 '"ov5640 1-003c":0[fmt:JPEG_1X8/1280x720]'
    gst-launch-1.0 v4l2src device=/dev/video0 ! image/jpeg,width=1280,height=720,framerate=30/1 ! rtpjpegpay name=pay0 ! udpsink host=$desktop port=8000

On your desktop machine, you will need to install the gstreamer suite and the special v4l2loopback kernel module to bring the mjpeg stream to the Video 4 Linux device /dev/video10.

    sudo apt install gstreamer1.0-tools gstreamer1.0-plugins-base gstreamer1.0-plugins-good gstreamer1.0-plugins-bad gstreamer1.0-plugins-ugly v4l2loopback-dkms
    sudo modprobe v4l2loopback video_nr=10 max_buffers=32 exclusive_caps=1 # Creates /dev/video10 as a virtual v4l2 device, allocates increased buffers and exposes exclusive capabilities for chromium to find the video device
    gst-launch-1.0 udpsrc port=8000 ! application/x-rtp, encoding-name=JPEG,payload=26,framerate=30/1 ! rtpjpegdepay ! jpegdec ! video/x-raw, format=I420, width=1280, height=720 ! autovideoconvert ! v4l2sink device=/dev/video10

The most common error found when launching the gstreamer pipeline above is the following error message, which seems to happen when the [max_buffers aren’t set](https://github.com/umlaeute/v4l2loopback/issues/174) on the v4l2loopback module (see above), or if there is a v4l client (vlc, chromium) already connected to /dev/video10 when starting the pipeline. There does seem to be a small level of instability in this stack that could be improved.

    gstbasesrc.c(3055): gst_base_src_loop (): /GstPipeline:pipeline0/GstUDPSrc:udpsrc0:
    streaming stopped, reason not-negotiated (-4)

Now that you have /dev/video10 hooked into the gstreamer pipeline you can then connect to it using VLC. VLC is a good local test that things are working. You can view the stream like this. Note that you could do the same thing with mpv/ffmpeg, but there are [problems](https://www.raspberrypi.org/forums/viewtopic.php?t=270023) currently.

    vlc v4l2:///dev/video10

Be sure to disconnect VLC before trying to use the virtual web camera with chromium. Launch chromium and go to a web conference like [jitsi](https://meet.jit.si). When it prompts you for the camera pick the "Dummy Video Device..." and it should be much like what you see in VLC. Note that Firefox isn’t really working at this moment and the symptoms appear very similar to the problem with mpv/ffmpeg mentioned above, ie. when they connect to the camera they show only the first frame and then drop. It’s unclear whether the bug is in gstreamer, v4l, or ffmpeg (or somewhere in these instructions).
