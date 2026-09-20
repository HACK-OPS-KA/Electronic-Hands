---
name: arduino-sensors
description: >-
  Help builders with Arduino/ESP32 boards and sensors at hack//ops op//002.
  Use when the user mentions Arduino, Uno, Nano, ESP32 (non-CrowPanel),
  breadboard sensors, servos, I2C modules, or blink/serial debugging.
---

# Arduino + sensors skill

## do first

1. read [AGENTS.md](../../../AGENTS.md) and [docs/safety.md](../../../docs/safety.md).
2. read [docs/kits/arduino-sensors.md](../../../docs/kits/arduino-sensors.md).
3. ask which **exact board** and sensor modules are on the bench — do not invent a BOM.

## goals

1. Blink uploads successfully on the real board.
2. one sensor printing to Serial with common ground.
3. actuators get a supply that can feed them.

## hello path

1. Arduino IDE → correct board + port.
2. Examples → Blink → upload.
3. wire one sensor → `Serial.begin(115200)` → plot values.
4. then motors/servos with proper power.

## pitfalls

- charge-only USB cables.
- 5 V into 3.3 V pins.
- guessing I2C addresses — read the module sheet.
- committing wifi passwords in sketches.
