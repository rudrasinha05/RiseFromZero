# 00 — Vision, Product Rules, Scope & Fidelity

**Revision:** 2026-11-12 · **Stage:** requirements capture · **Legend:** [CONFIRMED] stated/accepted by owner; [WORKING] previous assistant framing or practical interpretation awaiting approval; [TBD] explicitly undecided.

## 1. The promise
[CONFIRMED] **Rise From Zero** is a story-first, realistic, massive connected-world racing game. The drama is about a childhood friendship broken by betrayal; the gameplay is about rebuilding a career from nothing through driving, reputation, skill, car ownership and rivalry. At each point, racing must feel integrated with the world, story, driving realism, opponents and police.

### Non-negotiable design rules
- [CONFIRMED] **Do not skip the heartbreak/recovery arc.** Two poor friends learn cars together in a garage, rise through races; one betrays the other into prison; the betrayer builds an empire; the player eventually returns and challenges it.
- [CONFIRMED] **The girlfriend matters throughout:** appears from introductory/loading presentation, guides the player, remains emotionally attached to the player despite pressure from the antagonist, secretly helps the comeback; has contextual expressions/reactions after races.
- [CONFIRMED] **No mid-race quiz or dialogue/Q&A interruption.** Reactions and ending branches use game performance, progress and observed actions, not pop-up moral-choice questionnaires.
- [CONFIRMED] **Realism means believable physical consequences**, not just photorealistic graphics. Jump height, flight trajectory, orientation, landing, tire grip, collision, braking, wet roads, suspension and camera feedback must be explainable by physics. No arbitrary “car snaps straight” landings.
- [CONFIRMED] **Accessible but deep:** manual/automatic transmission; configurable keyboard/gamepad/joystick; individual camera modes; responsive controls with player-defined remapping.
- [CONFIRMED] **Structured progression:** lower-rank parts and cars first; higher levels open subtiers and alternate versions across **every** vehicle component. No universal day-one high-end engine, gearbox or nitrous.
- [CONFIRMED] **World features are playable**, not painted backdrops: dams, lakes, forests, hills, bridges, alleyways and shortcuts contain meaningful driveable racing or chase routes where terrain permits.
- [CONFIRMED] **Race conditions belong to the challenger/expert:** some day, some night, some rain, varying city/terrain; not all races at noon. The player chooses eligible car and permissible setup.
- [CONFIRMED] **Garage growth is voluntary**: earn, purchase cars, upgrade capacity/tools, keep money instead if desired. Progression gates still apply.
- [CONFIRMED] **Busted is consequential but not a campaign reset**: courtroom/fine/bail or jail sequence, keep the earned career; replay the failed/abandoned race as needed.
- [CONFIRMED] **Long and short cutscenes** should make a lengthy, emotional storyline legible.
- [CONFIRMED] Final desired deliverable is an actual playable Windows build / installer / EXE, tested end-to-end; code text alone is not “the game.”

## 2. Design hierarchy: avoid contradictions
1. **Owner's explicit requirement** outranks any assistant suggestion.
2. **Approved story/career rules** outrank convenience edits by programmers or AI agents.
3. **Physics plausibility and performance** must be tested; where real physics conflicts with cinematic intent, document the design compromise before coding.
4. **Fun, usability and accessibility** can be improved without secretly breaking the user's progression/race-setting rules.
5. [TBD] On any unresolved matter, create an issue/decision entry rather than silently canonizing a guess.

## 3. Player agency: important interpretation
Freedom **inside the rules**, not permission to bypass them.
- Player can change car among already unlocked/owned/eligible vehicles, camera, automatic/manual gearbox, permitted tune, paint, bought parts, input device, bindings and garage expenditure.
- Player **cannot** buy ultimate parts before earned unlocks, skip mandatory boss challenges, or reschedule an expert's fixed race as a default.
- Only eligible/compatible engine swaps and car-part combinations may be equipped.
- Finishing a rank is determined by race rules, not by expensive upgrades alone.

## 4. Scale and realism
[WORKING estimates, explicitly NOT hard specs] Five connected city regions; perhaps 100–250 square km in mature product, perhaps 150–300 GB for a high-detail release, perhaps a long 40–80-hour story career; development at AAA ambition could take a 4–7 year experienced-studio effort and much longer for a tiny team. **These figures are conversation-level estimates**, not locked size budgets, contractual timelines, or current evidence. The product may need optimization, content streaming and asset reuse rather than huge file size.

### World and audiovisual bar
- Distinct city skyline, road patterns, street furniture, local sound, weather, day/night lighting and traffic profiles; see World document.
- Every actual car interior visible at cockpit quality: instruments reflect telemetry; mirrors, steering and wipers behave plausibly.
- Physical interactions and damage should match collision energy/impact, not fixed animation-only outcomes.
- [TBD] Device minimum/recommended specifications, performance target (FPS/resolution), vehicle count, exact map area, controller hardware matrix, engine choice, licensing, monetization and release date.

## 5. Feature ownership and implementation discipline
Every feature needs: **requirement → technical plan → dependency/assets → code/data → in-engine proof → automated checks where possible → playable manual QA → release artifact**. AGO agents can follow the same handoff, but no agent may claim “done” merely for writing files or generating screenshots. The owner is the final authority on changing game canon or large resource decisions.

## 6. What is deliberately not frozen
No confirmed protagonist/girlfriend/villain names, scene-by-scene dialogue, complete betrayal mechanism, exact chronology of every romance beat, number of boss races, car model counts, real-world map city coordinates, official music, licensing contracts, rendering engine or release timeline. Files that demonstrate examples **must identify those examples as proposals**. Record future owner decisions in 11-DECISIONS-OPEN-QUESTIONS.md.

## 7. Navigation
Story: 01 + 02; rival career: 03; geography: 04; driving: 05; controls: 06; cars: 07; law system: 08; future tech/AGO: 09; milestones/testing: 10; change ledger: 11.
