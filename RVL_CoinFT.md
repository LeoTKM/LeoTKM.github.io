---
layout: default
---

## CoinFT
### RVL


<div style="margin-bottom:10px"></div>

<div style="margin-top:20px; text-align: center;">
    <figure style="margin: 0;">
        <img src="/assets/img/RVL/CoinFT.png" alt="TrackerSchematic" style="width: 540px; border-radius: 10px;">
        <figcaption style="margin-top: 0px; color: #666;">Figure 1: Left: During fabrication. Right: Calibration setup</figcaption>
    </figure>
</div>


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
As you can see, the model is performing quite well. However, there are still some improvements that could be made, such as reducing the Bota sensor’s output rate to get smoother reference readings (currently, the Bota sensor outputs at 500 Hz and the CoinFT sensor outputs at around 70 Hz)

<div style="margin-top:20px"></div>
[Back](./RVLLAB)