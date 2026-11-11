# 06 — Inputs, Manual / Automatic Gearbox, Keybinding & Devices

## Confirmed input requirements
- **Keyboard playable** with fully configurable keys.
- **Gamepad/joystick support** and detection: if connected, the game should recognize device and present its valid mappings/icons/axes rather than assuming a generic keyboard.
- **Every gameplay control must be remappable** by the player: accelerator, normal brake, handbrake, steering left/right, nitrous, gear up/down, clutch (if manual), camera, look-back and other implemented commands.
- **Automatic and manual transmission** settings. Manual shift is real player action, not merely cosmetic.
- **Requested default manual mapping:** **Left Shift = gear up**, **Right Shift = gear down**. Distinguish physical left/right Shift keys in the input layer; the default is a design requirement to validate across keyboard layouts and OS/device handling.
- Save user binding profiles and ensure changes work during racing and after reopening the game.

## Initial action map (other defaults proposed, not canon)
| Action | Keyboard default | Controller/joystick suggested |
|---|---|---|
| Accelerate | W or Up Arrow [PROPOSED] | Right trigger or configurable analog axis |
| Brake / reverse | S or Down Arrow [PROPOSED] | Left trigger or analog axis |
| Steer | A/D [PROPOSED] | Left stick or wheel axis |
| Handbrake | Space [PROPOSED] | Face/shoulder button |
| **Gear UP** | **Left Shift [CONFIRMED]** | User-mappable paddle / button |
| **Gear DOWN** | **Right Shift [CONFIRMED]** | User-mappable paddle / button |
| Clutch | C [PROPOSED, optional manual clutch] | User-mappable pedal/button |
| Nitrous | N [PROPOSED] | User-mappable button |
| Change camera | V [PROPOSED] | User-mappable button |
| Look back | B [PROPOSED] | User-mappable button |
| Pause | Escape [PROPOSED] | Start/Menu |

The table is a **starting mapping sheet**. Only Left/Right Shift as stated above is specifically requested as default; all actions, including those, remain editable.

## Device detection and remapping flow
1. Scan input devices at startup and on hotplug/unplug.
2. Identify keyboard vs generic gamepad vs racing wheel/joystick and available axes/buttons, without assuming that device labels are universally reliable.
3. Select usable default profile only if none is saved; use matching glyphs on HUD.
4. Expose **Controls → Device → Edit bindings** where user can click an action, press desired key/button/axis, and see that input assigned.
5. Warn on conflicting assignments (two actions to same button); allow meaningful dual bindings where non-conflicting.
6. Expose invert steering, analog deadzone, sensitivity, steering curve and controller vibration options [WORKING].
7. Persist profiles per player/device. On unplug, allow safe fallback without erasing previous profile.
8. Test racing, garage menus and cinematics across devices.

## Gearbox behavior
- **Automatic:** physics system selects gear according to tuning and speed; manual bindings can be inactive or temporary override only if explicitly configured.
- **Manual:** gear state changes on intentional shift; observe RPM, power interruptions and gear ratios. **Clutch optional** per owner discussion: simple manual mode can simulate clutch automatically; advanced manual mode may require explicit clutch input.
- **No implicit high-end gear access:** chosen gearbox hardware and its individual gear sets/variants unlock **by career stage and car fitment**. Input mode (manual/auto) is different from *owning* an upgraded gearbox.

## UI requirements
- Control settings show **device name**, action, currently assigned input, restore defaults, test input visualization and Save/Cancel.
- Pause screen accessible by keyboard/controller; focus state visible.
- Display active gear/RPM/speed clearly in cockpit and HUD if selected.
- Left vs Right Shift recognition tested in Windows packaged build. Consider keyboard rollover, accessibility remaps, international keyboards; failed recognition requires a documented fallback and explicit user setting.

## Acceptance tests
- Reassign brake and handbrake separately; new bindings work immediately.
- Save, quit, launch EXE; bindings survive.
- Connect gamepad while on menu, drive, then disconnect: no lockup.
- Joystick steering axis calibrates and works independently of buttons.
- Left Shift upshifts while Right Shift downshifts, including successive shifts.
- Automatic mode does not randomly ignore requested settings; manual clutch mode works only when chosen.
- Camera view can be changed by either keyboard or controller.
- Profiles for two different devices do not overwrite one another.
