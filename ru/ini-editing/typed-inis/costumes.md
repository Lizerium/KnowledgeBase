---
title: Костюмы
---

## Обзор

INI-файл костюмов соответствует частям тела, определённым в [bodyparts](bodyparts.md). Костюмы — это то, что фактически используется в других местах игры, например, в [mbases.ini](../hardcoded-inis/data/missions/mbases.ini.md) или в файлах сюжета.

### Ванильные примеры

- `DATA\CHARACTERS\costumes.ini`

## Синтаксис

### Костюм

```ini
[Costume]
nickname = STRING
body = STRING
righthand = STRING
lefthand = STRING
```

| Параметр  | Информация                                                                    |
| --------- | ----------------------------------------------------------------------------- |
| nickname  | См. описание nickname для дополнительной информации.                          |
| body      | Ссылка на Body (см. [bodyparts](bodyparts.md) для доступных тел).             |
| righthand | Ссылка на RightHand (см. [bodyparts](bodyparts.md) для доступных правых рук). |
| lefthand  | Ссылка на LeftHand (см. [bodyparts](bodyparts.md) для доступных левых рук).   |
