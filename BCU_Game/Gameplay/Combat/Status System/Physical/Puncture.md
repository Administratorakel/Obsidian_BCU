# Puncture & Breach

## Puncture

### Core Mechanics

- Puncture increases incoming DMG of the corresponding damage type.
- Two variants:
    - **Physical Puncture:** Increases physical DMG taken.
    - **Magical Puncture:** Increases magical DMG taken.
- Both variants belong to the same status and share a maximum of 6 stacks.
- Unlike Impact, Puncture does not directly reduce DEF.
- Each stack is either physical or magical.
- Hybrid stacks do not exist.

### Individual Stack Strength

- Each stack increases incoming DMG of its corresponding type by 2.5%.
- Individual stack strength is fixed.
- Stack strength is independent of:
    - DMG of the triggering attack.
    - Enemy DEF.
    - Critical strikes.
- Each stack remembers its corresponding damage type.
- DMG vulnerability from individual stacks accumulates additively.

### Stacking

- Maximum of 6 shared stacks.
- Physical and magical stacks can coexist.
- Every successful application refreshes the duration of the entire status.
- Upon receiving the sixth stack, Puncture immediately transforms into Breach.
- All six vulnerability values and their corresponding damage types are preserved during the transformation.

---

## Breach

### Core Mechanics

- Breach is the enhanced version of Puncture.
- Represents six accumulated Puncture stacks.
- Exists as a single enhanced status.
- Unlike Fracture, Breach does not have additional enhanced stack progression.
- Preserves the DMG vulnerability of all six Puncture stacks.
- Increases incoming DMG against Stability Barriers.
- Enables Puncture status combinations.

### Stacking & Replacement

- Breach remembers all six underlying Puncture stacks and their corresponding damage types.
- Further successful Puncture applications:
    - Replace the oldest remembered Puncture stack through FIFO (First In, First Out).
    - Refresh the entire status duration.
- The total number of remembered stacks never exceeds six.
- Replacing stacks allows the distribution of physical and magical DMG vulnerability to change while Breach remains active.

### DMG Vulnerability

- Each remembered physical stack provides 2.5% physical DMG vulnerability.
- Each remembered magical stack provides 2.5% magical DMG vulnerability.
- Reaching Breach does not inherently increase the existing DMG vulnerability beyond the six accumulated Puncture stacks.

|Physical stacks|Magical stacks|Physical vulnerability|Magical vulnerability|
|--:|--:|--:|--:|
|6|0|15%|0%|
|5|1|12.5%|2.5%|
|4|2|10%|5%|
|3|3|7.5%|7.5%|
|2|4|5%|10%|
|1|5|2.5%|12.5%|
|0|6|0%|15%|

### Stability Barrier DMG

- Breach increases incoming DMG against Stability Barriers.
- The additional barrier DMG applies to all attacks against the affected entity, regardless of:
    - Weapon type.
    - Damage type.
    - Whether the attack applies another Puncture stack.
    - Which player attacks the affected entity.
- Additional barrier-specific DMG cannot carry over into HP DMG when a Stability Barrier is destroyed.
- Regular DMG vulnerability remains applicable.
- The exact additional barrier DMG value is undecided.
- Further interactions will be established when designing the Stability Barrier system.

---

## DMG Calculation

### Calculation Order

1. Calculate incoming DMG.
2. Apply the corresponding DEF calculations.
3. Apply the corresponding DMG vulnerability from Puncture or Breach.

- Puncture and Breach amplify DMG after DEF calculations.
- DMG vulnerability stacks additively with vulnerability from other sources.
- Physical vulnerability only affects physical DMG.
- Magical vulnerability only affects magical DMG.

### Affected Damage Sources

- Normal attacks.
- Heavy attacks.
- Abilities.
- Damage over Time (DoT).
- Other corresponding status DMG.
- Application to all corresponding damage sources is provisional.

### Dynamic Vulnerability

- DMG vulnerability is calculated dynamically.
- Every incoming damage instance references the currently active Puncture or Breach values.
- Existing DoT effects dynamically adjust their DMG when vulnerability changes.
- DMG vulnerability is not permanently recorded when a DoT is initially applied.

### Application Order

- The attack that applies a new Puncture stack does not benefit from that newly applied stack.
- Newly applied vulnerability affects subsequent damage instances.
- This rule is provisional and may be reconsidered when establishing status combinations.

---

## Duration & Decay

### General

- Puncture and Breach follow the gradual stabilization principle established for Impact and Fracture.
- Every successful application refreshes the entire status duration.
- Stacks decay gradually rather than disappearing simultaneously.
- The oldest stack decays first (FIFO).
- The duration timer restarts after each decay step.

### Breach Decay

- When Breach expires:
    - Breach reverts to Puncture with 5 stacks.
    - The oldest remembered Puncture stack is removed.
    - The remaining five vulnerability values and their damage types are preserved.
    - The additional Stability Barrier DMG is removed.
    - Access to Puncture status combinations is lost.

### Puncture Decay

- Puncture gradually loses its remaining stacks.
- Each decay step removes the oldest stack and its corresponding 2.5% DMG vulnerability.
- The status disappears once no stacks remain.
- Applying Puncture to an enemy with 5 Puncture stacks immediately transforms the status into Breach again.

### Status Lifecycle

- Ascending: Puncture (1–5) → Breach.
- Descending: Breach → Puncture (5–1) → No status.
- There is no separate active Puncture (6) state.
- There are no additional Breach stacks.

---

## Status Combinations

### Requirements

- Puncture itself cannot participate in status combinations.
- Only its enhanced version, Breach, enables status combinations.
- Combinations become available immediately upon reaching Breach.
- Despite requiring Breach, these combinations are referred to as **Puncture combinations**.

### Combined Status Behavior

- Existing DMG vulnerability remains active in some form during status combinations.
- Additional Stability Barrier DMG may be preserved, enhanced or modified depending on the individual combination.
- The exact behavior is determined individually for each combination.

### Individual Combination Rules

The following mechanics will be decided separately for each Puncture combination:

- Maximum duration.
- Maximum stacks.
- Scaling mechanics.
- DMG vulnerability behavior.
- Stability Barrier DMG behavior.
- Breach consumption or preservation.
- Status decay behavior.
- Behavior of additional Puncture applications.
- Transition back into Breach or Puncture.
- Effects upon expiration.

### Natural Status Synergies

- Puncture can naturally amplify DMG dealt by other statuses without triggering an actual status combination.
- These synergies do not require Breach.
- Natural status synergies are distinct from actual status combinations.

---

## Visual Representation

- Physical Puncture stacks are represented by a grayish color.
- Magical Puncture stacks are represented by a pinkish color.
- One shared status icon displays the total stack count.
- Color distribution indicates the number of physical and magical stacks.
- Breach is displayed as a single enhanced status rather than displaying six active Puncture stacks.
- The exact visual representation of the underlying vulnerability distribution during Breach remains undecided.

---

## Lore

- Puncture represents openings created within the physical or magical structure of an entity.
- These openings increase the entity's vulnerability to corresponding incoming DMG.
- Repeated applications increasingly compromise the entity's structural integrity.
- Breach represents a sufficiently compromised structure that Stability Barriers become more vulnerable to incoming attacks.
- Gradual status decay represents the world attempting to stabilize the affected entity again.
- Continued Puncture applications actively counteract this stabilization.

---

## Placeholder Values

|Parameter|Value|
|---|---|
|Maximum Puncture stacks|6|
|Physical vulnerability per physical stack|2.5%|
|Magical vulnerability per magical stack|2.5%|
|Maximum vulnerability of one damage type|15%|
|Additional Breach stack progression|None|
|Additional Stability Barrier DMG|Undetermined|
|Base status duration|Undetermined|

---

## Remaining Open Questions

- Base status duration.
- Exact additional Stability Barrier DMG.
- Detailed interactions with the Stability Barrier system.
- Final numerical balancing.
- Potential limitations on accumulated DMG vulnerability from multiple sources.
- Final damage source eligibility.
- Final status application order when considering combinations.
- Visual representation of Breach.
- Individual status combinations and their mechanics.