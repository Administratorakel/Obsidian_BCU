[[Skirmisher]] 
Weapon Mastery Progress Lv 100 bonus:


## 10. Whip

**Identity:** Stability tether and orbital crowd control

- Extended melee reach and sweeping attacks.
- Uses a connector stone at its tip to generate a Stability rope.

**Vector Break connection:**

- Player must Vector Break through an enemy.
- Contact in the first half of VB creates a larger orbit radius.
- Contact in the second half creates a smaller orbit radius.
- Player waits at the corresponding distance for a short preparation period.
- Left/right input initiates orbital movement.

**Swinging:**

- Connected enemy becomes the anchor.
- Rope continuously squeezes affected enemies.
- Additional enemies are automatically entangled.
- More enemies increase potential damage and Stability consumption.
- Swinging continuously drains Stability.
- Some abilities can be cast during swinging.
- Reversing orbit direction consumes one VB stack.

**Disengagement:**

- Certain abilities release the tether and launch the player.
- Using VB again can release the tether without consuming another stack.

**Bosses:**

- Can serve as anchors.
- Generally receive little single-target swing damage.
- Groups of enemies around bosses can make swinging effective.
- Some bosses visibly send Stability disruptions through the rope.
- Reaching the connector stone interrupts the player.

**Bulletjump:** Increased speed and greatly increased damage range.


# Whip — Weapon Identity

**BCU Game | Combat Philosophy: [[Skirmisher]]**

**Status:** Core weapon identity, normal attacks, Orbital Movement, and crowd control established. Balancing, abilities, and Weapon Mastery remain unfinished.

**Combat Identity:** Stability Tether & Orbital Crowd Control  
**Weapon Range:** Medium  
**Primary Strengths:** Positioning, multi-target attacks, enemy gathering, and sustained crowd control.

---

## 1. Core Identity

The Whip is a medium-range weapon that rewards positioning and controls groups of enemies through its Stability tether.

Its two defining mechanics are:

1. **Distance-Based Attacks:** Normal attacks deal progressively more damage toward the end of their range.
2. **Orbital Movement (OM):** The player connects the Whip to an enemy using [[Vector Break]], then orbits that enemy while gathering and compressing nearby enemies.

Most Whip abilities help position the player at an optimal attacking distance.

---

## 2. Normal Attacks

### Range and Damage

- Medium attack range.
- All three stances have the same maximum range.
- Normal attacks hit multiple enemies along the Whip's length.
- Each enemy's damage is calculated independently according to its distance from the player.
- Damage increases smoothly with distance.

### Distance-Based Damage Distribution

|Distance|Base Damage|
|---|---|
|0% (point-blank)|25%|
|0–75%|Smooth increase toward 100%|
|75–100%|100%|

The outermost **25% of the Whip's range is the Tip Zone**.

### Tip Zone

- Enemies hit in the Tip Zone gain an increased chance of receiving a critical hit.
- The Critical Chance bonus varies depending on the equipped stance.
- The Tip Zone does not grant additional base damage beyond the established damage distribution.
- The Tip Zone is deliberately broad to avoid excessive micropositioning.

### Multi-Target Damage Falloff

Normal attacks can strike multiple enemies.

- The first enemy receives 100% of its distance-adjusted damage.
- Each subsequent enemy receives progressively less damage.
- Falloff resets with every individual normal attack.
- A minimum damage multiplier prevents damage from becoming insignificant against large groups.

**Provisional minimum:** 20% of distance-adjusted damage.

Exact falloff percentages remain undecided.

---

## 3. Attack Stances

|Stance|Attack Coverage|Tip Critical Chance|
|---|---|---|
|Default|Balanced|Standard bonus|
|Wide|Broad sweeping attacks|Lower bonus|
|Focused|Narrow, precise attacks|Higher bonus|

All stances:

- Have identical maximum attack range.
- Use the same distance-based damage distribution.
- Can hit multiple enemies.
- Apply multi-target damage falloff.

Exact Critical Chance bonuses and stance-specific attack speeds remain undecided.

---

## 4. Stability Tether

The Whip features a connector stone at its tip that generates a Stability rope.

### Tether Activation

1. The player activates [[Vector Break]].
2. Vector Break contacts its first enemy.
3. The connector stone automatically attaches to that enemy.
4. The enemy becomes the tether's anchor.
5. The player moves into the Orbital Movement preparation position.

The tether remains attached until manually disconnected, broken by an applicable ability, or expired.

### Orbit Radius

The timing of the enemy's contact during Vector Break determines the orbital radius.

- Contact during the first half of VB produces a larger orbital radius.
- Contact during the second half produces a smaller orbital radius.

Exact distances remain undecided.

---

## 5. Orbital Movement Preparation Instance (OMPI)

OMPI is the preparation state before Orbital Movement begins.

### Movement

- The player is completely stationary during OMPI.
- Normal movement is disabled.
- The player remains connected to the anchored enemy.
- Orbital Movement can be initiated through mouse or keyboard input.
- Compatible abilities remain usable.

### Preparation Duration

- A preparation timer begins when the player reaches the ready position.
- If the timer expires, the tether automatically disconnects.
- Using a tether-compatible ability during OMPI resets the preparation timer.
- Abilities that disconnect the tether terminate OMPI.

**Preparation duration:** Undecided.

---

## 6. Orbital Movement Controls

Orbital Movement is abbreviated **OM**.

### Mouse Controls

- Mouse controls are always available.
- The cursor's position relative to the player determines orbital direction.
- A visual indicator displays the available direction.
- Left-click activates OM.
- Cursor distance does not affect movement speed or radius.

### Keyboard Controls

Keyboard controls are available simultaneously with mouse controls.

- W/A/S/D can initiate Orbital Movement.
- Direction is interpreted according to the selected control reference.

**Settings:**

- Camera-relative controls — Default.
- Player-facing-relative controls — Optional.

### Activation

- OM begins with a single directional input.
- The player does not need to hold the input.
- Orbital movement continues automatically.
- The player remains in the selected orbital direction until reversal or termination.

---

## 7. Orbital Acceleration

Orbital Movement starts at a fixed base speed.

Movement speed gradually increases as the player completes revolutions around the anchor.

### Acceleration Progression

|Completed Revolutions|Speed Bonus|
|---|---|
|0|+0%|
|1|+50%|
|2|+100%|

- Acceleration occurs smoothly throughout each revolution.
- Maximum orbital speed is reached after two complete revolutions.
- Base orbital speed never changes.
- Acceleration is based on orbital progress rather than elapsed time.
- Early gameplay may not allow enough OM duration to reach maximum speed.

### Direction Reversal

Reversing Orbital Movement:

- Costs **1 Vector Break charge**.
- Immediately reverses orbital direction.
- Does not disconnect the Stability tether.
- Removes 50% of the accumulated speed bonus.
- Does not reduce the base orbital speed.
- Allows acceleration to continue after reversal.

**Example:**

Current orbital speed bonus: +80%.

After reversal: +40%.

No deceleration phase is required.

---

## 8. Orbital Movement Duration

OM has two independent limitations:

1. Maximum Orbital Movement duration.
2. Available Stability.

**Orbital Movement ends when either runs out, whichever happens first.**

The OM timer begins when orbital movement starts, not when the tether initially connects.

### Stability Consumption

Stability is continuously consumed during OM.

Consumption depends on:

- **Base consumption:** Constant Stability drain while orbiting.
- **Entangled enemies:** Additional enemies increase Stability consumption.
- **Orbital speed:** Higher speed slightly increases Stability consumption.

The speed-related increase should remain small.

Exact consumption values and OM duration remain undecided.

---

## 9. Automatic Enemy Entanglement

The Stability tether automatically catches enemies it touches while the player orbits.

No additional input is required.

### Physical Behavior

The tether behaves like a rope of effectively unlimited length.

When the tether contacts an enemy:

1. The enemy becomes entangled.
2. The moving tether physically sweeps the enemy inward.
3. Continued orbital movement draws the enemy toward the central anchor.
4. The rope progressively tightens around the gathered enemies.
5. Additional enemies can become entangled and join the central group.

The intended appearance resembles a rope continuously wrapping around enemies, gradually compressing them toward the center.

### Enemy Gathering

- The original anchor remains at the exact center.
- Captured enemies gather around the anchor.
- Enemies are distributed approximately evenly.
- They retain some distance from other entities.
- The more enemies become entangled, the smaller the gaps between them become.
- Enemies should not simply overlap into a single position.

### Compression Damage

- Entangled enemies receive continuous squeezing damage.
- Compression becomes visually tighter as more enemies are captured.
- Exact damage and its relationship to enemy count remain undecided.

### Crowd Control

- Ordinary enemies cannot attack or use abilities while tightly entangled.
- Stronger enemies and bosses may resist the crowd-control effect.
- Specific enemy resistances remain undecided.

---

## 10. Ending Orbital Movement

When OM ends:

- The tether disconnects.
- Entangled enemies remain gathered around the anchor.
- Enemies are not launched outward.
- The clustered formation remains in place initially.

### Enemy Recovery

**Captured enemies require 1 second to recover.**

During this second:

- They cannot move.
- They cannot attack.
- They cannot activate abilities.

Afterward, they resume normal behavior and naturally disperse.

This creates opportunities for follow-up AoE attacks and allied abilities.

---

## 11. Boss Interactions

Bosses can serve as orbital anchors.

### Moving Bosses

- Bosses can move normally while tethered.
- The player's orbit follows the boss's position.
- Orbital radius remains consistent relative to the moving boss.
- Bosses may continue attacking and using abilities.
- Ordinary enemies can still gather around a moving boss.

### Boss Resistance

- Bosses generally resist direct crowd control.
- Bosses receive relatively little damage from single-target swinging.
- Gathering additional enemies around bosses can make OM more effective.

### Stability Disruptions

Certain bosses can send Stability disturbances along the tether toward the player.

- These disturbances are visibly communicated.
- Reversing orbital direction does not avoid them.
- The player must disconnect before the disturbance reaches them.
- Disengaging abilities can be used defensively.

Exact disruption timing and consequences remain undecided.

---

## 12. Whip Abilities

Whip abilities will be developed individually through the universal [[Archetypes]] system.

### Positioning Abilities

Most abilities should help players reach the Whip's optimal attacking distance.

### Tether-Compatible Abilities

Some abilities can be activated while the tether is connected.

- Certain abilities are compatible with OMPI.
- Certain abilities are compatible with OM.
- Compatible abilities preserve the tether connection.
- During OMPI, compatible abilities reset the preparation timer.

### Disengaging Abilities

Other abilities terminate the tether connection.

These abilities may:

- Reposition the player.
- Launch the player away from the anchor.
- Help avoid dangerous boss mechanics.

### Orbital Recovery Abilities — Proposed

Some disengaging abilities may allow the player to reconnect and resume Orbital Movement.

Possible behavior:

1. The player disengages using an ability.
2. The ability performs its movement or defensive action.
3. The player reconnects to the anchor.
4. Orbital Movement resumes.
5. The ability grants additional OM duration.

**Established direction:** Certain abilities can restore OM and extend its duration.

**Still undecided:** Which abilities provide this behavior, how much duration they restore, and whether orbital speed is retained.

---

## 13. Vector Break Identity

The Whip's Vector Break has increased speed and greatly increased damage range.

Its primary special interaction is establishing the Stability tether.

### Existing Features

- First enemy contacted becomes the anchor.
- Contact timing determines orbital radius.
- Direction reversal costs one VB charge.
- A subsequent VB can disengage the player without consuming an additional charge.
- Reversing direction does not disconnect the tether.

Further details will be established during ability design.

---

## 14. Weapon Mastery

The Whip's unique Weapon Mastery bonuses remain undecided.

Potential areas to explore later include:

- Orbital Movement acceleration.
- Orbital duration.
- Stability efficiency.
- Enemy compression.
- Tip Zone Critical Chance.
- Tether interactions.

These are **possibilities, not confirmed upgrades**.

Lv 50 and Lv 100 Mastery identities still need to be established.

---

## 15. Remaining Design Questions

### Orbital Movement

- Exact OMPI preparation duration.
- Exact OM duration.
- Base orbital speed.
- Exact orbit radii.
- What happens to acceleration when reconnecting through an ability.
- Whether acceleration can exceed +100% through Mastery.

### Stability

- Base Stability consumption.
- Additional consumption per entangled enemy.
- Speed-based consumption multiplier.

### Combat

- Multi-target damage falloff values.
- Tip Zone Critical Chance bonuses.
- Compression damage calculation.
- Resistance rules for stronger enemies.

### Abilities

- Which abilities can be used during OMPI.
- Which abilities can be used during OM.
- Which abilities disengage.
- Which abilities restore OM.
- How OM duration extensions work.

### Weapon Mastery

- Lv 50 unique mechanic.
- Lv 100 unique mechanic.
- General progression bonuses.

---

## Core Design Philosophy

**The Whip rewards precise positioning outside Orbital Movement and transforms the battlefield through controlled movement inside Orbital Movement.**

Its normal attacks reward maintaining an effective distance, while its Stability tether rewards surrounding enemies, gathering them, and controlling their positioning.

The Whip's strength comes from manipulating the battlefield rather than dealing overwhelming damage to a single enemy.

Its gameplay revolves around:

**Position → Connect → Orbit → Entangle → Compress → Disengage.**