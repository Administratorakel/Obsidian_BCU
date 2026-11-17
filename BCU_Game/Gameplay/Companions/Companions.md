[[Targeting and Aggro]]

Future system:

Purpose:
- Status application support
- Gold collection
- Dmg support

Rules:
Solo player → companion active
Party of 2 → both companions active
Party of 3 → leader companion active
Party of 4+ → companions only collect Gold


[[Party]]
[[Amy]]
[[Dipsy]]
[[Aleksei]]


**Status:** Concept development  
**Implementation:** Planned for later development

## 1. General Companion Rules

Companions are permanent combat assists that support the player without requiring additional micromanagement.

### Combat Behavior

- Companions are immortal and have no HP.
    
- Enemies cannot target companions.
    
- Companions cannot physically block enemies or players.
    
- Enemies cannot physically block players either.
    
- Companions never initiate combat without player involvement.
    
- When the player attacks an enemy, companions may engage.
    
- When Vector Break hits an enemy, companions enter combat.
    
- Using Vector Break without hitting an enemy does not initiate companion combat.
    
- Companions disengage when the player moves sufficiently far away.
    
- Outside combat, companions follow the player.
    

### Player Defeat

When the player is defeated:

- Companions immediately stop participating in combat.
    
- They approach the player's defeated body.
    
- They lie down beside the player until the situation changes.
    

### Companion Progression

Companion survivability upgrades are unnecessary because companions cannot be defeated.

Other possible progression systems, such as damage scaling or ability modifications, remain undecided.

### Combat Initiation

Companions cannot independently start combat.

They respond to player-initiated engagements.

### Disengagement

If the player moves sufficiently far away from the encounter, companions abandon their targets and return.

The disengagement distance remains undecided.


## Shared rules
- Companions are **immortal, untargetable assists**. They have no HP or downed/revival state.
- Companions cannot body-block players or enemies; enemies cannot body-block players either.
- They **do not initiate combat without player involvement**.
- Player attacks (including a damaging Vector Break hit) can engage companions. A non-damaging/non-hitting mobility dash does not.
- When the player is only moving, companions follow peacefully.
- If the player moves sufficiently far from an encounter, companions **disengage and return**.
- On player defeat, companions stop fighting, approach the body and **lie down beside the player**.
- Exact follow distance, leash range, damage rules and ability modifications remain unfinalized.
y
- White Havanese–Maltese dog; yellowish beard-like facial fur.
- Magic support: grants a player barrier; also planned to have suitable offensive magic (not yet specified).

## Aleksei
- Grey cat with a white chest patch and a tiny red leaf on it.
- Ranged attacks; grants an Agility buff to player.
- Inspired by his tendency to hide behind people.

## Dipsy
- Toy-like small Russian lapdog; whitish with some brown.
- Territorial personality reflected in an **armored melee fighter** role.

## Little Cato and Ms. Handsome — paired companion
- Both real-life female cats; smaller, grey/white/black with a somewhat tiger-striped pattern. Each is affectionate individually, but they hiss when close to each other.
- **One companion slot containing two cats.** Which named cat is A/B remains undecided.
- Both cats have the **same basic attack pattern and attack range**.
- Each cat claims a **melee-sized territory associated with the enemy it fights**. Territory currently grants **no combat buff**.

### Cat A — independent disruptor
- Favors a nearby enemy other than the player's focused target; can engage Elite enemies and bosses.
- Uses attacks and small occasional stuns to occupy an enemy while the enemy continues trying to reach the player.
- When engaging a grouped enemy, may attack nearby members of that engaged group; when isolated, attacks only the individual.
- Cat A's territory **follows its current target**; when the target dies, its territory ends and Cat A picks another target.
- Bosses and Elites resist stuns.

### Cat B — player-focused attacker
- Attacks an enemy marked by the mouse, or the **first enemy hit by the player's melee attack**.
- Establishes territory around the player-focused enemy.
- Damage type differentiation and upgrades are **undecided**.

### Catfight — joint effect
- **Normal trigger:** the **two territory circles touch or overlap** while the catfight ability is available. This supersedes the earlier single-cat boundary-crossing concept.
- Cats begin fighting each other roughly at the center of the effect; their fight damages nearby enemies in an **AoE with radius twice a territory radius** (example only).
- Catfight cooldown: **15 seconds** (initial tuning).
- During cooldown, both cats continue their respective independent attacks; overlap does not trigger another catfight. Whether an already-active overlap automatically triggers at cooldown expiry is **undecided**.
- **One enemy exception:** both cats can engage the same enemy. A suggested special delay is **7.5 seconds**, starting only when both cats are actively engaged with it; this is initially half the 15-second catfight cooldown.
- Players can intentionally bring targets/territories together using push and pull abilities.
- Catfight damage frequency/type/duration, visuals and whether AoE hits through walls remain **undecided**.
- The older buff from standing in or striking enemies inside a territory has been **removed for now**, including its ranged-hit lingering effect.