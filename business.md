---
layout: default
---

## Business Card V2
Jun 2025 - Jul 2025



<div style="display: grid; grid-template-columns: repeat(6, 1fr); gap: 10px; max-width: 240px; margin-bottom: 24px;">
    <img src="assets/img/stm32cubeide-logo.png" alt="STM32CubeIDE" style="width: 28px;">
    <img src="assets/img/BusinessCard/logo.jpg" alt="STM32CubeIDE" style="width: 28px;">
    <img src="assets/img/altium-logo.png" alt="Altium Designer" style="width: 120px; horizontal-align: middle;">
</div>
<h3 style="margin: 10px">Version 2</h3>     
<img src="/assets/img/BusinessCard/BusinessV3.jpg" alt="SAM PCB" style="height: 280px; border-radius: 10px;">
<div style="margin-bottom:20px"></div>

This is the second version, featuring the addition of a MicroSD card slot, reinforced ESD protection and some layout changes. To ensure a continuous GND plane below the USB2.0 signal lines, I designed the board as a 4-layer PCB.

The previous version was powered up and tested. However, some flaws prevented direct access via USB. These issues have been resolved, and the board is expected to trigger computer scripts once the components and firmware are added. 
<div style="margin-bottom:20px"></div>

<h3 style="margin: 10px">Version 1</h3>     
<img src="/assets/img/BusinessCard/BusinessReal.jpeg" alt="SAM PCB" style="height: 280px; border-radius: 10px;">
<div style="margin-bottom:20px"></div>

This is the first version of my very first PCB design. 

<!-- Compared to the first version, I changed the improper PCB layout, moved and added components to address the issues I got from the first testing results. I also added pads around the perimeter, which not only makes it more aesthetically pleasing but also allows me to use it as a programmable dev board. -->
<div style="margin-bottom:20px"></div>
<!-- <img src="/assets/img/BusinessCard/Flashed.mov" alt="SAM PCB" style="height: 280px; border-radius: 10px; margin-top:10px"> -->

<!-- <video style="height: 280px; border-radius: 10px;" autoplay loop muted playsinline>
    <source src="/assets/img/BusinessCard/Flashed.mov" type="video/mov">
    Your browser does not support the video tag.
</video>
<div style="margin-bottom:20px"></div>

I was extremely thrilled to see the board successfully flashed and working. -->

<!-- <div style="margin-top:20px"></div>
### Next Steps
<div style="margin-top:10px"></div>
While the current version functions as a "LED" board, my goal is to turn it into a  controller that I can carry with me and use to program peripheral devices anytime.
The board already supports several communication protocols, including SPI and I2C.
The next step is to have data readings to appear on my host computer. This would involve adding a UART-to-USB chip, the supporting circuitry, and having a USB port for wired communication.
<div style="margin-top:10px"></div> -->
<div style="margin-top:20px"></div>
[Back](./AESN.html)
