---
layout: default
---


## Stenokeyboard
Oct 2025 - Dec 2025


<div style="display: grid; grid-template-columns: repeat(6, 1fr); gap: 10px; max-width: 240px; margin-bottom: 24px;">
    <img src="assets/img/stm32cubeide-logo.png" alt="STM32CubeIDE" style="width: 28px;">

    <img src="assets/img/altium-logo.png" alt="Altium Designer" style="width: 120px;">
    <img src="assets/img/usb2.png" alt="UBC Rocket" style="width: 50px;">
</div>

<img src="/assets/img/Steno/StenoPhysical.jpeg" alt="PCB" style="height: 280px; border-radius: 10px;">
<div style="margin-bottom:20px"></div>

The chip STM32F103 includes more than 23 GPIO pins which is enough to connect each switch and so I decided not to use a more complex design with keyboard matrix.

The original approach was to use hardware interrupt lines to detect key presses and record them within a defined time period. However, there was not enough interrupt lines. So instead, I used a loop that polls the GPIO pins and monitors key state changes in software.

This project uses Plover, an open source application that inteprates input from the keyboard. Plover uses the TX Bolt protocol over serial. Each word consists of 4 bytes of data with each bit indicating a pressed key.

 <a href="https://develop-docs.qmk.fm/features/stenography">
Link to the protocol
    <img src="assets/img/link.png" alt="link" style="width: 10px;">

<div style="margin-top:20px"></div>

<video width="400" controls>
  <source src="/assets/img/Steno/StenoWorking.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

<div style="margin-top:20px"></div>

[Back](./AESN.html)
 