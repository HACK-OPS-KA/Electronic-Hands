# Arduino + sensors

## what it is / when to pick it

classic microcontroller path: board + sensors + actuators on a breadboard.
pick it when you need a fast “sense → decide → move/light” loop for jam
prompts (make it move, sixth sense, etc.).

## what’s in the box

**ask crew** what is on the table. expect some mix of:

- Arduino Uno / Nano class boards and/or ESP32 variants  
- jumper wires, breadboards  
- common sensors (distance, IMU, light, buttons, …)  
- LEDs, buzzers, small motors / servos (check current!)

do **not** invent a BOM in commits. if the crate label says otherwise, believe
the crate.

Edge Impulse / tinyML tracks: only if mentors have that lane staffed — see
crew, do not assume cloud accounts are ready.

## first 30 minutes

1. identify the exact board (Uno vs Nano vs ESP32). that picks the Arduino
   IDE board menu entry and often the voltage level (5 V vs 3.3 V).
2. install [Arduino IDE](https://www.arduino.cc/en/software) (or PlatformIO if
   you already live there).
3. USB cable that does **data**, not charge-only.
4. open **File → Examples → 01.Basics → Blink**, select the right board +
   port, upload. onboard LED must blink on the real board.
5. wire one sensor with a **common ground**, print values on Serial at 115200.
6. only then add a servo/motor with a supply that can feed it (not the PC USB
   alone for hungry motors).

## official docs

- Arduino getting started: https://docs.arduino.cc/learn/starting-guide/getting-started-arduino/  
- board reference hub: https://docs.arduino.cc/hardware/  
- ESP32 (if that is your board): https://docs.espressif.com/projects/arduino-esp32/en/latest/  

sensor modules: use the vendor sheet for **that** module (often Adafruit /
SparkFun / generic HW-XXX). paste the chip name into search; do not guess I2C
addresses.

## common failure modes

- charge-only USB cable.  
- 5 V signal into a 3.3 V-only pin.  
- motor back-EMF without diode / shared ground nightmares.  
- Serial Monitor left open → upload fails.  
- floating inputs read as haunted randomness — use pull-ups/pull-downs.

## safety notes

- servos and motors need adequate power and secure mounts.
- soldering: stands, ventilation, eye line when snipping leads.
- see [../safety.md](../safety.md).
