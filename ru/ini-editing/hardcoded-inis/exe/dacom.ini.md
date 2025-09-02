---
title: dacom.ini
---

## Оглавление

- [Оглавление](#оглавление)
  - [Обзор](#обзор)
  - [Синтаксис](#синтаксис)
    - [\[DACOM\]](#dacom)
    - [\[Libraries\]](#libraries)
    - [\[System\]](#system)
    - [\[Engine\]](#engine)
    - [\[RenderManager\]](#rendermanager)
    - [\[TriMesh\]](#trimesh)
    - [\[RenderPipeline\]](#renderpipeline)
    - [\[TextureLibrary\]](#texturelibrary)
    - [\[SoundManager\]](#soundmanager)
    - [\[Alchemy\]](#alchemy)
    - [\[BatchedMaterials\]](#batchedmaterials)
    - [\[MaterialMap\]](#materialmap)

### Обзор

Этот файл управляет настройкой параметров времени запуска приложения и загрузкой библиотеки.

### Синтаксис

Каждый из следующих разделов может быть написан только один раз, желательно в указанном порядке.

#### [DACOM]

| Ключ               | Значение | Несколько | Примечание                                                                      |
| ------------------ | -------- | --------- | ------------------------------------------------------------------------------- |
| **IgnoreDACOMEnv** | boolean  | нет       |                                                                                 |
| **DLLPath**        | path     | нет       | Этот путь определяет, где `dacom.dll` ищет библиотеки, вызываемые в этом файле. |

#### [Libraries]

Записи DLL в этом блоке определяются как ключ без значения. Для поиска этих файлов используется DLLPath, как определено в блоке [DACOM].

#### [System]

Вызывает значения из Windows API. Записи в этом блоке определяются как ключ без значения.

#### [Engine]

Вызывает значения из Windows API. Записи в этом блоке определяются как ключ без значения.

#### [RenderManager]

Вызывает значения из Windows API. Записи в этом блоке определяются как ключ без значения.

#### [TriMesh]

| Ключ      | Значение | Множественное | Примечание |
| --------- | -------- | ------------- | ---------- |
| tristrips | boolean  | no            |            |

#### [RenderPipeline]

| Ключ                          | Значение | Несколько | Примечание                                                                                                     |
| ----------------------------- | -------- | --------- | -------------------------------------------------------------------------------------------------------------- |
| **MGSDB**                     | path     | нет       | Имя файла `FLConfigDatabase`, используемого для настройки видеокарт в игре Freelancer                          |
| **DEVICE_GAMMA**              | boolean  | нет       | Принудительно включает контроль гаммы                                                                          |
| **TEXTURE_ALLOW_DXT**         | boolean  | нет       | Принудительно включает поддержку DXT                                                                           |
| **ALPHAREF**                  | integer  | нет       | `d3drenderstate`: значение по умолчанию для alpha ref                                                          |
| **ALPHATESTENABLE**           | boolean  | нет       | `d3drenderstate`: базовая проверка альфа-канала                                                                |
| **ALPHAFUNC**                 | integer  | нет       | `d3drenderstate`: `D3DCMP_GREATER`                                                                             |
| **LOCALVIEWER**               | boolean  | нет       | `d3drenderstate`: блики от источников света                                                                    |
| **zfunc**                     | integer  | нет       | Функция сравнения по глубине по умолчанию: `D3DCMP_LESSEQUAL`                                                  |
| **FPU_PRESERVE**              | boolean  | нет       | Direct3D должен сохранять и восстанавливать состояние FPU каждый раз при необходимости изменения состояния FPU |
| **MULTITHREADED**             | boolean  | нет       | Запрос многопоточной безопасности. Direct3D чаще использует глобальный критический раздел.                     |
| **HARDWARE_VERTEXPROCESSING** | boolean  | нет       | Флаги обработки вершин взаимно исключающие. Если устройство не поддерживает HW-TL, будет использован SW-TL     |
| **MIXED_VERTEXPROCESSING**    | boolean  | нет       |                                                                                                                |
| **SOFTWARE_VERTEXPROCESSING** | boolean  | нет       |                                                                                                                |
| **LOCKABLE_BACKBUFFER**       | boolean  | нет       | Разрешить блокировку backbuffer                                                                                |
| **USE_SYSLOCK**               | boolean  | нет       | Ресурсы (vb, ib, texture) должны использовать глобальную критическую блокировку Windows при использовании      |
| **HANDLE_SWAPLOSS**           | boolean  | нет       |                                                                                                                |
| **VIEWSPACE_LIGHTS**          | boolean  | нет       |                                                                                                                |
| **TEXTURE_CUBEMAPS**          | boolean  | нет       |                                                                                                                |

#### [TextureLibrary]

| Ключ                     | Значение | Несколько | Примечание                                                                                                    |
| ------------------------ | -------- | --------- | ------------------------------------------------------------------------------------------------------------- |
| **TEXTURE_LOD_LOAD_MIN** | integer  | нет       | Хотя это может работать в других приложениях, в Freelancer файл `perfoptions.ini` переопределит это значение. |

#### [SoundManager]

| Ключ                     | Значение | Множественное | Примечание                                                        |
| ------------------------ | -------- | ------------- | ----------------------------------------------------------------- |
| speakerConfiguration     | integer  | no            | установите только если вы хотите переопределить настройки Windows |
| createAll2dInSoftware    | boolean  | no            |                                                                   |
| 3D_SW_Algorithm          | string   | no            |                                                                   |
| use2DHW                  | integer  | boolean       |                                                                   |
| use3DHW                  | integer  | boolean       |                                                                   |
| maxSoundChannels         | integer  | no            |                                                                   |
| FORCE_FREQ_CONTROL_TO_SW | boolean  | no            |                                                                   |
| max3DPan                 | integer  | no            |                                                                   |

#### [Alchemy]

| Ключ                              | Значение | Несколько | Примечание                                                                   |
| --------------------------------- | -------- | --------- | ---------------------------------------------------------------------------- |
| **Alchemy.maxVertices**           | integer  | нет       | Не используется, переопределяется пулом частиц                               |
| **Alchemy.maxIndices**            | integer  | нет       | Не используется, переопределяется пулом частиц                               |
| **Alchemy.useMaterialBatcher**    | boolean  | нет       |                                                                              |
| **FxBasicAppearance.poolSize**    | integer  | нет       | Максимальное количество частиц BasicAppearance, отображаемых одновременно    |
| **FxRectAppearance.poolSize**     | integer  | нет       | Максимальное количество частиц RectAppearance, отображаемых одновременно     |
| **FxPerpAppearance.poolSize**     | integer  | нет       | Максимальное количество частиц PerpAppearance, отображаемых одновременно     |
| **FxOrientedAppearance.poolSize** | integer  | нет       | Максимальное количество частиц OrientedAppearance, отображаемых одновременно |
| **FLBeamAppearance.poolSize**     | integer  | нет       | Максимальное количество частиц BeamAppearance, отображаемых одновременно     |
| **FLDustAppearance.poolSize**     | integer  | нет       | Максимальное количество частиц DustAppearance, отображаемых одновременно     |
| **FxMeshAppearance.poolSize**     | integer  | нет       | Максимальное количество частиц MeshAppearance, отображаемых одновременно     |
| **MeshAppearance.poolSize**       | integer  | нет       | Максимальное количество частиц BasicAppearance, отображаемых одновременно    |
| **FxParticleAppearance.poolSize** | integer  | нет       | Максимальное количество частиц ParticleAppearance, отображаемых одновременно |

#### [BatchedMaterials]

| Ключ | Значение | Множественное | Примечание |
| ---- | -------- | ------------- | ---------- |
| Type | string   | no            |            |

#### [MaterialMap]

| Ключ          | Значение | Несколько | Примечание                                                                                                         |
| ------------- | -------- | --------- | ------------------------------------------------------------------------------------------------------------------ |
| **DcDtEtTwo** | string   |           | Предопределённые типы материалов                                                                                   |
| **EcEtOcOt**  | string   |           | Предопределённые типы материалов                                                                                   |
| **DcDtEcEt**  | string   |           | Предопределённые типы материалов                                                                                   |
| **name**      | string   | да        | Все записи здесь, похоже, являются регулярными выражениями для имени материала, чтобы переопределить тип материала |
