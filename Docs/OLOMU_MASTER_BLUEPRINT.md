# OLOMU MASTER BLUEPRINT

This document is the high-level architectural vision for Olomu.

Olomu will eventually contain the following interconnected systems. These systems must work together rather than becoming isolated features.

## Core Systems (to be designed and implemented)

1. **Project Architecture** – Overall folder structure, coding standards, assembly definitions, and dependency rules.
2. **Player Character** – Player representation, stats, needs, and progression hooks.
3. **Character Rig** – Animation-ready character setup, bone hierarchy, and avatar definition.
4. **Camera and Controls** – Camera behaviour, input mapping, and player agency.
5. **World System** – Streaming, loading, terrain, and spatial organisation of the game world.
6. **Interaction System** – How the player interacts with objects, NPCs, and the environment.
7. **Resource System** – Gathering, scarcity, and resource types present in the world.
8. **Building System** – Construction, placement, and persistence of player-built structures.
9. **Crafting System** – Recipes, stations, and item creation pipeline.
10. **Inventory** – Storage, equipment, weight/capacity rules, and item data.
11. **Combat** – Combat rules, damage, status effects, and combat feedback.
12. **NPC AI** – Behaviour trees / state machines, schedules, and decision-making for non-player characters.
13. **Animal AI** – Wildlife behaviour, ecosystems, and interaction with the player and environment.
14. **Living World** – Systems that make the world continue existing beyond the player’s immediate attention.
15. **Day/Night** – Time-of-day cycle and its effects on gameplay and systems.
16. **Weather** – Weather states and their influence on the world and systems.
17. **Animation** – Animation controllers, blending, and procedural elements.
18. **Audio** – Sound design architecture, spatial audio, and adaptive music.
19. **VFX** – Visual effects pipeline, performance considerations.
20. **Save / Progression** – Persistence of world state, player progress, and long-term consequences.
21. **UI** – User interface architecture and data binding.
22. **Story Engine** – The system that drives narrative responses from player actions and world state.
23. **Quest System** – Structured and emergent quest generation and tracking.
24. **World Events** – Events that can occur independently of or in reaction to the player.
25. **Player Choices** – Meaningful decisions and their recording.
26. **Consequences** – How choices and actions permanently or temporarily alter the world.
27. **Environmental Storytelling** – Narrative delivered through the world itself rather than dialogue alone.
28. **Optimization** – Performance targets, profiling strategy, and platform considerations.

## Camera foundation — approved design only

The camera decisions below define the intended player-facing structure. They do not authorize Unity implementation, camera values, scenes, prefabs, scripts, or input code.

- Perspective: angled top-down / isometric-like view.
- Follow: automatic player follow.
- Rotation: not allowed for the player.
- Free camera pan: not allowed.
- Zoom: limited zoom in/out only.
- Input pattern: pinch-style zoom is the intended mobile interaction pattern; exact input mapping remains for implementation planning.
- Home base: permits a modestly wider maximum zoom-out than normal locations so the player can understand construction and keep the character and nearby objectives visible together.
- Overworld: uses the standard limited zoom range.
- Fort: uses the standard limited zoom range or a slightly tighter maximum view to preserve combat readability and avoid seeing outside the Fort.
- Follow behavior remains consistent across home base, overworld, and Fort; no separate combat camera switch is approved.
- The opening camera must keep the character and the first base objective visible together when the player spawns one tile south of it facing north.
- Exact zoom limits, follow smoothing, camera height, angle, clipping, obstruction handling, and device-specific behavior remain unresolved.

## Guiding Principles

- Systems should communicate primarily through well-defined events where appropriate.
- Prefer modular design with clear responsibilities.
- The world should feel alive and reactive.
- Creative content remains original; architectural lessons may be learned from other games.
- No permanent creative decisions (story, characters, factions, specific locations, etc.) without explicit approval from the project owner.

## Current Status

Pre-production. All systems listed above are planned but not yet implemented.
