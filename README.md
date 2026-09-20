# Electronic-Hands

kit docs and agent pack for **hack//ops op//002**
if it does not physically exist in the room, it does not count.

this repo is **not** a project submission archive. demos are live, on the bench.
use it to get Reachy Mini, SO-ARM101, Arduino + sensors, and CrowPanel Advance
blinking before you invent the cursed part.

site: [hackops.tech](https://hackops.tech) · photos: [hackops.tech/photos.html](https://hackops.tech/photos.html)

---

## kits on the bench

| kit | start here | agent skill |
|---|---|---|
| Reachy Mini | [docs/kits/reachy-mini.md](docs/kits/reachy-mini.md) | `.cursor/skills/reachy-mini` |
| SO-ARM101 | [docs/kits/so-arm101.md](docs/kits/so-arm101.md) | `.cursor/skills/so-arm101` |
| Arduino + sensors | [docs/kits/arduino-sensors.md](docs/kits/arduino-sensors.md) | `.cursor/skills/arduino-sensors` |
| CrowPanel Advance | [docs/kits/crowpanel-advance.md](docs/kits/crowpanel-advance.md) | `.cursor/skills/crowpanel-advance` |

full index: [docs/kits/README.md](docs/kits/README.md)

also read:

- [docs/safety.md](docs/safety.md) — before you power anything
- [docs/tips.md](docs/tips.md) — weekend tips, serial, demo readiness
- [AGENTS.md](AGENTS.md) — rules for coding agents (and humans who behave like them)

---

## quick rules

- physical proof only. screenshots of a sim are homework, not a demo.
- shared kits stay shared. do not reflash communal units without asking crew.
- no secrets in the repo. wifi passwords, API keys, `.env` — keep them local.
- prefer vendor docs linked from the kit pages. do not invent APIs.
- saying no to photos is fine: answer on lu.ma, sticker at check-in.

---

## workflow (human version)

1. clone this repo.
2. pick a kit from the table above.
3. read `docs/safety.md`, then that kit page.
4. get the official hello-world / blink / teleop running on real hardware.
5. build your thing. demo it live on sunday.

---

## workflow (AI version)

paste this to your agent after opening the repo in Cursor (or any agent that can
read `AGENTS.md` and `.cursor/skills/`):

```text
You are helping at hack//ops op//002 (Electronic-Hands).
1. Read AGENTS.md and docs/safety.md first. Obey them.
2. Ask which kit we are using: reachy-mini | so-arm101 | arduino-sensors | crowpanel-advance.
3. Read docs/kits/<kit>.md and the matching .cursor/skills/<kit>/SKILL.md before writing code.
4. Prefer official upstream docs linked from the kit page. Do not invent flash settings or APIs.
5. First goal: one physical hello-world on the real device. Then iterate toward the live demo.
6. Never commit secrets, never reflash shared kit firmware without confirmation, never skip safety notes.
```

one-shot clone (bash):

```bash
git clone https://github.com/HACK-OPS-KA/Electronic-Hands.git && cd Electronic-Hands && cat AGENTS.md
```

---

## what this repo is not

- not a place to dump team project code (keep that in your own repos / USB).
- not a full rewrite of Hugging Face / Elecrow / Arduino manuals.
- not legal advice and not a substitute for nova floor rules.

built by [hack//ops](https://hackops.tech) · Karlsruhe
