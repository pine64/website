---
title: "Audio"
draft: false
menu:
  docs:
    title:
    parent: "Pinebook_Pro/Features"
    identifier: "Pinebook_Pro/Features/Audio"
    weight: 
---

## ALSA configuration

If you do not have the integrated sound card selected as the default, create `/etc/asound.conf` with the following contents:

```
defaults.pcm.!card rockchipes8316c
defaults.ctl.!card rockchipes8316c
```

If you want to enable software mixing (dmix) by default for all ALSA apps (works without Pipewire or PulseAudio), make `/usr/share/alsa/cards/simple-card.conf` file contain this:

```
# default with dmix/dsnoop
simple-card.pcm.default {
	@args [ CARD ]
	@args.CARD {
		type string
	}
	type asym
	playback.pcm {
		type plug
		slave.pcm {
			@func concat
			strings [ "dmix:CARD=" $CARD ",RATE=44100" ]
		}
	}
	capture.pcm {
		type plug
		slave.pcm {
			@func concat
			strings [ "dsnoop:CARD=" $CARD ",RATE=44100" ]
		}
	}
}
```

## Pop/click suppression workaround

If you’re annoyed by loud popping and clicking sounds, which occur a few seconds after the sound playback stops as a result of the components of the audio chain being turned on and off automatically by the Linux kernel, you can execute the following command manually, or automatically on boot using the `tmpfiles.d` systemd feature, for example:

```
echo 50 > /sys/kernel/debug/asoc/rockchip,es8316-codec/dapm_pop_time
```

This is a workaround because it effectively (ab)uses a built-in debugging feature of the Linux kernel’s audio subsystem, and one of the downsides is that a lot of messages are produced in the kernel log whenever the components of the audio chain are turned on and off automatically by the kernel.

## Speaker polarity workaround

On newer Pinebook Pro batches, the inverted built-in speaker polarity issue has been fixed. On these units, the speaker polarity can be made reversed again by the `alsa-ucm-conf` package, which configures ALSA devices continuously. One workaround would be to remove the package, and the speaker polarity will no longer be set incorrectly. However, this also prevents the built-in speakers from being muted when an output device is plugged into the aux port.
Another workaround is to edit file `/usr/share/alsa/ucm2/Rockchip/es8316/HiFi.conf` and change all instances of `R Invert` to `Normal`. This is a workaround because it’s likely to be overwritten and lost if the `alsa-ucm-conf` package is updated.
