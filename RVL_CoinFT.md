---
layout: default
---

## CoinFT
### RVL


<div style="margin-bottom:10px"></div>
<a href="https://github.com/rvl-lab-utoronto/CoinFT" aria-label="GitHub Repository" style="color: #24292e; text-decoration: none; display: inline-block;">
    <svg height="32" viewBox="0 0 16 16" width="24" style="display: block;">
        <path fill="currentColor" d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"></path>
    </svg>
</a>

<div style="margin-bottom:10px"></div>

<div style="margin-top:20px; text-align: center;">
    <figure style="margin: 0;">
        <img src="/assets/img/RVL/CoinFT.png" alt="TrackerSchematic" style="width: 540px; border-radius: 10px;">
        <figcaption style="margin-top: 0px; color: #666;">Figure 1: Left: During fabrication. Right: Calibration setup</figcaption>
    </figure>
</div>

<div style="margin-top:20px"></div>
<h3 style="margin-bottom:10px; margin-top:10px">Fabrication</h3>  
Some of the components used in the original CoinFT sensor are not available in my region, parts such as the mold used to provide a compressible layer betweeen the PCBs were replaced with Mold Max 40, and 1200 Primer was replaced with 99% IPA. Here, the CoinFT sensor is placed on top of a reference sensor (the Bota SensOne).



<h3 style="margin-bottom:10px; margin-top:20px">Calibration</h3>  
The Stanford team found that the change in capacitance of each of the 12 electrodes on the PCB can be mapped to the amount of pressure exerted on the sensor. However, these individual readings don't have any direct physical meanings.  
<div style="margin-bottom:10px"></div>
So, I trained a MLP on the 12 sensor inputs using the reference sensor's measurements as the groud truth. The model outputs 6 values corresponding to the 6DoF FT data.

<div style="margin-top:20px; text-align: center;">
    <figure style="margin: 0;">
        <img src="/assets/img/RVL/CoinFT_trained.PNG" alt="TrackerSchematic" style="width: 540px; border-radius: 10px;">
        <figcaption style="margin-top: 0px; color: #666;">Figure 2: Evaluation on the test set</figcaption>
    </figure>
</div>
<div style="margin-top:20px"></div>
As you can see, the model is performing quite well. However, there are still some improvements that could be made, such as reducing the Bota sensor’s output rate to get smoother reference readings (currently, the Bota sensor outputs at 500 Hz and the CoinFT sensor outputs at around 70 Hz)

<div style="margin-top:20px"></div>
[Back](./RVLLAB)