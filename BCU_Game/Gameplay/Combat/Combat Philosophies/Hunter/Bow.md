[[Hunter]]

# Bow — Weapon Identity

**Status:** Core identity established; balancing pending  
**Combat Identity:** Hunter's Pace  
**Damage Type:** Physical / Magical  
**Combat Philosophy:** Hunter

## 1. Weapon Identity

The Bow is a ranged weapon specializing in precision, positioning, and movement speed gained through successful attacks.

Its defining mechanic, **Hunter's Pace**, rewards successful arrow hits with stacking movement-speed bonuses.

Unlike Dual Guns, which emphasize mobile firing, the Bow attacks from a stationary position and uses accumulated movement speed to reposition between attacks.

**Design Philosophy:** Successful attacks reward the player with greater mobility, allowing them to reposition efficiently before their next attack.

## 2. Normal Attacks

Every normal Bow attack consists of two animation phases:

1. **Arrow Preparation:** Taking an arrow and positioning it against the bowstring.
2. **Drawing & Aiming:** Pulling the bowstring, aiming, and releasing the arrow.

These phases are independently affected by attack stances.

### Stance Mechanics

| Stance   |Arrow Preparation|Drawing & Aiming|Arrows Fired|
|---|---|---|---|
| Standard |Normal speed|Normal speed|1|
| Focused  |50% faster|Normal speed|1|
| Wide     |Normal speed|50% slower|2|

**All values are provisional.**

### Standard Stance

- Balanced preparation and aiming speeds.
- Fires one arrow per normal attack.
- Provides consistent ranged damage.

### Focused Stance

- Arrow preparation is 50% faster.
- Drawing and aiming speed remains unchanged.
- Fires one arrow per attack.
- Specializes in reducing preparation time between shots.

### Wide Stance

- Arrow preparation speed remains unchanged.
- Drawing and aiming are 50% slower.
- Fires two arrows with a very slight spread.
- Both arrows can hit enemies within a tightly grouped formation.
- Arrows do not require a successful hit to complete the attack.

Weapon Mastery can further improve preparation speed, drawing speed, and the number of additional arrows.

## 3. Movement During Attacks

**Current decision: Normal Bow attacks are stationary.**

- The player cannot move during arrow preparation.
- The player cannot move during drawing and aiming.
- Movement resumes after the attack finishes.

Movement during arrow preparation was considered but postponed to avoid unnecessary complexity in BCU's MMORPG-style combat.

This decision can be revisited during Bow implementation.

## 4. Hunter's Pace

Hunter's Pace is the Bow's defining passive combat mechanic.

### Stack Generation

Every individual arrow that successfully hits an enemy grants one Hunter's Pace stack.

- Maximum: **4 stacks**.
- Each successful arrow hit generates one stack.
- Multiple arrows hitting the same enemy can generate multiple stacks.
- Wide Stance can generate multiple stacks from one attack.
- Missing an attack does not generate stacks.
- Weapon Mastery can improve the movement-speed bonus.

### Stack Expiration

- All accumulated stacks expire simultaneously.
- Exact stack duration remains undecided.
- Whether successful hits refresh the shared expiration timer is undecided.

### Movement Speed

Each Hunter's Pace stack increases the player's movement speed.

The exact movement-speed increase per stack will be determined during balancing.

### Combat Rhythm

1. Fire arrows at enemies.
2. Successful hits generate Hunter's Pace stacks.
3. Accumulated stacks increase movement speed.
4. Reposition between stationary attacks.
5. Continue attacking to maintain mobility.

**Hunter's Pace rewards accuracy with repositioning potential rather than allowing attacks while moving.**

## 5. Weapon Mastery

Bow Weapon Mastery improves the weapon's existing characteristics.

### General Progression

Potential improvements include:

- Faster arrow preparation.
- Faster drawing and aiming.
- Additional arrows.
- Increased Hunter's Pace movement-speed bonuses.

Exact unlock levels and numerical improvements remain undecided.

### Level 50 / 100 — Homing Arrows

Homing arrows are planned as higher-level Weapon Mastery enhancements.

- Arrows gain homing capabilities.
- Homing improves the reliability of attacks, particularly Wide Stance.
- Level 50 and Level 100 are intended mastery milestones for homing improvements.
- Exact homing strength and progression remain undecided.

The homing effect should complement the Bow's precision identity rather than completely eliminate the importance of positioning.

### Additional Mastery Concept

An earlier Bow Mastery concept proposed increased damage at longer distances.

This remains a separate potential Mastery bonus and has not yet been finalized.

## 6. Vector Break / Bulletjump

Previously established characteristics:

- Increased movement speed.
- Significantly increased travel distance.

Exact interactions between Vector Break and Hunter's Pace remain undecided.

## 7. Stance Synergies

The three stances provide different approaches to generating Hunter's Pace.

| Stance   |Hunter's Pace Interaction|
|---|---|
| Standard |Consistent single-arrow stack generation|
| Focused  |More frequent opportunities to land arrows|
| Wide     |Multiple potential stacks from a single attack|

This creates different combat rhythms without requiring separate resources or additional inputs.

## 8. Unresolved Questions

- Exact movement-speed bonus per Hunter's Pace stack.
- Hunter's Pace stack duration.
- Whether successful hits refresh stack duration.
- Exact attack preparation and aiming animation speeds.
- Arrow spread angle in Wide Stance.
- Additional arrows gained through Weapon Mastery.
- Exact Lv 50 and Lv 100 homing improvements.
- Whether movement becomes possible during arrow preparation in the future.
- Interactions between Hunter's Pace and Vector Break.
- Exact Bow ability interpretations.

These details will be addressed during balancing and implementation.

## Core Design Principle

**The Bow rewards precision with mobility.**

Players commit to stationary ranged attacks, accumulate movement speed through successful arrow hits, and use that speed to reposition before attacking again.

Its identity is defined by the relationship between **accuracy, attack preparation, and movement**, rather than continuous mobile firing.