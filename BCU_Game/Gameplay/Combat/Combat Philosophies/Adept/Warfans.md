[[Adept]]

# Warfans – Weapon Concept

**BCU Game – Obsidian Documentation**

**Status:** Core weapon identity established  
**Weapon Type:** Magical  
**Combat Role:** Piercing attacks, buffs, offensive support, and crowd control

---

## 1. Core Identity

Warfans are magical weapons that release piercing projectiles through swinging attacks.

Their defining mechanic is the creation of **Magical Residues**, which can be collected and consumed to enhance abilities.

The weapon emphasizes:

- Deliberate targeting and positioning.
- Preparation through normal attacks.
- Mage-like ability charging.
- Buffing and supporting allies.
- Strategic use of Standard, Wide, and Focused stances.

## 2. Normal Attacks

Normal attacks release magical projectiles that can damage multiple enemies along their path.

Two attack modes exist.

### Focused Attacks

The player selects an enemy as their target.

- Projectile travels toward the focused enemy.
- Enemies pierced before the focused target receive **50% damage**.
- The focused target receives **100% damage**.
- The projectile stops upon reaching the focused enemy.
- One Magical Residue appears at the focused enemy's hit position.

### Unfocused Attacks

The player attacks forward without selecting an enemy.

- Projectile travels forward through enemies within its maximum range.
- The first enemy hit receives **100% damage**.
- Every subsequent enemy receives **50% damage**.
- The projectile continues through enemies until its maximum range.
- One Magical Residue appears at the position of the last enemy hit.
- If no enemy is hit, the projectile disappears without creating a residue.

### General Rules

- Each successful normal attack creates **exactly one residue**, regardless of how many enemies are hit.
- Residues are created from the projectile itself.
- Residues remain stationary at their creation positions.
- They do not follow enemies that move or die.
- Normal attack damage percentages are initial balancing values.

---

## 3. Magical Residues

Magical Residues represent fragments of the player's Stability left behind by Warfan projectiles.

### Basic Rules

- **Lifetime:** 4 seconds.
- **Ownership:** Each residue belongs exclusively to its creator.
- **Location:** Stationary in the environment.
- **Maximum collection range:** Unlimited.
- **Expiration:** Residues disappear harmlessly.
- **Stance memory:** Each residue remembers the stance used to create it.

Only the caster's own residues can enhance their abilities.

The four-second duration is provisional. A three-second duration may be tested later.

---

## 4. Ability Charging and Residue Collection

Warfans are intended to feel like a mage weapon, with comparatively longer ability charging times.

### Collection Process

1. The player begins charging an ability.
2. A visible focal point appears at the ability's target location.
3. All active residues belonging to the caster are identified and locked in.
4. Their expiration timers stop.
5. Residues travel toward the focal point in order of distance.
6. Arriving residues apply their stance-dependent enhancements.
7. The ability activates with the collected enhancements.

Possible focal points include the caster, an ally, an enemy, or an ability's target area.

### Residue Arrival Timing

Residues normally arrive between **10% and 50% of the ability's original charging time**.

- Nearby residues arrive closer to 10%.
- Distant residues arrive later.
- All residues normally arrive no later than 50%.

**Example: Four-second charge**

- Earliest arrival: 0.4 seconds.
- Latest normal arrival: 2 seconds.

Distance determines arrival timing within this window.

### Early Completion

Standard Stance residues can shorten the remaining charging time.

- Residue collection and charging-time reductions are accounted for when channeling begins.
- If Standard residues cause the ability to finish earlier than other residues would normally arrive, the remaining residues are immediately pulled in.
- All locked-in residues contribute before the ability activates.
- The ability does not wait unnecessarily for distant residues.

Exact calculation and animation handling will be determined during implementation.

---

## 5. Stance-Dependent Residue Effects

Each residue retains its creation stance and provides a generally consistent enhancement when absorbed.

### Standard Stance – Charging Speed

**Reduces the remaining ability charging time.**

- Each Standard residue reduces the remaining charge time by a percentage.
- Reductions apply to the remaining time rather than the original total.
- Multiple Standard residues can accelerate an ability considerably.
- Early completion also accelerates collection of other locked-in residues.

**Identity:** Faster spellcasting through preparation.

### Wide Stance – Expansion

**Expands the ability's effect through magical pulses.**

- Collected Wide residues create or contribute to pulses around the ability's focal point.
- Offensive abilities can affect additional enemies.
- Support abilities can spread buffs to more allies.
- Utility effects may receive expanded area coverage.

**Identity:** Greater area coverage and group effectiveness.

### Focused Stance – Intensity

**Strengthens the ability's effect.**

- Offensive abilities may deal increased damage.
- Buffs may become stronger.
- Other ability effects may increase in intensity.
- Exact scaling depends on the ability.

**Identity:** Stronger immediate effects.

### Mixed Residues

Residues from multiple stances can coexist.

For example, a player could create two Standard residues, switch stance to create three Wide residues, and then charge an ability.

The ability could receive both reduced charging time and expanded effects.

**General rule:** Stance effects remain consistent across abilities, but exceptions may be introduced when designing individual abilities.

---

## 6. Visual Identity

### Projectiles

- Magical projectiles originate from swinging the Warfans.
- Their color and appearance may depend on the equipped weapon.
- Attack animations and projectile shapes should make different Warfans visually recognizable.

### Residues

- Residue appearance communicates its creation stance.
- Colors and shapes should make different residue types distinguishable.
- Players should recognize which enhancements are approaching their abilities.
- Different stance residues can be visible simultaneously.

### Charging

- The focal point remains visible during charging.
- Residues travel toward it from their stationary locations.
- Their movement makes the upcoming ability enhancement visually understandable.

---

## 7. Intended Combat Rhythm

**Normal Attacks → Residue Creation → Stance Switching → Ability Charging → Residue Collection → Enhanced Ability**

Warfans should reward thoughtful preparation while retaining fluid combat.

Focused attacks prioritize a particular enemy. Unfocused attacks offer greater freedom when fighting groups.

Their residues allow players to influence upcoming abilities through stance selection and positioning.

---

## 8. Confirmed Baseline Decisions

- Magical piercing normal attacks.
- Focused and unfocused attack modes.
- 100% primary target damage and 50% secondary damage as starting values.
- Exactly one residue per successful normal attack.
- Stationary residues at projectile termination positions.
- No residue when an unfocused attack hits nothing.
- Four-second residue lifetime.
- Residues belong to their creator.
- Unlimited residue collection range.
- Expiration pauses when residues are locked in by an ability.
- Collection window of 10–50% of original charging time.
- Distance-based collection order.
- Standard residues can accelerate collection through early ability completion.
- Standard enhances charging speed.
- Wide expands ability coverage.
- Focused increases effect intensity.
- Residues remember their creation stance.
- Mixed stance residues can enhance the same ability.

---

## 9. Open Questions for Development

These do not prevent the baseline from being considered established.

- Exact projectile range, width, and travel speed.
- Interaction with terrain and obstacles.
- Exact charging-time reduction per Standard residue.
- Wide pulse size, stacking, and scaling.
- Focused intensity scaling.
- Precise distance-to-arrival calculation.
- Maximum practical residue count.
- Specific abilities and exceptional stance interactions.
- Final projectile and residue visual designs.
- Whether residue lifetime should remain four seconds or decrease to three.

---

## 10. Development Status

**Core Warfan weapon identity: Established.**

The normal attack behavior, residue system, collection rules, and three stance identities have been defined.

Numerical balancing, implementation details, and individual abilities will be addressed separately.

The next major design stage is creating the individual Warfan abilities around this established baseline.