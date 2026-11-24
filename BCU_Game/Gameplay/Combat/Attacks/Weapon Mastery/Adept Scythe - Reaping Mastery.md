# Adept Scythe — Reaping Mastery

**Status:** Core mechanics established; balancing and ability interactions pending  
**Weapon:** Adept Scythe  
**Combat Philosophy:** Adept  
**Mechanic:** Reaping  
**Unlock:** Weapon Mastery Lv 50  
**Upgrade:** Weapon Mastery Lv 100

---

## 1. Core Concept

**Reaping** is a weapon-specific stacking mechanic that rewards the Adept Scythe for repeatedly applying Slash to enemies already suffering from maximum Slash stacks.

Unlike Slash, which is a status effect applied to enemies, **Reaping stacks accumulate on the player**.

Reaping stacks can accumulate indefinitely and are spent to enhance selected Scythe abilities.

**Design Philosophy:** Repeatedly exploiting wounded enemies allows the player to accumulate supernatural power, which can be invested into stronger abilities.

Reaping's damage scaling uses diminishing returns to prevent excessive damage against enemies with very high HP.

---

## 2. Reaping Activation

Reaping becomes available at **Adept Scythe Mastery Lv 50**.

### Activation Requirements

- At least one enemy must have **6 Slash stacks applied by the player**.
    
- Reaping activates automatically when this condition is met.
    
- No additional player input is required.
    
- Only one qualifying enemy is necessary to activate Reaping.
    
- Multiple enemies can contribute to Reaping simultaneously.
    

### Stack Generation

Once an enemy has 6 Slash stacks, additional successful Slash procs against that enemy generate Reaping stacks.

- Each additional qualifying Slash proc grants **1 Reaping stack**.
    
- Reaping counts the number of Slash procs, not their damage.
    
- The enemy's Slash stacks remain capped at 6.
    
- Reaping stacks accumulate on the player.
    
- Reaping has no maximum stack count.
    

### Example

An enemy already has 6 Slash stacks.

|Action|Reaping Stacks|
|---|---|
|Enemy reaches 6 Slash stacks|0|
|Additional Slash proc|1|
|Another Slash proc|2|
|Three additional Slash procs|5|
|Ten additional Slash procs|15|

Reaping does not increase Slash's maximum stack count.

---

## 3. Multiple Enemies

Reaping can accumulate through multiple enemies simultaneously.

As long as at least one enemy has 6 Slash stacks applied by the player, Reaping remains active.

Each qualifying Slash proc is counted once per enemy.

### Example

Three enemies each have 6 Slash stacks.

An attack successfully applies one additional Slash proc to each enemy.

**Result: 3 Reaping stacks gained.**

A single Slash proc cannot generate multiple Reaping stacks against the same enemy.

Separate qualifying procs can generate additional stacks.

---

## 4. Weapon Mastery Progression

Reaping is enhanced at two Weapon Mastery milestones.

|Mastery Level|Effect|Maximum Damage Enhancement|
|---|---|---|
|**Lv 50**|Reaping I|+25%|
|**Lv 100**|Reaping II|+50%|

### Lv 50 — Reaping I

Unlocks the Reaping system.

- Allows accumulation of Reaping stacks.
    
- Enables selected abilities to consume Reaping stacks.
    
- Consumed stacks enhance ability damage.
    
- Maximum damage enhancement: **+25%**.
    
- Damage scaling uses diminishing returns.
    

### Lv 100 — Reaping II

Improves the existing Reaping mechanic.

- Maximum damage enhancement increases to **+50%**.
    
- Reaping accumulation remains unlimited.
    
- Ability enhancements continue using diminishing returns.
    
- Exact progression curve remains undecided.
    

The damage enhancement is rounded upward.

---

## 5. Damage Scaling

Reaping stacks do not automatically increase:

- Normal attack damage.
    
- Enhanced normal attack damage.
    
- Slash's damage-over-time effect.
    
- Every ability's damage.
    

Instead, **selected abilities receive damage enhancements when they consume Reaping stacks**.

### Scaling Rules

- Damage enhancement depends on the number of Reaping stacks consumed.
    
- More consumed stacks provide greater enhancement.
    
- Diminishing returns prevent unrestricted damage growth.
    
- Lv 50 maximum enhancement: +25%.
    
- Lv 100 maximum enhancement: +50%.
    
- Exact scaling formulas remain undecided.
    

The stack counter itself has no maximum.

---

## 6. Ability Consumption

Selected Adept Scythe abilities can consume Reaping stacks to enhance their effects.

### Consumption Rules

- Different abilities may consume different amounts of Reaping stacks.
    
- Some abilities may consume all available stacks.
    
- Other abilities may consume a fixed amount or proportion.
    
- The number of stacks consumed determines the enhancement.
    
- Unconsumed stacks remain available for subsequent abilities.
    
- Exact consumption rules will be established during individual ability design.
    

### Example

The player has **100 Reaping stacks**.

An ability consumes **20 stacks**.

- The ability's enhancement is calculated using 20 stacks.
    
- The player retains 80 Reaping stacks.
    
- The enhancement follows the applicable Mastery damage cap.
    

The ability does not calculate its bonus from the original 100 stacks.

### Ability-Specific Scaling

Individual abilities may eventually use different scaling curves or consumption requirements.

These decisions are postponed until their basic versions have been designed.

---

## 7. Reaping Duration and Expiration

Reaping is connected to the presence of fully stacked Slash on enemies.

### Active State

Reaping remains active while at least one qualifying enemy has 6 Slash stacks.

### Expiration

When no qualifying enemy remains:

- Reaping begins a **5-second expiration countdown**.
    
- Existing Reaping stacks remain available during that period.
    
- If no new qualifying enemy appears before expiration, all accumulated Reaping stacks disappear.
    

### Reactivation

If the player establishes 6 Slash stacks on another enemy before the Reaping timer expires:

- Reaping becomes active again.
    
- Existing Reaping stacks are preserved.
    
- The expiration countdown is cancelled.
    
- Reaping accumulation can continue.
    

This allows players to carry Reaping between enemies when they maintain sufficient combat pressure.

---

## 8. Weapon Switching

**Switching away from the Adept Scythe immediately removes all accumulated Reaping stacks.**

Reaping cannot be stored for use with other weapons.

Re-equipping the Scythe does not restore previously accumulated stacks.

---

## 9. Visual Identity

Activating Reaping may alter the Scythe's appearance or attack behavior.

Potential effects include:

- Increasing the Stability blade's size.
    
- Increasing attack speed.
    
- Additional supernatural visual effects as Reaping accumulates.
    

**These are possibilities, not established mechanics.**

Any visual progression should remain readable even when Reaping stacks become extremely numerous.

---

## 10. Relationship with Slash

Reaping interacts with the existing Slash status without replacing its fundamental mechanics.

### Slash Properties

- Physical damage-over-time effect.
    
- Partially ignores Physical Defense.
    
- Maximum of 6 stacks.
    
- Shared 5-second expiration timer.
    
- Additional Slash applications refresh the timer.
    
- Each stack increases Slash's DoT damage equally.
    

### Reaping Interaction

- Reaping activates when an enemy reaches 6 Slash stacks applied by the player.
    
- Additional Slash procs generate Reaping stacks.
    
- Reaping does not increase Slash's damage or maximum stacks.
    
- Reaping does not automatically consume the enemy's Slash stacks.
    
- Slash's elemental combinations remain separate mechanics.
    

### Important Design Revision

An earlier concept proposed consuming all 6 Slash stacks to trigger the Scythe's Mastery enhancement.

**That concept has been replaced by Reaping.**

The current system preserves maximum Slash stacks on enemies while additional Slash procs generate player-side Reaping stacks.

---

## 11. Unresolved Mechanics

The following details remain undecided:

- Exact diminishing-returns formula.
    
- Exact rounding behavior for percentage bonuses.
    
- Reaping consumption amounts for individual abilities.
    
- Whether different abilities use different scaling curves.
    
- Which abilities can consume Reaping.
    
- Whether consuming Reaping also changes an ability's range, area, movement, or other characteristics.
    
- Potential blade-size and attack-speed modifications.
    
- Exact visual representation of Reaping stacks.
    
- Interactions with future Scythe abilities, including Domain.
    

These decisions will be made during ability development and balancing.

---

## 12. Core Design Principle

**Reaping transforms repeated Slash applications into an unlimited, player-held resource that empowers selected Scythe abilities.**

The mechanic rewards sustained combat against heavily wounded enemies without allowing damage to scale indefinitely.

Players can accumulate Reaping through multiple enemies, preserve stacks by maintaining fully stacked Slash, and decide how much accumulated power to invest in their abilities.

**Slash creates the opportunity. Reaping accumulates the power. Abilities release it.**