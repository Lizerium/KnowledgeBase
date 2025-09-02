---
title: Взрывы
---

:::caution

Эта страница находится в процессе разработки!

На этой странице может быть недостающая, неполная или неверная информация, так как она всё ещё находится в разработке! Относитесь к информации на ней с долей скепсиса и не стесняйтесь вносить свои предложения и исправлять ошибки!

:::

## Обзор

Эти файлы используются для определения взрывов и обломков, используемых при создании оружия, кораблей и солнечных батарей.

### Ванильные примеры

- `DATA\FX\explosions.ini`

## Синтаксис

### [Debris]

```ini
nickname = STRING
death_method = STRING
lifetime = FLOAT, FLOAT
linear_drag  = FLOAT
angular_drag = FLOAT, FLOAT, FLOAT
rotation_inertia = INT, INT, INT
trail = STRING
explosion = STRING
```

| Параметр         | Информация |
| ---------------- | ---------- |
| nickname         |            |
| death_method     |            |
| lifetime         |            |
| linear_drag      |            |
| angular_drag     |            |
| rotation_inertia |            |
| trail            |            |
| explosion        |            |

### [Explosion]

```ini
[Explosion]
nickname = STRING
lifetime = FLOAT
process = STRING
num_child_pieces = INT
debris_type = STRING, INT
innards_debris_start_time = FLOAT
innards_debris_num = INT
innards_debris_radius = INT
debris_impulse = INT
effect = STRING, FLOAT
innards_debris_object = STRING
```

| Параметр                  | Информация |
| ------------------------- | ---------- |
| nickname                  |            |
| lifetime                  |            |
| process                   |            |
| num_child_pieces          |            |
| debris_type               |            |
| innards_debris_start_time |            |
| innards_debris_num        |            |
| innards_debris_radius     |            |
| debris_impulse            |            |
| effect                    |            |
| innards_debris_object     |            |

### [Simple]

```ini
nickname = STRING
DA_archetype = PATH
material_library = PATH
mass = INT
```

| Параметр         | Информация |
| ---------------- | ---------- |
| nickname         |            |
| DA_archetype     |            |
| material_library |            |
| mass             |            |
