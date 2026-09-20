# Olomu AI Repository Map

## Purpose

This map helps a new AI or reviewer quickly locate the correct file, folder, or design note before answering questions or making changes.

## Project status and non-negotiable rules

Start here:

- `README.md` — repository purpose, project status, top-level folder map, originality rules.
- `Development/DEVELOPMENT_RULES.md` — privacy, originality, modularity, documentation, and reproducibility rules.
- `Development/UNITY_AI_INSTRUCTIONS.md` — AI development rules, including read-before-modifying, no invented requirements, no copying, testing, and documentation.
- `Research/Approved/AI_Handoff_Note.md` — current approved design state, unresolved questions, next study, and implementation gates.

Current gate:

```text
IMPLEMENTATION_ALLOWED: false
APPROVED_FOR_UNITY: false
```

Do not create Unity scenes, prefabs, scripts, ScriptableObjects, gameplay code, audio assets, or middleware projects unless the owner explicitly authorizes implementation.

## Where to look by question

| Question or task | First file or folder | Related files |
|---|---|---|
| What is the current project state? | `Research/Approved/AI_Handoff_Note.md` | `README.md` |
| What can an AI modify or implement? | `Development/UNITY_AI_INSTRUCTIONS.md` | `Development/DEVELOPMENT_RULES.md` |
| What is the overall game architecture? | `Docs/OLOMU_MASTER_BLUEPRINT.md` | `Technical/` |
| What is the opening player loop? | `Research/Approved/AI_Handoff_Note.md` | `Research/Approved/Overworld_Farming_Yield_Study_v1.json` |
| What is the starting state? | `Research/Approved/AI_Handoff_Note.md` | `Research/Approved/Scarcity_Config_v3.3.json` |
| What is the Pine Grove first-trip plan? | `Research/Approved/Overworld_Farming_Yield_Study_v1.json` | `Research/Approved/AI_Handoff_Note.md` |
| What must be measured before Pine Grove is finalized? | `Research/Approved/Overworld_Farming_Yield_Study_v1.json` → `firstVisitStudyDefinition` | `Research/Approved/AI_Handoff_Note.md` |
| What are the current scarcity and survival values? | `Research/Approved/Scarcity_Config_v3.3.json` | `Research/Approved/Overworld_Farming_Yield_Study_v1.json` |
| What are the economy-loop findings? | `Research/Approved/Economy_Loop_Study_v1.json` | `Research/Approved/Scarcity_Config_v3.3.json` |
| What is the sound direction? | `Research/Approved/Sound_Foundation_Design_v1.md` | `Technical/AUDIO_SYSTEM.md` |
| Is an audio asset or Unity audio setup approved? | `Research/Approved/Sound_Foundation_Design_v1.md` | `Technical/AUDIO_SYSTEM.md` |
| Where are story and world decisions? | `Docs/` | `GameDesign/` |
| Where are technical architecture notes? | `Technical/` | `Docs/OLOMU_MASTER_BLUEPRINT.md` |
| Where are gameplay pillar documents? | `GameDesign/` | `Docs/` |
| Where are roadmap and task notes? | `Development/` | `Development/CHANGELOG.md`, `ROADMAP.md`, `TODO.md` |
| Where is the Unity project? | `UnityProject/` | Currently placeholder only; do not assume implementation exists. |

## Approved research files

### `Research/Approved/AI_Handoff_Note.md`

Primary handoff and current-state file. Contains:

- approved opening sequence
- character creation and starting state
- camera foundation
- Pine Grove conditional-feasibility result
- Pine Grove measurement requirements
- emergency food/water decision D, deferred
- unresolved work
- next actionable study
- AI working rules

### `Research/Approved/Overworld_Farming_Yield_Study_v1.json`

Authoritative study structure for overworld farming research. Contains:

- approved-for-design metadata
- confirmed foundation and provisional values
- overworld zone inventory
- resource-separation rules
- timing and danger measurements
- inventory-pressure tracking
- first-visit requirements
- `firstVisitStudyDefinition` for Pine Grove
- follow-up Maintenance/Workbench study reference

Do not add final yields, travel times, objective costs, or emergency supplies without measurement and approval.

### `Research/Approved/Scarcity_Config_v3.3.json`

Scarcity, durability, survival, and resource configuration. Treat values according to their recorded status: verified, provisional, unresolved, or hypothesis.

### `Research/Approved/Economy_Loop_Study_v1.json`

Economy and Fort-loop research. Do not treat design intent as proven final balance.

### `Research/Approved/Sound_Foundation_Design_v1.md`

Design-only sound direction. Contains:

- sparse, tactile, lonely tone
- home-base ambience
- Pine Grove ambience and gathering feedback
- Fort ambience and restrained durability feedback
- sound-scope exclusions
- unresolved technical audio details

It does not authorize:

- `.wav`, `.ogg`, or other audio assets
- FMOD/Wwise projects
- Unity AudioSources or Mixers
- adaptive music
- voice acting
- production audio folders

## Main folders

### `Docs/`

High-level design, story, world, locations, factions, player choices, quests, events, and the master blueprint.

Important files:

- `Docs/OLOMU_MASTER_BLUEPRINT.md` — high-level architectural vision and approved camera foundation.
- `Docs/WORLD_DESIGN.md` — world design.
- `Docs/LOCATIONS.md` — location design.
- `Docs/STORY_BIBLE.md` — story reference.
- `Docs/STORY_DESIGN_RULES.md` — story constraints.
- `Docs/CHARACTERS.md` — character design.
- `Docs/FACTIONS.md` — faction design.
- `Docs/QUEST_SYSTEM.md` — quest design.
- `Docs/WORLD_EVENTS.md` — world-event design.

### `GameDesign/`

Core gameplay pillars:

- `PLAYER.md` — player design.
- `SURVIVAL.md` — survival design.
- `EXPLORATION.md` — exploration design.
- `INVENTORY.md` — inventory design.
- `CRAFTING.md` — crafting design.
- `BUILDING.md` — building design.
- `COMBAT.md` — combat design.
- `ANIMALS.md` — animal design.
- `NPC_AI.md` — NPC behavior design.
- `PROGRESSION.md` — progression design.

### `Technical/`

Technical architecture references only. Important files:

- `Technical/UNITY_ARCHITECTURE.md` — Unity architecture.
- `Technical/CHARACTER_SYSTEM.md` — character system architecture.
- `Technical/INTERACTION_SYSTEM.md` — interaction architecture.
- `Technical/WORLD_SYSTEM.md` — world architecture.
- `Technical/EVENT_SYSTEM.md` — event architecture.
- `Technical/SAVE_SYSTEM.md` — save architecture.
- `Technical/AUDIO_SYSTEM.md` — currently a placeholder; do not treat it as approved audio implementation.
- `Technical/PERFORMANCE.md` — performance constraints.
- `Technical/AI_ARCHITECTURE.md` — AI architecture.
- `Technical/QUEST_ARCHITECTURE.md` — quest architecture.
- `Technical/ANIMATION_SYSTEM.md` — animation architecture.

### `Development/`

Project process and AI guidance:

- `Development/UNITY_AI_INSTRUCTIONS.md` — required AI development rules.
- `Development/DEVELOPMENT_RULES.md` — project-wide development rules.
- `Development/ROADMAP.md` — roadmap.
- `Development/TODO.md` — task list.
- `Development/CHANGELOG.md` — major change history.

### `Research/`

Historical, architectural, and gameplay research. `Research/Approved/` contains the currently approved design-study files. Do not assume a research document means implementation is authorized.

### `UnityProject/`

Placeholder directory at present. It contains `.gitkeep`; no Unity implementation should be assumed to exist.

## Change procedure for a new AI

1. Read `README.md`.
2. Read `Development/UNITY_AI_INSTRUCTIONS.md` and `Development/DEVELOPMENT_RULES.md`.
3. Read `Research/Approved/AI_Handoff_Note.md`.
4. Locate the specific subject file using the table above.
5. Inspect the exact file before proposing changes.
6. Separate verified findings, approved design requirements, hypotheses, provisional assumptions, and unresolved questions.
7. Do not invent missing values.
8. Before any write, state the exact file and scope of the change.
9. Keep implementation blocked unless the owner explicitly changes the gate.
10. Record major approved changes in the appropriate documentation and, when required, `Development/CHANGELOG.md`.

## Current next study

The next actionable work is measurement and validation for `overworld_pine_grove`:

- base-to-zone travel time
- gathering time
- return time
- total first-loop duration
- first-visit scrap observation
- repeatable 30-minute scrap rate
- food and water presence
- cloth and oil presence
- tool-gated nodes
- threat and escape behavior
- hunger and thirst loss
- approved scrap requirement for the first base objective
- one-run versus two-run requirement

After those measurements, review the emergency food/water decision. Do not create Unity or audio implementation as part of this study.
