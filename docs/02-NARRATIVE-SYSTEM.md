# 02 — Reactive Narrative, Girlfriend, Cutscenes & Endings

## North-star requirement
[CONFIRMED] The story is lengthy, emotional and continuous. **No in-race Q&A or forced choice prompts.** The game must read the player's actual **race performance, progress and behavior** and respond through dialogue, expressions, scenes, rival treatment and alternative endings.

## Narrative event pipeline
1. **Precondition:** a chapter, reputation level, named rank, previous scene or eligible car/race is reached.
2. **Event:** race accepted/scheduled/started/finished, lost, collision, pursuit, arrested, elite rival encountered, garage expansion or story cutscene viewed.
3. **Telemetry captured:** event timestamp, rank, race ID, result, finish position, clean driving, crashes, damage, missed checkpoints, police heat/bounty, caught/escaped, car used, upgrades installed, and perhaps relationship-history flags.
4. **Event rules:** deterministic base conditions check; only approved narrative rules choose branch. Do not use unbounded LLM improvisation as canon.
5. **Scene:** short post-race reaction or milestone cinematic; emotional line/animation tied to the actual event.
6. **Persistent flags:** record scene seen, relevant relationship changes, discoveries, betrayal clues and current story state, so a save/load continues coherently.
7. **Ending resolver:** at final confrontation, derives ending from *approved* performance/actions and story flags.

### Sample technical events (PROPOSED schema, not user-approved scoring)
| Event name | Example data | Story response category |
|---|---|---|
| RaceFinished | raceId, rank, finishPlace, bestLap, collisions | celebratory / disappointed / worried |
| RaceLost | raceId, rivalId, deficitSeconds | supportive / mocking / determined |
| PoliceChaseEscaped | maxHeat, bountyEarned, escapeMethod | relief / caution / rival respect |
| PlayerBusted | raceId, courtCaseId, fine, timePenalty | concern / setback; career retained |
| CarPurchased | modelId, garageSlot | pride / changing status |
| RankAdvanced | rankFrom, rankTo, requiredWinsMet | boss challenge / major scene |
| ClueDiscovered | clueId, source | girlfriend's secret support / betrayal arc |
| FinalRaceResolved | rival, careerFlags, performance | approved ending selection |

**Note:** Performance metrics are design inputs only. The exact dialogue and weights are [TBD].

## Girlfriend — stable character arc
[CONFIRMED] She is in the **intro/loading experience**, present as **love interest and guide**, provides clues, remains in love with the player, is under the former friend's **coercion/pressure**, and secretly supports a return from prison. **Her face, behavior and interactions should change after every race as appropriate to results.**

**Continuity guardrails:**
- She should not simply “turn evil” because the rival holds power.
- The player should not be required to win affection by choosing quiz answers.
- Some meetings should carry anxiety after dangerous pursuits, not just generic “great race!” messages.
- She can be constrained or unable to speak openly while still providing credible clues.
- Exact coercion event, stakes, methods and how the truth is revealed remain **owner-approval-required**.

### Proposed emotion triggers for implementation design
- Win + controlled driving → pride, admiration.
- Win + severe collision or high police heat → happiness mixed with fear.
- Loss after strong effort → encouragement, strategy hint.
- Repeated losses → frustration, concern; no shaming or hard lock.
- Arrest/bust → worry, legal/life consequences.
- Rising rank → hope; antagonist's pressure may increase.
- Story reveal → surprise, relief, grief, protective behavior.

*These reactions illustrate a system; they are not fixed lines of script.*

## Cutscene rules
- **Long cinematic scenes** anchor major story turns: childhood partnership, betrayal, court/prison, release, truth reveal, major boss and finale.
- **Short contextual scenes** reinforce continuity: race invitations, rival taunts, finish reactions, girlfriend meetings, police close calls, garage upgrades and unlocked city.
- **In-world delivery** when suitable: phone/radio dialogue, garage interaction or roadside meeting without requiring a big cutscene every few minutes. [WORKING proposal]
- Skippability, subtitles, localized languages, controller prompts, checkpoint resume and accessibility must be engineered. [TBD UX decisions]

## Branching without Q&A
Player progress determines *when* some scenes can occur, but not arbitrary plot reversal:
- Pre-betrayal: protagonist and friend are together.
- Betrayal: protagonist ends up imprisoned.
- Prison period: antagonist builds empire.
- Comeback: protagonist truly rebuilds from low resources.
- Finale: confronting the former friend is mandatory to main arc.
- Multiple **end-scene variations** should consider performance/choices demonstrated by gameplay. Owner has NOT selected exact endings. Preserve the core outline unless expressly changed.

## Narrative acceptance tests
- Every meaningful race completion has an event and eligible reaction; fallback dialogue never contradicts current act.
- Returning from ordinary police bust never triggers main story's prison betrayal again.
- Saved game reload preserves relationship flags, discoveries and seen scenes.
- Player who loses races still experiences coherent support and can retry progression.
- No quiz UI interrupts steering/driving during a race.
- Replays of finished races don't repeatedly award one-time story milestones.
- Finale cannot start before required rivals/boss gates are satisfied.

## Writer's next tasks
Create character bibles with approved names; storyboard each act; define numbered chronological scenes and secret clue graph; design finite ending branch conditions; add exact localizations/voice scripts; build a versioned dialogue table. These are **future deliverables**, not already written canon.
