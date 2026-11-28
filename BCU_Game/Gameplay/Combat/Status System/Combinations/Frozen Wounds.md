# Frozen Wounds

**Combination:** [[Ice]] + [[Slash]] **Category:** Elemental + Physical **Identity:** Enhanced critical damage during Freeze, followed by empowered Slash DoT. **Duration:** Freeze duration + 5-second enhanced DoT phase **Combination Cooldown:** None

## Activation

- Requires a completed Ice set and [[Slash|Laceration]], representing six stacks of each status.
- Combination eligibility is checked before the ordinary sixth-stack payoff.
- Both completed sets are consumed and stored within Frozen Wounds.
- Frozen Wounds consists of two distinct phases:
    - Frozen Phase.
    - Enhanced Slash DoT Phase.

## Stored Stack Properties

- Frozen Wounds preserves six individual Slash stacks.
- The consumed Ice DMG is distributed equally among the six stacks.
- Each stack contains:
    - Stored Slash DMG.
    - One-sixth of the consumed Ice DMG.
    - Original physical or magical damage category.
    - Critical strike result.
    - Applicable Critical DMG multiplier.
    - Original damage attribution.
- The assigned Ice contribution remains constant even when individual Slash stacks are replaced.

## Phase 1 — Frozen Phase

- The affected enemy experiences Freeze according to the ordinary Ice rules.
- Ordinary Freeze provides its established Final Critical Chance vulnerability.
- Frozen Wounds additionally increases the Critical DMG multiplier of all critical hits against the affected enemy by **+1.0**.
- This bonus applies to all eligible attacks, not exclusively Slash applications.
- Stored Slash stacks do not deal DoT during this phase.
- Damage does not accumulate through suspended DoT ticks.
- The Frozen Phase lasts strictly until the enemy thaws.

## Critical DMG Bonus

- The additional Critical DMG multiplier is fixed at +1.0 for initial testing.
- Examples:
    - 1.5× becomes 2.5×.
    - 2.0× becomes 3.0×.
    - 2.5× becomes 3.5×.
- The additional multiplier applies to successful critical strikes.
- Newly applied Slash stacks can retain the enhanced Critical DMG multiplier.
- The bonus ends immediately when the Frozen Phase ends.

## FIFO Stack Replacement

- Only successful Slash status applications can replace stored stacks.
- Ordinary attacks that do not apply Slash cannot replace stacks.
- Replacement follows FIFO (First In, First Out).
- The oldest stored Slash component is replaced by the newly calculated Slash component.
- The replaced Slash component is discarded.
- Its assigned Ice DMG contribution is preserved.
- Newly applied Slash stacks follow their ordinary independent critical strike calculation, benefiting from Frozen Wounds' additional Critical DMG multiplier when critical.
- Frozen Wounds always retains exactly six enhanced stacks.
- Repeated replacement does not increase or multiply the total stored Ice contribution.

## Phase 2 — Enhanced Slash DoT

- When the enemy thaws, the Frozen Phase immediately ends.
- The six remaining enhanced stacks determine the strength of a single enhanced Slash DoT status.
- The enhanced DoT lasts five seconds.
- Damage is dealt periodically rather than released in an instantaneous burst.
- Physical and magical damage categories remain independently calculated.
- The incorporated Ice DMG follows the corresponding Slash damage category.
- All enhanced Slash DMG retains Slash's provisional 100% corresponding DEF penetration.
- Stored critical results and applicable Critical DMG multipliers are preserved.
- The enhanced DoT does not grant additional Critical Chance or Critical DMG vulnerability.

## Freeze Resistance & Immunity

- Frozen Wounds can activate even if Freeze is completely prevented.
- If the target cannot be frozen, Frozen Wounds immediately transitions into its enhanced Slash DoT phase.
- No separate Frozen Phase occurs.
- If a Slash application initiates the combination:
    - The initiating Slash application receives one opportunity to perform FIFO replacement.
    - This application can benefit from the additional +1.0 Critical DMG multiplier.
    - The six resulting stacks are immediately converted into the enhanced DoT.
- If an Ice application initiates the combination:
    - The six existing Laceration stacks are directly converted into the enhanced DoT.
    - No FIFO replacement occurs.
- Freeze immunity does not inherently prevent the enhanced Slash DMG.

## Stability Barrier Interaction

- Stability Barriers protect against Freeze according to the established crowd-control protection rules.
- If a Stability Barrier prevents Freeze, Frozen Wounds follows the immediate enhanced DoT transition rules.
- Enhanced Slash DMG interacts with Stability Barriers according to ordinary Slash damage rules.
- Frozen Wounds does not inherently bypass Stability Barriers.

## Independent Status Accumulation

- During the Frozen Phase, eligible Slash applications replace stored stacks through FIFO.
- During the enhanced DoT phase, ordinary Slash applications accumulate independently.
- Newly accumulated ordinary Slash stacks cannot replace or refresh the enhanced DoT's stored stacks.
- Players can build toward subsequent combinations while the enhanced DoT remains active.

## Reactivation & DoT Replacement

- Multiple enhanced Frozen Wounds DoTs do not stack.
- When another enhanced Frozen Wounds DoT becomes active, its strength is compared with the currently active enhanced DoT.
- If the new DoT is stronger:
    - It replaces the existing DoT.
    - Its duration begins at five seconds.
- If the existing DoT is stronger:
    - It retains its stored damage properties.
    - Its duration is refreshed to five seconds.
- The stronger enhanced DoT is always preserved.
- No combination-specific cooldown is applied.

## PvP Interaction

- Frozen Wounds is available in both PvE and PvP.
- The same fundamental mechanics apply to affected players.
- PvP-specific balancing adjustments may be introduced following testing.

## Visual Representation

- Frozen Wounds possesses a distinct status icon and visual identity.
- The Frozen Phase visually represents frozen lacerations.
- The transition into the enhanced DoT phase visually communicates the reopening of the empowered wounds.
- Both phases should be distinguishable.
- Remaining status duration is displayed where applicable.

## Numerical Balancing — TBD

- Stored Ice DMG contribution coefficient.
- Enhanced Slash DMG scaling.
- Enhanced DoT tick interval.
- Final Critical DMG bonus balancing.
- Potential boss-specific adjustments.
- Potential PvP-specific adjustments.

## Remaining Implementation Details

- Exact conversion of stored Ice DMG into enhanced Slash DMG per tick.
- Exact comparison method for determining the stronger enhanced DoT.
- Handling of equally strong enhanced DoTs.
- Multiplayer damage attribution for incorporated Ice DMG.
- Interaction with ordinary Ice accumulation during the Frozen Phase.
- Handling of simultaneous Slash applications and thawing.
- Whether another Frozen Phase can coexist with an already active enhanced DoT.
- Exact FIFO handling when the sixth Slash application itself initiates Frozen Wounds, ensuring that the triggering stack is not counted twice.

## Design Philosophy

Frozen Wounds rewards players for utilizing the enemy's frozen state to improve the strength of its existing wounds.

The increased Critical DMG multiplier provides an immediate offensive benefit, while successful Slash applications allow players to improve the six stored stacks through FIFO replacement.

When the enemy thaws, the enhanced wounds begin dealing sustained Slash DMG for five seconds.

Unlike [[Cauterization]], which immediately releases accumulated damage, Frozen Wounds emphasizes preparation, critical strikes and sustained damage after the crowd-control phase.

The combination remains useful against Freeze-immune enemies through its immediate enhanced DoT conversion, while enemies susceptible to Freeze provide additional opportunities to improve its damage.