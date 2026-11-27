# Cool Combustion — Status Combination

## 1. Overview

- **Combination:** [[Fire]] + [[Ice]]
    
- **Category:** Elemental + Elemental
    
- **Identity:** Accumulated Fire potential converted into immediate widespread burst DMG.
    
- **Damage Type:** Fire
    
- **Damage Categories:** Physical and Magical
    
- **Activation:** Six Fire stacks against an enemy with an eligible completed Ice set.
    
- **Effect duration:** Instantaneous.
    
- **Radius:** 1.5× ordinary Combustion radius (provisional).
    
- **DMG falloff:** None.
    
- **Combination-specific cooldown:** None.
    
- **Availability:** Solo and multiplayer.
    

---

## 2. Design Philosophy

Cool Combustion combines Fire's accumulated offensive potential with Ice's ability to interrupt and transform existing conditions.

Unlike ordinary Combustion, which spreads Heat and Burn to maintain offensive pressure, Cool Combustion consumes accumulated Fire potential throughout its explosion radius.

### Core Identity

- Immediate burst DMG instead of sustained DMG.
    
- Increased explosion radius.
    
- Complete removal of explosion DMG falloff.
    
- Rewards preparing multiple enemies with Fire before activating the combination.
    
- Sacrifices remaining Freeze duration.
    
- Sacrifices existing Fire stacks, Heat and Burn.
    
- Does not generate further Fire pressure through propagation.
    

Cool Combustion should encourage deliberate preparation rather than simply acting as an improved version of ordinary Combustion.

---

## 3. Activation Requirements

Cool Combustion requires:

- Six Fire stacks.
    
- An eligible completed six-stack Ice set.
    
- Both sets belonging to the same responsible status pool.
    

### Eligible Ice States

- Ordinary Freeze.
    
- Enhanced Slow replacing Freeze against Freeze-immune enemies.
    
- A newly completed Ice set during its immediate combination eligibility check.
    

The target does not necessarily need to be physically frozen.

### Activation Priority

- Cool Combustion activates automatically when its requirements are satisfied.
    
- Eligible combinations take priority over ordinary sixth-stack payoffs.
    
- Ordinary Combustion does not activate separately.
    
- Ordinary Freeze does not need to activate separately if both sets complete simultaneously.
    
- Competing combinations follow the universal combination priority rules.
    

See [[Status]].

---

## 4. Simultaneous Status Completion

Fire and Ice can reach six stacks through the same damage instance.

If both sets become eligible simultaneously:

1. Complete both sets.
    
2. Perform the combination eligibility check.
    
3. Calculate the completed Ice set's Final Critical Chance vulnerability.
    
4. Calculate Cool Combustion using the applicable offensive properties.
    
5. Consume the relevant status sets.
    
6. Resolve Cool Combustion.
    

Neither ordinary Combustion nor ordinary Freeze resolves independently.

The completed Ice set provides its applicable Final Critical Chance vulnerability for the combination calculation even if ordinary Freeze never formally activates.

This interaction is intentionally permitted.

---

## 5. Explosion Radius

Cool Combustion uses an increased radius relative to ordinary Combustion.

**Cool Combustion Radius = Ordinary Combustion Radius × 1.5**

- The multiplier is fixed.
    
- Accumulated Heat does not independently increase the radius.
    
- The initial 1.5 multiplier is provisional.
    
- Future changes to ordinary Combustion's radius automatically affect Cool Combustion's radius.
    

### Explosion Center

- The primary target serves as the explosion center.
    
- The explosion originates from the primary target's position at activation.
    
- Subsequent movement or death of the primary target does not relocate the explosion.
    

### Targeting

- Ordinary Combustion's targeting rules remain applicable.
    
- Terrain and obstruction interactions follow ordinary Combustion.
    
- Cool Combustion does not introduce additional targeting exceptions.
    

---

## 6. Removal of DMG Falloff

Cool Combustion completely removes ordinary Combustion's distance-based DMG falloff.

- The primary enemy receives 100% of calculated Combustion DMG before mitigation.
    
- Every affected surrounding enemy receives 100% of calculated Combustion DMG before mitigation.
    
- Distance from the explosion center does not reduce DMG.
    
- Individual enemy defenses, resistances and barriers remain applicable.
    

### Example

|Distance from Center|Relative Combustion DMG|
|---|---|
|Primary target|100%|
|Near the center|100%|
|Halfway to the boundary|100%|
|At the explosion boundary|100%|
|Outside the explosion radius|0%|

The removal of DMG falloff is a primary benefit of Cool Combustion.

---

## 7. Damage Components

Cool Combustion consists of up to four DMG components for each affected enemy.

### 1. Primary Combustion DMG

- Calculated using the primary target's accumulated Heat.
    
- References ordinary Combustion's DMG calculation.
    
- Includes applicable remembered propagated Heat on the primary target.
    
- Applied at full strength to every affected enemy.
    
- Does not possess distance-based falloff.
    

### 2. Individual Stored Heat Conversion

- References the receiving surrounding enemy's own accumulated Heat.
    
- Converts ordinary stored Heat into additional immediate DMG.
    
- Includes eligible remembered propagated Heat.
    
- Does not require the surrounding enemy to possess six Fire stacks.
    
- Even one Fire stack can contribute additional DMG.
    
- References ordinary Combustion's Heat-to-DMG coefficient for initial implementation.
    

The primary target does not receive this additional component because its stored Heat already determines the original Combustion DMG.

### 3. Existing Burn Conversion

- References any active Burn belonging to the responsible pool on the receiving enemy.
    
- Converts all remaining scheduled Burn DMG into immediate DMG.
    
- Preserves the existing Burn's offensive and critical properties.
    
- Does not include Burn DMG already dealt.
    

### 4. Potential New Burn Conversion

- Calculates the Burn that ordinary Combustion would generate.
    
- Converts its entire potential DMG duration into immediate DMG.
    
- References Cool Combustion's full, non-falloff DMG when calculating the hypothetical Burn.
    
- Does not actually apply a new Burn.
    

---

## 8. General Damage Formula

**Total Cool Combustion DMG per Enemy = Primary Combustion DMG + Individual Heat Conversion DMG + Existing Burn Conversion DMG + Potential New Burn Conversion DMG**

Each component is included only when applicable.

### Primary Target

**Primary Target DMG = Primary Combustion DMG + Existing Burn Conversion DMG + Potential New Burn Conversion DMG**

The primary target's stored Heat and remembered propagated Heat must not be counted twice.

### Surrounding Targets

**Surrounding Target DMG = Primary Combustion DMG + Individual Heat Conversion DMG + Existing Burn Conversion DMG + Potential New Burn Conversion DMG**

Individual Heat and existing Burn components depend on the receiving enemy's own accumulated Fire properties.

### Additional DMG Multipliers

Cool Combustion does not inherently increase the converted Burn DMG through an additional multiplier.

- Existing Burn conversion: 100%.
    
- Potential new Burn conversion: 100%.
    
- Primary Combustion DMG: 100%.
    
- Individual Heat conversion: ordinary Combustion coefficient (provisional).
    

The increased radius, removal of falloff and immediate conversion already provide substantial benefits.

---

## 9. Individual Heat Conversion

Cool Combustion converts accumulated Heat on surrounding enemies into additional immediate DMG.

### Conversion Rules

- Every eligible ordinary Fire stack contributes its stored Heat.
    
- Remembered propagated Heat also contributes.
    
- The surrounding enemy's Fire stack count does not need to meet any minimum threshold beyond possessing applicable stored Heat.
    
- The original offensive properties of stored Heat remain preserved.
    
- Heat conversion does not perform new ordinary Status Chance rolls.
    
- Heat conversion does not trigger an independent Combustion.
    

### Provisional Calculation

**Individual Heat Conversion DMG = Total Eligible Stored Heat × Ordinary Combustion DMG Coefficient**

The detailed coefficient and applicable critical interactions reference [[Fire]].

### Example

Assume three affected enemies possess different accumulated Heat values.

|Enemy|Stored Fire Stacks|Stored Heat|
|---|---|---|
|Primary target|6|600|
|Surrounding enemy A|3|300|
|Surrounding enemy B|1|100|

Assuming an illustrative Combustion coefficient of 1:

|Enemy|Primary Combustion DMG|Additional Heat Conversion|Total Before Burn Conversion|
|---|---|---|---|
|Primary target|600|0|600|
|Surrounding enemy A|600|300|900|
|Surrounding enemy B|600|100|700|

The primary target's Heat is not counted twice.

All values are illustrative and do not establish final numerical balancing.

---

## 10. Existing Burn Conversion

Cool Combustion consumes existing Burn belonging to the responsible pool on every affected enemy.

### Conversion Rules

- Calculate all remaining scheduled Burn DMG.
    
- Convert that DMG into an immediate damage component.
    
- Remove the existing Burn.
    
- Do not count previously dealt Burn DMG.
    
- Do not restart or extend the original Burn timer.
    
- Preserve the original stored offensive properties.
    
- Preserve the original critical properties.
    
- Preserve original proportional contributor attribution.
    

### Example

An enemy's Burn possesses:

- 100 DMG per tick.
    
- Five remaining scheduled ticks.
    

Cool Combustion converts:

**100 × 5 = 500 DMG**

The enemy receives 500 immediate pre-mitigation Burn conversion DMG instead of five future ticks.

The existing Burn is removed.

---

## 11. Potential New Burn Conversion

Ordinary Combustion can generate Burn on affected enemies.

Cool Combustion instead converts this hypothetical Burn into immediate DMG.

### Calculation Rules

- Calculate the Burn that Combustion would ordinarily generate.
    
- Use Cool Combustion's full, non-falloff DMG as the applicable calculation basis.
    
- Calculate the entire potential Burn DMG across its full intended duration.
    
- Convert all potential ticks into immediate DMG.
    
- Preserve applicable offensive and critical properties.
    
- Do not apply a separate new Burn.
    

### Existing and Potential Burn

Existing Burn and potential new Burn are calculated separately.

- Existing Burn contributes its remaining scheduled DMG.
    
- Potential new Burn contributes its entire potential scheduled DMG.
    
- Both components are included when applicable.
    
- Ordinary stronger-Burn replacement does not discard either conversion component.
    

### Example

|Burn Component|Potential DMG|
|---|---|
|Existing Burn remaining DMG|300|
|Potential new Burn total DMG|500|
|Combined Burn Conversion DMG|800|

Both components are converted into immediate DMG.

No active Burn remains afterward.

---

## 12. Combined Damage Example

The following example illustrates how the different components interact.

Assume Cool Combustion produces:

- 600 primary Combustion DMG.
    
- 400 potential new Burn DMG per affected enemy.
    
- An illustrative Heat conversion coefficient of 1.
    

|Enemy|Primary Combustion|Individual Heat|Existing Burn|Potential New Burn|Total DMG|
|---|---|---|---|---|---|
|Primary target|600|0|200|400|1,200|
|Enemy A|600|300|150|400|1,450|
|Enemy B|600|100|0|400|1,100|
|Enemy C|600|0|0|400|1,000|

All values represent illustrative pre-mitigation DMG.

### Result

- Every enemy receives the full primary Combustion DMG.
    
- Prepared surrounding enemies receive additional individual conversion DMG.
    
- Existing Burn increases the immediate payoff.
    
- Enemies without prior Fire applications still receive primary Combustion DMG and applicable potential new Burn conversion.
    
- No enemy receives a newly applied Burn.
    
- No Heat is propagated.
    

---

## 13. Status Consumption

### Primary Target

Cool Combustion consumes:

- All six ordinary Fire stacks.
    
- All corresponding stored Heat.
    
- Eligible remembered propagated Heat.
    
- Existing Burn.
    
- The completed Ice set.
    
- Remaining Freeze or enhanced Slow duration.
    
- The consumed Ice set's Final Critical Chance vulnerability.
    

### Surrounding Enemies

Cool Combustion consumes all applicable Fire properties belonging to the responsible pool:

- Ordinary Fire stacks.
    
- Stored Heat.
    
- Remembered propagated Heat.
    
- Existing Burn.
    

### Surrounding Ice Effects

Cool Combustion does not consume:

- Surrounding enemies' ordinary Ice stacks.
    
- Surrounding enemies' completed Ice sets.
    
- Surrounding enemies' Freeze effects.
    
- Surrounding enemies' enhanced Slow effects.
    
- Surrounding enemies' Ice-related critical vulnerability.
    

Only the primary target sacrifices its completed Ice set.

### Unrelated Statuses

Other statuses and combinations are not inherently consumed or removed by Cool Combustion.

Any specialized interaction must be explicitly established.

---

## 14. Consumption Timing

All applicable damage components and offensive properties are determined before status consumption.

### Resolution Order

1. Determine the primary target and explosion center.
    
2. Determine all affected enemies.
    
3. Identify the responsible status pool.
    
4. Read the primary target's accumulated Heat.
    
5. Determine applicable Ice critical vulnerability.
    
6. Calculate primary Combustion DMG and its critical properties.
    
7. Read each surrounding enemy's eligible stored Heat.
    
8. Read existing Burn properties and remaining scheduled DMG.
    
9. Calculate potential new Burn DMG.
    
10. Determine all applicable contributor attribution.
    
11. Complete all necessary damage calculations.
    
12. Consume the relevant Fire properties and primary completed Ice set.
    
13. Deliver the calculated Cool Combustion DMG.
    
14. Resolve eligible enemy death and other resulting effects.
    

The calculation of affected enemies before damage delivery remains provisional for implementation.

### Purpose

- Prevent duplicate Heat calculations.
    
- Prevent previously dealt Burn DMG from being counted again.
    
- Preserve critical vulnerability before its consumption.
    
- Prevent enemy deaths from modifying other components of the same explosion.
    
- Prevent unrelated triggered effects from changing the already calculated explosion.
    

---

## 15. Heat Propagation & Secondary Explosions

Cool Combustion does not propagate Heat.

### Restrictions

- Does not apply new Fire stacks.
    
- Does not generate new remembered propagated Heat.
    
- Does not apply new Burn.
    
- Does not generate secondary Combustions.
    
- Does not generate secondary Cool Combustions.
    
- Does not recursively spread its explosion.
    

### Individual Heat Conversion

Consuming Heat on surrounding enemies generates only local conversion DMG against those enemies.

It does not create another explosion centered on them.

### Ice Propagation

Cool Combustion does not:

- Apply Ice stacks.
    
- Apply Slow.
    
- Apply Freeze.
    
- Propagate Ice-related critical vulnerability.
    

Existing Ice effects on surrounding enemies remain unaffected.

---

## 16. Damage Categories & Damage Type

Cool Combustion remains entirely Fire-based.

### Damage Type

- Primary Combustion DMG: Fire.
    
- Individual Heat conversion DMG: Fire.
    
- Existing Burn conversion DMG: Fire.
    
- Potential new Burn conversion DMG: Fire.
    

Ice changes the behavior of accumulated Fire rather than contributing direct Ice DMG.

### Damage Categories

- Original Physical and Magical DMG proportions remain preserved.
    
- Physical components remain Physical Fire DMG.
    
- Magical components remain Magical Fire DMG.
    
- Individual components retain their applicable Damage Category distribution.
    
- No new Damage Category roll occurs solely because Cool Combustion activates.
    

Physical and Magical components remain independently calculated.

See [[Damage Calculation]] and [[Status]].

---

## 17. Critical Strike Interactions

Cool Combustion preserves the applicable critical properties of its individual DMG components.

### Primary Combustion Critical Strike

- Uses ordinary Combustion's critical strike rules.
    
- Benefits from the primary target's applicable Ice Final Critical Chance vulnerability.
    
- The shared initial Combustion calculation applies to every affected enemy.
    
- The primary target's critical vulnerability can therefore indirectly benefit DMG against surrounding enemies.
    

This shared critical interaction remains provisional for balancing.

### Simultaneous Completion

If Fire and Ice reach six stacks simultaneously:

- Calculate the completed Ice set's applicable Final Critical Chance vulnerability.
    
- Include this vulnerability in the Cool Combustion calculation.
    
- Consume the completed Ice set before damage delivery.
    

Freeze does not need to formally activate first.

### Existing Burn Critical Properties

- Existing Burn retains its original critical properties.
    
- A critical Cool Combustion does not retroactively strengthen existing Burn.
    
- Conversion does not perform a new Burn critical roll.
    

### Potential New Burn Critical Properties

- References ordinary Combustion Burn generation rules.
    
- Preserves the applicable critical properties of the hypothetical Burn.
    
- Does not receive additional critical scaling solely because it is converted into immediate DMG.
    

### Individual Heat Conversion

- Preserves applicable stored Heat properties.
    
- References ordinary Combustion's relevant critical calculation rules.
    
- Must not apply critical multipliers twice.
    

The exact critical calculation for independently converted surrounding Heat remains subject to implementation review.

---

## 18. Defense & Resistance

### Physical and Magical DEF

Each DMG component follows the applicable defense interactions of its originating Fire mechanic.

- Physical components reference applicable Physical DEF rules.
    
- Magical components reference applicable Magical DEF rules.
    
- Existing Fire-specific DEF exceptions remain applicable.
    
- Conversion does not inherently grant additional DEF penetration.
    

### Fire DMG Resistance

Fire DMG Resistance mitigates all Cool Combustion DMG components.

- Primary Combustion DMG.
    
- Individual Heat conversion DMG.
    
- Existing Burn conversion DMG.
    
- Potential new Burn conversion DMG.
    

### Ice DMG Resistance

Ice DMG Resistance affects the preceding Ice mechanics.

It does not directly reduce Cool Combustion's Fire DMG.

Applicable Ice resistance can influence:

- Freeze duration.
    
- Enhanced Slow.
    
- Available combination activation window.
    
- Applicable Ice critical vulnerability.
    
- Immediate completed-set resolution.
    

This separation remains provisional for balancing.

### Dynamic Mitigation

Converted Burn DMG uses the receiving enemy's defensive properties at the moment of Cool Combustion.

- Hypothetical future DEF changes are not calculated.
    
- Hypothetical future resistance changes are not calculated.
    
- Hypothetical future vulnerability changes are not calculated.
    
- All converted remaining DMG is evaluated using current applicable target properties.
    

See [[Fire]], [[Ice]] and [[Status]].

---

## 19. Freeze Immunity & Complete Ice Resistance

### Freeze-Immune Enemies

Enemies possessing Freeze Immunity can still enable Cool Combustion through Ice's completed enhanced Slow alternative.

- Ordinary physical freezing is not mandatory.
    
- The completed Ice set remains the relevant requirement.
    
- Cool Combustion resolves at full applicable strength.
    
- The completed enhanced Slow effect is consumed.
    

### Complete Ice DMG Resistance

Enemies with 100% Ice DMG Resistance can enable Cool Combustion during the immediate combination check upon completing their Ice set.

- The completed set briefly becomes eligible.
    
- Cool Combustion takes priority if its Fire requirement is satisfied.
    
- Otherwise, ordinary complete Ice resistance resolution occurs.
    

### Simultaneous Completion

Completing both Fire and Ice through the same damage instance can enable Cool Combustion even against completely Ice-resistant enemies.

Applicable critical vulnerability continues to follow the established Ice rules.

---

## 20. Complete Fire Resistance

Enemies with 100% Fire DMG Resistance can still serve as Cool Combustion centers.

- Eligible Fire stacks and stored Heat can exist despite complete Fire DMG Resistance.
    
- Cool Combustion still activates when its requirements are satisfied.
    
- The resistant enemy receives no applicable Fire DMG.
    
- Surrounding enemies receive DMG according to their own defenses and resistances.
    
- The primary target's Fire resistance does not reduce the offensive calculation applied to surrounding enemies.
    
- Relevant Fire and Ice properties are still consumed.
    

### Design Purpose

Completely Fire-resistant enemies can be used as strategically positioned explosion centers against less resistant surrounding enemies.

---

## 21. Invulnerability

Invulnerable enemies can remain eligible for Cool Combustion's status consumption.

### Invulnerable Primary Target

- Can serve as the explosion center.
    
- Relevant Fire and completed Ice properties are consumed.
    
- Receives no actual DMG while invulnerable.
    
- Other affected enemies resolve DMG normally.
    

### Invulnerable Surrounding Enemies

- Eligible Fire stacks are consumed.
    
- Stored Heat is consumed.
    
- Remembered propagated Heat is consumed.
    
- Existing Burn is consumed.
    
- No actual DMG is dealt while invulnerable.
    

Invulnerability does not preserve Fire properties that would otherwise be consumed by Cool Combustion.

---

## 22. Stability Barrier Interactions

Cool Combustion follows ordinary Combustion and Burn barrier interactions.

See [[Stability Barrier System]].

### General Rules

- Primary Combustion DMG interacts with barriers normally.
    
- Individual Heat conversion follows the applicable Fire DMG barrier rules.
    
- Existing Burn conversion follows ordinary Burn barrier interactions.
    
- Potential new Burn conversion follows the applicable Burn barrier interactions.
    
- Cool Combustion does not inherently penetrate Stability Barriers.
    
- No additional barrier DMG multiplier is granted.
    
- Barrier protection does not inherently preserve consumed Fire properties.
    
- Status consumption remains part of combination resolution.
    

The immediate conversion of multiple damage components must preserve their applicable barrier behavior.

Exact component-level barrier resolution requires implementation testing.

---

## 23. Multiplayer & Pool Ownership

Cool Combustion follows the shared fundamental status pool system.

### Responsible Pool

- Party members contribute to shared Fire and Ice pools.
    
- Independent parties maintain separate pools.
    
- Solo players maintain independent pools.
    
- Cool Combustion uses only the responsible pool's eligible statuses.
    

### Fire Consumption Ownership

Cool Combustion only consumes Fire properties belonging to the responsible pool.

Fire stacks, stored Heat, propagated Heat and Burn belonging to other parties or independent players remain untouched.

### Ice Consumption Ownership

Only the responsible pool's completed Ice set on the primary target is consumed.

Independent Ice sets belonging to other parties or solo players remain untouched.

### Independent Activations

Different parties can independently activate Cool Combustion against the same enemy, provided their respective requirements are satisfied.

They cannot consume or convert each other's accumulated Fire properties.

---

## 24. Solo & Cooperative Combination Activation

Status combinations do not require two distinct contributing players.

### Solo Players

- A solo player can eventually supply both required completed sets independently.
    
- Solo combination activation is intentionally possible.
    
- Exact weapon, ability and companion interactions may determine how efficiently this can be achieved.
    

### Parties

- Party members collectively contribute Fire and Ice.
    
- Different players can specialize in different statuses.
    
- Cooperation can accelerate combination preparation.
    
- Multiple contributors are not a mandatory activation requirement.
    

### Companions

- Companions can deal DMG and apply statuses.
    
- Companions are intended to support combination preparation.
    
- Exact companion ownership and contribution rules remain undecided.
    

### Universal System Revision

This decision supersedes the previous group-exclusive combination activation requirement.

The universal [[Status]] note will be updated after all individual status combinations have been reviewed.

---

## 25. Damage Attribution

Cool Combustion preserves the originating contributor attribution of every converted DMG component.

### Primary Combustion

- Attribution follows the proportional stored Heat contributions used for the primary Combustion calculation.
    
- The player triggering Cool Combustion does not automatically receive all DMG credit.
    

### Individual Heat Conversion

- Attribution follows the original stored Heat contributions on the receiving enemy.
    
- Remembered propagated Heat retains its existing proportional attribution.
    

### Existing Burn Conversion

- Attribution follows the existing Burn's original contributors.
    
- Original proportional attribution remains preserved.
    

### Potential New Burn Conversion

- Attribution follows the originating Combustion and Burn generation rules.
    
- Contributors retain credit according to their applicable stored offensive contributions.
    

### Example

Assume a surrounding enemy receives:

|DMG Component|Player A|Player B|Player C|
|---|---|---|---|
|Primary Combustion|400|200|0|
|Individual Heat Conversion|0|100|200|
|Existing Burn Conversion|100|0|0|
|Potential New Burn Conversion|200|100|0|
|Total Attribution|700|400|200|

The enemy receives a total of 1,300 pre-mitigation DMG.

Individual attribution is preserved rather than assigning the entire explosion to one player.

All values are illustrative.

---

## 26. Ice Contributor Participation

Ice contributors do not automatically receive a percentage of Cool Combustion's DMG credit solely because they supplied Ice stacks.

### Design Principles

- Fire DMG attribution remains based on actual Fire contributions.
    
- Ice contributors are recognized for enabling the combination.
    
- Combination participation should contribute toward applicable participation and loot eligibility.
    
- Ice contribution does not duplicate or redistribute existing Fire DMG attribution.
    

### Future Development

- Combination-specific participation credit.
    
- Experience and loot contribution.
    
- Recognition of utility-focused players.
    
- Companion contribution tracking.
    
- Attribution when multiple players contribute to the completed Ice set.
    

See [[Participation and Loot]] and [[Party]].

---

## 27. Cleansing

Cool Combustion is instantaneous and cannot itself be cleansed after activation.

### Preventing Activation

Cleansing can prevent Cool Combustion by removing required status properties before the combination activates.

Examples include:

- Reducing Fire below its six-stack requirement.
    
- Cleansing the completed Ice set.
    
- Removing relevant accumulated Heat.
    
- Removing existing Burn before conversion.
    

### Reducing Potential DMG

Cleansing surrounding enemies can reduce their additional conversion DMG by removing:

- Ordinary Fire stacks.
    
- Stored Heat.
    
- Remembered propagated Heat.
    
- Existing Burn.
    

Cleansing surrounding enemies does not inherently prevent them from receiving the primary Cool Combustion explosion.

### Post-Activation

- Cool Combustion leaves no independently active combination effect.
    
- There is no Cool Combustion duration to cleanse.
    
- Consumed statuses cannot be restored through cleansing.
    

Individual Fire and Ice cleansing follows their respective status rules.

---

## 28. Enemy Death & Triggered Effects

Enemy deaths caused by Cool Combustion can trigger unrelated eligible death-based mechanics.

### Examples

- [[Poison]] spreading.
    
- Other explicitly established enemy death effects.
    
- Applicable kill-related mechanics.
    

Cool Combustion does not inherently suppress unrelated statuses or death-triggered effects.

### Resolution Restrictions

- Death-triggered effects do not retroactively modify already calculated Cool Combustion DMG.
    
- Consumed Fire properties do not generate secondary Combustions.
    
- Enemy deaths do not relocate the original explosion center.
    
- Enemy deaths do not cause Cool Combustion to recursively propagate.
    

Exact ordering between multiple simultaneous enemy death effects remains subject to universal implementation rules.

---

## 29. Reapplication & Cooldown

Cool Combustion possesses no dedicated internal cooldown.

After resolution:

- Players can immediately begin applying new Fire stacks.
    
- Players can immediately begin applying new Ice stacks.
    
- No combination-specific temporary immunity is applied.
    
- Ordinary Status Chance Resistance remains applicable.
    
- Guaranteed status applications follow their established rules.
    

### Natural Limitation

Cool Combustion consumes its required Fire and Ice sets.

Activating another Cool Combustion therefore requires preparing new eligible sets.

The extensive consumption of surrounding Fire properties also reduces the accumulated potential available for subsequent activations.

---

## 30. General Status Damage Restrictions

Cool Combustion DMG does not behave as an ordinary direct attack hit.

### Status Chance

- Cool Combustion cannot apply additional statuses through ordinary Status Chance rolls.
    
- Converted Heat cannot recursively apply Fire.
    
- Converted Burn cannot recursively generate Burn.
    
- The explosion cannot generate Ice stacks.
    

### On-Hit Effects

General status damage restrictions remain applicable.

Cool Combustion does not inherently trigger:

- Life Steal.
    
- Stability recovery.
    
- Effects requiring ordinary direct attack hits.
    

Explicitly established exceptions and unrelated eligible death-based mechanics remain possible.

See [[Status]].

---

## 31. Ordinary Combustion Comparison

|Property|Ordinary Combustion|Cool Combustion|
|---|---|---|
|Activation requirement|Six Fire stacks|Six Fire stacks + completed Ice set|
|Explosion radius|Standard|1.5× standard|
|Explosion DMG falloff|Yes|None|
|Primary Fire consumption|Yes|Yes|
|Primary Ice consumption|No|Yes|
|Surrounding Fire consumption|No|Yes|
|Surrounding stored Heat conversion|No|Yes|
|Existing Burn conversion|No|Yes|
|Potential new Burn conversion|No|Yes|
|New Burn application|Yes|No|
|Heat propagation|Yes|No|
|Surrounding Ice consumption|No|No|
|Ice propagation|No|No|
|Secondary explosions|Follows ordinary Fire rules|No|
|Additional conversion multiplier|Not applicable|None|
|Dedicated combination cooldown|Not applicable|None|

### Ordinary Combustion Identity

- Explosion.
    
- Heat propagation.
    
- Burn application.
    
- Continued offensive pressure.
    
- Preparation of future Fire effects.
    

### Cool Combustion Identity

- Enlarged explosion.
    
- Immediate burst DMG.
    
- Consumption of accumulated Fire potential.
    
- Sacrifice of crowd control.
    
- No continued Fire propagation.
    

Both mechanics should remain strategically valuable.

---

## 32. Strategic Applications

### Prepared Enemy Groups

Players can distribute Fire stacks among several enemies before completing Fire and Ice on the primary target.

Cool Combustion then converts the accumulated Fire properties throughout its radius.

### Sustained Damage Conversion

Players can allow existing Burns to accumulate before converting their remaining scheduled DMG into immediate burst damage.

Waiting too long reduces the remaining Burn DMG available for conversion.

### Crowd-Control Sacrifice

Activating Cool Combustion consumes the primary target's Freeze or enhanced Slow.

Players must decide whether immediate burst DMG is more valuable than the remaining crowd-control duration.

### Resistance-Based Positioning

Fire-resistant enemies can serve as explosion centers against nearby enemies with lower Fire resistance.

### Simultaneous Completion

Carefully prepared attacks capable of completing both Fire and Ice simultaneously can trigger Cool Combustion without requiring a previously active Freeze window.

### Cooperative Specialization

- Fire-focused players accumulate Heat and Burn across enemy groups.
    
- Ice-focused players prepare eligible primary targets.
    
- Utility-focused players can reposition enemies to improve the explosion's effectiveness.
    
- Solo players can eventually prepare combinations independently or with companions.
    

---

## 33. Balance Considerations

Cool Combustion possesses several significant advantages:

- Increased explosion radius.
    
- Complete removal of DMG falloff.
    
- Immediate conversion of sustained Burn DMG.
    
- Additional conversion of surrounding stored Heat.
    
- Consumption of remembered propagated Heat.
    
- Potentially powerful shared critical calculation.
    

These advantages are balanced through:

- The requirement for two compatible completed status sets.
    
- Consumption of the primary completed Ice set.
    
- Removal of remaining Freeze duration.
    
- Consumption of accumulated Fire properties.
    
- Removal of existing Burn.
    
- No new Burn application.
    
- No Heat propagation.
    
- No secondary explosions.
    
- The requirement to rebuild status sets after activation.
    

### Removed DMG Multiplier

An additional 20% multiplier for converted Burn DMG was initially considered.

This multiplier has been removed.

The increased radius, removal of falloff and immediate damage conversion already provide sufficient mechanical advantages for initial testing.

### Potential Balance Risks

- Excessive burst DMG against densely grouped enemies.
    
- Excessive additional DMG from surrounding stored Heat.
    
- Large area coverage when ordinary Combustion radius increases.
    
- Critical Combustion benefiting every affected enemy.
    
- High combined DMG from existing and potential Burn conversion.
    
- Rapid repeated preparation through multiple party members.
    
- Excessively powerful combinations with future weapon or companion mechanics.
    

These interactions should be evaluated through implementation and playtesting rather than introducing additional restrictions prematurely.

---

## 34. Lore

Cool Combustion represents the interaction between accumulated Heat and a completed state of Ice.

Rather than allowing Fire to continue spreading and burning, the interaction rapidly releases its accumulated offensive potential.

The resulting explosion consumes existing Fire throughout the surrounding area, transforming sustained pressure into a concentrated moment of destruction.

The primary target's frozen or otherwise completed Ice state is sacrificed during this process.

The combination demonstrates how two opposing elemental effects can produce a new outcome rather than simply cancelling each other out.

Exact visual and narrative representation remains open.

---

## 35. Visual Representation

Cool Combustion should be visually distinguishable from ordinary Combustion.

### Visual Information

Players should be able to recognize:

- Combination activation.
    
- The primary explosion center.
    
- Increased explosion radius.
    
- Immediate consumption of surrounding Fire.
    
- Disappearance of existing Burn.
    
- Consumption of the primary completed Ice set.
    
- Absence of subsequent Fire propagation.
    

### Potential Visual Direction

- A brief thermal disturbance before the explosion.
    
- Fire effects collapsing into a colder-looking burst.
    
- A rapidly expanding explosion wave.
    
- Existing flames on surrounding enemies disappearing simultaneously.
    
- A short-lived contrast between Fire and Ice visuals.
    

Visual suggestions are not finalized.

### Combat DMG Display

- Multiple damage components resolve within the immediate combination event.
    
- Physical and Magical DMG remain independently calculated.
    
- General combat DMG display settings remain applicable.
    
- Exact representation of converted Heat and Burn components remains undecided.
    

---

## 36. Provisional Values

|Property|Current Value|
|---|---|
|Required Fire stacks|6|
|Required Ice stacks|Completed six-stack set|
|Radius multiplier|1.5×|
|Primary Combustion DMG across radius|100%|
|Explosion DMG falloff|None|
|Existing Burn conversion|100% of remaining scheduled DMG|
|Potential new Burn conversion|100% of total potential DMG|
|Individual Heat conversion coefficient|Ordinary Combustion coefficient|
|Additional Burn conversion multiplier|None|
|Fire consumption|All responsible Fire properties within radius|
|Primary Ice consumption|Entire completed set|
|Surrounding Ice consumption|None|
|Heat propagation|None|
|Burn application|None|
|Ice propagation|None|
|Secondary explosions|None|
|Effect duration|Instantaneous|
|Dedicated cooldown|None|
|Minimum distinct contributing players|1|

---

## 37. Remaining Design & Implementation Questions

### Numerical Balancing

- Final explosion radius multiplier.
    
- Final ordinary Combustion radius.
    
- Final Individual Heat conversion coefficient.
    
- Final Burn and Combustion DMG coefficients.
    
- Balance between immediate conversion and ordinary sustained Fire pressure.
    
- Effectiveness against large enemy groups.
    
- Effectiveness against elites and bosses.
    

### Critical Strike Interactions

- Exact critical calculation for independently converted surrounding Heat.
    
- Preventing duplicate critical scaling.
    
- Testing the primary target's critical vulnerability benefiting the entire explosion.
    
- Final interaction with ordinary Combustion Burn critical properties.
    

### Damage Resolution

- Exact implementation of pre-calculated simultaneous explosion resolution.
    
- Internal ordering of converted damage components.
    
- Component-level mitigation and rounding.
    
- Exact representation of multiple damage components within one immediate combination event.
    
- Stability Barrier interactions when several converted components resolve together.
    
- Simultaneous combination and enemy death resolution.
    

### Status Interactions

- Interaction with active combinations that retain Fire-related properties.
    
- Competing combination priority during simultaneous status completion.
    
- Exact handling of other combination-generated Burn variants.
    
- Compatibility with future specialized Fire effects.
    

### Multiplayer

- Participation credit for Ice contributors.
    
- Companion status pool ownership.
    
- Companion contribution tracking.
    
- Party membership changes during combination resolution.
    
- Interaction with universal combination attribution rules.
    

### Visual Representation

- Explosion appearance.
    
- Fire consumption effects.
    
- Ice consumption effects.
    
- Combat DMG display.
    
- Audio feedback.
    
- Performance when affecting large enemy groups.
    

---

## 38. Superseded Mechanics

### Additional Converted Burn Multiplier

Previous proposal:

- Increase converted Burn DMG by 20%.
    

Current:

- Convert 100% of applicable remaining or potential Burn DMG.
    
- No additional conversion multiplier.
    

### Surrounding Fire Preservation

Previous proposal:

- Consume surrounding Burn while preserving ordinary Fire stacks and stored Heat.
    

Current:

- Consume and convert all eligible surrounding Fire stacks, stored Heat, remembered propagated Heat and Burn.
    

### Heat Propagation

Previous proposal:

- Preserve ordinary Combustion's Heat propagation and Burn application.
    

Current:

- No Heat propagation.
    
- No newly applied Burn.
    
- All applicable potential is converted into immediate DMG.
    

### Group-Exclusive Activation

Previous system:

- Status combinations require allied players.
    

Current:

- Solo activation is possible.
    
- Cooperation improves combination preparation but is not mandatory.
    
- Companions can eventually assist in applying required statuses.
    

### Equal Combination DMG Attribution

Previous system:

- Combination DMG credit is divided equally between two contributing players.
    

Current Cool Combustion rule:

- Each Fire DMG component preserves its original proportional contributor attribution.
    
- Ice contributors receive applicable participation recognition instead of automatically receiving Fire DMG credit.
    

---

## 39. Design Status

Cool Combustion's core mechanics are established.

### Established Mechanics

- Fire and Ice activation requirements.
    
- Simultaneous completion eligibility.
    
- Increased explosion radius.
    
- Complete removal of DMG falloff.
    
- Primary Combustion DMG.
    
- Individual surrounding Heat conversion.
    
- Remembered propagated Heat conversion.
    
- Existing Burn conversion.
    
- Potential new Burn conversion.
    
- Complete responsible Fire consumption throughout the explosion radius.
    
- Primary completed Ice consumption.
    
- Preservation of surrounding Ice effects.
    
- Preservation of independent status pools.
    
- No additional conversion multiplier.
    
- No newly applied Burn.
    
- No Heat propagation.
    
- No Ice propagation.
    
- No secondary explosions.
    
- Original critical property preservation.
    
- Dynamic target mitigation.
    
- Resistance and immunity interactions.
    
- Ordinary Stability Barrier interactions.
    
- Individual proportional DMG attribution.
    
- Ice contributor participation recognition.
    
- Solo and multiplayer activation.
    
- Immediate status reapplication.
    
- No dedicated combination cooldown.
    

Further development primarily concerns numerical balancing, implementation details, universal combination interactions and visual representation.

---

## Related Notes

- [[Status]]
    
- [[Fire]]
    
- [[Ice]]
    
- [[Lightning]]
    
- [[Poison]]
    
- [[Damage Calculation]]
    
- [[Critical Hits]]
    
- [[Stability Barrier System]]
    
- [[Participation and Loot]]
    
- [[Party]]
    
- [[Companions]]
    
- [[Arc Combustion]]
    
- [[Toxic Combustion]]
    
- [[Shattering Voltage]]
    
- [[Cryotoxicity]]
    
- [[Frozen Wounds]]