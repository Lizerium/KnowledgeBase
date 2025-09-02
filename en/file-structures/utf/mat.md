---
title: Materials library (.mat)
---

## Overview

Materials are either stored in separate file (.mat) or embedded into model files (.3db, .cmp, .dfm, etc).

```mermaid
flowchart LR
    \ --> A[Texture library]
    A --> B[texture]
    \ --> M[Material library]
    M --> M1[material]
    M1 --> DT(Dt_name)
    M1 --> T(Type)
    DT -.-> B
```

Certain assets cannot have reference to external material file and will require materials to be embedded directly in model file, such as starspheres, cutscene props and deformable models.

### Material types

| Type                          | Alpha | Description                                                                                                     |
| ----------------------------- | ----- | --------------------------------------------------------------------------------------------------------------- |
| DcDt                          | No    | Diffuse color + Diffuse texture.                                                                                |
| DcDtTwo                       | No    | Two-sided variant of DcDt.                                                                                      |
| DcDtEc                        | No    | Diffuse color + Diffuse texture + Emission color.                                                               |
| DcDtEcTwo                     | No    | Two-sided variant of DcDtEc.                                                                                    |
| DcDtOcOt                      | Yes   | Diffuse color + Diffuse texture + Opacity color + Opacity texture.                                              |
| DcDtOcOtTwo                   | Yes   | Two-sided variant of DcDtOcOt.                                                                                  |
| DcDtEcOcOt                    | Yes   | Diffuse color + Diffuse texture + Emission color + Opacity color + Opacity texture.                             |
| DcDtEcOcOtTwo                 | Yes   | Two-sided variant of DcDtEcOcOt.                                                                                |
| DcDtEt                        | No    | Diffuse color + Diffuse texture + Emission texture.                                                             |
| EcEt                          | No    | Emission color + Emission texture.                                                                              |
| Nebula                        | Yes   | Diffuse texture tinted by vertex color with blending (ADD, SRCALPHA, ONE).                                      |
| NebulaTwo                     | Yes   | Two-sided variant of Nebula.                                                                                    |
| BtDetailMapMaterial           | No    | Diffuse texture with detail texture blended in overlay mode. Detail texture uses second UV texture mapping set. |
| BtDetailMapMaterialTwo        | No    | Two-sided variant of DetailMaterial.                                                                            |
| NomadMaterial                 | Yes   | Special material for nomad ships.                                                                               |
| NomadMaterialNoBendy          | Yes   | Ditto.                                                                                                          |
| GlassMaterial                 | Yes   | Transparent material used for cockpit.                                                                          |
| GFGlassMaterial               | Yes   | Ditto.                                                                                                          |
| HighGlassMaterial             | Yes   | Ditto.                                                                                                          |
| PlanetWaterMaterial           | Yes   | Multiply blending mode material.                                                                                |
| AtmosphereMaterial            | Yes   |                                                                                                                 |
| ExclusionZoneMaterial         | Yes   | Material for exclusion zone shells.                                                                             |
| HUDIconMaterial               | Yes   | Material for HUD icons.                                                                                         |
| HUDAnimMaterial               | Yes   | Animated material for HUD. Animation is toggled in settings.                                                    |
| NullMaterial                  | No    | Fallback material.                                                                                              |
| DetailMapMaterial             | No    |                                                                                                                 |
| DetailMap2Dm1Msk2PassMaterial | No    |                                                                                                                 |
| IllumDetailMapMaterial        | No    |                                                                                                                 |
| Masked2DetailMapMaterial      | No    |                                                                                                                 |

- `NomadMaterial` and `NomadMaterialNoBendy` do not display when environment map is used for the object.
- ❗ Material type can be overridden by matching regexp in [MaterialMap] of dacom.ini.

When model uses both transparent and non-transparent (opaque) materials it should be multi-part compound and any mesh groups using transparent material(s) should be kept in parts separate from mesh groups using opaque materials, i.e. transparent cockpit glass should be in part separate from hull it is attached to. Mesh groups with opaque materials are drawn front to back, afterwards mesh groups with transparent materials are drawn back to front with depth buffer write disabled.

#### Material properties

| Name      | Type     | Description                               |
| --------- | -------- | ----------------------------------------- |
| Ac        | float[3] | Ambient color.                            |
| Dc        | float[3] | Diffuse color.                            |
| Oc        | float    | Opacity color (alpha).                    |
| Ec        | float[3] | Emission color.                           |
| Sc        | float[3] | Specular color.                           |
| Sp        | float    | Specular power.                           |
| Dt_name   | string   | Diffuse texture name.                     |
| Dt_flags  | uint32   | Diffuse texture wrap flags.               |
| Et_name   | string   | Emission texture name.                    |
| Et_flags  | uint32   | Emission texture wrap flags.              |
| Bt_name   | string   | Detail texture name.                      |
| Bt_flags  | uint32   | Detail texture wrap flags.                |
| Nt_name   | string   | Nomad texture name.                       |
| Nt_flags  | uint32   | Nomad texture wrap flags.                 |
| Alpha     | float    | Opacity level.                            |
| Fade      | float    | Steep view angle fade factor.             |
| Scale     | float    | Vertex offset scaling?                    |
| Dm_name   | string   | Diffuse mask texture name.                |
| Dm_flags  | uint32   | Diffuse mask texture wrap flags.          |
| TileRate  | float    | Diffuse mask texture tiling multiplier.   |
| Dm0_name  | string   | Diffuse mask 0 texture name.              |
| Dm0_flags | uint32   | Diffuse mask 0 texture wrap flags.        |
| TileRate0 | float    | Diffuse mask 0 texture tiling multiplier. |
| Dm1_name  | string   | Diffuse mask 1 texture name.              |
| Dm1_flags | uint32   | Diffuse mask 1 texture wrap flags.        |
| TileRate1 | float    | Diffuse mask 1 texture tiling multiplier. |
| flip u    | uint32   | Flip texture horizontally.                |
| flip v    | uint32   | Flip texture vertically.                  |

- `Ac` is used in `AtmosphereMaterial`, but can be applied to many other materials to override ambient color from scene.
- `Oc` is used in any transparent material.
- `Ec` is used in `DcDtEc`, `DcDtEcOcOt`, `EcEt`.
- ❗ There is no "`Ot_name`" or "`Ot_flags`" since transparency is taken from alpha channel of texture formats which support transparency.
- `Et_name` and `Et_flags` are used in `DcDtEt` and `EcEt`.
- `Bt_name` and `Bt_flags` are used in `BtDetailMapMaterial` and `BtDetailMapMaterialTwo`.
- `Nt_name` and `Nt_flags` are used in `NomadMaterial` and `NomadMaterialNoBendy`.
- `Alpha`, `Fade` and `Scale` are used in `AtmosphereMaterial`.
- `Dm_name`, `Dm_flags` and `TileRate` are used in `DetailMapMaterial`.
- `Dm0_name`, `Dm0_flags` and `TileRate0` are used in `DetailMap2Dm1Msk2PassMaterial`, `IllumDetailMapMaterial`, `Masked2DetailMapMaterial`.
- `Dm1_name`, `Dm1_flags` and `TileRate1` are used in `DetailMap2Dm1Msk2PassMaterial`, `IllumDetailMapMaterial`, `Masked2DetailMapMaterial`.

## Material animation

```mermaid
stateDiagram-v2
    direction LR
    Library: Material library

    [*] --> Library
    Library --> MaterialAnim
    MaterialAnim --> material_name
    material_name --> MACount
    material_name --> MADeltas
    material_name --> MAKeys
    material_name --> MAFlags
```

Material animation is stored in model file and permits simple UV offset and scaling looped keyframe animation.

| Name     | Type      | Description                             |
| -------- | --------- | --------------------------------------- |
| MACount  | uint32    | Number of MADeltas keyframes.           |
| MADeltas | _varying_ | UV offset and scale velocity keyframes. |
| MAKeys   | _varying_ | UV offset and scale keyframes.          |
| MAFlags  | uint32    | Animation flags.                        |

Each keyframe in `MADeltas`:

| Name         | Type  | Description               |
| ------------ | ----- | ------------------------- |
| time         | float | Keyframe time.            |
| uOffsetSpeed | float | U tiling offset velocity. |
| vOffsetSpeed | float | V tiling offset velocity. |
| uScaleSpeed  | float | U tiling scale velocity.  |
| vScaleSpeed  | float | V tiling scale velocity.  |

Each keyframe in `MAKeys`:

| Name    | Type  | Description     |
| ------- | ----- | --------------- |
| uOffset | float | U start offset. |
| vOffset | float | V start offset. |
| uScale  | float | U start scale.  |
| vScale  | float | V start scale.  |

- `MAKeys` keyframes count will be one less MACount. First keyframe is implicit state of original UV values.
