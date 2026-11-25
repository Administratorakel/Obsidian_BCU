[[Hunter]]

**BCU Game – Weapon Design Documentation**

**Status:** Core weapon identity established; balancing and individual abilities pending  
**Weapon Type:** Physical, dual-wielded melee  
**Combat Identity:** Relentless close-range aggression through Engagement, Disengagement, and Momentum

---

## 1. Core Identity

Twin Daggers specialize in extremely fast, close-range combat against individual enemies and small groups.

Their defining mechanic is **Engage and Disengage**, allowing offensive and other compatible abilities to incorporate rapid movement.

Successful normal attacks generate **Momentum stacks**, which can enhance the movement distance of abilities.

The weapon emphasizes:

- High attack speed.
    
- Short melee attack range.
    
- Relentless offensive pressure.
    
- Rapid individual dagger strikes.
    
- Fighting single enemies or small groups.
    
- Deliberate engagement and disengagement.
    
- Building Momentum through successful hits.
    
- Using Momentum to reposition offensively or defensively.
    

Twin Daggers do not inherently require unusually high critical chance. Their primary statistical strength is attack speed.

## 2. Normal Attacks

Each normal attack animation uses both daggers.

### Two-Strike Rule

- Every normal attack animation contains exactly **two individual dagger strikes**.
    
- Each dagger performs one strike.
    
- Strikes can occur sequentially or simultaneously.
    
- Each strike has independent hit detection.
    
- Both strikes generally deal equal damage.
    
- Stance-specific damage variations may be introduced later.
    

An individual dagger strike can damage multiple enemies depending on its hitbox.

### Attack Stances

All three stances maintain the two-strike rule, but change how the daggers attack.

**Standard Stance – Balanced Assault**

- Alternating dagger attacks.
    
- Balanced attack coverage.
    
- Suitable for single enemies and small groups.
    
- Two strikes per animation.
    

**Wide Stance – Sweeping Assault**

- Broader attacks covering nearby enemies.
    
- Both daggers may swing simultaneously.
    
- Wider coverage without greatly increasing the weapon's short reach.
    
- Two individually registered strikes per animation.
    

**Focused Stance – Concentrated Assault**

- Narrower, more concentrated attacks.
    
- Emphasizes attacking a particular target.
    
- Both daggers remain involved.
    
- Two strikes per animation.
    
- Additional damage characteristics remain undecided.
    

### Combination Progression

The full normal attack combination can eventually reach seven attack animations through Weapon Mastery progression.

With two strikes per animation:

- Seven attack animations.
    
- Fourteen individual strikes.
    
- Fourteen potential Momentum stacks.
    

Later combo animations may feature more elaborate movements, but retain two individual strikes each.

Exact animation designs remain open.

---

## 3. Momentum – Weapon Mastery Mechanic

Momentum is a proposed Weapon Mastery bonus that rewards successful consecutive dagger strikes.

It enhances the Engage/Disengage system rather than directly increasing damage, critical chance, or attack speed.

### Stack Generation

- Each successful individual dagger strike generates **one Momentum stack**.
    
- A strike must hit at least one enemy.
    
- Hitting multiple enemies with the same dagger strike still generates only one stack.
    
- Each dagger is evaluated independently.
    
- Missing an attack generates no Momentum.
    
- Missing does not impose an additional penalty.
    

**Example:**

One normal attack animation performs two strikes:

- Left dagger hits three enemies: +1 stack.
    
- Right dagger hits one enemy: +1 stack.
    
- Total: 2 Momentum stacks.
    

If the right dagger misses, only one stack is generated.

### Maximum Stacks

Maximum Momentum is determined by the total number of individual strikes in the player's currently unlocked normal attack combination.

**Formula:**

Maximum Momentum = Unlocked Combo Animations × 2

Examples:

|Combo animations|Maximum stacks|
|---|---|
|3|6|
|4|8|
|5|10|
|6|12|
|7|14|

These values assume two strikes per animation.

The exact starting combo length and mastery unlock progression follow the general BCU Weapon Mastery system.

### Momentum Expiration

- Momentum stacks expire after **1 second without a successful dagger strike**.
    
- Successful strikes refresh the timer.
    
- The timer applies to accumulated Momentum.
    
- The one-second duration is the current provisional value.
    

Momentum expires independently of the stored Engage/Disengage movement window.

---

## 4. Engage and Disengage

Engage and Disengage are the defining movement mechanics of the Twin Daggers.

They are incorporated into compatible abilities, rather than being separate normal attacks.

### Engage

Engage rapidly moves the player toward an enemy or chosen direction while performing an ability.

- Can target a selected enemy.
    
- Can function without an enemy selected.
    
- Without a target, movement follows the intended movement or aiming direction.
    
- Intermediate enemies do not automatically stop the movement.
    
- Walls and solid obstacles stop actual displacement.
    
- Exact movement distance depends on the ability and Momentum.
    

### Disengage

Disengage executes an ability while retreating.

- Movement is always backward relative to the character's facing direction.
    
- Camera direction does not determine retreat direction.
    
- The attack can happen before, during, or after the movement.
    
- Attack timing depends on the individual ability.
    
- Walls and solid obstacles stop displacement.
    

### Input System – Provisional

The current intended input distinction is:

- **Tap ability:** Engage variation.
    
- **Hold ability:** Disengage variation.
    

The precise interaction with abilities that already require holding or charging remains to be resolved individually.

Not every ability necessarily requires identical movement behavior.

---

## 5. Momentum-Based Movement

Momentum increases the distance available to Engage and Disengage.

The exact distance gained per stack is not yet established.

### Ability-Dependent Scaling

Different abilities can interact with Momentum differently.

Possible tendencies:

|Ability category|Movement characteristic|
|---|---|
|Direct offense|Stronger target engagement|
|AoE offense|Shorter movement with broader attacks|
|Utility|Ability-specific repositioning|
|Mobility|Greater movement potential|

These are design directions, not finalized numerical rules.

Movement distances are determined by the individual ability, potentially modified by Momentum.

---

## 6. Stored Engage/Disengage Pair

A Momentum-powered movement creates a temporary opportunity to execute the opposite movement.

This allows the player to retreat and return, or engage and retreat, without immediately rebuilding Momentum.

### Movement Pair Rules

1. The player accumulates Momentum.
    
2. They activate an Engage or Disengage ability.
    
3. The accumulated Momentum is consumed.
    
4. The movement range used is stored temporarily.
    
5. The player has **2 seconds** to execute the opposite movement.
    
6. The complementary movement uses the stored distance, subject to the second ability's supported movement limit.
    
7. The stored movement opportunity disappears after use or expiration.
    

Both movement orders are valid:

**Engage → Disengage**

**Disengage → Engage**

The player may choose different compatible abilities for the two movements.

### Example

The player accumulates 10 Momentum stacks.

They use an AoE ability to Disengage, retreating a Momentum-enhanced distance.

For the next two seconds, they may activate another ability to Engage with the stored range.

If that second ability supports less movement, its own movement limit applies.

The exact distance calculations remain open for balancing.

### Stored Movement Duration

- Stored movement lasts **2 seconds**.
    
- Taking damage does not remove the stored opportunity.
    
- The timer expires normally regardless of incoming damage.
    
- After expiration, the unused complementary movement is lost.
    

---

## 7. Generating Momentum During a Movement Window

New Momentum can accumulate while a stored Engage/Disengage opportunity remains active.

The systems operate independently.

### Rules

- Activating the first movement consumes the currently accumulated stacks.
    
- Its movement range is stored for the complementary movement.
    
- Successful dagger strikes can immediately generate fresh Momentum.
    
- Fresh stacks do not modify the stored movement range.
    
- The stored complementary movement takes priority when the opposite movement is activated.
    
- Newly accumulated Momentum remains available afterward, provided it has not expired.
    

### Example

1. Player accumulates 10 stacks.
    
2. Player Engages, storing the corresponding movement range.
    
3. Player lands new attacks and accumulates 4 stacks.
    
4. Player Disengages within the two-second window.
    
5. The Disengage uses the stored movement range, subject to its ability limit.
    
6. The 4 new stacks remain available for a future movement pair.
    

Fresh Momentum follows its own one-second expiration timer.

Handling repeated movement activations of the same type before completing a pair remains an implementation detail to finalize.

---

## 8. Movement Interruption and Collision

Engage and Disengage follow BCU's existing dash-style movement principles.

### Interruption

- Ordinary enemy attacks cannot interrupt an active Engage or Disengage movement.
    
- The player can still receive damage.
    
- Movement is not automatically invulnerable.
    
- Taking damage does not remove the stored complementary movement opportunity.
    

### Walls and Obstacles

- Walls prevent further movement.
    
- If the player activates movement directly into a wall, the animation still executes.
    
- The character remains in place if movement is completely blocked.
    
- Attempting the movement still consumes the corresponding movement opportunity.
    

### Enemies

- Ordinary enemies between the player and their intended destination do not automatically stop engagement.
    
- The player may travel past them to reach the intended target.
    
- Exact collision handling and special enemy exceptions remain for implementation.
    

---

## 9. Movement Visuals and Weapon Mastery

Engage and Disengage should feel extremely fast and aggressive.

At lower mastery levels:

- Movement remains visually readable.
    
- The character visibly travels between positions.
    
- Attack animations accompany the movement.
    

At higher mastery levels:

- Movement may become considerably faster.
    
- The movement could visually approach a blinking step or extremely rapid displacement.
    
- The intended destination and collision restrictions remain relevant.
    

Actual teleportation is not currently required.

The exact progression and mastery milestone responsible for these improvements remain undecided.

---

## 10. Intended Combat Rhythm

The Twin Daggers reward maintaining close combat pressure.

**Normal Attacks → Build Momentum → Engage or Disengage → Stored Opposite Movement → Continue Attacking**

For example:

1. The player attacks an enemy repeatedly.
    
2. Successful dagger strikes accumulate Momentum.
    
3. The player Disengages using an offensive ability.
    
4. The player has two seconds to Engage again.
    
5. The return Engage uses the previously stored movement range.
    
6. Meanwhile, any new successful attacks can build Momentum for the next movement pair.
    

This allows rapid offensive repositioning without restricting the weapon to single-target combat.

Wide Stance supports fighting small groups, while Focused Stance emphasizes concentrated attacks.

---

## 11. Established Design Decisions

- Twin Daggers prioritize high attack speed.
    
- High inherent critical chance is not required.
    
- Close-range combat can target one enemy or small groups.
    
- Every normal attack animation uses both daggers.
    
- Exactly two individually registered dagger strikes per animation.
    
- Both strikes generally deal equal damage.
    
- All three stances retain the two-strike rule.
    
- Stances change normal attack patterns rather than directly changing movement mechanics.
    
- Standard uses balanced alternating attacks.
    
- Wide provides broader coverage.
    
- Focused provides concentrated attacks.
    
- Engage and Disengage are integrated with compatible abilities.
    
- Engagement can function without a selected enemy.
    
- Disengagement always travels backward relative to player facing.
    
- Offensive ability effects may occur before, during, or after disengagement.
    
- Individual abilities determine their movement characteristics.
    
- Momentum can increase movement range.
    
- Each successful individual dagger strike generates one Momentum stack.
    
- Multiple enemies hit by one dagger strike do not generate additional stacks.
    
- Missing attacks generate no stacks and impose no additional penalty.
    
- Maximum Momentum equals the total individual strikes in the unlocked combo.
    
- Maximum potential with seven combo animations is 14 stacks.
    
- Fresh Momentum expires after 1 second without a successful hit.
    
- A Momentum-powered movement stores a complementary movement opportunity.
    
- The stored movement window lasts 2 seconds.
    
- Engage/Disengage pairs can occur in either order.
    
- Fresh Momentum can accumulate during the stored movement window.
    
- Stored range and newly accumulated Momentum remain independent.
    
- Incoming damage does not remove the stored movement opportunity.
    
- Enemy attacks do not normally interrupt active movement.
    
- Walls stop displacement but do not cancel the executed movement.
    
- Blocked movement still consumes the movement opportunity.
    
- Higher Weapon Mastery may make movement increasingly blink-like.
    

---

## 12. Open Questions for Development

The following details do not prevent the core identity from being considered established.

### Balancing

- Base Engage and Disengage distances.
    
- Additional movement distance per Momentum stack.
    
- Individual ability movement limits.
    
- Final Momentum expiration balancing.
    
- Movement duration and travel speed.
    
- Exact movement scaling at higher mastery.
    

### Combat and Abilities

- Exact attack animations for each stance.
    
- Additional stance-specific damage behavior.
    
- Which abilities support Engage, Disengage, or specialized variants.
    
- Interaction between holding to Disengage and charging an ability.
    
- Handling repeated same-direction movement attempts during an active stored pair.
    
- Special enemy collision and targeting exceptions.
    

### Weapon Mastery

- Exact level where Momentum becomes available.
    
- Progression of movement speed improvements.
    
- Possible blink-like movement enhancements.
    
- Any additional rewards for consecutive attacks.
    

---

## 13. Development Status

**Twin Daggers Core Identity: Established.**

The weapon now has a recognizable combat philosophy built around:

**Relentless close-range aggression, two-strike dagger attacks, Momentum generation, and ability-based Engagement/Disengagement.**

The next major development stage is designing individual Twin Dagger abilities and determining how their movement variations interact with Momentum.

Precise numerical balancing, specialized animations, and remaining edge cases will be addressed during further design and implementation.