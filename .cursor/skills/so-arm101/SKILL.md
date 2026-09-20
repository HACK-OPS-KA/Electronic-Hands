---
name: so-arm101
description: >-
  Help builders use SO-ARM101 / SO-101 arms with LeRobot at hack//ops op//002.
  Use when the user mentions SO ARM, SO-101, SO-ARM100/101, Feetech STS3215,
  leader-follower teleop, or lerobot calibrate/teleoperate.
---

# SO-ARM101 skill

## do first

1. read [AGENTS.md](../../../AGENTS.md) and [docs/safety.md](../../../docs/safety.md).
2. read [docs/kits/so-arm101.md](../../../docs/kits/so-arm101.md).
3. prefer upstream: https://huggingface.co/docs/lerobot/en/so101

## goals

1. correct PSU on each arm (voltage matters).
2. ports + ids identified; teleop without cameras.
3. do not re-ID motors on a shared kit unless crew agrees.

## hello path

1. install LeRobot + Feetech stack per HF/Seeed docs (no invented pins).
2. discover leader/follower ports.
3. calibrate only if needed.
4. `lerobot-teleoperate` with `so101_leader` / `so101_follower` types — copy
   flags from upstream once ports are known.

## pitfalls

- wrong voltage → dead motors.
- cameras before teleop works.
- swapping leader/follower ids.
- leaving torque on unattended.
