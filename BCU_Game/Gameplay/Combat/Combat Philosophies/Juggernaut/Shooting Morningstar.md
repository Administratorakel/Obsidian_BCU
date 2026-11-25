[[Juggernaut]]
## Weapon Classification

- **Class:** Juggernaut
- **Damage Type:** Physical / Magical
- **Weapon Identity:** Battlefield Manipulation & Gravitational Influence
- **Weapon Structure:** Chained morningstar with retractable spikes.

## Core Weapon Philosophy

The Shooting Morningstar specializes in manipulating enemy positions through kinetic and gravitational forces.

Unlike conventional weapons, the Shooting Morningstar can involuntarily reposition certain elites and bosses without necessarily interrupting their ongoing actions.

Its combat identity revolves around:

- Gathering and spreading enemies.
- Directional enemy displacement.
- Manipulating enemy positioning through stance transitions.
- Reducing enemy armor.
- Utilizing terrain collisions to amplify damage.
- Gravitational battlefield control through Weapon Mastery.

Normal attacks primarily reposition enemies, while abilities and Vector Break can additionally manipulate the player's position.

---

## Normal Attacks

All three stances share the same general normal attack animation sequence. The primary difference is the configuration of the Morningstar's retractable spikes.

Individual normal attacks may feature different forms of displacement, including pushing, pulling, gathering and directional repositioning.

Not every normal attack necessarily displaces enemies.

### Default Stance

- Spikes are partially extended.
- Balanced contact area.
- Repositions enemies according to the individual attack animation.
- May feature forward, sideways or downward displacement.

### Wide Stance

- Spikes are fully extended.
- Increased attack coverage.
- Specializes in manipulating larger groups of enemies.
- Wider contact area allows more enemies to be caught by the weapon.

### Focused Stance

- Spikes are fully retracted.
- Smaller contact area.
- Concentrates kinetic force into precise blunt impacts.
- Normal attacks have a chance to apply armor reduction.
- Specializes in weakening individual enemies.

The ball remains the primary source of damage. Separate damage calculations for individual spikes are not required.

---

## Shooting Star

The first normal attack of the Shooting Morningstar's attack loop is named **Shooting Star**.

### Default

The ball is launched toward the enemy, dealing damage and knocking the enemy backward.

### Wide

The ball is launched with extended spikes, damaging and pushing enemies across a wider contact area.

### Focused

The ball is launched with fully retracted spikes.

Upon hitting an enemy:

- The player is pulled toward the enemy.
- The concentrated kinetic impact deals damage.
- One armor-reduction stack is guaranteed to be applied.

This attack represents an exception to the general philosophy of normal attacks primarily repositioning enemies rather than the player.

---

## Armor Reduction

The Shooting Morningstar can weaken enemy armor through concentrated kinetic and gravitational forces.

### Application Sources

- Focused Shooting Star: Guaranteed application.
- Other Focused normal attacks: Chance-based application.
- Gravitational Impact: Guaranteed application.
- Gravitational Field: Periodic application.

### Rules

- All Shooting Morningstar armor-reduction sources apply the same debuff.
- Maximum of four stacks, provisionally.
- Armor reduction per stack remains undecided.
- Stack duration remains undecided.
- Application chance of other Focused normal attacks remains undecided.

The Shooting Morningstar's armor reduction may interact with other armor-reduction sources.

Reaching 100% armor reduction through multiple sources should remain possible, although the Shooting Morningstar alone does not necessarily need to achieve this.

---

## Enemy Displacement

The Shooting Morningstar specializes in involuntary enemy movement.

### Normal Enemies

Normal enemies can be fully affected by the weapon's displacement mechanics.

Depending on the attack, enemies may be:

- Pushed.
- Pulled.
- Gathered.
- Compressed.
- Spread apart.
- Repositioned sideways or in other directions.

### Elites and Bosses

The Shooting Morningstar can involuntarily move elites and bosses that would otherwise resist conventional knockback.

However:

- Displacement strength may be significantly reduced.
- Enemies may continue walking or performing actions while being displaced.
- Stance-transition effects may stagger them instead of fully dragging or compressing them.
- Individual enemies may have different levels of displacement resistance.

Displacement does not inherently cause action interruption, stun or knockdown unless explicitly defined by the attack.

---

## Terrain Collision Damage

Selected displacement attacks and abilities can deal additional damage by forcing enemies against terrain.

### Rules

- An enemy receives double damage when a compatible displacement attack forces it into terrain.
- This represents the initial kinetic impact and the subsequent collision.
- Both Wide-to-Focused and Focused-to-Wide stance transitions support terrain collision damage.
- Not every displacement attack necessarily supports terrain collision damage.

Compatible attacks and exact collision behavior will be defined individually.

---

## Stance Transition — Spike Manipulation

The Shooting Morningstar possesses a unique interaction with customized normal attack loops unlocked through its weapon-specific Stance Combo Book.

The current normal attack checks the stance classification of the following attack.

When transitioning directly between Wide and Focused, the Morningstar changes its spike configuration at the end of the current attack animation, creating additional damage and displacement.

### Wide → Focused

The extended spikes retract into the ball.

- Caught enemies are compressed toward a single location.
- The compression deals additional damage.
- Normal enemies are pulled together.
- Elites and bosses may stagger or experience reduced involuntary movement.
- Compatible terrain collisions deal double transition damage.

### Focused → Wide

The retracted spikes extend outward.

- Nearby enemies caught by the extending spikes are pushed outward.
- The extension deals additional damage.
- Transition damage is slightly higher than Wide-to-Focused transition damage.
- Elites and bosses may stagger or experience reduced involuntary movement.
- Compatible terrain collisions deal double transition damage.

### Transition Overview

|Current Stance|Following Stance|Additional Effect|
|---|---|---|
|Default|Default|None|
|Default|Wide|None|
|Default|Focused|None|
|Wide|Default|None|
|Wide|Wide|None|
|Wide|Focused|Compression + Damage|
|Focused|Default|None|
|Focused|Wide|Expansion + Damage|
|Focused|Focused|None|

### Transition Rules

- Transition damage and displacement occur at the end of the current attack animation.
- The effect is synchronized with the spikes extending or retracting.
- Cancelling the attack before the transition occurs forfeits both transition damage and displacement.
- Enemies do not need to have been hit by the original normal attack to be affected by the transition.
- Additional enemies caught by the changing spike configuration can also be damaged and displaced.
- Every normal attack retains its inherent effects independently of stance-transition effects.
- Transitions involving Default do not produce additional damage or displacement.

The Stance Combo Book allows players to create customized attack loops that alternate between compressing and spreading enemies.

---

## Vector Break

The Shooting Morningstar's Vector Break combines enemy displacement, offensive impact and player repositioning.

### Execution

1. The player swings the Morningstar toward the ground in front of them.
2. The Morningstar takes on its Wide configuration with extended energy spikes.
3. The ground impact damages and knocks down enemies caught within its coverage.
4. The player utilizes the weapon's energy and position to swing through an elevated arc around the ball.
5. The player lands behind the affected enemies.

### Weapon Mastery Interaction

The ground impact activates Gravitational Impact and Gravitational Field once the respective mastery milestones have been unlocked.

Exact animation, movement distance, trajectory and damage values remain undecided.

---

## Ability Concept — Pull

_Provisional ability concept._

The Shooting Morningstar launches its ball with retracted spikes toward the ground.

### Execution

1. The player swings the ball overhead and launches it toward the ground.
2. The ground impact launches nearby enemies into the air.
3. The ball rebounds from the ground.
4. The player whips the chain, raising the ball to approximately the height of the airborne enemies.
5. The spikes extend.
6. A large magical spiked shell forms around the ball.
7. The player retracts the chain, pulling caught enemies toward their position.

The ability combines physical and magical damage with enemy gathering.

The ground impact also qualifies for the Shooting Morningstar's gravitational mastery effects.

---

# Weapon Mastery

The Shooting Morningstar develops gravitational properties through its major Weapon Mastery milestones.

These mechanics are available independently of the player's chosen stance or customized normal attack loop.

---

## Level 50 — Gravitational Impact

Whenever the Morningstar's ball strikes the ground, gravitational force is released around the impact location.

### Activation Sources

- Normal attacks.
- Abilities.
- Vector Break.

Every combat-related ground impact qualifies, regardless of stance.

### Effects

- Nearby normal enemies are pulled toward the impact location.
- Enemies do not need to be directly struck by the ball to be affected.
- Affected enemies receive one armor-reduction stack.
- The armor-reduction stack is identical to the stack applied by Focused normal attacks.
- The gravitational pull itself does not deal additional damage.

### Purpose

Gravitational Impact strengthens the Shooting Morningstar's enemy-gathering capabilities and allows all three stances to apply armor reduction through ground impacts.

---

## Level 100 — Gravitational Field

Every ground impact additionally creates a temporary Gravitational Field centered on the impact location.

Gravitational Field does not replace Gravitational Impact.

### Properties

|Property|Value|
|---|---|
|Duration|1.5 seconds|
|Damage Type|Magical|
|Damage Interval|0.25 seconds|
|Maximum Damage Ticks per Field|6|
|Armor Reduction Interval|1 second|
|Additional Armor Stacks per Full Field Exposure|1|
|Multiple Fields|Allowed|
|Overlapping Effect Stacking|Disabled|

### Effects on Normal Enemies

- Continuously pulled toward the center of the field.
- Receive periodic magical damage.
- Receive one armor-reduction stack per second of exposure.

### Effects on Elites and Bosses

- Slowed instead of continuously pulled.
- Receive periodic magical damage.
- Receive armor-reduction stacks under the same timing rules.

### Overlapping Gravitational Fields

Multiple Gravitational Fields can coexist.

When an enemy is affected by multiple overlapping fields:

- The enemy is pulled toward the nearest active field's center.
- Gravitational pulling strength does not stack.
- Slowing strength does not stack.
- Magical damage does not stack.
- Armor-reduction application frequency does not increase.
- Damage and armor-reduction timers are shared across overlapping fields.
- Switching between overlapping fields does not reset these timers.
- Switching fields cannot generate additional damage ticks or armor-reduction applications.

Enemies entering an existing Gravitational Field are also affected.

### Single Ground Impact Timeline

Assuming an enemy is affected by the initial impact and remains inside the field for its entire duration:

|Time|Gravitational Effect|
|---|---|
|0.00s|Gravitational Impact + Armor Reduction|
|0.25s|Magical Damage|
|0.50s|Magical Damage|
|0.75s|Magical Damage|
|1.00s|Magical Damage + Armor Reduction|
|1.25s|Magical Damage|
|1.50s|Magical Damage + Field Expiration|

A single ground impact can therefore apply:

- One initial gravitational displacement.
- Six magical damage ticks.
- Two armor-reduction stacks.
- Continuous gravitational manipulation for 1.5 seconds.

---

## Weapon Identity Summary

The Shooting Morningstar controls the battlefield by manipulating enemy positioning rather than relying exclusively on conventional crowd control.

Its retractable spikes allow the player to gather, compress and spread enemies through customized attack loops, while concentrated kinetic impacts weaken enemy armor.

With increasing Weapon Mastery, the Morningstar develops gravitational properties that turn ground impacts into temporary areas of battlefield control.

Its ability to involuntarily reposition even elites and bosses distinguishes it from conventional displacement-oriented weapons.

---

## Remaining Design Decisions

- Individual normal attack animations.
- Individual normal attack displacement directions.
- Damage distribution between physical and magical attacks.
- Armor reduction per stack.
- Armor-reduction duration and application chances.
- Final maximum armor-reduction stacks.
- Transition damage multipliers.
- Transition displacement strength.
- Terrain collision compatibility per attack.
- Gravitational Impact radius and pulling strength.
- Gravitational Field radius.
- Gravitational Field damage per tick.
- Gravitational Field pulling and slowing strength.
- Gravitational Impact behavior against elites and bosses.
- Timer behavior when enemies completely leave all active fields and subsequently reenter.
- Final Vector Break animation and movement properties.
- Final Pull ability execution.

**Design Status:** Core weapon identity and Level 50/100 Weapon Mastery mechanics finalized. Numerical balancing, individual animations and remaining implementation details are intentionally deferred.