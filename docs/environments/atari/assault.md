---
title: Assault
---

# Assault

```{figure} ../../_static/videos/atari/assault.gif
:width: 120px
:name: Assault
```

This environment is part of the <a href='..'>Atari environments</a>. Please read that page first for general information.

## Description

You control a vehicle that can move sideways. A big mother ship circles overhead and continually deploys smaller drones.You must destroy these enemies and dodge their attacks.

For a more detailed documentation, see [the AtariAge page](https://atariage.com/manual_html_page.php?SoftwareID=827)

## Actions

Assault has the action space `Discrete(7)` with the table below lists the meaning of each action's meanings.
As Assault uses a reduced set of actions for `v0`, `v4` and `v5` versions of the environment.
To enable all 18 possible actions that can be performed on an Atari 2600, specify `full_action_space=True` during
initialization or by passing `full_action_space=True` to `gymnasium.make`.

| Value   | Meaning     |
|---------|-------------|
| `0`     | `NOOP`      |
| `1`     | `FIRE`      |
| `2`     | `UP`        |
| `3`     | `RIGHT`     |
| `4`     | `LEFT`      |
| `5`     | `RIGHTFIRE` |
| `6`     | `LEFTFIRE`  |

## Observations

Atari environment have two possible observation types, the observation space is listed below.
See variants section for the type of observation used by each environment id.

- `obs_type="rgb" -> observation_space=Box(0, 255, (210, 160, 3), np.uint8)`
- `obs_type="ram" -> observation_space=Box(0, 255, (128,), np.uint8)`

Additionally, `obs_type="grayscale"` cause the environment return a grayscale version of the rgb array for observations with the observation space being `Box(0, 255, (210, 160), np.uint8)`

## Variants

Assault has the following variants of the environment id which have the following differences in observation,
the number of frame-skips and the repeat action probability.

| Env-id                      | obs_type=   | frameskip=   | repeat_action_probability=   |
|-----------------------------|-------------|--------------|------------------------------|
| Assault-v0                  | `"rgb"`     | `(2, 5)`     | `0.25`                       |
| Assault-ram-v0              | `"ram"`     | `(2, 5)`     | `0.25`                       |
| Assault-ramDeterministic-v0 | `"ram"`     | `4`          | `0.25`                       |
| Assault-ramNoFrameskip-v0   | `"ram"`     | `1`          | `0.25`                       |
| AssaultDeterministic-v0     | `"rgb"`     | `4`          | `0.25`                       |
| AssaultNoFrameskip-v0       | `"rgb"`     | `1`          | `0.25`                       |
| Assault-v4                  | `"rgb"`     | `(2, 5)`     | `0.0`                        |
| Assault-ram-v4              | `"ram"`     | `(2, 5)`     | `0.0`                        |
| Assault-ramDeterministic-v4 | `"ram"`     | `4`          | `0.0`                        |
| Assault-ramNoFrameskip-v4   | `"ram"`     | `1`          | `0.0`                        |
| AssaultDeterministic-v4     | `"rgb"`     | `4`          | `0.0`                        |
| AssaultNoFrameskip-v4       | `"rgb"`     | `1`          | `0.0`                        |
| ALE/Assault-v5              | `"rgb"`     | `4`          | `0.25`                       |
| ALE/Assault-ram-v5          | `"ram"`     | `4`          | `0.25`                       |

## Difficulty and modes

It is possible to specify various flavors of the environment via the keyword arguments `difficulty` and `mode`.
A flavor is a combination of a game mode and a difficulty setting. The table below lists the possible difficulty and mode values
along with the default values.

| Available Modes   | Default Mode   | Available Difficulties   | Default Difficulty   |
|-------------------|----------------|--------------------------|----------------------|
| `[0]`             | `0`            | `[0]`                    | `0`                  |

## Version History

A thorough discussion of the intricate differences between the versions and configurations can be found in the general article on Atari environments.

* v5: Stickiness was added back and stochastic frameskipping was removed. The environments are now in the "ALE" namespace.
* v4: Stickiness of actions was removed
* v0: Initial versions release