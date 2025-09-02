---
title: Эффекты
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
    - [EffectType](#effecttype)
    - [VisEffect](#viseffect)
    - [EffectLOD](#effectlod)
    - [Effect](#effect)
      - [Beam Breakdown](#beam-breakdown)

### Обзор

Эти файлы управляют эффектами и прикрепленными к ним звуками, их типами, а также текстурой и звуковыми компонентами эффектов. Блоки `[BeamSpear` и `[BeamBolt]` также можно использовать для непосредственного создания простых эффектов лучей.

#### Ванильные примеры

- `DATA\FX\WEAPONS\weapons_ale.ini`
- `DATA\FX\beam_effects.ini`
- `DATA\FX\effects.ini`
- `DATA\FX\effect_types.ini`

### Синтаксис

Блоки `[EffectType]` всегда следует вызывать перед всеми остальными, а затем `[VisEffect]`. Обычно они вызываются в отдельном INI-файле, как определено в [freelancer.ini](../hardcoded-inis/exe/freelancer.ini.md).

#### EffectType

:::caution

Количество и названия блоков `[EffectType]` фактически жёстко заданы в коде и не могут быть изменены или добавлены. Однако блок `[EffectType]` позволяет определить свойства каждого типа.

:::

```ini
[EffectType]
nickname = STRING
priority = INT
generic_priority = INT
lod_type = STRING
radius = INT
visibility = STRING
update = STRING
run_time = INT
pbubble = INT, INT
```

| Параметр         | Информация                                                                                                                                                                                                                                       |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| nickname         | Как эффект ссылается на блоки `[Effect]`.                                                                                                                                                                                                        |
| priority         | Устанавливает приоритет рендеринга эффекта. Видимо, определяет порядок отсечения при достижении лимита частиц.                                                                                                                                   |
| generic_priority | То же самое, что `priority`, но для эффекта, на который ссылается `vis_generic` в блоках `[Effect]`.                                                                                                                                             |
| lod_type         | Опции: `EFT_LOD_NONE`, `EFT_LOD_TRAIL`, `EFT_LOD_WEAPON`, `EFT_LOD_SMALL`, `EFT_LOD_MEDIUM`, `EFT_LOD_LARGE` и `EFT_LOD_SMALL_DISTANT`.                                                                                                          |
| radius           | Диапазон: 0 до ∞. Приблизительный размер объекта; может использоваться при расчёте `visibility` и `update`.                                                                                                                                      |
| visibility       | Определяет видимость эффекта. Опции: `EXIST_OFFSCREEN` или `CULL_OFFSCREEN`.                                                                                                                                                                     |
| update           | Определяет, обновляется ли эффект, когда он вне экрана. Опции: `UPDATE_OFFSCREEN` или `CULL_UPDATE`.                                                                                                                                             |
| run_time         | Максимальное время работы эффектов этого типа.                                                                                                                                                                                                   |
| pbubble          | Определяет максимальное и минимальное расстояние видимости эффекта. Любой радиус выше жёстко заданного максимального диапазона рендеринга или максимального расстояния видимости эффекта использоваться не будет — применяется жёсткий максимум. |

#### VisEffect

```ini
[VisEffect]
nickname = STRING
alchemy = PATH
effect_crc = INT
textures = PATH
```

| Параметр   | Информация                                                                                              |
| ---------- | ------------------------------------------------------------------------------------------------------- |
| nickname   | Как этот эффект ссылается на блоки `[Effect]`.                                                          |
| alchemy    | Путь к файлу `.ale`.                                                                                    |
| effect_crc | CRC-ссылка, указывающая на имя эффекта, используемое внутри файла `.ale`.                               |
| textures   | Ссылки на конкретные `.txm` файлы, используемые эффектом. Можно определить несколько ключей `textures`. |

#### EffectLOD

```ini
[EffectLOD]
type = STRING
max_lod_screen_size = INT
min_lod_screen_size = INT
min_screen_size = INT
```

| Parameter           | Information |
| ------------------- | ----------- |
| type                |             |
| max_lod_screen_size |             |
| min_lod_screen_size |             |
| min_screen_size     |             |

#### Effect

```ini
[Effect]
nickname = STRING
effect_type = STRING
snd_effect = STRING ;optional
vis_effect = STRING
vis_generic = STRING ;optional
lgt_effect = STRING ;optional
lgt_range_scale = INT ;optional
lgt_radius = INT ;optional
```

| Параметр        | Информация                                                                                                                                                     |
| --------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| nickname        | Как этот эффект ссылается на другие блоки и файлы.                                                                                                             |
| effect_type     | Тип эффекта, как определено в блоке `[EffectType]`.                                                                                                            |
| snd_effect      | Звуковой эффект, прикреплённый к этому эффекту, который воспроизводится как определено в [sounds](sounds.md). Звук будет зациклен на всю длительность эффекта. |
| vis_effect      | Блок `[VisEffect]`, используемый с этим эффектом.                                                                                                              |
| vis_generic     | Неясно. Возможно, это «резервный эффект», используемый, когда эффект не может быть воспроизведён по какой-либо причине.                                        |
| lgt_effect      |                                                                                                                                                                |
| lgt_range_scale |                                                                                                                                                                |
| lgt_radius      |                                                                                                                                                                |

```ini
[BeamSpear]
nickname = STRING
tip_length = INT
tail_length = INT
head_width = INT
core_width = FLOAT
tip_color = INT, INT, INT
core_color = INT, INT, INT
outter_color = INT, INT, INT
tail_color = INT, INT, INT
head_brightness = INT
trail_brightness = FLOAT
head_texture = STRING
trail_texture = STRING
flash_size = INT
```

| Параметр         | Информация                                                |
| ---------------- | --------------------------------------------------------- |
| nickname         | Как BeamSpear ссылается на блоки `[Effect]`.              |
| tip_length       | Длина наконечника луча.                                   |
| tail_length      | Длина хвоста луча.                                        |
| head_width       | Ширина головной части луча.                               |
| core_width       | Ширина сердцевины луча.                                   |
| tip_color        | RGB-цвет наконечника луча.                                |
| core_color       | RGB-цвет сердцевины луча.                                 |
| outter_color     | RGB-цвет внешнего «свечения» луча.                        |
| tail_color       | RGB-цвет хвоста луча.                                     |
| head_brightness  | Альфа (прозрачность) головной части луча (диапазон 0–1).  |
| trail_brightness | Альфа (прозрачность) хвоста луча (диапазон 0–1).          |
| head_texture     | Текстура головной части луча (может быть шар или звезда). |
| trail_texture    | Текстура хвоста луча (может быть широкой или тонкой).     |
| flash_size       | Размер вспышки луча при его создании.                     |

```ini

[BeamBolt]
nickname = STRING
tip_length = INT
tail_length = INT
core_length = INT
head_width = INT
core_width = FLOAT
sec_core_width = INT
tip_color = INT, INT, INT
core_color = INT, INT, INT
outter_color = INT, INT, INT
sec_core_color = INT, INT, INT
sec_outter_color = INT, INT, INT
tail_color = INT, INT, INT
head_brightness = INT
trail_brightness = FLOAT
head_texture = STRING
trail_texture = STRING
flash_size = INT
```

| Параметр         | Информация                                                                                                                        |
| ---------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| nickname         | Как BeamSpear ссылается на блоки `[Effect]`.                                                                                      |
| tip_length       | Длина наконечника луча.                                                                                                           |
| tail_length      | Длина хвоста луча.                                                                                                                |
| head_width       | Ширина головной части луча.                                                                                                       |
| core_width       | Ширина сердцевины луча.                                                                                                           |
| sec_core_width   | Задает диаметр вторичной сердцевины.                                                                                              |
| tip_color        | RGB-цвет наконечника луча.                                                                                                        |
| core_color       | RGB-цвет сердцевины луча.                                                                                                         |
| outter_color     | RGB-цвет внешнего «свечения» луча.                                                                                                |
| sec_core_color   | Задает цвет внутри вторичной сердцевины.                                                                                          |
| sec_outter_color | Задает цвет внешнего кольца вторичной сердцевины. Цвет вторичной сердцевины — градиент от `sec_core_color` до `sec_outter_color`. |
| tail_color       | RGB-цвет хвоста луча.                                                                                                             |
| head_brightness  | Альфа (прозрачность) головной части луча (диапазон 0–1).                                                                          |
| trail_brightness | Альфа (прозрачность) хвоста луча (диапазон 0–1).                                                                                  |
| head_texture     | Текстура головной части луча (может быть шар или звезда).                                                                         |
| trail_texture    | Текстура хвоста луча (может быть широкой или тонкой).                                                                             |
| flash_size       | Размер вспышки луча при его создании.                                                                                             |

##### Beam Breakdown

Ниже представлен анализ различных элементов, входящих в состав BeamSpear и BeamBolt. Автор — Cpt_Rei_Fukai.

![Схема различных элементов, из которых состоит балка](/img/beam-diagram.png)
