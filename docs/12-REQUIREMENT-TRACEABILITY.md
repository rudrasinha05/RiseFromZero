# 12 — Requirement-by-Requirement Coverage & Source-of-Truth Audit

**Audit date:** 2026-11-12. **Goal:** avoid losing a verbally agreed requirement when work resumes months later or is handed to AGO agents. This is a structured **coverage index**, not a claim of feature implementation.

**Status codes:** C = confirmed user intent preserved; W = working interpretation requiring explicit agreement; T = TBD details open; I = future implementation / not done.

## Narrative, relationship and career experience
| Req ID | Requirement preserved | Canon status | Design files | Build status |
|---|---|---|---|---|
| RFZ-N01 | Title **Rise From Zero** | C | README, 00 | I |
| RFZ-N02 | Two poor childhood friends | C | 01 | I |
| RFZ-N03 | Learn driving/mechanics in the garage | C | 01 | I |
| RFZ-N04 | Friends race and gain reputation together | C | 01 | I |
| RFZ-N05 | One friend betrays protagonist into story imprisonment | C | 01, 02 | I |
| RFZ-N06 | Betrayer becomes racing empire's leader | C | 01 | I |
| RFZ-N07 | Prison release → start again from zero | C | 01 | I |
| RFZ-N08 | Protagonist climbs and defeats former friend/empire | C | 01 | I |
| RFZ-N09 | Girlfriend in intro/loading | C | 01, 02 | I |
| RFZ-N10 | Girlfriend guides/helps, loves protagonist, rival pressures her, she secretly supports comeback | C | 01, 02 | I |
| RFZ-N11 | Rich emotional story, small and large cinematic cutscenes | C | 01, 02 | I |
| RFZ-N12 | End-of-race expressions/reactions depend on player's performance | C | 01, 02 | I |
| RFZ-N13 | Different endings from gameplay/progress/actions | C | 01, 02 | I |
| RFZ-N14 | No during-race Q&A to choose narrative paths | C | 00, 02 | I |
| RFZ-N15 | Precise dialogue/character identities/betrayal method/finale branches yet to be decided | T | 01, 11 | I |

## Race ladder
| Req ID | Requirement preserved | Status | Files | Build |
|---|---|---|---|---|
| RFZ-R01 | Fifteen rival ranks target | C | 03 | I |
| RFZ-R02 | Five fixed races for an expert rank | C | 03 | I |
| RFZ-R03 | At least three of five wins required to advance | C | 03 | I |
| RFZ-R04 | Boss's prescribed challenges all won | C | 03 | I |
| RFZ-R05 | Expert determines race place/time/day/night/weather scenario | C | 03 | I |
| RFZ-R06 | Race result, busted/retry, rewards feed career and story | C | 02, 03, 08 | I |
| RFZ-R07 | Exact rank orientation, rival identities and boss race counts unconfirmed | T | 03, 11 | I |

## World and environment
| Req ID | Requirement preserved | Status | Files | Build |
|---|---|---|---|---|
| RFZ-W01 | Five interconnected city-scale regions | C | 04 | I |
| RFZ-W02 | Old/Metro/Industrial/Mountain/Luxury names are placeholders | W | 04, 11 | I |
| RFZ-W03 | Highways, flyovers, villages and small connecting roads | C | 04 | I |
| RFZ-W04 | Alleys, service roads and hidden shortcuts | C | 04 | I |
| RFZ-W05 | Mountains, valleys, forests and dirt roads | C | 04 | I |
| RFZ-W06 | Lakes, reservoirs, shoreline routes and drivable dam road | C | 04 | I |
| RFZ-W07 | Bridges, tunnels and credible road continuity | C | 04 | I |
| RFZ-W08 | Geography participates in driving, races and chases | C | 00, 04 | I |
| RFZ-W09 | Day/night/weather and traffic vary with time and location | C | 04 | I |
| RFZ-W10 | Rain affects grip and visibility | C | 04, 05 | I |
| RFZ-W11 | Bounty hotspots and bounded pursuit breakers | C | 04, 08 | I |
| RFZ-W12 | Massive permanent dams/bridges should not collapse at random | C | 04, 08 | I |
| RFZ-W13 | 100–250 km² / 150–300 GB discussed only as estimate | W | README, 04, 11 | I |

## Vehicle physics and camera
| Req ID | Requirement preserved | Status | Files | Build |
|---|---|---|---|---|
| RFZ-P01 | Real car-like dynamics, high-speed physical plausibility | C | 05 | I |
| RFZ-P02 | Jumps obey believable gravity/momentum/rotation | C | 05 | I |
| RFZ-P03 | Landings cause suspension compression, shift, skid/damage | C | 05 | I |
| RFZ-P04 | Tires, braking, traction, gears and weather affect handling | C | 05 | I |
| RFZ-P05 | Realistic cockpit view per car; dashboard, instruments, moving wheel | C | 05 | I |
| RFZ-P06 | Rear-view mirrors and wipers during rain | C | 05 | I |
| RFZ-P07 | Hood, bumper, chase and cinematic cameras | C | 05 | I |
| RFZ-P08 | Camera response to road/chassis movement; believable audio | C | 05 | I |
| RFZ-P09 | No claim of perfectly exact real-world physics without measurement | W | 05 | I |

## Controls, cars, customization
| Req ID | Requirement preserved | Status | Files | Build |
|---|---|---|---|---|
| RFZ-C01 | Manual or automatic transmission | C | 06 | I |
| RFZ-C02 | Default **Left Shift up / Right Shift down** | C | 06 | I |
| RFZ-C03 | Keyboard, controller, joystick with connection recognition | C | 06 | I |
| RFZ-C04 | Fully editable bindings for accelerator/brake/handbrake/gears/nitrous/camera/clutch | C | 06 | I |
| RFZ-C05 | Individual saved input profiles | C | 06 | I |
| RFZ-U01 | Part-by-part career unlocks, not everything at level one | C | 07 | I |
| RFZ-U02 | Basic → Advanced → Pro → Ultimate tier families | C | 07 | I |
| RFZ-U03 | Many sublevels within each part/tier | C | 07 | I |
| RFZ-U04 | At least multiple Pro and Ultimate engine alternatives (owner example two or three each) | C | 07 | I |
| RFZ-U05 | Engine, gearbox and nitrous all have their **own** levels/variants | C | 07 | I |
| RFZ-U06 | Paint, spoiler, hood, body kit, rims, tires, suspension, brakes, turbo, exhaust, lights, interior | C | 07 | I |
| RFZ-U07 | Highest earned career tier unlocks compatible choices; money still buys parts | C | 07 | I |
| RFZ-U08 | Owned cars start modest and unlock by rank/cost; desired premium real-brand cars | C | 07 | I |
| RFZ-U09 | Maserati/Rolls-Royce Ghost/Land Rover-Pagani-Bugatti-Ferrari desired subject to rights | C | 07 | I |
| RFZ-G01 | Small garage initially, expandable by choice | C | 07 | I |
| RFZ-G02 | Buying/upgrading not forced; player remains free within rank gates | C | 07 | I |

## Police and release
| Req ID | Requirement preserved | Status | Files | Build |
|---|---|---|---|---|
| RFZ-L01 | Heat and bounty hotspots | C | 08 | I |
| RFZ-L02 | Pursuit breaker examples tanks/billboards/construction | C | 08 | I |
| RFZ-L03 | Police chases react to environment/time/region | C | 08 | I |
| RFZ-L04 | Busted → court/fine/bail or jail, race interrupted | C | 08 | I |
| RFZ-L05 | Career progress **not reset** on normal busted outcome | C | 08 | I |
| RFZ-L06 | Story betrayal prison is separate from normal busted mechanic | C | 01, 08 | I |
| RFZ-D01 | Aim for source code, gameplay, tested Windows EXE/installer | C | 09, 10 | I |
| RFZ-D02 | AGO future handoff with independently verified tasks/results | C | 09, 10 | I |
| RFZ-D03 | “No errors” cannot be guaranteed ahead of tests; require real quality evidence | W | 10 | I |

## Completeness audit procedure
1. At each future session, read the README, **01 story flow**, this matrix and decision log.
2. Identify whether the new owner requirement already has a matching ID. If no, **add a row**, linked docs and acceptance criteria.
3. For uncertain narrative details, keep **TBD** rather than generating fake facts.
4. Any source-code task must cite one or more **RFZ- IDs** from this table.
5. QA reviews each linked acceptance test before a task becomes “done”.
6. Reconcile newly recovered transcripts with these requirements. Correct any miscaptured word/number; record a dated change.
7. Preserve older approved facts unless owner explicitly revises them.

## Integrity note
This register covers the details **available from the current design conversation and recovered earlier decisions**. It does **not** claim a verbatim archive of unseen conversations or an already complete screenplay. The explicit TBD sections prevent loss of unknowns and false certainty.
