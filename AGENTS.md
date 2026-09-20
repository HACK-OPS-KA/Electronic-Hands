# AGENTS.md — Electronic-Hands

rules for coding agents helping builders at **hack//ops op//002**.

humans: read this too if you are skimming with an AI.

## mission

get real hardware moving, sensing, or lighting up in the room. the demo is
in person. this repo is kit docs + skills, not a submission monorepo.

## before you write code

1. read [docs/safety.md](docs/safety.md).
2. confirm which kit the human is using.
3. read the matching page under [docs/kits/](docs/kits/) and the skill under
   `.cursor/skills/<kit>/SKILL.md`.
4. open the **official** upstream links from that kit page. prefer them over
   memory.

## hard rules

- **physical bar.** prefer real-device steps. simulation is fine for Reachy
  Mini practice (`--sim`) but the weekend demo must run on hardware in the room.
- **do not invent.** board pins, motor IDs, Arduino core versions, LeRobot
  CLI flags, CrowPanel flash settings — copy from linked vendor docs or ask.
- **no secrets.** never commit `.env`, wifi passwords, tokens, private keys,
  or calibration dumps that contain secrets. keep them local / out of git.
- **shared kits.** Reachy Mini, SO-ARM101, CrowPanels, and loaner Arduinos may
  be shared. do not wipe firmware, recalibrate motors, or change motor IDs on
  a communal unit without the human confirming with crew.
- **power.** wrong voltage fries motors. SO-ARM leader/follower supplies
  differ (see kit page). LiPo only if the crew says the pack is on the table
  and charged safely.
- **safety.** pinch points on arms, hot soldering irons, eye protection for
  cutting. if unsure, stop and ask a mentor on the floor.
- **scope.** do not add a `projects/` submission archive, Faust CI, or website
  gallery wiring in this repo unless a maintainer asks.
- **tone.** lowercase is fine in user-facing copy that matches hack//ops.
  no emojis unless the human asks. no fake “done” when the board is not
  actually flashing.

## preferred workflow

1. hello-world / blink / teleop on hardware (first 30 minutes goal).
2. one sensor or one actuator path that is demo-visible.
3. then the product idea. do not polish a slide deck.

## when stuck

- check [docs/tips.md](docs/tips.md) (serial ports, drivers, demo readiness).
- re-read the kit “common failure modes” section.
- ask crew on the floor before inventing a workaround that modifies shared
  hardware.

## photos

event photography is opt-out via lu.ma + sticker at check-in. details:
https://hackops.tech/photos.html
