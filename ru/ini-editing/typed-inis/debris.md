---
title: Обломки
---

:::caution

Эта страница находится в процессе разработки!

На этой странице может быть недостающая, неполная или неверная информация, так как она всё ещё находится в разработке! Относитесь к информации на ней с долей скепсиса и не стесняйтесь вносить свои предложения и исправлять ошибки!

:::

## Обзор

### Ванильные примеры

- `DATA\FX\explosions.ini`

## Синтаксис

### Обломки

```ini
[Debris]
nickname = STRING
death_method = STRING
lifetime = FLOAT, FLOAT
linear_drag = FLOAT
angular_drag = INT, INT, INT
trail = STRING
explosion = STRING
```

| Параметр     | Информация |
| ------------ | ---------- |
| nickname     |            |
| death_method |            |
| lifetime     |            |
| linear_drag  |            |
| angular_drag |            |
| trail        |            |
| explosion    |            |

### Explosion

```ini
[explosion]
nickname = STRING
lifetime = FLOAT, FLOAT
process = STRING
effect = STRING
debris_impulse = INT ;optional
debris_type = STRING, FLOAT ;repeatable, optional
innards_debris_start_time = INT ;optional
innards_debris_num = INT ;optional
innards_debris_radius = INT ;optional
innards_debris_object = STRING ;optional
```

| Параметр                  | Информация |
| ------------------------- | ---------- |
| nickname                  |            |
| lifetime                  |            |
| process                   |            |
| effect                    |            |
| debris_impulse            |            |
| debris_type               |            |
| innards_debris_start_time |            |
| innards_debris_num        |            |
| innards_debris_radius     |            |
| innards_debris_object     |            |

### Simple

```ini
[Simple]
nickname = STRING
DA_archetype = PATH
material_library = PATH
Mass = INT
```

| Параметр         | Информация |
| ---------------- | ---------- |
| nickname         |            |
| DA_archetype     |            |
| material_library |            |
| Mass             |            |
