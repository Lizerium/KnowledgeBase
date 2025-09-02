---
title: Basic rooms
---

## Overview
These files are used to define the room INI files present in each base, as well as the starting room when the based is loaded. Files in `DATA\UNIVERSE\SYSTEMS\INTRO\BASES\` specifically are used to define the [room](rooms.md) ini files the menu screens use.

### Vanilla Examples

* `DATA\UNIVERSE\SYSTEMS\LI01\BASES\li01_01_base.ini`
* `DATA\UNIVERSE\SYSTEMS\RH02\BASESrh02_06_base.ini`
* `DATA\UNIVERSE\SYSTEMS\INTRO\BASES\intro1_base.ini`

## Syntax

Blocks should be called in the below order. Multiple `[Room]` blocks may be called.

### BaseInfo

```ini
[BaseInfo]
nickname = STRING
start_room = STRING
ship_repair_cost = FLOAT ;optional
price_variance = FLOAT ;optional
```

| Parameter        | Information                                                                                                                                                                                                                                 |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| nickname         | How this base is referenced elsewhere.                                                                                                                                                                                                      |
| start_room       | Defines the room players start in when they dock with or log in at this base.                                                                                                                                                               |
| ship_repair_cost | Defaults to 0.33 if not specified. Affects the repair value of the ship and its groups, but not equipment. The formula is: `repair_cost = (1 - damage) * hit_pts * ship_repair_cost`. Damage is the fractional health value (75/100 = 0.75) |
| price_variance   | Picks a random number between (1 - price_variance) and (1 + price_variance) to adjust the cost of each good (equipment and commodities).                                                                                                    |

### Room

```ini
[Room]
nickname = STRING
file = PATH
```

| Parameter | Information                                         |
| --------- | --------------------------------------------------- |
| nickname  | How this room is referenced in `[BaseInfo]` blocks. |
| file      | The [Base Rooms](./rooms.md) file this entry points to.   |
