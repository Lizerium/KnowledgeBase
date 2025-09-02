---
title: missions.ini
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
    - [\[Mission\]](#mission)
    - [\[NPC\]](#npc)
    - [\[Dialog\]](#dialog)
    - [\[Trigger\]](#trigger)
    - [\[MsnRandEnc\]](#msnrandenc)
    - [\[NNObjective\]](#nnobjective)
    - [\[ObjList\]](#objlist)
    - [\[MsnSolar\]](#msnsolar)
    - [\[MsnShip\]](#msnship)
    - [\[MsnLoot\]](#msnloot)
    - [\[MsnFormation\]](#msnformation)

### Обзор

Эти файлы управляют триггерами сюжетных миссий и состоят из серии триггеров, условий и действий, позволяющих создавать сложные, разветвлённые миссии. По умолчанию можно определить максимум 14 таких файлов (от миссии 01a до миссии 13).

#### Ванильные примеры

- `DATA\MISSIONS\M01A\m01a.ini`
- `DATA\MISSIONS\M09\m09.ini`
- `DATA\MISSIONS\M11\m11.ini`

### Синтаксис

Несколько блоков могут быть определены в любом порядке.

#### [Mission]

Похоже, этот блок определяется только один раз для каждого файла.

```ini
[Mission]
mission_title = INT
mission_offer = INT
reward = INT
npc_ship_file = PATH
```

| Параметр          | Описание                                                                                                                                                       |
| ----------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **mission_title** | Похоже, это IDS, определяющий название миссии при её предложении на базе.                                                                                      |
| **mission_offer** | Похоже, это текст, который отображается при предложении миссии на базе.                                                                                        |
| **reward**        | Награда в кредитах за выполнение миссии.                                                                                                                       |
| **npc_ship_file** | Ссылка на файл [npcships.ini](./npcships.ini.md), используемый для миссии. Каждая миссия имеет свой файл, расположенный в той же папке, что и INI-файл миссии. |

#### [NPC]

Похоже, что синтаксис аналогичен [specific_npc.ini](./specific_npc.ini.md), но с добавлением ключа `npc_ship_arch`.

```ini
[NPC]
nickname = STRING
space_costume = STRING, STRING, STRING
affiliation = STRING
npc_ship_arch = STRING ;optional
individual_name = INT
voice = STRING ;optional
```

| Параметр            | Описание                                                                                                   |
| ------------------- | ---------------------------------------------------------------------------------------------------------- |
| **nickname**        | Как этот НПС ссылается в блоках `[MsnShip]`.                                                               |
| **space_costume**   | Ссылка на записи `Head`, `Body` и `Accessory` из [bodyparts.ini](./../../../typed-inis/bodyparts.md).      |
| **affiliation**     | Ссылка на запись `FactionProps` из [faction_prop.ini](./faction_prop.ini.md).                              |
| **npc_ship_arch**   | Ссылка на NpcShipArch из файла [npcships.ini](./npcships.ini.md), используемого для миссии.                |
| **individual_name** | IDS-имя, отображаемое в космосе для этого НПС. Может быть переопределено ключом `random_name` в `MsnShip`. |
| **voice**           | Запись голоса, используемая для НПС, из [voices.ini](../../../typed-inis/voices.md).                       |

#### [Dialog]

```ini
[Dialog]
nickname = STRING
system = STRING
line = STRING, STRING, STRING, FLOAT, FLOAT
```

| Параметр | Описание |
| -------- | -------- |
| nickname |          |
| system   |          |
| line     |          |

#### [Trigger]

Триггер представляет собой набор действий, которые необходимо выполнить при выполнении определенных условий.

```ini
[Trigger]
nickname = STRING
repeatable = BOOL
system = STRING
InitState = ENUM ;optional
Cnd_True = ENUM ;optional
Cnd_Destroyed = STRING, INT, ENUM ;optional
Cnd_Timer = FLOAT ;optional
Cnd_CharSelect = STRING, STRING, STRING ;optional
Cnd_CargoScanned = STRING, STRING ;optional
Cnd_CommComplete = STRING ;optional
Cnd_LaunchComplete = STRING, STRING ;optional
Cnd_JumpInComplete = STRING ;optional
Cnd_JumpgateAct = STRING ;optional
Cnd_PlayerLaunch = ENUM ;optional
Cnd_SpaceEnter = STRING ;optional
Cnd_SpaceExit = ENUM ;optional
Cnd_SystemEnter = STRING, ENUM, ... ;optional
Cnd_SystemExit = STRING, ENUM, ... ;optional
Cnd_BaseEnter = STRING ;optional
Cnd_BaseExit = STRING ;optional
Cnd_LocEnter = STRING, STRING ;optional
Cnd_InZone = BOOL, STRING, STRING ;optional
Cnd_InTradelane = BOOL, STRING ;optional
Cnd_InSpace = BOOL ;optional
Cnd_DistShip = ENUM, STRING, STRING, INT ;optional
Cnd_DistVec = ENUM, STRING, INT, INT, INT, INT ;optional
Cnd_DistVecLbL = ENUM, STRING, STRING, INT, INT, INT, INT ;optional
Cnd_DistCircle = STRING, STRING ;optional
Cnd_HealthDec = STRING, FLOAT ;optional
Cnd_EncLaunched = STRING ;optional
Cnd_HasMsn = BOOL ;optional
Cnd_WatchVibe = STRING, STRING, STRING, ENUM ;optional
Cnd_WatchTrigger = STRING, BOOL ;optional
Cnd_TLExited = STRING, ENUM, STRING ;optional
Cnd_TLEntered = STRING, STRING, STRING ;optional
Cnd_TetherBroke = STRING, STRING, INT, INT, INT ;optional
Cnd_ProjHitShipToLbl = STRING, INT, STRING ;optional
Cnd_ProjHit = STRING, INT, STRING ;optional
Cnd_RumorHeard = STRING ;optional
Cnd_PlayerManeuver = STRING, STRING ;optional
Cnd_NPCSystemEnter = STRING, STRING, STRING ;optional
Cnd_MsnResponse = ENUM ;optional
Cnd_LootAcquired = STRING, STRING ;optional
Act_ActTrig = STRING ;optional
Act_DeactTrig = STRING ;optional
Act_ChangeState = ENUM, INT ;optional
Act_SetVibeLbl = STRING, STRING, ENUM ;optional
Act_SetVibeLblToShip = STRING, STRING, ENUM ;optional
Act_SetVibeShipToLbl = STRING, STRING, ENUM ;optional
Act_SetRep = STRING, STRING, FLOAT ;optional
Act_Cloak = STRING, BOOL ;optional
Act_Invulnerable = STRING, BOOL, BOOL, FLOAT ;optional
Act_Destroy = STRING, ENUM ;optional
Act_SetNNObj = STRING, ENUM ;optional
Act_SetNNState = STRING, ENUM ;optional
Act_NNIds = INT, ENUM ;optional
Act_SetNNHidden = STRING, BOOL, BOOL ;optional
Act_GiveObjList = STRING, STRING ;optional
Act_RpopAttClamp = BOOL ;optional
Act_SetOffer = INT ;optional
Act_SetTitle = INT ;optional
Act_AddRTC = PATH ;optional
Act_RemoveRTC = PATH ;optional
Act_RandomPopSphere = INT, INT, INT, INT, ENUM ;optional
Act_Forceland = STRING ;optional
Act_PlayerCanDock = BOOL, STRING ;optional
Act_LockDock = STRING, STRING, ENUM ;optional
Act_PlayerCanTradelane = BOOL, STRING, STRING ;optional
Act_PobjIdle = ENUM ;optional
Act_SpawnShip = STRING, STRING, INT, INT, INT, FLOAT, FLOAT, FLOAT, FLOAT ;optional
Act_SpawnSolar = STRING ;optional
Act_SpawnFormation = STRING, STRING, INT, INT, INT, FLOAT, FLOAT, FLOAT, FLOAT ;optional
Act_EtherComm = STRING, INT, STRING, STRING, INT, STRING, STRING ;optional
Act_SendComm = STRING, STRING, STRING ;optional
Act_StartDialog = STRING ;optional
Act_PlayerEnemyClamp = INT, INT ;optional
Act_PlayMusic = STRING, STRING, STRING, STRING ;optional
Act_AdjHealth = STRING, FLOAT ;optional
Act_NagDistTowards =  ENUM, STRING, STRING, STRING, INT, INT, ENUM ;optional
Act_NagDistLeaving =  ENUM, STRING, STRING, STRING, INT, INT, ENUM ;optional
Act_NagOff = STRING ;optional
Act_NagClamp = BOOL ;optional
Act_MarkObj = STRING, INT ;optional
Act_SetLifetime = STRING, INT ;optional
Act_Save = STRING, INT ;optional
Act_SetInitialPlayerPos = INT, INT, INT, INT, INT, INT, INT ;optional
Act_EnableManeuver = STRING, BOOL ;optional
Act_LockManeuvers = TRUE ;optional
Act_EnableEnc = STRING ;optional
Act_DisableEnc = STRING ;optional
Act_Jumper = STRING, BOOL ;optional
Act_LightFuse = STRING, STRING ;optional
Act_RevertCam = ENUM ;optional
Act_AdjAcct = INT ;optional
Act_GCSClamp = BOOL ;optional
Act_MovePlayer = INT, INT, INT, INT ;optional
Act_RelocateShip = STRING, INT, INT, INT, FLOAT, FLOAT, FLOAT, FLOAT ;optional
Act_RelocateForm = STRING, INT ;optional
Act_CallThorn = PATH, STRING ;optional
Act_PlaySoundEffect = STRING ;optional
Act_SetShipAndLoadout = STRING, STRING ;optional
Act_Popupdialog = INT, INT, STRING ;optional
Act_AddAmbient = PATH, STRING ;optional
Act_RemoveAmbient = PATH ;optional
Act_HostileClamp = BOOL ;optional
Act_DisableTradelane = STRING ;optional
Act_StaticCam = FLOAT, FLOAT, FLOAT, FLOAT, FLOAT, FLOAT, FLOAT ;optional
Act_SpawnShipRel = SSTRING, INT, FLOAT ;optional
Act_SpawnLoot = STRING ;optional
Act_SetVibeOfferBaseHack = STRING ;optional
Act_SetOrient = STRING, INT, INT, INT, INT ;optional
Act_SetFlee = STRING ;optional
Act_RpopTLAttacksEnabled = BOOL ;optional
Act_RepChangeRequest = STRING ;optional
Act_RemoveCargo = STRING ;optional
Act_SetPriority = STRING, ENUM ;optional
Act_PilotParams = STRING ;optional
Act_PlayNN = STRING ;optional
Act_PlayerForm = STRING ;optional
Act_NNPath = INT, INT, STRING, STRING ;optional
Act_NagGreet = STRING, STRING ;optional
Act_GiveNNObjs = ENUM ;optional
Act_DockRequest = STRING ;optional
Act_DisableFriendlyFire = STRING ;optional
Act_DebugMsg = STRING ;optional
```

| Параметр                     | Описание                                                                                                                                                                                                                                                                                                                                                                                                |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **nickname**                 | Как этот триггер упоминается в других местах файла, обычно через `Act_ActTrig`.                                                                                                                                                                                                                                                                                                                         |
| **repeatable**               | Можно ли активировать триггер более одного раза. Ключ должен присутствовать для работы и обычно принимает значение `no_params`.                                                                                                                                                                                                                                                                         |
| **system**                   | Система, в которой срабатывает триггер, берётся из [Universe.ini](../../../typed-inis/universe.md).                                                                                                                                                                                                                                                                                                     |
| **InitState**                | Enum `ACTIVE`. Если ключ присутствует, триггер начинается в активированном состоянии.                                                                                                                                                                                                                                                                                                                   |
| **Cnd_True**                 | Обязательный ключ, если других условий нет. Принимает значение `no_params`.                                                                                                                                                                                                                                                                                                                             |
| **Cnd_Destroyed**            | Триггер требует уничтожения указанных объектов. Ссылается на `MsnShip`, `MsnSolar`, `label` или `MsnFormation`, число (вероятно, количество оставшихся или уничтоженных, `-1` используется для всех объектов группы) и необязательный Enum, который, по-видимому, определяет способ уничтожения.                                                                                                        |
| **Cnd_Timer**                | Триггер отсчитывает время с момента активации в секундах перед срабатыванием.                                                                                                                                                                                                                                                                                                                           |
| **Cnd_CharSelect**           | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Cnd_CargoScanned**         | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Cnd_CommComplete**         | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Cnd_LaunchComplete**       | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Cnd_JumpInComplete**       | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Cnd_JumpgateAct**          | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Cnd_PlayerLaunch**         | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Cnd_SpaceEnter**           | Принимает `no_params`, что означает, что триггер срабатывает, когда игрок выходит в космос через андерокинг, либо принимает [system](../../../typed-inis/universe.md), что, вероятно, требует выхода в космос именно в этой системе для срабатывания.                                                                                                                                                   |
| **Cnd_SpaceExit**            | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Cnd_SystemEnter**          | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Cnd_SystemExit**           | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Cnd_BaseEnter**            | Триггер срабатывает, когда игрок стыкуется на указанной базе. Ссылается на `Base` из [Universe.ini](../../../typed-inis/universe.md).                                                                                                                                                                                                                                                                   |
| **Cnd_BaseExit**             | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Cnd_LocEnter**             | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Cnd_InZone**               | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Cnd_InTradelane**          | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Cnd_InSpace**              | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Cnd_DistShip**             | Enum: `INSIDE` или `OUTSIDE`, а также `TICK_AWAY`, `TICK_ALWAYS` и `TICK_TOWARDS`.                                                                                                                                                                                                                                                                                                                      |
| **Cnd_DistVec**              | Триггер срабатывает, когда объект находится на определённом расстоянии от заданного вектора. Первый параметр — `inside` или `outside`, определяющий, должен ли объект быть внутри или снаружи заданного расстояния. Второй — объект (`MsnShip` или `Player`). Следующие три — координаты XYZ, затем float — требуемое расстояние. Наблюдается также параметр `tick_away`, но его назначение неизвестно. |
| **Cnd_DistVecLbL**           | Похоже на `Cnd_DistVec`, но применяется к группам с метками.                                                                                                                                                                                                                                                                                                                                            |
| **Cnd_DistCircle**           | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Cnd_HealthDec**            | Триггер требует, чтобы указанный `MsnShip` или `MsnSolar` имел здоровье ниже определённого значения. Первый параметр — объект, второй — процент от 0 до 1.                                                                                                                                                                                                                                              |
| **Cnd_EncLaunched**          | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Cnd_HasMsn**               | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Cnd_WatchVibe**            | Enum: `REP_FRIEND_MAXIMUM`, `REP_FRIEND_THRESHOLD`, `REP_NEUTRAL_FRIENDLY`, `REP_NEUTRAL`, `REP_NEUTRAL_HOSTILE`, `REP_HOSTILE_THRESHOLD`, `REP_HOSTILE_MAXIMUM`.                                                                                                                                                                                                                                       |
| **Cnd_WatchTrigger**         | Enum: `ON`, `OFF`, `ACTIVE`, `COMPLETE`.                                                                                                                                                                                                                                                                                                                                                                |
| **Cnd_TLExited**             | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Cnd_TLEntered**            | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Cnd_TetherBroke**          | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Cnd_ProjHitShipToLbl**     | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Cnd_ProjHit**              | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Cnd_RumorHeard**           | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Cnd_PlayerManeuver**       | Enum: `GOTO`, `DOCK`, `FORMATION`.                                                                                                                                                                                                                                                                                                                                                                      |
| **Cnd_NPCSystemEnter**       | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Cnd_MsnResponse**          | Требуется конкретный ответ от результата триггера `Act_AddRTC`. Enum: `REJECT` или `ACCEPT`.                                                                                                                                                                                                                                                                                                            |
| **Cnd_LootAcquired**         | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_ActTrig**              | Ссылка на триггер для активации. Все условия триггера должны быть выполнены для его срабатывания.                                                                                                                                                                                                                                                                                                       |
| **Act_DeactTrig**            | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_ChangeState**          | Enum: `FAIL` или `SUCCEED`.                                                                                                                                                                                                                                                                                                                                                                             |
| **Act_SetVibeLbl**           | Enum: `REP_FRIEND_MAXIMUM`, `REP_FRIEND_THRESHOLD`, `REP_NEUTRAL_FRIENDLY`, `REP_NEUTRAL`, `REP_NEUTRAL_HOSTILE`, `REP_HOSTILE_THRESHOLD`, `REP_HOSTILE_MAXIMUM`.                                                                                                                                                                                                                                       |
| **Act_SetVibeLblToShip**     | Enum: `REP_FRIEND_MAXIMUM`, `REP_FRIEND_THRESHOLD`, `REP_NEUTRAL_FRIENDLY`, `REP_NEUTRAL`, `REP_NEUTRAL_HOSTILE`, `REP_HOSTILE_THRESHOLD`, `REP_HOSTILE_MAXIMUM`.                                                                                                                                                                                                                                       |
| **Act_SetVibeShipToLbl**     | Enum: `REP_FRIEND_MAXIMUM`, `REP_FRIEND_THRESHOLD`, `REP_NEUTRAL_FRIENDLY`, `REP_NEUTRAL`, `REP_NEUTRAL_HOSTILE`, `REP_HOSTILE_THRESHOLD`, `REP_HOSTILE_MAXIMUM`.                                                                                                                                                                                                                                       |
| **Act_SetRep**               | Enum: `REP_FRIEND_MAXIMUM`, `REP_FRIEND_THRESHOLD`, `REP_NEUTRAL_FRIENDLY`, `REP_NEUTRAL`, `REP_NEUTRAL_HOSTILE`, `REP_HOSTILE_THRESHOLD`, `REP_HOSTILE_MAXIMUM`.                                                                                                                                                                                                                                       |
| **Act_Cloak**                | Включает или выключает маскировку на корабле, если у него есть устройство маскировки. Первый параметр — корабль, второй — true/false для состояния маскировки. Учтите, что NPC всё равно будут разговаривать, если у них задан голос.                                                                                                                                                                   |
| **Act_Invulnerable**         | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_Destroy**              | Уничтожает `MsnShip`, `MsnSolar` или `MsnFormation`. Первый параметр — объект для уничтожения, второй — метод. Enum: `EXPLODE` или `SILENT`.                                                                                                                                                                                                                                                            |
| **Act_SetNNObj**             | Устанавливает цель нейросети, например, точку маршрута или текст задачи. См. блок `[NNObjective]` для деталей. Enum: `OBJECTIVE_HISTORY` или `OBJECTIVE`. Кажется, можно установить только одну цель за раз.                                                                                                                                                                                            |
| **Act_SetNNState**           | Enum: `ACTIVE` или `COMPLETE`.                                                                                                                                                                                                                                                                                                                                                                          |
| **Act_NNIds**                | Enum: `HISTORY`.                                                                                                                                                                                                                                                                                                                                                                                        |
| **Act_SetNNHidden**          | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_GiveObjList**          | Отправляет `ObjList` к `MsnShip`. Первый параметр — корабль или формация, второй — набор команд `ObjList` для выдачи.                                                                                                                                                                                                                                                                                   |
| **Act_RpopAttClamp**         | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_SetOffer**             | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_SetTitle**             | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_AddRTC**               | Активирует набор катсцен в реальном времени (RTC) из конфигурации по указанному пути. Может быть повторяемым, если указан параметр `repeatable` в качестве второго аргумента.                                                                                                                                                                                                                           |
| **Act_RemoveRTC**            | Неясно, вероятно отключает состояние RTC, созданное `Act_AddRTC`. Требуются дополнительные тесты.                                                                                                                                                                                                                                                                                                       |
| **Act_RandomPopSphere**      | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_Forceland**            | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_PlayerCanDock**        | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_LockDock**             | Enum: `UNLOCK` и `LOCK`.                                                                                                                                                                                                                                                                                                                                                                                |
| **Act_PlayerCanTradelane**   | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_PobjIdle**             | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_SpawnShip**            | Создаёт `MsnShip`. Обязателен только первый аргумент. Остальные аргументы: `ObjList`, набор из 3 чисел для координат XYZ и набор из 4 чисел для ориентации WXYZ. Эти значения переопределяют настройки, заданные в `MsnShip`.                                                                                                                                                                           |
| **Act_SpawnSolar**           | Создаёт `MsnSolar`.                                                                                                                                                                                                                                                                                                                                                                                     |
| **Act_SpawnFormation**       | Создаёт `MsnFormation`. Обязателен только первый аргумент. Остальные аргументы: `ObjList`, набор из 3 чисел для координат XYZ и набор из 4 чисел для ориентации WXYZ. Эти значения переопределяют настройки, заданные в `MsnFormation`.                                                                                                                                                                 |
| **Act_EtherComm**            | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_SendComm**             | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_StartDialog**          | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_PlayerEnemyClamp**     | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_PlayMusic**            | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_AdjHealth**            | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_NagDistTowards**       | Enum: `NAG_ALWAYS` и `NAG_OUT_OF_COMBAT`.                                                                                                                                                                                                                                                                                                                                                               |
| **Act_NagDistLeaving**       | Enum: `NAG_ALWAYS` и `NAG_OUT_OF_COMBAT`.                                                                                                                                                                                                                                                                                                                                                               |
| **Act_NagOff**               | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_NagClamp**             | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_MarkObj**              | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_SetLifetime**          | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_Save**                 | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_SetInitialPlayerPos**  | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_EnableManeuver**       | Enum: `GOTO`, `DOCK` и `FORMATION`.                                                                                                                                                                                                                                                                                                                                                                     |
| **Act_LockManeuvers**        | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_EnableEnc**            | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_DisableEnc**           | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_Jumper**               | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_LightFuse**            | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_RevertCam**            | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_AdjAcct**              | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_GCSClamp**             | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_MovePlayer**           | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_RelocateShip**         | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_RelocateForm**         | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_CallThorn**            | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_PlaySoundEffect**      | Проигрывает [звук](../../../typed-inis/sounds.md). Звук, похоже, игнорирует регуляторы громкости и воспроизводится на полной громкости для игрока.                                                                                                                                                                                                                                                      |
| **Act_SetShipAndLoadout**    | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_Popupdialog**          | Отображает всплывающее окно на экране игрока. В космосе это приостанавливает игру. Первый параметр — IDS NAME для заголовка окна, второй — IDS INFO для содержимого. Enum: `CLOSE`, обязательный.                                                                                                                                                                                                       |
| **Act_AddAmbient**           | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_RemoveAmbient**        | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_HostileClamp**         | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_DisableTradelane**     | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_StaticCam**            | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_SpawnShipRel**         | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_SpawnLoot**            | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_SetVibeOfferBaseHack** | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_SetOrient**            | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_SetFlee**              | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_RpopTLAttacksEnabled** | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_RepChangeRequest**     | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_RemoveCargo**          | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_SetPriority**          | Enum: `NORMAL` и `ALWAYS_EXECUTE`.                                                                                                                                                                                                                                                                                                                                                                      |
| **Act_PilotParams**          | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_PlayNN**               | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_PlayerForm**           | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_NNPath**               | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_NagGreet**             | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_GiveNNObjs**           | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_DockRequest**          | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_DisableFriendlyFire**  | —                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Act_DebugMsg**             | —                                                                                                                                                                                                                                                                                                                                                                                                       |

#### [MsnRandEnc]

```ini
[MsnRandEnc]
nickname = STRING
encounter_type = STRING
attacker_rep_name = STRING
target_ship_name = STRING
activation_type = STRING, INT, INT
formation = STRING, INT, INT, INT, STRING, INT
num_forms = INT, INT
label = STRING
```

| Параметр          | Описание |
| ----------------- | -------- |
| nickname          |          |
| encounter_type    |          |
| attacker_rep_name |          |
| target_ship_name  |          |
| activation_type   |          |
| formation         |          |
| num_forms         |          |
| label             |          |

#### [NNObjective]

Представляет цель, которая будет отображена игроку в виде путевой точки или текстовой цели на экране.

```ini
[NNObjective]
nickname = STRING
state = ENUM
type = STRING, INT
```

| Параметр     | Описание                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| ------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **nickname** | Как этот `NNObjective` упоминается в других местах файла.                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| **state**    | Начальное состояние цели. Enum: `HIDDEN` (скрыта), `ACTIVE` (активна) и `COMPLETE` (завершена).                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **type**     | Типы NNObjectives: <br/><br/> **ids**: Строка, записываемая в журнал Нейросети как цель и отображаемая на экране. Принимает одну строку. <br/><br/> **rep_inst**: Помечает конкретный корабль или объект `solar` маркером, как если бы он был назначен как цель. Требует две строки для журнала Нейросети, набор координат XYZ и объект для пометки. В vanilla координаты часто равны 0. <br/><br/> **navmarker**: Создаёт точку пути в космосе. Принимает систему, две строки для журнала Нейросети и координаты XYZ. |

#### [ObjList]

Представляет собой серию приказов, отдаваемых NPC, группе NPC или формированию.

```ini
[ObjList]
nickname = STRING
system = STRING
GotoShip = ENUM, STRING, INT, BOOL, INT
GotoVec = ENUM, INT, INT, INT, INT , BOOL
GotoSpline = ENUM, INT, INT, INT, INT, INT, INT, INT, INT, INT, INT, INT, INT, BOOL
MakeNewFormation = STRING, STRING
Follow = STRING, INT, INT, INT, INT
StayInRange = INT, INT, INT, INT
BreakFormation = ENUM
Avoidance = BOOL
Delay = INT
SetLifetime = STRING, INT
SetPriority = ENUM
Dock = STRING, STRING
Idle = ENUM
```

| Параметр             | Описание                                       |
| -------------------- | ---------------------------------------------- |
| **nickname**         |                                                |
| **system**           |                                                |
| **GotoShip**         | Enum: `GOTO`, `GOTO_CRUISE` и `GOTO_NO_CRUISE` |
| **GotoVec**          | Enum: `GOTO`, `GOTO_CRUISE` и `GOTO_NO_CRUISE` |
| **GotoSpline**       | Enum: `GOTO`, `GOTO_CRUISE` и `GOTO_NO_CRUISE` |
| **MakeNewFormation** |                                                |
| **Follow**           |                                                |
| **StayInRange**      |                                                |
| **BreakFormation**   | Enum: `no_params`                              |
| **Avoidance**        |                                                |
| **Delay**            |                                                |
| **SetLifetime**      |                                                |
| **SetPriority**      | Enum: `NORMAL` и `ALWAYS_EXECUTE`              |
| **Dock**             |                                                |
| **Idle**             | Enum: `no_params`                              |

#### [MsnSolar]

```ini
[MsnSolar]
nickname = STRING
string_id = INT
position = INT, INT, INT
orientation = INT, INT, INT, INT
radius = INT
archetype = STRING
loadout = STRING
system = STRING
base = STRING
faction = STRING
pilot = STRING
costume = STRING
voice = STRING
visit = INT
label = STRING
```

| Параметр    | Описание |
| ----------- | -------- |
| nickname    |          |
| string_id   |          |
| position    |          |
| orientation |          |
| radius      |          |
| archetype   |          |
| loadout     |          |
| system      |          |
| base        |          |
| faction     |          |
| pilot       |          |
| costume     |          |
| voice       |          |
| visit       |          |
| label       |          |

#### [MsnShip]

```ini
[MsnShip]
nickname = STRING
position = INT, INT, INT
rel_pos = INT, INT, INT
orientation = INT, INT, INT, INT
radius = INT
NPC = STRING
random_name = BOOL
jumper = BOOL
arrival_obj = STRING
init_objectives = STRING
cargo = STRING, INT
```

| Параметр        | Описание |
| --------------- | -------- |
| nickname        |          |
| position        |          |
| rel_pos         |          |
| orientation     |          |
| radius          |          |
| NPC             |          |
| random_name     |          |
| jumper          |          |
| arrival_obj     |          |
| init_objectives |          |
| cargo           |          |

#### [MsnLoot]

```ini
[MsnLoot]
nickname = STRING
archetype = STRING
string_id = INT
rel_pos_obj = STRING
rel_pos_offset = INT, INT, INT
velocity = INT, INT, INT
equip_amount = INT
health = INT
Can_Jettison = BOOL
```

| Параметр       | Описание |
| -------------- | -------- |
| nickname       |          |
| archetype      |          |
| string_id      |          |
| rel_pos_obj    |          |
| rel_pos_offset |          |
| velocity       |          |
| equip_amount   |          |
| health         |          |
| Can_Jettison   |          |

#### [MsnFormation]

```ini
[MsnFormation]
nickname = STRING
position = INT, INT, INT
orientation = FLOAT, FLOAT, FLOAT, FLOAT
formation = STRING
ship = STRING ;multiple
```

| Параметр    | Описание |
| ----------- | -------- |
| nickname    |          |
| position    |          |
| orientation |          |
| formation   |          |
| ship        |          |
