# 03 — Career, Rival Ranks, Experts, Bosses & Race Scheduling

## 1. Structure
[CONFIRMED in prior discussion] Design includes **15 rival ranks**, arranged as a visible ladder. At each rank, its designated **expert has five fixed races**. Player must win **at least three of those five** to satisfy the expert progression threshold; bosses require successful completion of **their specified challenge races**, including **all** required boss races. Boss race count and positioning within the 15-rank ladder are not yet fixed. The career must display remaining tasks transparently.

**Critical ambiguity:** “15 rival ranks” is agreed, but the actual order number (15→1 or 1→15), number of experts per rank and timing of boss gates should be formally approved before hard-coding. The 15 rows below are *slots*, not made-up opponents.

| Slot | Expert identity | Five-race playlist | Wins required | Boss condition |
|---|---|---|---|---|
| 01 | TBD | TBD × 5 | ≥3 | TBD |
| 02 | TBD | TBD × 5 | ≥3 | TBD |
| 03 | TBD | TBD × 5 | ≥3 | TBD |
| 04 | TBD | TBD × 5 | ≥3 | TBD |
| 05 | TBD | TBD × 5 | ≥3 | TBD |
| 06 | TBD | TBD × 5 | ≥3 | TBD |
| 07 | TBD | TBD × 5 | ≥3 | TBD |
| 08 | TBD | TBD × 5 | ≥3 | TBD |
| 09 | TBD | TBD × 5 | ≥3 | TBD |
| 10 | TBD | TBD × 5 | ≥3 | TBD |
| 11 | TBD | TBD × 5 | ≥3 | TBD |
| 12 | TBD | TBD × 5 | ≥3 | TBD |
| 13 | TBD | TBD × 5 | ≥3 | TBD |
| 14 | TBD | TBD × 5 | ≥3 | TBD |
| 15 | TBD | TBD × 5 | ≥3 | TBD |

**Not automatic:** 15 × 5 = 75 *expert race slots* planned under the stated framework; boss races may be additional. This is a content requirement estimate, not a tested implementation or proof of a specific career length.

## 2. One challenge from invitation to completion
1. **Expert announces** the course, venue, race type, required vehicle class if applicable, and **day/night/time** (the expert decides); condition can include rain, evening visibility, industrial traffic, mountain roads.
2. **Player prepares:** choose an owned/unlocked eligible car, legal within-rank upgrades and setups, manual/automatic, camera and remapped input controls.
3. **Travel physically** through the city/region to meet the challenge; choose available routes, shortcuts or mapped highway.
4. **Race begins at its designed local time/weather**. AI competitors, traffic, checkpoints, police possibility, road surface and race camera react to the event setting.
5. **Record the attempt:** win/loss, clean vs risky, collisions, police heat, bust, cash/reputation outcome and story telemetry.
6. **Update progress:** expert-race win flags, 3-of-5 eligibility, boss challenges; display precise unmet requirements.
7. **Run reaction scene:** girlfriend/rival/milestone lines depend on actual results, not a questionnaire.
8. **Next choice:** replay failed races, take next fixed challenge, repair/upgrade existing cars, save for garage expansion or pursue already unlocked events.

## 3. Challenges and race formats
[WORKING types/examples] sprint point-to-point, circuit, highway run, drag, narrow mountain switchback, timed checkpoint, night urban, wet forest, dam route, industrial multi-lap. **Formats listed here are representative**, not an approved count or a requirement that every expert use each format. Bosses need differentiated techniques and race conditions rather than only larger horsepower.

### Proposed race record shape
~~~yaml
race_id: rank-01-race-01
rival_rank_slot: 1
expert_id: "TBD"
race_name: "TBD"
race_type: "TBD"
world_region: "TBD"
route_id: "TBD"
start_local_time: "TBD"
time_of_day: "TBD"       # chosen by expert
weather_profile: "TBD"
traffic_profile: "TBD"
police_rules: "TBD"
eligible_vehicle_classes: []
min_car_performance: null
checkpoint_sequence: []
rewards: {money: "TBD", reputation: "TBD", bounty: "TBD"}
unlock_conditions: []
story_events: []
provenance: "design placeholder, not approved content"
~~~

## 4. Results and progression
- A previously recorded win must not disappear if a player changes car or reloads a save.
- A loss is not automatically full career reset; retry according to defined race entry rules.
- A **bust** triggers its lawful consequence and can mark the current attempt failed/invalid; **previous career wins persist**.
- Optional races/free-roam events may provide cash/reputation but cannot bypass mandatory expert/boss progression.
- Purchased parts **do not** unlock ranked entry before career conditions.
- Avoid granting an expert win twice through repeated completion.
- Every boss race must have a visible requirement and consistent result handling.

## 5. Opponent AI
**[WORKING engineering design]** Expert style profiles (aggressive/blocking, clean-line, late braking, wet-road precision), car class, reaction to traffic, mistakes proportional to driving skill, line choice and damage/traction should differ. Time-of-day must not merely recolor the road; headlights, visibility, traffic density/types and possible police tactics matter. Avoid magical catch-up that breaks the physical realism rule; difficulty should come from meaningful driving skill/configuration.

## 6. Progression tied to parts and story
Each rank advances available **vehicle models, customization subtiers, garage opportunities and narrative chapters** according to separate unlock tables. These must be data-driven, allowing any engine, nitrous, spoiler or gearbox variant to have explicit:
- first eligible career stage;
- cost and reputation prerequisite;
- fitment/class restriction;
- objective performance change;
- model/asset ID;
- shop availability;
- test case.

## 7. Boss rule clarification
[CONFIRMED] Boss's **required challenge races must be won**, as agreed, not skipped merely because expert win quota reached. [TBD] Boss count and exact required races; whether all five of an expert's races remain replayable after three wins; exact chapter-to-rank map; rank naming and reward economy.

## 8. Career UX acceptance
- Show e.g. “2 of 3 required expert wins; 2/5 completed race wins” with accurate underlying data.
- Distinguish **expert races** and **boss races**, with boss completion gate.
- Show actual local event time/conditions and next available attempt, not randomly reschedule a challenge.
- After repeat, recovery from crash/bust or resume, progression stays internally consistent.
- No monetization purchase skips ranks.
