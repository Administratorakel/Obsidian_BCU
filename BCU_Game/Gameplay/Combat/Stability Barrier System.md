**Identity:** Additional defensive protection and temporary resistance against combat effects  
**Design Status:** Under development

---

## Core Mechanics

- Stability Barriers provide an additional defensive layer.
    
- Incoming applicable DMG reduces Barrier capacity before damaging HP.
    
- Stability Barriers can protect affected entities against specific crowd-control effects.
    
- Crowd-control protection consumes Barrier capacity.
    
- Barrier capacity and the ordinary Stability resource are treated as separate concepts.
    
- Abilities may consume Stability to generate Stability Barriers.
    

See:

- [[Stability]]
    
- [[Stability Barrier]]
    
- [[Damage Calculation]]
    
- [[Status]]
    

---

## Barrier Capacity

- Each Barrier possesses a maximum capacity.
    
- Each Barrier possesses a current remaining capacity.
    
- Percentage-based protection costs reference maximum Barrier capacity.
    
- A Barrier breaks once its remaining capacity reaches zero.
    
- Exact Barrier capacity formulas remain undecided.
    

---

## Crowd-Control Protection

### General Principle

- Stability Barriers can prevent applicable crowd-control effects by consuming a percentage of maximum Barrier capacity.
    
- Crowd-control protection is not free immunity.
    
- Stronger stored status DMG can increase the required protection cost.
    
- Different crowd-control effects can possess different base costs.
    
- The exact list of Barrier-protected effects remains individually defined.
    

### Protection Priority

1. Check intrinsic immunity.
    
2. Check applicable status resistance.
    
3. Determine whether the incoming effect requires Barrier protection.
    
4. Calculate the applicable protection cost.
    
5. Consume Barrier capacity.
    
6. Prevent the incoming effect.
    

### Intrinsic Immunity

- If an entity is intrinsically immune to an incoming effect, Barrier protection is unnecessary.
    
- No Barrier capacity is consumed.
    
- Immunity takes priority over Barrier protection.
    

### Complete Resistance

- If applicable resistance completely prevents an incoming effect, no Barrier capacity is consumed.
    

### Insufficient Capacity

If the required protection cost exceeds the remaining Barrier capacity:

- Consume all remaining Barrier capacity.
    
- Break the Barrier.
    
- Successfully prevent the incoming crowd-control effect.
    
- Do not transfer excess protection cost into HP DMG.
    
- Subsequent effects are no longer protected if no Barrier remains.
    

A Barrier can therefore prevent one final crowd-control effect even if its remaining capacity is insufficient to pay the full cost.

---

## Provisional Protection Formula

### General Structure

P_base = min(1, B + K × D_stored)

Where:

- P_base = proportion of maximum Barrier capacity consumed.
    
- B = effect-specific base protection cost.
    
- K = stored DMG scaling coefficient.
    
- D_stored = applicable accumulated stored DMG.
    

### Resistance Adjustment

P_effective = P_base × (1 − R)

Where:

- R = applicable status resistance, expressed as a decimal fraction.
    

### Capacity Consumption

Barrier Capacity Consumed = Maximum Barrier Capacity × P_effective

The actual capacity consumed cannot exceed the remaining Barrier capacity.

The formula's final implementation, resistance ordering and rounding remain subject to testing.

---

## Lightning Protection

See [[Lightning]].

### Ordinary Stuns

Applies to:

- Third-stack Lightning stun.
    
- Sixth-stack Lightning Discharge stun.
    

Provisional values:

- Base protection cost: 50%.
    
- Stored Charge coefficient: 0.000005.
    
- Maximum protection cost: 100%.
    

Formula:

P_stun = min(1, 0.50 + 0.000005 × D_stored)

### Static Charge Interruptions

Applies to:

- Fourth-stack Lightning animation interruption.
    
- Fifth-stack Lightning animation interruption.
    

Provisional values:

- Base protection cost: 0%.
    
- Stored Charge coefficient: 0.000005.
    
- Maximum protection cost: 100%.
    

Formula:

P_interrupt = min(1, 0.000005 × D_stored)

### Applicable Charge

|Lightning Effect|Stored Charge Used|
|---|---|
|Third-stack stun|Current accumulated Charge|
|Fourth-stack interruption|Current accumulated Charge|
|Fifth-stack interruption|Current accumulated Charge|
|Sixth-stack Discharge stun|Strongest retained completed Charge|

- Stored Charge includes applicable critical calculations.
    
- Lightning DMG Resistance reduces the resulting protection cost.
    
- Complete Lightning DMG Resistance prevents Barrier consumption.
    
- Intrinsic stun immunity prevents Barrier consumption against ordinary stuns.
    
- Stun immunity does not inherently prevent Static Charge interruptions.
    
- Blocking Lightning crowd control does not prevent Discharge buff distribution.
    

---

## Physical Status Interactions

### Slash & Laceration

See [[Slash]].

- Slash and Laceration damage Stability Barriers before HP.
    
- Neither inherently bypasses Stability Barriers.
    
- Corresponding DEF penetration remains governed by Slash's individual mechanics.
    
- Detailed Barrier mitigation interactions remain undecided.
    

### Impact & Fracture

See [[Impact]].

- Impact and Fracture reduce corresponding enemy DEF.
    
- Whether Stability Barriers possess independent DEF or reference the affected entity's DEF remains undecided.
    

### Puncture & Breach

See [[Puncture]].

- Breach increases applicable incoming attack DMG against Stability Barriers.
    
- Additional barrier-specific DMG does not carry over into HP DMG.
    
- Exact additional Barrier DMG remains undecided.
    
- The ordinary corresponding DMG vulnerability remains applicable.
    
- Individual Breach combinations may introduce additional Barrier interactions.
    

---

## Elemental Status Interactions

### Fire

See [[Fire]].

- Burn and Combustion damage Stability Barriers before HP.
    
- Neither inherently bypasses Stability Barriers.
    
- Target-side Barrier mitigation does not reduce stored Heat.
    
- Detailed Heat, Burn and Combustion interactions remain subject to the general damage calculation system.
    

### Ice

See [[Ice]].

The following remain undecided:

- Protection against ordinary Slow.
    
- Protection against Freeze.
    
- Protection against enhanced Slow.
    
- Whether Barrier protection affects Final Critical Chance vulnerability.
    
- Potential Ice-specific Barrier protection costs.
    

### Lightning

See the established Lightning protection rules above.

### Poison

See [[Poison]].

Detailed Poison interactions remain undecided.

---

## Design Philosophy

- Stability Barriers should provide meaningful protection without granting unlimited crowd-control immunity.
    
- Protecting against stronger effects can require sacrificing significant Barrier capacity.
    
- Breaking an enemy's Barrier creates opportunities for subsequent crowd-control effects.
    
- Intrinsic resistance and immunity prevent unnecessary Barrier consumption.
    
- Offensive status builds can specialize in pressuring Stability Barriers.
    
- Different statuses can interact with Barriers in different ways.
    

---

## Remaining Open Questions

### Barrier Fundamentals

- Maximum Barrier capacity formula.
    
- Barrier creation sources.
    
- Stability resource consumption.
    
- Barrier duration.
    
- Barrier regeneration.
    
- Multiple Barrier instances.
    
- Barrier replacement and stacking.
    
- Barrier ownership.
    
- Player and enemy Barrier differences.
    

### Damage Calculation

- Barrier-specific DEF.
    
- Interaction with General Defense.
    
- Interaction with Physical and Magical DEF.
    
- Interaction with DMG resistance.
    
- Interaction with DMG vulnerability.
    
- Ordinary DMG overflow into HP.
    
- Stability Barrier penetration.
    
- Exact Breach bonus.
    
- Barrier-specific critical DMG interactions.
    

### Crowd-Control Protection

- General protection cost formula.
    
- Incorporating crowd-control duration into protection costs.
    
- Effect-specific base protection costs.
    
- Effect-specific stored DMG coefficients.
    
- Resistance calculation order.
    
- Protection against Ice effects.
    
- Protection against other crowd-control mechanics.
    
- Resolution of simultaneous protected effects.
    
- Barrier break feedback.
    

### Additional Mechanics

- Interaction with active Shield blocking.
    
- Interaction with [[Vector Break]].
    
- Interaction with Instability.
    
- Interaction with status combinations.
    
- Barrier restoration.
    
- Barrier-specific abilities and weapon mechanics.
    

---

## Design Status

The initial Stability Barrier protection framework is established through Lightning's crowd-control interactions.

The general Barrier creation, capacity, mitigation, regeneration and damage-overflow systems remain under development.

All currently established numerical formulas are provisional and intended for early testing.