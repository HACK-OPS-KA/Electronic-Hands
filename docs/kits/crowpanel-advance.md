# CrowPanel Advance

## what it is / when to pick it

Elecrow **CrowPanel Advance** HMI — ESP32-S3 IPS touch displays (several sizes
in the Advance line). pick it when the demo needs an on-desk touch UI,
local graphics (LVGL / LovyanGFX), or an ESP32 brain with a serious screen.

## what’s in the box

confirm **size** (e.g. 3.5 / 5 / 7") and **hardware revision** (V1.0 vs later)
with crew — examples and library packs differ by version.

USB cable, optional speaker / battery harness if provided. treat as shared
glass: do not yeet face-down.

## first 30 minutes

1. install Arduino IDE.
2. install **esp32 by Espressif Systems** board package — Elecrow’s Advance
   guides pin **3.0.2** at the time of their wiki. prefer that over “whatever
   latest” unless crew says a newer combo is validated on site.
3. follow Elecrow’s Advance intro for your size/version:
   - board: **ESP32S3 Dev Module** (typical)  
   - flash size / partition / PSRAM settings from **their** wiki for your panel  
   - they often require replacing framework files with their **ESP32S3_120M**
     pack for stable high-speed PSRAM — do this from their instructions, not
     from memory.
4. install the library versions they list (LovyanGFX, LVGL, touch driver, …)
   from their Advance library bundle links.
5. burn their serial “hello world” or simplest touch demo until the panel
   shows life.
6. then build your UI. cold-boot to a visible screen in under a minute for
   sunday.

## official docs

- Advance HMI intro: https://www.elecrow.com/pub/wiki/1_Introduction_to_CrowPanel-Advance-HMI_Screen.html  
- course / get started hub: https://www.elecrow.com/wiki/HMI_Display_course.html  
- 7.0 Advance example wiki: https://elecrow.com/wiki/ESP32_Display-7.0_inch%28Advance_Series%29wiki.html  

always match **your** size + revision page if crew names it.

## common failure modes

- wrong ESP32 core version → compile or flash weirdness.  
- skipping the 120 MHz PSRAM replace → flicker / jank.  
- wrong partition / PSRAM menu → boot loops.  
- libraries from random GitHub instead of the pinned Advance bundle.  
- V1.0 example code on a newer panel revision (or the reverse).

## safety notes

- glass cracks once. keep tools off the panel.  
- if using the BAT connector, only the specified LiPo range from Elecrow —
  see [../safety.md](../safety.md).  
- USB power while drawing a bright full-screen UI is usually fine; add-on
  radios / amps may need more thought.
