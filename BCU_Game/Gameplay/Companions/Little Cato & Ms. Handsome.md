# 3. Little Cato & Miss Handsome

**Companion type:** Dual-character companion  
**Companion slots required:** 1

### Real-Life Inspiration

Little Cato and Miss Handsome are two small female cats.

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

# 4. Little Cato — Independent Disruption


Little Cato operates independently of the player's primary target.

### Target Selection

- Prioritizes a nearby enemy that the player is not focusing on.
- Can target regular enemies, Elites, and bosses.
- If only one enemy is available, Little Cato may attack the player's target.
- When Little Cato's target dies, its territory disappears and Little Cato selects another target.

### Combat Behavior

Little Cato's attacks its selected enemy using the shared feline attack pattern.

Its attacks may occasionally inflict short stuns.

- Regular enemies can be interrupted.
- Elite enemies have stun resistance.
- Bosses have stun resistance.

Little Cato does not function as a tank.

Enemies continue attempting to reach and attack the player, even while Little Cato disrupts them.

If Little Cato engages an enemy belonging to a group, it may attack other nearby enemies belonging to that same group.

If the selected enemy is isolated, Little Cato only attacks that enemy.

### Territory

Little Cato establishes a circular territory around the enemy it is attacking.

- Approximate radius: melee range.
    
- Territory follows the selected enemy.
    
- Territory ends when that enemy dies.
    
- Territory does not currently provide combat buffs.
    

The territory represents the enemy Little Cato is fighting over.

---

# 5. Miss Handsome — Player-Focused Offense

**Identity:** Little Cato or Miss Handsome — undecided.

Miss Handsome follows the player's combat decisions.

### Target Selection

Miss Handsome selects its target through the player's actions.

**Melee combat:**

- The first enemy struck by the player's melee attack becomes Miss Handsome's target.
    

**Mouse targeting:**

- An enemy explicitly marked or selected with the mouse becomes Miss Handsome's target.
    

Miss Handsome attacks the selected enemy using the same attack pattern and range as Little Cato.

### Territory

Miss Handsome establishes its own circular territory around its selected enemy.

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

When Little Cato and Miss Handsome come into territorial conflict, they begin fighting each other.

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

1. Little Cato establishes territory around Enemy A.
    
2. Miss Handsome establishes territory around Enemy B.
    
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

| Area                    | Example radius |
| ----------------------- | -------------- |
| Little Cato territory   | 2 m            |
| Miss Handsome territory | 2 m            |
| Catfight                | 4 m            |

_These values are illustrative. Actual territory sizes remain undecided._

### Damage

The exact damage calculation, number of damage instances, damage type, and duration are not yet established.

Whether catfight damage should pass through walls remains undecided.

---

# 7. Catfight Cooldown

**Initial cooldown: 15 seconds**

After a catfight:

- Both cats continue their normal combat behavior.
    
- Littlle Cato continues attacking independently.
    
- Miss Handsome continues following the player's target.
    
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
    
2. Miss Handsome joins the player immediately.
    
3. Little Cato also begins attacking that enemy.
    
4. Once both cats are actively engaging the same enemy, a timer begins.
    
5. After the timer expires, the catfight may activate.
    

### Initial Timing

**Single-target delay = 50% of Catfight cooldown**

With a 15-second cooldown:

**15 × 0.5 = 7.5 seconds**

This value is provisional and may be adjusted during gameplay testing.

The 7.5-second timer starts when both cats actively engage the same enemy, not merely when combat begins.

### Enemy Death

When Little Cato's target dies:

- Its territory ends.
    
- Little Cato searches for another eligible enemy.
    

Miss Handsome's targeting is determined by the player's current combat focus.

### Targeting Restrictions

Little Cato may engage bosses and Elite enemies.

Bosses and Elites possess resistance against stuns.

### Collision

Companions do not physically obstruct players or enemies.

Their territories are gameplay areas rather than physical obstacles.




**Core concept: Two affectionate cats who cannot stand each other, turning their territorial rivalry into an accidental combat advantage.**