# RGB-Matrix-SM16306

> 8×16 RGB LED matrix based on **SM16306SJ constant-current drivers**.  
> Designed as a cost-effective alternative to addressable LED panels.  

---
![alt text](<img/img.png>)
## Motivation
When working on a previous badge project, it became clear that building matrices out of addressable LEDs (e.g. WS2812) quickly becomes too expensive.  
The solution: use **standard RGB LEDs** combined with **constant-current drivers**.  

---

## Hardware Overview
- **LEDs**: XL-B1010RGBT-HF  
- **Matrix size**: 8 × 16 (128 RGB = 384 channels)  
- **Drivers**: SM16306SJ  
  - 16 constant-current channels per chip  
  - Current per channel: **20 mA**  
- **Row control**: standard shift register + power switches for row selection  
- **Power budget**:  
  - up to **34 LEDs per row**  
  - peak current up to **2 A per row**  

---

## Key Points
- At least **5× cheaper** compared to addressable LED matrices.  
- **Accurate current driving** ensures stable brightness and color balance.  
- Easily scalable for larger panels.  
- Requires an external **controller** (e.g. RP2040, ESP32) to drive shift registers and SM16306SJ chips.  

---

## PCB Notes
- Initial goal: a **two-sided layout**  
  - LEDs on the front  
  - Drivers + shift registers on the back  
- In practice: all components ended up on the same side to simplify routing.  
- Possible future version: **two-board design** (LED front panel + driver board).  

---

## Next Steps
- Integrate this matrix into the upcoming **badge version**.  
- Provide example firmware (SPI driving + timing).  
- Test long-term reliability at **20 mA per channel** load.  

---
