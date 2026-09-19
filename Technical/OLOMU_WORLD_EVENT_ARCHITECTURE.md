# OLOMU WORLD EVENT ARCHITECTURE

**Status:** Design specification only. Not yet implemented.

---

## 1. Purpose

Olomu should be an event-driven world.

Gameplay systems should be able to report meaningful changes to a central event layer without needing to know which story, NPC, faction, quest, or other system will react to those changes.

### Core Principle

```
Player / NPC / World
        ↓
Action
        ↓
World Event
        ↓
Systems listen
        ↓
World reacts
        ↓
Story may react
        ↓
Future world state changes
```

---

## 2. World Event

A World Event represents a meaningful occurrence in the game world.

### Example Event Categories (Types only — no story content)

**Player**
- PlayerEnteredRegion
- PlayerLeftRegion
- PlayerDiscoveredLocation
- PlayerCollectedResource
- PlayerCraftedItem
- PlayerBuiltStructure
- PlayerDestroyedObject
- PlayerHelpedCharacter
- PlayerHarmedCharacter
- PlayerMadeChoice

**Combat**
- CombatStarted
- CharacterDamaged
- CharacterDefeated
- EnemyEscaped
- PlayerEscaped

**NPC**
- NPCMetPlayer
- NPCRelationshipChanged
- NPCJoinedCommunity
- NPCLeftCommunity
- NPCChangedOccupation
- NPCChangedFaction

**Community**
- CommunityHelped
- CommunityDamaged
- CommunityThreatened
- CommunityProspered
- CommunityCollapsed

**Exploration**
- LocationDiscovered
- SecretDiscovered
- DocumentFound
- HistoricalSiteDiscovered
- HiddenPathDiscovered

**Faction**
- FactionRelationshipChanged
- FactionConflictStarted
- FactionTradeStarted
- FactionTerritoryChanged

These are examples of event **types** only. No actual Olomu story content is defined here.

---

## 3. Event Data

Every event should contain enough information for systems to understand what happened.

Conceptually:

```
WorldEvent
├── EventId
├── EventType
├── WorldTime
├── LocationId
├── InstigatorId
├── TargetId
├── RelatedFactionId
├── RelatedCommunityId
├── Data
└── Tags
```

Not every event requires every field.

The implementation should use appropriate typed event data rather than putting everything into one uncontrolled data structure.

---

## 4. Event Publishing

Systems should publish events when meaningful state changes occur.

Example flow:

```
Player gathers resource
        ↓
Resource system updates resource
        ↓
ResourceGathered event
        ↓
Inventory receives resource
        ↓
Quest system may react
        ↓
World statistics may update
        ↓
Other systems may react
```

The resource system should **not** directly control the quest system. This keeps systems modular.

---

## 5. Event Subscribers

Potential event consumers include:

- Story System
- Quest System
- NPC System
- Faction System
- Relationship System
- World Simulation
- Achievement System
- Save System
- UI System
- Audio / VFX system
- Analytics / debugging system

A system should subscribe only to events relevant to it.

---

## 6. World Memory

Olomu should remember meaningful world changes.

```
EVENT
 ↓
WORLD STATE CHANGE
 ↓
SAVE
 ↓
FUTURE SYSTEMS READ STATE
```

Examples of meaningful persistent changes:
- NPC relationship changed
- Community status changed
- Faction relationship changed
- Location discovered
- Important object destroyed
- Player made a major decision
- Story milestone completed

Not every tiny event needs permanent storage.

Distinguish between:

- **Temporary events** — used to trigger immediate reactions
- **Persistent events** — used to change the long-term world

---

## 7. Event → Consequence

A major Olomu principle:

```
Event
 ↓
Immediate consequence
 ↓
Persistent state change
 ↓
Future consequence
```

Consequences should not always happen immediately. A player’s decision today may change a character’s behavior much later.

---

## 8. Event Safety

The architecture must avoid uncontrolled chains (e.g. Event A → Event B → Event C → Event A creating an infinite loop).

The system should therefore support:

- event IDs
- source identification
- recursion protection
- processing limits
- deterministic ordering where required
- debugging / logging
- cancellation where appropriate

---

## 9. Save System Integration

The Save System should store important persistent world state.

The event system itself should **not** become the save system.

Separate:

- **EVENT** — describes what happened
- **PERSISTENT WORLD STATE** — describes what is currently true

---

## 10. Debugging

The event architecture should eventually support developer tools showing:

- Event
- Event Type
- Time
- Location
- Source
- Target
- Listeners
- Responses
- World State Changes

This will be important when debugging complex story chains.

---

## 11. Unity Implementation Status

**Do not implement this architecture yet.**

This document is a design specification only.

When implementation begins, Unity AI (or developers) must first inspect the existing project architecture and then create the event system incrementally.

---

## Originality Note

This architecture is based on general game-development principles. It does **not** reproduce any other game’s class names, namespaces, proprietary code, story content, or unique narrative systems.
