---
layout: default
---


## Face Tracker
Jan 2026 - 

<img src="/assets/img/FaceTracker/TrackerDemo.jpg" alt="TrackerSchematic" style="height: 280px; border-radius: 10px;">
<div style="margin-bottom:20px"></div>
<!-- <div style="display: grid; grid-template-columns: repeat(6, 1fr); gap: 10px; max-width: 240px; margin-bottom: 24px;">
    <img src="assets/img/stm32cubeide-logo.png" alt="STM32CubeIDE" style="width: 28px;">
    <img src="assets/img/UBC/UBCRocketsLogo.png" alt="UBC Rocket" style="width: 30px;">
    <img src="assets/img/altium-logo.png" alt="Altium Designer" style="width: 120px;">
</div> -->
This is a vision-based tracking system that detects a human face and performs closed-loop motor control to maintain perfect alignment in real time. 



<!-- The main technical challenges in this project are implementing the face tracking algorithm on limited hardware and controlling the stepper motors through the H-bridge drivers. Running OpenCV functions on a 500MHz STM32 with limited memory requires optimization of the camera library, and may also need to use external memory or offloading some tasks such as dedicating a second STM32 for motor control.  -->

<!-- To avoid design flaws caused by unfamiliarity with the components, the project is divided into different phases to test individual devices, followed by the final assembly.  -->
<div style="margin-top:20px"></div>
<h3 style="margin-bottom:10px; margin-top:10px">Viability Test (Completed) </h3>  
Programmed the USB camera and stepper motor to ensure basic functionalities before starting the project. 


<div style="margin-top:20px"></div>

<!-- <div style="display: flex; gap: 20px; align-items: stretch;">
  
  <img src="/assets/img/FaceTracker/Camera.png" alt="TrackerCamera" style="width: 220px; height: 220px; border-radius: 10px; object-fit: cover;">
</div>
<div style="margin-top:20px"></div> -->

<h3 style="margin-bottom:10px; margin-top:10px">Hardware Prototype (Completed)</h3>  
Built a prototype integrating:
  - A V4L camera  
  - A NEMA 17 stepper motor
  - A temporary microcontroller
  - Power supply and control circuitry

3D modeled the camera base to assess physical constraints and define dimensions for the custom PCB. Also tested the motor under heavy load and rapid switching commands to assess current threshold (for the PCB). 

<div style="margin-top:20px"></div>
<div style="display: flex; gap: 20px; align-items: stretch;">

  <video style="height: 300px; border-radius: 10px; object-fit: cover;" controls muted>  
    <source src="/assets/img/FaceTracker/Prototype.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
  <!-- <img src="/assets/img/FaceTracker/CameraFrame.jpg" alt="TrackerCamera" style="width: 300px; height: 220px; border-radius: 10px; object-fit: cover;"> -->
</div>
<div style="margin-top:20px"></div>

<h3 style="margin-bottom:10px; margin-top:10px">Before PCB</h3>  
In this phase, every component including the code will be fit tested. 


With the latest version of ROS2 running on the Pi Zero 2 W (The controller), the OpenCV based face recognition algorithm can run directly in Python without readapting the code written during the Viability Test phase. On the other hand, the majority of sensor data acquisition is implemented in C++ to achieve lower latency.

<div style="margin-top:20px"></div>
<div style="display: flex; gap: 20px; align-items: stretch;">

<!-- <img src="/assets/img/FaceTracker/CameraFrame.jpg" alt="TrackerSchematic" style="height: 280px; border-radius: 10px;"> -->
<!-- <img src="/assets/img/FaceTracker/Pi.png" alt="TrackerSchematic" style="height: 280px; border-radius: 10px;"> -->
</div>
<div style="margin-top:20px"></div>
[Back](./AESN.html)

