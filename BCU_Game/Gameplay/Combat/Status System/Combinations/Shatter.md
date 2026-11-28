## Overview

- Shatter is the physical-elemental status combination of [[Impact]] and [[Ice]].
- Requires Impact to have reached Fracture and Ice to reach its six-stack threshold.
- Fracture does not require additional enhanced stacks to participate in Shatter.
- Combines Freeze, progressive DEF reduction and a single-target DMG burst.
- Rewards coordinated Impact and Ice applications during Freeze.
- Follows the group-exclusive status combination rules established in [[Status]].q

## Activation

- Requires:
    - Active Fracture (0–6 stacks).
    - Six completed Ice stacks.
    - Eligibility under the universal status combination rules.
- Upon activation:
    - The enemy becomes affected by normal Freeze.
    - Shatter begins at 0 stacks.
    - The six currently remembered Impact/Fracture stacks are stored.
    - The six contributing Ice stacks are stored.
    - All existing flat and percentage-based DEF reductions from Fracture are preserved.
    - Ordinary Impact and Ice stack accumulation becomes restricted.
- Freeze-immune enemies follow a separate activation procedure.

## Stored DMG

### Impact & Fracture

- Impact and Fracture maintain two separate DMG values:
    - Pre-mitigation DMG used for ordinary flat DEF reduction calculations.
    - Post-mitigation DMG used for Shatter Burst.
- Fracture continues to replace its remembered Impact/Fracture stacks through FIFO before Shatter activates.
- Only the six currently remembered stacks contribute to Shatter.
- Previously replaced stacks do not contribute.
- Reaching additional Fracture stacks does not increase the number of remembered stacks beyond six.

### Ice

- Only the six Ice stacks contributing to Shatter activation are stored for Shatter Burst.
- Additional Ice applications during Shatter do not contribute stored DMG.
- Replacing stored Ice stacks through FIFO during successful Freeze extensions remains a potential balancing alternative.

### Shatter

- Each additional Shatter stack stores its own post-mitigation DMG.
- Shatter stacks exist additionally to the six remembered Impact/Fracture stacks.
- This additional stack storage is exclusive to Shatter.
- The original Impact/Fracture stacks cannot be replaced during active Shatter.

### Maximum Stored Stacks

|Source|Maximum contributing stacks|
|---|--:|
|Impact/Fracture|6|
|Ice|6|
|Shatter|4|
|Total|16|

### Stored Properties

- Each contributing stack preserves:
    - Original contributor.
    - Physical or magical DMG category.
    - Relevant pre-mitigation DMG.
    - Post-mitigation DMG.
    - Applicable critical strike results.
    - Applicable DMG vulnerability and mitigation already accounted for when storing DMG.
- Stored DMG is not retroactively modified by changes to offensive attributes, enemy DEF or DMG vulnerability.

## Active Shatter

### Freeze

- Shatter inherits the ordinary Freeze mechanics established in [[Ice]].
- Normal Freeze duration and resistance rules remain applicable.
- Additional Ice applications can extend Freeze according to its ordinary extension mechanics.
- These applications do not accumulate ordinary Ice stacks.
- Successful Freeze extensions do not increase the stored Ice DMG contributing to Shatter Burst.
- Freeze ends when:
    - Its duration expires.
    - It is forcibly removed.
    - Shatter reaches four stacks and triggers Shatter Burst.

### Shatter Stack Application

- Maximum of four Shatter stacks.
- Every successful Impact status application during active Shatter instead applies a Shatter stack.
- Physical Impact applies a physical Shatter stack.
- Magical Impact applies a magical Shatter stack.
- Physical and magical Shatter stacks share the same four-stack maximum.
- Hybrid Shatter stacks do not exist.
- Each Shatter stack independently calculates and stores its properties.
- Shatter stacks do not replace the original six Impact/Fracture stacks.
- Reaching the fourth Shatter stack immediately triggers Shatter Burst.
- Excess Impact applications beyond the fourth Shatter stack are prevented by the stabilization restriction.

## DEF Reduction

### Preserved DEF Reduction

- All flat and percentage-based DEF reductions present upon Shatter activation remain effective.
- The original Impact/Fracture reductions are protected from decay throughout active Shatter.
- Extending Freeze also extends the period during which these reductions remain protected.
- Additional Shatter stacks provide their own flat and percentage-based DEF reductions.

### Flat DEF Reduction

- Each Shatter stack applies the ordinary flat DEF reduction of an Impact stack.
- Follows the calculation established in [[Impact]].
- Flat DEF reduction depends on:
    - Pre-mitigation DMG of the triggering application.
    - Corresponding original DEF of the enemy.
- Physical Shatter reduces physical DEF.
- Magical Shatter reduces magical DEF.
- Flat DEF reductions can reduce the corresponding DEF below zero.

### Percentage-Based DEF Reduction

- Each Shatter stack provides a base additional percentage-based DEF reduction of 2.5%.
- This reduction additionally scales with the individual stack's stored post-mitigation DMG.
- Current scaling factor: 0.0005.

**Additional DEF Reduction = 0.025 + (Individual Stored DMG × 0.0005)**

- The calculation produces a decimal percentage modifier.
- Each stack calculates its percentage-based reduction independently.
- Only the stored DMG of the individual Shatter stack contributes to its scaling.
- Previously stored Impact, Fracture, Ice and other Shatter DMG do not contribute to this calculation.
- Physical Shatter exclusively increases physical DEF reduction.
- Magical Shatter exclusively increases magical DEF reduction.
- Additional percentage-based DEF reductions stack additively with the preserved Fracture percentage-based reductions.

### Percentage-Based DEF Reduction Examples

|Individual stored DMG|Additional DEF reduction|
|--:|--:|
|10|3%|
|50|5%|
|100|7.5%|
|200|12.5%|
|500|27.5%|
|1,000|52.5%|

- The scaling factor is provisional.
- Numerical balancing must account for potentially excessive DEF reduction at higher DMG values.

### DEF Calculation Order

1. Reference the enemy's original corresponding DEF.
2. Apply the accumulated percentage-based DEF reductions.
3. Apply the accumulated flat DEF reductions.
4. Calculate incoming DMG using the resulting effective DEF.

- Ordinary negative DEF rules remain applicable.
- No additional Shatter-specific DEF reduction cap has been established.
- Potential limitations will be reconsidered during numerical balancing and the universal physical combination review.

## Shatter Burst

### Activation

- Immediately triggers upon reaching four Shatter stacks before Freeze ends.
- The fourth Shatter stack calculates and applies its DEF reductions normally before Shatter Burst occurs.
- Shatter Burst immediately ends Freeze.
- The enemy subsequently enters the four-second lingering phase.
- Natural or forced thawing before reaching four Shatter stacks does not trigger Shatter Burst.

### DMG Calculation

- Shatter Burst deals 50% of the combined stored post-mitigation DMG of:
    - Six remembered Impact/Fracture stacks.
    - Six original Ice stacks.
    - Four additional Shatter stacks.

**Shatter Burst DMG = 0.5 × (Stored Impact/Fracture DMG + Stored Ice DMG + Stored Shatter DMG)**

- Only currently stored contributing stacks are included.
- Replaced Impact/Fracture stacks are excluded.
- Additional Ice applications used to extend Freeze are excluded.
- The original stored DMG has already undergone mitigation.
- Shatter Burst does not perform another ordinary DEF calculation.
- The accumulated DEF reduction does not independently amplify Shatter Burst.
- DEF reductions may indirectly increase Shatter Burst through the increased post-mitigation DMG stored by subsequent Shatter applications.

### DMG Categories

- Shatter Burst preserves the physical and magical DMG categories of all contributing stacks.
- Physical and magical stored DMG are accumulated separately.
- The 50% multiplier is applied to both accumulated DMG categories.
- No additional DMG category roll occurs.

### Critical Strikes

- Shatter Burst cannot independently critically strike.
- Critical strikes already accounted for within stored DMG remain effective.
- Critical DMG is not applied a second time.

### DMG Vulnerability

- DMG vulnerability is accounted for when individual DMG values are stored.
- Active vulnerability from [[Puncture]], Breach or other sources can therefore increase the stored DMG of contributing stacks.
- DMG vulnerability is not recalculated when Shatter Burst occurs.
- Previously accounted-for vulnerability is not applied a second time.

### DMG Classification & Resistance

- Shatter Burst is classified as status DMG.
- Applicable status DMG resistances remain effective.
- Resistances already accounted for within stored DMG must not be applied a second time.
- Shatter Burst cannot apply additional statuses.
- Shatter Burst cannot directly generate additional status combinations.

### Targeting

- Single-target DMG.
- Only damages the enemy affected by Shatter.
- Does not generate an AoE or spreading effect.

### Stability Barriers

- Shatter Burst follows ordinary Stability Barrier interaction rules.
- Does not inherently penetrate Stability Barriers.
- Does not provide additional Stability Barrier DMG.

### DMG Attribution

- Each original contributor receives proportional DMG credit based on their individual stored DMG contribution.
- Shared status pools do not duplicate stored DMG.
- Individual physical and magical DMG contributions remain attributable to their original contributors.
- Additional Ice applications that extend Freeze do not contribute direct Shatter Burst DMG attribution.

## Natural & Forced Thawing

- If Freeze expires before reaching four Shatter stacks:
    - Shatter Burst does not occur.
    - Active Shatter ends.
    - All accumulated DEF reductions enter the lingering phase.
- If Freeze is forcibly removed through cleansing or another mechanic:
    - The same rules apply.
    - Shatter Burst does not occur.
    - All accumulated DEF reductions enter the lingering phase.
- Failure to trigger Shatter Burst does not remove the accumulated DEF reduction payoff.

## Freeze-Immune Enemies

- Freeze immunity does not prevent Shatter activation.
- The game checks combination eligibility before resolving the ordinary Freeze effect.
- If Shatter is eligible against a Freeze-immune enemy:
    - Shatter activates.
    - The enemy does not become frozen.
    - Shatter Burst immediately occurs.
    - No additional Impact application is required.
    - No Shatter stacks are generated.
    - No additional Shatter-specific flat or percentage-based DEF reductions are applied.
    - The preserved Impact/Fracture DEF reductions enter the four-second lingering phase.

### Freeze-Immune Burst DMG

- Only the original six Impact/Fracture and six Ice stacks contribute.

**Shatter Burst DMG = 0.5 × (Stored Impact/Fracture DMG + Stored Ice DMG)**

- Maximum of 12 contributing stacks.
- All ordinary Shatter Burst DMG calculation and attribution rules remain applicable.

### Partial Freeze Resistance

- Enemies with reduced Freeze duration but without complete Freeze immunity follow ordinary Shatter mechanics.
- The requirement of four Shatter stacks remains unchanged.
- Reduced Freeze duration naturally decreases the available window for triggering Shatter Burst.
- Ordinary Freeze extension and resistance rules remain applicable.

## Lingering DEF Reduction

### Core Mechanics

- Duration: 4 seconds.
- Begins immediately when active Shatter ends.
- Occurs regardless of whether Shatter Burst was successfully triggered.
- Preserves all accumulated DEF reductions from:
    - Remembered Impact stacks.
    - Fracture.
    - Additional Shatter stacks.
- Both flat and percentage-based DEF reductions remain effective.
- All preserved values remain unchanged throughout the lingering phase.
- No ordinary stack decay occurs during this phase.
- The lingering effect cannot accumulate additional stacks or increase its existing DEF reduction.
- Shatter cannot be triggered again during this phase.

### Expiration

- Upon expiration:
    - All lingering DEF reductions are removed.
    - All contributing stored stacks and DMG values are discarded.
    - Ordinary Impact and Ice stack accumulation becomes available again.
    - Shatter becomes eligible for activation again.

### Cleansing

- Appropriate cleansing mechanics can remove the lingering DEF reductions before their duration expires.
- Cleansing does not remove the stabilization restriction.
- The original four-second restriction must expire before ordinary Impact and Ice accumulation or Shatter reactivation becomes possible.

## World Stabilization

### Core Philosophy

- The world attempts to stabilize entities affected by powerful physical status combinations.
- Participating statuses are temporarily prevented from accumulating ordinary stacks.
- This prevents excessive combination chaining, overlapping DEF reduction pools and continuous exploitation of the same combination.

### Active Shatter

- Ordinary Impact stack accumulation is prevented.
- Successful Impact applications instead generate Shatter stacks.
- Ordinary Ice stack accumulation is prevented.
- Additional Ice applications can still extend the active Freeze.
- Combination-specific applications remain possible.
- Unrelated statuses remain unaffected by this restriction.

### Lingering Phase

- Ordinary Impact stack accumulation is completely prevented.
- Ordinary Ice stack accumulation is completely prevented.
- Additional Shatter stacks cannot be applied.
- Shatter cannot be reactivated.
- Excess Impact stacks originating from the application that triggered Shatter Burst are prevented.
- The restriction remains active for the original four-second duration, even if the lingering DEF reductions are cleansed prematurely.

### Universal Physical Combination Application

- World Stabilization is intended to become a potential universal mechanic for physical status combinations.
- The exact implementation and possible combination-specific exceptions will be established after all physical combinations have been designed.
- Shatter currently follows its individually established stabilization rules.

## Multiplayer

- Shatter follows the group-exclusive status combination system.
- Allied players contribute through shared Impact and Ice status pools.
- Impact users contribute by applying additional Shatter stacks.
- Ice users contribute by extending the available Freeze duration.
- Other allied players benefit from the accumulated DEF reduction.
- Individual stored DMG attribution is preserved.
- Interactions between independent parties triggering Shatter against the same enemy remain undecided.
- The scope of stabilization restrictions across independent parties will be established during the universal physical combination review.

## Example Scenario

### Activation

- The enemy is affected by Fracture and reaches six Ice stacks.
- Six remembered Impact/Fracture stacks contribute a combined 600 stored DMG.
- Six Ice stacks contribute a combined 300 stored DMG.
- Shatter activates at 0 stacks.
- The enemy becomes frozen.
- Existing Fracture DEF reductions are preserved.

### Shatter Progression

|Shatter stack|Stored DMG|Additional corresponding DEF reduction|
|--:|--:|--:|
|1|100|7.5%|
|2|200|12.5%|
|3|150|10%|
|4|100|7.5%|
|Total|550|37.5%|

- Each stack additionally applies its ordinary flat Impact DEF reduction.
- The example assumes all four Shatter stacks share the same DMG category.
- Existing Fracture DEF reductions remain effective additionally.

### Shatter Burst

- The fourth Shatter stack is reached before Freeze expires.
- Total stored DMG:
    - Impact/Fracture: 600.
    - Ice: 300.
    - Shatter: 550.
    - Total: 1,450.
- Shatter Burst deals 50% of 1,450 = 725 DMG before any applicable remaining status resistance or Stability Barrier interaction.
- Freeze immediately ends.
- All accumulated DEF reductions remain effective for four seconds.
- Impact and Ice cannot accumulate ordinary stacks during this period.
- Upon expiration, the enemy can accumulate Impact and Ice normally again.

## Balancing & Future Review

- Individual Shatter stack percentage-based DEF reduction scaling of 0.0005.
- Base additional percentage-based DEF reduction of 2.5%.
- Shatter Burst multiplier of 50%.
- Four-second lingering duration.
- Potential maximum DEF reduction limitations.
- Effectiveness against enemies with significantly reduced Freeze duration.
- Potential FIFO replacement of stored Ice stacks through successful Freeze extensions.
- Interactions between Shatter and other physical status combinations.
- Interactions between independent parties.
- Stabilization restriction ownership and scope in multiplayer.
- Universal rules for physical combination consumption, retention, overlapping effects and reactivation.
- Overall effectiveness of combining crowd control, DEF reduction, burst DMG and lingering effects within a single combination.

## Related

- [[Status]]
- [[Impact]]
- [[Ice]]
- [[Puncture]]
- [[Damage Calculation]]
- [[Shattering Voltage]]
- [[x Thermal Fracture]]
- [[x Disruption]]
- [[x Corrosion]]