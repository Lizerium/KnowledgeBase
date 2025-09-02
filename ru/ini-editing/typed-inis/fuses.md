---
title: Взрыватели
---

:::caution

Эта страница находится в процессе разработки!

На этой странице может быть недостающая, неполная или неверная информация, так как она всё ещё находится в разработке! Относитесь к информации на ней с долей скепсиса и не стесняйтесь вносить свои предложения и исправлять ошибки!

:::

## Оглавление

- [Оглавление](#оглавление)
  - [Обзор](#обзор)
    - [Ванильные примеры](#ванильные-примеры)
  - [Синтаксис](#синтаксис)
    - [fuse](#fuse)
    - [ignite_fuse](#ignite_fuse)
    - [destroy_group](#destroy_group)
    - [destroy_root](#destroy_root)
    - [destroy_hp_attachment](#destroy_hp_attachment)
    - [start_effect](#start_effect)
    - [start_cam_particles](#start_cam_particles)
    - [impulse](#impulse)
    - [damage_group](#damage_group)
    - [damage_root](#damage_root)

### Обзор

#### Ванильные примеры

- `DATA\FX\fuse_freeport7.ini`
- `DATA\FX\fuse.ini`
- `DATA\FX\fuse_suprise_solar.ini`
- `DATA\FX\fuse_li_dreadnought.ini`

### Синтаксис

#### fuse

```ini
[fuse]
name = STRING
lifetime = INT
death_fuse = BOOL
```

| Параметр   | Информация |
| ---------- | ---------- |
| name       |            |
| lifetime   |            |
| death_fuse |            |

#### ignite_fuse

```ini
[ignite_fuse]
at_t = FLOAT
fuse = STRING
fuse_t = INT
```

| Параметр | Информация |
| -------- | ---------- |
| at_t     |            |
| fuse     |            |
| fuse_t   |            |

#### destroy_group

```ini
[destroy_group]
at_t = FLOAT
group_name = STRING
fate = STRING
```

| Параметр   | Информация |
| ---------- | ---------- |
| at_t       |            |
| group_name |            |
| fate       |            |

#### destroy_root

```ini
[destroy_root]
at_t = INT
```

| Параметр | Информация |
| -------- | ---------- |
| at_t     |            |

#### destroy_hp_attachment

```ini
[destroy_hp_attachment]
at_t = FLOAT
hardpoint = STRING
fate = STRING
```

| Параметр  | Информация |
| --------- | ---------- |
| at_t      |            |
| hardpoint |            |
| fate      |            |

#### start_effect

```ini
[start_effect]
effect = STRING
hardpoint = STRING
at_t = FLOAT
pos_offset = INT, INT, INT
ori_offset = INT, INT, INT
attached = BOOL
```

| Параметр   | Информация |
| ---------- | ---------- |
| effect     |            |
| hardpoint  |            |
| at_t       |            |
| pos_offset |            |
| ori_offset |            |
| attached   |            |

#### start_cam_particles

```ini
[start_cam_particles]
effect = STRING
at_t = FLOAT
pos_offset = INT, INT, INT
ori_offset = INT, INT, INT
```

| Параметр   | Информация |
| ---------- | ---------- |
| effect     |            |
| at_t       |            |
| pos_offset |            |
| ori_offset |            |

#### impulse

```ini
[impulse]
at_t = FLOAT
hardpoint = STRING
pos_offset = INT, INT, INT
radius = INT
force = INT
damage = INT
```

| Параметр   | Информация |
| ---------- | ---------- |
| at_t       |            |
| hardpoint  |            |
| pos_offset |            |
| radius     |            |
| force      |            |
| damage     |            |

#### damage_group

```ini
[damage_group]
group_name = STRING
at_t = FLOAT
damage_type = STRING
hitpoints = INT
```

| Параметр    | Информация |
| ----------- | ---------- |
| group_name  |            |
| at_t        |            |
| damage_type |            |
| hitpoints   |            |

#### damage_root

```ini
[damage_root]
at_t = FLOAT
damage_type = STRING
hitpoints = INT
```

| Параметр    | Информация |
| ----------- | ---------- |
| at_t        |            |
| damage_type |            |
| hitpoints   |            |
