---
layout: default
---


## Face Tracker
*Jan 2026* -
<div style="margin-bottom:10px"></div>
<a href="https://github.com/MarcusLeoTKM/FaceTrack26" aria-label="GitHub Repository" style="color: #24292e; text-decoration: none; display: inline-block;">
    <svg height="32" viewBox="0 0 16 16" width="24" style="display: block;">
        <path fill="currentColor" d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"></path>
    </svg>
</a>

<div style="margin-bottom:10px"></div>
<div style="text-align: center;">
    <img src="/assets/img/FaceTracker/TrackerDemo.jpg" alt="TrackerSchematic" style="height: 320px; border-radius: 10px;">
</div>
<div style="margin-bottom:20px"></div>

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

<!-- <div style="margin-top:20px"></div> -->
<div style="display: flex; gap: 20px; align-items: stretch; justify-content: center;">
    <div style="margin-top:20px; text-align: center;">
        <figure style="margin: 0;">
            <video style="width: 300px; border-radius: 10px; object-fit: cover;" controls muted>  
                <source src="/assets/img/FaceTracker/Prototype.mp4" type="video/mp4">
                Your browser does not support the video tag.
            </video>
            <figcaption style="margin-top: 8px; color: #666;">Figure 1: Hardware prototype</figcaption>
        </figure>
    </div>
</div>
  <!-- <video style="height: 300px; border-radius: 10px; object-fit: cover;" controls muted>  
    <source src="/assets/img/FaceTracker/Prototype.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video> -->
  <!-- <img src="/assets/img/FaceTracker/CameraFrame.jpg" alt="TrackerCamera" style="width: 300px; height: 220px; border-radius: 10px; object-fit: cover;"> -->
<div style="margin-top:20px"></div>

<h3 style="margin-bottom:10px; margin-top:10px">Control and Tuning (Completed)</h3>  
Earlier last week, I wrote a face detection algorithm in Python using OpenCV on my personal computer and verified the needed functions. At this stage of the project, the motor controls that was previously written in C with a STM32 dev board was adapted along with the new detection program into Python on a Pi Zero 2W, which will be the brain of the system. 
Everything was done on my iMac, using SSH and VSCode.

<div style="margin-top:20px"></div>


<div style="margin-top:20px; text-align: center;">
    <figure style="margin: 0;">
        <img src="/assets/img/FaceTracker/FaceTrackSSH.jpg" alt="TrackerSchematic" style="width: 450px; border-radius: 10px;">
        <figcaption style="margin-top: 8px; color: #666;">Figure 2: SSH on VSCode</figcaption>
    </figure>
</div>

<div style="margin-top:20px"></div>
The current model experiences stalling when new motor control signals come in (charging and discharging the coils). That could be mitigated using stepper motor acceleration libraries to smooth the motion, however, the camera's motion toward the target position still has jitter. As a result, I'm using a closed-loop PID controller to actively drive the motor, with the target PWM driving frequency adjusted based on the angle offset provided by the onboard magnetic encoder via I2C.


The PID parameters were physcially tuned using a custom 3D base. 

<div style="display: flex; gap: 20px; align-items: stretch;">
<div style="margin-top:20px; text-align: center;">
    <figure style="margin: 0;">
        <img src="/assets/img/FaceTracker/FaceTrackPID.png" alt="TrackerSchematic" style="width: 540px; border-radius: 10px;">
        <figcaption style="margin-top: 8px; color: #666;">Figure 3: PID control diagram</figcaption>
    </figure>
</div>

<!-- <img src="/assets/img/FaceTracker/CameraFrame.jpg" alt="TrackerSchematic" style="height: 280px; border-radius: 10px;"> -->
<!-- <img src="/assets/img/FaceTracker/Pi.png" alt="TrackerSchematic" style="height: 280px; border-radius: 10px;"> -->
</div>

<div style="margin-top:20px; text-align: center;">
    <figure style="margin: 0;">
        <video style="width: 300px; border-radius: 10px; object-fit: cover;" controls muted>  
        <source src="/assets/img/FaceTracker/FaceTrackerLive.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>
        <figcaption style="margin-top: 8px; color: #666;">Figure 4: The camera following my face</figcaption>
    </figure>
</div>

<div style="margin-top:20px"></div>

<h3 style="margin-bottom:10px; margin-top:10px">ROS2 Integration (In Progress)</h3>  
Camera motion in one axis is relatively simple to control, however, with the addition of the second motor, the program must continuously switch between reading the angle, updating each motor with the new position, and checking whether the person has moved. It’s going to be impossible to navigate if we add new functions such as checking the PCB temperature or enabling voice commands. As a result, I'm adding ROS2 to this project. In addition to the reasons mentioned above, I'm also doing this because I wanted to have a STM32 chip on the PCB, and it will be much easier to communicate with it using C.
<div style="margin-top:20px"></div>

<h3 style="margin-bottom:10px; margin-top:10px">PCB Design (In Progress)</h3>  

I’m using a DRV8825 motor driver for the motors, but the board uses a potentiometer for current limiting and male header pins for communication, which are not reliable for long term use.

In addition, I need to power both the Pi and the motors, so I will need a proper power distribution solution. With that in mind, I plan to move to a custom 4-layer PCB design once PID tuning and ROS2 are integrated into the system.

<div style="margin-top:20px"></div>
[Back](./AESN.html)

