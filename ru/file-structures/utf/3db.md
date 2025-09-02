---
title: Жесткая однокомпонентная модель (.3db)
---

## Обзор

Файл .3db UTF.

```mermaid
stateDiagram-v2
    direction LR

    state meshType <<choice>>

    Levels: Level0 … Level9

    [*] --> meshType
    [*] --> VMeshWire
    [*] --> Hardpoints

    meshType --> VMeshPart
    meshType --> MultiLevel

    VMeshPart --> VMeshRef
    MultiLevel --> Levels
    MultiLevel --> Switch2
    Levels --> VMeshPart

    note right of VMeshRef
        @VMeshData
    end note

    VMeshWire --> VWireData
    Hardpoints --> Fixed
    Hardpoints --> Revolute
    Fixed --> HPMount
    Revolute --> HPWeapon
```

## Уровень детализации

Для отображения модели корневая запись сетки должна содержать либо `VMeshPart`, либо `MultiLevel`, если модель имеет более одного уровня детализации (LOD).

Каждая запись уровня должна содержать `VMeshPart` (которая, в свою очередь, должна содержать `VMeshRef`), указывающую на фрагмент в `VMeshData` для рисования в качестве сетки LOD.

`MultiLevel` может содержать запись `Switch2` в виде массива чисел с плавающей запятой, начинающегося с 0, где каждое последующее число является максимальным диапазоном для уровня.

## Каркас HUD

Когда объект, использующий модель, может быть выбран в качестве цели, в списке контактов HUD может отображаться каркасная модель.

Корневая запись должна содержать запись `VMeshWire` с записью данных `VWireData` внутри.

* Обычно `VWireData` использует один из буферов сетки, уже используемых частью LOD, но может указывать на любой другой для рисования фигур, не привязанных к вершинам отображаемой сетки.