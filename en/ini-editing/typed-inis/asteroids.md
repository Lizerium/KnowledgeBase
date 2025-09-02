---
title: Asteroids
---

:::caution

This page is a work in progress!

There may be missing, incomplete or incorrect information on this page as it's still being built! Take information here with a pinch of salt, and feel free to contribute and correct things!

:::

## Overview

These files govern the properties of individual asteroids used by [asteroid field](asteroid_fields.md) ini types.

### Vanilla Examples

- `DATA\SOLAR\asteroidarch.ini`

## Syntax

Blocks can be called in any order and any number of times. Nicknames need to be unique.

### Asteroid

```ini
[Asteroid]
nickname = STRING
DA_archetype = PATH
material_library = PATH
```

| Parameter        | Information |
| ---------------- | ----------- |
| nickname         |             |
| DA_archetype     |             |
| material_library |             |

```ini
[AsteroidMine]
nickname = STRING
DA_archetype = PATH
material_library = PATH
explosion_arch = STRING
detect_radius = INT
explosion_offset = INT
recharge_time = INT
```

| Parameter        | Information                                                                                                                                                                      |
| ---------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| nickname         |                                                                                                                                                                                  |
| DA_archetype     |                                                                                                                                                                                  |
| material_library |                                                                                                                                                                                  |
| explosion_arch   | An `[Explosion]` entry defining the explosion effect and damage of the mine. Note: The damage will always be centered to the mine’s center, not where the effect will be played. |
| detect_radius    | The radius from the mine’s center within players or NPCs will trigger the explosion.                                                                                             |
| explosion_offset | The radius from the mine’s center in direction to the trigger where the `explosion_arch` (not damage!) will be rendered at.                                                      |
| recharge_time    | Delay in seconds after which another explosion can occur.                                                                                                                        |

```ini
[DynamicAsteroid]
nickname = STRING
DA_archetype = PATH
material_library = PATH
explosion_arch = STRING
```

| Parameter        | Information |
| ---------------- | ----------- |
| nickname         |             |
| DA_archetype     |             |
| material_library |             |
| explosion_arch   |             |
