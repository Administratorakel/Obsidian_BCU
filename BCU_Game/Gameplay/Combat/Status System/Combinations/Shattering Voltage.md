# Shattering Voltage — Status Combination

**Identity:** Instantaneous elemental burst with radial electrical propagation, positional obstruction and crowd control.  
**Combination:** [[Ice]] + [[Lightning]]  
**Category:** Elemental + Elemental  
**Trigger:** 6 Ice stacks + 6 Lightning stacks within the same eligible group pool.  
**Consumption:** Both contributing completed sets on the primary target.

## Core Mechanics
- Shattering Voltage occurs when accumulated electrical Charge violently fractures the frozen layer of the primary enemy.
- The primary target receives Physical Ice DMG and Magical Lightning DMG as two components of one burst event, followed by a one-second Lightning stun attempt.
- An instantaneous radial electrical discharge deals Magical Lightning DMG to exposed surrounding enemies.
- The electrical discharge loses DMG with distance from its origin.
- Exposed surrounding enemies receive guaranteed Lightning applications up to three ordinary building stacks, or a duration refresh if already at or above three.
- No Ice stacks are propagated.
- Ice fragments are not separate damaging projectiles.
- Shattering Voltage has no combination-specific cooldown.

## 1. Activation & Ownership
- Both contributing elemental sets must reach their six-stack thresholds within the same eligible group-owned pools.
- General group-exclusive combination requirements follow [[Status]].
- Whenever a compatible status reaches its sixth stack, the game checks for eligible combinations before resolving its ordinary sixth-stack payoff.
- If Shattering Voltage is eligible, it activates automatically and takes priority over the ordinary Freeze or Lightning Discharge payoff of the triggering set.
- Both contributing six-stack sets are consumed immediately upon activation, before the combination resolves its effects.
- Required stored offensive properties, contributors and applicable critical vulnerability are captured before consumption.
- An already completed Lightning set remains eligible while its shared enemy-side timer is active.
- An Ice set is eligible according to its established completed-set lifetime and immediate combination eligibility rules.
- Resistance, crowd-control immunity, Stability Barrier protection and invulnerability do not inherently prevent combination activation when the required sets are eligible.
- Shattering Voltage does not require the primary target to be visibly frozen.
- Different groups cannot combine their independent status pools.
- General combination priority rules follow [[Status]].

## 2. Status Consumption
### Ice
- Consume the entire contributing completed Ice set and its stored Ice DMG.
- Remove the effects dependent on that consumed set, including any associated Freeze or Slow that is active.
- A Stability Barrier prevents Ice crowd control, including Slow and Freeze; an Ice set can nevertheless satisfy combination eligibility before consumption.
- If the sixth Ice stack triggers Shattering Voltage, ordinary Freeze resolution is skipped. No separate Freeze protection cost is charged for that skipped payoff.
- The completed Ice set is consumed even if the primary target has complete Ice DMG Resistance or is invulnerable.

### Lightning
- Consume the entire contributing completed Lightning set and all its retained completed Charge.
- If the sixth ordinary Lightning stack triggers Shattering Voltage directly, consume the Charge of that contributing six-stack set instead of resolving ordinary Lightning Discharge.
- Do not consume a separate incomplete ordinary Lightning building set that coexists with the contributing completed set.
- Consumed Charge is not retained on the primary target.
- The primary target cannot receive propagated Lightning stacks from its own Shattering Voltage.
- Previously granted Lightning Discharge player buffs remain active for their remaining durations.
- Shattering Voltage does not grant a new Lightning Discharge speed buff.
- Both sets are consumed even if the primary target is invulnerable or the resulting damage is completely negated.

## 3. Primary Target Burst
### Physical Ice DMG
- The physical force of the frozen layer shattering deals Physical Ice DMG exclusively to the primary target.
- Base ice-shattering DMG scales with the stored Ice DMG of the consumed Ice set.
- The exact scaling coefficient remains subject to numerical balancing.
- The final Damage Category is Physical, regardless of the original contributing Ice stacks' Damage Categories.
- The final Damage Type is Ice.
- Apply current Physical DEF, Physical DMG vulnerability, Ice DMG Resistance and other applicable target-side modifiers according to [[Status]] and [[Damage Calculation]].

### Magical Lightning DMG
- The internal electrical discharge deals Magical Lightning DMG to the primary target.
- Base electrical DMG scales with the entire consumed Lightning Charge.
- The exact scaling coefficient remains subject to numerical balancing.
- The final Damage Category is Magical, regardless of the original contributing Lightning stacks' Damage Categories.
- The final Damage Type is Lightning.
- Apply current Magical DEF, Magical DMG vulnerability, Lightning DMG Resistance and other applicable target-side modifiers according to [[Status]] and [[Damage Calculation]].
- The primary target receives the full base electrical DMG without distance falloff.
- The same base electrical DMG is used for surrounding enemies before distance falloff.

### Unified Burst Event
- Both primary damage components belong to one instantaneous combination event.
- No deliberate delay exists between the two damage components or the radial discharge.
- Internally resolve Physical Ice DMG before Magical Lightning DMG, followed by the primary stun attempt.
- If the Physical Ice DMG is lethal, the Magical Lightning DMG is still calculated and applied as part of the same burst event.
- The primary target dying during the burst does not cancel the surrounding electrical discharge.
- Display separate damage numbers for Physical Ice DMG and Magical Lightning DMG.
- An enhanced visual representation may communicate that both damage numbers belong to the same mixed-DMG combination event.

## 4. Shared Critical Strike
- Shattering Voltage performs one new shared Critical Chance roll per activation.
- Use the triggering player's applicable Critical Chance and Critical DMG attributes.
- The result applies to both primary damage components and all surrounding electrical DMG from that activation.
- Individual damage components and surrounding enemies do not roll independently.
- Shattering Voltage is not a guaranteed critical strike.
- The primary target's applicable Final Critical Chance vulnerability from Ice/Freeze benefits the shared roll for the entire burst.
- If the sixth Ice stack directly triggers the combination before Freeze resolves, include the Final Critical Chance vulnerability that would ordinarily be available, provided resistance or applicable protection does not prevent that vulnerability.
- Capture the applicable vulnerability before consuming the Ice set.
- Do not grant the Freeze-derived critical vulnerability when the relevant effect is prevented, including by complete Ice resistance or applicable Stability Barrier protection.
- Surrounding enemies do not need to be frozen to benefit from the shared critical result.
- The primary target's applicable vulnerability is used for the shared roll; surrounding enemies do not make separate target-specific critical rolls.
- Existing stored Ice DMG and Lightning Charge retain their established offensive properties, including any original stored critical calculations.
- If the shared roll critically strikes, apply the triggering player's Critical DMG multiplier to the combination's damage and to newly propagated Charge as established below.
- Enemy-side defenses, resistances, vulnerabilities and barriers remain individually applicable to each receiving enemy.

## 5. Radial Electrical Discharge
### Origin & Radius
- The electrical discharge originates from the center of the primary target's hitbox.
- The primary target's own hitbox is excluded from wave obstruction calculations.
- The discharge has a fixed radius independent of stored Charge and primary target size.
- The exact radius remains subject to numerical balancing.
- There is no fixed maximum number of affected enemies.
- The effect is an instantaneous radial wave with obstruction, not a collection of separate projectiles or an unrestricted AoE that passes through enemies.
- Only hostile enemies are eligible to receive its damage and propagated Lightning applications.

### Cylindrical Hitboxes
- Initially use standing cylindrical enemy hitboxes, with size and position appropriate to the enemy's body.
- Enemies are eligible for the radial discharge when an exposed portion of their hitbox lies within the discharge radius, even if the hitbox center lies outside it.
- Larger enemy hitboxes obstruct a wider portion of the radial wave.
- Enemies can shield other enemies from the electrical discharge by standing between them and its origin.
- Solid environmental obstacles also obstruct the electrical discharge.
- Friendly entities do not obstruct the wave.
- Hostile enemies with complete Lightning DMG Resistance still obstruct the wave.
- Invulnerable hostile enemies still obstruct the wave.

### Binary Exposure
- Determine exposure and obstruction for the entire explosion before resolving its damage.
- An enemy is exposed if any unobstructed portion of its hitbox is reachable by the electrical wave within the discharge radius.
- A fully obstructed enemy receives neither electrical AoE DMG nor propagated Lightning applications or duration refreshes.
- A partially exposed enemy receives the same distance-adjusted DMG and applicable Lightning effects as a fully exposed enemy at the same distance.
- Do not apply an additional exposure-percentage DMG penalty.
- Exposure is binary: exposed or protected.
- An enemy killed by the explosion continues to obstruct the wave for that same explosion, because exposure was determined before damage resolution.
- Enemy damage processing order must not alter the exposure results of that explosion.

### Distance Falloff
- Measure distance from the origin to the closest exposed point of the receiving enemy's hitbox within the radius.
- Greater distance results in lower electrical AoE DMG.
- The exact falloff curve and minimum edge DMG remain subject to numerical balancing.
- Distance falloff affects only the direct electrical AoE DMG.
- Distance does not reduce inherited Charge, guaranteed stack count, Lightning duration or the duration of applicable Lightning crowd control.
- No separate multi-target damage reduction is introduced by this design; any additional universal multi-target rules, if applicable, require reconciliation during balancing.

## 6. Lightning Propagation
### Guaranteed Applications
- Every exposed surviving surrounding enemy is eligible for guaranteed Lightning applications belonging to the originating group.
- Shattering Voltage can only increase the receiving enemy's ordinary Lightning building set up to three stacks.
- Do not replace existing stacks through FIFO.
- Do not remove or alter the stored Charge of existing stacks.
- Do not reduce an existing stack count above three.
- Guaranteed propagation bypasses Status Chance Resistance.
- No additional ordinary Status Chance rolls occur from the electrical AoE damage.
- No Ice stacks are propagated.

| Existing ordinary Lightning stacks | New stacks | Resulting ordinary stacks |
|---:|---:|---:|
| 0 | 3 | 3 |
| 1 | 2 | 3 |
| 2 | 1 | 3 |
| 3 | 0 | 3 |
| 4 | 0 | 4 |
| 5 | 0 | 5 |

### Completed Lightning Sets
- A receiving enemy may possess an existing completed Lightning set alongside its ordinary building set.
- The completed set does not count toward the three-stack propagation limit.
- A receiving enemy with a completed set and zero ordinary building stacks can receive three ordinary stacks.
- Propagation does not consume, replace or recalculate the receiving enemy's retained completed Charge.
- The ordinary and completed sets retain the shared enemy-side timer behavior established in [[Lightning]].

### Duration
- Propagated Lightning uses a five-second base duration.
- Applying one, two or three propagated stacks refreshes the receiving group's shared Lightning duration to five seconds.
- An exposed surviving enemy with three or more ordinary Lightning stacks receives the same five-second duration refresh even though no new stacks or Charge are applied.
- The duration refresh also maintains an eligible coexisting completed Lightning set according to the shared timer rules.
- A duration refresh alone does not trigger a stun, Static Charge, Lightning Discharge or a status combination.
- No duration refresh is granted to fully obstructed enemies or to the primary target by its own explosion.

## 7. Propagated Charge Calculation
- Each generated Lightning stack inherits a fixed percentage of the total consumed Lightning Charge.
- The exact inherited percentage per stack remains subject to numerical balancing.
- Determine inherited Charge from the original consumed Charge, before receiving-enemy DEF, DMG Resistance, vulnerability or Stability Barrier mitigation.
- Do not calculate inherited Charge from the electrical DMG actually dealt.
- Distance falloff does not reduce inherited Charge.
- Every generated stack stores Magical Lightning Charge, irrespective of the original Damage Categories of the consumed Lightning set.
- All generated stacks from the same Shattering Voltage inherit the same Charge per stack.
- The amount per stack does not increase when fewer than three stacks can be applied.
- Unused potential applications do not redistribute their Charge to the stacks that are applied.
- The combination's shared critical result is inherited by generated Charge. On a critical strike, apply the triggering player's Critical DMG multiplier to the inherited Charge; do not make separate critical rolls for generated stacks.
- Preserve the original Lightning contributors' proportional Charge attribution, including through the inherited critical scaling.
- Complete Lightning DMG Resistance, invulnerability or full absorption of electrical DMG does not reduce the Charge stored by successfully applied stacks.

### Illustrative Charge Distribution
Assume a Shattering Voltage would generate 100 Charge per stack after applicable offensive and critical calculations. These are illustrative values only.

| Existing ordinary stacks | New stacks | Charge per new stack | Total new Charge |
|---:|---:|---:|---:|
| 0 | 3 | 100 | 300 |
| 1 | 2 | 100 | 200 |
| 2 | 1 | 100 | 100 |
| 3–5 | 0 | — | 0 |

- Generated stacks behave as ordinary Lightning stacks after application.
- They retain their generated Charge, Damage Category, attribution and applicable stored critical properties.
- They can subsequently contribute toward ordinary Lightning milestones, Lightning Discharge or eligible combinations through additional ordinary status applications.

## 8. Crowd Control
### Primary Target Stun
- Shattering Voltage attempts to stun the primary target for one second after resolving both primary damage components.
- This is a Lightning stun and follows the ordinary Lightning stun rules.
- Use the entire consumed Lightning Charge for the Stability Barrier protection cost calculation.
- The stun is not the ordinary sixth-stack Lightning Discharge payoff and grants no speed buff.
- Lightning DMG Resistance proportionally reduces the applicable stun duration and protection cost.
- Stun immunity or complete Lightning DMG Resistance prevents the effective stun without unnecessary Barrier consumption.
- A surviving primary target can be stunned even if its burst DMG was fully absorbed, subject to the separate stun protection check.

### Surrounding Enemy Stun
- Propagated stacks trigger the normal third-stack Lightning stun when an exposed enemy newly reaches three ordinary Lightning stacks.
- Base stun duration is 0.5 seconds.
- The applicable accumulated Charge includes all three current ordinary stacks, including pre-existing stacks.
- Ordinary Lightning resistance, immunity and Stability Barrier rules apply.
- An enemy already at three or more ordinary stacks receives no new stun from the duration refresh alone.
- No additional special AoE stun exists independently of reaching the third-stack threshold.
- Propagation cannot directly trigger fourth- or fifth-stack Static Charge interruptions or a sixth-stack Lightning Discharge.

## 9. Stability Barrier & Resistance Interactions
### Activation
- Stability Barrier protection does not prevent the required elemental stacks from satisfying combination eligibility.
- When the sixth stack completes a valid combination, consume the contributing sets immediately instead of first resolving the triggering set's standalone payoff.
- Stability Barriers protect against Ice Slow and Freeze; the absence of visible Freeze does not inherently prevent Shattering Voltage activation.

### Damage & Crowd-Control Order
- Resolve the primary target's Physical Ice DMG and Magical Lightning DMG before its one-second stun attempt.
- Resolve a surrounding enemy's electrical AoE DMG before applying its propagated stacks and attempting any third-stack stun.
- Apply ordinary Stability Barrier damage absorption rules to the damage components.
- A Barrier that survives the burst can separately protect against the subsequent stun.
- A Barrier destroyed by burst DMG cannot protect against the subsequent stun unless another applicable protection exists.
- If a Barrier breaks while paying the cost of protecting against a stun, that stun is still prevented, following [[Lightning]].
- Guaranteed Lightning propagation can occur even if all electrical DMG is absorbed.

### Primary Stun Protection Formula
Use the existing provisional ordinary Lightning stun formula:

`P_base = min(1, 0.50 + 0.000005 × Q_consumed)`

`P_effective = P_base × (1 − R_lightning)`

- `P_base` = base proportion of maximum Stability Barrier capacity consumed to prevent the stun.
- `Q_consumed` = entire stored Lightning Charge consumed by Shattering Voltage, including its previously stored critical calculations.
- `R_lightning` = applicable Lightning DMG Resistance as a decimal fraction.
- Protection costs reference maximum Barrier capacity rather than remaining Barrier capacity.
- The formula and numerical values remain provisional and follow future revisions to [[Lightning]] and [[Stability Barrier System]].
- Surrounding third-stack stuns use the corresponding ordinary Lightning protection formula and the receiving set's applicable accumulated Charge.

### Complete Resistance
- Complete Ice DMG Resistance negates the Physical Ice DMG and prevents its applicable Freeze-derived critical vulnerability, but does not inherently prevent combination activation or the electrical component.
- Complete Lightning DMG Resistance negates Magical Lightning DMG and effective Lightning crowd control, but does not inherently prevent activation, stack propagation, Charge storage or duration refresh.
- No protection cost is charged for a crowd-control effect already rendered ineffective by intrinsic immunity or complete resistance.
- Resistances do not change physical wave obstruction.

## 10. Death & Invulnerability
- The primary target's death does not cancel an already activated Shattering Voltage.
- Both primary damage components resolve as part of one burst event, even if the first is lethal.
- The surrounding electrical discharge still resolves from the captured primary origin.
- Surrounding enemies killed by electrical AoE DMG receive no subsequent Lightning applications or duration refresh.
- Enemies killed by the wave continue to provide their precomputed obstruction for that explosion.
- Invulnerable enemies can still receive guaranteed Lightning applications and applicable crowd control, following ordinary Lightning rules.
- Both contributing completed sets are consumed even if the primary target is invulnerable.
- Invulnerable hostile enemies can still physically obstruct the wave.

## 11. Multiplayer & Damage Attribution
- Shattering Voltage belongs to the group whose eligible Ice and Lightning sets are consumed.
- Propagated stacks and duration refreshes affect only the originating group's Lightning pool on each receiving enemy.
- Different groups retain independent status pools, completed sets, Charge and timers.
- Use the triggering player's critical attributes for the shared critical roll and Critical DMG multiplier.
- Attribute damage proportionally to the original contributors rather than using the previous fixed 50/50 combination split.
- Attribute the Physical Ice component according to the contributing Ice set's stored damage contributions.
- Attribute the Magical Lightning components, including surrounding electrical DMG, according to the contributing Lightning set's stored Charge contributions.
- Preserve proportional attribution when generating propagated Charge.
- Shared pools and multiple contributors do not duplicate damage.
- General contributor, aggro and loot rules follow [[Status]], [[Party]] and [[Participation and Loot]].

## 12. Recursive Combinations & Activation Limits
- Shattering Voltage cannot directly generate another status combination through its guaranteed Lightning propagation.
- The three-stack application limit prevents generated stacks from directly completing a six-stack Lightning set.
- Duration refreshes do not count as new threshold activations or combination triggers.
- Propagated Lightning stacks remain genuine ordinary stacks and can later participate in combinations when further eligible applications complete the required set.
- There is no combination-specific cooldown, chain-specific damage penalty or special restriction on subsequently activating a legitimately completed combination.
- Each later Shattering Voltage is a new activation with its own consumed sets, stored values, shared critical roll, origin and obstruction calculation.
- Earlier proposals allowing direct recursive Shattering Voltage, Arc Combustion or Neurotoxin activation through propagation are superseded by the three-stack limit.

## 13. Resolution Order
1. Apply the triggering sixth Ice or Lightning stack.
2. Check eligible combinations using the general status combination priority rules.
3. If Shattering Voltage is selected, capture the contributing stored Ice DMG, Lightning Charge, contributor information and applicable critical vulnerability.
4. Immediately consume both contributing completed sets; skip the triggering set's ordinary sixth-stack payoff.
5. Capture the primary hitbox center, surrounding enemy exposure, obstruction and applicable distances before explosion damage resolution.
6. Perform one shared critical roll using the triggering player's attributes and captured primary Ice/Freeze vulnerability.
7. Calculate the primary Physical Ice DMG, full base Magical Lightning DMG and distance-adjusted surrounding electrical DMG.
8. Resolve the primary Physical Ice DMG followed by Magical Lightning DMG as components of the same burst event, even if the first component is lethal.
9. Attempt the primary target's one-second Lightning stun if it is still an applicable target, using its current Barrier state.
10. Resolve the electrical AoE DMG against the precomputed exposed surrounding enemies.
11. For each surviving exposed surrounding enemy, apply guaranteed Lightning stacks up to three ordinary stacks, or refresh its Lightning duration if no stacks can be added.
12. Resolve ordinary third-stack stun attempts where the threshold is newly reached, using current target resistance, immunity and Barrier state.

All steps belong to one instantaneous combination activation, with no intentional inter-component delay. The exact processing order between different surrounding enemies must not change the precomputed wave exposure.

## 14. Lore & Visual Representation
- Accumulated electrical energy violently fractures the frozen layer of the affected entity.
- The internal discharge and physical shattering damage the primary enemy simultaneously in perceived gameplay.
- Electrical energy radiates outward from the primary enemy rather than launching physical ice projectiles.
- The discharge weakens with distance and is blocked by bodies and solid obstacles.
- The visual presentation should reflect applicable Ice protection and resistance rather than imply an active Freeze where none exists.
- The primary enemy receives two damage numbers, potentially linked through an enhanced mixed-DMG visual.
- A shared critical strike should communicate one powerful critical combination across its entire burst.
- Exact animation, VFX, audio and damage-number presentation remain subject to visual development.

## 15. Placeholder Values & Balancing

| Parameter | Value / design |
|---|---|
| Required Ice stacks | 6 |
| Required Lightning stacks | 6 |
| Consumed Ice set | Entire contributing set |
| Consumed Lightning Charge | Entire contributing set |
| Primary Ice DMG category/type | Physical Ice |
| Primary and AoE electrical DMG category/type | Magical Lightning |
| Ice-shattering DMG coefficient | Undetermined |
| Electrical discharge DMG coefficient | Undetermined |
| Primary electrical DMG | Full base electrical DMG |
| Shared critical rolls | 1 per activation |
| Primary stun | 1 second (provisional) |
| Surrounding third-stack stun | 0.5 seconds (ordinary Lightning) |
| Propagation limit | 3 ordinary building stacks |
| Propagated Charge percentage per stack | Undetermined |
| Propagated Lightning duration | 5 seconds (provisional) |
| Electrical discharge radius | Fixed; exact radius undetermined |
| Distance falloff curve / edge DMG | Undetermined |
| Distance falloff affects propagated Charge | No |
| Additional partial-exposure penalty | No |
| Enemy and environmental obstruction | Yes |
| Maximum AoE target count | No fixed cap |
| Additional Status Chance rolls | None |
| Direct recursive combinations | No |
| New Lightning Discharge buff | No |
| Combination-specific cooldown | None |

## Design Status
- Fundamental mechanics are established.
- Numerical coefficients, radius and falloff curve remain open for testing and balancing.
- Exact cylindrical hitbox exposure detection, burst-event handling and visual implementation remain technical development tasks.
- The existing general status system and Stability Barrier formulas remain subject to their own ongoing revisions.
