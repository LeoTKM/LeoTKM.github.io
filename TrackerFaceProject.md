---
layout: default
---


## Face Tracker
Jan 2026 - 

<img src="/assets/img/TrackerDemo.png" alt="TrackerSchematic" style="height: 280px; border-radius: 10px;">
<div style="margin-bottom:20px"></div>
<!-- <div style="display: grid; grid-template-columns: repeat(6, 1fr); gap: 10px; max-width: 240px; margin-bottom: 24px;">
    <img src="assets/img/stm32cubeide-logo.png" alt="STM32CubeIDE" style="width: 28px;">
    <img src="assets/img/UBC/UBCRocketsLogo.png" alt="UBC Rocket" style="width: 30px;">
    <img src="assets/img/altium-logo.png" alt="Altium Designer" style="width: 120px;">
</div> -->

The main technical challenges in this project are implementing the face tracking algorithm on limited hardware and controlling the stepper motors through the H-bridge drivers. Running OpenCV functions on a 500MHz STM32 with limited memory requires optimization of the camera library, and may also need to use external memory or offloading some tasks such as dedicating a second STM32 for motor control. 

<h3 style="margin-bottom:10px; margin-top:10px">Phase 1</h3>  

Phase 1 involves testing and developing firmware for a USB camera (to be replaced later by a DCMI camera) and a small stepper motor.

<div style="margin-top:20px"></div>

<video width="400" controls>
  <source src="/assets/img/StepperMotor.mp4" type="video/quicktime">
  Your browser does not support the video tag.
</video>

<div style="margin-top:20px"></div>
[Back](./AESN.html)
