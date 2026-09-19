# UNITY AI INSTRUCTIONS

These rules apply to any AI-assisted development work on the Olomu Unity project.

## Rule 1 — Read before modifying

Before changing an existing system, inspect the relevant code, scenes, prefabs, components, ScriptableObjects, and documentation.

## Rule 2 — Do not destroy working systems

Do not replace or rewrite working systems unnecessarily.

## Rule 3 — Follow the architecture

New systems must fit the documented Olomu architecture.

## Rule 4 — Modular design

Prefer modular systems with clear responsibilities.

## Rule 5 — Event-driven communication

Where appropriate, systems should communicate through well-defined events rather than creating unnecessary direct dependencies.

## Rule 6 — Preserve compatibility

When modifying a system, check what other systems depend on it.

## Rule 7 — No invented requirements

If the design is unclear, identify the uncertainty rather than silently inventing a major feature.

## Rule 8 — No copying

Do not recreate another game’s protected creative content.

## Rule 9 — Test changes

After significant changes, verify that the Unity project still compiles and that affected systems still function.

## Rule 10 — Document major changes

Major architectural changes must be recorded in the appropriate documentation and CHANGELOG.md.
