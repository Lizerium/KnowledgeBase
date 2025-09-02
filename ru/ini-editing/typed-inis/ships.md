---
title: Корабли
---

:::caution

Эта страница находится в процессе разработки!

На этой странице может быть недостающая, неполная или неверная информация, так как она всё ещё находится в разработке! Относитесь к информации на ней с долей скепсиса и не стесняйтесь вносить свои предложения и исправлять ошибки!

:::

## Оглавление

- [Оглавление](#оглавление)
  - [Обзор](#обзор)
    - [Ванильные примеры](#ванильные-примеры)
    - [Обработка судов](#обработка-судов)
  - [Синтаксис](#синтаксис)
    - [Simple](#simple)
    - [Ship](#ship)
    - [CollisionGroup](#collisiongroup)

### Обзор

Хотя файлы `shiparch.ini` и `rtc_shiparch.ini` указаны как имеющие настраиваемые расположения в `freelancer.ini`, корабли, используемые NPC, _должны_ находиться в файле `shiparch.ini` по умолчанию, иначе могут произойти сбои.

#### Ванильные примеры

- `DATA\SHIPS\shiparch.ini`
- `DATA\SHIPS\rtc_shiparch.ini`

#### Обработка судов

Управление кораблём определяется несколькими ключами из блока `[Engine]` из [equipment](./equipment.md), а также ключами, относящимися к самому элементу `[Ship]`. Масса корабля смягчает любые изменения скорости и влияет на поведение при столкновении с другими объектами. `rotation_inertia` действует практически так же, но при повороте.

`rotation_inertia` обычно должна составлять от 10 до 20% от `angular_drag`, чтобы избежать странного поведения автопилота.

Где `linear_drag` = сумма значений `linear_drag` двигателя и корабля:

```c
$Strafe\ Speed = strafe\_force/(linear\_drag)$

$Max\ Turn\ Speed = steering\_torque/angular\_drag$

$Top\ Speed = max\_force†/linear\_drag$
```

†Значение определено в записи [equipment](./equipment.md).

### Синтаксис

#### Simple

```ini
[Simple]
nickname = STRING
DA_archetype = PATH
material_library = PATH ;repeatable
LODranges = INT, INT, ...
MinSpecLOD = INT
```

| Параметр         | Информация                                                                                                                                                     |
| ---------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| nickname         | Как этот простой объект ссылается в других файлах игры.                                                                                                        |
| DA_archetype     | Путь к модели архетипа, используемой для простого объекта. Обычно это файл .3db или .cmp.                                                                      |
| material_library | Путь к библиотеке материалов (.mat), используемой `DA_archetype`. Отсутствие .mat-файлов может привести к некорректному отображению корабля или частей модели. |
| ScreenReset      |                                                                                                                                                                |
| LODranges        |                                                                                                                                                                |
| MinSpecLOD       |                                                                                                                                                                |

#### Ship

```ini
[Ship]
ids_name = INT
ids_info = INT
ids_info1 = INT
ids_info2 = INT
ids_info3 = INT
ship_class = INT
nickname = STRING
LODranges = INT, INT, ...
msg_id_prefix = STRING
mission_property = STRING
type = STRING
mass = INT
hold_size = INT
linear_drag = INT
fuse = STRING, FLOAT, FLOAT ;repeatable
max_bank_angle = INT
camera_offset = INT, INT
camera_angular_acceleration = FLOAT
camera_horizontal_turn_angle = INT
camera_vertical_turn_up_angle = INT
camera_vertical_turn_down_angle = INT
camera_turn_look_ahead_slerp_amount = INT
nanobot_limit = INT
shield_battery_limit = INT
hit_pts = INT
DA_archetype = PATH
material_library = PATH ;repeatable
envmap_material = STRING
cockpit = PATH
pilot_mesh = STRING
explosion_arch = STRING
surface_hit_effects = INT, STRING, STRING, STRING
steering_torque = INT, INT, INT
angular_drag = INT, INT, INT
rotation_inertia = INT, INT, INT
nudge_force = INT
strafe_force = INT
strafe_power_usage = INT
bay_door_anim = STRING
bay_doors_open_snd = STRING
bay_doors_close_snd = STRING
HP_bay_surface = STRING
HP_bay_external = STRING
num_exhaust_nozzles = INT
HP_tractor_source = STRING
shield_link = STRING, STRING, STRING
hp_type = STRING, STRING ;repeatable
```

| Параметр                            | Информация                                                                                                                                                                                                                                                   |
| ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| ids_name                            | Строковой идентификатор имени корабля.                                                                                                                                                                                                                       |
| ids_info                            | Текст описания характеристик, используемый у дилера кораблей.                                                                                                                                                                                                |
| ids_info1                           | «Флэйвор-текст», используемый в описании корабля.                                                                                                                                                                                                            |
| ids_info2                           | Поля характеристик, отображаемые в инфобоксе корабля при осмотре вне дилера. В оригинальной игре обычно `66608`.                                                                                                                                             |
| ids_info3                           | Цифровые значения характеристик, отображаемые в инфобоксе корабля при осмотре вне дилера.                                                                                                                                                                    |
| ship_class                          | Значение от 0 до 3. Определяет класс корабля у дилера: 0 = «Лёгкий истребитель», 1 = «Тяжёлый истребитель», 2 = «Фрейтер», 3 = «Очень тяжёлый истребитель».                                                                                                  |
| nickname                            | Внутреннее имя корабля, используемое в других INI-файлах игры.                                                                                                                                                                                               |
| LODranges                           |                                                                                                                                                                                                                                                              |
| msg_id_prefix                       | Ссылка на ID префикса, например «Liberty Heavy Fighter», используемого при общении станций и других кораблей. Обычно содержится в [voices](./voices.md), звуковые файлы находятся в бинарных UTF-файлах.                                                     |
| mission_property                    | Определяет, к чему корабль может пристыковаться. Доступные варианты: `can_use_berths` (использование стыковочных колец), `can_use_med_moors`, `can_use_large_moors`.                                                                                         |
| type                                | Влияет на значения `attack_preference` NPC в [pilots_population.ini](../hardcoded-inis/data/missions/pilots.md). Также может влиять на поведение NPC в формации. Наблюдаемые значения: `FIGHTER`, `FREIGHTER`, `TRANSPORT`, `CAPITAL`, `GUNBOAT`, `CRUISER`. |
| mass                                | Масса корабля. Чем больше значение, тем сильнее замедляются изменения скорости корабля.                                                                                                                                                                      |
| hold_size                           | Размер грузового отсека корабля.                                                                                                                                                                                                                             |
| linear_drag                         | Сопротивление, применяемое к кораблю при движении. Действует даже в режиме отключенного двигателя.                                                                                                                                                           |
| fuse                                | Плавкий предохранитель для корабля. Обычно указывается как [`fuse`](./fuses.md), задержка в секундах и порог hit_pts для срабатывания.                                                                                                                       |
| max_bank_angle                      | Максимальный угол крена при повороте в градусах.                                                                                                                                                                                                             |
| camera_offset                       | Смещение камеры по осям Y и Z относительно центра корабля.                                                                                                                                                                                                   |
| camera_angular_acceleration         |                                                                                                                                                                                                                                                              |
| camera_horizontal_turn_angle        |                                                                                                                                                                                                                                                              |
| camera_vertical_turn_up_angle       |                                                                                                                                                                                                                                                              |
| camera_vertical_turn_down_angle     |                                                                                                                                                                                                                                                              |
| camera_turn_look_ahead_slerp_amount |                                                                                                                                                                                                                                                              |
| nanobot_limit                       | Максимальное количество наноботов, которое корабль может нести.                                                                                                                                                                                              |
| shield_battery_limit                | Максимальное количество батарей щита, которое корабль может нести.                                                                                                                                                                                           |
| hit_pts                             | Максимальное количество очков прочности корабля.                                                                                                                                                                                                             |
| DA_archetype                        | Путь к архетипу модели корабля. Обычно это файл .3db или .cmp.                                                                                                                                                                                               |
| material_library                    | Путь к библиотеке материалов (.mat), используемой `DA_archetype`. Отсутствие .mat-файлов приведёт к некорректному отображению корабля или его частей.                                                                                                        |
| envmap_material                     | Кубическая текстура для модели. В оригинальных файлах почти всегда используется `envmapbasic`.                                                                                                                                                               |
| cockpit                             | Путь к записи [Cockpit](./cockpits.md) в ini. Определяет свойства кабины корабля в режиме от первого лица.                                                                                                                                                   |
| pilot_mesh                          | Ссылка на блок `[Simple]`, который прикрепляется к hardpoint HpPilot.                                                                                                                                                                                        |
| explosion_arch                      | Определяет [взрыв](./explosions.md), который воспроизводится при уничтожении корабля.                                                                                                                                                                        |
| surface_hit_effects                 | Порог нанесённого урона и список возможных визуальных [эффектов](./effects.md), используемых при повреждении корпуса корабля.                                                                                                                                |
| steering_torque                     |                                                                                                                                                                                                                                                              |
| angular_drag                        | «Сопротивление» при повороте; определяет скорость ускорения при повороте от нулевой до максимально разрешённой.                                                                                                                                              |
| rotation_inertia                    |                                                                                                                                                                                                                                                              |
| nudge_force                         |                                                                                                                                                                                                                                                              |
| strafe_force                        |                                                                                                                                                                                                                                                              |
| strafe_power_usage                  |                                                                                                                                                                                                                                                              |
| bay_door_anim                       | Анимация в файле модели для открытия и закрытия дверей грузового отсека.                                                                                                                                                                                     |
| bay_doors_open_snd                  | [Звук](./sounds.md), воспроизводимый при открытии дверей отсека.                                                                                                                                                                                             |
| bay_doors_close_snd                 | [Звук](./sounds.md), воспроизводимый при закрытии дверей отсека.                                                                                                                                                                                             |
| HP_bay_surface                      | Hardpoint, обозначающий расположение дверей отсека. Обычно используется для целей анимации.                                                                                                                                                                  |
| HP_bay_external                     | Hardpoint, обозначающий расположение дверей отсека. Обычно используется для целей анимации.                                                                                                                                                                  |
| num_exhaust_nozzles                 | Определяет количество hardpoints `HpEngine`, используемых для присоединения эффектов двигателя к кораблю.                                                                                                                                                    |
| HP_tractor_source                   | Hardpoint-источник для [эффекта](./effects.md) трактора при его активации.                                                                                                                                                                                   |
| shield_link                         | Определяет щит корабля. Ссылка на запись [`[Shield]`](./equipment.md), затем hardpoint для центрирования щита и hardpoint для `[ShieldGenerator]`.                                                                                                           |
| hp_type                             | Определяет «классы» hardpoints на корабле. Обычно указывается класс hardpoint (например, `hp_gun_special_1`) и список hardpoints, к которым применяется этот класс. Hardpoints могут иметь несколько назначенных классов.                                    |

#### CollisionGroup

```ini
[CollisionGroup]
obj = STRING
separable
parent_impulse = INT ;optional
child_impulse = INT ;optional
dmg_hp = STRING ;optional
dmg_obj = STRING ;optional
fuse = STRING, INT, INT ;optional
group_dmg_hp = STRING ;optional
group_dmg_obj = STRING ;optional
mass = INT
debris_type = STRING
separation_explosion = STRING
type = STRING
hit_pts = INT
root_health_proxy = BOOL
explosion_resistance = FLOAT ;optional
linked_equip = STRING, FLOAT ;optional
```

| Параметр             | Информация                                                                                                                                                                                                                                                                                       |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| obj                  | Ссылается на блок `[Simple]`, определённый в другом месте файла Shiparch.                                                                                                                                                                                                                        |
| separable            | Обычно определяется как ключ без значения. При наличии позволяет CollisionGroup отделяться от корабля при определённых условиях.                                                                                                                                                                 |
| parent_impulse       |                                                                                                                                                                                                                                                                                                  |
| child_impulse        |                                                                                                                                                                                                                                                                                                  |
| dmg_hp               |                                                                                                                                                                                                                                                                                                  |
| dmg_obj              | Ссылается на объект `[Simple]`, который будет использоваться в этом `CollisionGroup`.                                                                                                                                                                                                            |
| mass                 | Масса CollisionGroup. Это значение ослабляет любые изменения скорости, которые делает CollisionGroup. Чем выше значение, тем сильнее ослабление.                                                                                                                                                 |
| fuse                 |                                                                                                                                                                                                                                                                                                  |
| group_dmg_hp         |                                                                                                                                                                                                                                                                                                  |
| group_dmg_obj        |                                                                                                                                                                                                                                                                                                  |
| debris_type          |                                                                                                                                                                                                                                                                                                  |
| separation_explosion | [Взрыв](./explosions.md), который используется, когда этот объект отделяется от родительского.                                                                                                                                                                                                   |
| type                 |                                                                                                                                                                                                                                                                                                  |
| hit_pts              | Количество очков здоровья у этой группы столкновения.                                                                                                                                                                                                                                            |
| root_health_proxy    | Определяет, применяется ли урон, нанесённый этой группе столкновения, также к корневому объекту. `true` — урон применяется к корню, `false` — урон остаётся только для этой группы.                                                                                                              |
| explosion_resistance | Определяет множитель урона от взрывов. По умолчанию 1. 0 означает, что урон от взрывов никогда не применяется.                                                                                                                                                                                   |
| linked_equip         | При разрушении этой группы столкновения наносится урон определённому типу оборудования на корабле. Первый элемент принимает набор типов оборудования: scanner, engine, weapon, shield, thruster, power, light, tractor, attached_fx, internal_fx, tradelane, repairdroid, cloaking_device, armor |
