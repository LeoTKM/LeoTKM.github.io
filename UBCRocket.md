---
layout: default
---

## UBC Rocket
*May 2025 - Aug 2025*


<div style="display: grid; grid-template-columns: repeat(6, 1fr); gap: 10px; max-width: 240px; margin-bottom: 24px;">
    <img src="assets/img/UBC/UBCRocketsLogo.png" alt="UBC Rocket" style="width: 30px;">
</div>

I had four awesome months at UBC Rocket, where I participated in two projects and a test launch in Oregon. I was responsible for soldering components at first and gradually took on some harder tasks such as PCB design, and firmware programming. 

Over the following weeks, I used Altium to create my own boards, including one made for UBC <a href="./sam-m10q.html">SAM M10Q GNSS Module</a>. I programmed and tested it using a STM32 Nucleo board via UART and it was successfully flown with the rocket at the 2025 Launch Canada competition.
<div style="margin-bottom: 30px;"></div>

### Soldering
Soldered Radio, BMS, Buck Converter, GNSS Module and Vector Thrust boards.

A little technique for soldering a 0402 component is to first apply a thin layer of solder to the pads using a soldering iron, then, place the 0402 on the pad and use a heat gun to melt the solder underneath, allowing the component to attach. No hot plate needed.

<div style="display: flex; overflow-x: auto; gap: 10px; padding: 10px; max-width: 100%; aspect">
  <img src="/assets/img/UBC/Radio.png" alt="NAS view 1" style="height: 280px; border-radius: 10px;">
  <img src="/assets/img/UBC/BuckConverter.png" alt="NAS view 2" style="height: 280px; border-radius: 10px;">
  <!-- Add more images here -->
</div>

<div style="margin-top: 40px"></div>

### PCB Design
 <a href="./sam-m10q.html">
SAM-M10Q GNSS module 
    <img src="assets/img/link.png" alt="link" style="width: 10px;">



This design follows the guidelines suggested in the manual, including the use of stitching vias and size of 5cm by 5cm.

<div style="display: flex; overflow-x: auto; gap: 10px; padding: 10px; max-width: 100%; aspect">
  <img src="/assets/img/UBC/GPS-V2.png" alt="SAM PCB" style="height: 280px; border-radius: 10px;">
  <!-- Add more images here -->
</div>


<div style="margin-top: 40px"></div>

[Back](./AESN.html)
