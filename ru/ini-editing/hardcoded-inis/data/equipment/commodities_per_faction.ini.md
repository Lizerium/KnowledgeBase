---
title: commodities_per_faction.ini
---

## Обзор

В этом файле описываются товары, которые будут перевозить `NPC`-торговцы фракции.

### Ванильные примеры

- `DATA\EQUIPMENT\commodities_per_faction.ini`

## Синтаксис

Могут быть определены несколько экземпляров каждого блока.

### [FactionGood]

```ini
[FactionGood]
faction = STRING
MarketGood = STRING
```

| Параметр   | Описание                                                                               |
| ---------- | -------------------------------------------------------------------------------------- |
| faction    | Название фракции, определённое в [`faction_prop.ini`](../missions/faction_prop.ini.md) |
| MarketGood | Товар, определённый в [`goods.ini`](../../../typed-inis/goods.md)                      |
