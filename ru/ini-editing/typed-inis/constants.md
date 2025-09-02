---
title: Константы
---

## Оглавление

- [Оглавление](#оглавление)
  - [Обзор](#обзор)
    - [Ванильные примеры](#ванильные-примеры)
  - [Синтаксис](#синтаксис)
    - [\[Constants\]](#constants)
    - [\[EngineEquipConsts\]](#engineequipconsts)
    - [\[ShieldEquipConsts\]](#shieldequipconsts)
    - [\[PhySysConsts\]](#physysconsts)
    - [\[CommConsts\]](#commconsts)
    - [\[AsteroidConsts\]](#asteroidconsts)
    - [\[ThrusterEquipConsts\]](#thrusterequipconsts)

### Обзор

Тип ini-констант Constants хранит множество стандартных констант, используемых в игре. Благодарим _indivisible_ за нахождение дополнительных констант.

#### Ванильные примеры

- `DATA\constants.ini`

### Синтаксис

Каждый из следующих разделов можно записать только один раз, желательно в указанном порядке. Если параметр указан как необязательный, это означает, что он отсутствует в файле по умолчанию и вместо этого задаётся жёстко заданными значениями в DLL-библиотеках игры. Добавляйте необязательные значения только при необходимости.

#### [Constants]

```ini
[Constants]
COLLISION_DAMAGE_FACTOR = FLOAT
MUSIC_CROSS_FADE_DELAY = FLOAT
MUZZLE_CONE_ANGLE = FLOAT
PLAYER_COLLISION_GROUP_HIT_PTS_SCALE = FLOAT
PLAYER_ATTACHED_EQUIP_HIT_PTS_SCALE = FLOAT
MAX_PLAYER_AMMO = INT ;необязательный
FIRE_FAILED_DELAY = FLOAT ;необязательный
FIRE_FAILED_SOUND = STRING ;необязательный
SND_CARGO_JETTISONED = STRING ;необязательный
JETTISONED_CARGO_VELOCITY = FLOAT ;необязательный
LOOT_UNSEEN_RADIUS = FLOAT ;необязательный
LOOT_UNSEEN_LIFE_TIME = FLOAT ;необязательный
LOOT_OWNER_SAFE_TIME = FLOAT ;необязательный
```

| Параметр                             | Информация                                                                                                                                                                                                                                                                                                                                                                                         |
| ------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| COLLISION_DAMAGE_FACTOR              | `По умолчанию`: 0,5 (0,25, если убрать)<br/><br/> `Диапазон`: от 0 до ∞<br/><br/> Множитель произвольного значения урона от столкновения. Чем выше этот параметр, тем больше урона получат игроки при столкновении с чем-либо. NPC, похоже, не подвержены этому эффекту.                                                                                                                           |
| MUSIC_CROSS_FADE_DELAY               | `По умолчанию`: 10 (30, если удалено) <br/><br/> `Диапазон`: от 0 до ∞ <br/><br/> Время в секундах, в течение которого громкость двух музыкальных композиций постепенно увеличивается и уменьшается соответственно. Используется, например, при переключении между боевой музыкой и космической музыкой.                                                                                           |
| MUZZLE_CONE_ANGLE                    | `По умолчанию`: 40 (90, если удалено) <br/><br/> `Диапазон`: от 0 до 180 <br/><br/> Угол конуса в градусах, вокруг которого может стрелять пушка, несмотря на невозможность прямого прицеливания. Это означает, что снаряды будут стрелять под углом, если смотреть из пушки. Используйте _force_gun_ori_, чтобы переопределить это при определении пушки. Эта константа влияет только на игроков. |
| PLAYER_COLLISION_GROUP_HIT_PTS_SCALE | `По умолчанию`: 3 (1, если удалено)                                                                                                                                                                                                                                                                                                                                                                |
| PLAYER_ATTACHED_EQUIP_HIT_PTS_SCALE  | `По умолчанию`: 5 (1, если удалено)                                                                                                                                                                                                                                                                                                                                                                |
| MAX_PLAYER_AMMO                      | `По умолчанию`: 50 <br/><br/> `Диапазон`: от 0 до ∞ <br/><br/> Определяет максимальное количество боеприпасов любого типа, которое может иметь игрок. Обратите внимание, что это ограничение действует для каждого типа, поэтому для каждой ракеты, мины, крылатого дезинтегратора и т. д. будет свой лимит. Не влияет на другой груз.                                                             |
| FIRE_FAILED_DELAY                    | `По умолчанию`: 1 <br/><br/> `Диапазон`: от 0 до ∞ <br/><br/> Задержка, по истечении которой будет воспроизведен звук «огонь не удался». Используется в основном во время крейсерского плавания или на торговых путях для обозначения невозможности открытия огня.                                                                                                                                 |
| FIRE_FAILED_SOUND                    | `По умолчанию`: fire_dry <br/><br/> Псевдоним звука, воспроизводимого при стрельбе, отключен.                                                                                                                                                                                                                                                                                                      |
| SND_CARGO_JETTISONED                 | `По умолчанию`: cargo_jettison <br/><br/> Название звука, который воспроизводится при сбросе груза.                                                                                                                                                                                                                                                                                                |
| JETTISONED_CARGO_VELOCITY            | `По умолчанию`: 10 <br/><br/> `Диапазон`: от 0 до ∞ <br/><br/> Скорость, с которой груз будет выброшен из корабля.                                                                                                                                                                                                                                                                                 |
| LOOT_UNSEEN_RADIUS                   | `По умолчанию`: 2500 <br/><br/> `Диапазон`: от 0 до ∞ <br/><br/> Расстояние, на котором добыча считается «невидимой», начиная отсчет со значения, определенного ниже.                                                                                                                                                                                                                              |
| LOOT_UNSEEN_LIFE_TIME                | `По умолчанию`: 60 <br/><br/> `Диапазон`: от 0 до ∞ <br/><br/> Время, в течение которого добыча сохраняется, несмотря на то, что её «невидят», то есть на расстоянии, указанном выше. По истечении этого времени добыча исчезает.                                                                                                                                                                  |
| LOOT_OWNER_SAFE_TIME                 | `По умолчанию`: 1 <br/><br/> `Диапазон`: от 0 до ∞                                                                                                                                                                                                                                                                                                                                                 |

#### [EngineEquipConsts]

```ini
[EngineEquipConsts]
CRUISE_DISRUPT_TIME = INT
MAX_DELTA_FX_THROTTLE = FLOAT
THROTTLE_STEADY_TIME = FLOAT
THROTTLE_ATTEN_MOD_RANGE = FLOAT
DELTA_THROTTLE_ATTEN_MOD_CHANGING = FLOAT
DELTA_THROTTLE_ATTEN_MOD_STEADY = FLOAT
CRUISE_STEADY_TIME = FLOAT
DELTA_CRUISE_ATTEN_MOD_STEADY = FLOAT
CRUISE_ATTEN_MOD_RANGE = FLOAT
MAX_ENGINE_FX_THROTTLE = ? ;необязательный
CRUISE_DRAG = FLOAT? ;необязательный
CRUISE_ACCEL_TIME = FLOAT ;необязательный
CRUISING_SPEED = INT ;необязательный
```

| Параметр                          | Информация                                                                                                                                                                                                          |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| CRUISE_DISRUPT_TIME               | `По умолчанию:` 5 <br/><br/> `Диапазон: `0 до ∞ <br/><br/> Время, в течение которого крейсерская скорость отключена после попадания крейсерским разрушающим устройством.                                            |
| MAX_DELTA_FX_THROTTLE             | `По умолчанию:` 0.250000                                                                                                                                                                                            |
| THROTTLE_STEADY_TIME              | `По умолчанию:` 0.500000                                                                                                                                                                                            |
| THROTTLE_ATTEN_MOD_RANGE          | `По умолчанию:` 0.500000                                                                                                                                                                                            |
| THROTTLE_ATTEN_MOD_RANGE          | `По умолчанию:` 8.000000                                                                                                                                                                                            |
| DELTA_THROTTLE_ATTEN_MOD_CHANGING | `По умолчанию:` 8.000000                                                                                                                                                                                            |
| DELTA_THROTTLE_ATTEN_MOD_STEADY   | `По умолчанию:` -1.000000                                                                                                                                                                                           |
| CRUISE_STEADY_TIME                | `По умолчанию:` 2.000000                                                                                                                                                                                            |
| DELTA_CRUISE_ATTEN_MOD_STEADY     | `По умолчанию:` -1.000000                                                                                                                                                                                           |
| CRUISE_ATTEN_MOD_RANGE            | `По умолчанию:` 8.000000                                                                                                                                                                                            |
| MAX_ENGINE_FX_THROTTLE            | Неизвестно                                                                                                                                                                                                          |
| CRUISE_DRAG                       | `По умолчанию:` 1 <br/><br/> `Диапазон: `-128 до 128 (short) <br/><br/> Определяет изменение скорости в крейсерском режиме. Отрицательные значения вызывают замедление, большие значения — очень низкое замедление. |
| CRUISE_ACCEL_TIME                 | `Диапазон: `0 до ∞ <br/><br/> Время, за которое корабль разгоняется до крейсерской скорости. Независимо от установленной крейсерской скорости, для достижения её всегда будет затраченное это время.                |
| CRUISING_SPEED                    | `Диапазон: `0 до ∞ <br/><br/> Скорость в крейсерском режиме. Чтобы в игре отображалась настоящая скорость (по умолчанию всегда показывается 300), необходимо редактировать freelancer.exe.                          |

#### [ShieldEquipConsts]

```ini
[ShieldEquipConsts]
HULL_DAMAGE_FACTOR = FLOAT
```

| Параметр           | Информация                                                                                                                                                                                                                                                                                     |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| HULL_DAMAGE_FACTOR | `По умолчанию:` 0.500000 <br/><br/> `Диапазон: `0 до ∞ <br/><br/> Множитель урона по корпусу, который будет применяться к щитам. Это означает, что оружие фактически нанесёт `energy_damage = energy_damage + hull_damage * HULL_DAMAGE_FACTOR`, где _energy_damage_ задаётся в секции оружия. |

#### [PhySysConsts]

```ini
[PhySysConsts]
MATERIAL_FRICTION = FLOAT
MATERIAL_ELASTICITY = FLOAT
DEFAULT_LINEAR_DAMPING = FLOAT
DEFAULT_ANGULAR_DAMPING = FLOAT, FLOAT, FLOAT
RC_MAX_DELTA_ORIENTATION = ? ;необязательный
RC_MAX_DELTA_POSITION = ? ;необязательный
GOLEM_ANGULAR_DAMP_FACTOR = ? ;необязательный
GOLEM_TORQUE_FACTOR = ? ;необязательный
GOLEM_DAMP_FACTOR = ? ;необязательный
GOLEM_FORCE_FACTOR = ? ;необязательный
GOLEM_MAX_TORQUE = ? ;необязательный
GOLEM_MAX_TRANSLATION_FORCE = ? ;необязательный
GOLEM_DELTA_ORIENTATION = ? ;необязательный
GOLEM_MAX_DELTA_POSITION = ? ;необязательный
GOLEM_CHILD_ANGULAR_DAMP = ? ;необязательный
GOLEM_CHILD_LINEAR_DAMP = ? ;необязательный
GOLEM_CHILD_MASS = ? ;необязательный
RMGR_LOOK_AHEAD_MIN_SECONDS_INTRA = ? ;необязательный
RMGR_LOOK_AHEAD_MAX_DISTANCE_INTRA = ? ;необязательный
RMGR_LOOK_AHEAD_MIN_DISTANCE_INTRA = ? ;необязательный
RMGR_LOOK_AHEAD_MAX_RADIUS_INTRA = ? ; optional
RMGR_LOOK_AHEAD_TIME_INTRA = ? ;необязательный
RMGR_LOOK_AHEAD_MIN_SECONDS_WORLD = ? ;необязательный
RMGR_LOOK_AHEAD_MAX_DISTANCE_WORLD = ? ;необязательный
RMGR_LOOK_AHEAD_MIN_DISTANCE_WORLD = ? ;необязательный
RMGR_LOOK_AHEAD_MAX_RADIUS_WORLD = ? ;необязательный
RMGR_LOOK_AHEAD_TIME_WORLD = ? ;необязательный
MIN_TIME_BETWEEN_COLLISIONS = ? ;необязательный
ANOM_LIMITS_MAX_ANGULAR_VELOCITY_PER_PSI = ? ;необязательный
ANOM_LIMITS_MAX_VELOCITY = ? ;необязательный
MAX_SPAWNED_MINDIST_COUNT = ? ;необязательный
PHYSICAL_SIM_RATE = ? ;необязательный
```

| Параметр                | Информация                                   |
| ----------------------- | -------------------------------------------- |
| MATERIAL_FRICTION       | `По умолчанию:` 0.100000                     |
| MATERIAL_ELASTICITY     | `По умолчанию:` 0.900000                     |
| DEFAULT_LINEAR_DAMPING  | `По умолчанию:` 0.500000                     |
| DEFAULT_ANGULAR_DAMPING | `По умолчанию:` 0.200000, 0.200000, 0.200000 |

#### [CommConsts]

```ini
[CommConsts]
COMM_PLAYER_FAR_DIST = FLOAT
COMM_PLAYER_FAR_DIST_ATTEN = FLOAT
CHATTER_MAX_DIST = FLOAT
CHATTER_MAX_DIST_ATTEN = FLOAT
CHATTER_START_ATTEN = FLOAT
COMM_CONFLICT_PRIORITY_CUTOFF = INT
WALLA_MAX_DIST = FLOAT
WALLA_MAX_DIST_ATTEN = FLOAT
WALLA_START_ATTEN = FLOAT
WALLA_PRIORITY_CUTOFF = INT
```

| Параметр                      | Информация                                                                                                                                 |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| COMM_PLAYER_FAR_DIST          | `По умолчанию:` 6000.000000 <br/><br/> `Диапазон: `0 до ∞ <br/><br/> Расстояние, с которого игрок считается «далеко» с точки зрения связи. |
| COMM_PLAYER_FAR_ATTEN         | `По умолчанию:` 0.000000                                                                                                                   |
| CHATTER_MAX_DIST              | `По умолчанию:` 3500.000000 <br/><br/> `Диапазон: `0 до ∞ <br/><br/> Расстояние, на котором игроки не будут слышать болтовню NPC по связи. |
| CHATTER_MAX_DIST_ATTEN        | `По умолчанию:` -16.000000                                                                                                                 |
| COMM_CONFLICT_PRIORITY_CUTOFF | `По умолчанию:` -3                                                                                                                         |
| WALLA_MAX_DIST                | `По умолчанию:` 3500.000000                                                                                                                |
| WALLA_MAX_DIST_ATTEN          | `По умолчанию:` -24.000000                                                                                                                 |
| WALLA_START_ATTEN             | `По умолчанию:` -8.000000                                                                                                                  |
| WALLA_PRIORITY_CUTOFF         | `По умолчанию:` -3                                                                                                                         |

#### [AsteroidConsts]

```ini
[AsteroidConsts]
MAX_ASTEROID_LOOT_DAMAGE = FLOAT
MAX_LOOT_PER_ASTEROID = INT
```

| Параметр                 | Информация                                                                                                                                                    |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| MAX_ASTEROID_LOOT_DAMAGE | `По умолчанию:` 20000.000000 <br/><br/> `Диапазон: `0 до ∞                                                                                                    |
| MAX_LOOT_PER_ASTEROID    | `По умолчанию:` 3 <br/><br/> `Диапазон: `0 до ∞ <br/><br/> Максимальное количество добычи, которое может быть найдено в одном астероиде (при его разрушении). |

#### [ThrusterEquipConsts]

```ini

[ThrusterEquipConsts] ;необязательный
OUTSIDE_CONE_ATTENUATION = ? ;необязательный
OUTSIDE_CONE_ANGLE = ? ;необязательный
INSIDE_CONE_ANGLE = ? ;необязательный
MIN_VOLUME_FORCE = ? ;необязательный
MAX_VOLUME_FORCE = ? ;необязательный
EXTERIOR_SOUND_NAME = STRING ;необязательный
INTERIOR_SOUND_NAME = STRING ;необязательный
```

| Параметр                 | Информация  |
| ------------------------ | ----------- |
| OUTSIDE_CONE_ATTENUATION | Неизвестный |
| OUTSIDE_CONE_ANGLE       | Неизвестный |
| INSIDE_CONE_ANGLE        | Неизвестный |
| MIN_VOLUME_FORCE         | Неизвестный |
| MAX_VOLUME_FORCE         | Неизвестный |
| EXTERIOR_SOUND_NAME      | Неизвестный |
| INTERIOR_SOUND_NAME      | Неизвестный |
