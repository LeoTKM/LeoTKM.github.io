---
layout: default
---


## RVL Lab
*May 2026 - Aug 2026* 

<!-- c, python, opencv, PID, Altium, i2c, ROS2, MATLAB? -->

<div style="margin-bottom:10px"></div>
Summer research experience at the Robot Vision and Learning (RVL) lab, advised by Prof. Florian Shkurti. I designed and integrated a custom UMI-style gripper and a real-time teleoperation system to support force-aware VLA experiments. This setup allowed us to perform and collect contact rich manipulation data for the training datasets. 

<!-- Teleop -->
<h3 style="margin-bottom:10px; margin-top:20px">Teleoperation Arm</h3>  
<i><a href="./RVL_TELE.html" style="color:rgb(68, 143, 218);">Flexiv-Rizon Teleoperation Arm</a></i>

Designed to teleoperate a pair of Flexiv Rizon 4S arms. 
 

<!-- CoinFT -->
<h3 style="margin-bottom:10px; margin-top:20px">CoinFT Replication</h3> 
<i><a href="./RVL_CoinFT.html" style="color:rgb(68, 143, 218);">CoinFT</a></i>

<i><a href="https://coin-ft.github.io/" style="color:rgb(68, 143, 218);">Original Paper</a></i>

6DoF FT sensors on the market were too large for our custom UMI-style gripper and tactile sensors have reportedly been difficult to work with. As a result, we chose CoinFT.


<div style="margin-top:20px; text-align: center;">
    <figure style="margin: 0;">
        <img src="/assets/img/RVL/CoinFT.png" alt="TrackerSchematic" style="width: 540px; border-radius: 10px;">
        <figcaption style="margin-top: 0px; color: #666;">Figure 1: Left: During fabrication. Right: Calibration setup</figcaption>
    </figure>
</div>
<!-- We decided to build a custom UMI style gripper, and one of the most important advantages of UMI was the minimal emboidment gap, ie. the model needs to think that the data of human operating the UMI were from the actual robotic arm. The Flexiv Rizon came with sensors for wrench at the end effector, and it's important that the UMI couterpart can also somehow sense and relay a similar snesory input to the processor. Papers have shown that you can infer the measurements for the TCP wrench with using torque/force data collected at the finger tips. 6DoF FT sensors on the market -->





<!-- Custom UMI -->
<h3 style="margin-bottom:10px; margin-top:20px">Custom UMI</h3>
<i><a href="./RVL_UMI.html" style="color:rgb(68, 143, 218);">UMI-Style Gripper</a></i>

<i><a href="https://umi-gripper.github.io/" style="color:rgb(68, 143, 218);">Original Paper</a></i>

Flexiv Rizon arms use native grippers known as Grav. The finger structure of Grav differs from existing open source/COTS UMI-style gripper (eg. UMI, PIKA). To minimize the embodiment gap, we decided to develop our own custom UMI-style gripper on top of the exisiting teleoperation setup for comparison.

<div style="margin-top:20px; text-align: center;">
    <figure style="margin: 0;">
        <img src="/assets/img/RVL/UMI_two.jpg" alt="TrackerSchematic" style="width: 540px; border-radius: 10px;">
        <figcaption style="margin-top: 0px; color: #666;">Figure 2: Custom UMI-style gripper</figcaption>
    </figure>
</div>

<!-- Custom Gripper -->
<!-- <h3 style="margin-bottom:10px; margin-top:20px">Custom Teleop Gripper</h3>  

<div style="margin-top:20px; text-align: center;">
    <figure style="margin: 0;">
        <video style="border-radius: 10px; width: 540px" controls>
        <source src="/assets/img/RVL/CustomGripper.mp4" type="video/mp4">
        Your browser does not support the video tag.
        </video>
        <figcaption style="margin-top: 8px; color: #666;">Figure 1: Gripper animation</figcaption>
    </figure>
</div> -->

<div style="margin-top:20px"></div>
<!-- Hardware Purchase -->
<h3 style="margin-bottom:10px; margin-top:20px">Hardware Sourcing</h3>  
Managed the procurement of $1,500+ in lab equipment.
<div style="margin-top:20px; text-align: center;">
    <figure style="margin: 0;">
        <img src="/assets/img/RVL/HardwareSourcing.png" alt="TrackerSchematic" style="width: 540px; border-radius: 10px;">
        <figcaption style="margin-top: 0px; color: #666;">Figure 1: Purchase</figcaption>
    </figure>
</div>

<!-- Paper -->
<!-- <h3 style="margin-bottom:10px; margin-top:20px">Force VLA Paper</h3>   -->


<div style="margin-top:20px"></div>
[Back](./AESN)