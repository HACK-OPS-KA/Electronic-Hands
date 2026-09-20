# tips for the weekend

practical notes for op//002. pair with [safety.md](safety.md) and your kit page.

## first hour

1. claim a bench spot, power strip, and USB cable that actually data-syncs
   (many charge-only cables exist to ruin your night).
2. pick **one** kit path and get hello-world before brainstorming architecture.
3. write down serial port names (`COM3`, `/dev/ttyACM0`, …) when they show up.
   they change when you replug.

## serial and drivers

- windows: install the vendor USB-UART / CP210x / CH340 driver if the port
  never appears.
- unplug other USB serial devices when identifying SO-ARM leader vs follower
  ports — LeRobot’s discovery flow expects you to unplug on cue.
- close serial monitors before uploading Arduino / ESP32 firmware or the
  port stays locked.

## shared kits

- label your breadboard jumper mess; leave loaner robots in a known rest pose.
- if you calibrate an SO-ARM, note the `id` you used and tell the next team.
- do not hoard the only CrowPanel or Reachy Mini overnight without asking.

## sensors and noise

- common grounds matter. floating grounds invent haunted ADCs.
- debounce buttons in software or hardware; raw digital pins bounce.
- I2C: check address conflicts; pull-ups are often already on modules.

## demo readiness (sunday)

- demo is live in the room. bring a short script: what it is → what moves /
  senses → one proof → what broke and how you fixed it.
- have a cold-boot path: power cycle → one command or one button → visible
  effect in under 60 seconds.
- backup video on your phone is fine for the archive, not a substitute for
  the live demo.
- photos: if you answered **no** on lu.ma, grab a sticker at check-in.

## agent use

- paste the AI workflow from the root [README.md](../README.md).
- keep the agent on **one kit skill** at a time.
- if the agent invents a pinout, make it cite `docs/kits/` or upstream docs.

## when the wifi lies

- prefer offline / USB workflows for firmware.
- do not hardcode venue wifi passwords into committed sketches.
