---
title: "Recorder for loud noises"
draft: false
menu:
  docs:
    title:
    parent: "PineCube/Projects"
    identifier: "PineCube/Projects/Recorder_for_loud_noises"
    weight: 
---

The PineCube can be used as a recorder for loud noises. If you have a kernel that has the sound support (see the Sound Control section) then you can use it to make recordings when there is a noise above a certain threshold. The following script is a very simple example that uses the _alsa-utils_ and the _sox_ command to do this. You can use the **noise-stats.txt** file and some noise testing to figure out a good threshold for your camera.

```
 #!/bin/bash

 # Directory where the sound recordings should go
 NOISE_FILE_DIR="/root/noises"

 # Threshold to use with the mean delta to decide to preserve the recording
 MEAN_DELTA_THRESHOLD="0.002"

 # Sample length (in seconds)
 SAMPLE_LENGTH="10"

 while :
 do
      stats=$(arecord -d "$SAMPLE_LENGTH" -f S16_LE > /tmp/sample.wav 2>/dev/null && sox -t .wav /tmp/sample.wav -n stat 2>&1 | grep 'Mean    delta:' | cut -d: -f2 | sed 's/^[ ]*//')
      ts=$(date +%s)
      if (( $(echo "$stats > $MEAN_DELTA_THRESHOLD" | bc -l) )); then
           mv /tmp/sample.wav "$NOISE_FILE_DIR/noise-$ts.wav" # TODO convert to mp3
      fi
      rm -f /tmp/sample.wav
      echo "$ts $stats" >> noise-stats.txt
 done
```
