---
layout: default
---

## UTAT University of Toronto Aerospace Team
*Sep 2024* - 


<div style="display: grid; grid-template-columns: repeat(6, 1fr); gap: 10px; max-width: 240px; margin-bottom: 24px;">
    <img src="assets/img/UTAT/UTAT_logo.png" alt="UTAT" style="width: 30px;">
</div>

This is my second year at UTAT. This year, I'm ready to take on some more advanced tasks, primarily in control systems, calibration and custom PCB design. So far, I've already built a PCB for a relay station to ensure robust signal communication between the ground station and drone.

<div style="margin-bottom: 30px;"></div>

<!-- Comment out entire sections:
<script>
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
        data-target="image-PCB"
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
          PCB
        </div>
    </div>


</div> 
<div id="image-PCB" style="display: none; margin-top: 10px;">
    <img src="/assets/img/RelayPCB.png" alt="Testing the keyboard module" style="border-radius: 10px; height: 400px;">
</div>
-->

### PCB Design

<div style="display: flex; overflow-x: auto; gap: 10px; padding: 10px; max-width: 100%; aspect">
  <img src="/assets/img/UTAT/RelayPCB.png" alt="Relay PCB" style="height: 280px; border-radius: 10px;">
  <!-- Add more images here -->
</div>
The current drone experiences severe signal loss when navigating over mountains. Therefore, I designed a PCB for relaying drone control signals that will be mounted on top of a guyed tower being built by our mechanical team. 

I incorporated high speed signal design principles including a complete ground plane below high-frequency traces, appropriate via placement for proper return paths, rounded corners for signal integrity, and impedance control with length matching for USB (though USB 2.0 doesn't really need this).


<div style="margin-bottom:20px"></div>

[Back](./AESN.html)