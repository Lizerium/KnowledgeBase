---
title: soundcfg.ini
---

## Обзор

Этот файл, по-видимому, управляет поведением звука во Freelancer в глобальном масштабе. Блок `[reverb]` можно использовать для управления поведением отдельных звуков. Неясно, вызывает ли этот файл Freelancer, требуются дополнительные исследования.

## Синтаксис

Можно определить несколько блоков `[reverb]`

### CFG

```ini
[Voice]
ear_doppler_factor = FLOAT
ducking_rtc_down_by = INT
ducking_rtc_down_time = FLOAT
default_crv_pitch = INT
default_crv_attenuation = INT
music_fade_time = INT
cross_fade_silence = INT
cockpit_attenuation = INT
ducking_spaceflight_down_by = INT
ducking_spaceflight_down_time = FLOAT
ducking_spaceflight_up_time = FLOAT
spaceflight_dialogue_pan_range = INT
ducking_comm_down_by = -INT
ducking_comm_down_time = FLOAT
ducking_comm_up_time = FLOAT
master_music = INT
master_ambient = INT
master_interface = INT
master_sfx = INT
master_voice = INT
```

| Параметр                         | Информация                                                                                    |
| -------------------------------- | --------------------------------------------------------------------------------------------- |
| `ear_doppler_factor`             | Сила эффекта Доплера для движущихся звуковых источников.                                      |
| `ducking_rtc_down_by`            | Степень сжатия громкости аудиосигнала, когда другой аудиосигнал превышает определённый порог. |
| `ducking_rtc_down_time`          | Длительность действия эффекта приглушения (ducking down).                                     |
| `default_crv_pitch`              | Определяет изменение высоты тона в тональной части аудиосегмента.                             |
| `default_crv_attenuation`        | Определяет кривую затухания по умолчанию.                                                     |
| `music_fade_time`                | Определяет время затухания/появления музыки.                                                  |
| `cross_fade_silence`             | Длительность тишины при кроссфейде во время смены музыкального трека.                         |
| `cockpit_attenuation`            | Затухание звука по умолчанию в режиме кабины.                                                 |
| `ducking_spaceflight_down_by`    | Уровень приглушения звуков в космосе.                                                         |
| `ducking_spaceflight_down_time`  | Длительность приглушения звуков в космосе.                                                    |
| `ducking_spaceflight_up_time`    | Скорость восстановления приглушённых звуков в космосе (?).                                    |
| `spaceflight_dialogue_pan_range` | Определяет диапазон панорамы диалогов в космосе.                                              |
| `ducking_comm_down_by`           | Уровень приглушения звука связи при обращении к NPC.                                          |
| `ducking_comm_down_time`         | Длительность приглушения звука связи при обращении к NPC.                                     |
| `ducking_comm_up_time`           | Скорость восстановления приглушённых звуков связи в космосе (?).                              |
| `master_music`                   | Общая громкость музыки.                                                                       |
| `master_ambient`                 | Общая громкость фоновых звуков.                                                               |
| `master_interface`               | Общая громкость интерфейсных звуков.                                                          |
| `master_sfx`                     | Общая громкость звуковых эффектов.                                                            |
| `master_voice`                   | Общая громкость голосов.                                                                      |

### reverb

```ini
[reverb]
nickname = STRING
settings = INT, INT, INT
```

| Параметр | Описание                                                                                             |
| -------- | ---------------------------------------------------------------------------------------------------- |
| nickname | Похоже, что это ссылка на запись в [sounds.ini](../../../typed-inis/sounds.md)                       |
| settings | Определяет уровень реверберации. Не совсем ясно, за что отвечают эти числа — требуется тестирование. |
