# Poison — Elemental Status

## 1. Overview

- **Category:** Elemental
- **Damage Type:** Poison
- **Identity:** Progressive infection, offensive pressure and spreading.
- **Maximum stacks:** 6
- **Base stack duration:** 5 seconds
- **Sixth-stack payoff:** Poisonous Strikes
- **Damage behavior:** Application-triggered maximum HP DMG.
- **Stack ownership:** Party-specific.
- **Damage attribution:** Individual and proportional.

### Design Philosophy

- Reward continued Poison applications rather than passive damage over time.
- Become increasingly effective against enemies with larger HP pools.
- Reward investment into Poison DMG and Status Chance.
- Allow stronger Poison builds to increase percentage-based HP DMG without allowing unrestricted scaling.
- Encourage strategic enemy grouping and chain infections.
- Allow allied players to cooperate through shared Poison stacks.
- Remain mechanically distinct from [[Fire]] and [[Slash]].

---

## 2. Stack Ownership

Poison follows the party-shared stack system established in [[Status]].

- Players belonging to the same party contribute to a shared Poison stack pool on each enemy.
- Players outside the party maintain independent pools.
- Solo players maintain their own individual pools.
- Different parties can independently activate Poisonous Strikes against the same enemy.
- Every stack retains its individual damage properties and original contributor.
- Physical and magical Poison applications contribute to the same pool.
- Physical and magical damage classifications remain individually recorded.

### Stored Stack Properties

Each Poison stack stores the applicable:

- Original contributor.
- Original offensive Poison DMG.
- Damage Category.
- Critical strike properties.
- Application order.
- Applicable duration properties.
- Damage attribution information.

Changes to a player's offensive attributes do not retroactively modify previously stored damage values.

---

## 3. Base Poison Mechanics

Poison no longer deals conventional damage over time.

- Poison stacks accumulate through successful Poison status applications.
- The first two stacks prepare the enemy for subsequent Poison effects.
- Beginning at three stacks, successful Poison-applying hits deal additional maximum HP-based DMG.
- The maximum HP DMG percentage increases with the current stack milestone.
- Accumulated stored Poison DMG further increases the maximum HP DMG percentage through diminishing returns.
- Ordinary attacks that do not successfully apply Poison do not trigger this additional damage.
- Applying multiple Poison stacks through a single hit triggers the additional damage only once.

Poison's damage output therefore depends on continued successful applications rather than an independent damage tick timer.

---

## 4. Stack Progression

|Stacks|Base Maximum HP DMG|Effect|
|---|--:|---|
|1|0%|Initial infection.|
|2|0%|Infection preparation.|
|3|0.125%|Additional HP DMG becomes available.|
|4|0.250%|Increased additional HP DMG.|
|5|0.375%|Further increased additional HP DMG.|
|6|0.500%|Poisonous Strikes activates.|

- The listed percentages represent the base values before stored Poison DMG scaling.
- Stored DMG scaling becomes available at three stacks.
- One and two stacks do not provide additional maximum HP DMG.
- All numerical percentages remain subject to playtesting and balancing.

---

## 5. Stored Poison DMG

Every successfully applied Poison stack stores an offensive Poison DMG value.

The accumulated stored Poison DMG is the sum of the stored damage values belonging to the relevant stack set.

**Accumulated Stored DMG = Sum of all relevant stored Poison stack DMG values**

Stored Poison DMG is used for:

- Scaling additional maximum HP DMG.
- Determining the strength of spreading Poison stacks.
- Maintaining proportional damage attribution.
- Determining the offensive strength of Poisonous Strikes.

### Damage Properties

- Stored Poison DMG does not represent damage already inflicted upon the enemy.
- Stored Poison DMG is retained independently from the enemy's HP.
- Existing stored damage values are not recalculated when offensive attributes change.
- Poison does not independently scale with Weapon Attack Speed after its application.
- Attack Speed can indirectly increase Poison's effectiveness through more frequent successful applications.

---

## 6. Maximum HP DMG Calculation

Stored Poison DMG increases the percentage of maximum HP DMG dealt.

It does not provide an additional flat damage component.

### General Formula

**Poison HP DMG Percentage = Base Milestone Percentage + Stored DMG Scaling Bonus**

**Additional Poison DMG = Target Maximum HP × Poison HP DMG Percentage**

The Stored DMG Scaling Bonus follows a diminishing-return function.

### Conceptual Formula

- H = Target Maximum HP
- D = Accumulated Stored Poison DMG
- B = Base Milestone Percentage
- F(D) = Diminishing-return percentage bonus

**Additional Poison DMG = H × (B + F(D))**

Applicable critical multipliers, resistances and defensive interactions are resolved according to their respective rules.

### Example — Conceptual

An enemy possesses 10,000 maximum HP.

|Effective HP DMG Percentage|Additional DMG|
|--:|--:|
|0.125%|12.5|
|0.250%|25|
|0.375%|37.5|
|0.500%|50|
|0.600%|60|
|0.750%|75|
|1.000%|100|

The values above 0.5% are illustrative examples of potential stored DMG scaling and do not represent established limits.

---

## 7. Diminishing Returns

The efficiency of additional stored Poison DMG decreases as its accumulated value increases.

### Established Principles

- Increasing stored Poison DMG always increases the effective maximum HP DMG percentage.
- Additional stored Poison DMG becomes progressively less efficient.
- The marginal scaling efficiency approaches zero at sufficiently high stored DMG values.
- Increasing stored DMG must not reduce the resulting HP DMG percentage.
- The base milestone percentage remains the unscaled foundation of the calculation.
- Poison must not provide unrestricted maximum HP DMG scaling.

### Design Objectives

- Remain relatively modest during early-game progression.
- Become increasingly valuable against high-HP enemies during later progression.
- Reward powerful Poison-focused equipment and builds.
- Prevent excessively high stored damage values from producing disproportionately powerful HP DMG.
- Prevent repeated spreading from creating exploitable damage values.

### Numerical Balancing

The following remain undecided:

- Exact diminishing-return formula.
- Initial scaling efficiency.
- Rate of efficiency reduction.
- Maximum attainable or asymptotic HP DMG percentages.
- Whether individual stack milestones require different scaling curves or limits.

The previously discussed fixed multipliers of 0.00005 and 0.0001 are superseded.

The final formula should be determined after establishing representative player DMG and enemy HP values throughout level progression.

---

## 8. Poison Damage Activation

Additional maximum HP DMG triggers through successful Poison-applying hits.

### General Rules

- The triggering attack must successfully apply at least one Poison stack.
- Additional maximum HP DMG can trigger only once per individual hit.
- Applying multiple stacks through one hit does not multiply the additional HP DMG.
- Unsuccessful Poison applications do not trigger additional HP DMG.
- There is no dedicated internal cooldown.
- Different enemies resolve their Poison interactions independently.

### Multi-Hit Weapons

Weapons with high Attack Speed or multiple damage instances can benefit from more frequent successful Poison applications.

However:

- High Status Chance does not multiply the additional HP DMG within a single hit.
- Applying several stacks through one hit primarily accelerates stack progression.
- Attack Speed does not extend Poisonous Strikes.
- Poisonous Strikes does not automatically grant maximum HP DMG to every ordinary attack.

Fast weapons can naturally synergize with Poison, subject to numerical balancing.

---
## 9. Poisonous Strikes

Poisonous Strikes represents Poison's completed six-stack effect.

### Activation

Upon reaching six Poison stacks:

1. Check for eligible allied status combinations according to [[Status]].
2. Resolve an eligible combination when applicable.
3. Otherwise, activate Poisonous Strikes.
4. Preserve the completed six-stack set.
5. Calculate its accumulated stored Poison DMG.
6. Establish eligible player contributions.
7. Begin the fixed Poisonous Strikes duration.

### Effects

- Base additional maximum HP DMG increases to 0.5%.
- Stored Poison DMG increases this percentage through diminishing returns.
- Eligible players trigger the additional damage through successful Poison-applying hits.
- The completed set enables Poison spreading upon enemy death.

### Duration

- Fixed duration: **5 seconds**.
- The duration cannot be refreshed.
- Ordinary attacks cannot extend the duration.
- Additional Poison applications cannot extend the duration.
- Attack Speed does not influence the duration.

The previously proposed diminishing duration-extension sequence is removed completely.

### Stored DMG Reference

While Poisonous Strikes is active:

- Its damage scaling references only the stored DMG of its completed six-stack set.
- Newly accumulating Poison stacks do not increase the existing Poisonous Strikes damage.
- The completed set retains its stored damage and contributor information.
- Its effective HP DMG percentage remains based on that completed set.

---

## 10. Poisonous Strikes — Multiplayer Eligibility

Poisonous Strikes rewards players who contributed to the relevant completed Poison set.

- Every allied player who contributed to the completed set becomes eligible for Poisonous Strikes.
- Contributing at least one stack is sufficient.
- Players do not receive a weaker or stronger HP DMG percentage based solely on their individual contribution.
- Eligible players benefit from the same completed set's calculated HP DMG percentage.
- Players who did not contribute to the completed set do not automatically receive its benefit.
- Party membership alone does not grant Poisonous Strikes.
- Players can continue contributing to subsequent Poison stack sets.

The previous party-wide 0.5% HP DMG bonus for non-contributing allies is removed.

The previous initiator-exclusive 1% HP DMG bonus is also superseded.

### Example

- Player A contributes four Poison stacks.
- Player B contributes two Poison stacks.
- Player C contributes no Poison stacks.

The party reaches six stacks and activates Poisonous Strikes.

- Player A becomes eligible for Poisonous Strikes.
- Player B becomes eligible for Poisonous Strikes.
- Player C does not become eligible through party membership alone.

Player C can contribute to subsequent Poison sets.

---

## 11. Completed and Accumulating Poison Sets

A party can accumulate a new Poison stack set while Poisonous Strikes is already active.

Each party can maintain:

- One active completed six-stack set.
- One separately accumulating Poison stack set.

### Independent Timers

Both sets use independent timers.

#### Completed Set

- Fixed five-second duration.
- Cannot be refreshed or extended.
- Contains the currently active Poisonous Strikes effect.

#### Accumulating Set

- Base five-second shared stack duration.
- Successful new applications refresh its timer according to the ordinary status duration rules.
- Newly accumulated stacks do not modify the completed set.

### Example

- At second 0, Poisonous Strikes activates.
- At second 4, a new Poison stack is applied.
- At second 5, Poisonous Strikes expires.
- The newly applied Poison stack retains its own remaining duration.

The expiration of Poisonous Strikes does not automatically remove independently accumulated Poison stacks.

---

## 12. Completed Set Replacement

If the accumulating set reaches six stacks while Poisonous Strikes is already active:

- The new completed set replaces the previous completed set.
- Replacement occurs regardless of which set contains more stored DMG.
- The previous completed set is removed.
- The new completed set establishes its own stored DMG scaling.
- Player eligibility and contribution information are recalculated.
- A fresh five-second Poisonous Strikes duration begins.

### Restrictions

- A party cannot maintain multiple simultaneous Poisonous Strikes effects on the same enemy.
- The stronger completed set is not automatically preserved.
- Replacement does not combine the stored DMG of both completed sets.
- Replacing Poisonous Strikes does not trigger Poison spreading.
- Further Poison applications can begin accumulating another set.

This prevents players from indefinitely maintaining an unusually powerful completed Poison set.

---

## 13. Natural Expiration

When Poisonous Strikes naturally expires:

- Its completed six-stack set is removed entirely.
- Its additional maximum HP DMG effect ends.
- Its player eligibility information is removed with that completed set.
- Its death-spreading eligibility ends.
- No completed Poison stacks are returned to the ordinary stack pool.
- Independently accumulating Poison stacks remain unaffected.

The accumulating set continues following its own duration and stack progression rules.

---

## 14. Cleansing

Cleansing Poisonous Strikes differs from its natural expiration.

### Completed Set Cleansing

When Poisonous Strikes is cleansed:

- Poisonous Strikes ends immediately.
- The completed set is reduced from six stacks to three stacks.
- The three oldest stacks are removed through FIFO.
- The three newest stacks retain their original stored properties.
- Damage attribution associated with surviving stacks is preserved.
- The completed set's Poisonous Strikes bonuses cease.
- The cleansed set no longer qualifies for completed-set spreading.

### Continued Applications

- Players remain capable of contributing further Poison stacks.
- Surviving contributions remain attributed to their original contributors.
- Poisonous Strikes can activate again after a relevant set reaches six stacks.
- Eligibility is determined from the new completed set.

### Remaining Cleansing Details

The exact interaction between the three surviving stacks and an already accumulating secondary set requires confirmation.

The duration assigned to the surviving stacks following cleansing also requires confirmation.

---

## 15. Poison Spreading

Poison spreading represents the infection's primary group-combat mechanic.

### Activation Condition

Poison spreads when an enemy dies while carrying an eligible completed Poison effect.

- Ordinary Poisonous Strikes enables spreading.
- Poison combinations are intended to preserve spreading as part of their identity.
- Individual combinations may modify the spreading behavior.
- Reaching six stacks alone does not trigger spreading.
- Natural expiration does not trigger spreading.
- Cleansing does not trigger spreading.
- Completed-set replacement does not trigger spreading.

The enemy does not need to die specifically from Poison DMG.

---

## 16. Spread Target Selection

Upon the death of a fully poisoned enemy:

- Search for eligible enemies within the spreading radius.
- Prioritize enemies based on proximity to the defeated enemy.
- Select a maximum of three eligible enemies.
- Each selected enemy receives three Poison stacks.

### Target Eligibility

- Enemies outside the spreading radius are excluded.
- Defeated enemies are excluded.
- Enemies already possessing six Poison stacks for the spreading party are skipped.
- Enemies possessing fewer than six relevant Poison stacks remain eligible.
- Enemies protected by Stability Barriers can receive spreading Poison stacks.

If fewer than three eligible enemies exist, only the available eligible enemies receive Poison.

### Spreading Radius

- The ordinary spreading radius remains numerically undecided.
- Individual Poison combinations may modify the spreading radius.
- Poison does not spread indiscriminately to every enemy within range.

---

## 17. Spread DMG Calculation

The spreading effect preserves the average stored DMG of the completed Poison set.

### Formula

**Average Stored DMG per Stack = Completed Set Stored DMG ÷ 6**

Every selected enemy receives three stacks.

**Total Spread Stored DMG per Enemy = Completed Set Stored DMG × 0.5**

### Example

A completed Poison set contains 12,000 accumulated stored Poison DMG.

- Average stored DMG per stack: 2,000.
- Number of spreading stacks: 3.
- Total stored DMG received by each eligible enemy: 6,000.

Each selected enemy receives the same three-stack infection strength.

The damage is not divided between the selected enemies.

### Spread Damage Scaling

- Spreading transfers stored Poison DMG rather than the defeated enemy's calculated HP DMG.
- The receiving enemy's maximum HP determines its own percentage-based Poison DMG.
- The defeated enemy's maximum HP is not inherited.
- The defeated enemy's effective maximum HP DMG percentage is not directly inherited.
- Stored DMG scaling is recalculated from the receiving enemy's relevant Poison stacks.
- Target-specific resistances and defensive properties are recalculated for the receiving enemy.

This prevents an enemy with exceptionally high maximum HP from transferring its absolute HP-based damage values to weaker enemies.

---

## 18. Spread Application Rules

Spreading applies three guaranteed Poison stacks to each selected enemy.

### Guaranteed Application

Spreading ignores:

- General Status Chance Resistance.
- Individual Poison Status Chance Resistance.
- Ordinary Status Chance rolls.
- Base and Final Status Chance modifiers.

Spreading follows the guaranteed direct application rules in [[Status]].

### Duration

- Spread stacks receive a fresh, full Poison duration.
- The remaining duration of the defeated enemy's Poison effect is irrelevant.
- Spread stacks follow the receiving pool's ordinary timer rules.
- Existing stored stack properties are not recalculated solely because spreading refreshes the timer.

### Overflow

If an eligible enemy already possesses four or five Poison stacks:

- Spreading behaves as three ordinary stack applications.
- Normal threshold resolution applies.
- Reaching six stacks activates an eligible combination or Poisonous Strikes.
- Additional applications follow the established completed-set and accumulating-set mechanics.
- No separate overflow system exists exclusively for spreading.

---

## 19. Spread Damage Attribution

Spreading preserves the proportional contributions of the original completed Poison set.

- Every contributing player retains their applicable damage attribution.
- Contributions are distributed according to their original stored Poison DMG proportions.
- Damage attribution is separate from the number of spreading stacks.
- A spreading stack can carry attribution information belonging to multiple contributors.
- Individual contribution percentages do not generate additional stacks.
- Damage must not be duplicated merely because several players contributed.

### Example

A completed set contains 12,000 stored Poison DMG.

|Contributor|Original Contribution|Contribution Percentage|
|---|--:|--:|
|Player A|9,600|80%|
|Player B|2,400|20%|
|Total|12,000|100%|

Each receiving enemy receives 6,000 stored Poison DMG through three stacks.

|Contributor|Spread Contribution|
|---|--:|
|Player A|4,800|
|Player B|1,200|
|Total|6,000|

Both players retain their proportional attribution.

### Repeated Spreading

- Contribution information persists through subsequent infections.
- New Poison applications can introduce additional contributor information.
- Future spreading recalculates contribution proportions from the relevant completed set.
- Contributors represented through spread stacks can become eligible for Poisonous Strikes.
- Players do not need to directly attack every infected enemy to contribute to its completed Poison set.

---

## 20. Independent Party Spreading

Different parties maintain independent Poison pools.

If several parties possess eligible completed Poison sets when an enemy dies:

- Every party resolves its spreading independently.
- Each party uses its own stored DMG values.
- Each party performs its own eligible target selection.
- Each party maintains its own contributor attribution.
- Each party can spread to a maximum of three eligible enemies.
- Different parties may infect the same receiving enemies.
- Their respective Poison pools remain independent.

One party's completed Poison set does not automatically prevent another party from infecting the same enemy.

---

## 21. Critical Poison DMG

Additional maximum HP-based Poison DMG can critically strike.

- The applicable Critical DMG multiplier can multiply percentage-based HP DMG.
- Critical scaling is permitted provisionally.
- Critical properties must not be applied twice.
- Baseline Critical Chance should remain consistent with the general combat philosophy.
- The interaction between high Critical DMG and maximum HP DMG requires playtesting.

### Conceptual Formula

**Critical Poison DMG = Maximum HP-Based Poison DMG × Applicable Critical DMG Multiplier**

### Example

Assuming:

- Target maximum HP: 10,000.
- Effective Poison HP DMG percentage: 0.6%.
- Critical DMG multiplier: 1.5.

Ordinary Poison DMG: 60.

Critical Poison DMG: 90.

The exact critical roll behavior and the relationship between stored critical stack properties and application-triggered critical damage require final confirmation.

See [[Critical Hits]] and [[Status]].

---

## 22. Resistance and Defense

### ### Ordinary Defense

- Poison's maximum HP-based DMG is affected by corresponding DEF.
- Physical Poison DMG references Physical DEF.
- Magical Poison DMG references Magical DEF.
- Maximum HP-based DMG does not inherently bypass DEF.
- Applicable DEF is evaluated dynamically when DMG occurs.
- Individual Poison combinations may explicitly override ordinary defensive interactions.

### Status Chance Resistance

- Ordinary Poison applications follow the established Status Chance Resistance rules.
- Elite and boss enemies may resist ordinary Poison applications.
- Guaranteed spreading bypasses Status Chance Resistance.

### Status DMG Resistance

- Poison DMG remains affected by applicable Poison DMG Resistance.
- Resistance is evaluated against the receiving enemy.
- Poison DMG Resistance does not inherently prevent Poison stack accumulation.
- Guaranteed spreading does not bypass applicable DMG Resistance.

The exact interaction with other forms of DMG vulnerability remains subject to the general damage system and individual testing.

---

## 23. Stability Barrier Interaction

Poison's maximum HP-based DMG does not inherently bypass Stability Barriers.

### Damage

- Applicable Stability Barriers protect the enemy against Poison HP DMG.
- Poison's maximum HP-based nature does not grant automatic barrier penetration.
- Barrier interactions follow the established [[Stability Barrier System]].
- Any damage overflow follows the general barrier rules.

### Stack Application

- Stability Barriers do not inherently prevent Poison spreading.
- Shielded enemies remain eligible spreading targets.
- Poison can accumulate on shielded enemies according to applicable status application rules.
- Poisonous Strikes can remain mechanically relevant even while a barrier protects the enemy's HP.

Individual Poison combinations may introduce specialized barrier interactions.

---

## 24. General Status Damage Restrictions

Poison follows the general status damage restrictions in [[Status]].

- Additional Poison DMG does not automatically generate ordinary recursive Status Chance rolls.
- Additional Poison DMG does not independently trigger general on-hit effects.
- Life Steal and Stability recovery do not automatically trigger from additional status DMG.
- Explicit spreading is an intentional exception to ordinary restrictions against recursive status applications.
- Stored Poison information remains independent of subsequent changes to the originating player's offensive attributes.
- Existing Poison stacks follow the established persistence rules when their contributing player dies.

Spreading itself is a scripted status application rather than an ordinary attack hit.

---

## 25. Poison Combinations

Poison participates in combinations with compatible completed elemental and physical statuses.

|Partner|Combination|
|---|---|
|[[Fire]]|[[Toxic Combustion]]|
|[[Ice]]|[[x Cryotoxicity]]|
|[[Lightning]]|[[x Neurotoxin]]|
|[[Slash]]|[[x Viral Wounds]]|
|[[Impact]]|[[x Corrosion]]|
|[[Puncture]]|[[x Toxic Infiltration]]|
### Toxic Combustion

- Preserves Poisonous Strikes without consuming or refreshing its completed set.
- Converts ordinary Combustion Burn and Heat propagation into Toxic Blight.
- Toxic Blight deals flat and maximum HP-based Poison DMG.
- Toxic Blight is independent of ordinary Poison stacks.
- Ordinary Poison spreading resolves before Toxic Blight spreading.
- See [[Toxic Combustion]] for complete mechanics.

### General Combination Philosophy

Poison combinations should retain the infection and spreading identity of Poison.

Individual combinations may modify:

- Spreading radius.
- Spreading strength.
- Spread stack count.
- Additional maximum HP DMG.
- Status application behavior.
- Defensive interactions.
- Duration.
- Stored damage scaling.
- Additional combination-specific effects.

These potential modifications are design possibilities rather than universally established combination rules.

### Combination Priority

- Eligible combinations are checked upon completion of a six-stack set.
- Combination resolution takes priority over ordinary Poisonous Strikes when applicable.
- Individual combination notes determine which originating properties are preserved, replaced or consumed.
- Spreading should ordinarily transfer base Poison rather than automatically duplicating the entire combination.

The remaining five Poison combinations require individual review following the redesign of Poison.

Previous combination mechanics relying on Poison DoT must be reconsidered.

---

## 26. Poison Lifecycle

### Ordinary Progression

No Poison → Poison (1–2) → Poison (3–5) → Poisonous Strikes

### Natural Expiration

Poisonous Strikes → Completed set removed.

Independently accumulated stacks remain active.

### Cleansing

Poisonous Strikes → Poison (3).

The oldest three completed stacks are removed through FIFO.

### Continued Applications

Poisonous Strikes + Accumulating Poison (1–5).

### Completed Set Replacement

Poisonous Strikes + New Poison (6) → New Poisonous Strikes.

The previous completed set is replaced entirely.

### Death Spreading

Enemy dies with eligible completed Poison effect → Three guaranteed Poison stacks applied to each of the three closest eligible enemies within the spreading radius.

---

## 27. Superseded Mechanics

The following previously recorded Poison mechanics are removed:

- Conventional Poison damage over time.
- Three-stack DoT totaling 5% maximum HP.
- Six-stack DoT totaling 15% maximum HP.
- Initiator-exclusive 1% maximum HP DMG through ordinary attacks.
- Automatic 0.5% maximum HP DMG bonus for other party members.
- Poisonous Strikes duration extensions through ordinary attacks.
- Diminishing duration-extension sequence of +1.0, +0.8, +0.6, +0.4, +0.2, +0.05 and 0 seconds.
- Spreading immediately upon reaching six stacks.
- Unlimited spreading targets within an area.
- Fixed additive flat DMG scaling from stored Poison DMG.
- Fixed stored DMG multipliers of 0.00005 and 0.0001.
- Exclusively player-specific Poison pools within the same party.

These mechanics are superseded by the current Poison design.

---

## 28. Remaining Design and Implementation Questions

### Numerical Balancing

- Exact stored Poison DMG calculation upon stack application.
- Exact diminishing-return function.
- Appropriate maximum HP DMG scaling limits.
- Whether each milestone requires an individual scaling limit.
- Representative early-game and late-game stored DMG values.
- Representative enemy HP values throughout progression.
- Poison performance against elites and bosses.
- Spreading radius.
- Damage rounding and minimum damage.
- Critical damage balancing.

### Application Resolution

- Whether a threshold-crossing hit uses the stack milestone before or after its applications.
- Whether stored DMG from the triggering hit contributes to that hit's additional Poison DMG.
- Whether guaranteed non-hit applications can independently trigger additional HP DMG.
- Exact critical roll behavior.
- Physical and magical category distribution within spread stacks.

### Multiplayer

- Interaction with party membership changes.
- Attribution when a new player contributes during an already active Poisonous Strikes effect.
- Exact damage attribution for application-triggered HP DMG.
- Interaction with companions.
- Independent party contribution and loot calculations.

### Cleansing

- Integration of surviving cleansed stacks into an existing accumulating set.
- Duration of surviving stacks after cleansing.
- Cleansing behavior for incomplete Poison sets.
- Simultaneous cleansing and completed-set replacement.

### Combinations

- Review the five remaining Poison combinations.
- Establish individual combination spreading behavior.
- Determine preserved and consumed stack properties.
- Replace mechanics relying on the superseded Poison DoT.
- Establish specialized defensive and Stability Barrier interactions.

### Visual Representation

- Poison stack indicators.
- Poisonous Strikes visuals.
- Completed and accumulating set indicators.
- Eligible player feedback.
- Infection spreading animation.
- Physical and magical Poison representation.
- Distinction between independent party Poison effects.

---

## 29. Design Status

### Mechanically Established

- Six-stack progression.
- Application-triggered maximum HP DMG.
- No conventional damage over time.
- Increasing milestone HP DMG percentages.
- Stored DMG-based percentage scaling.
- Diminishing returns.
- Once-per-hit damage activation.
- No dedicated internal cooldown.
- Party-shared stack accumulation.
- Contributor-specific Poisonous Strikes eligibility.
- Fixed five-second Poisonous Strikes duration.
- Independent completed and accumulating sets.
- Newest completed set replacement.
- Complete natural expiration.
- Partial FIFO cleansing.
- Death-exclusive spreading.
- Maximum of three spreading targets.
- Three guaranteed spreading stacks per target.
- Proportional stored damage transfer.
- Proportional multiplayer damage attribution.
- Fresh spreading duration.
- Independent party spreading.
- Stability Barrier protection against Poison DMG.
- Spreading eligibility for shielded enemies.
- Provisional critical HP DMG scaling.

### Further Development

Poison's core mechanical identity is established.

Remaining development primarily concerns numerical balancing, specific application-order and cleansing edge cases, visual representation and individual status combinations.

---

## Related Notes

- [[Status]]
- [[Damage Calculation]]
- [[Critical Hits]]
- [[Normal Attacks]]
- [[Stability Barrier System]]
- [[Multiplayer]]
- [[Party]]
- [[Participation and Loot]]
- [[Toxic Combustion]]
- [[x Cryotoxicity]]
- [[x Neurotoxin]]
- [[x Viral Wounds]]
- [[x Corrosion]]
- [[x Toxic Infiltration]]