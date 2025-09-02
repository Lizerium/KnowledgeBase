---
title: Дисплей на лобовом стекле
---

:::caution

Эта страница находится в процессе разработки!

На этой странице может быть недостающая, неполная или неверная информация, так как она всё ещё находится в разработке! Относитесь к информации на ней с долей скепсиса и не стесняйтесь вносить свои предложения и исправлять ошибки!

:::

## Обзор

### Ванильные примеры

- `DATA\INTERFACE\hud.ini`

## Синтаксис

### HUD

```ini
[HUD]
shapes = PATH
```

| Параметр | Информация |
| -------- | ---------- |
| shapes   |            |

### Receiver

```ini
[Receiver]
action = STRING
shut = FLOAT, FLOAT, FLOAT
open = FLOAT, FLOAT, FLOAT
delay = FLOAT
speaker_rotate = INT, INT, INT
male_speaker_offset = FLOAT, FLOAT, FLOAT
female_speaker_offset = FLOAT, FLOAT, FLOAT
backdrop = STRING
static = INT
win_pos = FLOAT, FLOAT, FLOAT
win_size = FLOAT, FLOAT
btn_pos = FLOAT, FLOAT
fly_time = INT
tool_tip_id = INT
```

| Параметр              | Информация |
| --------------------- | ---------- |
| action                |            |
| shut                  |            |
| open                  |            |
| delay                 |            |
| speaker_rotate        |            |
| male_speaker_offset   |            |
| female_speaker_offset |            |
| backdrop              |            |
| static                |            |
| win_pos               |            |
| win_size              |            |
| btn_pos               |            |
| fly_time              |            |
| tool_tip_id           |            |

### Waypoint

Этот блок, по-видимому, пуст, не используется или не имеет известных ключей.

### Status

Этот блок, по-видимому, пуст, не используется или не имеет известных ключей.

### Target

Этот блок, по-видимому, пуст, не используется или не имеет известных ключей.

### Core

Этот блок, по-видимому, пуст, не используется или не имеет известных ключей.

### ContactList

Этот блок, по-видимому, пуст, не используется или не имеет известных ключей.

### Maneuvers

```ini
[Maneuvers]
maneuver = STRING, INT, INT, PATH, PATH
```

| Параметр | Информация |
| -------- | ---------- |
| maneuver |            |

### Steer

```ini
[Steer]
radius = INT
range = INT
color = INT, INT, INT, INT
size = INT
```

| Параметр | Информация |
| -------- | ---------- |
| radius   |            |
| range    |            |
| color    |            |
| size     |            |

### Targetable_Objects

Этот блок, по-видимому, пуст, не используется или не имеет известных ключей.

### DamageIndicator

Этот блок, по-видимому, пуст, не используется или не имеет известных ключей.

### CruiseProgress

Этот блок, по-видимому, пуст, не используется или не имеет известных ключей.
