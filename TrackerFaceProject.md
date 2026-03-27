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
This is a pan-tilt face-tracking camera.

<!-- The main technical challenges in this project are implementing the face tracking algorithm on limited hardware and controlling the stepper motors through the H-bridge drivers. Running OpenCV functions on a 500MHz STM32 with limited memory requires optimization of the camera library, and may also need to use external memory or offloading some tasks such as dedicating a second STM32 for motor control.  -->

<!-- To avoid design flaws caused by unfamiliarity with the components, the project is divided into different phases to test individual devices, followed by the final assembly.  -->


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
<div style="margin-top:20px; text-align: center;">
<figure style="margin: 0;">
        <video style="height: 300px; border-radius: 10px; object-fit: cover;" controls muted>  
    <source src="/assets/img/FaceTracker/Prototype.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
        <figcaption style="margin-top: 8px; color: #666;">Figure 1: Hardware prototype</figcaption>
</figure>
</div>
  <!-- <video style="height: 300px; border-radius: 10px; object-fit: cover;" controls muted>  
    <source src="/assets/img/FaceTracker/Prototype.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video> -->
  <!-- <img src="/assets/img/FaceTracker/CameraFrame.jpg" alt="TrackerCamera" style="width: 300px; height: 220px; border-radius: 10px; object-fit: cover;"> -->
</div>
<div style="margin-top:20px"></div>

<h3 style="margin-bottom:10px; margin-top:10px">Control and Tuning (In Progress)</h3>  
Earlier last week, I wrote a face detection algorithm in Python using OpenCV on my personal computer and verified the needed functions. At this stage of the project, the control logic that was previously written in C with a STM32 dev board was adapted along with the new detection program into Python on a Pi Zero 2W, which will be the brain of the system. 
Everything was done on my iMac, using SSH and VSCode.
<div style="margin-top:20px"></div>


<div style="margin-top:20px; text-align: center;">
    <figure style="margin: 0;">
        <img src="/assets/img/FaceTracker/FaceTrackSSH.jpg" alt="TrackerSchematic" style="width: 450px; border-radius: 10px;">
        <figcaption style="margin-top: 8px; color: #666;">Figure 2: SSH on VSCode</figcaption>
    </figure>
</div>

<div style="margin-top:20px; text-align: center;">
    <figure style="margin: 0;">
        <img src="/assets/img/FaceTracker/FaceTrackPID.png" alt="TrackerSchematic" style="width: 540px; border-radius: 10px;">
        <figcaption style="margin-top: 8px; color: #666;">Figure 3: PID control diagram</figcaption>
    </figure>
</div>

The current model experiences stalling when new motor control signals come in (charging and discharging the coils). That could be mitigated using stepper motor acceleration libraries to smooth the motion, however, the camera's motion toward the target position still has jitter which I want to avoid. As a result, I'm using a closed-loop PID controller to actively drive the motor, with the target speed adjusted based on the positional offset provided by the camera feedback.
<div style="display: flex; gap: 20px; align-items: stretch;">

<!-- <img src="/assets/img/FaceTracker/CameraFrame.jpg" alt="TrackerSchematic" style="height: 280px; border-radius: 10px;"> -->
<!-- <img src="/assets/img/FaceTracker/Pi.png" alt="TrackerSchematic" style="height: 280px; border-radius: 10px;"> -->
</div>
<div style="margin-top:20px"></div>
[Back](./AESN.html)

