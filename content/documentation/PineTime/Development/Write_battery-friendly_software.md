---
title: "Write battery-friendly software"
draft: false
menu:
  docs:
    title:
    parent: "PineTime/Development"
    identifier: "PineTime/Development/Write_battery-friendly_software"
    weight: 
---

The key to save battery is to enable only what you need when you need it. nRF52832 has a lot of functionalities allowing you to draw as little current as possible. Here are some tips and tricks:

* Disable / shutdown / put in sleep mode **all devices around the MCU** (display controller, touch controller, external memory).
* Disable all **peripheral inside the MCU** when you don’t need them (SPI, TWI(I²C)). The power management of the NRF52832 is very smart and will completely shut down (power off and disable the clock) the peripheral when the software disables it.
* Put the MCU to sleep as soon and as often as possible. If you are not using a RTOS, this is done by calling _WFE_ (wait for event) instruction. Most of the time, RTOS implement this functionality. For example, FreeRTOS calls it the _tickless mode_: it puts the CPU in sleep mode when no task is planned for execution for more than a specified time, and wakes up as soon as an event is detected or when a task is ready to run.
* Do not use logging (JLink RTT, SWO, semihosting), it uses a lot of power.
* Ensure that the debug circuitry of the MCU is not enabled when you measuring the battery life. The debug peripheral is enabled as soon as you connect a debugger to the device, and **is not automatically disabled**, even if you disconnect the debugger you will have to wait for the battery to go flat to disable to port. The software running in the NRF52832 cannot disable the debug peripheral. To disable the debug circuitry:
  * using `nrfjprog --reset`
  * using JLinkExe: issue the command `writeDP 1 0`
  * or with _OpenOCD_:
    * issue the command `halt`
    * issue the command `flash fillw 0x10001208 0xFFFFFF00 0x01`
    * issue the command `reset`
* You can check if the debug port is enabled using the following code:
```
DWT->CYCCNT ? "NO":"YES"
```
* Read [the errata sheet of the MCU](https://infocenter.nordicsemi.com/pdf/nRF52832_Rev_2_Errata_v1.1.pdf) and apply workarounds if they apply to your software.
