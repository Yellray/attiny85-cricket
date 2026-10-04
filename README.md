# ATtiny85 Cricket

This project implements a simple audio generator on an ATtiny85 using Timer0 hardware PWM. The firmware drives a piezo output with dynamically modified duty cycles and timing patterns to produce non-periodic, insect-like audio. After a pattern is executed, another random value between 25 and 35 is generated to determine the idle time in minutes, during which the device remains inactive. After this period, the device generates a new sound pattern, and the process repeats continuously.

<p align="center">
  <img src="documentation/pcb-view.png" alt="PCB view" width="500">
</p>

---

> **Note:** The circuit is built around an ATtiny85 microcontroller, which is not particularly well suited for this application. The device is powered directly from a coin cell and draws approximately 6 mA on average, resulting in a theoretical battery life of around 1.5 days.
>
>Using sleep modes together with an interrupt-based wake-up mechanism would significantly reduce power consumption. This would allow the ATtiny85 to shut down almost completely during the long idle periods, while still being able to wake up when needed.
>
>Since this was a fun weekend project, the firmware in this repository does not currently implement this power-saving feature.
