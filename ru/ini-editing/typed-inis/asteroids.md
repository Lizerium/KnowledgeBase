---
title: Астероиды
---

:::caution

Эта страница находится в стадии разработки!

На этой странице может быть недостающая, неполная или неверная информация, поскольку она всё ещё находится в разработке! Относитесь к информации, представленной здесь, с долей скепсиса и не стесняйтесь вносить свои дополнения и исправлять ошибки!

:::

## Обзор

Эти файлы управляют свойствами отдельных астероидов, используемых ini-типами [Астероидные поля](asteroid_fields.md).

### Ванильные примеры

* `DATA\SOLAR\asteroidarch.ini`

## Синтаксис

Блоки можно вызывать в любом порядке и любое количество раз. Псевдонимы должны быть уникальными.

### Asteroid

```ini
[Asteroid]
nickname = STRING
DA_archetype = PATH
material_library = PATH
```

| Параметр        | Информация |
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

| Параметр        | Информация |
| ---------------- | ----------- |
| nickname         |             |
| DA_archetype     |             |
| material_library |             |
| explosion_arch   | Запись `[Explosion]`, определяющая эффект взрыва и урон мины. `Примечание`: урон всегда будет приходиться на центр мины, а не на место, где будет воспроизводиться эффект. |
| detect_radius    | Радиус от центра мины в пределах игроков или NPC вызовет взрыв. |
| explosion_offset | Радиус от центра мины в направлении к триггеру, где будет визуализироваться `explosion_arch` (не урон!). |
| recharge_time    | Задержка в несколько секунд, после которой может произойти еще один взрыв. |

```ini
[DynamicAsteroid]
nickname = STRING
DA_archetype = PATH
material_library = PATH
explosion_arch = STRING
```

| Параметр        | Информация |
| ---------------- | ----------- |
| nickname         |             |
| DA_archetype     |             |
| material_library |             |
| explosion_arch   |             |
