# Dual Guns – Mobile Firepower

## 1. Weapon Identity

**Weapon Identity:** Mobile Firepower  
**Combat Role:** Mobile mid-range sustained damage  
**Mastery Mechanic:** Dual Rhythm (alternative name: Crossfire)

The Dual Guns are magical mid-range weapons that reward continuous movement, positioning and sustained offensive pressure.

Unlike most weapons, the Dual Guns allow the player to freely move while performing normal attacks. Successful normal attacks generate stacks that enhance abilities, with increased stack generation while moving.

### Core Characteristics

- Free movement during normal attacks.
- Comparatively low damage per individual projectile.
- High sustained offensive pressure.
- Attack range slightly greater than that of the Whip.
- Movement-based ability enhancement.
- Non-piercing magical projectiles.
- Exceptional mobility through Vector Break.
- Individual abilities may restrict movement.

---

## 2. Normal Attacks

Normal attacks consist of individual magical projectiles fired from both guns.

- Each projectile hits only the first enemy it encounters.
- Projectiles do not pierce enemies.
- The player can walk and run while performing normal attacks.
- Normal attacks support automatic targeting and manual directional attacking.
- The exact attack animations, projectile count and damage values are yet to be determined.

### Attack Stances

The three stances primarily change projectile distribution rather than attack speed, projectile count or maximum attack range.

|Stance|Behaviour|
|---|---|
|Default|Relatively straight projectile trajectories with a slight spread.|
|Wide|Individual projectiles distributed across a wide area, with certain attacks potentially covering up to 180°.|
|Focused|Concentrated projectile distribution intended for single-target damage.|

The Wide Stance distributes individual shots rather than turning normal attacks into shotgun-like blasts.

---

## 3. Core Weapon Mechanic – Ability Enhancement Stacks

Successful normal attacks generate stacks that enhance the effectiveness of abilities.

### Stack Generation

- Every successful projectile hit generates stacks.
- While stationary: 1 stack per successful projectile hit.
- While moving: 2 stacks per successful projectile hit.
- Movement alone does not generate stacks.
- Missing an enemy does not generate stacks.
- The ×2 movement multiplier is provisional.

### Stack Accumulation and Consumption

- The player can accumulate more than 100 stacks.
- 100 stacks are sufficient to fully enhance one compatible ability.
- Compatible abilities consume up to 100 stacks.
- Excess stacks remain available for subsequent abilities.
- Abilities can benefit from fewer than 100 stacks with reduced enhancement.

### Stack Decay

- Moving prevents stack decay.
- Remaining stationary for 2 seconds initiates gradual stack decay.
- Stacks disappear gradually rather than simultaneously.
- Casting abilities interferes with the decay timer.
- Vector Break resets the decay timer.

The exact decay rate and interaction between ordinary ability casts and the decay timer remain undecided.

### Ability Enhancements

The effect of accumulated stacks depends on the individual ability and its purpose.

Preliminary enhancement examples:

- Offensive abilities: additional projectiles.
- AoE abilities: additional simultaneously affected targets.
- Mobility abilities: increased movement speed.
- Utility abilities: increased duration or effectiveness.

Individual ability enhancements will be determined during ability development.

---

## 4. Vector Break

The Dual Guns' Vector Break focuses entirely on mobility and repositioning rather than dealing damage.

### Characteristics

- Extremely fast, blink-like movement.
- No projectiles are fired during Vector Break.
- Extended initial invulnerability frames.
- Resets the ability enhancement stack decay timer.
- Does not interrupt the current normal attack loop.
- The player resumes the existing attack loop after repositioning.

### Difference Between Dash and Vector Break

|Mechanic|Dash|Vector Break|
|---|---|---|
|Interrupts attack loop|Yes|No|
|Offensive projectiles|No|No|
|Extended invulnerability|—|Yes|
|Resets stack decay timer|—|Yes|

Preserving the normal attack loop is an exclusive advantage of Vector Break over regular Dash.

---

## 5. Mastery Level 50 – Dual Rhythm

Dual Rhythm introduces a secondary stack mechanic that exists independently of the core ability enhancement stacks.

### Stack Generation

- Both guns must successfully hit an enemy at least once within the same normal attack loop.
- Both guns do not need to hit the same enemy.
- Maximum of one Dual Rhythm stack generated per attack loop.
- Maximum of 10 stacks for now.

### Damage Bonus

- Each stack increases all Dual Guns damage.
- The damage bonus applies to both normal attacks and abilities.
- Provisional damage bonus: +1% per stack.
- Provisional maximum damage bonus: +10%.

### Stack Loss and Decay

Dual Rhythm stacks can be lost in two ways:

**Unsuccessful attack loop:**

- Completing an attack loop without successfully hitting an enemy with both guns removes one stack.

**Time-based decay:**

- Initial grace period of 2 seconds.
- After the grace period, one stack is lost every second.
- Casting an ability resets the decay timer.

Abilities do not consume Dual Rhythm stacks.

### Stance Switching

- The player can only switch stances while outside attack and ability animations.
- Existing Dual Rhythm stacks are retained when switching stances.
- Switching stances does not inherently replenish stacks.
- A sufficiently quick stance switch allows the player to maintain and build upon existing stacks.

### Naming

- Current preferred name: Dual Rhythm.
- Alternative name: Crossfire.

---

## 6. Mastery Level 100 – Enhanced Dual Rhythm

When the player reaches maximum Dual Rhythm stacks, normal attacks gain additional effects depending on the currently equipped stance.

|Stance|Additional Effect|
|---|---|
|Default|Small blasts occur at the targets hit, dealing additional radial damage.|
|Wide|Stance-specific additional damage effect. Exact details to be recovered.|
|Focused|Stance-specific additional effect. Exact details to be recovered.|

These additional effects depend on maintaining maximum Dual Rhythm stacks.

The exact damage values and balancing remain undecided.

---

## 7. Comparison of Stack Mechanics

|Property|Ability Enhancement|Dual Rhythm|
|---|---|---|
|Acquisition|Baseline weapon mechanic|Mastery Lv. 50|
|Generation|Successful individual projectile hits|Both guns hit within one attack loop|
|Generation while moving|×2|No additional bonus established|
|Maximum|Can exceed 100|10 (provisional)|
|Purpose|Enhance abilities|Increase all weapon damage|
|Consumed by abilities|Yes, up to 100|No|
|Initial decay duration|2 seconds stationary|2 seconds|
|Decay prevention|Movement|Ability casts reset timer|
|Mastery Lv. 100 interaction|None established|Stance-specific normal attack enhancements|

Both stack mechanics operate independently of one another.

---

## 8. Alternative Control Schemes

The player can toggle between two global control schemes. These are not exclusive to the Dual Guns.

### WASD Movement / Mouse Attacks

- WASD controls player movement.
- Mouse position determines attack direction.
- Movement and attack direction operate independently, subject to weapon-specific restrictions.

### Mouse Movement / WASD Attacks

- Mouse controls player movement.
- Pressing WASD automatically initiates normal attacks in the corresponding camera-relative direction.
- Combining two directional keys enables diagonal attacks.
- Eight possible attack directions.
- Holding directional input continuously performs normal attacks.

The Dual Guns particularly benefit from these control schemes because they can move and attack simultaneously.

---

## 9. Attack Direction Lock

The following rules apply to normal attacks across both control schemes.

- Each individual normal attack locks its direction when its animation begins.
- Changing directional input during an attack affects the next attack rather than the current one.
- Changing attack direction does not reset the attack loop.
- Releasing the attack input allows the current attack to finish.
- No subsequent attack begins unless another attack input is active.
- Providing a new directional input before the current attack finishes continues the existing attack loop without interruption.
- Individual weapon mechanics may override these rules.

---

## 10. Manual Attacking and Automatic Targeting

Outside the Engaged Attack State:

- Manual directional attacks override automatic targeting.
- The currently selected enemy remains selected.
- The player can attack other enemies without changing their selected target.
- Targeted abilities can still use the selected enemy.

Whether releasing manual attack input automatically resumes previously active automatic attacking remains undecided.

---

## 11. Engaged Attack State

The Engaged Attack State begins when the player reaches the closest possible attack position against a selected enemy and automatically attacks it.

This state preserves the Metin2-inspired automatic combat system while providing additional design space for weapon-specific mechanics.

### General Rules

- The player remains focused on the selected enemy.
- Directional inputs do not change movement or attack direction by default.
- Directional inputs are still registered internally.
- Individual weapon mechanics can interpret directional inputs differently.
- Abilities, Dash and Vector Break continue to follow their existing rules.

### Weapon-Specific Interactions

|Weapon|Directional input while engaged|
|---|---|
|Standard weapons|No effect.|
|Scythe|Activates Attack Steering.|
|Dual Guns|Enables movement while attacking.|
|Future weapons|Potential weapon-specific mechanics.|

No additional universal mechanics, such as item throwing, are currently planned for directional inputs during this state.

### Dual Guns – Engaged Mobility

The Dual Guns are an exception to the standard movement restrictions of the Engaged Attack State.

- The player can move while automatically attacking the selected enemy.
- Movement does not inherently interrupt normal attacks.
- Successful projectile hits while moving benefit from increased ability enhancement stack generation.
- This reinforces the Dual Guns' identity as a mobile sustained-damage weapon.

The precise interaction between manual attack direction, automatic targeting and movement under both control schemes remains to be finalized.

---

## 12. Core Design Philosophy

The Dual Guns reward the player for maintaining continuous offensive pressure while actively moving around the battlefield.

Rather than relying on powerful individual attacks, the player builds momentum through successful projectile hits and converts that momentum into enhanced abilities.

At higher mastery levels, Dual Rhythm additionally rewards consistently landing attacks with both guns, increasing overall damage and eventually unlocking stance-specific normal attack enhancements.

Vector Break complements this identity by allowing rapid repositioning without sacrificing the player's existing attack loop.

The Dual Guns should encourage movement without making stationary combat completely unviable.

---

## 13. Remaining Development Decisions

- [ ] Exact normal attack animations.
- [ ] Projectile count and distribution per attack.
- [ ] Exact attack range.
- [ ] Normal attack damage values.
- [ ] Individual ability enhancement effects.
- [ ] Final movement-based stack generation multiplier.
- [ ] Ability enhancement stack decay rate.
- [ ] Ordinary ability interaction with the ability enhancement decay timer.
- [ ] Exact Vector Break speed, distance and invulnerability duration.
- [ ] Final Dual Rhythm damage bonus per stack.
- [ ] Final Dual Rhythm maximum stack count.
- [ ] Complete Mastery Lv. 100 stance-specific effects.
- [ ] Automatic targeting behaviour after releasing manual attack input.
- [ ] Dual Guns input behaviour during the Engaged Attack State under both control schemes.
- [ ] Final mastery mechanic name: Dual Rhythm or Crossfire.
- [ ] Overall numerical balancing.

---

**Development Status:** Core weapon identity and mechanics established. Individual ability interactions, some mastery details and numerical balancing remain open.

**Last updated:** 25.11.2026