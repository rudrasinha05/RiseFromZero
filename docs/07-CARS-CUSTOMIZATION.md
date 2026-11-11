# 07 — Car Roster, Part-by-Part Unlocks, Full Customization & Garage

## Player-facing principle
[CONFIRMED] **Full customization ultimately available**, but **not everything at every level**. **Every individual car part** has its **own unlock levels, subtiers, multiple choices, compatibility and earned purchase cost**. Upgrading engine every rank to the absolute best is forbidden by the intended economy; gearboxes and nitrous are equally tiered. At appropriate final career level, all existing compatible customization options become **eligible** to use, but **not automatically owned or free**.

## 1. Part taxonomy (each item needs its own variants and progression)
**Powertrain:** complete engine models/builds, ECU, intake/air filter, exhaust, turbo/supercharger, engine internals, fuel system, intercooler, nitrous system, transmission/gearbox and ratios, clutch, differential, drivetrain swap where physically plausible.  
**Handling:** suspension, springs, dampers, ride height, anti-roll bars, steering, brakes, tires/compounds, wheel/rim sizes and styles, aero parts.  
**Body/exterior:** full body kits, bumpers, side skirts, fenders, spoiler/wings, hood, vents, roof options, mirrors, lights, underglow where appropriate, paint, wrap/livery, stickers/decals, rim colors.  
**Interior:** seats, dashboard trim, wheel style, gauges/instrument skins, cabin color, materials where compatible.  
**Care / garage:** repair, tuning, setup presets, visual preview, inventory, owned part storage, buy/sell/restore where subsequently approved.

These are **catalogue areas** rather than confirmation that literally every mentioned subcomponent ships. Explicit owner examples—**engine, gearbox, nitrous, spoiler, hood, body kit, paint, rims, tires, suspension, brakes, turbo, exhaust, lights, interior**—are mandatory parts of the customization design.

## 2. Universal tier ladder
| Tier | Meaning | Examples of what becomes available | Availability rule |
|---|---|---|---|
| **Basic / Street** | Starting and small affordable upgrades | limited engine tune, first gearbox set, low-power nitrous, simple paint, modest wheel/hood options | Early career |
| **Advanced** | Significant mechanical choices | improved engine and gear parts, more turbo/tires, additional spoiler/paint/body variants | Mid progression by explicit level |
| **Pro** | Several competitive builds, not single “Pro” item | **Pro Engine A / B / C** (concept examples, ~2–3 choices), advanced ratios, stronger nitrous alternatives, serious suspension/aero | High career unlock |
| **Ultimate** | Highest-end selectable builds | **Ultimate Engine A / B / C** (concept examples, ~2–3 choices), top gearbox variants, multiple ultimate nitrous stages, advanced body/visual options, eligible swaps | Late/final career |
 
**Important:** Owner wants **two or three Pro options and two or three Ultimate options**, especially for engines, and “more and more choices” generally. They are *different builds*, not merely skin changes or aliases. Some parts can require *more levels within each of these four broad tiers*: e.g. **Nitrous Basic-I / II; Advanced-I / II; Pro-I / II / III; Ultimate-I / II / III**. These variant names/numbers are **illustrative** until the owner approves counts.

### Example engine tree (data proposal)
- Basic: 1.1 low-output tune, 1.2 mild tune, 1.3 supporting parts, conditional engine eligibility.
- Advanced: 2.1 improved engine, 2.2 alternative torquey build, 2.3 tuning improvement.
- Pro: **P-A balanced**, **P-B acceleration/torque**, **P-C high-rev track** (distinct curves, engine sound, fuel/heat/damage impact as appropriate).
- Ultimate: **U-A straight-line**, **U-B grip/balance**, **U-C peak-racing** (only if compatible, budgeted and earned).
- **Engine swap** possible where car's hardpoints, weight, cooling, driveshaft etc. are realistically compatible. Unrealistic fitment without explanation is rejected by physics rule.

### Example nitrous progression
Nitrous should never jump from “none” to “Ultimate” at the start. Tier and **substage** govern bottle capacity, delivery curve, charge/cooldown, refill and tuning constraints. A small nitrous stage must have materially different acceleration and risk/usage dynamics from Pro or Ultimate. The exact bottle names and levels are **TBD**.

### Gearbox progression
Different transmissions/ratios unlock at different ranks; a gearbox affects shift speed, RPM range, acceleration/top speed, possible manual/clutch behavior and compatibility. **Unlocking the option to use manual shift** is not the same as unlocking an Ultimate transmission.

### Visual progression
- Starting colors/paint vs later metallic/pearl/matte/custom liveries [WORKING tier examples].
- Spoiler, hood, body kit, rims, headlights and interior *each* have separate unlocked designs and potential tier ladders.
- Player chooses combinations among available items; changes can be cosmetics-only or physical. A bigger spoiler isn't automatically “faster”; aerodynamic effect must be actually simulated and described.
- Paint/recolor remains available with reasonable starter options; advanced effects unlock later.

## 3. Car roster and branded vehicles
[CONFIRMED aspiration] Real-looking (potentially branded) car collection spanning starter to hypercar with economic/rank ladder. User specifically referenced **Maserati, Rolls-Royce Ghost, Range Rover/Land Rover, Pagani, Bugatti and Ferrari** as desired roster examples; keep these as targets **subject to actual trademark/model/data licenses**. Do not commit unauthorized logos/model assets or assume those brands have granted permission.

### Roster planning fields
Car ID, brand/model or fictional substitute, approved rights, vehicle category, acquisition requirement, in-game price, mass, dimensions, drivetrain, power/torque, gearing, suspension, wheelbase, tire dimensions, sound set, cockpit/interior assets, mirror/wiper setup, compatible parts, damage limits, handling test and LOD versions.

[TBD] Exact car total, precise make/models/year, starting car, whether some prestige cars are race-ineligible for physics reasons, licensing strategy, online marketplace.

## 4. Garage growth
- [CONFIRMED] Start with a **small garage (approximately 1–2 cars in early concept)**.
- As money and reputation grow, player can **choose** to upgrade parking slots, repair and tuning stations, dedicated workshop bays, cosmetic area and storage.
- [CONFIRMED] **Purchases are voluntary; no forced spending.** The player can keep money and race with existing eligible car if rules allow.
- Garage must remember owned vehicles, build configurations, spare parts, repairs, paint scheme, garage layout/capacity and saved presets.
- [WORKING] The story/visual garage can change with career, reflecting the zero-to-empire arc. Exact upgrade stages and prices TBD.

## 5. Data contract for every selectable part
~~~yaml
part_id: "engine-pro-b"      # example only
category: engine
subcategory: complete_build
tier: Pro
sublevel: "P-B"
first_eligible_rank: "TBD"
price: "TBD"
compatible_car_ids: []
prerequisite_part_ids: []
stat_changes:
  torque_curve: "TBD"
  weight_delta_kg: "TBD"
  cooling_effect: "TBD"
assets: {mesh: "TBD", sound: "TBD", ui_icon: "TBD"}
requires_manual_validation: true
approved_by_owner: false
~~~

## 6. Menu flow
Garage → select owned car → inspect 3D model/interior and stats → choose upgrade category → choose *tier* → compare variants within tier → show unlocked/locked reason, price, compatibility and real performance change → preview visuals/sounds → purchase/equip → save build → test-drive. Never show the entire Ultimate catalog as usable at Level 1.

## 7. Acceptance tests
- Low-level player cannot equip high-tier engine/gearbox/nitrous even with cash cheat; entitlement checked centrally.
- Pro and Ultimate each show multiple **distinct** build variants when unlocked.
- Sublevel/variant flags are independent per part, not shared global “engine is max” switch.
- Purchased compatible parts survive game save/load and vehicle swap.
- Wrong-car parts show understandable fitment error; don't clip through interior or engine bay.
- Upgrades meaningfully affect measured driving where described.
- Both cabin and exterior appearance match saved customizations.
- Money/reputation deducted only once, no duplication exploit.
- Garage slot cap blocks extra acquisition without destroying already-owned cars.
- Highest legitimate level unlocks *eligible choices*, not free ownership; previous low-tier choices remain selectable.
