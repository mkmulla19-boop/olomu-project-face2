# Olomu Project — AI Handoff Note

## Repository

`mkmulla19-boop/olomu-project-face2`

## Current project phase

The project remains in research and design-validation.

```text
IMPLEMENTATION_ALLOWED: false
APPROVED_FOR_UNITY: false
```

Do not create Unity scenes, prefabs, scripts, ScriptableObjects, or gameplay code unless the user explicitly authorizes implementation.

## Approved design foundation

### Opening

```text
Load
→ Minimal character creation
→ Playable home base
→ Spawn south of first objective, facing north
→ Examine broken workbench / storage foundation
→ Learn scrap is required
→ Travel to overworld_pine_grove
→ Gather initial resources
→ Return to home base
```

### Character creation

- Male/Female toggle.
- 4–6 head presets and 3 skin-tone swatches.
- No class, attributes, perks, or gameplay effect.
- No player-facing name at first load.
- Internal identifier: `Survivor_####`.
- Later renaming and appearance changes remain deferred features.

### Starting state

- Hunger: 80%, provisional.
- Thirst: 80%, provisional.
- Empty inventory.
- Backpack capacity: 8, provisional.
- Loot reserve: 3 slots, provisional.
- No starting weapon.
- No starting food or water.

### Spawn

- Player spawns inside the owned home base.
- Spawn point is one tile south of the first base objective.
- Character faces north toward the broken workbench/storage foundation.
- Camera must keep the character and first objective visible together.

## Camera foundation — approved design only

- Angled top-down / isometric-like perspective.
- Automatic player follow.
- No player-controlled rotation.
- No free camera pan.
- Limited zoom in/out.
- Home base permits a modestly wider maximum zoom-out for construction visibility.
- Overworld uses the standard limited zoom range.
- Fort uses the standard or slightly tighter maximum view for combat readability and boundary control.
- Same general follow behavior across home base, overworld, and Fort.
- No separate combat camera switch.
- Exact technical camera values remain unresolved.

## First overworld trip — feasibility result

Status: `CONDITIONALLY_FEASIBLE_PENDING_MEASUREMENTS`.

There is no hard conflict with the current foundation, provided `overworld_pine_grove` is designed as an unarmed first-gathering zone.

Requirements:

- First visit must be completable unarmed.
- Mandatory combat is not allowed during the first visit.
- Initial resources must be hand-gatherable or world-lootable.
- Target no-combat visit should remain under 10 minutes.
- First run must provide measurable progress toward repairing the first workbench/storage foundation objective.
- Food and water availability in Pine Grove must be evaluated before finalizing the no-starting-food/no-starting-water rule.
- Travel time and survival drain must be measured together to validate the provisional 80%/80% start.

Soft tensions:

- The provisional 80%/80% start supports one short loop but may not support two consecutive loops without food or water.
- The no-weapon start requires Pine Grove gathering to avoid mandatory combat and weapon-gated resources.
- Exact resource yields and travel cost remain unresolved.

## Pine Grove Study Definition — Measurements Required

This section defines requirements only. It does not add final yields, travel times, objective costs, or emergency supplies.

### Route

- Measure base exit to Pine Grove zone-load completion on foot without a sprint bonus.
- Measure a route covering first-visit hand-gatherable nodes and world-loot spawns without backtracking beyond zone bounds.
- Measure Pine Grove exit to base entry, including overworld map traversal if applicable.
- Record total exit + gather + return loop duration as the survival-drain basis.
- Keep the target no-combat gathering duration under 10 minutes as a requirement, not a result.

### Resources

- Record scrap obtained during the first visit.
- Measure repeatable scrap rate over a 30-minute loop using 2–3 timed runs.
- Record food presence, type, and amount as observations only.
- Record water presence and amount as observations only.
- Record cloth presence separately.
- Verify whether oil is absent or present; absence remains an expectation to test.
- Record tool-gated nodes. Any required first-visit tool must be found in the same zone and cannot be craft-gated.

### Safety

- Preserve unarmed gathering and no mandatory combat as first-visit requirements.
- Record threat type, speed, vision, patrol/static behavior, and node-blocking frequency.
- Record escape, avoidance, cover, and zone-edge options, including stamina cost if applicable.

### Survival

- Calculate hunger loss as provisional hunger drain multiplied by measured total loop minutes.
- Calculate thirst loss as provisional thirst drain multiplied by measured total loop minutes.
- Evaluate remaining hunger and thirst after one loop from the provisional 80%/80% start.
- Evaluate whether a second loop reaches zero before return.
- Do not promote provisional drain rates to final balance.

### First objective progress

- Define the required scrap for the broken workbench/storage foundation as a missing design input; do not invent it in this study.
- After the objective requirement is approved, determine whether one or two runs are expected.
- Treat three or more runs as a potential opening-grind risk requiring review.

### Categories

Verified findings:

- Opening sequence is defined and committed.
- Provisional 80%/80% provides approximately 36 minutes of hunger and 28 minutes of thirst before zero under current provisional drain rates.
- Backpack capacity 8 and loot reserve 3 remain provisional.
- Camera foundation supports visibility of the player and gathering objectives.
- Resources remain separate and there is no badge-to-resource conversion.

Hypotheses:

- Pine Grove can provide first-repair progress in one or two unarmed runs.
- The player can avoid threats on the first visit through pathing.
- Thirst may be the limiting need for a second trip.

Missing measurements:

- Base-to-Pine travel time.
- First-visit gathering time.
- Pine-to-base return time.
- Scrap count on first visit.
- Repeatable scrap rate.
- Food and water presence.
- Tool-gated nodes.
- Threat and escape behavior.
- Total hunger and thirst loss per loop.
- Approved scrap requirement for the first objective.
- One-run versus two-run requirement.

Provisional assumptions:

- 80%/80% starting needs.
- Backpack capacity 8 and loot reserve 3.
- Hunger drain 2.222222 per minute and thirst drain 2.857143 per minute.
- Fort clear times 12/15/18 minutes; not used as Pine Grove results.

## Emergency base food/water decision

- Decision: Option D — keep unresolved until the yield and travel study provides data.
- No emergency food or water item is added to the base at this stage.
- No starting food or water value is being invented.
- This decision is not implementation authorization.

## Existing foundation and unresolved work

The durability-first Fort model remains intact:

- Full-clear condition loss: 40.5.
- Repair is per weapon.
- Up to three discrete repair kits may be needed.
- Fractional repair-kit pooling is not allowed.
- No badge-to-resource conversion.
- Food, water, scrap, cloth, oil, and detection remain separate resources.

Unresolved:

- Pine Grove food, water, scrap, cloth, and oil yields.
- First-trip travel time and total loop duration.
- Pine Grove danger layout and mandatory-combat status.
- Repair-kit source and maintenance-item yields.
- Fort clear times and survival-drain multiplier.
- Death-loss value and recovery windows.
- Exact camera angle, height, zoom limits, smoothing, clipping, obstruction handling, and device controls.

## Next actionable study

Complete the Pine Grove measurements defined above, including:

- scrap minimum per run
- food/water availability
- weapon requirement
- travel time
- first-loop total duration
- interruption and danger tracking
- first-objective scrap requirement

After that, proceed to the planned Maintenance/Workbench study, then Death Recovery finalization.

## Working rules

1. Work one file at a time.
2. Keep research in `Research/`.
3. Keep requirements, hypotheses, provisional values, verified findings, and final balance separate.
4. Do not treat reference-game observations as Olomu facts.
5. Do not convert research into Unity implementation.
6. Review exact changes before modifying approved files.
7. Preserve `IMPLEMENTATION_ALLOWED: false` and `APPROVED_FOR_UNITY: false` until explicitly changed by the owner.
