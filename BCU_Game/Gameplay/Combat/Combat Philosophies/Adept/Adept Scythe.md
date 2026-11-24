[[Adept]]
# Adept Scythe — Weapon Identity

**Status:** Core identity established; balancing and ability design pending  
**Combat Identity:** Attack Steering  
**Combat Philosophy:** Adept  
**Weapon Type:** Magical / Stability-based

---
## 1. Core Identity

The Adept Scythe specializes in **Attack Steering**, allowing players to enhance ongoing normal attacks through directional input.

Its defining characteristics are:

- Weak basic attacks that can be enhanced using Stability.
- Directional enhancements that modify attack damage, reach, blade shape, and movement.
- Short directional dashes accompanying enhanced attacks.
- Fluid, supernatural attack animations.
- A Stability blade capable of changing shape or detaching from its handle.
- Directional enhancement mechanics shared across the three attack stances.
- Selected abilities that also support Attack Steering.

**Design Philosophy:** The Scythe allows players to invest Stability into directional attack enhancements, combining supernatural blade manipulation with deliberate positioning.

Unlike weapons that primarily reward consecutive attacks or precise timing, the Scythe rewards directional control and Stability management.

## 2. Weapon Construction

The Scythe possesses a physical handle and a blade formed from Stability.

The Stability blade can:

- Change its shape during attacks.
- Expand or extend beyond its basic dimensions.
- Follow unusual cutting trajectories.
- Detach from the handle during selected animations.
- Move independently during a very small number of abilities.

Blade detachment is not required for normal attacks.

The Scythe's conventional attack combinations can be performed entirely with its blade attached.


## 3. Normal Attack Combinations

The Scythe uses three stances:

1. **Default**
2. **Wide**
3. **Focused**

Each stance possesses a normal attack combination of up to seven attacks.

### Basic Attacks

- Basic attacks use conventional Scythe animations.
- The Stability blade retains its basic shape.
- The blade remains attached to its handle.
- The player can complete an entire seven-hit combination without directional enhancement.
- Basic attack damage is relatively weak.
- Basic attacks do not consume Stability through Attack Steering.

### Enhanced Attacks

Directional input can enhance a normal attack.

Enhancements:

- Increase or modify attack damage.
- Modify attack reach and coverage.
- Change the Stability blade's shape and movement.
- Move the player through a short directional dash.
- Consume Stability.
- Preserve the normal attack combination's progression.

For example:

**Attack 1 → Enhanced Attack 2 (Left) → Attack 3 → Enhanced Attack 4 (Forward)**

Attack Steering enhances the current attack rather than inserting an additional attack into the combination.

All enhanced normal attacks share the same damage value and Stability cost, regardless of stance, direction, or combo position.

Exact numerical values remain undecided.

---

## 4. Directional Input

Attack Steering supports four directional inputs.

|Input|Enhancement Direction|
|---|---|
|W|Forward|
|A|Left|
|S|Backward|
|D|Right|

Diagonal input behavior remains to be determined.

### Input Behavior

- Holding a directional input is sufficient to activate Attack Steering.
- Players do not need to release and press the directional button again.
- Players can enhance consecutive attacks by continuously holding a direction.
- Each attack can receive only one directional enhancement.
- Once an enhancement activates, its direction is locked.
- Changing directional input afterward does not modify the active enhancement.
- The next normal attack can use a different enhancement direction.

### Directional Reference

**Current behavior:**

- Untargeted attacks use camera-relative directional input.
- Targeted attacks use player-facing-relative directional input.

**Future feature:**

Players will be able to toggle directional input between:

- Camera-relative controls.
- Player-facing-relative controls.

The exact configuration and implementation of this toggle remain open.


## 5. Attack Steering Timing

Attack Steering uses an enhancement window within each normal attack animation.

### Enhancement Window

|Animation Progress|Behavior|
|---|---|
|0–20%|Initial preparation and opportunity to release directional input|
|21–100%|Directional enhancement can activate|

**The 21% threshold is provisional and intended for initial testing.**

### Input Examples

**Example A — Holding Forward**

1. Player begins a normal attack while holding W.
2. The attack reaches 21% animation progress.
3. Forward enhancement activates automatically.
4. Stability is consumed.
5. The enhanced slash executes.
6. The player performs the corresponding directional dash.

**Example B — Releasing Input**

1. Player begins an attack while holding W.
2. Player releases W before the enhancement window.
3. The attack continues normally without enhancement.

**Example C — Delayed Directional Input**

1. Player begins an attack without directional input.
2. The attack reaches 60% animation progress.
3. Player presses A.
4. Left enhancement activates immediately.

**Example D — Changing Direction**

1. Player activates a forward enhancement.
2. Player changes input from W to D.
3. The attack remains forward-enhanced.
4. The next attack can use right enhancement.

The enhanced attack occurs nearly immediately after enhancement activation, with the dash following naturally.

Exact animation blending and damage-frame timing remain implementation details.

## 6. Targeting and Automatic Attacking

Attack Steering respects BCU's existing targeted and untargeted combat behavior.

### Untargeted Combat

- Normal attacks follow the player's usual attack direction.
- Directional enhancements use camera-relative input by default.
- If no direction is held, the player performs a basic attack.
- Directional enhancements do not require a selected target.

### Targeted Combat — Approaching

When the player has selected an enemy but has not yet entered the targeted attacking state:

- Movement input retains its normal movement function.
- Holding A, for example, moves the player left.
- Directional input does not automatically trigger Attack Steering while merely approaching.
- Pressing the normal attack button can initiate an ordinary attack in the player's current facing direction.

### Targeted Combat — Attacking

Once the character reaches the targeted automatic-attacking state:

- Attacking receives higher priority than movement.
- Directional inputs can enhance ongoing normal attacks.
- Enhancement directions are interpreted relative to the character's facing direction.
- Sideways enhancements preserve the character's orientation toward the selected target.

This allows players to circle or reposition around enemies while continuing their attacks.

## 7. Enhanced Attack Movement

Each enhanced attack performs a short directional dash.

### Dash Properties

- Forward, backward, left, and right enhancements have the same base travel distance.
- All three stances share the same base dash distance.
- Dash duration differs by stance.
- Dash movement occurs immediately as part of the enhanced attack.
- The enhanced slash occurs almost immediately, followed naturally by the dash.
- Dash distance may improve through Weapon Mastery.

### Stance Differences

|Stance|Dash Distance|Dash Duration|
|---|---|---|
|Default|Standard|Standard|
|Wide|Standard|Slightly longer|
|Focused|Standard|Slightly shorter|

The different dash durations create different movement speeds without changing travel distance.

### Collision Rules

- Enhanced dashes can pass through enemies.
- Environmental obstructions stop physical movement.
- The enhanced attack animation continues even when movement is blocked.
- An obstructed dash effectively executes its animation in place.

### Airborne Restriction

**Attack Steering cannot be activated while airborne.**

Only grounded attacks can initiate directional enhancements.

Interactions with abilities that cause airborne movement remain undecided.


## 8. Stance-Specific Enhancements

Each stance has its own set of shared directional enhancement animations.

### Default Stance

Balanced blade manipulation.

- Moderate attack coverage.
- Standard enhancement movement speed.
- Balanced supernatural cutting animations.

### Wide Stance

Emphasizes broad cutting trajectories.

- Larger cutting areas.
- Wider blade transformations.
- Slightly slower directional dash.
- Same enhanced attack damage and Stability cost as other stances.

### Focused Stance

Emphasizes concentrated attacks.

- More focused attack coverage.
- Narrower or more concentrated blade transformations.
- Slightly faster directional dash.
- Same enhanced attack damage and Stability cost as other stances.

### Animation Reuse

The directional enhancement animations are shared across all seven combo positions within each stance.

For example, Default Stance's left-enhanced animation is reused for attacks 1–7.

This avoids creating separate directional animations for every individual combo attack.

### Animation Count

Assuming left/right enhancement animations can share mirrored animations:

|Animation Category|Count|
|---|---|
|Default basic attacks|7|
|Wide basic attacks|7|
|Focused basic attacks|7|
|Default directional enhancements|3|
|Wide directional enhancements|3|
|Focused directional enhancements|3|
|**Total**|**30**|

The three directional enhancement animations per stance represent:

- Forward
- Backward
- Sideways (mirrored left/right)

If left and right require separate animations, the total becomes **33**.

These counts exclude abilities and other general character animations.


## 9. Stability Consumption

Attack Steering consumes Stability when an enhancement activates.

### Rules

- All enhanced normal attacks consume the same amount of Stability.
- Stability is consumed immediately upon enhancement.
- Missing an enemy does not refund Stability.
- Cancelling an enhanced attack does not refund Stability.
- Insufficient Stability prevents enhancement.
- If enhancement cannot activate, the attack continues as a basic attack.

The exact cost remains undecided.

### Combat Implications

Basic attacks provide a low-damage option without Attack Steering's additional Stability cost.

Enhanced attacks consume Stability in exchange for stronger attacks, altered blade geometry, and directional movement.

Players must decide when enhanced attacks are worth their resource cost.
## 10. Ability Interactions

**Current decision:** Selected abilities support Attack Steering.

Directional enhancement is not mandatory for every Scythe ability.

### General Rules

- All abilities continue following BCU's established cancellation rules.
- Activating an ability cancels the ongoing normal attack and its enhancement.
- Any active enhanced dash is cancelled.
- Stability already spent on the normal attack enhancement remains consumed.
- Selected abilities may receive directional enhancements.
- Directional ability enhancements provisionally use the same 21% activation threshold.
- Additional Stability costs depend on the individual ability.

### Individual Ability Design

Directional effects will be determined after each ability's core mechanics have been established.

Potential interactions include changes to:

- Attack trajectories.
- Movement.
- Blade shape.
- Attack coverage.
- Enemy positioning.

These are possibilities rather than established universal effects.

### Independent Blade Abilities

A very small number of abilities may allow the Stability blade to detach and continue attacking independently.

The Scythe's **Domain ability** is a potential candidate.


## 12. Future Weapon Mastery Improvements

Potential Scythe Mastery improvements include:

- Increased directional dash distance.
- Enhanced Slash effects at Levels 50 and 100.
- Improvements to existing Attack Steering characteristics.

Exact progression and balancing remain undecided.

## 13. Remaining Design Questions

### Normal Attack System
- Exact Stability cost per enhanced attack.
- Exact damage values for basic and enhanced attacks.
- Exact attack reach and blade geometry.
- Diagonal directional input behavior.
- Implementation of the camera-relative/player-facing-relative toggle.
- Animation blending when enhancement activates late.
- Behavior when an attack's damage frame has already passed.

### Abilities
- Which abilities support Attack Steering.
- Directional effects of individual abilities.
- Additional Stability costs for selected ability enhancements.
- Independent Stability blade behavior.
- Possible Domain interactions.

### Weapon Mastery
- Mastery progression for enhanced dash distance.
- Slash stack generation and consumption details.

---

## 14. Core Design Principle

**The Adept Scythe transforms ordinary attacks into supernatural, directionally enhanced strikes.**

Basic attacks are relatively weak and conventional.

By investing Stability, players can enhance attacks with altered blade shapes, modified damage and reach, and short directional dashes.

The three stances provide different combat styles while sharing a consistent Attack Steering system.

**The weapon's depth comes from controlling how and when attacks are enhanced, rather than introducing additional resources or complicated combo inputs.**




For Lv 50/100 buff, check: [[Adept Scythe - Reaping Mastery]]
