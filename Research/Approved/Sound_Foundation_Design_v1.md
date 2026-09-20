# Olomu Sound Foundation — Design Only

## Status

```text
IMPLEMENTATION_ALLOWED: false
APPROVED_FOR_UNITY: false
```

This file records the current sound design direction only. It is not a production asset list, audio implementation plan, Unity configuration, or audio project setup.

## Purpose

Support the opening loop and survival tone without creating a cinematic or gamey sound identity. Sound should reinforce scarcity, isolation, and tactile interaction without becoming a tutorial or an adaptive music system.

## Core tone

- Tone: sparse, tactile, lonely, survival-first.
- The game should feel quiet and exposed rather than heroic or cinematic.
- Sound should support tension through absence and environmental detail, not through loud dramatic scoring.
- No music-led gameplay. Music does not indicate loot rarity, danger, or resource value.

## Opening loop sound role

### Character creation

- No music during creation.
- Only minimal UI confirmation sound, if used.
- No gameplay advantage from sound.

### Home base spawn

- Quiet ambience: wind through gaps, distant forest sounds, structure creak, subtle environment texture.
- No music on first spawn.
- Player should hear their own footsteps and nearby interaction sounds clearly.
- The base should feel empty and underused, reinforcing the scarcity theme.

### Broken workbench / storage foundation

- Distinct interaction sound for investigation: wood creak, metal rattle, a low mechanical scrape.
- Not a success chime.
- This should communicate broken state and the need to repair, without becoming a heavy reward sound.

### Pine Grove first visit

- Nature ambience only: pine wind, leaves rustle, distant bird life, light environmental texture.
- No combat music on first visit.
- Gather sounds should be hand-gatherable, satisfying, and low-intensity.
- If threats are present, their sounds should be audible before full visual confirmation so the player can avoid rather than be forced into combat.
- The opening loop remains unarmed and non-combat by design.

### Return to base

- Return to the same quiet base ambience.
- Repair or placement feedback may use weighty but low-contrast material sounds, such as wood thud or metal settle.
- The base should not become a loud or celebratory environment during the first loop.

## Location-based sound roles

### Home base

- Ambience: wind through gaps, distant wild ambience, subtle structural creaks.
- Workbench/storage interaction: material-based, low-impact mechanical noise.
- Building placement: soft confirmation, not a dramatic reward sound.
- Hunger/thirst: do not use a constant combat-style warning. Keep any survival cue sparse and subtle.

### Overworld Pine Grove

- Ambience: pine wind, dry grass rustle, natural environmental movement.
- Gathering: distinct but soft pickup sounds for scrap, wood, and loose materials.
- Threats: audible warning before full visual identification where possible.
- No combat music during a safe first visit.

### Fort

- Ambience: enclosed, damp, slightly echoing, more mechanical and enclosed than the base or Pine Grove.
- Footsteps and impact sound should feel more contained and heavier.
- Durability feedback should reflect weapon condition through tactile sound changes, not through numeric UI cues.
- Floor pressure can be expressed via ambience and reverb, not by a separate music system.

## System-wide rules

- Resource types remain separate in sound: food, water, scrap, cloth, oil, and detection should not be collapsed into one generic pickup cue.
- Sound should support gameplay readability without becoming a tutorial layer.
- UI sound should be minimal and soft.
- No voice acting, no narrative voice prompts, and no survival narration.
- Sound should never replace gameplay information or hide a mechanical rule behind a single noise.

## What is not approved yet

These remain out of scope for this design note and should not be created as part of current design work:

- Audio assets (.wav/.ogg/.aiff)
- FMOD/Wwise projects
- Unity AudioSource setup
- Audio Mixer layouts or snapshots
- Detailed attenuation or reverb pipeline
- Clip counts, exact dB values, and asset naming conventions
- Adaptive music system
- Combat music system
- Boss music or dramatic score elements
- Voice acting
- Advanced 3D occlusion or obstruction simulation

## Unresolved technical details

These are intentionally unresolved and should remain design-only until later implementation approval:

- Exact mixer values
- Distance attenuation settings
- Reverb tuning
- Clip lengths and audio file counts
- Audio middleware choice
- Audio file naming and catalog structure
- Final hunger/thirst feedback behavior
- Exact durability-feedback rules

## Recommendation

This design foundation is coherent with the current game direction and does not conflict with the opening loop or resource model.

It should be preserved as a research note only until a later implementation phase is approved.

```text
DESIGN_STATUS: COHERENT_FOR_DESIGN
IMPLEMENTATION_ALLOWED: false
APPROVED_FOR_UNITY: false
```
