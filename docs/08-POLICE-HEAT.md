# 08 — Police Pursuits, Heat, Bounty, Pursuit Breakers, Busted & Legal Consequences

## Intent
[CONFIRMED] Police are not decorative traffic. Pursuits, heat, bounty hotspots and the environment alter open-world decisions and race tension. **Being busted has consequences—court/fine/bail/jail where applicable—but must NOT wipe the whole career.**

## 1. Core loop
Driving / reckless acts / race incident → legal attention / heat rise → police detection and response → pursuit across city regions → attempted escape or intentional pursuit breaker → if escaped: return to lower-heat activity, retain applicable bounty/rewards; if busted: event interruption, legal/court/fine/bail or prison consequence → recover → **career rank, garage, acquired cars and previously earned victories persist**.

**Story exception:** The protagonist's original long-term imprisonment due to **friend's betrayal** is a specific main plot event. Ordinary pursuit busts are **repeatable gameplay/legal consequences**; never confuse them with the canonical betrayal/jail story arc or replay the cutscene on every arrest.

## 2. Police Heat
[CONFIRMED] Heat must increase from risk/infractions and affect pursuit intensity; players attempt to lose or reduce it in safe areas. [WORKING] Heat may govern patrol sensitivity, available units, frequency of roadblocks, pursuit tactics and area pressure. **No numerical Heat scale/level threshold has been approved**, so don't treat e.g. 1–5 or 1–10 as canon.

### Heat state ideas (proposed engineering)
- **Calm:** normal patrol/traffic; no chase.
- **Suspicion:** attention, detection or follow.
- **Pursuit:** escalating car units; likely high-speed police.
- **Severe pursuit:** coordinated units, roadblock/backup tactics appropriate to region.
- **Escape / cooldown:** sight lost, hide, reroute, reduce active search; long-term notoriety may persist if designed.
Names, transitions, thresholds and cooldown durations TBD.

## 3. Bounty
[CONFIRMED] Risk-heavy pursuits and hotspots offer **Bounty** rewards/notoriety, which may accompany increased Heat. Track bounty separately from cash, rank and police heat unless an explicit game economy design ties them. [TBD] Bounty spends/unlocks/losses/caps and exact scoring algorithm. Do not silently equate Bounty with normal prize money.

## 4. Pursuit-breaker objects
[CONFIRMED] Triggerable/breakable objects can block a pursuing unit: **billboards, water tanks, construction structures/scaffolding and selected destructible props**. A concrete example is a construction object falling on a **forest service road** after the player passes it and blocking the police car path. Must have:
- marked or discoverable activation/collision trigger and credible damage event;
- collision and realistic broken-material behavior;
- **no implausible collapse of a massive dam or permanent bridge**;
- cops re-evaluate road graph, detour or stop; they do **not** pass through debris;
- visible player feedback (“Pursuit Breaker” success if warranted) and bounty/heat rule if earned;
- cleanup/respawn mechanism for future races and saved games;
- physics/performance budget to prevent impossible memory/CPU costs.

## 5. Regional police variation
- Old City: dense corners and alley detection/escape complexity.
- Metro: high-speed arterials, intersections, possible roadblock logic.
- Industrial: truck routing and service-road detours.
- Mountain/forest/dam: limited alternate routes, ravine and bridge safety, remote chase.
- Luxury area: different road profile and response density.
**[WORKING]** These are role profiles, not confirmed police jurisdiction lore. Police cannot teleport or ignore vehicle dynamics simply to catch a player.

## 6. Busted pipeline
[CONFIRMED] Police can catch the player, with **court process, fines and bail/release**, and in appropriate circumstances **jail**. This is a **penalty scene/state**, not a wipe. Race interrupted by arrest may be **restarted/retried**, while persistent money/garage/car/career progression remains according to save rules.

### Proposed implementation state machine
~~~mermaid
flowchart TD
  A["Driving / racing"] --> B{"Police detect offence?"}
  B -->|No| A
  B -->|Yes| C["Pursuit + heat"]
  C --> D{"Escaped?"}
  D -->|Yes| E["Cooldown / bounty result"]
  D -->|No| F{"Busted?"}
  F -->|No| C
  F -->|Yes| G["Arrest scene"]
  G --> H["Court / fine / bail / short jail consequences"]
  H --> I["Return to open world; career saved"]
  I --> J["Retry interrupted race if necessary"]
~~~

### Legal consequences: preserve narrative nuance
Court and bail need credible in-universe handling rather than claiming exact real-world criminal law, especially because the fictional setting/jurisdiction is TBD. [TBD] Court dates, legal counsel, prison duration, whether player pays on screen, time skip, fine algorithm and how repeated arrests affect character relationships. Do not simulate a harsh real legal system accidentally.

## 7. Integration with race and story
- Expert challenges take place on roads with varying time, traffic and potential police presence.
- Police chase is possible in some race scenarios; exact event involvement is specified per race.
- Win/loss/busted modifies race state and story telemetry, girlfriend/rival expressions and future available attempts.
- Player can use short routes and breakers to escape, but using one should incur the correct damage/heat/bounty effects.
- A busted event must not hand the player Ultimate car parts or skip rank gates.

## 8. QA scenarios
1. Pursuit triggered by defined in-game offense increases Heat; police use physically plausible travel.
2. Escape breaks line of sight with appropriate cooldown; no out-of-nowhere instant recapture.
3. Pursuit breaker blocks pursuing cars, not the just-passed player by an impossible teleport; nav AI handles collision.
4. Police arrested during expert race: race attempt fails/retries per rule; **already-earned wins remain**.
5. Fines/bail applied once only, never double-charged on save/reload.
6. Garage, unlocked engine and car selections persist after legal sequence.
7. Original storyline prison event fires once at correct act, not on ordinary bust.
8. Distinct day/night, wet-road and region traffic actually influence pursuits.
9. Large permanent infrastructure does not collapse from a small car contact.
10. Persistent bounty/Heat values are validated, visible and saved as specified.
