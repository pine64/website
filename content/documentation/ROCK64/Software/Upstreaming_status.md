---
title: "Upstreaming status"
draft: false
menu:
  docs:
    title:
    parent: "ROCK64/Software"
    identifier: "ROCK64/Software/Upstreaming_status"
    weight:
---

{{< admonition type="warning" >}}
 The data presented in this section requires updating.
{{</ admonition >}}

| Function  | Status  |     | Component | Notes |
| ---       | ---     | --- | ---       | ---
| Video Output | Linux Mainline | | `rockchipdrm` | With mpv, you'll need to specify something like `mpv --gpu-context=drm --drm-connector=1.HDMI-A-1` to get it to play back on a VT |
| 3D Acceleration | Linux Mainline | Upstream Mesa | `lima` | Very recent version recommended for the best experience. Has weird glitches on HDMI output in weston. |
| Video Decode | Linux Staging | Broken/Not in ffmpeg | `hantro_vpu` and `rockchip_vdec`, using `v4l2-requests` | [Soon to be moved out of staging](https://lore.kernel.org/linux-media/49b1-608d4d00-2b-62afdf80@101971638/), ffmpeg patch set [seemingly abandoned](https://patchwork.ffmpeg.org/project/ffmpeg/patch/20201209202513.27449-3-jonas@kwiboo.se/), does not work on newer kernels. [Git branch with commits](https://github.com/Kwiboo/FFmpeg/commits/v4l2-request-hwaccel-master-stable) |
| Audio | Linux Mainline | | `snd_soc_rockchip_*` |  |
| Power Button | Linux Mainline |  | `rk805_pwrkey` | If your PWR switch does nothing unless held, this may need to be loaded manually with `modprobe` or by putting it in `/etc/modules-load.d/` |
| Analog Video Output | Needs porting | | `rockchip_drm_tve` | Definitely needs some cleanup before it'd be ready for mainline, and needs some dt bindings written. |