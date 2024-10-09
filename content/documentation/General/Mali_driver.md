---
title: "Mali Driver"
draft: false
menu:
  docs:
    title:
    parent: "General"
    identifier: "General/Mali_driver"
    weight: 
---

Here is the good DRM powerpoint presentation by Free Electron: https://free-electrons.com/pub/conferences/2017/kr/ripard-drm/ripard-drm.pdf

Here is the DRM video presentation by Free Electron: https://www.youtube.com/watch?v=LbDOCJcDRoo

## Wayland MALI Driver

* [MALI-400 R6P2 Kernel Mode Setting binary download](http://files.pine64.org/doc/MALI/mali400-r6p2-01rel0-km-003.tar.7z) (1.86MB, MD5 _523276872A9A11D1831ACE42F95DBBB1_)
* [MALI-400 R6P2 WAYLAND 64-bit binary driver and binary download](http://files.pine64.org/doc/MALI/mali400-r6p2-01rel0-um009-wayland.tar.bz2) (179KB, MD5 _1698E8C54BDC6FE0804699F545FFE793_)

## X11 MALI Driver

* [MALI EULA document](http://files.pine64.org/doc/MALI/MALI%20EULA.pdf)
* [MALI-400 64-bit binary driver and binary download](http://files.pine64.org/doc/MALI/x11_pine.tar.bz2) from _pine64.org_ (1.7MB, MD5 _4F56AE6FB793E7D946867942AF58FEAC_)

## X11 Notice

Attached are the implemented driver and library.

* lib_x11_r6p0.tar.bz2：opengles upper layer library；
* r6p0_kernel_driver.tar.bz2：gpu driver code；
* sunxi_arm_video.tar.bz2： dri2 and exa video related accelerator implementation；
* sunxi_drm_0622.tar.bz2：drm driver；

Usage：

Using drm driver not able to coexist with display driver，due to utilize display relate BSP section；Drm driver able to integrate with sunxi_arm_video apply gem during cache and cache refresh，open cache able to increase performance；Drm driver utilize sunxi_tr BSP rotate section，not able to public sharing with sunxi_tr；

Known issue：

Due to rotate hardware not support crop, and majority exa accelerators operate using crop，sunxi_arm_video is reference code (features already verified)，this allow familiar with xorg hardware accelation，
If using web page and character appear vertical strip, this may not related to cache problem and may due to character library. This issue still need to further verified.
