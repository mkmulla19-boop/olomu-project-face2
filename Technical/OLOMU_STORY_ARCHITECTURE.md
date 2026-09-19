# OLOMU STORY ARCHITECTURE

**Status:** Design specification only. Not yet implemented.

---

## 1. Purpose

Olomu’s story should be a system operating inside the living world rather than a collection of disconnected cutscenes.

### Core Principle

```
WORLD
 ↓
PLAYER ACTION
 ↓
WORLD EVENT
 ↓
STORY SYSTEM
 ↓
STORY CONDITION
 ↓
STORY RESPONSE
 ↓
WORLD CHANGE
 ↓
NEW EVENTS
```

---

## 2. Story Layers

Olomu should support multiple layers of storytelling:

- **Main Story** — the major narrative arc
- **Character Stories** — stories centered around individual characters
- **Community Stories** — stories involving settlements and communities
- **Faction Stories** — stories involving political, economic, military, or social groups
- **Investigation Stories** — stories discovered through evidence, exploration, documents, witnesses, and environmental clues
- **World Events** — dynamic events that may occur independently of the player’s main story
- **Environmental Stories** — stories communicated through the world itself
- **Personal Stories** — events created by the player’s relationships and choices

---

## 3. Story Objectives

A story objective describes something the player must accomplish, discover, experience, or decide.

Possible objective categories (not fixed quests):

- DISCOVER
- INVESTIGATE
- FOLLOW
- OBSERVE
- LISTEN
- TALK
- MEET
- RESCUE
- PROTECT
- ESCORT
- REPAIR
- BUILD
- GATHER
- HUNT
- SURVIVE
- DELIVER
- RETURN
- CHOOSE
- DECIDE

---

## 4. Story Conditions

Story progression should depend on conditions. Examples:

- Player discovered location
- NPC relationship >= threshold
- Required item obtained
- Community state changed
- Faction relationship changed
- World event occurred
- Previous story stage completed
- Player made specific choice
- Required evidence discovered

The story system should evaluate conditions rather than assuming the player always follows one linear path.

---

## 5. Story Flow

The architecture should support:

**Linear**  
A → B → C → D

**Branching**
```
        B
       / \
A →   C   D
       \ /
        E
```

**Parallel**
```
        ┌→ B
A ──────┤
        └→ C
```

**Conditional**
```
A
↓
Condition?
├── Yes → B
└── No  → C
```

**Delayed consequence**
```
Choice A
   ↓
Nothing immediately visible
   ↓
Later world event
   ↓
NPC / community / faction response
```

---

## 6. Story State

Story progression should be represented by explicit state.

Conceptually:

```
StoryId
StageId
Status
Conditions
CompletedObjectives
Choices
Consequences
RelatedCharacters
RelatedLocations
RelatedFactions
```

Possible statuses (use only those required by the final implementation):

- Locked
- Available
- Active
- Paused
- Completed
- Failed
- Expired
- BranchClosed

---

## 7. Story + World Events

The story system should listen to world events.

Example 1:

```
Player discovers hidden location
        ↓
LocationDiscovered event
        ↓
Investigation system checks evidence
        ↓
Story condition satisfied
        ↓
New investigation stage becomes available
```

Example 2:

```
Player helps a community
        ↓
CommunityHelped event
        ↓
World state changes
        ↓
NPC relationship changes
        ↓
Future story branch becomes available
```

---

## 8. Story Without Quest Markers

Not every story should appear as a traditional quest.

Some stories should be discovered through:

- conversations
- exploration
- objects
- documents
- environmental clues
- NPC behavior
- rumors
- world events
- changes in communities
- player observation

The player should sometimes realize “Something is happening” before the game explicitly says “Here is your quest.”

---

## 9. Dialogue

Dialogue should be connected to world and story state.

A conversation may change depending on:

- previous conversations
- player choices
- relationship
- faction reputation
- discovered information
- current world state
- completed story stages

Dialogue should therefore not be treated as isolated text.

---

## 10. Investigation

Olomu should eventually support investigations where the player assembles information.

```
Clue A
   +
Clue B
   +
Witness information
   +
Environmental evidence
   ↓
Player understanding
   ↓
New conclusion
   ↓
New story possibility
```

The player should not necessarily receive every answer automatically.

---

## 11. Choices and Consequences

Choices should be meaningful. A choice may affect:

- relationships
- communities
- factions
- resources
- access to locations
- future dialogue
- future encounters
- story branches
- world state

Do not create meaningless dialogue choices simply to provide the appearance of choice.

---

## 12. Story Persistence

Important story decisions must survive saving and loading.

```
PlayerChoice
 ↓
StoryState
 ↓
WorldState
 ↓
Save
 ↓
Load
 ↓
World continues consistently
```

The Save System should preserve the necessary story state.

---

## 13. World Story Loop

The long-term architecture should support:

```
PLAYER
 ↓
ACTION
 ↓
EVENT
 ↓
WORLD RESPONSE
 ↓
STORY RESPONSE
 ↓
CONSEQUENCE
 ↓
NEW WORLD STATE
 ↓
NEW OPPORTUNITIES
 ↓
PLAYER
```

This loop is one of the central design principles of Olomu.

---

## 14. Originality Requirement

This architecture is inspired by general game-development principles and research into existing game architectures.

It must **not** reproduce another game’s:

- story
- quests
- dialogue
- characters
- locations
- factions
- assets
- proprietary implementation
- unique narrative content

Olomu must have its own world, story, characters, history, conflicts, and identity.

---

## 15. Implementation Status

These documents define architecture only.

**Do not implement the systems yet.**

The project owner must approve the architecture before Unity implementation begins.
