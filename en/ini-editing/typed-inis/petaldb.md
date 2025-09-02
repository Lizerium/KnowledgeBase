---
title: Petaldb
---

## Overview

The PetalDB ini type is used to define the models in the game.

### Vanilla Examples

- `DATA\petaldb.ini`

## Syntax

### [ObjectTable]

This is the only section within the file and it contains all entries.

```ini
[ObjectTable]
room = STRING, PATH ;repeatable
prop = STRING, PATH ;repeatable
cart = STRING, PATH ;repeatable
```

| Parameter                  | Information                                                                                                                                          |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| _room_ or _prop_ or _cart_ | The _STRING_ value sets the internal nickname of the model. The _PATH_ points to the model's location within the game files. Entries are repeatable. |
