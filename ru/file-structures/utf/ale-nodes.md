---
title: Узлы алхимии
---

## Оглавление

- [Оглавление](#оглавление)
  - [Обзор](#обзор)
  - [Характеристики](#характеристики)
  - [Узлы](#узлы)
    - [FxNode](#fxnode)
    - [FxCubeEmitter](#fxcubeemitter)
    - [FxSphereEmitter](#fxsphereemitter)
    - [FxConeEmitter](#fxconeemitter)
    - [FxBasicAppearance](#fxbasicappearance)
    - [FxRectAppearance](#fxrectappearance)
    - [FxOrientedAppearance](#fxorientedappearance)
    - [FxPerpAppearance](#fxperpappearance)
    - [FLBeamAppearance](#flbeamappearance)
    - [FLDustAppearance](#fldustappearance)
    - [FxParticleAppearance](#fxparticleappearance)
    - [FxMeshAppearance](#fxmeshappearance)
    - [FxRadialField](#fxradialfield)
    - [FxGravityField](#fxgravityfield)
    - [FxCollideField](#fxcollidefield)
    - [FxTurbulenceField](#fxturbulencefield)
    - [FxAirField](#fxairfield)
    - [FLDustField](#fldustfield)
    - [FLBeamField](#flbeamfield)

### Обзор

### Характеристики

Это список известных свойств, используемых в архетипах узлов алхимии.

| Имя                              | Тип            | Описание                                                                    |
| -------------------------------- | -------------- | --------------------------------------------------------------------------- |
| Node_Name                        | String         | Имя архетипа. Обязательное свойство.                                        |
| Node_LifeSpan                    | Float          | Срок службы узла. Обязательное свойство.                                    |
| Node_Transform                   | Transform      | Преобразование узла. Обязательное свойство.                                 |
| ~~Node_ClassName~~               | String         | Неиспользованный.                                                           |
| Emitter_LODCurve                 | Animated float | Кривая смещения уровня детектирования излучателя.                           |
| Emitter_InitialParticles         | Integer        | Число изначально созданных частиц.                                          |
| Emitter_Frequency                | Animated curve | Скорость/частота появления частиц (единиц в секунду).                       |
| Emitter_MaxParticles             | Animated curve | Максимально допустимое количество частиц.                                   |
| Emitter_EmitCount                | Animated curve | Неизвестный.                                                                |
| Emitter_InitialLifeSpan          | Animated curve | Продолжительность жизни частиц назначается при их генерации.                |
| Emitter_Pressure                 | Animated curve | Начальная скорость. Должна быть выше 0, чтобы некоторые частицы были видны. |
| Emitter_VelocityApproach         | Animated curve | Наследует скорость родительского объекта.                                   |
| CubeEmitter_Width                | Animated curve | Ширина FxCubeEmitter.                                                       |
| CubeEmitter_Height               | Animated curve | Высота FxCubeEmitter.                                                       |
| CubeEmitter_Depth                | Animated curve | Глубина FxCubeEmitter.                                                      |
| CubeEmitter_MinSpread            | Animated curve | Минимальный угол рассеивания FxCubeEmitter.                                 |
| CubeEmitter_MaxSpread            | Animated curve | Максимальный угол рассеивания FxCubeEmitter.                                |
| SphereEmitter_MinRadius          | Animated curve | Внутренний радиус FxSphereEmitter (полый).                                  |
| SphereEmitter_MaxRadius          | Animated curve | Внешний радиус FxSphereEmitter.                                             |
| ConeEmitter_MinRadius            | Animated curve | Внутренний радиус FxConeEmitter (полый).                                    |
| ConeEmitter_MaxRadius            | Animated curve | Внешний радиус FxConeEmitter.                                               |
| ConeEmitter_MinSpread            | Animated curve | Минимальный угол рассеивания FxConeEmitter.                                 |
| ConeEmitter_MaxSpread            | Animated curve | Максимальный угол рассеивания FxConeEmitter.                                |
| Appearance_LODCurve              | Animated float | Внешний вид кривой смещения LOD.                                            |
| BasicApp_TriTexture              | Boolean        | Используйте треугольную сетку.                                              |
| BasicApp_QuadTexture             | Boolean        | Используйте четырехъядерную сетку.                                          |
| BasicApp_MotionBlur              | Boolean        | Применяет размытие движения для нетекстурированных объектов.                |
| BasicApp_Color                   | Animated color | Анимация цветовых оттенков.                                                 |
| BasicApp_Alpha                   | Animated float | Цветная альфа-анимация.                                                     |
| BasicApp_Size                    | Animated float | Размер сетки.                                                               |
| BasicApp_HtoVAspect              | Animated float | Соотношение сторон по горизонтали и вертикали.                              |
| BasicApp_Rotate                  | Animated float | Анимация вращения. Игнорируется при включенном эффекте MotionBlur.          |
| BasicApp_TexName                 | String         | Название текстуры.                                                          |
| BasicApp_BlendInfo               | Color blending | Режим смешивания цветов.                                                    |
| BasicApp_UseCommonTexFrame       | Boolean        | Используйте обычную анимацию текстур.                                       |
| BasicApp_TexFrame                | Animated float | Анимация индивидуальной текстуры частиц.                                    |
| BasicApp_CommonTexFrame          | Animated curve | Анимация текстуры общего узла.                                              |
| BasicApp_FlipTexU                | Boolean        | Отразить текстуру по горизонтали.                                           |
| BasicApp_FlipTexV                | Boolean        | Отразить текстуру вертикально.                                              |
| OrientedApp_Width                | Animated float |                                                                             |
| OrientedApp_Height               | Animated float |                                                                             |
| RectApp_CenterOnPos              | Boolean        |                                                                             |
| RectApp_ViewingAngleFade         | Boolean        | Спрайт затухает при большом угле обзора.                                    |
| RectApp_Scale                    | Animated float |                                                                             |
| RectApp_Length                   | Animated float |                                                                             |
| RectApp_Width                    | Animated float |                                                                             |
| BeamApp_DisablePlaceHolder       | Boolean        |                                                                             |
| BeamApp_DupeFirstParticle        | Boolean        |                                                                             |
| BeamApp_LineAppearance           | Boolean        |                                                                             |
| ParticleApp_LifeName             | String         | Относится к названию эффекта, отображаемому в течение срока действия.       |
| ParticleApp_DeathName            | String         | Относится к названию эффекта, отображаемому в конце.                        |
| ParticleApp_UseDynamicRotation   | Boolean        | Применяет преобразование из этого узла.                                     |
| ParticleApp_SmoothRotation       | Boolean        |                                                                             |
| ~~MeshApp_MeshId~~               | Integer        | Неизвестный. Начальный индекс группы сетки?                                 |
| ~~MeshApp_MeshName~~             | String         | Unknown                                                                     |
| ~~MeshApp_UseParticleTransform~~ | Boolean        | Позволяет ли преобразовывать отдельные частицы?                             |
| ~~MeshApp_ParticleTransform~~    | Transform      | Преобразование отдельных частиц?                                            |
| RadialField_Approach             | Animated curve |                                                                             |
| RadialField_Attenuation          | Animated float |                                                                             |
| RadialField_Magnitude            | Animated curve |                                                                             |
| RadialField_Radius               | Animated curve |                                                                             |
| CollideField_Height              | Animated curve |                                                                             |
| CollideField_Reflectivity        | Animated curve |                                                                             |
| CollideField_Width               | Animated curve |                                                                             |
| AirField_Approach                | Animated curve |                                                                             |
| AirField_Magnitude               | Animated curve |                                                                             |
| GravityField_Gravity             | Animated curve |                                                                             |
| TurbulenceField_Approach         | Animated curve |                                                                             |
| TurbulenceField_Magnitude        | Animated curve |                                                                             |
| 0x1C65B7B9                       | Boolean        | Дубликат BeamApp_LineAppearance.                                            |
| 0x0BA0B3BB                       | Transform      | Неизвестный.                                                                |
| 0x03503B61                       | Boolean        | Неизвестный.                                                                |
| 0x0ABE0402                       | Boolean        | Неизвестный.                                                                |
| 0xE63AA248                       | Animated curve | Неизвестный.                                                                |

- ❔ 0xE63AA248 тип появляется в некоторых узлах FLDustField.
- ❔ 0x0BA0B3BB, 0x03503B61 и 0x0ABE0402 типы появляются в tail.app (FLBeamAppearance) gf_tradelaneship01.ale.
- BasicApp_CommonTexFrame может анимировать текстуры с несколькими подтекстурами (т.е. количество текстур > 1), в то время как BasicApp_TexFrame не может (по умолчанию используется последняя текстура). Свойство частоты кадров игнорируется и зависит от воспроизведения, управляемого кривой (0.0 — первый кадр, 1.0 — последний кадр).

### Узлы

- Префикс «FL» в некоторых именах не является опечаткой.

#### FxNode

Может использоваться для группировки нескольких узлов для преобразований.

- Node_Name
- Node_LifeSpan
- Node_Transform

#### FxCubeEmitter

Излучатель кубического объема.

- Node_Name
- Node_LifeSpan
- Node_Transform
- Emitter_LODCurve
- Emitter_InitialParticles
- Emitter_Frequency
- Emitter_MaxParticles
- Emitter_EmitCount
- Emitter_InitLifeSpan
- Emitter_Pressure
- Emitter_VelocityApproach
- CubeEmitter_Width
- CubeEmitter_Depth
- CubeEmitter_Height
- CubeEmitter_MinSpread
- CubeEmitter_MaxSpread

#### FxSphereEmitter

Сферический объемный излучатель.

- Node_Name
- Node_LifeSpan
- Node_Transform
- Emitter_LODCurve
- Emitter_InitialParticles
- Emitter_Frequency
- Emitter_MaxParticles
- Emitter_EmitCount
- Emitter_InitLifeSpan
- Emitter_Pressure
- Emitter_VelocityApproach
- SphereEmitter_MinRadius
- SphereEmitter_MaxRadius

#### FxConeEmitter

Конусный объемный излучатель.

- Node_Name
- Node_LifeSpan
- Node_Transform
- Emitter_LODCurve
- Emitter_InitialParticles
- Emitter_Frequency
- Emitter_MaxParticles
- Emitter_EmitCount
- Emitter_InitLifeSpan
- Emitter_Pressure
- Emitter_VelocityApproach
- ConeEmitter_MinRadius
- ConeEmitter_MaxRadius
- ConeEmitter_MinSpread
- ConeEmitter_MaxSpread

#### FxBasicAppearance

Простой спрайт рекламного щита, повернутый к камере.

- Node_Name
- Node_LifeSpan
- Node_Transform
- Appearance_LODCurve
- BasicApp_TriTexture
- BasicApp_QuadTexture
- BasicApp_MotionBlur
- BasicApp_Color
- BasicApp_Alpha
- BasicApp_Size
- BasicApp_HToVAspect
- BasicApp_Rotate
- BasicApp_TexName
- BasicApp_BlendInfo
- BasicApp_UseCommonTexFrame
- BasicApp_TexFrame
- BasicApp_CommonTexFrame
- BasicApp_FlipTexU
- BasicApp_FlipTexV

#### FxRectAppearance

- Node_Name
- Node_LifeSpan
- Node_Transform
- Appearance_LODCurve
- BasicApp_MotionBlur
- RectApp_CenterOnPos
- RectApp_ViewingAngleFade
- BasicApp_Color
- BasicApp_Alpha
- RectApp_Scale
- RectApp_Length
- RectApp_Width
- BasicApp_TexName
- BasicApp_BlendInfo
- BasicApp_UseCommonTexFrame
- BasicApp_TexFrame
- BasicApp_CommonTexFrame
- BasicApp_FlipTexU
- BasicApp_FlipTexV

#### FxOrientedAppearance

Плоский спрайт, ориентация которого не зависит от направления частиц.

- Node_Name
- Node_LifeSpan
- Node_Transform
- Appearance_LODCurve
- RectApp_ViewingAngleFade
- OrientedApp_Width
- OrientedApp_Height
- BasicApp_Color
- BasicApp_Alpha
- BasicApp_TexName
- BasicApp_BlendInfo
- BasicApp_UseCommonTexFrame
- BasicApp_TexFrame
- BasicApp_CommonTexFrame
- BasicApp_FlipTexU
- BasicApp_FlipTexV

#### FxPerpAppearance

Спрайт рекламного щита обращен перпендикулярно направлению его частиц.

- Node_Name
- Node_LifeSpan
- Node_Transform
- Appearance_LODCurve
- RectApp_ViewingAngleFade
- BasicApp_Color
- BasicApp_Alpha
- BasicApp_Size
- BasicApp_TexName
- BasicApp_BlendInfo
- BasicApp_UseCommonTexFrame
- BasicApp_TexFrame
- BasicApp_CommonTexFrame
- BasicApp_FlipTexU
- BasicApp_FlipTexV

#### FLBeamAppearance

Пересекающиеся прямоугольники образуют отрезки прямых из частиц.

- Node_Name
- Node_LifeSpan
- Node_Transform
- Appearance_LODCurve
- BasicApp_Color
- BasicApp_Alpha
- RectApp_Scale
- RectApp_Width
- BasicApp_TexName
- BasicApp_BlendInfo
- BasicApp_UseCommonTexFrame
- BasicApp_TexFrame
- BasicApp_CommonTexFrame
- BasicApp_FlipTexU
- BasicApp_FlipTexV
- BeamApp_DisablePlaceHolder
- BeamApp_DupeFirstParticle
- BeamApp_LineAppearance

#### FLDustAppearance

Спрайт рекламного щита, изменяющий прозрачность в зависимости от движения камеры: когда спрайты покоя прозрачны, они становятся непрозрачными при движении или вращении камеры.

- Node_Name
- Node_LifeSpan
- Node_Transform
- BasicApp_Color
- BasicApp_Alpha
- BasicApp_Size
- BasicApp_TexName
- BasicApp_BlendInfo
- BasicApp_UseCommonTexFrame
- BasicApp_TexFrame
- BasicApp_CommonTexFrame
- BasicApp_FlipTexU
- BasicApp_FlipTexV

#### FxParticleAppearance

Внешний вид, который использует другие эффекты в том же файле .ale для визуализации.
Когда частицы живы, они воспроизводят эффект, указанный в `ParticleApp_LifeName`, а после истечения срока действия — эффект `ParticleApp_DeathName`.
`ParticleApp_UseDynamicRotation` применяет вращение от ориентации частицы.
`ParticleApp_SmoothRotation` включает или отключает сферическую линейную интерполяцию для движения вращения.

- Node_Name
- Node_LifeSpan
- Node_Transform
- ParticleApp_LifeName
- ParticleApp_DeathName
- ParticleApp_UseDynamicRotation
- ParticleApp_SmoothRotation

#### FxMeshAppearance

❗ Не работает.

- Node_Name
- Node_LifeSpan
- Node_Transform
- MeshApp_MeshId
- MeshApp_MeshName
- MeshApp_UseParticleTransform
- MeshApp_ParticleTransform

#### FxRadialField

Поле аттрактора/рефлектора.

- Node_Name
- Node_LifeSpan
- Node_Transform
- RadialField_Radius
- RadialField_Attenuation
- RadialField_Magnitude
- RadialField_Approach

#### FxGravityField

Ускоряет частицы. Используйте вращение `Node_Transform` для изменения направления.

- Node_Name
- Node_LifeSpan
- Node_Transform
- GravityField_Gravity

#### FxCollideField

Создает плоское поле отражения поверхности.

- Node_Name
- Node_LifeSpan
- Node_Transform
- CollideField_Reflectivity
- CollideField_Width
- CollideField_Height

#### FxTurbulenceField

Беспорядочно встряхивайте частицы.

- Node_Name
- Node_LifeSpan
- Node_Transform
- TurbulenceField_Magnitude
- TurbulenceField_Approach

#### FxAirField

Перезаписывает скорость частиц.

- Node_Name
- Node_LifeSpan
- Node_Transform
- AirField_Magnitude
- AirField_Approach

#### FLDustField

Сохраняет частицы визуализированными только в пределах объема сферы.

- Node_Name
- Node_LifeSpan
- Node_Transform
- SphereEmitter_MaxRadius

#### FLBeamField

- Node_Name
- Node_LifeSpan
- Node_Transform
