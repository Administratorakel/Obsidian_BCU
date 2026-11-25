# Whip — Weapon Design

**Project:** [[BCU Game]]  
**Weapon:** Whip  
**Combat Identity:** Mobile Battlefield Control / Orbital Crowd Control  
**Damage Type:** Physical  
**Design Status:** Core Identity Complete  
**Remaining:** Balancing, exact values, individual abilities

---

## 1. Core Weapon Identity

The Whip is a medium-range weapon focused on positioning, enemy gathering, sustained compression damage, and battlefield manipulation.

Its defining mechanics are:

1. **Distance-Based Normal Attacks:** Damage increases toward the Whip's maximum attack range.
    
2. **Stability Tether:** [[Vector Break]] establishes a connection with enemies.
    
3. **Orbital Movement (OM):** The player swings around an enemy or cluster of enemies.
    
4. **Enemy Entanglement:** Enemies caught by the tether are pulled into a compressed central group.
    
5. **Sustained Control:** The player sacrifices Stability to immobilize enemies and progressively damage them.
    

The Whip's primary strength is controlling multiple enemies rather than dealing overwhelming single-target damage.

**Combat Loop:**

Position → Vector Break → Gather → OMPI → Orbit → Entangle → Compress → Disengage

---

## 2. Normal Attacks

### Attack Range

- Medium-range weapon.
    
- All three stances have identical maximum attack range.
    
- Normal attacks can hit multiple enemies.
    
- Damage is calculated independently for each enemy based on distance.
    

### Distance-Based Damage

|Distance from Player|Damage|
|---|---|
|Point-blank|25%|
|0–75% of range|Smoothly increases toward 100%|
|75–100% of range|100%|

The final 25% of the Whip's attack range is called the **Tip Zone**.

### Tip Zone

Enemies hit within the Tip Zone have an increased chance of receiving a critical hit.

The bonus depends on the equipped stance.

The Tip Zone does not increase base damage beyond the established distance-based distribution.

### Multi-Target Damage Falloff

- First enemy receives 100% of its distance-adjusted damage.
    
- Subsequent enemies receive progressively less damage.
    
- Falloff resets with each normal attack.
    
- Minimum provisional multiplier: 20%.
    

Exact damage falloff remains undecided.

---

## 3. Attack Stances

|Stance|Attack Coverage|Tip Critical Chance|
|---|---|---|
|Default|Balanced|Standard bonus|
|Wide|Broad sweeping attacks|Lower bonus|
|Focused|Narrow, precise attacks|Higher bonus|

All three stances:

- Have the same maximum range.
    
- Use the same distance-based damage calculation.
    
- Can strike multiple enemies.
    
- Apply multi-target damage falloff.
    

Exact critical bonuses and attack-speed differences remain undecided.

---

## 4. Stability Tether

The Whip has a connector stone at its tip that generates a Stability tether.

The tether enables the Whip's signature Orbital Movement mechanic.

### Tether Activation

1. The player activates [[Vector Break]].
    
2. Vector Break passes through one or more enemies.
    
3. All enemies hit become part of the initial cluster.
    
4. The highest-priority enemy becomes the original anchor.
    
5. Enemies are immediately gathered around the anchor during Vector Break.
    
6. The player enters Orbital Movement Preparation Instance (OMPI).
    

Establishing the tether requires only the normal Vector Break charge.

**No additional Stability cost is required.**

### Anchor Selection Priority

When multiple enemies are hit during one Vector Break, the anchor is selected using:

1. **Enemy Tier:** Bosses take priority over elites, and elites over normal enemies.
    
2. **Maximum HP:** Among enemies of the same highest tier, the one with the greatest maximum HP becomes the anchor.
    
3. **Hit Order:** If both tier and maximum HP are identical, the first enemy hit wins.
    

The candidate anchor changes immediately when a higher-priority enemy is encountered during the same Vector Break.

### Initial Cluster

Enemies hit during Vector Break are gathered immediately, rather than gradually during OMPI.

They become immobilized but do not yet receive compression damage.

---

## 5. Orbital Movement Preparation Instance (OMPI)

OMPI is the stationary preparation state between Vector Break and Orbital Movement.

### Player Behavior

- The player remains completely stationary.
    
- Normal movement is disabled.
    
- The Stability tether remains connected.
    
- The player may initiate OM in either direction.
    
- Compatible abilities may be used without disconnecting the tether.
    
- Abilities that require disengagement terminate OMPI.
    

### Enemy Behavior

- Ordinary enemies in the initial cluster are already immobilized.
    
- They cannot move, attack, or activate abilities.
    
- Compression damage has not yet started.
    
- Elite and boss exceptions follow their resistance rules.
    

### OMPI Timer

**Provisional values:**

- Base duration: 5 seconds.
    
- Each additional enemy reduces the base preparation time by 5%.
    
- This equals 0.25 seconds per additional enemy.
    
- Minimum preparation duration: 1 second.
    

|Enemies Gathered|Preparation Duration|
|---|---|
|1|5.00 s|
|2|4.75 s|
|3|4.50 s|
|5|4.00 s|
|9|3.00 s|
|13|2.00 s|
|17 or more|1.00 s|

Gathering large groups leaves the player less time to begin swinging.

### Ability Interactions

Tether-compatible abilities cast during OMPI reset the preparation timer to its **reduced maximum**, not the original five seconds.

Example:

With nine enemies gathered, a compatible ability resets the OMPI timer to three seconds.

### Stability Consumption

OMPI has no passive Stability drain.

Abilities cast during OMPI may still consume Stability according to their individual costs.

### OMPI Expiration

If preparation expires before OM begins:

- The tether disconnects.
    
- The gathered enemies are released.
    
- The player exits OMPI.
    

The existing one-second enemy recovery rule applies to the released cluster.

---

## 6. Orbital Movement (OM)

Orbital Movement begins when the player chooses a direction during OMPI.

The player automatically swings around the central anchor or cluster.

### Base Duration

**10 seconds — provisional.**

- The OM timer starts when orbital movement begins.
    
- OM ends when its timer expires or Stability reaches zero, whichever happens first.
    
- Weapon Mastery can increase the OM duration.
    
- Certain recovery abilities can extend the remaining duration.
    

The exact regular Mastery progression remains undecided.

### Automatic Movement

Once initiated:

- OM continues automatically.
    
- The player does not need to hold an input.
    
- Compatible abilities can be cast while swinging.
    
- Compatible abilities do not return the player to OMPI.
    
- Only disengagement or specifically designed interruption abilities stop swinging.
    
- Reversing orbital direction does not disconnect the tether.
    

---

## 7. Orbital Movement Controls

Mouse and keyboard controls are always available simultaneously.

### Mouse Controls

- The cursor's position relative to the player determines orbital direction.
    
- The left or right side selects the corresponding direction.
    
- A visual indicator shows the currently available orbital direction.
    
- Left-click initiates OM.
    
- Cursor distance does not affect orbital speed or radius.
    

### Keyboard Controls

W/A/S/D can initiate OM.

A setting determines the directional reference:

- **Default:** Camera-relative.
    
- **Optional:** Player-facing-relative.
    

The appropriate directional key depends on the selected reference.

Only a single input is required to start swinging.

---

## 8. Orbital Radius

The timing of enemy contact during Vector Break determines orbital radius.

- Contact during the first half of Vector Break creates a larger orbit.
    
- Contact during the second half creates a smaller orbit.
    
- Once established, orbital radius remains consistent.
    
- Changes in cluster population do not alter the radius.
    

Exact orbital distances remain undecided.

---

## 9. Orbital Acceleration

The player begins Orbital Movement at a fixed base speed.

Speed increases according to completed orbital revolutions rather than elapsed time.

### Acceleration Progression

|Orbital Progress|Movement Speed Bonus|
|---|---|
|Start|+0%|
|1 complete revolution|+50%|
|2 complete revolutions|+100%|

Acceleration increases smoothly throughout each revolution.

The maximum bonus is +100%.

At maximum acceleration, the player moves at twice their original orbital speed.

Early gameplay may not provide enough OM duration to reach maximum acceleration.

### Direction Reversal

Reversing direction:

- Costs one Vector Break charge.
    
- Happens immediately.
    
- Does not disconnect the tether.
    
- Removes 50% of the accumulated orbital speed bonus.
    
- Does not affect base speed.
    
- Preserves orbital radius.
    

**Example:**

An accumulated +80% speed bonus becomes +40% after reversal.

The player then accelerates normally again.

This momentum loss is an intentional consequence that Weapon Mastery does not remove.

---

## 10. Stability Consumption

Stability consumption begins immediately when OM starts.

### Base Consumption

**Provisional values:**

- Base drain: 2% Stability per second.
    
- Each additional living entangled enemy: +1% Stability per second.
    
- Original anchor: No additional enemy cost.
    

The additional cost of a dead enemy disappears immediately.

### Speed Multiplier

Orbital acceleration increases the entire Stability drain.

|Speed Bonus|Total Drain Multiplier|
|---|---|
|+0%|×1.00|
|+50%|×1.25|
|+100%|×1.50|

The multiplier scales smoothly with accumulated speed.

**Example with five enemies total:**

Base drain: 2%  
Four additional enemies: 4%  
Combined drain: 6% per second

At maximum orbital speed:

6% × 1.5 = **9% Stability per second**.

### Reaching Zero Stability

When Stability reaches zero:

- OM ends normally.
    
- The tether disconnects.
    
- Gathered enemies enter their normal recovery period.
    
- No additional zero-Stability penalty is applied.
    

The Whip follows any separately established Instability rules, but reaching zero does not introduce a special Whip-specific penalty.

---

## 11. Enemy Entanglement

During Orbital Movement, the tether gathers additional enemies.

### Capture Area

The capture area is a **relatively narrow strip following the Stability tether**.

It extends from the point where the player holds the Whip to the central cluster.

- Enemies entering this strip are automatically caught.
    
- Precise visual rope contact is not required.
    
- The strip has a small collision tolerance.
    
- Enemies outside the strip remain unaffected, even when inside the orbital radius.
    
- As the player swings, the capture strip sweeps around the center.
    

### Initial Capture

Upon entering the capture area:

1. The enemy becomes entangled.
    
2. Compression damage begins immediately.
    
3. The enemy is gradually drawn toward the central cluster.
    
4. Once the enemy reaches the cluster, it increases the group's compression damage multiplier.
    

### Pulling Behavior

The movement should resemble a physical rope sweeping and tightening around enemies.

- Enemies are pulled inward progressively.
    
- Faster orbital speed increases pulling speed.
    
- Enemy gathering should look continuous rather than teleporting.
    
- The Stability tether behaves as though it has effectively unlimited length.
    

The exact pulling-speed relationship remains undecided.

---

## 12. Central Enemy Cluster

The Whip's cluster has a fixed central area.

### Enemy Distribution

- The central area does not grow with enemy count.
    
- The original anchor occupies its center.
    
- Additional enemies distribute themselves approximately evenly around it.
    
- With two enemies, they stand close together.
    
- As more enemies are captured, available spacing decreases.
    
- Large clusters may visually overlap as compression increases.
    

### Cluster Capacity

**No hard enemy-count limit is intended.**

The system is naturally limited through:

- Stability consumption.
    
- Orbital duration.
    
- Time needed to gather enemies.
    
- Individual enemy resistances.
    

A technical limit may be introduced if required for performance.

### Anchor Death

If the original anchor dies:

- If no other entangled enemies remain, OM ends.
    
- If other enemies survive, the cluster remains active.
    
- The surviving enemies collectively define the orbital center.
    
- No individual enemy needs to become a replacement anchor.
    
- Orbital radius remains unchanged.
    

The original anchor's special compression damage bonus does not transfer to another enemy.

### Cluster Movement

When the anchor is a moving boss, the orbital center follows the boss.

The player maintains the established orbital radius relative to the moving anchor.

---

## 13. Compression Damage

Compression damage represents the physical tension and tightening force of the Stability tether.

It is not intended to feel like a conventional status-based damage-over-time effect.

### Damage Timing

Compression damage is applied every **0.25 seconds**.

Four damage instances occur per second.

Each instance deals one quarter of the calculated damage per second.

### Damage Activation

- Vector Break gathering does not cause compression damage.
    
- OMPI does not cause compression damage.
    
- Compression begins when OM starts.
    
- Enemies caught after OM begins receive compression damage immediately upon entanglement.
    
- Compression pauses during Orbital Recovery when the tether is disconnected.
    

### Enemy Count Scaling

Compression damage increases as more enemies reach the central cluster.

- Enemies already in the cluster contribute to the damage multiplier.
    
- Newly caught enemies receive damage immediately.
    
- However, they contribute to the group's multiplier only after reaching the cluster.
    
- Dead enemies stop contributing immediately.
    

The exact increase per enemy remains undecided.

### Original Anchor Bonus

The original anchor receives **50% additional compression damage**.

Example:

If regular enemies receive 100 compression damage per second, the original anchor receives 150 damage per second.

If the anchor dies, the bonus disappears.

Other entangled enemies do not inherit this bonus.

### Damage Balancing

Still undecided:

- Base compression damage.
    
- Enemy-count scaling.
    
- Exact interactions with enemy defense.
    
- Elite and boss damage resistance.
    

---

## 14. Elite Enemy Interactions

Elites have different crowd-control properties from ordinary enemies.

### Pulling Resistance

- Ordinary enemies use the standard pulling speed.
    
- Physical size alone does not reduce pulling speed.
    
- Elite enemies are pulled more slowly toward the cluster.
    
- Exact elite pulling-speed penalties remain undecided.
    

### Intelligence-Based Counterattacks

Elite enemies may recognize and counter the Stability tether depending on their intelligence.

Less intelligent elites generally remain trapped.

More intelligent elites may launch counterattacks through the tether.

### Stability Disruptions

Intelligent elites can produce a visible Stability disruption that travels along the tether toward the player.

- The disruption does not automatically break OM upon activation.
    
- The player has an opportunity to respond.
    
- Reversing orbital direction does not avoid it.
    
- The player must disengage or use an appropriate tether-breaking ability to avoid the disruption.
    

Specific elite counterattacks are determined during individual enemy design.

---

## 15. Boss Interactions

Bosses can serve as Orbital Movement anchors.

### Boss Movement

- Bosses continue moving normally while serving as anchors.
    
- The player's orbit follows the boss's position.
    
- The established orbital radius remains consistent.
    
- Bosses may continue attacking and using abilities.
    
- Ordinary enemies may still be gathered around a boss.
    

### Boss Resistance

Bosses generally resist being pulled or immobilized.

They may also possess specialized mechanics that interfere with the tether.

Bosses are not intended to become permanently disabled simply because the player has established an orbit.

### Boss Stability Disruptions

Certain bosses can send visible disturbances through the tether toward the player.

These require disengagement or a suitable defensive ability.

Simply reversing orbital direction does not avoid the disturbance.

Exact counterattack patterns are enemy-specific.

---

## 16. Ending Orbital Movement

When OM ends normally:

- The tether disconnects.
    
- Gathered enemies remain at their final positions.
    
- No outward explosion or knockback occurs.
    
- The enemy cluster does not immediately disperse.
    

### Enemy Recovery

Captured ordinary enemies remain unable to act for **1 second** after release.

During this period they cannot:

- Move.
    
- Attack.
    
- Use abilities.
    

After the recovery period, enemies resume their normal behavior.

The concentrated cluster provides an opportunity for allied AoE attacks and follow-up combat.

---

## 17. Orbital Recovery

Orbital Recovery refers to special abilities that temporarily break the tether and subsequently restore Orbital Movement.

Individual abilities will determine their exact behavior.

### General Recovery Sequence

1. The player activates an applicable recovery ability.
    
2. The tether temporarily disconnects.
    
3. The player performs the ability.
    
4. The ability reconnects to the original anchor or surviving cluster.
    
5. OM resumes with an ability-specific duration extension.
    

### Duration

- The OM timer pauses during recovery.
    
- The recovery ability adds duration to the time remaining before disengagement.
    
- The timer resumes upon successful reconnection.
    

### Stability

- Regular OM Stability consumption pauses.
    
- The recovery ability may have its own Stability cost.
    
- The player must have sufficient Stability to activate it.
    
- If Stability is insufficient, the ability cannot activate.
    

### Orbital Direction and Momentum

Upon successful recovery:

- No directional input: Resume the previous direction.
    
- Same direction: Retain the full accumulated speed bonus.
    
- Opposite direction: Immediately reverse and lose 50% of the accumulated speed bonus.
    

Direction changes performed through the recovery ability do not require an additional VB charge.

### Anchor Preservation

Orbital Recovery returns to the original anchor or surviving cluster.

Switching to a completely different enemy requires Vector Break or another ability specifically designed for that interaction.

### Enemy Behavior During Recovery

- Clustered enemies remain immobilized.
    
- Compression damage pauses.
    
- The one-second enemy recovery period does not begin during an ongoing recovery.
    
- Enemies being pulled inward freeze at their current positions.
    
- Their movement may resume after reconnection.
    

Some abilities may change the player's position enough that partially gathered enemies are no longer in contact with the new tether path.

Those enemies may need to be caught again.

Their exact release and recovery behavior depends on the individual ability.

### Failed Recovery

If reconnection fails:

- OM ends.
    
- The tether remains disconnected.
    
- Gathered enemies begin their normal release recovery.
    
- No orbital duration extension is granted.
    

---

## 18. Whip Abilities — Future Design

Individual Whip abilities remain deliberately undecided.

They will be designed after the core identities of all BCU weapons are established.

This will help prevent overlapping weapon identities.

### Established Ability Categories

**Tether-Compatible Abilities**

Can be performed while maintaining the connection.

Depending on the ability, they may function during OMPI, OM, or both.

**Disengaging Abilities**

Disconnect the tether and may reposition the player.

**Orbital Recovery Abilities**

Disconnect temporarily and then reconnect to continue OM, potentially adding duration.

**Anchor-Switching Abilities**

May allow the player to transition between different anchors while swinging.

The concept of temporarily preserving an old cluster during anchor transitions is reserved for potential ability design rather than Weapon Mastery.

---

## 19. Weapon Mastery

The Whip follows the universal [[Weapon Mastery]] system.

Its two unique Mastery bonuses are established at levels 50 and 100.

Other standard Mastery rewards and gradual progression remain subject to the universal system.

### Level 50 — Tether Reinforcement

The Whip becomes more efficient at maintaining large groups of enemies.

**Effect 1: Orbital Duration Extension**

Each additional enemy gathered into the central cluster extends the remaining Orbital Movement duration by **0.5 seconds**.

- Each enemy can grant this extension only once per orbital session.
    
- Repeatedly capturing the same enemy cannot generate unlimited duration.
    
- The exact eligibility of enemies gathered during the initial Vector Break can be finalized during implementation.
    

**Effect 2: Stability Efficiency**

Additional enemy Stability consumption is reduced:

- Before Level 50: 1% per additional enemy per second.
    
- At Level 50: 0.75% per additional enemy per second.
    

The base 2% Stability drain is unchanged by this specific effect.

The speed multiplier still applies to the entire drain.

These values are provisional.

### Level 100 — Execution Pressure

The Whip becomes increasingly dangerous and efficient the longer Orbital Movement continues.

**Effect 1: Accelerating Compression Damage**

- Compression damage increases over time.
    
- Each subsequent increase becomes larger than the previous increase.
    
- Damage continues ticking every 0.25 seconds.
    
- There is no instant-execution threshold.
    
- The accumulated damage bonus resets when OM ends.
    

**Effect 2: Progressive Stability Efficiency**

- Stability consumption decreases progressively as the player maintains OM.
    
- The longer the player swings, the more efficient the tether becomes.
    
- At sufficiently sustained movement, Stability consumption may become very low.
    
- The efficiency bonus resets when OM ends.
    

Both effects are intended to reward uninterrupted, sustained Orbital Movement.

**Exact scaling remains undecided and requires playtesting.**

### Mastery Design Philosophy

Level 50 rewards gathering enemies and sustaining large clusters.

Level 100 rewards maintaining a successful orbit long enough to build enormous compression damage while reducing its resource cost.

Mastery should enhance the Whip's underlying mechanics rather than replace individual abilities.

---

## 20. Unresolved Design Details

### Numerical Balancing

- Exact orbital radii.
    
- Normal attack damage falloff.
    
- Tip Zone critical bonuses.
    
- Compression damage base values.
    
- Compression damage increase per gathered enemy.
    
- Elite pulling-speed resistance.
    
- Boss compression resistance.
    
- Regular Mastery-based OM duration increases.
    

### Level 100 Balancing

- Compression damage acceleration formula.
    
- Stability efficiency progression.
    
- Minimum Stability consumption.
    
- Potential practical upper limits.
    

### Ability Design

- Individual tether-compatible abilities.
    
- Disengagement abilities.
    
- Orbital Recovery ability effects.
    
- Anchor-switching abilities.
    
- Interactions with partially gathered enemies.
    
- Exact behavior of previously preserved clusters during anchor switching.
    

### Implementation Considerations

- Narrow tether capture collision.
    
- Physical-looking enemy pulling.
    
- Fixed-area cluster distribution.
    
- Large cluster performance.
    
- Moving boss anchors.
    
- Smooth transitions after anchor death.
    
- Clear visual telegraphs for tether disruptions.
    

---

## 21. Final Weapon Identity

**The Whip is a mobile battlefield-control weapon that turns positioning, gathered enemies, and sustained orbital momentum into increasing offensive pressure.**

Its strengths are:

- Multi-target control.
    
- Enemy gathering.
    
- Battlefield manipulation.
    
- Sustained compression damage.
    
- Orbital mobility.
    
- Powerful group combat.
    

Its weaknesses are:

- Stability consumption.
    
- Limited single-target effectiveness compared with dedicated damage weapons.
    
- Vulnerability to tether disruptions.
    
- Dependency on positioning and maintaining an orbit.
    
- Momentum loss when reversing direction.
    

### Mastery Evolution

**Base Whip:** Gather and control enemies through Orbital Movement.

**Level 50:** Maintain larger enemy groups more efficiently and extend orbital duration through successful gathering.

**Level 100:** Build accelerating compression damage while progressively reducing Stability consumption.

---

**Design Status: Identity Complete**

The Whip's core mechanics, combat identity, and unique Mastery directions have been established.

Individual abilities and numerical balancing will be revisited after the remaining BCU weapon identities are designed.