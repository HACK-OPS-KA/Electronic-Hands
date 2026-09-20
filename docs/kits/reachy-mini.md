# Reachy Mini

## what it is / when to pick it

small expressive robot (Pollen Robotics) with a head, antennas, and an SDK
that talks to a local **daemon**. pick it when your demo needs presence,
gaze, speech/vision hooks, or a social “creature” on the table.

## what’s in the box

exact unit on site: ask crew (Lite vs Wireless matters for how the daemon
runs). treat as a **shared kit** unless crew assigns it to your team.

TBD on the day: cables, mount, any spare antennas / SD assets.

## first 30 minutes

1. on your laptop: Python **3.10–3.12**, then install the SDK per upstream
   (uv recommended):

   ```bash
   uv venv reachy_mini_env --python 3.12
   # activate the venv for your OS, then:
   uv pip install "reachy-mini"
   ```

2. start the daemon for **hardware** (Lite / USB — daemon on the laptop) or
   follow Wireless docs if that is your unit. for practice without the robot:

   ```bash
   uv pip install "reachy-mini[mujoco]"
   reachy-mini-daemon --sim
   ```

3. verify the daemon API docs load (Lite/sim: http://localhost:8000/docs ).

4. run a tiny script that wiggles antennas (from the official quickstart):

   ```python
   from reachy_mini import ReachyMini

   with ReachyMini() as mini:
       mini.goto_target(antennas=[0.5, -0.5], duration=0.5)
       mini.goto_target(antennas=[-0.5, 0.5], duration=0.5)
       mini.goto_target(antennas=[0, 0], duration=0.5)
   ```

5. only after that works on **real hardware**, layer vision / apps / LLM glue.

## official docs

- installation: https://huggingface.co/docs/reachy_mini/SDK/installation  
- quickstart: https://huggingface.co/docs/reachy_mini/SDK/quickstart  
- Python SDK: https://huggingface.co/docs/reachy_mini/SDK/python-sdk  
- simulation: https://huggingface.co/docs/reachy_mini/platforms/simulation/get_started  
- source: https://github.com/pollen-robotics/reachy_mini  

## common failure modes

- daemon not running → SDK connects to nothing useful.
- wrong connection mode (USB Lite vs Wireless network) → force only if auto
  detect fails; see upstream `connection_mode` notes.
- macOS MuJoCo sim needs `mjpython` — see sim docs.
- Git LFS missing when pulling model assets from source installs.

## safety notes

- pinch points at neck / antennas. clear the desk.
- do not leave torque-enabled motion loops running unattended.
- shared unit: do not reflash or factory-reset without crew.
- see [../safety.md](../safety.md).
