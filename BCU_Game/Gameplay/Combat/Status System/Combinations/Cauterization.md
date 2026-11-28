# Cauterization

**Combination:** [[Fire]] + [[Slash]] **Category:** Elemental + Physical **Identity:** Single-target burst damage and increased Status Chance. **Duration:** 5 seconds **Combination Cooldown:** None

## Activation

- Requires a completed Fire set and [[Slash|Laceration]], representing six stacks of each status.
- Combination eligibility is checked before the ordinary sixth-stack payoff.
- Both completed sets are immediately consumed.
- Their stored damage values determine the strength of Cauterization.
- Cauterization appears as an independent combination status.

## Burst Damage

- Cauterization immediately releases the stored Fire and remaining Laceration damage.
- Both damage components retain their respective damage types and properties.
- Cauterization exclusively damages the primary target.
- No AoE damage or status propagation occurs.

## Laceration Damage

- All remaining potential Laceration DMG is released immediately.
- The calculation accounts for the natural expiration and gradual decay of individual Slash stacks.
- Each consumed Slash stack retains its:
    - Original damage category.
    - Stored damage per tick.
    - Critical strike result.
    - Critical DMG multiplier.
    - Original damage attribution.
    - Corresponding DEF penetration.
- Physical and magical Slash DMG remain independently calculated.
- Slash DMG is not converted into Fire DMG.
- The consumed Laceration no longer deals its original DoT.

## Fire Damage

- The consumed Fire set releases its stored Heat as immediate Fire DMG.
- Fire DMG retains its corresponding damage properties.
- Fire and Slash DMG are independently calculated but belong to the same combination burst.

## Increased Status Chance

- The affected enemy becomes more vulnerable to further status applications for five seconds.
- Increased Status Chance applies to all physical and elemental statuses.
- All eligible allied players attacking the affected enemy benefit from the bonus.
- The bonus applies additively to the attacking player's existing Status Chance.
- The bonus is calculated from the combined pre-mitigation Fire and Laceration burst DMG.
- Enemy DEF, DMG resistance and Stability Barrier absorption do not reduce the calculated Status Chance bonus.

## Status Chance Scaling

- Initial scaling coefficient: **0.00005 percentage points per point of combined pre-mitigation burst DMG.**
- Formula:

Additional Status Chance (percentage points) = Total Pre-Mitigation Burst DMG × 0.00005

|Combined Burst DMG|Additional Status Chance|
|--:|--:|
|10,000|+0.5 pp|
|20,000|+1 pp|
|50,000|+2.5 pp|
|100,000|+5 pp|
|200,000|+10 pp|
|500,000|+25 pp|
|1,000,000|+50 pp|

- A player with 20% Status Chance attacking an enemy affected by a five-percentage-point Cauterization bonus possesses 25% Status Chance before other applicable modifiers.
- The scaling coefficient is provisional and subject to testing.

## Status Accumulation

- Ordinary Fire and Slash stacks can accumulate independently while Cauterization is active.
- Newly accumulated stacks follow their ordinary status rules.
- Cauterization supports the activation of subsequent combinations through its increased Status Chance.

## Reactivation

- Only one instance of Cauterization may exist on a target at a time.
- A subsequent activation immediately releases another Fire and Laceration damage burst.
- The newly calculated Status Chance bonus replaces the previous bonus.
- Multiple Cauterization bonuses do not stack.
- The duration resets to five seconds.
- No combination-specific cooldown is applied.

## PvP Interaction

- Cauterization is available in both PvE and PvP.
- The same fundamental mechanics apply.
- PvP-specific balancing adjustments may be introduced following testing.

## Visual Representation

- Cauterization possesses a distinct status icon and visual identity.
- Its remaining duration is displayed.
- The activation visually represents the burning of existing wounds.
- The burst should communicate the combination of Fire and Slash damage.

## Numerical Balancing — TBD

- Final Status Chance scaling coefficient.
- Potential diminishing returns for Status Chance scaling.
- Potential maximum Status Chance bonus.
- Final Fire burst damage scaling.
- Potential boss-specific and PvP-specific adjustments.

## Remaining Implementation Details

- Exact calculation of remaining Laceration ticks, including simultaneous expiration and tick events.
- Target-side damage modifiers evaluated at the moment of activation.
- Critical strike calculation for the Fire damage component.
- Interaction between increased Status Chance and Status Chance Resistance.
- Whether additional Status Chance can exceed 100% and how excess chance is handled.
- Exact multiplayer attribution for the combined burst.
- Stability Barrier damage resolution order.

## Design Philosophy

Cauterization combines the accumulated damage of Fire and Slash into a powerful single-target burst while preparing the affected enemy for further status applications.

Unlike the Combustion combinations, Cauterization does not focus on AoE damage or propagation. Its distinctive strength lies in concentrating accumulated damage onto one target and increasing the effectiveness of subsequent status-focused attacks.

The combination rewards stronger contributing elemental and physical sets through both its immediate damage and its scaling supportive effect.

Cauterization is particularly suited to coordinated group combat, enabling players to build towards further status combinations more efficiently.