### Stability Barrier
**Archetype:** Consumes Stability to provide temporary defensive protection. Supports survival at the cost of an offensive resource.

**Sword interpretation — Guarding Edge (suggestion):** The swordsman assumes a brief guarded stance, manifesting a protective Stability Barrier around the body. Unlike a Shield's active block, this is a temporary ability-based defense.
[[Stability Barrier]], consume Stability Energy to create a protective barrier.
	- Defensive survival
	- Resource management



## Stability Barrier Interactions

### Core Mechanics

Stability Barriers protect against:

- Third-stack Lightning stuns.
    
- Fourth-stack Static Charge interruptions.
    
- Fifth-stack Static Charge interruptions.
    
- Sixth-stack Discharge stuns.
    

Protection consumes a calculated percentage of maximum Stability Barrier capacity.

See [[Stability Barrier System]].

### Protection Priority

1. Determine whether the enemy is intrinsically immune to the incoming effect.
    
2. Determine whether Lightning DMG Resistance renders the effect ineffective.
    
3. If protection is unnecessary, do not consume Barrier capacity.
    
4. If an active Barrier exists, calculate its protection cost.
    
5. Consume the required Barrier capacity.
    
6. Prevent the incoming crowd-control effect.
    

### Insufficient Barrier Capacity

If the remaining Barrier capacity cannot cover the protection cost:

- The remaining Barrier capacity is consumed.
    
- The Barrier breaks.
    
- The incoming crowd-control effect is still prevented.
    
- Excess protection cost does not transfer into HP DMG.
    
- Subsequent crowd-control effects can affect the enemy if no Barrier remains.
    

---

## Barrier Protection Costs

### Ordinary Stuns

The third-stack stun and sixth-stack Discharge stun use the following provisional formula:

P_stun = min(1, 0.50 + 0.000005 × D_stored)

Where:

- P_stun = proportion of maximum Barrier capacity consumed.
    
- D_stored = applicable calculated stored Charge.
    

### Static Charge Interruptions

The fourth- and fifth-stack interruptions use the following provisional formula:

P_interrupt = min(1, 0.000005 × D_stored)

Static Charge has no fixed base Barrier protection cost.

### Resistance Adjustment

- Lightning DMG Resistance reduces the resulting protection cost proportionally.
    
- Complete resistance prevents Barrier capacity consumption.
    
- Intrinsic immunity prevents Barrier capacity consumption when protection is unnecessary.
    

Provisional resistance-adjusted calculation:

P_effective = P_base × (1 − Lightning DMG Resistance)

Resistance is expressed as a decimal fraction.

### Applicable Stored Charge

|Milestone|Charge Used|
|---|---|
|Third-stack stun|Accumulated Charge of the three current stacks|
|Fourth-stack interruption|Accumulated Charge of the four current stacks|
|Fifth-stack interruption|Accumulated Charge of the five current stacks|
|Sixth-stack stun|Strongest retained completed Discharge Charge|

- Applicable critical calculations are included in stored Charge.
    
- The current milestone's Charge contribution is included before calculating the protection cost.
    

### Illustrative Protection Costs

Assuming zero Lightning DMG Resistance:

|Stored Charge|Stun Cost|Interruption Cost|
|---|---|---|
|0|50%|0%|
|1,000|50.5%|0.5%|
|5,000|52.5%|2.5%|
|10,000|55%|5%|
|50,000|75%|25%|
|100,000|100%|50%|
|200,000|100%|100%|

All percentages reference maximum Barrier capacity rather than remaining Barrier capacity.

### Future Development

- The formulas remain provisional.
    
- Longer stuns or interruptions may require different protection costs.
    
- Crowd-control duration may eventually become part of the general Barrier protection formula.
    
- These formulas are intended as an initial foundation for the general Stability Barrier system.