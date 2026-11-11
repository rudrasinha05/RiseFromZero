# 10 — Build Milestones, QA, Definition of Done & Windows Delivery

## Principle
Keep the final five-city AAA vision, but **validate each mechanical and narrative subsystem in stages**. A prototype does not reduce the eventual ambition; it lets us find bad physics, camera discomfort, expensive rendering and brittle progression before building hundreds of roads and cars. No fixed delivery date is guaranteed.

## Stage 0 — Design lock (current phase)
**Inputs:** this README, 00–11 design docs, explicit decision log, future story scene grid and car/part/rank tables.  
**Exit:** owner-approved requirements with tagged unknowns, a sequence of priorities, selected game engine, starter vertical-slice scene and suitable target hardware profile.  
**Current stage:** documents being saved; detailed gameplay implementation and 3D content **not yet created**.

## Stage 1 — Driving vertical slice / gameplay proof
**Target demo (proposal):** one small traversable road district; one physically modeled car with cockpit + chase + hood + bumper; acceleration, braking, manual/automatic gears, Left/Right Shift, remappable controls, realistic jump/landing; day/night, rain and surface-grip test; one basic race; simple garage view; simple police pursuit/bust.  
**Exit evidence:** launched Windows debug build and recording of actual gameplay; suspension and braking telemetry; controller/keymapping and save/load pass.

### Required tests
- A fresh install launches and drives with keyboard without editor running.
- The cockpit instruments track real vehicle state.
- Wheel/suspension and camera react plausibly to bumps, ramps and landings.
- Normal/wet surfaces change grip, and night racing is readable.
- Manual Left Shift up / Right Shift down works, and changing bindings works.
- A race finishes, rewards exactly once, saves and reloads.
- Police bust gives a penalty and resumes without resetting career.

## Stage 2 — Core career systems
**Build:** expert race definitions and rank ladder, 5 fixed expert races, 3 win threshold, boss gate tests; time/weather event control; full garage economy skeleton, cars and per-part sublevel locks, car fitment. Short reactions/cutscene trigger prototype.  
**Exit:** a small end-to-end career chain: complete → reaction → spend/upgrade → more difficult race → boss unlock, and persistent saved progress.

**Quality gates:** no rank skipping; no free Ultimate tiers; losing/busted doesn't delete legitimate wins; expert controls challenge schedule; HUD accurately shows all requirements.

## Stage 3 — Narrative and regional content expansion
**Build:** complete approved screenplay, key long cutscenes, intro girlfriend, betrayal/prison and post-release arcs, full story flags, finale/ending resolver; connected roads across five city regions; richer traffic and landscape landmarks; region-specific police pursuit breakers; a growing licensed/fictional vehicle roster.  
**Exit:** full main story walk-through with continuity across scenes, real geography traversal, case-by-case race, cinematic and character reaction review.

## Stage 4 — Production content / polish
**Build:** performance budgets, unique interiors, audio, variants of every planned tier, debris and heat behaviors, large-map streaming, weather fidelity, animation, AI diversity, UI, gameplay difficulty balance and accessibility.  
**Exit:** stable feature/content complete beta, no showstopping regressions on target hardware.

## Stage 5 — Release packaging / PC installer
**Build:** signed Windows EXE if feasible, full self-contained distribution/installer, assets and user settings, crash logs, save migration, versioned release, clean-machine smoke test.  
**Exit:** install → launch → start/continue campaign → race → customize car → escape/get busted → save → quit → reload works on supported machines. No success claim without tested files.

## Trackable work categories
- **GDD / screenplay:** emotional story, exact script, rivals, ending branches.
- **Physics and vehicles:** cars, real-world units, camera and controls.
- **World design:** five connected regions, traversal, time/weather, roads and surface metadata.
- **Gameplay systems:** races, progression, economy, customization, garage, police.
- **Presentation:** cockpit art, 3D visuals, UI, sound, cutscenes, expressions.
- **Technical delivery:** code standards, source control, asset pipeline, QA, performance and install.

## Acceptance matrix
| Test ID | Scenario | Must pass |
|---|---|---|
| NAR-01 | Fresh player watches intro | Girlfriend appears in intro/loading as intended; no contradictory lore |
| NAR-02 | Protagonist betrayal | Friend causes story prison event at approved beat |
| NAR-03 | Post-release | Player restarts at low status and limited garage |
| NAR-04 | Win/risky/loss | Contextual story reactions differ based on actual telemetry |
| NAR-05 | Gameplay branch | No in-race Q&A interrupts steering |
| NAR-06 | Final boss | Only reachable after mandatory gates; endings depend on approved behavior |
| CAR-01 | Car launch/jump | Momentum and angular motion physically plausible |
| CAR-02 | Hard landing | Suspension contact forces and skid/damage plausible |
| CAR-03 | Rain | Wet grip and braking differ from dry |
| CAM-01 | Cockpit per car | Distinct interior, working speed/RPM/gear/wheel; wipers and mirrors |
| CAM-02 | Multiple views | Hood, bumper, chase, cinematic functioning appropriately |
| CTL-01 | Keyboard manual | Left Shift up, Right Shift down by default |
| CTL-02 | Rebind | Every assigned gameplay button editable and saved |
| CTL-03 | Controller | Hotplug and remapped analog/joystick functions |
| CUS-01 | Engine | Low/Advanced/Pro/Ultimate with multiple distinct Pro/Ultimate builds |
| CUS-02 | Nitrous / gearbox | Own individual sublevels, not fully unlocked initially |
| CUS-03 | Visual catalog | Paint, spoiler, hood, kits, lights, rims, tires, interiors and variants |
| CUS-04 | Fitment | Wrong vehicle compatibility properly blocked |
| GAR-01 | Expansion | Optional purchases; owned vehicles and builds persist |
| RACE-01 | Five-race ladder | Five defined expert races, min-three-win gate |
| RACE-02 | Boss | All required boss challenge wins enforced |
| RACE-03 | Time | Expert-assigned local race time/weather honored |
| MAP-01 | Cross-region | Roads/shortcuts continuous, no dead decorative geography |
| MAP-02 | Dam/forest/lake | Real driveable routes that affect racing/chases |
| POL-01 | Heat/bounty | Risks and rewards track correctly |
| POL-02 | Breaker | Selected objects block cop route with meaningful collision |
| POL-03 | Busted | Court/fine/bail/jail where set; career remains |
| SAVE-01 | Reload | Cash, cars, race wins, clues, controls and heat consistent |
| PERF-01 | Map streaming | Stable FPS/memory under defined hardware budget (TBD) |
| REL-01 | Installer | Fresh Windows machine successfully installs and runs |

**Metrics TBD:** minimum FPS, quality presets, target GPU, max allowable crash rate, maximum save time, exact physics tolerance and asset counts.

## Evidence format for every completed task
- Requirement/test IDs implemented;
- source commit SHA and content changelog;
- screenshot/video only as supporting evidence, **not a substitute for actual running code**;
- build/launch instructions and runtime logs;
- automated test result and manual QA reproduction;
- known defects and performance notes;
- proof of compatibility with current approved design version.

## Scheduling reality
Early design conversation gave **6–12 months as a rough demo idea, 1–3 years as a smaller substantial game, ~4–7 years for a well-resourced AAA studio; solo far longer**. These are **very uncertain estimates**, not deadlines. Never market an untested game as complete, and do not promise a bug-free release before verification.
