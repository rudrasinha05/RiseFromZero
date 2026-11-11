# 09 — Technical Architecture, Content Data & Future AGO Implementation Handoff

## 1. What exists vs what is planned
As of **12 Nov 2026**, this repository is a **design/requirements repository**. Documentation **does not mean a running game, source code, 3D assets or a Windows installer exists**. Full AAA-scale delivery is a multi-disciplinary effort. A future **AGO (Artificial General Organization)** agent organization could manage and implement well-specified tasks, but current AGO autonomy is **not assumed**. Owner explicitly wants the docs detailed enough to avoid retelling every design decision later.

**Possible engine:** Unreal Engine with C++/Blueprints is a **candidate** because of high-fidelity 3D/physics/Windows packaging. It was previously discussed, **not selected as a binding decision**. Another engine should only be selected after prototype comparison and documented owner approval.

## 2. Suggested runtime modules (proposal)
| Module | Responsibilities | Key interfaces |
|---|---|---|
| VehicleSimulation | physics state, suspension, tire forces, engine/transmission/nitrous | VehicleSpec + ControlInput → VehicleTelemetry |
| InputProfiles | keyboard/gamepad/joystick, key capture, remap and persistence | DeviceId + Bindings → ControlInput |
| CameraManager | cockpit/hood/bumper/chase/cinematic; per-car rig and stabilization | ViewMode + VehicleTelemetry → CameraPose |
| WorldStreaming | terrain/road sectors/landmarks, LOD, day-night, weather, surfaces | WorldRegion + EnvironmentState |
| TrafficAI | normal cars, road rules and event-aware routing | RoadGraph + TrafficProfile |
| RaceManager | scheduled expert challenge, checkpoint rules, timer, scoring | RaceDefinition + Player/RivalResults |
| RivalCareer | 15 slots, five-race sets, 3-win quota, boss gates | CareerState + RaceResult |
| PoliceAI | heat/bounty, detection/pursuit, pursuit breakers, bust | PoliceState + WorldEvents |
| GarageEconomy | cars, owned parts, prices, buy/equip, fitment, garages | GarageState + Catalog + Unlocks |
| CutsceneNarrative | timeline, story flags, reactions/branches and endings | NarrativeState + TelemetryEvent |
| SaveGame | atomic versioned serialization/checkpoints | All persistent states |
| UI/HUD | maps, career, garage, settings, race overlays, dialogue | Above systems → Player UX |
| Audio/Visuals | engine/tires/weather/collisions/music/cinematic | Vehicle/World/Narrative signals |
| BuildRelease | reproducible Windows EXE and installer, packaging QA | Tested game build/artifacts |

## 3. Data-driven content, not hard-coded one-offs
Use human-reviewable source-of-truth data (JSON/YAML/engine assets, depending on engine):
- **WorldRegion**: ID, routes, road surface, terrain/city, weather/time profiles, pursuit hotspots.
- **VehicleSpec**: chassis/engine/tires/interior/rights/variants, no “one physics value fits all.”
- **PartSpec**: distinct tier, sublevel, career unlock, price, compatibility and measured behavior.
- **RaceDefinition**: rank, expert, race format, 5-race playlist, time/place/weather, course, rivals, rewards, cinematic triggers.
- **RivalDefinition**: 15 slots, expert identity, driving style and order.
- **BossDefinition**: explicitly required races; progression conditions.
- **StoryScene/Dialogue**: act/order, prerequisites, skip policy, reaction triggers, branching flags, localization and assigned VO.
- **PoliceRules**: region sensitivity, heat and bounty thresholds, legal sequence.
- **GarageDefinition**: level, parking capacity, workshop services and price.
- **InputProfile**: per-device bindings, axes, deadzone and user overrides.
- **GameSave**: version, chronology, cars, cash, ranks, race history, heat, story flags, GUI options.

## 4. Example save shape (PROPOSED illustrative schema)
~~~json
{
  "saveVersion": 1,
  "story": {
    "actId": "ACT_04",
    "completedSceneIds": [],
    "relationshipFlags": {},
    "clueFlags": {},
    "endingFlags": {}
  },
  "career": {
    "currentRankSlot": "TBD",
    "expertRaceWinsByRank": {},
    "completedBossRaceIds": [],
    "raceHistory": []
  },
  "garage": {
    "garageId": "starter",
    "capacity": 2,
    "ownedCarIds": [],
    "installedPartsByCar": {},
    "customPaintByCar": {}
  },
  "economy": {"cash": 0, "reputation": 0, "bounty": 0},
  "police": {"heat": 0, "legalStatus": "clear"},
  "controls": {"activeDevice": "keyboard", "bindingsByDevice": {}},
  "world": {"regionId": "TBD", "localTime": "TBD", "weather": "TBD"}
}
~~~
**Warning:** Example values/capacity are placeholders; serialization details and version migration policy require engineering review. Do not turn them into arbitrary real defaults.

## 5. Environment + physics technical contracts
- Common coordinate system and physics timestep; clear fixed/semi-fixed simulation policy.
- Mass, inertia, collision materials, tires and wetness follow consistent physical units.
- Surface-type metadata accessible to wheel physics and AI routes.
- Time-of-day and weather drive visibility, NPC traffic and race scheduling, not solely shaders.
- Streaming sectors have persistent IDs; destructibles and their reset state are saved/reconciled.
- Per-car cockpit assets, instruments, mirrors and animation graph use vehicle telemetry.
- All vehicle tuning variants connect to actual simulation parameters and test telemetry.
- Multi-system events use stable IDs and idempotent rewards; race result and legal penalty won't duplicate on save/load.

## 6. Project folder proposal (do not create code scaffolding without a technical decision)
~~~text
RiseFromZero/
  README.md
  docs/                     # this design bible
  design-data/              # approved races, rank charts, cars, parts, script beats
  game/                     # chosen engine project (future)
  tools/                    # import, validation and build tooling (future)
  tests/                    # unit, physics and end-to-end tests (future)
  builds/                   # do NOT commit giant binaries to Git; artifact release storage
~~~
**No 3D game source code yet.** This description is a plan, not proof that folders/assets exist.

## 7. AGO delegation contract
Before giving an AGO agent a task, include:
1. **Requirement IDs and exact docs links** with [CONFIRMED]/[TBD] distinctions.
2. **One bounded deliverable**, module files, interfaces, test criteria and dependency list.
3. **Frozen acceptance criteria**; avoid widening scope mid-implementation.
4. **Asset rights** checks and no paid infrastructure without approved budget.
5. **Evidence expected:** commit, source diff, build logs, automated test outputs and actual recorded in-engine gameplay demonstration where practical.
6. **Independent QA:** reviewer must verify feature against docs; agent self-report is insufficient.
7. **End-user artifact** if release task: playable Windows package built, launched and tested.

### Suggested AI-agent roles (only future proposal)
Game Director / Narrative Designer; Physics Programmer; Gameplay Systems Engineer; World Artist/Level Designer; Vehicle Artist; AI Programmer; UI/UX Designer; Sound/Cinematics; QA/Automation Engineer; Build/Release Engineer. No claim that existing AGO instances currently perform these roles reliably.

## 8. Minimum reproducible pipeline
Requirements/issue → design acceptance → data/schema → source implementation → static checks → tests → engine editor launch → automated or manual controlled drive test → package dev EXE → fresh-machine test → upload build artifact + release notes → owner review → merge.

**Do not promise “without any error” before actual verification.** Record reproducible bugs, crashes, FPS limitations and workarounds.

## 9. Legal/asset handling
Branded real-world cars are aspirational; logos, exact model exteriors, licensed sounds and official music need legal clearance or lawful fictional alternatives. Never scrape and ship assets simply because models appear online. Ensure art/audio source attribution and license metadata per asset.

## 10. Technology decisions still open
Engine choice, supported Windows versions/GPU baseline, physics library, steering-wheel support, user account/cloud save, multiplayer, localization languages, custom vehicle formats, map generator/middleware, technical art pipeline, installer technology, CI cost/budget, version control/LFS and backlog tool. No approved paid purchase should be inferred from this document.
