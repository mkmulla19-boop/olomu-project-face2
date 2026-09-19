# STORY ENGINE

**Status:** Architectural principle defined; implementation pending.

## Core Principle

Olomu should use a **story engine**, not only a fixed list of missions.

The intended flow is:

```
Player Action
     ↓
Game Event
     ↓
World / Story System
     ↓
Quest or Story Condition
     ↓
Story Response
     ↓
World Changes
     ↓
New Events
     ↓
New Stories
```

The world should be capable of generating new situations from previous events and player actions.

## Possible Story Components

- Main story
- Side stories
- Character stories
- Investigations
- Faction stories
- World events
- NPC conversations
- Environmental clues
- Documents
- Communications
- Discoveries
- Player choices
- Consequences
- Persistent world state

## Notes

Exact architecture (event bus, condition evaluators, narrative state machines, etc.) will be designed in the Technical documentation later.
