---
layout: default
---


## SAM M10Q GNSS Module
*Jul 2025 - Aug 2025*
<div style="margin-bottom:10px"></div>


<div style="display: grid; grid-template-columns: repeat(6, 1fr); gap: 10px; max-width: 240px; margin-bottom: 24px;">
    <img src="assets/img/stm32cubeide-logo.png" alt="STM32CubeIDE" style="width: 28px;">
    <img src="assets/img/UBC/UBCRocketsLogo.png" alt="UBC Rocket" style="width: 30px;">
    <img src="assets/img/altium-logo.png" alt="Altium Designer" style="width: 120px;">
</div>

<script>
    /**
     * Toggles the visibility of a content block based on the button's data-target attribute.
     * @param {HTMLElement} buttonElement - The button that was clicked (passed as 'this').
     */
    function toggleContent(buttonElement) {
        // 1. Get the ID of the content block to target from the button's data attribute
        const targetId = buttonElement.getAttribute('data-target');
        const contentBlock = document.getElementById(targetId);

        // 2. Get the text container within the button (where the text is located)
        const textContainer = buttonElement.querySelector('.button-text');
        
        // 3. Toggle the display property
        if (contentBlock.style.display === 'none' || contentBlock.style.display === '') {
            // SHOW
            // The image container uses 'display: flex' internally for the carousel layout, 
            // but the outer container should use 'block' to appear on a new line.
            contentBlock.style.display = 'block'; 
            
            // Check if the content inside the contentBlock should be flex
            contentBlock.querySelector('div').style.display = 'flex'; 
        } else {
            // HIDE
            contentBlock.style.display = 'none';
        }
    }
</script>

<div style="display: flex; gap: 20px; margin-bottom: 20px;"> 
    <div 
        class="toggle-button"
        onclick="toggleContent(this)" 
        data-target="image-sam"
        style="
            display: flex;
            padding: 0;
            background-color: #f0f0f0;
            border-radius: 8px; 
            color: inherit;  
            width: 150px; 
            cursor: pointer; 
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1); 
        ">
        <div class="button-text" style="
          padding: 10px; 
          flex-grow: 1;
          text-align: center; 
          font-weight: bold;
        ">
          Development
        </div>
    </div>

    <div 
        class="toggle-button"
        onclick="toggleContent(this)" 
        data-target="image-gps"
        style="
            display: flex;
            padding: 0;
            background-color: #f0f0f0;
            border-radius: 8px; 
            color: inherit; 
            width: 150px; 
            cursor: pointer; 
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1); 
        ">
        <div class="button-text" style="
          padding: 10px; 
          flex-grow: 1;
          text-align: center; 
          font-weight: bold;
        ">
          PCB Design
        </div>
    </div>

</div> 
<div id="image-sam" style="display: none; margin-top: 10px;">
    <img src="/assets/img/UBC/SAM.png" alt="Testing the SAM module" style="border-radius: 10px; height: 280px;">
</div>

<div id="image-gps" style="display: none; margin-top: 10px;">
    <img src="/assets/img/UBC/GPS-V2.png" alt="SAM PCB" style="height: 280px; border-radius: 10px;">
</div>

<!-- This was a very straightforward project, the rocket collects location and time data from GNSS satellites (GPS, Beidou, etc.) and sends it back via the onboard radio. My part was to design the PCB that hosts the SAM-M10Q GNSS module and later program it to fetch the location and time data. The module starts transmission as soon as it's powered and connected via UART.

The return messages are written in NMEA format, which starts with different sentence types, such as GNGLL (shows latitude and longtitude), GNRMC (shows location and time), GNGSA (shows available satellites). I had to locate the lines starting with GNRMC and reformat them so they could be used by the FC. -->

I designed and soldered a custom PCB for a SAM-M10Q GNSS module and developed the embedded firmware to acquire satellite signals, parse positioning data, and make it available to the onboard avionics controller.
<div style="margin-bottom: 20px"></div>

<img src="/assets/img/UBC/SAM-output.jpg" alt="Branching" width="500" style="border-radius: 10px; vertical-align: middle;">
<div style="margin-bottom: 20px"></div>

The output from the GNSS module is shown above.
<!-- 015201.00 was the time when I was testing it. 4916.00492 N and 12315.14884 W represent the geolocation in DMM (Degrees and Decimal Minutes) format. 140825 is the date (August 14, 2025).  -->
 
During development, we realized that we needed a faster update and output rate, which required modifying the module's internal configuration items. The procedure for configuring them is included: 

 <a href="https://github.com/MarcusLeoTKM/SAM-M10Q">
SAM GitHub project
    <img src="assets/img/link.png" alt="link" style="width: 10px;">

<div style="margin-top:20px"></div>
[Back](./AESN.html)
