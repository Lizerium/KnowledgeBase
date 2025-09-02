---
title: Эффект прыжка
---

:::caution

Эта страница находится в процессе разработки!

На этой странице может быть недостающая, неполная или неверная информация, так как она всё ещё находится в разработке! Относитесь к информации на ней с долей скепсиса и не стесняйтесь вносить свои предложения и исправлять ошибки!

:::

## Обзор

### Ванильные примеры

- `DATA\FX\jumpeffect.ini`

## Синтаксис

### [JumpShipEffect]

```ini
[JumpShipEffect]
jump_out_effect = STRING
jump_in_effect = STRING
```

| Параметр        | Информация |
| --------------- | ---------- |
| jump_out_effect |            |
| jump_in_effect  |            |

### [JumpGateEffect]

```ini
[JumpGateEffect]
nickname = STRING
glow_ring_effect = STRING, STRING, ...
glow_ring_hp = STRING, STRING, ...
glow_create_time = INT, INT, ...
jump_out_time = INT
jump_out_tunnel_time = INT
jump_in_tunnel_time = INT
jump_in_time = INT
kill_time_before_done = FLOAT
jump_tunnel_effect = STRING
jump_tunnel = STRING
jump_ambient = INT, INT, INT
jump_background_color = INT, INT, INT
```

| Параметр              | Информация                                                                                                                                                       |
| --------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| nickname              |                                                                                                                                                                  |
| glow_ring_effect      | Список [эффектов](./effects.md), которые должны воспроизводиться, когда корабль пристыковывается к варп-шлюзу. Похоже, что в Freelancer есть лимит в 7 эффектов. |
| glow_create_time      | Время, через которое эффекты создаются после начала стыковки корабля.                                                                                            |
| jump_out_time         | Время, необходимое, чтобы корабль вошёл в туннель после достижения HpDockMountA.                                                                                 |
| jump_out_tunnel_time  | Время до загрузки целевой системы в Freelancer.                                                                                                                  |
| jump_in_tunnel_time   | Время после загрузки до момента, когда игрок входит в целевую систему.                                                                                           |
| jump_in_time          | Время от выхода игрока из туннеля до прибытия к варп-шлюзу.                                                                                                      |
| kill_time_before_done |                                                                                                                                                                  |
| jump_tunnel_effect    | Ссылка на [эффект](./effects.md), используемый во время последовательности прыжка.                                                                               |
| jump_tunnel           | Ссылка на блок [gate_tunnel](./gate_tunnel.md), который определяет используемый туннель прыжка.                                                                  |
| jump_ambient          | RGB-значение оттенка для фонового освещения внутри туннеля прыжка.                                                                                               |
| jump_background_color | RGB-значение оттенка для "фона" туннеля прыжка.                                                                                                                  |
