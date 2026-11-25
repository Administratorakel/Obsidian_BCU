
**Design Status:** Core weapon identity established  
**Weapon Identity:** Counter Arc (provisional name)  
**Combat Philosophy:** Timing, anticipation, positioning and retaliation  
**Damage Type:** Physical  
**Combat Style:** Deliberate attacks with reactive defensive and offensive mechanics

---

## 1. Core Weapon Identity

The Odachi specializes in deliberately timed counters that transform incoming enemy attacks into offensive opportunities.

Unlike weapons that generate and consume weapon-specific stacks, the Odachi rewards the player's understanding of enemy attack patterns, positioning and their own normal attack loop.

Its defining characteristics are:

- Slower, deliberate normal attacks.
- Complete negation of successfully countered attacks.
- Retaliation damage scaling with incoming damage.
- Enhanced abilities through successful counters.
- Stance-dependent counter properties.
- Attack loop preservation through successful counters.
- Expanded counter capabilities through Weapon Mastery.
- Meaningful interaction with customized attack loops.

The Odachi has three methods of countering:

1. Ordinary abilities.
2. Reversal Strike.
3. Vector Break.

Normal attacks themselves do not automatically counter incoming attacks.

---

## 2. General Counter Mechanics

### Counter Activation

All three counter methods initiate a counter window immediately upon pressing their respective activation button.

The counter window is divided into two stages.

|Counter Stage|Duration|
|---|--:|
|Initial Counter Window|1 second|
|Additional Counter Window|125 ms (⅛ second)|

Both values are provisional.

### Initial Counter Window

- Begins immediately upon button press.
- Allows the player to counter an incoming eligible attack.
- If no attack is countered, the window expires normally.
- The first successfully countered attack immediately replaces the remaining initial counter window with the additional counter window.

### Additional Counter Window

- Begins at the exact moment the first successful counter is registered.
- Lasts 125 ms.
- Further eligible incoming attacks can be countered during this window.
- Additional successful counters do not reset or extend its duration.
- Countering multiple attacks increases the resulting counter benefits.
- Retaliation occurs after the additional counter window closes, where applicable.

This system rewards precise timing while allowing the Odachi to effectively counter multiple enemies attacking within a short period.

### Damage and Effect Negation

A successfully countered attack completely negates:

- Incoming damage.
- Status effects.
- Knockback.
- Other associated secondary effects.

### Counter Direction

- Counters only protect the player against attacks coming from the front.
- Attacks coming from behind cannot be countered.
- Counter angles may vary depending on the interrupted normal attack's stance classification.
- Exact counter angles remain undecided.

### Multiple Counter Scaling

All three counter methods receive greater benefits when multiple attacks are successfully countered within the same counter window.

|Counter Method|Benefit|
|---|---|
|Ordinary Abilities|Greater ability enhancement|
|Reversal Strike|Increased retaliation damage|
|Vector Break|Increased reflected damage per attacker|

Exact scaling formulas and potential limitations remain undecided.

---

## 3. Normal Attacks and Stance Classification

The Odachi has three normal attack stances:

- Default Stance
- Wide Stance
- Focused Stance

Each individual normal attack retains its original stance classification, even when incorporated into a customized attack loop.

When an ordinary ability or Reversal Strike interrupts a normal attack animation, it inherits the counter properties associated with that individual attack's classification.

### Default — Timing

- Longer counter window.
- Balanced counter angle.
- Balanced retaliation slash coverage and damage.

### Wide — Coverage

- Wider frontal counter angle.
- Wider Reversal Strike slash coverage.
- Particularly effective against multiple enemies.

### Focused — Retaliation

- Narrower frontal counter angle.
- Narrower Reversal Strike slash coverage.
- Significantly increased retaliation damage or ability enhancement.
- Rewards precise positioning and timing.

### Activation Outside Normal Attacks

Ordinary abilities and Reversal Strike activated outside a normal attack animation use Default counter properties.

Vector Break does not inherit stance-specific counter properties.

Exact stance modifiers remain open for balancing.

---

## 4. Stance Books and Combo Books

### Stance Books

Stance Books unlock the corresponding weapon's normal attack stance.

Potential Odachi books:

- Odachi — Default Stance Book
- Odachi — Wide Stance Book
- Odachi — Focused Stance Book

### Combo Book

**Odachi — Combo Book**

The Combo Book unlocks the ability to individualize the Odachi's normal attack loop.

- Combo Books are weapon-specific.
- Consuming one Combo Book unlocks customization of the entire attack row.
- Players can combine individual attacks from different unlocked stances.
- Individual customization slots do not require separate Combo Books.
- Each attack retains its original stance classification.

### Example Customized Attack Loop

|Attack Position|Stance Classification|Counter Enhancement|
|---|---|---|
|1|Default|Longer counter window|
|2|Wide|Wider counter angle|
|3|Focused|Stronger retaliation|
|4|Focused|Stronger retaliation|
|5|Wide|Wider counter angle|
|6|Default|Longer counter window|
|7|Focused|Stronger retaliation|

This is an illustrative combination rather than a finalized attack loop.

The Odachi particularly benefits from customized attack loops because players can deliberately arrange their preferred counter opportunities throughout their combinations.

---

## 5. Ordinary Ability Counters

Ordinary Odachi abilities provide counter opportunities immediately upon activation.

### Successful Counter

When an incoming attack is successfully countered:

- All incoming damage and associated effects are negated.
- The ability receives an enhancement.
- Countering multiple attacks increases the enhancement.
- The ability inherits the counter properties of the interrupted normal attack's stance classification.

Unlike Reversal Strike and Vector Break, ordinary ability enhancements do not inherently scale with the amount of incoming damage countered.

### Ability-Specific Enhancements

The exact enhancements will depend on the individual ability.

Potential properties include:

- Damage.
- Effectiveness.
- Duration.
- Area of effect.

These are possible design directions, not established individual ability mechanics.

### Attack Loop Continuation

Successful ability counters may allow the player to continue their previous normal attack loop.

This behavior will be evaluated individually when designing the respective abilities.

---

## 6. Reversal Strike

**Ability Type:** Odachi-specific variant of [[Precision Strike]]  
**Purpose:** Dedicated reactive counterattack

Reversal Strike allows the player to deliberately interrupt a normal attack animation to counter an incoming enemy attack.

Unlike ordinary abilities, Reversal Strike is exclusively reactive and performs no offensive action unless a counter succeeds.

### Activation Rules

- Can be activated during a normal attack animation.
- Can also be activated outside normal attacks.
- Cancels the current normal attack animation upon activation.
- Inherits the counter properties of the interrupted swing.
- Uses Default properties when activated outside normal attacks.

### Successful Counter

- Completely negates incoming damage and associated effects.
- Opens the additional 125 ms counter window.
- Accumulates successfully countered attacks.
- Performs retaliation after the additional counter window closes.
- Retaliation damage scales with incoming damage.
- Countering multiple attacks further increases retaliation damage.

Reversal Strike does not inherently apply additional crowd control or staggering effects.

### Failed Counter

If no attack is successfully countered:

- No retaliation occurs.
- No offensive slash is performed.
- The normal attack loop resets.
- The full cooldown applies.
- The Stability cost remains unchanged.

### Stability and Cooldown

|Property|Successful Counter|Failed Counter|
|---|---|---|
|Stability Cost|100%|100%|
|Cooldown|50%|100%|
|Retaliation|Yes|No|
|Attack Loop|Continues|Resets|

Successful counters do not grant a special Stability refund.

Exact Stability cost and cooldown duration remain undecided.

---

## 7. Reversal Strike — Retaliation Behavior

### Physical Retaliation Slash

Every successful Reversal Strike performs a damaging physical slash after the additional counter window closes.

- The slash can damage enemies that did not contribute to the counter.
- The slash occurs even if only ranged attacks were countered.
- Slash damage scales with successfully countered incoming damage.
- Multiple countered attacks increase retaliation damage.
- Slash coverage and damage inherit the interrupted swing's stance classification.

### Stance-Specific Retaliation

|Classification|Counter Properties|Slash Properties|
|---|---|---|
|Default|Longer counter window|Balanced damage and coverage|
|Wide|Wider counter angle|Wider slash coverage|
|Focused|Narrower counter angle|Narrower slash with significantly increased damage|

When activated outside normal attacks, Reversal Strike performs the Default variant.

### Projectile Retaliation

Successfully countered projectiles create small, bright retaliation projectiles.

- Retaliation projectiles travel toward the original attacker.
- Projectile travel is nearly instantaneous.
- Projectile color matches the equipped Odachi's weapon trail color.
- Projectiles are launched approximately halfway through the physical retaliation slash animation.
- The exact launch frame will be determined according to the animation.

### Combined Retaliation

If the player counters melee attacks and projectiles within the same counter window:

- One physical retaliation slash is performed.
- Retaliation projectiles are launched during the slash animation.
- Both forms of retaliation occur as part of the same counterattack.

The exact damage distribution between physical and projectile retaliation remains undecided.

---

## 8. Reversal Strike — Attack Loop Continuation

A successful Reversal Strike preserves the player's normal attack loop progression.

### Successful Counter

1. The player performs a normal attack.
2. Reversal Strike cancels that attack animation.
3. The interrupted attack determines Reversal Strike's counter classification.
4. The player successfully counters an incoming attack.
5. Reversal Strike performs its retaliation.
6. The next normal attack in the existing attack loop becomes available.

The interrupted attack is not repeated.

### Failed Counter

- The normal attack loop resets.
- The next normal attack begins from the first attack in the loop.

This rewards successful counter timing while preventing players from repeatedly accessing the same advantageous counter variant without progressing through their attack combination.

---

## 9. Vector Break — Counter Reflection

The Odachi's [[Vector Break]] combines directional movement with defensive countering and damage reflection.

### Movement

- The player moves in their chosen direction.
- Vector Break remains useful for repositioning even when no counter succeeds.
- A successful counter briefly interrupts movement at the exact moment the incoming attack is countered.
- A distinctive counter sound plays.
- The player subsequently resumes the remaining Vector Break movement in the original direction.

The animation, sound and precise movement interruption duration will be experimented with during development.

### Counter Properties

- Initial counter window: 1 second.
- Additional counter window: 125 ms.
- The first successful counter replaces the initial counter window.
- Additional counters do not extend the additional window.
- Counter windows are not prematurely terminated by the completion of Vector Break movement.
- Counter angles follow the orientation of the Vector Break hurtbox.
- The counter direction is not necessarily identical to the movement direction.

This allows the player to reposition backwards while countering attacks from the front, provided the hurtbox orientation supports it.

### Stance Independence

Vector Break does not inherit counter properties from the interrupted normal attack.

It retains its own dedicated counter angle, timing and retaliation properties.

---

## 10. Vector Break — Damage Reflection

Successfully countered attacks are accumulated during the counter window.

Once the additional counter window closes:

- All accumulated retaliation damage is reflected simultaneously.
- Damage is reflected toward the respective attackers.
- Reflected damage scales with incoming damage.
- Countering multiple attacks increases the reflected damage each individual attacker receives.
- Reflection has no distance restriction.

### Example

Three enemies attack the player within the same successful counter window.

All three attacks are negated.

Each attacker receives greater reflected damage than they would have received if their attack had been countered individually.

The precise formula remains undecided.

### Attack Loop Interaction

|Counter Result|Attack Loop Behavior|
|---|---|
|Successful Vector Break counter|Continue with the next normal attack|
|Unsuccessful Vector Break counter|Reset the normal attack loop|

Like Reversal Strike, Vector Break rewards successful countering by preserving combat rhythm.

---

## 11. Weapon Mastery

The Odachi's unique Weapon Mastery bonuses expand the types of attacks that can be countered rather than introducing a separate stacking mechanic.

### Base Counter Capability

The Odachi can counter eligible melee attacks.

Physical projectiles and magical attacks cannot initially be countered.

### Mastery Level 50 — Physical Projectile Counters

The Odachi gains the ability to counter physical projectiles.

- All three counter methods receive this capability.
- Incoming physical projectile damage and secondary effects are completely negated upon a successful counter.
- Reversal Strike generates retaliation projectiles.
- Vector Break reflects damage toward the attacker.
- Ordinary abilities receive their respective counter enhancements.

### Mastery Level 100 — Magical Counters

The Odachi additionally gains the ability to counter magical attacks that directly strike the player.

This capability applies to all three counter methods.

### Counter Eligibility Overview

|Attack Type|Base|Lv. 50|Lv. 100|
|---|:-:|:-:|:-:|
|Melee Attacks|Yes|Yes|Yes|
|Physical Projectiles|No|Yes|Yes|
|Direct Magical Attacks|No|No|Yes|
|Persistent Ground AoE|No|No|No|
|Environmental Damage|No|No|No|

Persistent ground-based effects and environmental hazards cannot be countered, even at maximum Weapon Mastery.

---

## 12. Counter Method Comparison

|Property|Ordinary Ability|Reversal Strike|Vector Break|
|---|:-:|:-:|:-:|
|Complete Damage Negation|Yes|Yes|Yes|
|Secondary Effect Negation|Yes|Yes|Yes|
|Initial Counter Window|1s|1s|1s|
|Additional Counter Window|125ms|125ms|125ms|
|Multiple Counter Benefits|Yes|Yes|Yes|
|Incoming Damage Scaling|No|Yes|Yes|
|Stance-Specific Properties|Yes|Yes|No|
|Ability Enhancement|Yes|No|No|
|Physical Retaliation Slash|No*|Yes|No|
|Direct Damage Reflection|No*|No|Yes|
|Directional Movement|Ability-dependent|Undecided|Yes|
|Successful Counter Preserves Attack Loop|Ability-dependent|Yes|Yes|
|Failed Counter Resets Attack Loop|Ability-dependent|Yes|Yes|
|Successful Counter Halves Cooldown|No special rule|Yes|No special rule|

_Ordinary abilities may have individual exceptions when designed._

---

## 13. Visual and Audio Identity

The Odachi should communicate successful counters clearly without making combat feel excessively interrupted.

### Counter Feedback

- Brief, precise counter impact.
- Distinctive counter sound during Vector Break.
- Potential visual indication of active counter windows.
- Clear distinction between successful and unsuccessful counter attempts.

### Vector Break Animation

- Directional movement.
- Brief movement interruption upon successful counter.
- Continuation of remaining movement afterward.
- Animation implementation remains experimental.

### Reversal Strike Animation

- Deliberate counterattack preparation.
- Powerful physical retaliation slash.
- Stance-specific slash coverage.
- Small, bright retaliation projectiles matching the weapon's trail color.
- Projectile release synchronized with the slash animation.

The visual presentation of counters will be developed alongside the weapon's animations.

---

## 14. Intended Combat Rhythm

**Normal Attack → Anticipate Incoming Attack → Counter → Retaliate → Continue Attack Loop**

The player is rewarded for:

- Understanding enemy attack patterns.
- Maintaining appropriate facing direction.
- Selecting the correct counter method.
- Deliberately timing abilities.
- Learning their customized normal attack loop.
- Selecting suitable stance-specific counter opportunities.
- Countering groups of enemies within the additional counter window.
- Preserving offensive momentum through successful defensive actions.

The Odachi should feel deliberate, responsive and powerful in the hands of a player who understands both their own weapon and their opponents.

---

## 15. Remaining Design Questions

### Numerical Balancing

- Exact Default counter window extension.
- Exact frontal counter angles.
- Wide counter angle increase.
- Focused counter angle reduction.
- Focused retaliation damage multiplier.
- Incoming damage-to-retaliation conversion formula.
- Multiple counter scaling formula.
- Potential maximum retaliation damage.
- Reversal Strike Stability cost.
- Reversal Strike base cooldown.
- Ability-specific counter enhancements.

### Normal Attacks

- Exact normal attack animations.
- Attack speed.
- Attack range.
- Individual swing damage.
- Stance-specific normal attack patterns.
- Attack loop composition.

### Animation and Implementation

- Vector Break movement interruption duration.
- Behavior of movement interruptions when countering multiple attacks.
- Counter sound design.
- Visual indication of active counter windows.
- Retaliation slash animations.
- Projectile launch timing.
- Magical retaliation visuals.
- Interaction between animation duration and active counter windows.

### Individual Abilities

- Counter enhancements for each ability.
- Ability-specific attack loop continuation.
- Potential exceptions to general counter rules.

These details are intentionally left open until weapon implementation, ability design and playtesting.

---

## 16. Final Weapon Identity

**The Odachi is a timing-based counterattack weapon that transforms enemy aggression into defensive protection and offensive retaliation.**

Its defining mechanic is the ability to deliberately counter incoming attacks through ordinary abilities, Reversal Strike and Vector Break.

Customized normal attack loops allow players to influence their counter properties, while Weapon Mastery gradually expands the types of attacks they can counter.

Successful countering rewards the player with complete protection, enhanced offensive capabilities and preserved combat rhythm.

**Design Status: Core Weapon Identity Complete.**