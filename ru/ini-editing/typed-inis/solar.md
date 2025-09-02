---
title: Солнечный
---

:::caution

Эта страница находится в процессе разработки!

На этой странице может быть недостающая, неполная или неверная информация, так как она всё ещё находится в разработке! Относитесь к информации на ней с долей скепсиса и не стесняйтесь вносить свои предложения и исправлять ошибки!

:::

## Обзор

### Ванильные примеры

- `DATA\SOLAR\solararch.ini`

## Синтаксис

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

| Параметр            | Информация                                                                                                                                                                                                           |
| ------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| nickname            | Внутреннее имя (никнейм) солара, то есть как он будет упоминаться в других INI-файлах игры.                                                                                                                          |
| ids_name            | Строковый ID солара.                                                                                                                                                                                                 |
| ids_info            | Текстовое описание, отображаемое игроку при использовании опции «info» для объекта солара. Можно редактировать для причальных соларов через [knowledgemap.ini](../hardcoded-inis/data/interface/knowledgemap.ini.md) |
| type                |                                                                                                                                                                                                                      |
| animated_textures   |                                                                                                                                                                                                                      |
| DA_archetype        | Путь к файлу архетипной модели, используемой для солара. Обычно это файл формата .3db или .cmp.                                                                                                                      |
| material_library    | Путь к библиотеке материалов (.mat), используемой `DA_archetype`. Отсутствие .mat-файлов приведёт к некорректному отображению солара или его частей.                                                                 |
| distance_render     |                                                                                                                                                                                                                      |
| envmap_material     |                                                                                                                                                                                                                      |
| LODRanges           |                                                                                                                                                                                                                      |
| surface_hit_effects |                                                                                                                                                                                                                      |
| mass                |                                                                                                                                                                                                                      |
| loadout             |                                                                                                                                                                                                                      |
| nomad               |                                                                                                                                                                                                                      |
| open_anim           |                                                                                                                                                                                                                      |
| open_sound          |                                                                                                                                                                                                                      |
| close_sound         |                                                                                                                                                                                                                      |
| docking_sphere      |                                                                                                                                                                                                                      |
| docking_camera      |                                                                                                                                                                                                                      |
| jump_out_hp         |                                                                                                                                                                                                                      |
| solar_radius        |                                                                                                                                                                                                                      |
| shape_name          |                                                                                                                                                                                                                      |
| shield_link         |                                                                                                                                                                                                                      |
| explosion_arch      |                                                                                                                                                                                                                      |
| destructible        |                                                                                                                                                                                                                      |
| hit_pts             |                                                                                                                                                                                                                      |
| fuse                |                                                                                                                                                                                                                      |
| phantom_physics     | Определяет, может ли игрок взаимодействовать с солнечными батареями. Если установлено значение true, игрок будет игнорировать хитбоксы моделей.                                                                      |

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

| Параметр             | Информация |
| -------------------- | ---------- |
| obj                  |            |
| separable            |            |
| parent_impulse       |            |
| child_impulse        |            |
| dmg_hp               |            |
| dmg_obj              |            |
| mass                 |            |
| fuse                 |            |
| group_dmg_hp         |            |
| group_dmg_obj        |            |
| debris_type          |            |
| separation_explosion |            |
| type                 |            |
| hit_pts              |            |
| root_health_proxy    |            |
| explosion_resistance |            |
