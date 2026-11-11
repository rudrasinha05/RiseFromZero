# 04 — Five-City Connected Open World: Geography, Roads & Environment

## Vision
[CONFIRMED] Large and **believable** connected 3D racing world at a **five-city** scale. Roads do not end at a pretty landscape: lakes, dams, mountains, forests, bridges, alleys, rural settlements and valleys must be relevant to gameplay. Players should feel they are driving on credible infrastructure with plausible road layout, gradients, surface types and terrain scale.

## Proposed connected regions
[WORKING NAMES from earlier brainstorming, NOT final official city names]
1. **Old City** — compact older neighborhoods, markets, tight streets/alleys, dense intersections and shortcuts; rich in technical low-speed driving and police evasions.
2. **Metro City** — high-rise center, ring road, flyovers, interchanges, heavy rush-hour traffic, fast arterial roads; flexible circuit and sprint opportunities.
3. **Industrial City** — factories, warehouses, trucking corridors, container yards, service roads, parking areas, construction-site pursuit breakers; daytime industry and night freight traffic.
4. **Mountain City** — elevation change, switchbacks, valley roads, bridges, forest-edge tracks, cliffside drivable routes, dams and lake perimeter roads; rain/visibility/landing consequences important.
5. **Luxury City** — premium district, wide boulevard, scenic approaches, high-performance racing vibe and visually different car culture; access to expensive car market should follow career rules.

No geographic coordinates, layouts, population, exact distance, country, city boundaries, proportions or highway plans were confirmed. Treat five places as flexible zones connected by physically sensible roads. A map **shouldn't be assembled from isolated decorative icons**.

## Connectivity / navigation
- Intercity highways and alternate routes: highways, old country roads, village connectors, forest roads and limited-access service roads as appropriate.
- City interiors: main roads, alleys, underground/overhead connectors *where realistic*, backstreets, freight access, bridge approaches, parking spaces.
- Terrain system: mountains/valleys, rivers, **lakes and reservoirs**, dams, forests and meadows, slopes, rural settlements.
- **Dams:** credible drivable dam crest only where plausible; service roads, approach roads and adjacent tunnels/bridges may create race and chase choices. Avoid physically impossible roadway geometry.
- **Lakes:** shoreline runs, causeways, bridges, viewpoints, water hazards and escape routes.
- **Forests:** dirt trails, narrow bridges, limited sight distance, lower grip, branching pursuit escape points.
- **Hidden shortcuts:** must have plausible entrance/exit, vehicle-width clearance, visibility and speed risk; never teleport the player.
- **Pursuit hotspots:** layouts where police heat/bounty risk/reward and destructible trigger points offer unique strategies.
- All drivable connections need road-width, collision, guardrail, lighting, surface material, AI navigation graph and streaming boundaries.

## A map's functionality checklist
For every **named region or landmark**, world artists should document at least:
- unique landscape purpose and memorable visual silhouette;
- road/path types, entry/exit and intercity continuity;
- one or more race paths **or** free-roam drive/police usage;
- appropriate weather/driving impact;
- traffic profile and law-enforcement approach;
- one or more plausible shortcuts or points of risk, where appropriate;
- escape / pursuit-breaker options if terrain allows;
- LOD/streaming requirements and performance budget;
- QA drive-through at day and night, wet and dry.

## Environment is systemic
### Time of day
[CONFIRMED] Day, dusk, night and conditions vary between races. Certain experts deliberately pick time/location; no forced “all daytime.” Headlight reach, reflections, city illumination, readability of road markings, signal behavior and varied traffic should be credible.

### Weather
[CONFIRMED] Rain changes traction and stopping distance, reduces visibility, demands wipers in cockpit; also impacts spray, reflections, puddles if simulated. Avoid identical grip on dry and wet roads. [WORKING] Road-surface wetness system and event weather profiles should be data-driven.

### Traffic
[CONFIRMED] Traffic varies according to region, time, race scenario. Higher freight/truck presence is credible near industrial areas; dense commuting near central city; variable night flows. AI cars must obey geometry and respond to pursuit events. Exact pedestrian/NPC density TBD.

### Wildlife, props and damage
[TBD] Detailed animal/pedestrian content, non-road driving permissions and emergency response. Do not imply wholesale world destruction just because a billboard can fall.

## Police pursuit breakers
[CONFIRMED] **Billboards, water tanks, construction materials/scaffolding and selected breakable objects** can block pursuers when triggered. **Major permanent infrastructure** (dam wall, all bridges, city buildings) should not collapse at whim. Destruction must be bounded, intentional, physically plausible, show reliable collision/navmesh changes and reset safely for repeat gameplay.

### Signature illustrative route — not a locked race
Mountain road chase → **drivable dam roadway** → choice between highway and **forest service road** → triggerable construction structure blocks police approach → heat/bounty response → try to escape to lower-heat area. This route is an example of how map systems should interlock, not a finalized mission.

## Map implementation strategy (proposal)
- Start with an **end-to-end connected sample district** with road mesh, one credible car, forest/dam subregion, weather change, pursuit hotspot and interior cockpit. Scale after driveability/performance.
- Use landscape streaming and hierarchical LOD/virtualized geometry appropriate to chosen engine.
- Race routes and traffic AI should share the same road/navigation data, with safe off-route recovery.
- Vehicle physics uses surface material (asphalt, wet asphalt, gravel, mud) rather than purely visual labels.
- Use nighttime visibility QA on a range of displays; avoid “realistic” darkness that makes actual steering impossible.

## World-scale estimates
Conversation-only rough estimates were **100–250 km²** and **five connected cities**. **Not fixed**, because high-quality unique content, roads and memory/performance budgets determine actual feasible size. Storage **150–300 GB** was also an early guess, not a quality requirement. Any agency or AI worker must not pad a build with huge textures to meet a file-size target.

## World design open decisions
Map footprint and setting, exact road topology, region names, water bodies, drivable non-road limits, time/weather synchronization in free roam, police density, cross-city unlock gating, GPS/minimap route planning, repair stations, safehouses and vehicle licensing. Record approvals in decision log.
