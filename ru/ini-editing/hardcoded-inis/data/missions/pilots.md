---
title: Пилоты NPC
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
    - [\[EvadeDodgeBlock\]](#evadedodgeblock)
    - [\[EvadeBreakBlock\]](#evadebreakblock)
    - [\[BuzzHeadTowardBlock\]](#buzzheadtowardblock)
    - [\[BuzzPassByBlock\]](#buzzpassbyblock)
    - [\[TrailBlock\]](#trailblock)
    - [\[StrafeBlock\]](#strafeblock)
    - [\[EngineKillBlock\]](#enginekillblock)
    - [\[RepairBlock\]](#repairblock)
    - [\[GunBlock\]](#gunblock)
    - [\[MissileBlock\]](#missileblock)
    - [\[DamageReactionBlock\]](#damagereactionblock)
    - [\[CountermeasureBlock\]](#countermeasureblock)
    - [\[FormationBlock\]](#formationblock)
    - [\[JobBlock\]](#jobblock)
    - [\[Pilot\]](#pilot)

### Обзор

Этот файл определяет поведение пилота NPC в бою.

#### Ванильные примеры

- `DATA\MISSIONS\pilots_population.ini`

### Синтаксис

Каждый блок может быть определен несколько раз.

#### [EvadeDodgeBlock]

```ini
[EvadeDodgeBlock]
nickname = STRING
evade_dodge_style_weight = STRING, INT ;Multiple
evade_dodge_cone_angle = INT
evade_dodge_interval_time = INT
evade_dodge_time = INT
evade_dodge_distance = INT
evade_activate_range = INT
evade_dodge_roll_angle = INT
evade_dodge_waggle_axis_cone_angle = INT
evade_dodge_slide_throttle = INT
evade_dodge_turn_throttle = INT
evade_dodge_corkscrew_turn_throttle = FLOAT
evade_dodge_corkscrew_roll_throttle = INT
evade_dodge_corkscrew_roll_flip_direction = BOOL
evade_dodge_interval_time_variance_percent = FLOAT
evade_dodge_cone_angle_variance_percent = FLOAT
evade_dodge_direction_weight = STRING, FLOAT ;multiple
```

| Параметр                                       | Описание                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| ---------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **nickname**                                   | Как эта запись называется или на неё ссылаются в других местах.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| **evade_dodge_style_weight**                   | Принимает стиль уклонения (`waggle`, `waggle_random`, `slide` и `corkscrew`) и вес, определяющий поведение NPC при переходе в состояние `EVADE`.<br/>`waggle`: промежуточный вариант между `waggle_random` и `corkscrew`.<br/>`waggle_random`: случайный, резкий. Очень сильное и непредсказуемое защитное поведение, особенно против слабых пилотов.<br/>`slide`: отключение двигателя, дрейф и надежда на лучшее. Фактически намеренная ошибка, чтобы ИИ был смертным.<br/>`corkscrew`: длинные плавные кривые. Сильное, если защитник легче атакующего, слабое при равном весе, так как движение предсказуемо. |
| **evade_dodge_cone_angle**                     | Принимает значение в радианах (float). Наличие врага в этом конусе и в пределах `evade_activate_range` переводит пилота в поведение `EVADE`.                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| **evade_dodge_interval_time**                  | Возможно, минимальная продолжительность фазы `EVADE`, не прерываемой переходом в `TRAIL`/`FACE`/`BUZZ`. Например, установка этого параметра и `evade_dodge_time` в 100 делает уклонения бесконечными, установка `evade_dodge_interval_time` в 100 и `evade_dodge_time` в 3 — нет.                                                                                                                                                                                                                                                                                                                                 |
| **evade_dodge_time**                           | Максимальное время, которое пилот проводит в одной фазе `EVADE`.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **evade_dodge_distance**                       | Пилот будет уклоняться, пока не пройдёт указанное расстояние от цели. После завершения уклонения оно не повторяется, пока дистанция не будет снова пересечена.                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **evade_activate_range**                       | Наличие противника в конусе и в пределах этого радиуса переключает пилота в `EVADE`. Меньший радиус делает противника более агрессивным, больший — чаще заставляет защищаться.                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **evade_dodge_roll_angle**                     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| **evade_dodge_waggle_axis_cone_angle**         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| **evade_dodge_slide_throttle**                 | По-видимому, ничего не делает, если установить 1.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **evade_dodge_turn_throttle**                  | Установка в 0 делает все уклонения прямыми. Значение не превышает 1.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| **evade_dodge_corkscrew_turn_throttle**        | Установка в 0 делает `corkscrew` прямым и неэффективным. Значение не превышает 1.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **evade_dodge_corkscrew_roll_throttle**        | Установка в 0 делает `corkscrew` прямым и неэффективным. Значение не превышает 1.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **evade_dodge_corkscrew_roll_flip_direction**  | Вероятно, делает манёвр более «жарким». Эффект неясен.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| **evade_dodge_interval_time_variance_percent** |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| **evade_dodge_cone_angle_variance_percent**    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| **evade_dodge_direction_weight**               | Задает вес направления, в котором выполняются уклонения (возможно, не актуально для случайного `waggle`). Шансы могут быть слегка смещены. Из-за интерфейса уклонение вниз заставляет ИИ чаще стрелять по игрокам. Варианты: `left`, `right`, `up`, `down`.                                                                                                                                                                                                                                                                                                                                                       |

#### [EvadeBreakBlock]

```ini
[EvadeBreakBlock]
nickname = STRING
evade_break_roll_throttle = FLOAT
evade_break_time = INT
evade_break_interval_time = FLOAT
evade_break_afterburner_delay = INT
evade_break_afterburner_delay_variance_percent = INT
evade_break_attempt_reverse_time = INT
evade_break_reverse_distance = INT
evade_break_turn_throttle = INT
evade_break_direction_weight = STRING, INT
evade_break_direction_weight = STRING, INT
evade_break_style_weight = STRING, INT
evade_break_style_weight = STRING, INT
```

| Параметр                                       | Описание                                   |
| ---------------------------------------------- | ------------------------------------------ |
| nickname                                       | Как эта запись упоминается в другом месте. |
| evade_break_roll_throttle                      |                                            |
| evade_break_time                               |                                            |
| evade_break_interval_time                      |                                            |
| evade_break_afterburner_delay                  |                                            |
| evade_break_afterburner_delay_variance_percent |                                            |
| evade_break_attempt_reverse_time               |                                            |
| evade_break_reverse_distance                   |                                            |
| evade_break_turn_throttle                      |                                            |
| evade_break_direction_weight                   |                                            |
| evade_break_style_weight                       |                                            |

#### [BuzzHeadTowardBlock]

```ini
[BuzzHeadTowardBlock]
nickname = STRING
buzz_min_distance_to_head_toward = INT
buzz_min_distance_to_head_toward_variance_percent = FLOAT
buzz_max_time_to_head_away = INT
buzz_head_toward_engine_throttle = FLOAT
buzz_head_toward_turn_throttle = INT
buzz_head_toward_roll_throttle = INT
buzz_slide_throttle = INT
buzz_slide_interval_time = INT
buzz_slide_interval_time_variance_percent = FLOAT
buzz_dodge_turn_throttle = INT
buzz_dodge_cone_angle = INT
buzz_dodge_cone_angle_variance_percent = FLOAT
buzz_dodge_waggle_axis_cone_angle = INT
buzz_dodge_roll_angle = INT
buzz_dodge_interval_time = INT
buzz_dodge_interval_time_variance_percent = FLOAT
buzz_dodge_direction_weight = STRING, FLOAT
buzz_dodge_direction_weight = STRING, FLOAT
buzz_head_toward_style_weight = STRING, INT
```

| Параметр                                          | Описание                                   |
| ------------------------------------------------- | ------------------------------------------ |
| nickname                                          | Как эта запись упоминается в другом месте. |
| buzz_min_distance_to_head_toward                  |                                            |
| buzz_min_distance_to_head_toward_variance_percent |                                            |
| buzz_max_time_to_head_away                        |                                            |
| buzz_head_toward_engine_throttle                  |                                            |
| buzz_head_toward_turn_throttle                    |                                            |
| buzz_head_toward_roll_throttle                    |                                            |
| buzz_slide_throttle                               |                                            |
| buzz_slide_interval_time                          |                                            |
| buzz_slide_interval_time_variance_percent         |                                            |
| buzz_dodge_turn_throttle                          |                                            |
| buzz_dodge_cone_angle                             |                                            |
| buzz_dodge_cone_angle_variance_percent            |                                            |
| buzz_dodge_waggle_axis_cone_angle                 |                                            |
| buzz_dodge_roll_angle                             |                                            |
| buzz_dodge_interval_time                          |                                            |
| buzz_dodge_interval_time_variance_percent         |                                            |
| buzz_dodge_direction_weight                       |                                            |
| buzz_head_toward_style_weight                     |                                            |

#### [BuzzPassByBlock]

```ini
[BuzzPassByBlock]
nickname = STRING
buzz_distance_to_pass_by = INT
buzz_pass_by_time = INT
buzz_break_direction_cone_angle = INT
buzz_break_turn_throttle = FLOAT
buzz_pass_by_roll_throttle = INT
buzz_drop_bomb_on_pass_by = BOOL
buzz_break_direction_weight = STRING, INT
buzz_pass_by_style_weight = STRING, INT
```

| Параметр                        | Описание                                   |
| ------------------------------- | ------------------------------------------ |
| nickname                        | Как эта запись упоминается в другом месте. |
| buzz_distance_to_pass_by        |                                            |
| buzz_pass_by_time               |                                            |
| buzz_break_direction_cone_angle |                                            |
| buzz_break_turn_throttle        |                                            |
| buzz_pass_by_roll_throttle      |                                            |
| buzz_drop_bomb_on_pass_by       |                                            |
| buzz_break_direction_weight     |                                            |
| buzz_pass_by_style_weight       |                                            |

#### [TrailBlock]

```ini
[TrailBlock]
nickname = STRING
trail_lock_cone_angle = INT
trail_break_time = FLOAT
trail_min_no_lock_time = INT
trail_break_roll_throttle = INT
trail_break_afterburner = BOOL
trail_max_turn_throttle = FLOAT
trail_distance = INT
```

| Параметр                  | Описание                                   |
| ------------------------- | ------------------------------------------ |
| nickname                  | Как эта запись упоминается в другом месте. |
| trail_lock_cone_angle     |                                            |
| trail_break_time          |                                            |
| trail_min_no_lock_time    |                                            |
| trail_break_roll_throttle |                                            |
| trail_break_afterburner   |                                            |
| trail_max_turn_throttle   |                                            |
| trail_distance            |                                            |

#### [StrafeBlock]

```ini
[StrafeBlock]
nickname = STRING
strafe_run_away_distance = INT
strafe_attack_throttle = INT
```

| Параметр                 | Описание                                   |
| ------------------------ | ------------------------------------------ |
| nickname                 | Как эта запись упоминается в другом месте. |
| strafe_run_away_distance |                                            |
| strafe_attack_throttle   |                                            |

#### [EngineKillBlock]

```ini
[EngineKillBlock]
nickname = STRING
engine_kill_search_time = INT
engine_kill_face_time = INT
engine_kill_use_afterburner = BOOL
engine_kill_afterburner_time = INT
engine_kill_max_target_distance = INT
```

| Параметр                        | Описание                                   |
| ------------------------------- | ------------------------------------------ |
| nickname                        | Как эта запись упоминается в другом месте. |
| engine_kill_search_time         |                                            |
| engine_kill_face_time           |                                            |
| engine_kill_use_afterburner     |                                            |
| engine_kill_afterburner_time    |                                            |
| engine_kill_max_target_distance |                                            |

#### [RepairBlock]

```ini
[RepairBlock]
nickname = STRING
use_shield_repair_pre_delay = INT
use_shield_repair_post_delay = INT
use_shield_repair_at_damage_percent = INT
use_hull_repair_pre_delay = INT
use_hull_repair_post_delay = INT
use_hull_repair_at_damage_percent = INT
```

| Параметр                            | Описание                                   |
| ----------------------------------- | ------------------------------------------ |
| nickname                            | Как эта запись упоминается в другом месте. |
| use_shield_repair_pre_delay         |                                            |
| use_shield_repair_post_delay        |                                            |
| use_shield_repair_at_damage_percent |                                            |
| use_hull_repair_pre_delay           |                                            |
| use_hull_repair_post_delay          |                                            |
| use_hull_repair_at_damage_percent   |                                            |

#### [GunBlock]

Это определяет поведение NPC при стрельбе из обычного оружия. Солнечные пушки используют только значения с префиксом `auto_turret` и требуют установки `auto_turret = true` для оружия.

```ini
[GunBlock]
nickname = STRING
gun_fire_interval_time = FLOAT
gun_fire_interval_variance_percent = FLOAT
gun_fire_burst_interval_time = INT
gun_fire_burst_interval_variance_percent = FLOAT
gun_fire_no_burst_interval_time = INT
gun_fire_accuracy_cone_angle = INT
gun_fire_accuracy_power = INT
gun_fire_accuracy_power_npc = INT
gun_range_threshold = FLOAT
gun_target_point_switch_time = INT
gun_range_threshold_variance_percent = FLOAT
fire_style = STRING
auto_turret_interval_time = FLOAT
auto_turret_burst_interval_time = INT
auto_turret_no_burst_interval_time = INT
auto_turret_burst_interval_variance_percent = FLOAT
```

| Parameter                                   | Information                                                                                                                                                                                             |
| ------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| nickname                                    | Как эта запись упоминается в другом месте.                                                                                                                                                              |
| gun_fire_interval_time                      |                                                                                                                                                                                                         |
| gun_fire_interval_variance_percent          |                                                                                                                                                                                                         |
| gun_fire_burst_interval_time                |                                                                                                                                                                                                         |
| gun_fire_burst_interval_variance_percent    |                                                                                                                                                                                                         |
| gun_fire_no_burst_interval_time             |                                                                                                                                                                                                         |
| gun_fire_accuracy_cone_angle                |                                                                                                                                                                                                         |
| gun_fire_accuracy_power                     |                                                                                                                                                                                                         |
| gun_fire_accuracy_power_npc                 |                                                                                                                                                                                                         |
| gun_range_threshold                         |                                                                                                                                                                                                         |
| gun_target_point_switch_time                |                                                                                                                                                                                                         |
| gun_range_threshold_variance_percent        |                                                                                                                                                                                                         |
| fire_style                                  | Варианты: `single` или `multiple`. `single` запрещает NPC стрелять более чем одним оружием одновременно. `multiple` — стандартное поведение ванили, при котором NPC стреляют из своего оружия свободно. |
| auto_turret_interval_time                   |                                                                                                                                                                                                         |
| auto_turret_burst_interval_time             |                                                                                                                                                                                                         |
| auto_turret_no_burst_interval_time          |                                                                                                                                                                                                         |
| auto_turret_burst_interval_variance_percent |                                                                                                                                                                                                         |

#### [MissileBlock]

```ini
[MissileBlock]
nickname = STRING
missile_launch_interval_time = INT
missile_launch_interval_variance_percent = FLOAT
missile_launch_range = INT
missile_launch_cone_angle = INT
missile_launch_allow_out_of_range = BOOL
```

| Параметр                                 | Описание                                   |
| ---------------------------------------- | ------------------------------------------ |
| nickname                                 | Как эта запись упоминается в другом месте. |
| missile_launch_interval_time             |                                            |
| missile_launch_interval_variance_percent |                                            |
| missile_launch_range                     |                                            |
| missile_launch_cone_angle                |                                            |
| missile_launch_allow_out_of_range        |                                            |

#### [DamageReactionBlock]

```ini
[DamageReactionBlock]
nickname = STRING
evade_break_damage_trigger_percent = FLOAT
evade_dodge_more_damage_trigger_percent = FLOAT
engine_kill_face_damage_trigger_percent = INT
engine_kill_face_damage_trigger_time = INT
roll_damage_trigger_percent = FLOAT
roll_damage_trigger_time = INT
afterburner_damage_trigger_percent = FLOAT
afterburner_damage_trigger_time = FLOAT
brake_reverse_damage_trigger_percent = INT
drop_mines_damage_trigger_percent = FLOAT
drop_mines_damage_trigger_time = FLOAT
fire_guns_damage_trigger_percent = INT
fire_guns_damage_trigger_time = INT
fire_missiles_damage_trigger_percent = INT
fire_missiles_damage_trigger_time = INT
```

| Параметр                                | Описание                                   |
| --------------------------------------- | ------------------------------------------ |
| nickname                                | Как эта запись упоминается в другом месте. |
| evade_break_damage_trigger_percent      |                                            |
| evade_dodge_more_damage_trigger_percent |                                            |
| engine_kill_face_damage_trigger_percent |                                            |
| engine_kill_face_damage_trigger_time    |                                            |
| roll_damage_trigger_percent             |                                            |
| roll_damage_trigger_time                |                                            |
| afterburner_damage_trigger_percent      |                                            |
| afterburner_damage_trigger_time         |                                            |
| brake_reverse_damage_trigger_percent    |                                            |
| drop_mines_damage_trigger_percent       |                                            |
| drop_mines_damage_trigger_time          |                                            |
| fire_guns_damage_trigger_percent        |                                            |
| fire_guns_damage_trigger_time           |                                            |
| fire_missiles_damage_trigger_percent    |                                            |
| fire_missiles_damage_trigger_time       |                                            |

#### [CountermeasureBlock]

```ini
[CountermeasureBlock]
nickname = STRING
countermeasure_active_time = INT
countermeasure_unactive_time = INT
```

| Параметр                     | Описание                                   |
| ---------------------------- | ------------------------------------------ |
| nickname                     | Как эта запись упоминается в другом месте. |
| countermeasure_active_time   |                                            |
| countermeasure_unactive_time |                                            |

#### [FormationBlock]

```ini
[FormationBlock]
nickname = formation_fighter_test
countermeasure_unactive_time = INT
force_attack_formation_unactive_time = INT
break_formation_damage_trigger_percent = FLOAT
break_formation_damage_trigger_time = INT
break_formation_missile_reaction_time = INT
break_apart_formation_missile_reaction_time = INT
break_apart_formation_on_evade_break = BOOL
break_formation_on_evade_break_time = INT
formation_exit_top_turn_break_away_throttle = INT
formation_exit_roll_outrun_throttle = INT
formation_exit_max_time = INT
```

| Параметр                                    | Описание                                   |
| ------------------------------------------- | ------------------------------------------ |
| nickname                                    | Как эта запись упоминается в другом месте. |
| countermeasure_unactive_time                |                                            |
| force_attack_formation_unactive_time        |                                            |
| break_formation_damage_trigger_percent      |                                            |
| break_formation_damage_trigger_time         |                                            |
| break_formation_missile_reaction_time       |                                            |
| break_apart_formation_missile_reaction_time |                                            |
| break_apart_formation_on_evade_break        |                                            |
| break_formation_on_evade_break_time         |                                            |
| formation_exit_top_turn_break_away_throttle |                                            |
| formation_exit_roll_outrun_throttle         |                                            |
| formation_exit_max_time                     |                                            |

#### [JobBlock]

```ini
[JobBlock]
nickname = STRING
wait_for_leader_target = BOOL
maximum_leader_target_distance = INT
flee_when_leader_flees_style = BOOL
scene_toughness_threshold = STRING
flee_scene_threat_style = STRING
flee_when_hull_damaged_percent = INT
flee_no_weapons_style = BOOL
loot_flee_threshold = STRING
attack_subtarget_order = STRING
field_targeting = STRING
loot_preference = STRING
force_attack_formation = BOOL
combat_drift_distance = INT
attack_preference = STRING, INT, BITFIELD

```

| Параметр                       | Описание                                   |
| ------------------------------ | ------------------------------------------ |
| nickname                       | Как эта запись упоминается в другом месте. |
| wait_for_leader_target         |                                            |
| maximum_leader_target_distance |                                            |
| flee_when_leader_flees_style   |                                            |
| scene_toughness_threshold      |                                            |
| flee_scene_threat_style        |                                            |
| flee_when_hull_damaged_percent |                                            |
| flee_no_weapons_style          |                                            |
| loot_flee_threshold            |                                            |
| attack_subtarget_order         |                                            |
| field_targeting                |                                            |
| loot_preference                |                                            |
| force_attack_formation         |                                            |
| combat_drift_distance          |                                            |
| attack_preference              |                                            |

#### [Pilot]

```ini
[Pilot]
nickname = STRING
inherit = STRING
gun_id = STRING
missile_id = STRING
evade_dodge_id = STRING
evade_break_id = STRING
buzz_head_toward_id = STRING
buzz_pass_by_id = STRING
trail_id = STRING
strafe_id = STRING
engine_kill_id = STRING
mine_id = STRING
countermeasure_id = STRING
damage_reaction_id = STRING
missile_reaction_id = STRING
formation_id = STRING
repair_id = STRING
job_id = STRING
```

| Параметр            | Описание                                   |
| ------------------- | ------------------------------------------ |
| nickname            | Как эта запись упоминается в другом месте. |
| inherit             |                                            |
| gun_id              |                                            |
| missile_id          |                                            |
| evade_dodge_id      |                                            |
| evade_break_id      |                                            |
| buzz_head_toward_id |                                            |
| buzz_pass_by_id     |                                            |
| trail_id            |                                            |
| strafe_id           |                                            |
| engine_kill_id      |                                            |
| mine_id             |                                            |
| countermeasure_id   |                                            |
| damage_reaction_id  |                                            |
| missile_reaction_id |                                            |
| formation_id        |                                            |
| repair_id           |                                            |
| job_id              |                                            |
