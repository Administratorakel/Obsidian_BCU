[[Swordmaster]] 

Mastery buff:
**Lv 50 — Long-Sword Momentum I**

Consecutive successful hits build damage stacks.

- Missing an attack does not reset stacks.
- Stacks expire after a period without successful hits.
- Exact stack values and duration remain undecided.

**Lv 100 — Long-Sword Momentum II**

Upgrades the existing passive.

- Consecutive hits increase damage and attack speed.
- Damage bonuses become stronger.
- Stack expiration duration increases.


# Two-Handed Sword (2H Sword)

**Status:** Core identity established; balancing pending  
**Combat Identity:** Cleaving Follow-Through  
**Damage Type:** Physical / Magical

## 1. Weapon Identity

The Two-Handed Sword specializes in powerful, sweeping attacks that become more effective against groups of enemies.

Its defining mechanic, **Cleaving Follow-Through**, generates a secondary cutting arc after every normal attack.

The weapon should:

- Reward positioning and hitting multiple enemies.
    
- Excel at cleaving through groups.
    
- Deliver powerful, deliberate attacks.
    
- Remain effective against individual enemies and bosses.
    
- Feel distinct from the Odachi's counterattacks and Fighting Slab's momentum.
    

**Design Philosophy:** Every additional enemy struck increases the power of the follow-through attack.

## 2. Cleaving Follow-Through

Every normal attack produces two consecutive hits:

1. **Original Sword Swing:** Deals normal weapon damage.
    
2. **Secondary Cutting Arc:** Strikes the same enemies again after a short delay.
    

### Mechanics

- Every normal attack generates a secondary cutting arc.
    
- The arc activates **0.5 seconds after the original swing**.
    
- The arc follows the original attack's trajectory visually.
    
- It only damages enemies struck by the original sword swing.
    
- Enemies entering the area afterward cannot be struck by the secondary arc.
    
- Each enemy can receive one additional hit from the arc.
    
- The arc's damage increases with the number of enemies struck by the original swing.
    
- Secondary arc hits do not increase its damage.
    
- Damage scaling resets with each individual normal attack.
    

### Damage Calculation

**Arc Damage = Original Attack Damage × (20% + 5% × Enemies Hit)**

|Enemies hit by original swing|Secondary arc damage|
|---|---|
|1|25%|
|2|30%|
|3|35%|
|4|40%|
|5|45%|
|6|50%|
|10|70%|

_All values are provisional and subject to balancing._

### Multi-Target Damage Falloff

The original sword swing follows the general multi-target damage system unless an exception is established later.

Standard damage falloff:

|Enemy hit order|Damage|
|---|---|
|First|100%|
|Second|80%|
|Third|60%|
|Fourth|40%|
|Fifth and beyond|20%|

**The secondary cutting arc ignores multi-target damage falloff entirely.**

All enemies hit by the secondary arc receive its full calculated damage multiplier, regardless of their hit order.

## 3. Normal Attack Combinations

The Two-Handed Sword supports the three existing attack stances.

### Standard Stance

- Balanced attack coverage and damage.
    
- Reliable combinations against individual enemies and groups.
    

### Wide Stance

- Larger attack arcs.
    
- Greater potential to hit multiple enemies.
    
- Naturally increases Cleaving Follow-Through damage by hitting more targets.
    

### Fast Stance

- Faster, more compact attacks.
    
- More frequent follow-through activations.
    
- Potentially less effective at hitting large groups.
    

Each attack in the combination calculates its follow-through damage independently.

## 4. Vector Break / Bulletjump

**Established characteristics:**

- Increased damage.
    
- Increased damage range.
    

Further interactions with Cleaving Follow-Through remain undecided.

## 5. Weapon Mastery

Weapon Mastery provides progression through combat experience.

Cleaving Follow-Through remains independent of permanent mastery bonuses.

Possible future mastery interactions could improve the effectiveness of the secondary arc, but none have been established.

## 6. Distinction From Other Heavy Weapons

|Weapon|Defining mechanic|
|---|---|
|**2H Sword**|Cleaving Follow-Through: Delayed secondary damage that scales with enemies hit|
|**Hammer**|Impact Zones: Connected areas transmit diminishing shockwaves|
|**Odachi**|Counterattacking: Abilities provide opportunities to parry incoming attacks|
|**Fighting Slab**|Momentum: Repeated attacks build damage potential|

## 7. Unresolved Questions

- Exact visual appearance of the secondary cutting arc.
    
- Whether the original physical swing should retain standard multi-target damage falloff.
    
- Whether the secondary arc can critically strike independently.
    
- How secondary arc damage interacts with status effects.
    
- Whether certain abilities can modify Cleaving Follow-Through.
    
- Final damage balancing.
    

---

## Core Design Principle

**The Two-Handed Sword rewards hitting multiple enemies with powerful swings, generating increasingly devastating follow-through attacks.**

Its mechanic requires no additional input or resource management, making it straightforward to learn while rewarding positioning and crowd engagement.