# QUEST SYSTEM

**Status:** Architectural framework — no specific quests defined yet.

---

## Design Goals

Olomu quests should support more than simple objectives. The system should eventually handle:

- Main quests
- Side quests
- Character stories
- Investigation quests
- Faction quests
- Hidden objectives
- Discovery objectives
- Survival objectives
- Choice-based objectives
- Escort
- Rescue
- Protection
- Investigation
- Exploration
- Building
- Gathering
- Hunting
- Repair
- Dialogue
- Observation
- Decision-making

---

## Event-Responsive Quests

Quests should be capable of responding to game events:

```
Player discovers something
        ↓
Game Event
        ↓
Quest detects event
        ↓
Objective updates
        ↓
Story response
        ↓
World changes
```

---

## Integration

- Integrates with the Story Engine (see STORY_ENGINE.md)
- Can be influenced by world state and living-world systems
- Tracks player choices and consequences where relevant

Exact data structures and runtime behaviour will be designed later in Technical/QUEST_ARCHITECTURE.md.

Do not invent specific quest content yet.
