---
name: crowpanel-advance
description: >-
  Help builders flash and UI-code Elecrow CrowPanel Advance (ESP32-S3 HMI) at
  hack//ops op//002. Use when the user mentions CrowPanel, Advance HMI,
  Elecrow touch display, LovyanGFX/LVGL on ESP32-S3 panel.
---

# CrowPanel Advance skill

## do first

1. read [AGENTS.md](../../../AGENTS.md) and [docs/safety.md](../../../docs/safety.md).
2. read [docs/kits/crowpanel-advance.md](../../../docs/kits/crowpanel-advance.md).
3. confirm **panel size + hardware revision** with the human/crew.
4. prefer Elecrow wiki for that exact panel — pin Arduino-ESP32 **3.0.2** and
   their ESP32S3_120M replace steps when their guide says so.

## goals

1. board menu settings match Elecrow for that panel.
2. vendor hello / simplest touch demo on glass.
3. cold-boot to a visible UI for the live demo.

## hello path

1. Arduino IDE + esp32 core version from Elecrow Advance guide.
2. apply their PSRAM/120M framework replace if required.
3. install pinned libraries from their Advance bundle.
4. flash their hello-world / touch sample before custom LVGL apps.

## pitfalls

- “latest” esp32 core instead of the pinned one.
- skipping 120 MHz PSRAM pack → flicker.
- mixing V1.0 examples with newer revisions.
- inventing pin maps — use Elecrow’s for that size.
