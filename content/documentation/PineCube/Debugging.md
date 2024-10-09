---
title: "Debugging"
draft: false
menu:
  docs:
    title:
    parent: "PineCube"
    identifier: "PineCube/Debugging"
    weight: 5
---

Camera issues can be debugged with the gstreamer pipeline. If the camera does not appear to work, it is possible to change the `v4l2src` to `videotestsrc` and the gstreamer pipeline will produce a synthetic test image without using the camera hardware.

If the camera is only sensor noise lines over a black or white image, the camera may be in a broken state. When in that state, the following kernel messages were observed:

```
[ 1703.577304] alloc_contig_range: [46100, 464f5) PFNs busy
[ 1703.578570] alloc_contig_range: [46200, 465f5) PFNs busy
[ 1703.596924] alloc_contig_range: [46300, 466f5) PFNs busy
[ 1703.598060] alloc_contig_range: [46400, 467f5) PFNs busy
[ 1703.600480] alloc_contig_range: [46400, 468f5) PFNs busy
[ 1703.601654] alloc_contig_range: [46600, 469f5) PFNs busy
[ 1703.619165] alloc_contig_range: [46100, 464f5) PFNs busy
[ 1703.619528] alloc_contig_range: [46200, 465f5) PFNs busy
[ 1703.619857] alloc_contig_range: [46300, 466f5) PFNs busy
[ 1703.641156] alloc_contig_range: [46100, 464f5) PFNs busy
```
