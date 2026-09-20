# Olomu Project — AI Handoff Note

## Repository

`mkmulla19-boop/olomu-project-face2`

## Confirmed files

```text
README.md
Development/UNITY_AI_INSTRUCTIONS.md
Research/Approved/Scarcity_Config_v3.3.json
Research/Approved/Economy_Loop_Study_v1.json
```

## Current project phase

The project is still in the research and design-validation phase.

Unity implementation has not been authorized.

```text
IMPLEMENTATION_ALLOWED: false
```

Do not create Unity scenes, prefabs, scripts, ScriptableObjects, or gameplay code unless the user explicitly authorizes implementation later.

## Approved research files

### `Research/Approved/Scarcity_Config_v3.3.json`

Contains the current scarcity, durability, survival, and resource configuration.

### `Research/Approved/Economy_Loop_Study_v1.json`

Status:

```text
APPROVED_FOR_DESIGN
implementationAllowed: false
```

This approval means the study structure and verified findings are accepted for continued design. It does not mean that all balance values are final or ready for Unity implementation.

## Important verified findings

- Weapon condition-loss calculations are valid.
- Full-clear condition loss is `40.5`.
- Repair is handled per weapon.
- A full restore may require up to 3 discrete repair-kit uses when all three weapons need repair.
- Fractional repair-kit pooling is not allowed.
- Average badges:
  - Floor 1: `11.5`
  - Floor 2: `21.5`
  - Floor 3: `32.5`
  - Full clear: `65.5`
- Full crate set cost: `95` badges.
- One full crate set requires approximately `1.45` full clears.
- Hunger and thirst drain-rate calculations are mathematically valid.
- The death-bag interpretation remains consistent with the current design.

## Still unresolved

Do not silently decide or implement these:

- overworld food yield
- overworld water yield
- scrap yield
- repair-kit source and drop rates
- maintenance-item yield
- evidence-based clear time for each fort floor
- fort survival-drain multiplier
- badge-to-resource conversion
- Food_Stew versus Food_Dried balance
- final economic value of death losses

The `12/15/18 minute` floor-clear estimates are provisional assumptions, not approved authoritative values.

The intended loop is:

```text
Floor 1: slightly profitable
Floor 2: approximately break-even
Floor 3: net-loss without overworld preparation
```

This remains a design intention, not a mathematically proven final balance.

## Opening foundation — approved design decisions

These decisions define the opening structure only. They do not authorize Unity implementation and do not copy any external game's assets, UI, map, dialogue, or exact progression.

### Character creation

- Character creation occurs before the first playable home-base load.
- Creation is minimal and should take less than 15 seconds.
- Gender selection: Male / Female toggle.
- Appearance: 4–6 head presets and 3 skin-tone swatches.
- Appearance has no gameplay effect.
- No class, attributes, perks, or starting advantage are selected during creation.
- Player name is not required at first load.
- An internal temporary identifier uses the form `Survivor_####`; it is not player-facing.
- Player renaming is deferred to a later base setting.
- Appearance changes may be available later through a base mirror/camp item after Floor 1; this is a later design feature, not part of first boot.

### Spawn and first interaction

- After creation, the player spawns inside the owned home base.
- Spawn point: one tile south of the first base objective.
- Facing direction: north, toward the broken workbench / storage foundation objective.
- The camera should keep the character and first objective in view.
- The first interaction is to examine the base objective and learn that scrap is needed to repair it.
- The opening then directs the player toward `overworld_pine_grove` for initial resource preparation before returning to the base.

### Starting-state design decision

The following opening values are approved design decisions for the opening specification, not final balance claims:

- Hunger: `80%`.
- Thirst: `80%`.
- Initial inventory: empty.
- Backpack capacity: `8`.
- Loot reserve: `3` slots, still marked provisional in the scarcity configuration.
- Starting weapon: none.
- No starting food or water is granted by character creation.

The starting-state values must remain compatible with the authoritative scarcity configuration and may be revised if later validation shows a foundation conflict.

### Opening sequence

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

This is an Olomu design structure informed by broad survival-game patterns, not a reproduction of another game's opening.

## Next study

The approved opening foundation should be validated against the existing scarcity and economy foundation before beginning another study. No new study file is required for these opening decisions.

The next research file remains deferred until the opening foundation is confirmed against the project structure:

```text
Research/Approved/Overworld_Farming_Yield_Study_v1.json
```

Purpose:

- define or study food, water, scrap, maintenance, and repair-kit yields
- establish expected overworld yield per time period
- compare overworld preparation against Floor 1, Floor 2, and Floor 3 costs
- provide the missing values needed to revise the economy study

After that, the planned study is:

```text
Research/Approved/Death_Recovery_Finalization_Study_v1.json
```

## Working rules for the next AI

1. Work one file at a time.
2. Keep all research in the `Research/` folder.
3. Do not create broad folder structures unless explicitly requested.
4. Do not modify existing approved files without reviewing the exact change first.
5. Keep unresolved questions explicitly labeled.
6. Do not convert research into Unity implementation.
7. Before saving a file, show or explain what will be saved.
8. Preserve the distinction between:
   - approved for design
   - final balance
   - implementation authorized
9. Do not claim that a value is proven when the required conversion or yield data does not exist.
10. Ask the user before creating the next file if confirmation is needed.

## Last completed action

The opening foundation decisions were added to this handoff note:

- minimal character creation
- home-base spawn near the first objective
- initial opening-state values
- first interaction and outward resource loop

Unity implementation remains unauthorized.
