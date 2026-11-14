# 3. Little Cato & Ms. Handsome

**Companion type:** Dual-character companion  
**Companion slots required:** 1

### Real-Life Inspiration

Little Cato and Ms. Handsome are two small female cats.

Both have grey, white, and black fur with a somewhat tiger-like pattern.

Individually, both are sweet and affectionate. However, when they get too close to each other, they hiss and become hostile toward one another.

Their combat concept revolves around this territorial rivalry.

### Design Philosophy

Both cats have:

- The same attack pattern.
    
- The same attack range.
    
- Independent target selection.
    
- Individual territories.
    

Their different combat behaviors come primarily from their target selection.

When their territories overlap, they begin fighting each other, unintentionally damaging surrounding enemies.

**Important:** Their rivalry should emerge naturally through ordinary combat rather than requiring the player to activate a separate combination ability.

---

# 4. Cat A — Independent Disruption

**Identity:** Little Cato or Ms. Handsome — undecided.

Cat A operates independently of the player's primary target.

### Target Selection

- Prioritizes a nearby enemy that the player is not focusing on.
    
- Can target regular enemies, Elites, and bosses.
    
- If only one enemy is available, Cat A may attack the player's target.
    
- When Cat A's target dies, its territory disappears and Cat A selects another target.
    

### Combat Behavior

Cat A attacks its selected enemy using the shared feline attack pattern.

Its attacks may occasionally inflict short stuns.

- Regular enemies can be interrupted.
    
- Elite enemies have stun resistance.
    
- Bosses have stun resistance.
    

Cat A does not function as a tank.

Enemies continue attempting to reach and attack the player, even while Cat A disrupts them.

If Cat A engages an enemy belonging to a group, it may attack other nearby enemies belonging to that same group.

If the selected enemy is isolated, Cat A only attacks that enemy.

### Territory

Cat A establishes a circular territory around the enemy it is attacking.

- Approximate radius: melee range.
    
- Territory follows the selected enemy.
    
- Territory ends when that enemy dies.
    
- Territory does not currently provide combat buffs.
    

The territory represents the enemy Cat A is fighting over.

---

# 5. Cat B — Player-Focused Offense

**Identity:** Little Cato or Ms. Handsome — undecided.

Cat B follows the player's combat decisions.

### Target Selection

Cat B selects its target through the player's actions.

**Melee combat:**

- The first enemy struck by the player's melee attack becomes Cat B's target.
    

**Mouse targeting:**

- An enemy explicitly marked or selected with the mouse becomes Cat B's target.
    

Cat B attacks the selected enemy using the same attack pattern and range as Cat A.

### Territory

Cat B establishes its own circular territory around its selected enemy.

- Approximate radius: melee range.
    
- Territory follows the selected enemy.
    
- Territory is linked to the player-focused target.
    
- No combat buffs are currently associated with the territory.
    

### Possible Future Modifications

The cats may eventually receive:

- Different damage types.
    
- Modifiable damage types.
    
- Other individual combat modifications.
    

These mechanics remain undecided.

---

# 6. Combined Ability — Catfight

The defining ability of the dual companion.

When Cat A and Cat B come into territorial conflict, they begin fighting each other.

Their fighting creates a damaging area around them.

## Normal Activation

Both cats establish territories around their respective enemies.

The catfight activates when:

1. Both cats are actively participating in combat.
    
2. Their territorial circles touch or overlap.
    
3. The catfight cooldown has expired.
    

**The territories must physically intersect.**

It is not necessary for the cats themselves to occupy the exact same position.

### Player Interaction

The player can influence the activation through combat positioning.

For example:

1. Cat A establishes territory around Enemy A.
    
2. Cat B establishes territory around Enemy B.
    
3. The player uses a pull ability to bring the enemies closer together.
    
4. Their territories intersect.
    
5. The catfight activates.
    

Push abilities may also be used to influence positioning.

This allows players to deliberately create opportunities for the combined attack without introducing additional companion controls.

---

## Catfight Effect

When activated:

- Both cats begin fighting each other.
    
- Their approximate shared position becomes the center of the effect.
    
- A damaging AoE appears around the fight.
    
- Enemies within the AoE receive damage.
    

### Area Size

**Catfight radius = 2 × Territory radius**

Example:

|Area|Example radius|
|---|---|
|Cat A territory|2 m|
|Cat B territory|2 m|
|Catfight|4 m|

_These values are illustrative. Actual territory sizes remain undecided._

### Damage

The exact damage calculation, number of damage instances, damage type, and duration are not yet established.

Whether catfight damage should pass through walls remains undecided.

---

# 7. Catfight Cooldown

**Initial cooldown: 15 seconds**

After a catfight:

- Both cats continue their normal combat behavior.
    
- Cat A continues attacking independently.
    
- Cat B continues following the player's target.
    
- Their territories may continue to overlap without activating another catfight during cooldown.
    
- Once the cooldown expires, the catfight becomes available again.
    

### Pending Clarification

If territories are already overlapping when the cooldown expires, it remains to be decided whether the catfight activates immediately or requires the territories to separate and overlap again.

---

# 8. Single-Enemy Exception

When only one enemy is available, both cats may attack the same target.

Without a special rule, their territories would overlap almost immediately.

To avoid constantly triggering the catfight at the beginning of single-target encounters, an alternative activation rule applies.

### Single-Target Activation

1. The player attacks an enemy.
    
2. Cat B joins the player immediately.
    
3. Cat A also begins attacking that enemy.
    
4. Once both cats are actively engaging the same enemy, a timer begins.
    
5. After the timer expires, the catfight may activate.
    

### Initial Timing

**Single-target delay = 50% of Catfight cooldown**

With a 15-second cooldown:

**15 × 0.5 = 7.5 seconds**

This value is provisional and may be adjusted during gameplay testing.

The 7.5-second timer starts when both cats actively engage the same enemy, not merely when combat begins.

### Enemy Death

When Cat A's target dies:

- Its territory ends.
    
- Cat A searches for another eligible enemy.
    

Cat B's targeting is determined by the player's current combat focus.

### Targeting Restrictions

Cat A may engage bosses and Elite enemies.

Bosses and Elites possess resistance against stuns.

### Collision

Companions do not physically obstruct players or enemies.

Their territories are gameplay areas rather than physical obstacles.




**Core concept: Two affectionate cats who cannot stand each other, turning their territorial rivalry into an accidental combat advantage.**