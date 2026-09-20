# SO-ARM101

## what it is / when to pick it

open leader–follower robot arm family (SO-101 / SO-ARM10x) built to work with
**Hugging Face LeRobot**. pick it for teleoperation, imitation learning, or
any demo where a physical arm has to move on cue.

crew may say “SO ARM 101” out loud — same family as the SO-101 docs below.

## what’s in the box

typically a **leader** and **follower** arm, USB cables, and the matching
power supplies. motor voltage variants exist (**7.4 V vs 12 V** STS3215
lines). **ask crew which supplies belong to which arm** before plugging in.

TBD on the day: camera mounts, exact vendor kit (Seeed / other), calibration
IDs already burned on shared units.

## first 30 minutes

1. read the power warning in Seeed/HF docs. leader arms often use the lower
   voltage motors — **wrong PSU burns motors**.
2. install LeRobot + Feetech SDK per the SO-101 guide (do not invent versions).
3. discover serial ports for leader and follower (unplug when prompted).
4. if motors are already configured on a shared kit, **skip** `setup-motors`
   unless crew says otherwise.
5. calibrate leader and follower separately with the official
   `lerobot-calibrate` flow and stable `--teleop.id` / `--robot.id` names.
6. prove teleop **without cameras** first — one slow joint move.

example shape (ports/ids are yours — copy from upstream once ports are known):

```bash
lerobot-teleoperate \
  --robot.type=so101_follower \
  --robot.port=<FOLLOWER_PORT> \
  --robot.id=follower \
  --teleop.type=so101_leader \
  --teleop.port=<LEADER_PORT> \
  --teleop.id=leader
```

## official docs

- Hugging Face SO-101: https://huggingface.co/docs/lerobot/en/so101  
- LeRobot install: https://huggingface.co/docs/lerobot/en/installation  
- hardware / assembly upstream: https://github.com/TheRobotStudio/so-arm100  
- Seeed SO-ARM10x wiki: https://wiki.seeedstudio.com/lerobot_so100m_new/  

## common failure modes

- swapped leader/follower ports or IDs → wrong arm moves.
- wrong voltage on the motor bus → magic smoke.
- USB alone with no motor PSU → no motion / brown-outs.
- recalibrating a shared arm without noting the new `id` → next team inherits chaos.
- cameras before teleop works → debugging the wrong layer.

## safety notes

- keep hands clear of joints under torque.
- start with small motions; e-stop = cut motor power.
- do not leave teleop live pointed at people or drinks.
- see [../safety.md](../safety.md).
