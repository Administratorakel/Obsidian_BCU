# Toxic Combustion — Status Combination

## 1. Overview

- **Combination:** [[Fire]] + [[Poison]]
- **Category:** Elemental + Elemental.
- **Identity:** Persistent infection, sustained maximum HP-based DMG and death-triggered propagation.
- **Primary Damage Type:** Fire.
- **Secondary Damage Type:** Poison.
- **Damage Categories:** Physical and Magical.
- **Activation:** Six Fire stacks and an eligible completed Poison set.
- **Primary explosion radius:** Ordinary Combustion radius.
- **Toxic Blight application radius:** 1.5× ordinary Combustion radius (provisional).
- **Toxic Blight base duration:** 5 seconds (provisional).
- **Toxic Blight tick interval:** 0.5 seconds.
- **Transferred duration bonus:** 0.5 seconds per eligible Poison stack (provisional).
- **Maximum transferred duration:** 8 seconds (provisional).
- **Toxic Blight DMG falloff:** None.
- **Initial infection target limit:** None.
- **Death spreading target limit:** One enemy per defeated infected enemy.
- **Death spreading radius:** Ordinary Poison spreading radius.
- **Maximum transfer generations:** Unlimited for initial testing.
- **Combination-specific cooldown:** None.
- **Availability:** Solo and multiplayer.

---
## 2. Design Philosophy

Toxic Combustion combines Fire's accumulated Heat with Poison's maximum HP-based offensive potential.

Unlike ordinary Combustion, which propagates Heat and Burn, Toxic Combustion converts its propagation into a persistent Poison-based infection called **Toxic Blight**.

### Core Identity

- Immediate Fire explosion.
- Conversion of ordinary Combustion Burn into Poison DMG.
- Sustained flat and maximum HP-based Poison DMG.
- Increased initial infection radius.
- Death-triggered infection transfers.
- Preservation of Poisonous Strikes.
- Increased infection duration through deliberate Poison preparation.
- Persistent infection across multiple enemy deaths.
- No accumulating DMG amplification through repeated transfers.

Toxic Combustion should reward players who deliberately distribute Poison stacks across enemies and manage their deaths to maintain Toxic Blight.

Its spreading potential is intentionally unrestricted in generation count during initial testing.

---
## 3. Activation Requirements

Toxic Combustion requires:

- Six Fire stacks.
- An eligible completed six-stack Poison set.
- Both status sets belonging to the same responsible status pool.

### Eligible Activation States

Toxic Combustion can activate when:

- Fire reaches six stacks against an enemy with active Poisonous Strikes.
- Fire and Poison complete simultaneously through the same damage instance.
- Guaranteed status applications complete the relevant combination requirements.
- Another explicitly established mechanic produces both eligible completed sets.

### Activation Priority

- Toxic Combustion activates automatically.
- Eligible combinations take priority over ordinary sixth-stack payoffs.
- Ordinary Combustion does not resolve as an additional independent explosion.
- Poisonous Strikes is preserved.
- Competing combinations follow the universal combination priority rules.

See [[Status]].

---
## 4. Simultaneous Status Completion

Fire and Poison may reach six stacks through the same damage instance.

### Resolution

1. Complete both eligible status sets.
2. Check for eligible status combinations.
3. Calculate accumulated Fire Heat.
4. Calculate the completed Poison set's Poisonous Strikes properties.
5. Establish the Toxic Blight DMG properties.
6. Consume the eligible Fire stacks and accumulated Heat.
7. Activate Poisonous Strikes normally.
8. Resolve the primary Fire explosion and Toxic Blight applications.
9. Resolve eligible death-triggered spreading.

Poisonous Strikes remains active even though its completed set contributes to Toxic Combustion.

---
## 5. Primary Fire Explosion

The initial explosion follows ordinary [[Fire]] Combustion mechanics unless explicitly overridden.

### Preserved Properties

- Ordinary Combustion DMG calculation.
- Accumulated Heat from all six Fire stacks.
- Eligible remembered propagated Heat.
- Physical and magical Damage Category proportions.
- Ordinary Combustion critical strike calculation.
- Ordinary explosion radius.
- Ordinary distance-based explosion DMG falloff.
- Ordinary targeting and obstruction rules.
- Consumption of the primary target's eligible Fire stacks and accumulated Heat.

### Overridden Properties

Toxic Combustion does not:

- Generate a new ordinary Combustion Burn.
- Propagate remembered Heat to surrounding enemies.
- Apply additional Fire stacks through its infection.
- Apply additional Poison stacks through its infection.

Ordinary Burn and Heat propagation are converted into Toxic Blight.

The primary explosion itself remains Fire DMG.

Poison does not directly increase the primary Fire explosion's DMG.

---
## 6. Status Consumption and Preservation

### Fire Consumption

Toxic Combustion consumes:

- All six contributing Fire stacks.
- Their stored Heat.
- Eligible remembered propagated Heat on the primary target.

Fire consumption follows ordinary Combustion rules.

### Poison Preservation

Toxic Combustion does not consume:

- The completed Poison set.
- Poisonous Strikes.
- Independently accumulating Poison stacks.
- Stored Poison DMG belonging to the completed set.

Poisonous Strikes continues following its ordinary duration and expiration rules.

Toxic Combustion does not refresh or extend Poisonous Strikes.

### Repeated Utilization

The same completed Poison set can contribute to multiple Toxic Combustion activations during its remaining lifetime.

No dedicated consumption limit or internal cooldown restricts repeated utilization for initial testing.

---
## 7. Toxic Blight

**Toxic Blight** is a specialized stack-independent Poison DoT generated by Toxic Combustion.

### Core Mechanics

- Deals sustained flat Poison DMG.
- Deals additional maximum HP-based Poison DMG.
- Ticks every 0.5 seconds.
- Possesses an independent duration.
- Does not count toward Fire stacks.
- Does not count toward Poison stacks.
- Does not contribute toward ordinary status combination thresholds.
- Spreads upon the affected enemy's death.
- Can coexist with ordinary Burn.
- Can coexist with Poisonous Strikes.
- Can coexist with independently accumulating Poison stacks.

Toxic Blight represents the conversion of Fire's propagated offensive potential into a persistent Poison infection.

---
## 8. Toxic Blight Application Radius

The initial Toxic Blight application radius exceeds the ordinary Combustion explosion radius.

**Toxic Blight Radius = Ordinary Combustion Radius × 1.5**

- The radius multiplier is provisional.
- Every eligible enemy within the application radius receives Toxic Blight.
- There is no initial infection target limit.
- Toxic Blight does not require the receiving enemy to possess Fire or Poison stacks.
- The primary target also receives Toxic Blight.
- Toxic Blight follows ordinary Combustion targeting and obstruction rules.
- Stability Barriers do not prevent Toxic Blight application.

### Example

Assuming an ordinary Combustion radius of 4 meters:

|Distance|Fire Explosion|Toxic Blight|
|---|---|---|
|0–4 meters|Yes|Yes|
|4–6 meters|No|Yes|
|Beyond 6 meters|No|No|

Enemies outside the ordinary explosion radius can receive Toxic Blight without receiving explosion DMG.

No remembered Heat is propagated within either radius.

---
## 9. Toxic Blight Damage Components

Toxic Blight consists of two DMG components:

### Flat Poison DMG

- References the DMG that ordinary Combustion Burn would have generated.
- References all eligible accumulated Fire Heat.
- Includes remembered propagated Heat on the primary target.
- Preserves the contributing Heat's physical and magical Damage Category proportions.
- Converts the resulting DMG Type from Fire to Poison.
- Includes the applicable Combustion critical strike result.

### Maximum HP-Based Poison DMG

- References the completed Poison set's calculated Poisonous Strikes HP% DMG.
- Preserves the completed Poison set's physical and magical Damage Category proportions.
- Includes applicable stored critical DMG properties.
- Calculates actual HP-based DMG using the receiving enemy's maximum HP.

Both components are classified entirely as Poison DMG.

Fire Heat remains the source of the flat DMG calculation but does not determine the final Damage Type.

---
## 10. Toxic Blight Damage Calculation

Toxic Blight's offensive properties are calculated upon Toxic Combustion activation.

### Damage per Second

**Toxic Blight DPS = Flat Poison DPS + Maximum HP-Based Poison DPS**

**Maximum HP-Based Poison DPS = Target Maximum HP × Stored HP DMG Percentage**

The flat Poison DPS references the ordinary Combustion Burn DMG rate.

The stored HP DMG percentage references the completed Poison set's calculated Poisonous Strikes percentage.

### Damage per Tick

Toxic Blight deals DMG every 0.5 seconds.

Both DMG components are divided proportionally according to the tick interval.

**Flat DMG per Tick = Flat Poison DPS × 0.5**

**HP DMG per Tick = Target Maximum HP × Stored HP DMG Percentage × 0.5**

The increased tick frequency does not independently increase DPS.

### Example

Assuming:

- Flat Poison DPS: 200.
- Stored Poisonous Strikes HP DMG percentage: 1.4%.
- Target maximum HP: 10,000.
- Toxic Blight duration: 5 seconds.

|Component|Per Second|Per Tick|
|---|---:|---:|
|Flat Poison DMG|200|100|
|Maximum HP DMG|1.4%|0.7%|
|Maximum HP DMG Value|140|70|
|Combined DMG|340|170|

Over five seconds:

- Total ticks: 10.
- Total flat DMG: 1,000.
- Total maximum HP-based DMG: 700.
- Total combined DMG: 1,700.

All example values are illustrative and exclude target-side mitigation.

---
## 11. Damage Falloff

Toxic Blight does not possess distance-based DMG falloff.

- Every initially affected enemy receives the same calculated flat DMG properties.
- Every initially affected enemy receives the same calculated HP DMG percentage.
- Distance from the explosion center does not reduce Toxic Blight strength.
- Individual maximum HP values determine actual HP-based DMG.
- Individual target-side defenses, resistances, vulnerabilities and barriers remain applicable.

The primary Fire explosion retains ordinary Combustion's distance-based DMG falloff.

---
## 12. Damage Categories and Damage Type

Damage Category and Damage Type remain independent classifications.

### Flat Poison Component

The flat component inherits the physical and magical Damage Category proportions of the contributing Fire Heat.

### Maximum HP Component

The maximum HP-based component inherits the physical and magical Damage Category proportions of the completed Poison set.

### Example

Accumulated Fire Heat:

|Damage Category|Contribution|
|---|---:|
|Physical|60%|
|Magical|40%|

Completed Poison set:

|Damage Category|Contribution|
|---|---:|
|Physical|25%|
|Magical|75%|

Resulting Toxic Blight components:

|Component|Physical Poison|Magical Poison|
|---|---:|---:|
|Flat DMG|60%|40%|
|Maximum HP DMG|25%|75%|

The two DMG components retain their respective Damage Category distributions.

Both components possess Poison as their final Damage Type.

---
## 13. Critical DMG

Toxic Blight does not perform an additional independent critical strike roll.

### Inherited Critical Properties

- Critical DMG already contained within stored Fire Heat remains applicable.
- Critical DMG already contained within stored Poison DMG remains applicable.
- The initial Combustion's critical strike result influences Toxic Blight's flat DMG according to ordinary Combustion Burn rules.
- Previously incorporated critical modifiers are not applied again.
- Critical DMG must not be duplicated during conversion or spreading.

### Persistence

Calculated offensive properties remain stored throughout Toxic Blight's lifetime.

Death-triggered transfers preserve these properties without performing additional critical strike rolls.

Changes to the originating players' offensive attributes do not modify an existing Toxic Blight.

---
## 14. Defense and Resistance

Both Toxic Blight DMG components are affected by applicable target-side mitigation.

### Corresponding Defense

- Physical Poison DMG references Physical DEF.
- Magical Poison DMG references Magical DEF.
- Flat Poison DMG does not inherently bypass DEF.
- Maximum HP-based Poison DMG does not inherently bypass DEF.

Maximum HP-based DMG is not automatically defense-ignoring DMG.

This reflects the updated general Poison defense interaction.

### Damage Resistance

Damage Resistance references the final Damage Type rather than the originating Damage Type.

- The primary Combustion explosion is affected by Fire DMG Resistance.
- Toxic Blight's flat DMG is affected by Poison DMG Resistance.
- Toxic Blight's maximum HP-based DMG is affected by Poison DMG Resistance.
- Fire DMG Resistance does not affect Toxic Blight.
- No proportional Fire-Poison resistance calculation is performed.

### Dynamic Calculation

Applicable target-side properties are evaluated on every damage tick.

These include:

- Current Physical DEF.
- Current Magical DEF.
- Current Poison DMG Resistance.
- Current applicable DMG vulnerability.
- Current maximum HP.
- Current Stability Barrier properties.

Stored offensive properties remain unchanged.

See [[Damage Calculation]] and [[Status]].

---
## 15. Stability Barrier Interaction

Toxic Blight follows ordinary Stability Barrier mechanics.

### Application

- Stability Barriers do not inherently prevent Toxic Blight application.
- Shielded enemies remain eligible initial infection targets.
- Shielded enemies remain eligible death spreading targets.

### Damage

- Stability Barriers protect the affected enemy against Toxic Blight DMG.
- Both flat and maximum HP-based Poison DMG interact normally with barriers.
- Toxic Blight does not inherently possess Stability Barrier penetration.
- Damage overflow follows ordinary Stability Barrier rules.

The ability to infect a shielded enemy does not imply the ability to bypass its barrier.

See [[Stability Barrier System]].

---
## 16. Initial Duration

Every initial Toxic Blight application receives the same default duration.

**Initial Toxic Blight Duration = 5 seconds**

- The five-second duration is provisional.
- Existing Poison stacks do not increase the initial application duration.
- The primary target receives the same initial duration as surrounding enemies.
- Poisonous Strikes does not increase the initial duration.
- Distance does not influence duration.
- Stored DMG does not influence duration.

Only death-triggered Toxic Blight transfers receive Poison stack-based duration scaling.

---
## 17. Tick Timer

Toxic Blight uses an independent damage tick timer.

**Tick Interval = 0.5 seconds**

- The initial damage tick occurs after the first tick interval.
- Toxic Blight possesses its own tick timer independent of ordinary Burn.
- Different party-owned Toxic Blight effects maintain independent tick timers.
- Reapplication refreshes duration without resetting the existing tick timer.
- A newly established stronger effect becomes applicable to the next scheduled tick.
- If stronger reapplication and a damage tick resolve simultaneously, the tick uses the newly established stronger DMG.

### Expiration

If the final damage tick coincides with natural expiration:

- Resolve the final damage tick first.
- Resolve natural expiration afterward.
- A lethal final damage tick still qualifies for death-triggered spreading.

---
## 18. Toxic Blight and Ordinary Burn

Toxic Blight and ordinary Burn are independent effects.

### Coexistence

- Existing ordinary Burn remains active when Toxic Blight is applied.
- Ordinary Burn can subsequently be applied to an enemy affected by Toxic Blight.
- Both effects can deal DMG simultaneously.
- Both effects maintain independent durations.
- Both effects maintain independent damage tick timers.
- Both effects follow their respective strongest-effect rules.
- Neither effect automatically replaces the other.

### Toxic Combustion Restriction

Toxic Combustion itself does not generate a new ordinary Combustion Burn.

The ordinary Combustion Burn that would have been generated is converted into Toxic Blight's flat Poison DMG.

Existing ordinary Burn is not consumed or converted.

### Example

An enemy possesses:

- Existing ordinary Burn: 500 Fire DPS.
- Toxic Blight: 300 flat Poison DPS + 1% maximum HP Poison DPS.

Both effects remain active independently.

Applicable defenses and resistances are calculated according to each effect's respective Damage Categories and final Damage Types.

---
## 19. Heat Propagation and Conversion

Ordinary Combustion propagates Heat to surrounding enemies for future Fire status activations.

Toxic Combustion replaces this propagation with Toxic Blight.

### Conversion Rules

- No new remembered Heat is propagated.
- No ordinary Combustion Burn is propagated.
- Accumulated Heat determines Toxic Blight's flat Poison DMG.
- Remembered Heat on the primary target contributes toward Toxic Blight.
- The primary target's eligible accumulated Heat is consumed normally.

### Existing Surrounding Heat

- Previously stored Heat on surrounding enemies remains unaffected.
- Existing remembered Heat on surrounding enemies remains unaffected.
- Existing Fire stacks on surrounding enemies remain unaffected.
- Toxic Blight does not consume the receiving enemy's accumulated Heat.
- Toxic Blight does not generate additional remembered Heat.

Only the primary target's accumulated Fire potential contributes to the initial Toxic Blight calculation.

---
## 20. Poisonous Strikes Interaction

Toxic Blight does not replace Poisonous Strikes.

### Coexistence

An enemy may simultaneously possess:

- Active Poisonous Strikes.
- Independently accumulating Poison stacks.
- Toxic Blight.
- Ordinary Burn.
- Fire stacks.
- Remembered Heat.

Each mechanic maintains its own established properties and timers.

### Poisonous Strikes Preservation

- Toxic Blight references the completed Poison set upon activation.
- The original completed Poison set remains active.
- Toxic Blight does not extend its duration.
- Toxic Blight does not consume its stacks.
- Subsequent expiration of Poisonous Strikes does not remove Toxic Blight.
- Subsequent replacement of Poisonous Strikes does not recalculate Toxic Blight.
- Subsequent Poison applications do not increase existing Toxic Blight DMG.

Toxic Blight becomes independent of the originating Poisonous Strikes set after its initial calculation.

---
## 21. Ordinary Poison and Fire Applications

Toxic Blight does not behave as an ordinary Fire or Poison stack.

### Fire Applications

- Fire applications do not refresh Toxic Blight.
- Fire applications do not extend Toxic Blight.
- Fire applications do not increase Toxic Blight DMG.
- Ordinary Fire accumulation remains possible.

### Poison Applications

- Poison applications do not refresh Toxic Blight.
- Poison applications do not extend Toxic Blight.
- Poison applications do not increase Toxic Blight DMG.
- Ordinary Poison accumulation remains possible.

Poison preparation influences future death-triggered Toxic Blight targeting and duration rather than modifying an already active infection.

---
## 22. Strongest Toxic Blight Rule

Each responsible status pool maintains a maximum of one active Toxic Blight per enemy.

Multiple Toxic Blight effects belonging to the same pool do not stack independently.

### Strength Comparison

Toxic Blight strength is compared using combined DPS before target-side mitigation.

**Comparison DPS = Stored Flat DPS + Target Maximum HP × Stored HP DMG Percentage**

- Uses the receiving enemy's maximum HP.
- Includes both Toxic Blight DMG components.
- Includes inherited critical DMG properties.
- Excludes DEF.
- Excludes DMG Resistance.
- Excludes barriers.
- Excludes target-side DMG vulnerability.
- Does not compare remaining duration.
- Does not compare remaining total lifetime DMG.

### Stronger Application

A stronger Toxic Blight:

- Completely replaces the previous Toxic Blight's stored offensive properties.
- Replaces its Damage Category distributions.
- Replaces its contributor attribution.
- Replaces its remaining duration with the new application's duration.
- Preserves the existing damage tick timer.

### Weaker Application

A weaker Toxic Blight:

- Does not reduce the existing stronger DMG.
- Does not replace its stored offensive properties.
- Does not replace its contributor attribution.
- Refreshes the duration according to the newest application.
- Preserves the existing damage tick timer.

### Equally Strong Application

An equally strong Toxic Blight refreshes the duration without increasing DMG.

The exact tie-breaking rule for otherwise different but equally strong stored properties remains an implementation detail.

### No Component Mixing

The strongest flat DMG and strongest HP% DMG are not selected independently from different applications.

Toxic Blight preserves or replaces its complete offensive package.

---
## 23. Duration Refreshing

The newest successful direct Toxic Blight application determines the refreshed duration.

The strongest-effect rule preserves DMG strength independently of duration.

### Example

An enemy receives a transferred Toxic Blight with an eight-second duration.

One second later:

- Seven seconds remain.
- Another Toxic Combustion applies a weaker Toxic Blight.
- The new application possesses the default five-second duration.

Result:

- The stronger existing Toxic Blight DMG is preserved.
- The remaining duration becomes five seconds.
- The existing damage tick timer remains unchanged.

A new application can shorten an existing extended duration.

Existing extended durations are not indefinitely preserved through direct reapplication.

---
## 24. Death-Triggered Spreading

Toxic Blight spreads when an affected enemy dies while the infection remains active.

### Activation Conditions

- The defeated enemy possesses an eligible active Toxic Blight.
- The responsible status pool retains valid infection information.
- At least one eligible receiving enemy exists within the spreading radius.

### General Rules

- The enemy does not need to die from Toxic Blight DMG.
- The enemy does not need to possess Poison stacks.
- The enemy does not need to possess Poisonous Strikes.
- Any cause of death can trigger spreading.
- A lethal final Toxic Blight tick qualifies.
- Enemies killed by the initial Toxic Combustion explosion qualify.
- Player death does not prevent subsequent infection transfers.
- Natural expiration does not trigger spreading.
- Cleansing does not trigger spreading.

Toxic Blight maintains its own spreading eligibility independently of ordinary Poisonous Strikes.

---
## 25. Death Spreading Radius and Target Limit

Toxic Blight uses the ordinary Poison spreading radius.

**Toxic Blight Death Spreading Radius = Ordinary Poison Spreading Radius**

- The spreading radius originates from the defeated enemy.
- Ordinary Poison targeting and obstruction rules apply.
- Each defeated infected enemy can transfer Toxic Blight to a maximum of one eligible enemy.
- If no eligible enemy exists, that infection ends.
- The initial 1.5× Combustion radius multiplier does not apply to death spreading.

Unlike ordinary Poisonous Strikes, Toxic Blight does not spread to three enemies per death.

Its one-target transfer restriction prevents exponential infection multiplication through death spreading alone.

---
## 26. Death Spreading Target Eligibility

Eligible receiving enemies must:

- Be alive.
- Be within the applicable spreading radius.
- Satisfy ordinary Poison targeting and obstruction requirements.
- Not already possess an active Toxic Blight belonging to the originating status pool.

### Additional Rules

- Enemies with zero Poison stacks remain eligible.
- Enemies with active Poisonous Strikes remain eligible.
- Enemies protected by Stability Barriers remain eligible.
- Previously infected enemies become eligible again after Toxic Blight expires.
- Toxic Blight belonging to another independent party does not prevent infection.
- Existing Fire stacks or ordinary Burn do not affect eligibility.

Enemies already possessing the originating party's Toxic Blight are skipped entirely.

Death spreading does not refresh or strengthen an already active Toxic Blight.

---
## 27. Death Spreading Target Priority

Eligible receiving enemies are prioritized according to their current Poison stack count.

### Priority Order

1. Enemies with six completed Poison stacks.
2. Enemies with five Poison stacks.
3. Enemies with four Poison stacks.
4. Enemies with three Poison stacks.
5. Enemies with two Poison stacks.
6. Enemies with one Poison stack.
7. Enemies with zero Poison stacks.

If multiple eligible enemies possess the same priority:

- Select the closest enemy to the defeated enemy.

### Responsible Pool

Only Poison stacks belonging to the originating status pool contribute toward targeting priority.

Poison stacks belonging to unrelated players or parties are ignored.

### Completed and Accumulating Sets

Active Poisonous Strikes counts as six Poison stacks.

Independently accumulating Poison stacks are not added to the completed set.

An enemy with Poisonous Strikes and five independently accumulating Poison stacks still possesses a Toxic Blight targeting priority of six, not eleven.

The same zero-to-six stack evaluation applies to transferred duration scaling.

### Example

|Enemy|Poison Stacks|Existing Toxic Blight|Priority|
|---|---:|---|---|
|A|6|Yes|Excluded|
|B|5|No|First|
|C|3|No|Second|
|D|0|No|Third|

Enemy B receives the infection.

---
## 28. Transferred Toxic Blight Duration

Every successful death-triggered transfer establishes a fresh Toxic Blight duration.

The receiving enemy's relevant Poison stack count increases this duration linearly.

### Formula

**Transferred Duration = Base Duration + Poison Stack Count × Duration Bonus per Stack**

Provisional values:

- Base duration: 5 seconds.
- Duration bonus per stack: 0.5 seconds.
- Maximum contributing Poison stacks: 6.

|Poison Stacks|Transferred Duration|
|---:|---:|
|0|5.0 seconds|
|1|5.5 seconds|
|2|6.0 seconds|
|3|6.5 seconds|
|4|7.0 seconds|
|5|7.5 seconds|
|6|8.0 seconds|

### Duration Rules

- The defeated enemy's remaining duration is irrelevant.
- The defeated enemy's original duration is irrelevant.
- Transferred duration is determined upon infection.
- Subsequent Poison applications do not extend or refresh the transferred duration.
- Subsequent Poison expiration does not shorten the transferred duration.
- Poisonous Strikes counts as six stacks.
- Independently accumulating stacks are not added to the completed set.
- Only Poison stacks belonging to the originating status pool contribute.

This rewards preparing future infection targets with Poison without allowing continuous duration extension on an already infected enemy.

---
## 29. Transferred Toxic Blight DMG

Death-triggered spreading preserves the complete offensive properties of the transferred Toxic Blight.

### Preserved Properties

- Flat Poison DPS.
- Stored maximum HP DMG percentage.
- Physical and magical Damage Category distributions.
- Inherited critical DMG properties.
- Original contributor attribution.

### Recalculated Properties

- Actual maximum HP-based DMG using the receiving enemy's maximum HP.
- Applicable Physical DEF.
- Applicable Magical DEF.
- Applicable Poison DMG Resistance.
- Applicable target-side vulnerabilities.
- Applicable Stability Barrier properties.
- Transferred duration.

### Restrictions

- The receiving enemy's stored Poison DMG does not increase Toxic Blight strength.
- The receiving enemy's accumulated Fire Heat does not increase Toxic Blight strength.
- Repeated transfers do not accumulate additional offensive DMG.
- No independent critical strike is rolled upon transfer.
- No transfer-specific DMG falloff is applied.
- No transfer-specific DMG penalty is applied.

Receiving Poison stacks determine targeting priority and duration, not transferred DMG strength.

### Example

Original Toxic Blight:

- Flat Poison DPS: 300.
- Maximum HP Poison DPS: 1%.

Receiving Enemy A:

- Maximum HP: 10,000.
- Poison stacks: 2.
- Transferred duration: 6 seconds.
- Maximum HP Poison DPS: 100.

Receiving Enemy B:

- Maximum HP: 50,000.
- Poison stacks: 6.
- Transferred duration: 8 seconds.
- Maximum HP Poison DPS: 500.

The stored offensive properties remain identical.

Differences arise from receiving enemy properties and transferred duration.

---
## 30. Repeated Infection Generations

Toxic Blight can continue spreading through successive enemy deaths.

### Generation Rules

- No maximum transfer generation count exists for initial testing.
- Every successful transfer receives a fresh duration.
- Every successful transfer preserves the complete offensive properties.
- Each defeated infected enemy can produce a maximum of one new infection.
- Every transfer independently determines its receiving target.
- Every transfer independently evaluates receiving Poison stacks.
- Previously infected enemies can be infected again after expiration.

### Example

Enemy A dies:

- Toxic Blight transfers to Enemy B.

Enemy B dies before its infection expires:

- Toxic Blight transfers to Enemy C.

Enemy C dies before its infection expires:

- Toxic Blight transfers to Enemy D.

The infection can continue while eligible enemies remain available and infected enemies continue dying within their applicable durations.

Repeated transfers do not inherently increase the number of active infections.

---
## 31. Independent Ordinary Poison Spreading

Ordinary Poisonous Strikes spreading and Toxic Blight spreading are independent mechanics.

An enemy dying with both effects can trigger both spreading mechanics.

### Ordinary Poisonous Strikes

- Spreads to a maximum of three eligible nearby enemies.
- Applies three guaranteed Poison stacks to each receiving enemy.
- Prioritizes proximity.
- Preserves ordinary Poison spreading calculations and attribution.

See [[Poison]].

### Toxic Blight

- Spreads to a maximum of one eligible nearby enemy.
- Applies Toxic Blight without applying Poison stacks.
- Prioritizes the highest relevant Poison stack count.
- Uses proximity as the secondary priority.
- Preserves the original Toxic Blight offensive properties.
- Determines duration according to the receiving enemy's Poison stacks.

Neither spreading mechanic consumes or replaces the other.

---
## 32. Simultaneous Poison and Toxic Blight Spreading

When an enemy dies with both Poisonous Strikes and Toxic Blight:

1. Resolve ordinary Poisonous Strikes spreading.
2. Complete resulting Poison stack applications.
3. Resolve applicable Poison stack thresholds.
4. Recalculate eligible Toxic Blight targeting priorities.
5. Select the Toxic Blight receiving enemy.
6. Determine its transferred duration.
7. Apply Toxic Blight.

Newly spread Poison stacks can influence Toxic Blight targeting and duration.

### Example

Enemy A dies with Poisonous Strikes and Toxic Blight.

Surrounding enemies are ordered by proximity:

|Enemy|Initial Poison Stacks|Toxic Blight|
|---|---:|---|
|B|2|No|
|C|1|No|
|D|0|Yes|
|E|4|No|

Ordinary Poison spreads three stacks to B, C and D.

|Enemy|Updated Poison Stacks|Toxic Blight Eligibility|
|---|---:|---|
|B|5|Eligible|
|C|4|Eligible|
|D|3|Excluded|
|E|4|Eligible|

Enemy B receives Toxic Blight because it now possesses the highest eligible Poison stack count.

Its transferred duration becomes 7.5 seconds.

---
## 33. Lethal Initial Explosion

Enemies killed by the primary Toxic Combustion explosion remain eligible to trigger Toxic Blight spreading.

### Resolution Requirements

- Determine all eligible initial Toxic Blight targets.
- Resolve initial Toxic Blight applications as part of the complete Toxic Combustion event.
- Preserve spreading eligibility for enemies killed by the primary explosion.
- Finish all initial infection applications before resolving death-triggered Toxic Blight transfers.

This prevents a dying enemy from selecting another enemy that is about to receive Toxic Blight through the same initial application.

### Example

The initial explosion kills Enemy A.

Enemies B and C survive and are within the initial Toxic Blight radius.

Enemy D is outside the initial radius but within Enemy A's death spreading radius.

After initial applications:

- Enemy B possesses Toxic Blight.
- Enemy C possesses Toxic Blight.
- Enemy D does not possess Toxic Blight.

Enemy A's death-triggered spreading skips B and C.

Enemy D can receive the transferred infection.

---
## 34. Simultaneous Deaths and Target Coordination

Multiple infected enemies can die during the same resolution event.

Toxic Blight transfers belonging to the same responsible status pool coordinate target selection.

### Coordination Rules

- Avoid selecting an enemy already possessing Toxic Blight.
- Avoid selecting an enemy already reserved for another simultaneous Toxic Blight transfer.
- Reevaluate eligible targets when necessary.
- Preserve the Poison stack-based targeting priority.
- Preserve proximity as the secondary priority.
- Apply each successful transfer independently.
- Determine duration from the individual receiving enemy's Poison stacks.

If insufficient eligible enemies remain, excess infection transfers end.

### Independent Parties

Different parties perform their targeting coordination independently.

Different parties can select and infect the same receiving enemy.

---
## 35. Expiration and Simultaneous Spreading

Natural Toxic Blight expiration removes the effect without generating additional consequences.

### Natural Expiration

- Removes Toxic Blight.
- Removes its stored offensive properties from the affected enemy.
- Removes its spreading eligibility.
- Does not apply Poison stacks.
- Does not apply Fire stacks.
- Does not generate an explosion.
- Does not spread Toxic Blight.
- Does not remove ordinary Burn or Poisonous Strikes.

### Simultaneous Resolution

When damage ticks, expiration and death-triggered spreading occur simultaneously:

1. Resolve scheduled damage ticks.
2. Preserve spreading eligibility for enemies killed while Toxic Blight was active.
3. Remove naturally expired Toxic Blight from surviving enemies.
4. Resolve eligible ordinary Poison spreading.
5. Resolve eligible Toxic Blight spreading.

Enemies whose Toxic Blight has just expired are immediately eligible for reinfection.

A lethal final tick still qualifies for spreading even when it coincides with natural expiration.

---
## 36. Cleansing

Toxic Blight is exclusively removable through applicable Poison cleansing.

Fire cleansing does not remove Toxic Blight.

### Ordinary Poison Cleansing

Toxic Blight follows the general cleansing relationship between ordinary status stacks and their stack-independent damaging effects.

An applicable Poison cleanse:

- Removes active Toxic Blight.
- Removes the oldest eligible ordinary Poison stack according to established Poison cleansing rules.
- Preserves the stored properties of surviving Poison stacks.

This is analogous to Fire cleansing removing Burn and the oldest eligible Fire stack.

### Poisonous Strikes Cleansing

If the affected enemy possesses both Poisonous Strikes and Toxic Blight:

- Remove Toxic Blight.
- End Poisonous Strikes.
- Reduce the completed Poison set from six stacks to three stacks through FIFO.
- Preserve the three newest completed stacks.
- Preserve their original stored properties and attribution.

Existing general Poison cleansing rules determine interactions with independently accumulating Poison stacks.

### Spreading Restriction

A cleansed Toxic Blight:

- Cannot spread.
- Does not generate death-triggered infection transfers.
- Does not apply additional Poison stacks.
- Does not transfer its remaining duration or offensive properties.

Toxic Blight may subsequently be applied again through an eligible Toxic Combustion or death-triggered transfer.

---
## 37. Party Ownership

Toxic Blight follows the party-shared status ownership system.

### Within One Party

- A maximum of one active Toxic Blight exists per enemy.
- Strongest-effect comparison applies between applications.
- Death spreading references the originating party's Poison stacks.
- Simultaneous target selection is coordinated within that party.
- Contributor attribution remains independent of shared ownership.

### Between Different Parties

- Different parties maintain independent Toxic Blight effects.
- Different parties can simultaneously infect the same enemy.
- Their DMG values remain independent.
- Their duration timers remain independent.
- Their damage tick timers remain independent.
- Their strongest-effect comparisons remain independent.
- Their death spreading events remain independent.
- Their Poison stack-based targeting priorities remain independent.

One party's Toxic Blight does not prevent another party from infecting the same enemy.

Solo players maintain independent personal Toxic Blight effects.

The potential excessive scaling of independent party-owned effects remains subject to multiplayer balancing.

See [[Status]], [[Party]] and [[Multiplayer]].

---
## 38. Damage Attribution

Toxic Blight preserves the applicable original contributor information.

### Initial Attribution

- Flat DMG references contributing Fire Heat information.
- Maximum HP-based DMG references the completed Poison set's contributor information.
- Applicable general status combination attribution rules remain in effect.
- Sharing a status pool does not duplicate DMG.

### Subsequent Transfers

- Original contributor information remains preserved.
- Receiving Poison stack contributors do not automatically acquire Toxic Blight DMG attribution.
- Receiving enemy properties do not modify original offensive attribution.
- Subsequent infection generations do not independently create additional contributors.
- Original contributor death does not prevent continued attribution.

### Strongest-Effect Replacement

- A stronger Toxic Blight replaces the previous effect's stored contributor attribution.
- A weaker Toxic Blight refreshes duration without taking ownership of the stronger effect's DMG.
- Attribution from unrelated Toxic Blight applications is not merged.

The exact distribution of combination damage credit follows the applicable general attribution system.

See [[Participation and Loot]].

---
## 39. Player Death and Effect Persistence

Toxic Blight remains active after the death of its original contributing players.

### Persistence Rules

- Stored offensive properties remain unchanged.
- Existing durations continue normally.
- Existing damage tick timers continue normally.
- Eligible death-triggered spreading remains possible.
- Original contributor attribution remains preserved.

Toxic Blight does not require its originating players to remain alive to continue spreading.

Party membership changes, disconnections and map departure follow applicable general status persistence rules.

---
## 40. General Status Damage Restrictions

Toxic Blight follows the general restrictions for additional status DMG.

- Does not automatically trigger ordinary Status Chance rolls.
- Does not automatically apply Poison stacks through its damage ticks.
- Does not automatically apply Fire stacks through its damage ticks.
- Does not independently trigger general on-hit effects.
- Does not automatically trigger Life Steal.
- Does not automatically generate Stability recovery.
- Does not automatically generate additional status combinations.
- Does not generate remembered Heat.
- Does not independently recalculate stored offensive properties.

Death-triggered infection transfer is an explicitly permitted spreading mechanic.

It does not constitute an ordinary attack hit or ordinary status stack application.

---
## 41. Cooldowns and Restrictions

Toxic Combustion possesses no dedicated combination-specific cooldown.

Toxic Blight possesses:

- No dedicated application cooldown.
- No dedicated death spreading cooldown.
- No transfer generation cooldown.
- No maximum transfer generation count for initial testing.

### Natural Restrictions

Toxic Blight is instead restricted through:

- Fire's six-stack activation requirement.
- The requirement for an eligible completed Poison set.
- Poisonous Strikes' limited duration.
- The initial infection radius.
- The ordinary Poison death spreading radius.
- The one-target death spreading limit.
- Exclusion of already infected enemies.
- Independent effect expiration.
- Poison cleansing.
- Strongest-effect comparison.
- Target-side defenses and resistances.
- Stability Barrier protection.

These restrictions should be evaluated before introducing additional internal cooldowns.

---
## 42. Toxic Combustion Lifecycle

### Initial Activation

Six Fire stacks + Eligible completed Poison set

→ Toxic Combustion
→ Ordinary Fire explosion
→ Fire stacks and accumulated Heat consumed
→ Poisonous Strikes preserved
→ Toxic Blight applied within 1.5× ordinary Combustion radius.

### Initial Infection

Toxic Blight

→ Five-second duration
→ Flat and maximum HP-based Poison DMG every 0.5 seconds.

### Death Transfer

Infected enemy dies

→ Resolve ordinary Poison spreading if applicable

→ Select highest-priority eligible enemy

→ Transfer Toxic Blight with unchanged offensive properties

→ Establish fresh duration based on receiving Poison stacks.

### Natural Expiration

Toxic Blight expires

→ Infection removed

→ No additional effects.

### Cleansing

Poison cleanse

→ Toxic Blight removed

→ Applicable Poison stack cleansing resolved

→ No infection transfer.

### Reapplication

Another Toxic Combustion applies Toxic Blight

→ Compare combined pre-mitigation DPS

→ Preserve stronger offensive properties

→ Apply newest duration

→ Preserve existing damage tick timer.

---
## 43. Comprehensive Example

### Initial Situation

Enemy A possesses:

- Six Fire stacks.
- Eligible remembered Heat.
- Active Poisonous Strikes.
- A completed Poison set providing 1% maximum HP-based DMG.

Toxic Combustion activates.

Assuming the ordinary Combustion Burn calculation would provide 300 DPS:

- Primary explosion deals ordinary Fire DMG.
- All contributing Fire stacks and accumulated Heat are consumed.
- Poisonous Strikes remains active.
- No ordinary Combustion Burn is generated.
- No remembered Heat is propagated.
- Toxic Blight is applied within 1.5× ordinary Combustion radius.

### Initial Toxic Blight

Every eligible affected enemy receives:

- 300 flat Poison DPS.
- 1% maximum HP Poison DPS.
- Five-second duration.
- 0.5-second tick interval.

Every tick deals:

- 150 flat Poison DMG.
- 0.5% maximum HP Poison DMG.

### Enemy Death

Enemy B dies while infected.

Nearby enemies:

|Enemy|Poison Stacks|Existing Toxic Blight|
|---|---:|---|
|C|6|Yes|
|D|5|No|
|E|3|No|
|F|0|No|

Enemy C is excluded.

Enemy D receives Toxic Blight.

### Transferred Infection

Enemy D receives:

- 300 flat Poison DPS.
- 1% maximum HP Poison DPS.
- 7.5-second duration.
- 0.5-second tick interval.
- Original Damage Category distributions.
- Original contributor attribution.

Enemy D's five Poison stacks do not increase Toxic Blight DPS.

If Enemy D dies before expiration, the infection can transfer again.

All values are illustrative and exclude target-side mitigation.

---
## 44. Superseded Mechanics

The following previously proposed Toxic Combustion mechanics are removed:

- Spreading 50% of a fully stacked Poison DoT.
- Conventional Poison DoT inheritance.
- Consuming the completed Poison set upon activation.
- Removing Poisonous Strikes upon activation.
- Refreshing Poisonous Strikes through Toxic Combustion.
- Applying three guaranteed Poison stacks to surrounding enemies through Toxic Combustion.
- Converting all potential Burn ticks into immediate HP-based explosion DMG.
- Generating ordinary Combustion Burn alongside the newly generated Toxic Blight.
- Propagating remembered Heat alongside Toxic Blight.
- Replacing previously existing ordinary Burn with Toxic Blight.
- Preventing subsequent ordinary Burn from coexisting with Toxic Blight.
- Prioritizing enemies with the fewest Poison stacks.
- Prioritizing enemies with zero Poison stacks.
- Increasing transferred Toxic Blight DMG through receiving enemy Poison stacks.
- Accumulating additional DMG through successive infection generations.
- Refreshing Toxic Blight through ordinary Fire applications.
- Refreshing Toxic Blight through ordinary Poison applications.
- Applying mixed Fire-Poison DMG Resistance calculations.
- Performing an additional independent Toxic Blight critical strike.
- Globally shared Toxic Blight ownership across unrelated parties.

These mechanics are superseded by the current Toxic Combustion design.

---
## 45. Remaining Balancing and Implementation Questions

### Numerical Balancing

- Exact ordinary Combustion Burn DMG scaling.
- Exact Poisonous Strikes HP% DMG scaling.
- Toxic Blight performance against high-HP enemies.
- Toxic Blight performance against elites and bosses.
- Effectiveness of maximum HP-based DMG against ordinary DEF.
- Initial 1.5× application radius multiplier.
- Five-second default duration.
- 0.5-second duration bonus per Poison stack.
- Ordinary Poison spreading radius.
- Damage rounding for 0.5-second ticks.
- Independent party-owned Toxic Blight scaling.
- Repeated utilization of the same completed Poison set.
- Unlimited infection transfer generations.

### Implementation Details

- Deterministic ordering between otherwise equally eligible simultaneous infection sources.
- Tie-breaking between equally strong Toxic Blight effects with different stored offensive properties.
- Exact initial application and lethal explosion event processing.
- Integration with general party membership and status persistence rules.
- Integration with remaining general Poison cleansing edge cases.
- Final damage attribution calculations under the general combination system.
- Performance of simultaneous infection target selection.

These remaining considerations do not prevent initial implementation of the established core mechanics.

---
## 46. Visual Representation

Toxic Blight should be visually distinguishable from ordinary Burn and ordinary Poison.

Potential visual elements:

- Poison-colored combustion flames.
- Persistent toxic particles surrounding infected enemies.
- Distinct Toxic Blight status indicator.
- Visible death-triggered infection transfer.
- Recognizable 0.5-second damage tick rhythm.
- Clear distinction between Toxic Blight and ordinary Poison stacks.
- Visual feedback for transferred infections with increased duration.

Exact visual representation remains undecided.

---
## 47. Design Status

### Mechanically Established

- Fire and Poison combination activation.
- Ordinary primary Combustion explosion.
- Fire stack and accumulated Heat consumption.
- Preservation of Poisonous Strikes.
- Repeated utilization of completed Poison sets.
- Conversion of Burn and Heat propagation into Toxic Blight.
- Independent coexistence with existing ordinary Burn.
- Flat and maximum HP-based Poison DMG.
- Independent physical and magical Damage Category distributions.
- Final Damage Type-based resistance calculation.
- Ordinary corresponding DEF interaction.
- Ordinary Stability Barrier interaction.
- Inherited critical DMG without an additional critical roll.
- Unlimited initial infection targets.
- Increased initial application radius.
- No Toxic Blight DMG falloff.
- Five-second initial duration.
- 0.5-second damage tick interval.
- DPS-preserving tick calculations.
- Strongest-effect comparison using combined pre-mitigation DPS.
- Newest-application duration refreshing.
- Independent damage tick timer preservation.
- Death-exclusive infection transfers.
- One receiving enemy per defeated infected enemy.
- Highest-Poison-stack targeting priority.
- Proximity-based secondary targeting priority.
- Exclusion of already infected enemies.
- Zero-to-six Poison stack duration evaluation.
- Linear transferred duration scaling.
- Full offensive property preservation through transfers.
- No accumulating DMG amplification.
- Unlimited transfer generations.
- Independent ordinary Poison spreading.
- Ordinary Poison spreading before Toxic Blight spreading.
- Coordinated simultaneous target selection.
- Lethal initial explosion spreading eligibility.
- Lethal final tick spreading eligibility.
- Expiration before subsequent infection target selection.
- Poison-specific cleansing.
- Independent party ownership.
- Persistent original contributor attribution.
- Persistence following contributor death.
- No dedicated internal cooldown.
- No additional ordinary status stack applications.

### Further Development

Toxic Combustion's core mechanical identity is established and ready for initial implementation.

Further development primarily concerns numerical balancing, visual representation and integration with the general status resolution system.

---
## Related Notes

- [[Status]]
- [[Fire]]
- [[Poison]]
- [[Cool Combustion]]
- [[Arc Combustion]]
- [[Damage Calculation]]
- [[Critical Hits]]
- [[Stability Barrier System]]
- [[Normal Attacks]]
- [[Party]]
- [[Multiplayer]]
- [[Participation and Loot]]