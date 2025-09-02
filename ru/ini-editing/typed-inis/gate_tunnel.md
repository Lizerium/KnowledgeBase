---
title: Ворота туннеля
---

:::caution

Эта страница находится в процессе разработки!

На этой странице может быть недостающая, неполная или неверная информация, так как она всё ещё находится в разработке! Относитесь к информации на ней с долей скепсиса и не стесняйтесь вносить свои предложения и исправлять ошибки!

:::

## Обзор

### Ванильные примеры

- `DATA\FX\gate_tunnel.ini`

## Синтаксис

Блоки `[gate_tunnel]` должны быть определены до соответствующих им блоков `[layer]`.

### gate_tunnel

```ini
[gate_tunnel]
nickname = STRING
write_depth_buffer = INT
num_spline_control_points = INT
x_range = FLOAT
y_range = FLOAT
z_range = FLOAT
min_radius = FLOAT
max_radius = FLOAT
far_radius_factor = FLOAT
min_speed = FLOAT
max_speed = FLOAT
time_to_max_speed = FLOAT
fade_distance = FLOAT
near_alpha = FLOAT
far_alpha = FLOAT
num_t_steps = INT
num_s_steps = INT
min_rotation = INT
max_rotation = INT
min_rgb = INT, INT, INT
max_rgb = INT, INT, INT
```

| Параметр                  | Информация |
| ------------------------- | ---------- |
| nickname                  |            |
| write_depth_buffer        |            |
| num_spline_control_points |            |
| x_range                   |            |
| y_range                   |            |
| z_range                   |            |
| min_radius                |            |
| max_radius                |            |
| far_radius_factor         |            |
| min_speed                 |            |
| max_speed                 |            |
| time_to_max_speed         |            |
| fade_distance             |            |
| near_alpha                |            |
| far_alpha                 |            |
| num_t_steps               |            |
| num_s_steps               |            |
| min_rotation              |            |
| max_rotation              |            |
| min_rgb                   |            |
| max_rgb                   |            |

### layer

```ini
[layer]
texture = STRING
color = INT, INT, INT
near_alpha_factor = FLOAT
far_alpha_factor = FLOAT
radius_factor = FLOAT
u_offset = FLOAT
v_offset = FLOAT
du = FLOAT
dv = FLOAT
v_scale = FLOAT
```

| Параметр          | Информация |
| ----------------- | ---------- |
| texture           |            |
| color             |            |
| near_alpha_factor |            |
| far_alpha_factor  |            |
| radius_factor     |            |
| u_offset          |            |
| v_offset          |            |
| du                |            |
| dv                |            |
| v_scale           |            |
