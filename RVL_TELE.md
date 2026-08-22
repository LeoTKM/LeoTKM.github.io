---
layout: default
---

## Flexiv-Rizon Teleoperation Arm
### RVL

<div style="margin-bottom:10px"></div>

<a href="https://github.com/rvl-lab-utoronto/FACTR-Server/tree/main/FACTR_Teleop" aria-label="GitHub Repository" style="color: #24292e; text-decoration: none; display: inline-block;">
    <svg height="32" viewBox="0 0 16 16" width="24" style="display: block;">
        <path fill="currentColor" d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"></path>
    </svg>
</a>

<div style="margin-bottom:10px"></div>

<div style="margin-top:20px; text-align: center;">
    <figure style="margin: 0;">
        <img src="/assets/img/RVL/Teleop.jpg" alt="TrackerSchematic" style="width: 540px; border-radius: 10px;">
        <figcaption style="margin-top: 8px; color: #666;">Figure 1: The teleoperation arm V2</figcaption>
    </figure>
</div>

<div style="margin-bottom:10px"></div>

The completed system serves as a pair of leader arms currently used in an ongoing lab research project to teleoperate a dual-arm Flexiv Rizon 4S system for force data collection. 

<div style="margin-bottom:10px"></div>
I developed the entire end-to-end project including CAD design (Fusion & Onshape), implementation of the ROS 2 software stack for low-level Dynamixel servo communication, gravity compensation, a FastAPI interface for sending commands to the follower system, and URDF modeling with accurate mass distribution and inertia properties.

<div style="margin-top:20px"></div>
[Back](./RVLLAB)