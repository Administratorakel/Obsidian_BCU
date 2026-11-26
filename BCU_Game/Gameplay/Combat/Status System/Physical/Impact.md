## Impact

### Core Mechanics

- Impact reduces the corresponding DEF of the enemy.
- Two variants:
    - **Physical Impact:** Reduces physical DEF.
    - **Magical Impact:** Reduces magical DEF.
- Both variants belong to the same status and share a maximum of 6 stacks.
- Unlike Puncture, Impact directly reduces DEF rather than increasing incoming DMG.
- Each stack is either physical or magical.
- Hybrid stacks do not exist.
- Impact can be applied to enemies with zero or negative DEF.

### Individual Stack Strength

- Each stack reduces the corresponding DEF by an individually calculated flat amount.
- The flat reduction depends on:
    - DMG of the triggering attack before mitigation.
    - Corresponding original DEF of the enemy, unaffected by DEF reductions.
- Higher DMG results in stronger flat DEF reduction.
- Higher original DEF results in weaker flat DEF reduction when the triggering DMG is identical.
- Critical hits do not increase the strength of Impact stacks.
- Each stack remembers its individually calculated flat reduction value and damage type.
- Flat DEF reduction can reduce DEF below zero.

### Stacking

- Maximum of 6 shared stacks.
- Physical and magical stacks can coexist.
- Every successful application refreshes the duration of the entire status.
- Upon receiving the sixth stack, Impact immediately transforms into Fracture.
- The sixth stack calculates its flat reduction normally before the transformation.
- All six flat reduction values are preserved during the transformation.

---

## Fracture

### Core Mechanics

- Fracture is the enhanced version of Impact.
- Begins at 0 stacks.
- Immediately grants:
    - 10% physical DEF reduction.
    - 10% magical DEF reduction.
- Remembers all six flat DEF reduction values from Impact, including their corresponding damage types.
- These remembered values remain effective but do not count as Fracture stacks.
- Only the actual Fracture stacks count toward the displayed stack number.

### Stacking

- Maximum of 6 shared Fracture stacks.
- Applying Impact to an enemy affected by Fracture instead applies a Fracture stack.
- Each new Fracture stack:
    - Replaces the oldest remembered unenhanced reduction value through FIFO (First In, First Out).
    - Provides its own individually calculated flat DEF reduction using the Impact formula.
    - Additionally provides 2.5% DEF reduction of its corresponding damage type.
- At six Fracture stacks, all six remembered values are enhanced.
- Further applications continue replacing the oldest Fracture stack through FIFO.
- Replacing a stack removes its previous flat and percentage-based reductions and introduces the newly calculated values.
- If Fracture has partially decayed, new applications prioritize replacing the oldest unenhanced value.
- Every successful application refreshes the entire status duration.

### Percentage-Based DEF Reduction

- Default reduction: 10% for both DEF types.
- Additional reduction per physical Fracture stack: 2.5% physical DEF.
- Additional reduction per magical Fracture stack: 2.5% magical DEF.
- Percentage-based reductions stack additively.

|Physical stacks|Magical stacks|Physical DEF reduction|Magical DEF reduction|
|--:|--:|--:|--:|
|0|0|10%|10%|
|1|0|12.5%|10%|
|2|1|15%|12.5%|
|3|3|17.5%|17.5%|
|6|0|25%|10%|
|0|6|10%|25%|

- Individual flat DEF reductions apply additionally to these percentages.

---

## DEF Calculation

### Calculation Order

1. Reference the enemy's original corresponding DEF.
2. Apply the percentage-based DEF reduction.
3. Apply the accumulated flat DEF reduction.
4. Calculate incoming DMG using the resulting effective DEF.

### Negative DEF

- Flat DEF reduction can reduce DEF below zero.
- Negative DEF increases incoming DMG of the corresponding damage type.
- Percentage-based DEF reduction references original positive DEF.
- Percentage-based DEF reduction has no effect on original DEF values of zero or below.
- Percentage-based reduction does not multiply negative DEF.

### DEF Reduction Cap

- Currently no dedicated DEF reduction cap for Impact or Fracture.
- The previously established 60% cap has been removed.
- Potential limitations will be reconsidered during numerical balancing.

---

## Duration & Decay

### General

- Impact and Fracture share the same base duration.
- Every successful application refreshes the entire status duration.
- Stacks decay gradually rather than disappearing simultaneously.
- The oldest stack decays first (FIFO).
- The duration timer restarts after each decay step.

### Fracture Decay

- Fracture gradually loses its enhanced stacks.
- Losing a Fracture stack:
    - Removes its additional 2.5% DEF reduction.
    - Preserves its individual flat DEF reduction and damage type as an unenhanced remembered value.
- The default 10% physical and magical DEF reductions remain active while Fracture exists.
- Fracture with 0 stacks still contains six remembered flat reduction values.
- Fracture (0) effectively represents the sixth stack of Impact.
- When Fracture (0) decays:
    - Fracture reverts to Impact with 5 stacks.
    - Both default 10% DEF reductions are removed.
    - The oldest remembered flat reduction value is removed.
    - The five remaining flat reduction values are preserved.

### Impact Decay

- Impact gradually loses its remaining stacks.
- Each decay step removes the oldest stack and its corresponding flat DEF reduction.
- The status disappears once no stacks remain.
- Applying Impact to an enemy with 5 Impact stacks transforms the status into Fracture (0) again.

### Status Lifecycle

- Ascending: Impact (1–5) → Fracture (0–6).
- Descending: Fracture (6–0) → Impact (5–1) → No status.
- There is no separate active Impact (6) state, as reaching six Impact stacks immediately triggers Fracture.

---

## Status Combinations

### Requirements

- Impact itself cannot participate in status combinations.
- Only its enhanced version, Fracture, enables status combinations.
- Combinations become available immediately upon reaching Fracture (0).
- No additional Fracture stacks are required.
- Despite requiring Fracture, these combinations are referred to as **Impact combinations**.

### Scaling

- Each Impact combination has its own individually designed scaling mechanics.
- Fracture stack count may influence the strength of a combination.
- There is no universal scaling formula for all combinations.

### Combined Status Behavior

- Combined statuses can have their own maximum duration and stacking mechanics.
- Fracture's existing flat and percentage-based DEF reductions provisionally remain effective while the combination is active.
- Continued Impact applications during a combination may contribute toward rebuilding Fracture.
- Upon reaching the combination's maximum duration, accumulated stacks may transition back into Fracture.
- The exact behavior is determined individually for each combination.

### Individual Combination Rules

The following mechanics will be decided separately for each Impact combination:

- Maximum duration.
- Maximum stacks.
- Stack scaling.
- Fracture stack consumption or preservation.
- Whether Fracture continues decaying or its decay is suspended.
- Behavior of additional Impact applications.
- Transition back into Fracture.
- Effects upon expiration.

---

## Lore

- Impact represents damage to the physical or magical defensive structure of an entity.
- Repeated applications increasingly compromise the structural integrity of the affected entity.
- Fracture represents an enhanced state in which the defensive structure has been significantly compromised.
- Gradual status decay represents the world attempting to stabilize the affected entity again.
- Continued Impact applications actively counteract this stabilization.
- The transition from Fracture back to Impact represents gradual restoration of structural integrity rather than immediate recovery.

---

## Placeholder Values

|Parameter|Value|
|---|---|
|Maximum Impact stacks|6|
|Fracture starting stacks|0|
|Maximum Fracture stacks|6|
|Default physical DEF reduction|10%|
|Default magical DEF reduction|10%|
|Additional DEF reduction per Fracture stack|2.5%|
|Maximum percentage-based reduction per DEF type through Fracture|25%|
|Maximum total DEF reduction|Undetermined|

---

## Remaining Open Questions

- Exact formula for calculating individual flat DEF reduction.
- Exact DMG calculation when DEF is negative.
- Base status duration.
- Final numerical balancing.
- Potential future DEF reduction limitations.
- Visual representation of physical and magical stacks.
- Visual representation of the transition between Impact and Fracture.
- Individual status combinations and their mechanics.