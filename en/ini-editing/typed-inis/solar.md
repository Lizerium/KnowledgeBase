---
title: Solar
---

:::caution

This page is a work in progress!

There may be missing, incomplete or incorrect information on this page as it's still being built! Take information here with a pinch of salt, and feel free to contribute and correct things!

:::

## Overview

### Vanilla Examples

- `DATA\SOLAR\solararch.ini`

## Syntax

### Solar

```ini
[Solar]
nickname = STRING
ids_name = INT
ids_info = INT
type = STRING
animated_textures = BOOL
DA_archetype = PATH
material_library = PATH
distance_render = INT
envmap_material = STRING
LODRanges = INT, INT, ...
surface_hit_effects = INT, STRING, STRING, STRING
mass = FLOAT
loadout = STRING
nomad = BOOL
open_anim = STRING
open_sound = STRING
close_sound = STRING
docking_sphere = STRING, STRING, INT, STRING
docking_camera = INT
jump_out_hp = STRING
solar_radius = INT
shape_name = STRING
shield_link = STRING, STRING, STRING
explosion_arch = STRING
destructible = BOOL
hit_pts = INT
fuse = STRING, INT, INT
phantom_physics = BOOL

```

| Parameter           | Information                                                                                                                                                                                                  |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| nickname            | The internal nickname of the solar, i.e. how this will be referred to elsewhere in the game's INI files.                                                                                                     |
| ids_name            | The string ID name of the solar.                                                                                                                                                                             |
| ids_info            | The flavor text displayed when a player uses the 'info' option on a solar entity. This can be manipulated for dockable solars using [knowledgemap.ini](../hardcoded-inis/data/interface/knowledgemap.ini.md) |
| type                |                                                                                                                                                                                                              |
| animated_textures   |                                                                                                                                                                                                              |
| DA_archetype        | The path to the archetype model to use for the solar. Typically a .3db or .cmp file.                                                                                                                         |
| material_library    | The path to a material library (.mat) file that the `DA_archetype` uses. Missing .mat files will cause the solar, or parts of the model to render inconsistently.                                            |
| distance_render     |                                                                                                                                                                                                              |
| envmap_material     |                                                                                                                                                                                                              |
| LODRanges           |                                                                                                                                                                                                              |
| surface_hit_effects |                                                                                                                                                                                                              |
| mass                |                                                                                                                                                                                                              |
| loadout             |                                                                                                                                                                                                              |
| nomad               |                                                                                                                                                                                                              |
| open_anim           |                                                                                                                                                                                                              |
| open_sound          |                                                                                                                                                                                                              |
| close_sound         |                                                                                                                                                                                                              |
| docking_sphere      |                                                                                                                                                                                                              |
| docking_camera      |                                                                                                                                                                                                              |
| jump_out_hp         |                                                                                                                                                                                                              |
| solar_radius        |                                                                                                                                                                                                              |
| shape_name          |                                                                                                                                                                                                              |
| shield_link         |                                                                                                                                                                                                              |
| explosion_arch      |                                                                                                                                                                                                              |
| destructible        |                                                                                                                                                                                                              |
| hit_pts             |                                                                                                                                                                                                              |
| fuse                |                                                                                                                                                                                                              |
| phantom_physics     | Determines whether or not the player is able to interact with the solar. If this is set to true, the player will ignore model hitboxes.                                                                      |

### CollisionGroup

```ini
[CollisionGroup]
obj = STRING
separable
parent_impulse = INT
child_impulse = INT
dmg_hp = STRING
dmg_obj = STRING
mass = INT
fuse = STRING, INT, INT
group_dmg_hp = STRING
group_dmg_obj = STRING
debris_type = STRING
separation_explosion = STRING
type = STRING
hit_pts = INT
root_health_proxy = BOOL
explosion_resistance = FLOAT
```

| Parameter            | Information |
| -------------------- | ----------- |
| obj                  |             |
| separable            |             |
| parent_impulse       |             |
| child_impulse        |             |
| dmg_hp               |             |
| dmg_obj              |             |
| mass                 |             |
| fuse                 |             |
| group_dmg_hp         |             |
| group_dmg_obj        |             |
| debris_type          |             |
| separation_explosion |             |
| type                 |             |
| hit_pts              |             |
| root_health_proxy    |             |
| explosion_resistance |             |
