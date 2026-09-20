---
name: reachy-mini
description: >-
  Help builders use Reachy Mini at hack//ops op//002. Use when the user mentions
  Reachy, Reachy Mini, pollen robotics head/antennas, or reachy-mini SDK/daemon.
---

# Reachy Mini skill

## do first

1. read [AGENTS.md](../../../AGENTS.md) and [docs/safety.md](../../../docs/safety.md).
2. read [docs/kits/reachy-mini.md](../../../docs/kits/reachy-mini.md).
3. prefer upstream: https://huggingface.co/docs/reachy_mini/SDK/installation and quickstart.

## goals

1. daemon running (hardware or `--sim` for practice).
2. antenna/head hello on the **real** robot before product features.
3. keep shared units intact — no reset without confirmation.

## hello path

```bash
uv pip install "reachy-mini"
# hardware: start daemon per quickstart for Lite vs Wireless
# practice: uv pip install "reachy-mini[mujoco]" && reachy-mini-daemon --sim
```

```python
from reachy_mini import ReachyMini

with ReachyMini() as mini:
    mini.goto_target(antennas=[0.5, -0.5], duration=0.5)
    mini.goto_target(antennas=[0, 0], duration=0.5)
```

## pitfalls

- coding against a dead daemon.
- treating sim success as sunday demo done.
- inventing SDK methods — check Python SDK docs.
