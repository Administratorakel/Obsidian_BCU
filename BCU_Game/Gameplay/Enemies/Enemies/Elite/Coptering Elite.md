
**Status:** Core concept established — formulas and balancing partially provisional.

**Related:** [[Coptering]], [[EXP]], [[Archetypes]], [[Enemy Combat Behavior]]

## Overview

The Coptering Elite is a special elite enemy capable of stealing knowledge from defeated players.

It becomes progressively stronger through accumulated victories and stolen EXP.

Unlike ordinary elites, its power depends partly on its history of encounters with players.

A Coptering Elite may become an exceptionally powerful opponent if it survives long enough.

Players can deliberately allow it to grow stronger in pursuit of greater rewards.

This risk-versus-reward interaction is intentional.

## 1. Victories

A **Victory** represents a player defeated by the elite.

The elite accumulates victories over time.

Victories influence the probability that its departure chance will increase.

The number of victories is visible to players.

## 2. Stolen EXP

When a player dies while affected by Coptering, the elite steals 5% of the player's current EXP progress toward the next level.

The elite accumulates stolen EXP from multiple players.

Stolen EXP contributes toward the elite's progression.

Defeating higher-level players may provide substantially more EXP, allowing faster progression.

## 3. Milestones

**Milestones are the elite's progression levels, gained by accumulating stolen EXP.**

They are not departure milestones.

The number of Milestones is visible to players.

### Ability Acquisition

The elite unlocks random player Archetype abilities as it accumulates knowledge.

The abilities may adapt depending on the weapon used by the elite.

For example, the same acquired Archetype ability might behave differently when used with a sword rather than a hammer.

Specific adaptations have not been designed.

### Milestone Progression

The intended progression becomes increasingly expensive.

A simplified example:

- First additional ability: approximately one ordinary victory's worth of EXP.
- Second additional ability: approximately two further ordinary victories' worth of EXP.
- Later abilities require increasing amounts of stolen EXP.

These victory counts are illustrative equivalents, not fixed requirements.

A sufficiently high-level player may provide enough stolen EXP to unlock multiple Milestones at once.

**Stolen EXP determines progression, not the victory count alone.**

Exact EXP thresholds remain undecided.

## 4. Power Growth

The elite becomes stronger through accumulated knowledge.

Possible forms of growth include:

- Increased combat strength.
- Additional Archetype abilities.
- Weapon-dependent adaptations of acquired abilities.

Exact numerical stat scaling remains undecided.

The elite should eventually become a genuinely formidable opponent.

A highly developed Coptering Elite may require cooperation between players to defeat.

Map-dependent progression limits may be introduced for balancing.

However, the general intention is that its growth can appear practically limitless.

## 5. Loot Scaling

Stronger Coptering Elites are intended to provide better rewards.

The precise loot types are undecided.

The relationship between Milestones, Victories, and loot quality also requires balancing.

### Intentional Feeding

Players are allowed to deliberately strengthen a Coptering Elite by sacrificing victories.

This strategy is intentionally risky.

A stronger elite may provide better rewards, but it may also become too difficult to defeat.

Additionally, it may leave before the players obtain those rewards or recover their stolen EXP.

This is an intended risk-versus-reward mechanic.

## 6. Departure System

A Coptering Elite may leave after defeating players.

When it leaves:

- The elite disappears.
- Its accumulated stolen EXP becomes permanently unrecoverable.
- Players lose the opportunity to defeat that particular elite for its rewards.

The departure system contains two separate probabilities.

### A. Departure Growth Chance

After victories, the elite has a chance to increase its departure probability.


`Growth Chance = min(10% × (Victories - 1), 95%)`

This interpretation produces:

|Victory|Chance to Increase Departure Probability|
|---|---|
|1|0%|
|2|10%|
|3|20%|
|4|30%|
|5|40%|
|6|50%|
|7|60%|
|8|70%|
|9|80%|
|10|90%|
|11+|95%|

The chance never reaches 100%.

From the eleventh victory onward, it remains capped at 95%.

Therefore, even after many victories, the elite retains a small chance of not increasing its departure probability.

**Note:** The formula above reflects the agreed example in which the second victory has a 10% growth chance.

### B. Departure Probability

The proposed increase is based on the elite's Milestone level:

`Departure Increase = 5% × Milestones`

Examples:

|Milestones|Proposed Increase|
|---|---|
|1|5 percentage points|
|2|10 percentage points|
|3|15 percentage points|
|5|25 percentage points|
|10|50 percentage points|
|20|100 percentage points|

The actual departure probability cannot exceed 100%.

At 20 Milestones, a successful departure-growth roll can bring the departure probability to 100%.


 Additive

A successful growth roll adds the calculated amount to the existing departure probability.

Example:

Existing departure chance: 20%

Current Milestones: 3

Successful growth roll: +15 percentage points

New departure chance: 35%


### Timing

The working example assumes that:

1. The elite defeats a player.
2. The existing departure probability determines whether it leaves.
3. If it remains, a growth roll may increase the departure probability for its next victory.

The exact order of operations has not been finalized.

## 7. Player Information

Players can see:

- The elite's accumulated Victories.
- The elite's accumulated Milestones.
- An icon communicating the possibility of departure.

Players cannot see the exact departure probability.

The icon should communicate risk without revealing the underlying numerical chance.


## 8. Recovering Stolen EXP

If the original victim defeats the elite, their stolen EXP becomes recoverable.

If another player defeats the elite, previous victims can return to the enemy's death location.

They must recover their knowledge within a limited time.

After that period, unrecovered knowledge disappears.

While the elite remains alive, it retains stolen EXP indefinitely.

## 9. Design Philosophy

The Coptering Elite should create a distinctive encounter where:

- Its history matters.
- Players can recognize its growing strength.
- Greater power may lead to greater rewards.
- Deliberately strengthening it is possible.
- Cooperation may become necessary.
- The possibility of departure creates meaningful risk.
- Players possess useful information without knowing the exact outcome.

The enemy should remain challenging even after players understand its mechanics.

## Undecided

- Exact Milestone EXP thresholds.
- Exact stat scaling.
- Specific Archetype abilities and adaptations.
- Maximum progression by map.
- Loot types and reward scaling.
- Departure roll timing.
- Visual design of the departure indicator.
- EXP recovery time limit.

G(V)=\min(10%(V-1),95%)

A successful growth roll adds:

Delta D=5% * M

Therefore:

D_{new}=min(D_{old}+5%M,100%)

Where:

- \(V\) = accumulated victories.
- \(M\) = accumulated Milestones.
- \(D\) = departure probability.

This captures your confirmed additive behavior.

[[Boracle's Existential Crisis]]