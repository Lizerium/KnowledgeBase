---
title: INI-редактирование
description: Индекс раздела редактирования INI в этой вики.
id: ini-editing
---

## Оглавление

- [Оглавление](#оглавление)
  - [Основное](#основное)
  - [Типизированные INI-файлы](#типизированные-ini-файлы)
  - [Жестко закодированные INI-файлы](#жестко-закодированные-ini-файлы)
    - [EXE](#exe)
    - [DATA](#data)
    - [AI](#ai)
    - [Equipment](#equipment)
    - [FX](#fx)
    - [Interface](#interface)
    - [Missions](#missions)
    - [RandomMissions](#randommissions)
    - [Solar](#solar)
    - [Universe](#universe)

### Основное

INI-файлы в Freelancer можно в целом разделить на два типа: типизированные и жёстко заданные. Некоторые типизированные INI-файлы имеют ограничения на имя и место размещения. Перед перемещением отдельных записей INI-файлов из их стандартных расположений, пожалуйста, проверьте их. Ниже указано, где их можно найти или определить:

### Типизированные INI-файлы

Расположение этих INI-типов определяется в файле `freelancer.ini`. В большинстве случаев их можно разместить в любом месте каталога игры, если файл на них указывает.

| Имя                                                 | Описание                                                                                                        | Путь определяется |
| --------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- | ----------------- |
| [Астероиды](./typed-inis/asteroids.md)              | Определяет свойства отдельных моделей астероидов.                                                               | freelancer.ini    |
| [Астероидные поля](./typed-inis/asteroid_fields.md) | Определяет свойства отдельных полей астероидов.                                                                 | system            |
| [Комнаты баз](typed-inis/bases.md)                  | Определяет комнаты, присутствующие в базах.                                                                     | universe          |
| [Части тела](typed-inis/bodyparts.md)               | Индексирует все тела персонажей: тела, головы, руки и аксессуары.                                               | freelancer.ini    |
| [Кабины](typed-inis/cockpits.md)                    | Определяет свойства кабины корабля с видом от первого лица.                                                     | ships             |
| [Вогнутые объекты](typed-inis/concave.md)           | Списки вогнутых объектов.                                                                                       | freelancer.ini    |
| [Константы](typed-inis/constants.md)                | Сохраняет множество стандартных констант, которые используются на протяжении всей игры.                         | freelancer.ini    |
| [Костюмы](typed-inis/costumes.md)                   | Совмещает части тела, определённые в bodyparts.                                                                 | freelancer.ini    |
| [Обломки](typed-inis/debris.md)                     | Определяет обломки.                                                                                             | freelancer.ini    |
| [Формы эффектов](typed-inis/effect_shapes.md)       | Определяет формы текстур эффектов.                                                                              | freelancer.ini    |
| [Эффекты](typed-inis/effects.md)                    | Определяет эффекты и их типы.                                                                                   | freelancer.ini    |
| [Оборудование](typed-inis/equipment.md)             | Определяет оборудование.                                                                                        | freelancer.ini    |
| [Cтолкновения](typed-inis/encounters.md)            | Определяет поведение ИИ и спавн, используемые случайными NPC-встречами.                                         | system            |
| [Взрывы](typed-inis/explosions.md)                  | Определяет взрывы.                                                                                              | freelancer.ini    |
| [Шрифты](typed-inis/fonts.md)                       | Определяет шрифты, используемые в игре.                                                                         | freelancer.ini    |
| [Взрыватели](typed-inis/fuses.md)                   | Определяет управляемые/многоступенчатые взрывы, которые в Freelancer называются «fuses».                        | freelancer.ini    |
| [Ворота туннеля](./typed-inis/gate_tunnel.md)       | Определяет элементы эффектов тоннелей прыгательных ворот и дыр.                                                 | freelancer.ini    |
| [Товары](typed-inis/goods.md)                       | Определяет цену продажи и некоторые свойства оборудования и кораблей.                                           | freelancer.ini    |
| [Группы](typed-inis/groups.md)                      | Определяет начальное состояние мира игры: отношения фракций игрока, заблокированные прыгательные врата и дырки. | freelancer.ini    |
| [Дисплей на лобовом стекле](typed-inis/hud.md)      | Определяет элементы HUD.                                                                                        | freelancer.ini    |
| [Интерактивный граф](typed-inis/igraph.md)          | Определяет элементы источников света.                                                                           | freelancer.ini    |
| [Вступление](typed-inis/intro.md)                   | Определяет элементы игрового лаунчера, в основном не используемые.                                              | freelancer.ini    |
| [Эффект прыжка](typed-inis/jump_effect.md)          | Определяет элементы эффектов тоннелей прыгательных ворот и дыр.                                                 | freelancer.ini    |
| [Разгрузки](typed-inis/loadouts.md)                 | Определяет оборудование, прикреплённое к кораблям и соларам.                                                    | freelancer.ini    |
| [Рынки](typed-inis/markets.md)                      | Определяет места продажи и свойства оборудования и кораблей.                                                    | freelancer.ini    |
| [Туманность](typed-inis/nebula_fields.md)           | Определяет свойства отдельных полей туманностей.                                                                | system            |
| [Новый персонаж](typed-inis/newchardb.md)           | Определяет оборудование игрока и его ситуацию.                                                                  | freelancer.ini    |
| [Тип INI PetalDB](typed-inis/petaldb.md)            | Определяет несколько типов моделей реквизита, используемых на базах и в катсценах.                              | freelancer.ini    |
| [Кольца](typed-inis/rings.md)                       | Определяет планетарные кольца.                                                                                  | system            |
| [Комнаты баз](typed-inis/rooms.md)                  | Определяет содержимое и интерфейс комнат на базах.                                                              | bases             |
| [Слайдер RTC](typed-inis/rtcslider.md)              | Определяет свойства некоторых элементов, используемых в катсценах.                                              | freelancer.ini    |
| [Корабли](typed-inis/ships.md)                      | Определяет корабли.                                                                                             | freelancer.ini    |
| [Солнечный](typed-inis/solar.md)                    | Определяет статические объекты в космосе, которые могут быть размещены в файле системы.                         | freelancer.ini    |
| [Звуки](typed-inis/sounds.md)                       | Определяет звуки.                                                                                               | freelancer.ini    |
| [Система](typed-inis/system.md)                     | Определяет содержимое отдельных систем.                                                                         | universe          |
| [Вселенная](typed-inis/universe.md)                 | Индексирует базы и системы и определяет некоторые их свойства.                                                  | freelancer.ini    |
| [Голоса](typed-inis/voices.md)                      | Определяет голоса.                                                                                              | freelancer.ini    |
| [Эффективность оружия](typed-inis/weaponmoddb.md)   | Определяет типы оружия и щитов и определяет их эффективность друг против друга.                                 | freelancer.ini    |

### Жестко закодированные INI-файлы

Расположение этих типов INI-файлов жёстко задано и не может быть изменено обычными средствами. Если запись в списке ниже имеет суффикс `.ini`, файл должен соответствовать этому шаблону именования. Их можно разделить на несколько категорий:

#### EXE

| Название                                               | Описание                                                                                                                                                                        | Путь   |
| ------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------ |
| [freelancer.ini](hardcoded-inis/exe/freelancer.ini.md) | В первую очередь определяет, какие DLL подключаются FLserver.exe и Freelancer.exe, а также порядок их загрузки. Также указывает и определяет порядок загрузки typed INI-файлов. | `EXE\` |
| [dacom.ini](hardcoded-inis/exe/dacom.ini.md)           | Этот файл управляет конфигурацией настроек приложения при запуске и загрузкой библиотек.                                                                                        | `EXE\` |
| [dacomsrv.ini](hardcoded-inis/exe/dacomsrv.ini.md)     | Этот файл управляет конфигурацией настроек приложения при запуске и загрузкой библиотек **для FLServer.exe**. Структура идентична dacom.ini.                                    | `EXE\` |

#### DATA

| Название                                          | Описание                                                    | Путь    |
| ------------------------------------------------- | ----------------------------------------------------------- | ------- |
| [cameras.ini](hardcoded-inis/data/cameras.ini.md) | Определяет все камеры, используемые в игре во время полёта. | `DATA\` |
| [mouse.ini](hardcoded-inis/data/mouse.ini.md)     | Определяет характеристики различных курсоров в игре.        | `DATA\` |

#### AI

| Название                                                   | Описание                                                            | Путь       |
| ---------------------------------------------------------- | ------------------------------------------------------------------- | ---------- |
| [state_graph.db](hardcoded-inis/data/ai/state_graph.db.md) | Определяет некоторые элементы шаблонов полёта ИИ и поведения в бою. | `DATA\AI\` |

#### Equipment

| Название                                                                                    | Описание                                                                              | Путь              |
| ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ----------------- |
| [commodities_per_faction.ini](hardcoded-inis/data/equipment/commodities_per_faction.ini.md) | Определяет, какой груз носят NPC разных фракций в своих трюмах, когда это необходимо. | `DATA\Equipment\` |

#### FX

| Имя                                                      | Описание                                 | Путь       |
| -------------------------------------------------------- | ---------------------------------------- | ---------- |
| [lightanim.ini](hardcoded-inis/data/fx/lightanim.ini.md) | Определяет некоторые анимации освещения. | `DATA\FX\` |

#### Interface

| Имя                                                                       | Описание | Путь                       |
| ------------------------------------------------------------------------- | -------- | -------------------------- |
| [buttonmontage.ini](hardcoded-inis/data/interface/buttonmontage.ini.md)   |          | `DATA\Interface\`          |
| [navbar.ini](hardcoded-inis/data/interface/navbar.ini.md)                 |          | `DATA\Interface\Baseside\` |
| [buttontextures.ini](hardcoded-inis/data/interface/buttontextures.ini.md) |          | `DATA\Interface\`          |
| [infocardmap.ini](hardcoded-inis/data/interface/infocardmap.ini.md)       |          | `DATA\Interface\`          |
| [keylist.ini](hardcoded-inis/data/interface/keylist.ini.md)               |          | `DATA\Interface\`          |
| [keymap.ini](hardcoded-inis/data/interface/keymap.ini.md)                 |          | `DATA\Interface\`          |
| [knowledgemap.ini](hardcoded-inis/data/interface/knowledgemap.ini.md)     |          | `DATA\Interface\`          |
| [optlist.ini](hardcoded-inis/data/interface/optlist.ini.md)               |          | `DATA\Interface\`          |
| [rollover.ini](hardcoded-inis/data/interface/rollover.ini.md)             |          | `DATA\Interface\`          |

#### Missions

| Название                                                                     | Описание                                                                                 | Путь                 |
| ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | -------------------- |
| [empathy.ini](hardcoded-inis/data/missions/empathy.ini.md)                   | Определяет, как действия игрока влияют на отношения с фракциями.                         | `DATA\MISSIONS\`     |
| [faction_prop.ini](hardcoded-inis/data/missions/faction_prop.ini.md)         | Определяет фракции и некоторые их свойства.                                              | `DATA\MISSIONS\`     |
| factionsets.ini                                                              | Этот файл не используется.                                                               | `DATA\MISSIONS\`     |
| [formations.ini](hardcoded-inis/data/missions/formations.ini.md)             | Определяет формации, используемые NPC в космосе.                                         | `DATA\MISSIONS\`     |
| [lootprops.ini](hardcoded-inis/data/missions/lootprops.ini.md)               | Определяет базовые свойства дропа оборудования.                                          | `DATA\MISSIONS\`     |
| [missions](hardcoded-inis/data/missions/missions.ini.md)                     | Определяет некоторые скриптовые и событийные элементы однопользовательских миссий.       | `DATA\MISSIONS\M**\` |
| [mbases.ini](hardcoded-inis/data/missions/mbases.ini.md)                     | Определяет миссии и NPC, доступные на базах.                                             | `DATA\MISSIONS\`     |
| [news.ini](hardcoded-inis/data/missions/news.ini.md)                         | Определяет новости и место (и время) их доступности.                                     | `DATA\MISSIONS\`     |
| [npcships.ini](hardcoded-inis/data/missions/npcships.ini.md)                 | Определяет типы NPC-пилотов, их корабли и комплектование.                                | `DATA\MISSIONS\`     |
| [pilots](hardcoded-inis/data/missions/pilots.md)                             | Определяет элементы поведения NPC в бою.                                                 | `DATA\MISSIONS\`     |
| [ptough.ini](hardcoded-inis/data/missions/ptough.ini.md)                     | Определяет масштаб прочности игрока и уровень в зависимости от денежной ценности.        | `DATA\MISSIONS\`     |
| [rankdiff.ini](hardcoded-inis/data/missions/rankdiff.ini.md)                 | По-видимому, задаёт темп продвижения по рангу в сюжетной кампании.                       | `DATA\MISSIONS\`     |
| [shipclasses.ini](hardcoded-inis/data/missions/shipclasses.ini.md)           | Определяет классы кораблей и уровни, вызываемые встречами и миссиями.                    | `DATA\MISSIONS\`     |
| [specific_npc.ini](hardcoded-inis/data/missions/specific_npc.ini.md)         | Определяет характеристики конкретных NPC, встречающихся в однопользовательской кампании. | `DATA\MISSIONS\`     |
| [voice_properties.ini](hardcoded-inis/data/missions/voice_properties.ini.md) | По-видимому, относится к общим голосовым линиям, используемым пилотами в бою.            | `DATA\MISSIONS\`     |

#### RandomMissions

| Имя                                                                                        | Описание | Путь                   |
| ------------------------------------------------------------------------------------------ | -------- | ---------------------- |
| [diff2money.ini](hardcoded-inis/data/randommissions/diff2money.ini.md)                     |          | `DATA\RANSOMMISSIONS\` |
| [killablesolars.ini](hardcoded-inis/data/randommissions/killablesolars.ini.md)             |          | `DATA\RANSOMMISSIONS\` |
| [npcranktodiff.ini](hardcoded-inis/data/randommissions/npcranktodiff.ini.md)               |          | `DATA\RANSOMMISSIONS\` |
| [rmlootinfo.ini](hardcoded-inis/data/randommissions/rmlootinfo.ini.md)                     |          | `DATA\RANSOMMISSIONS\` |
| [solarformations.ini](hardcoded-inis/data/randommissions/solarformations.ini.md)           |          | `DATA\RANSOMMISSIONS\` |
| [vignettecriticalloot.ini](hardcoded-inis/data/randommissions/vignettecriticalloot.ini.md) |          | `DATA\RANSOMMISSIONS\` |
| [vignetteparams.ini](hardcoded-inis/data/randommissions/vignetteparams.ini.md)             |          | `DATA\RANSOMMISSIONS\` |

#### Solar

| Имя                                                       | Описание           | Путь          |
| --------------------------------------------------------- | ------------------ | ------------- |
| [stararch.ini](hardcoded-inis/data/solar/stararch.ini.md) | Определяет звезды. | `DATA\SOLAR\` |

#### Universe

| Имя                                                                                  | Описание                                                                                                                  | Путь             |
| ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------- | ---------------- |
| [paths](hardcoded-inis/data/universe/paths.md)                                       | Определяет кратчайшие пути, используемые автопилотом. Эти файлы генерируются во время выполнения, если они не существуют. | `DATA\UNIVERSE\` |
| [missioncreatedsolars.ini](hardcoded-inis/data/universe/missioncreatedsolars.ini.md) | Определяет солнечные батареи, созданные во время одиночных миссий.                                                        | `DATA\UNIVERSE\` |
