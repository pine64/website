---
title: "Microphones"
draft: false
menu:
  docs:
    title:
    parent: "Pinebook_Pro/Features"
    identifier: "Pinebook_Pro/Features/Microphones"
    weight: 
---

While it has been said that some Pinebook Pro units contain only one microphone despite having two labeled microphone holes on the outer casing, other units do indeed contain two microphones. It is presently unclear which batches have either configuration. Units from the initial community batch of 1000 units (following the initial 100) are believed to contain two, populating both labeled holes.

The wires leading to both microphones connect to the mainboard with a small white plastic connector, located directly adjacent to the ribbon cable attachment point for the keyboard interface.

## Built-in microphones not working

If pavucontrol input doesn’t show microphone activity try changing the privacy switches. If the switches are in the correct place and microphone input isn’t working you can run `alsamixer` from the command line, hit F6 and select the `es8316`, hit F4 to get to the capture screen, select the bar labeled ADC, increase the gain to 0&nbsp;dB, change the audio profile in pavucontrol to another one with input. Additionally you may want to modify ADC PGA to get the levels to where you want them. If that still hasn’t fixed it you may want to check that the microphone connector is plugged in.

## External wired microphone not working

If you connect a headset with a microphone, you might need to open `alsamixer`, change card to `es8316`, and change option `Differential Mux` from `lin1-rin1` to `lin2-rin2`.
