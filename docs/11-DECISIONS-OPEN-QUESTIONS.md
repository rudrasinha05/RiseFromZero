# 11 — Decision Register, Open Questions, Versioning & Non-Fabrication Rules

**Updated:** 2026-11-12  
**Purpose:** The owner said all previous design work should survive future handoff (including to AGO). Future contributors must be able to distinguish user-approved facts from engineering suggestions and unanswered questions.

## A. Locked / confirmed in user discussion

| ID | Decision | Where documented |
|---|---|---|
| D-001 | Chosen game name **Rise From Zero** | README |
| D-002 | Main story: two poor childhood friends; garage; racing rise; one betrays and sends other to prison; betrayer builds empire; released protagonist restarts from zero; ultimately challenges and defeats former friend | 01 |
| D-003 | Girlfriend seen from startup/loading, ongoing love interest and guide, coerced by rival and secretly supportive, reactions after races | 01, 02 |
| D-004 | Story long/emotional with short and long cutscenes and performance-based reactions/endings; **no mid-race Q&A** | 01, 02 |
| D-005 | Approximately five connected cities with mountains, valleys, lakes, dam roads, forests, alleys, highways, service roads and shortcuts | 04 |
| D-006 | Geography must serve races/escape; destructible police pursuit breakers and bounty hotspots | 04, 08 |
| D-007 | Physics-led driving with believable high-speed/jump/landing/weight/suspension; immersive cockpit and multiple camera views | 05 |
| D-008 | Manual and automatic shift; **Left Shift gear up, Right Shift gear down by default**; keyboard/gamepad/joystick and freely remappable controls | 06 |
| D-009 | Every component has rank-gated versions, Basic/Advanced/Pro/Ultimate and internal sublevels; multiple engine Pro/Ultimate choices; gearbox and nitrous similarly restricted | 07 |
| D-010 | Deep visual car customization (paint, spoiler, hood, bodykit, rims, tires, brakes, suspension, turbo, exhaust, lights, interior) | 07 |
| D-011 | Garage grows from small to bigger; player chooses whether/when to spend; new cars by rank/price, no automatic Ultimate access | 07 |
| D-012 | Expert racer sets race time/location/scenario, including night/rain; no daytime-only schedule | 03 |
| D-013 | 15 rival ranks, each expert's 5 fixed races, at least 3 wins to advance; boss's defined required challenges must be won | 03 |
| D-014 | Police Heat/Bounty, pursuit breakers, arrested/court/fine/bail/jail; failed race may need replay but campaign does not reset | 08 |
| D-015 | Desired delivery is runnable gameplay/Windows EXE/installer with testing, not just code fragments | 09, 10 |
| D-016 | AGO may be used **later**, but future automation must have verified delivery/QA and cannot be assumed ready now | 09 |

## B. Decisions suggested in conversation, not locked specifications
- **Region working names:** Old City, Metro City, Industrial City, Mountain City, Luxury City.
- **Map area estimate:** 100–250 square km; **installation estimate:** 150–300 GB, maybe >300 at exceptional fidelity. These are *rough predictions*, not feature criteria.
- **Story length estimate:** 40–80 h potential; unmeasured.
- **Technology:** Unreal Engine C++/Blueprints considered, not selected.
- **Development estimates:** 6–12-month demo idea, 1–3-year smaller game idea, AAA studio ~4–7 years; solo can take far longer. Highly uncertain.
- **Car brand aspirational list:** Maserati, Rolls-Royce Ghost, Range Rover/Land Rover, Pagani, Bugatti, Ferrari — licenses/rights not obtained.
- **Starter garage about 1–2 spaces**, but exact default cap/prices/starter car not frozen.
- **Engine builds:** Pro A/B/C; Ultimate A/B/C examples and nitrous numbered sublevels illustrate the requested variation; actual names/stats/prices are yet to be approved.
- **Optional gameplay additions** like wheel force feedback, VR, multiplayer, photo mode, property systems, pedestrian interaction and post-game free roam are **not confirmed**.

## C. Open questions — explicitly do not invent answers

### Story and presentation
- Names, ages, voices, appearance and precise backgrounds of player, childhood rival and girlfriend?
- Which betrayal act causes arrest? In which race? What evidence/motive? How does it affect the girlfriend?
- Exact length of imprisonment and what happens during it; who helps protagonist when released?
- Intro/loading composition and scene line scripts?
- Number/order of scenes, which acts include tutorials, and precise plot twists?
- Which observed achievements/actions select each ending, and what actually happens in them?
- Exact countries/languages/realism tone, soundtrack and animation casting?

### Racing and career
- Is ladder counted 15→1 or 1→15?
- Number of bosses, boss race counts, where boss gates sit and whether extra 5-race slots per expert?
- Does “3 out of 5 wins” mean any three distinct races, or a certain sequence? (Working interpretation: distinct.)
- Precise event types/locations/time windows, prize tables, race class restrictions and chapter assignments?
- Which races have optional police, and are races held at fixed in-game times or via waiting/scheduling?

### Vehicles and world
- Licensed brands vs fictional substitutes, individual models/year, actual physics measurements?
- World setting/region borders, geographic scale, season cycle, weather engine and night visibility targets?
- Can all roads be used for racing, or only nominated courses; what counts as “meaningful access”?
- Economy balancing, part price/grind, compatibility logic, garage inventory capacity and failure conditions?

### Technology, legal and release
- Rendering/physics engine, target Windows versions and hardware, measured FPS target?
- How many cars/tiles, all asset ownership rights, voice-over/localization budgets?
- Save system migrations, cloud account, multiplayer, mods, replay mode, installer strategy?
- How/when AGO is sufficiently QA-verified to manage development tasks?

## D. How to add new requirements without losing old work
1. Read the owner's latest request against this ledger.
2. Add a new ID to decisions with **source date**, precise text summary and approval status.
3. Mark superseded text explicitly; **don't silently overwrite old facts**.
4. Update corresponding doc(s), cross-links and acceptance tests.
5. For story changes, check prior/next beats to prevent broken chronology.
6. For mechanics, update the part/rank/data tables and add a regression test.
7. For estimates, include assumptions and date; never turn them into “promised specs.”
8. Never represent a hypothetical draft as user-approved canon.

## E. Traceability note
These documents reconstruct the **major confirmed decisions** from available project discussion, including pre-transcript context retrieved from prior conversation. **They are not a verbatim archived transcript of every utterance.** If original recordings contain more exact dialogue, numbers or scene decisions, those should be compared and incorporated into the relevant source section with provenance. The goal is preservation without falsely claiming that missing information was specified.
