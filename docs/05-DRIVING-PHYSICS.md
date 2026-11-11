# 05 — Driving Model, Car Dynamics, Cameras & Realism

## 1. Desired feel
[CONFIRMED] The driving and driving views must make the player feel **actually seated in a car**. The car obeys physical laws at high speed, on jumps, under steering/braking and on landing; cockpit, cameras, sound and environment express the same physics consistently. Not “game physics that make the car stick to the ground” or reset perfectly after a jump.

**Physics target:** believable, calibrated real-car dynamics with accessible gameplay, rather than an unverifiable claim of 100% real-world simulation. True perfect physical accuracy is impossible in a real-time game; engineer a measured, repeatable approximation and identify any intentional assists.

## 2. Motion model: requirements → simulation behavior
| Situation | Required physically credible response | QA observation |
|---|---|---|
| Acceleration | engine torque curve, gear ratios, driveline inertia, wheel traction and load determine acceleration | Different tuned engines/gears produce different traces |
| Top speed | drag, gearing, downforce, power and tires influence terminal speed | Can't gain speed forever without force/power |
| Hard braking | load transfers forward, brakes can exceed tire grip, stopping distance depends on tire and road | Wet-road stops longer than dry, all else equal |
| Cornering | combined longitudinal/lateral tire grip and load transfer; body roll and yaw appropriate | Excess speed understeers/oversteers plausibly |
| Gear shifts | engine RPM adjusts to gear/wheel speed, torque interruption/clutch dynamics | Wrong gears affect acceleration and sound |
| Nitrous | temporary engine power/torque increase with constraints and handling consequences | Multiple nitrous variants have measured differences |
| Bumps and potholes | springs/dampers/compression/rebound, wheel travel and chassis response | Rough road visibly affects car/camera |
| Jump launch | velocity at takeoff, gravity and angular velocity predict flight | No invisible midair snap/stick |
| Midair | plausible chassis rotations/drag and limited/justified angular influence | Car's direction changes consistently |
| Landing | suspension compression, contact forces, weight transfer, bounce, tire regrip, possible loss of control/damage | Landing can skid, bottom out or damage |
| Collision | impulse, mass, normal forces, material and contact point matter | A light tap differs from a wall impact |
| Rain / wet road | tire friction changes, braking/cornering changes and visibility suffers | Not just a shiny material effect |
| Gravel/dirt | traction and steering response differ from asphalt | Different line, braking and power use |

[WORKING engineering] Use a vehicle simulation with suspension raycasts/physics, tire curves/brush model or comparable vetted physics components; calibrate each car against plausible real-world performance data when licensed/available. Do not claim exact manufacturer handling without data.

## 3. Example minimum physical state
- Chassis: mass (kg), center of mass, moments of inertia (kg·m²), aerodynamic drag, downforce.
- Powertrain: torque curve vs RPM, idle/redline, gear ratios, final drive, clutch, engine braking, drivetrain type.
- Wheels: radius, mass, inertia, friction/slip curves, brake torque; temperature/wear optional [TBD].
- Suspension: spring stiffness, damping, wheel travel, anti-roll response.
- Environment: gravity, road slope/camber, friction material, roughness, wetness, air resistance.
- Dynamic state: position, velocity, yaw/pitch/roll, angular velocity, wheel forces/slip, gear, engine RPM, damage flags.

**No invented game-ready tuning constants here**. Measurements and selected units must come from prototyping/vehicle research.

## 4. Damage model
[CONFIRMED] Hard jumps/landings and impacts may **slip or damage the car**; a full damage system is desirable. [TBD] Mechanical vs cosmetic damage, damage repair/economy, gearbox failure, punctures and how severely damage affects speed. No arbitrary giant explosion due to small curb contact.

## 5. Camera modes
### Cockpit view (signature feature, highest fidelity)
- Per-car accurate-looking dashboard and interior, instrument cluster, RPM, speed, selected gear.
- Animated steering wheel, driver wheel/hands if implemented, plausible windshield view.
- Rear-view and side mirrors when technically feasible; visibility and performance budget to test.
- Rain on glass and functioning wipers; dashboard/night lighting at night.
- Natural chassis/camera movement under bumps, braking, acceleration and landing without exaggerated motion sickness.
- Engine, gear change, tire, wind, rain and collision sounds respond to state.
- Vehicle dimensions, eye height and steering side differ by car, not a single identical interior across fleet.

### Hood view
Forward-facing view positioned at or above hood; suitable for road reading and precise line choice.

### Bumper view
Low front-mounted perspective, visibly close to ground and responsive to road surface.

### Chase view
Third-person camera following the full vehicle; suspension travel, body roll, landings, damage, speed cues and obstruction avoidance apparent.

### Cinematic view
Camera style for replay, showcases and story/highlight moments, **not** a mode that takes control from the player unexpectedly. [TBD] Whether cinematic driving uses dynamic cuts; avoid steering difficulty.

**Camera QA:** FOV, camera shake and damping, eye position, obstruction, night lighting, mirror update/performance, wheel/gear animations, readability during high speed and jumps. Accessibility slider for shake/FOV suggested; not owner-set.

## 6. Controls integration
Simulation must accept throttle/brake/steer/clutch/nitrous/handbrake/gear up/gear down input independent of device. Bindings defined in 06. In manual mode, over-rev, downshift and clutch behavior should have credible feedback; optional assists may be a settings layer without invisibly bypassing chosen manual mechanics.

## 7. Test track acceptance scenarios
1. Same car, dry and wet, 100→0 km/h: consistent longer wet stopping under matched conditions.
2. Same car, engine tier A/B: acceleration telemetry differs for defensible reasons; graphics alone don't count.
3. Different tire compounds and loadouts affect grip at matched speed/curve.
4. A ramp jump preserves approximate ballistic motion; jump landing compression is smooth and mass-dependent.
5. Hard, asymmetric landing can induce yaw, loss of grip or mechanical consequence.
6. Cockpit tachometer, gears, steering wheel, wipers, mirrors stay consistent with car/weather.
7. Chase camera never hides critical road because of a tree/bridge and doesn't snap painfully after collision.
8. Manual shift and analog controller throttle produce correct simulator input; remapping persists.
9. Body kit/spoiler performance claims are accurately defined and tested; cosmetic parts need not magically increase power.
10. Results are reproducible enough to debug and tune.

## 8. Scope unknowns
Engine/physics middleware, sim-cade vs simulation aid settings, damage realism grade, driver animations, VR, wheel force feedback, performance targets, split-screen, multiplayer, replay camera system and precise vehicle model data. **Do not silently add or promise these as committed features.**
