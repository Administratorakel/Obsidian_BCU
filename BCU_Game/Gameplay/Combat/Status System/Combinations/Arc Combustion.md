# Arc Combustion — Status Combination

## 1. Overview

- **Combination:** [[Fire]] + [[Lightning]]
- **Category:** Elemental + Elemental
- **Identity:** Electrical chain reactions, distributed explosions, Charge harvesting and recursive combination activation.
- **Primary Damage Type:** Fire.
- **Secondary Damage Type:** Lightning.
- **Damage Categories:** Physical and Magical.
- **Activation:** Six Fire stacks and an eligible completed Lightning set.
- **Primary explosions per activation:** 1.
- **Electrical arcs per activation:** 3.
- **Journeys per arc:** 2.
- **Secondary explosions per activation:** 6.
- **Maximum targeting range per journey:** 5 meters (provisional).
- **Wave interval:** 1 second (provisional).
- **Secondary explosion radius:** 50% of ordinary Combustion radius (provisional).
- **Secondary DMG falloff:** None.
- **Combination-specific cooldown:** None.
- **Maximum recursion depth:** Unrestricted for initial testing.
- **Availability:** Solo and multiplayer.

---
## 2. Design Philosophy

Arc Combustion combines Fire's accumulated Heat with Lightning's accumulated electrical Charge.

Unlike [[Cool Combustion]], which consumes accumulated Fire potential throughout its surrounding area, Arc Combustion selectively interacts with enemies through electrical arcs.

### Core Identity

- Initial Fire explosion.
- Distributed Lightning explosions.
- Selective Charge harvesting.
- Prioritization of prepared enemies.
- Animation interruptions.
- Guaranteed Lightning applications.
- Recursive status combination activation.
- Potentially extensive chain reactions.
- Strong offensive potential against both scattered enemy groups and isolated targets.

Arc Combustion should reward players who deliberately distribute Lightning stacks across several enemies before activating the combination.

Its recursive potential is intentionally unrestricted during initial implementation and experimentation.

---

## 3. Activation Requirements

Arc Combustion requires:

- Six Fire stacks.
- An eligible completed Lightning set.
- Both status sets belonging to the same responsible status pool.

### Eligible Activation States

Arc Combustion can activate when:

- Fire reaches six stacks against an enemy with an existing completed Lightning set.
- Fire and Lightning complete simultaneously through the same damage instance.
- A guaranteed Lightning application completes an eligible combination requirement.
- Another explicitly established mechanic produces both required eligible sets.

### Activation Priority

- Arc Combustion activates automatically.
- Eligible combinations take priority over ordinary sixth-stack payoffs.
- Ordinary Combustion does not resolve as an additional independent explosion.
- Ordinary Lightning Discharge does not separately resolve when its newly completed set is immediately consumed by Arc Combustion.
- Competing combinations follow the universal combination priority rules.

See [[Status]].

---

## 4. Simultaneous Status Completion

Fire and Lightning may complete through the same damage instance.

### Resolution

1. Complete both eligible status sets.
2. Check for eligible status combinations.
3. Calculate accumulated Fire Heat.
4. Calculate accumulated Lightning Charge.
5. Perform the applicable ordinary Discharge critical calculation.
6. Establish the Charge available to Arc Combustion.
7. Consume the relevant completed status sets.
8. Resolve the primary Fire explosion.
9. Begin the electrical arc sequence.

### Lightning Discharge Restrictions

When Arc Combustion replaces a newly triggered ordinary Lightning Discharge:

- No ordinary Discharge stun is applied.
- No new Discharge speed buff is granted.
- The ordinary Discharge critical calculation is still performed where required to establish completed Charge.
- Previously granted player-side Discharge buffs remain unaffected.

The calculated Charge becomes available to the electrical arcs.

---

## 5. Primary Fire Explosion

The initial explosion follows ordinary [[Fire]] Combustion mechanics.

### Established Properties

- Uses accumulated Fire Heat.
- Includes applicable remembered propagated Heat.
- Preserves ordinary Combustion's Damage Categories.
- Preserves ordinary Combustion's critical strike calculation.
- Preserves ordinary explosion radius.
- Preserves ordinary distance-based DMG falloff.
- Applies Burn normally.
- Propagates Heat normally.
- Consumes the primary target's eligible Fire stacks and stored Heat.

Lightning does not directly increase the primary Fire explosion's DMG.

### Damage Classification

- Damage Type: Fire.
- Damage Categories: Physical and Magical.
- Original Heat Damage Category proportions remain preserved.

### Ordinary Combustion Interaction

Arc Combustion's primary explosion represents its Fire component.

It does not generate an additional separate ordinary Combustion beyond this primary explosion.

See [[Fire]].

---

## 6. Electrical Arc Structure

After the initial Fire explosion, three electrical arcs originate from the primary target.

Each arc independently completes two journeys.

### Explosion Structure

- Initial Fire explosion: 1.
- First-wave Lightning explosions: 3.
- Second-wave Lightning explosions: 3.

**Total explosions per Arc Combustion activation = 7**

Every activation produces the complete intended explosion structure, even when insufficient enemies are available.

### Arc Independence

Each arc possesses:

- Its own current position.
- Its own selected target.
- Its own travel path.
- Its own originating Charge reference.
- Its own remaining journey count.
- Its associated Arc Combustion activation identifier.
- Its associated chain reaction identifier.

Arcs coordinate target selection and wave timing while preserving independent explosion DMG.

---
## 7. Wave Timing

Arc Combustion uses fixed wave timing rather than fixed electrical arc travel speed.

### Provisional Timeline

|Time|Event|
|---|---|
|0 seconds|Primary Fire explosion.|
|1 second|All three first-wave Lightning explosions resolve.|
|2 seconds|All three second-wave Lightning explosions resolve.|

### General Timing Rules

- All arcs belonging to one activation share the same first-wave arrival time.
- All arcs belonging to one activation share the same second-wave arrival time.
- The provisional interval between waves is one second.
- Different travel distances do not change the scheduled arrival time.
- Travel speed adjusts according to the required distance.
- Short journeys retain the same arrival timing as long journeys.
- Remaining on the same enemy does not cause immediate additional explosions.

### Visual Travel

The arcs should visually communicate electrical movement between enemies.

Potential presentation:

- Brief electrical buildup.
- Rapid electrical movement.
- Simultaneous detonation at the scheduled wave time.

The exact visual distribution of waiting time and travel animation remains undecided.

### Superseded Travel Rule

The previous proposal of a fixed travel speed with distance-dependent arrival times is no longer applicable.

Fixed wave duration takes priority.

---

## 8. Arc Targeting Range

Each individual arc journey possesses a provisional maximum targeting range of five meters.

### First Wave

- Range is measured from the initial explosion center.
- Each arc selects an eligible target within five meters.

### Second Wave

- Range is measured from the arc's first destination.
- Each arc independently selects a new eligible target within five meters.

An arc can therefore travel up to ten meters across both journeys.

### Range Restrictions

- The targeting range does not scale with stored Heat.
- The targeting range does not scale with stored Charge.
- Returning to the primary target must respect the same targeting range.
- No additional range is granted simply because a target previously participated in the combination.

The five-meter range remains provisional.

---

## 9. Targeting Priority

Electrical arcs prioritize enemies based on their incomplete ordinary Lightning stack progression.

### Priority Order

1. Highest ordinary Lightning stack count.
2. Previously untargeted enemies.
3. Closest eligible enemy.

### Lightning Stack Priority

|Ordinary Lightning Stacks|Relative Priority|
|---|---|
|5|Highest.|
|4|High.|
|3|Medium-high.|
|2|Medium.|
|1|Low.|
|0|Lowest.|

### Completed Lightning Sets

- A completed Lightning set does not automatically grant six-stack targeting priority.
- Arcs prioritize enemies that are close to completing another ordinary Lightning set.
- An enemy with a completed set and independently accumulating ordinary stacks is evaluated according to its ordinary stack count.
- Completed-set Charge remains potentially relevant to harvesting, but does not independently increase targeting priority.

### Responsible Pool

Only Lightning stacks belonging to the responsible pool are considered.

Lightning stacks belonging to unrelated players or parties do not influence targeting priority.

---

## 10. Coordinated Target Selection

All three arcs coordinate their target selection at the beginning of each wave.

### General Rules

- Arcs attempt to select different enemies when equally suitable alternatives exist.
- Previously untargeted enemies receive priority when ordinary stack counts are equal.
- Higher ordinary Lightning stack counts take priority over untargeted enemies with fewer stacks.
- Proximity resolves remaining equal-priority alternatives.
- Multiple arcs may select the same enemy when appropriate.
- Duplicate targeting does not reduce explosion DMG.

### First-Wave Selection

The first wave selects targets following the primary Fire explosion.

### Second-Wave Selection

The second wave selects targets after the first-wave effects have resolved.

This allows:

- Newly applied Lightning stacks.
- Consumed Charge.
- Enemy deaths.
- Newly triggered combinations.
- Changed enemy positions.

To influence the next target selection.

### Final Targeting Decisions

The exact tie-breaking method between enemies with genuinely identical targeting priority remains an implementation detail.

---

## 11. Moving Targets

Once an arc selects an eligible enemy:

- The arc retains that enemy as its target.
- The arc follows the enemy's movement.
- Moving beyond the original five-meter targeting range does not invalidate the selected target.
- Arrival still occurs at the scheduled wave time.
- Travel presentation adjusts to the enemy's changing position.

The range restriction applies when selecting a target, rather than continuously throughout travel.

### Status Changes During Travel

Changes to the selected enemy's Lightning stacks do not cause automatic retargeting.

- Newly applied Lightning stacks can increase harvested Charge.
- Cleansing can reduce harvested Charge.
- Expiration can remove eligible Charge.
- Other combinations can consume relevant statuses.

Charge harvesting references the target's actual status properties when the arc arrives.

---

## 12. Insufficient Targets

Arc Combustion always attempts to resolve its complete six secondary explosions.

### Fewer Than Three Eligible Enemies

- Multiple arcs may target the same enemy.
- Duplicate targeting does not reduce their individual explosion DMG.
- Simultaneous direct arrivals use the shared status interaction rules.

### Isolated Primary Target

If no surrounding enemies are available:

- All three arcs remain on the primary target.
- The first three Lightning explosions occur at the first scheduled wave.
- The remaining three Lightning explosions occur at the second scheduled wave.
- Each wave applies one guaranteed Lightning stack.
- Each wave performs one Charge harvesting calculation.
- Each wave performs one animation interruption calculation.

The isolated primary enemy therefore experiences:

- One primary Fire explosion.
- Six secondary Lightning explosions.
- Two guaranteed Lightning application events.
- Two possible animation interruption events.

Guaranteed applications may subsequently be consumed through Charge harvesting.

### Returning Arcs

If an arc cannot find another eligible surrounding enemy:

- It may return to the primary target.
- The primary target must be within five meters of the arc's current position.
- Returning arcs follow ordinary direct targeting rules.
- Returning arcs can apply Lightning, harvest Charge and interrupt the primary target.

### No Eligible Target Within Range

If no eligible target exists and the primary target cannot be reached:

- The arc detonates at its current location.
- The scheduled explosion still occurs.
- The explosion deals its ordinary AoE Lightning DMG.
- No guaranteed Lightning stack is applied.
- No target-specific Charge is harvested.
- No direct arc interruption occurs.

---

## 13. Target Death During Travel

If an arc's selected enemy dies before its scheduled arrival:

- The arc retains the intended destination.
- The explosion occurs at the enemy's last relevant position.
- The scheduled wave timing remains unchanged.
- Nearby surviving enemies can receive the explosion's AoE DMG.

However:

- No Lightning stack is applied to the deceased enemy.
- No Charge is harvested from the deceased enemy.
- No direct animation interruption is applied.

The arc does not automatically select a replacement target during the existing journey.

The next journey follows ordinary target selection rules from the resulting explosion location.

---

## 14. Secondary Explosion Radius

All six secondary explosions use the same fixed radius.

### Provisional Formula

**Secondary Explosion Radius = Ordinary Combustion Radius × 0.5**

### General Rules

- First-wave and second-wave explosions have identical base radii.
- Radius does not scale with originating Charge.
- Radius does not scale with locally harvested Charge.
- Radius does not increase when multiple arcs target the same enemy.
- Every arc produces its own AoE explosion.

The radius multiplier remains provisional for testing.

---

## 15. Secondary Explosion DMG Falloff

Secondary Lightning explosions do not possess distance-based DMG falloff.

- The directly targeted enemy receives 100% of the calculated explosion DMG before mitigation.
- Every additional enemy within the explosion radius receives 100% of the calculated explosion DMG before mitigation.
- Distance from the explosion center does not reduce DMG.
- Each receiving enemy calculates its own applicable mitigation.

The limited explosion radius distinguishes these electrical explosions from the larger ordinary Fire explosion.

---

## 16. Originating Lightning Charge

Each arc carries a reference to the full completed Charge used to activate its Arc Combustion.

### Charge Calculation

- Existing completed Lightning sets use their remembered completed Discharge Charge.
- Applicable previously calculated critical properties remain included.
- Newly completed Lightning sets perform the appropriate Discharge critical calculation where necessary.
- The originating Charge is fixed upon combination activation.

### Charge Duplication Across Arcs

The originating Charge is not divided among the three arcs.

Each arc independently references the full originating Charge.

### Example

If Arc Combustion activates using 600 completed Charge:

- Arc A carries 600 Charge.
- Arc B carries 600 Charge.
- Arc C carries 600 Charge.

Each arc retains its own 600 originating Charge for both journeys.

The completed Lightning set on the primary target is consumed only once.

The repeated use of its calculated Charge across six explosions is an intentional combination payoff.

### Balance

This Charge structure remains provisional for initial testing.

---

## 17. Secondary Explosion Damage Calculation

Secondary explosions convert electrical Charge into Lightning DMG.

### Base Formula

**Secondary Explosion DMG = Applicable Explosion Charge × Charge-to-DMG Coefficient**

The Charge-to-DMG coefficient remains undecided.

### Applicable Explosion Charge

Applicable Charge can contain:

- The arc's originating Charge.
    
- Its allocated share of locally harvested Charge.
    

### General Rules

- All six secondary explosions use the same Charge-to-DMG coefficient.
    
- First-wave and second-wave explosions have equal base strength when their applicable Charge values are equal.
    
- Locally harvested Charge uses the same conversion coefficient as originating Charge.
    
- Wave number does not inherently increase or reduce DMG.
    
- Additional harvested Charge strengthens the applicable local explosion.
    
- Simultaneous arrivals can distribute harvested Charge across multiple explosions.
    

---

## 18. Guaranteed Lightning Applications

Every eligible direct arc arrival event applies one guaranteed Lightning stack to its target.

### Single Arc Arrival

For an individual arc:

**Guaranteed Stack Charge = Originating Arc Charge ÷ 6**

### Example

An arc carries 600 Charge.

Its guaranteed Lightning application contains:

**600 ÷ 6 = 100 Charge**

### Application Rules

- The stack is guaranteed.
    
- No ordinary Status Chance roll occurs.
    
- Status Chance Resistance does not prevent the application.
    
- The stack retains inherited offensive properties.
    
- The stack retains inherited proportional contributor attribution.
    
- The stack retains applicable Damage Category proportions.
    
- No additional critical strike roll is performed.
    

### Simultaneous Arrivals

Multiple eligible arcs hitting the same enemy during the same chain reaction wave event apply only one guaranteed Lightning stack.

The stack's Charge references the combined originating Charge of those arcs.

See Section 24.

---

## 19. Ordinary Lightning Milestones

Guaranteed arc applications can trigger ordinary Lightning milestone effects.

### Third Stack

Reaching three stacks can trigger:

- Ordinary Lightning stun.
    

### Fourth Stack

Reaching four stacks can trigger:

- Fourth-stack Static Charge animation interruption.
    

### Fifth Stack

Reaching five stacks can trigger:

- Fifth-stack Static Charge animation interruption.
    

### Sixth Stack

Reaching six stacks performs the ordinary combination eligibility check.

If no eligible combination takes priority:

- Ordinary Lightning Discharge activates.
    
- The applicable Discharge critical calculation occurs.
    
- The ordinary Discharge stun can activate.
    
- The ordinary Discharge buff can be granted.
    
- The completed Charge becomes available for subsequent harvesting.
    

### General Rule

Ordinary milestone effects resolve before applicable Charge harvesting.

The later consumption of Lightning Charge does not retroactively invalidate already resolved milestone effects or previously granted player buffs.

---

## 20. Charge Harvesting

Direct arc arrivals can harvest eligible accumulated Lightning Charge from their targeted enemy.

### Core Rules

- Apply the guaranteed Lightning stack first.
    
- Resolve ordinary stack progression.
    
- Resolve eligible status combinations.
    
- Resolve applicable ordinary Lightning milestone effects.
    
- Determine the remaining eligible Charge.
    
- Consume eligible Charge.
    
- Convert harvested Charge into additional local explosion DMG.
    

### Eligible Charge

Depending on the target's current status state, harvesting can reference:

- Ordinary Lightning stacks.
    
- Their associated accumulated Charge.
    
- The newly applied guaranteed Lightning stack.
    
- Eligible remembered completed Discharge Charge.
    

### Restrictions

- Charge consumed by another combination cannot be harvested again.
    
- Charge cannot be harvested twice by simultaneous arcs.
    
- Only the responsible pool's Charge can be harvested.
    
- Enemies merely caught in an explosion's AoE do not have their Charge harvested.
    
- Locally harvested Charge does not increase the arc's permanent originating Charge.
    

---

## 21. Completed Lightning Sets & FIFO

Targets can possess:

- An existing completed Lightning set.
    
- An independently accumulating ordinary Lightning set.
    

Arc applications follow ordinary Lightning progression and replacement rules before harvesting occurs.

### Resolution Principles

- FIFO governs eligible ordinary stack replacement.
    
- Newly applied stacks resolve before harvesting.
    
- Existing completed-set Charge follows established Lightning completed-set resolution.
    
- An eligible combination receives priority over ordinary Charge harvesting.
    
- Remaining eligible Lightning Charge is consumed normally afterward.
    

The interaction must preserve Lightning's independently established completed-set and building-set behavior.

### Previously Granted Buffs

Consuming a completed Lightning set does not remove previously granted player-side Discharge buffs.

This applies to both the primary target and surrounding enemies.

### Implementation Detail

The exact mapping of FIFO replacement to simultaneous completed and accumulating sets must remain consistent with [[Lightning]].

No separate unrestricted Charge duplication is introduced through harvesting.

---

## 22. Locally Harvested Charge

Harvested Charge strengthens only the explosion associated with the enemy from which it was consumed.

It is not carried forward into the arc's next journey.

### Example

An arc carries 600 originating Charge.

#### First Target

- Originating Charge: 600.
    
- Locally harvested Charge: 300.
    
- Applicable explosion Charge: 900.
    

#### Second Target

- Originating Charge: 600.
    
- Locally harvested Charge: 200.
    
- Applicable explosion Charge: 800.
    

The first target's harvested Charge does not increase the second explosion's originating Charge.

### Purpose

- Reward preparing individual enemies.
    
- Prevent unnecessary cumulative Charge amplification.
    
- Keep arc path calculations predictable.
    
- Reduce uncontrolled scaling during recursive chain reactions.
    

---

## 23. Charge Consumption Priority

If an arc's guaranteed Lightning application triggers another status combination, that combination receives priority over the originating arc's harvesting.

### Example

An enemy possesses:

- Five Lightning stacks.
    
- An eligible Fire combination requirement.
    
- Accumulated Lightning Charge.
    

An arc applies the sixth Lightning stack.

If Arc Combustion activates:

- The newly triggered Arc Combustion uses its eligible completed Charge.
    
- The same consumed Charge cannot additionally strengthen the originating arc.
    
- The originating arc retains its own full base explosion DMG.
    
- The originating arc continues its planned journey if another journey remains.
    

### General Rule

A stored Charge contribution cannot simultaneously be consumed by:

- A newly triggered combination.
    
- The originating arc's local harvesting.
    

Any Charge remaining after combination resolution may still be eligible for ordinary harvesting.

---

## 24. Simultaneous Arc Arrivals

Multiple arcs belonging to the same Arc Combustion chain can simultaneously target one enemy.

These arrivals share a single status interaction calculation while retaining individual explosion DMG.

### Combined Charge

**Combined Originating Charge = Sum of Originating Charge of All Eligible Arriving Arcs**

### Guaranteed Stack

**Guaranteed Stack Charge = Combined Originating Charge ÷ 6**

### Shared Status Interaction

Simultaneous eligible arrivals produce:

- One guaranteed Lightning stack.
    
- One ordinary milestone progression check.
    
- One combination eligibility check.
    
- One Charge harvesting event.
    
- One animation interruption event.
    

### Individual Explosion Resolution

- Every arriving arc still produces its own Lightning explosion.
    
- Each explosion retains its original originating Charge.
    
- Harvested Charge is distributed proportionally among those explosions.
    
- Harvested Charge is counted only once across the combined explosions.
    

### Example

Three arcs simultaneously target one enemy.

Each arc carries 600 Charge.

The enemy already possesses 300 accumulated Charge.

#### Combined Originating Charge

600 + 600 + 600 = 1,800

#### Guaranteed Stack

1,800 ÷ 6 = 300

#### Locally Harvested Charge

300 existing Charge + 300 newly applied Charge = 600

#### Combined Explosion Charge

1,800 + 600 = 2,400

#### Individual Explosion Allocation

|Arc|Originating Charge|Allocated Harvested Charge|Total Explosion Charge|
|---|---|---|---|
|A|600|200|800|
|B|600|200|800|
|C|600|200|800|
|Total|1,800|600|2,400|

Each arc then retains its original 600 originating Charge for its next journey.

---

## 25. Proportional Harvested Charge Distribution

Simultaneously arriving arcs can possess different originating Charge values.

Locally harvested Charge is distributed proportionally according to their originating Charge.

### Formula

**Allocated Harvested Charge = Total Harvested Charge × (Individual Arc Originating Charge ÷ Combined Originating Charge)**

### Example

|Arc|Originating Charge|Relative Share|
|---|---|---|
|A|600|40%|
|B|900|60%|
|Total|1,500|100%|

Assume the simultaneous arrival harvests 500 Charge.

|Arc|Originating Charge|Harvested Charge Allocation|Applicable Explosion Charge|
|---|---|---|---|
|A|600|200|800|
|B|900|300|1,200|
|Total|1,500|500|2,000|

### General Rules

- Harvested Charge is not duplicated.
    
- Original Damage Category proportions remain preserved.
    
- Original contributor attribution remains preserved.
    
- Locally harvested Charge retains its originating offensive properties.
    
- Each arc still produces an independent AoE explosion.
    

Distribution concerns the damage allocation of the harvested Charge rather than transferring permanent ownership to the receiving arc.

---

## 26. Arc Combustion Chain Identifiers

Every independently triggered Arc Combustion establishes a unique chain reaction identifier.

### Chain Membership

All recursively triggered Arc Combustions originating from that initial activation inherit its chain identifier.

This includes:

- The initial Arc Combustion.
    
- Arc Combustions triggered by its first wave.
    
- Arc Combustions triggered by its second wave.
    
- Further descendants triggered by those combinations.
    

### Individual Activations

Each Arc Combustion retains its own:

- Activation identifier.
    
- Activation time.
    
- Primary target.
    
- Originating Heat.
    
- Originating Charge.
    
- Three electrical arcs.
    
- First-wave schedule.
    
- Second-wave schedule.
    

Chain membership does not merge separate activations into one damage source.

### Purpose

The shared chain identifier determines which simultaneous arc arrivals can participate in one combined status interaction.

---

## 27. Recursive Wave Synchronization

Recursively triggered Arc Combustions naturally align their wave timing with the originating chain.

### Example Timeline

|Time|Original Arc Combustion A|Recursive Arc Combustion B|
|---|---|---|
|0 seconds|Primary Fire explosion.|—|
|1 second|First-wave explosions.|Triggered by A; primary Fire explosion.|
|2 seconds|Second-wave explosions.|First-wave explosions.|
|3 seconds|Finished.|Second-wave explosions.|

At second two, A's second wave and B's first wave naturally occur together.

### Shared Target Example

At second two:

- Two arcs from A target Enemy X.
    
- Three arcs from B target Enemy X.
    

Because both activations belong to the same chain and resolve during the same wave event:

- All five originating Charge contributions are combined.
    
- One guaranteed Lightning stack is applied.
    
- One Charge harvesting event occurs.
    
- One ordinary milestone progression check occurs.
    
- One animation interruption occurs.
    
- Five independent Lightning explosions deal DMG.
    

### Further Recursion

Additional recursively triggered Arc Combustions follow the same principle.

There is no established maximum number of overlapping descendant activations during initial testing.

---

## 28. Independent Arc Combustions

Separately triggered Arc Combustions do not share chain identifiers.

This applies even when they:

- Belong to the same player.
    
- Belong to the same party.
    
- Target the same enemy.
    
- Possess identical activation times.
    
- Happen to resolve during the same simulation tick.
    

### Independent Resolution

Separate chains maintain independent:

- Guaranteed Lightning applications.
    
- Charge harvesting calculations.
    
- Animation interruption calculations.
    
- Combination eligibility checks.
    
- Explosion DMG.
    

### No Artificial Synchronization

- Arcs do not wait for unrelated arcs to arrive.
    
- No additional synchronization window exists.
    
- Independent wave timers remain unchanged.
    
- An arc does not prematurely reserve or consume Charge for another independent chain.
    

If independent chains affect the same enemy, later resolutions reference the status properties remaining after earlier resolutions.

The exact tie-breaking order for independent chains resolving at precisely the same simulation time remains an implementation detail.

---

## 29. Recursive Arc Combustion Activation

Guaranteed Lightning applications can trigger another Arc Combustion when its requirements are satisfied.

### Recursive Activation Rules

- The new Arc Combustion performs its own primary Fire explosion.
    
- It receives its own calculated Heat and Charge.
    
- It generates three new electrical arcs.
    
- Each new arc completes two journeys.
    
- The new activation inherits the originating chain identifier.
    
- Its waves occur one and two seconds after its own activation.
    
- The originating arcs continue their planned journeys.
    

### Immediate Primary Explosion

The recursively triggered primary Fire explosion occurs immediately when the combination activates.

Its secondary Lightning explosions follow the established wave timing.

### No Initial Recursion Restriction

For initial testing:

- No maximum recursion depth.
    
- No maximum number of descendant activations.
    
- No combination-specific cooldown.
    
- No recursion-specific enemy immunity.
    
- No additional DMG reduction per generation.
    

Recursive combinations must still satisfy their actual status requirements.

---

## 30. Other Status Combination Interactions

Arc Combustion's guaranteed Lightning applications can trigger other eligible status combinations.

Potential examples include:

- [[Shattering Voltage]]
    
- [[Neurotoxin]]
    
- [[Conductive Wounds]]
    
- [[Disruption]]
    
- [[Short Circuit]]
    

### General Rules

- Eligible combinations receive priority over ordinary Charge harvesting.
    
- Consumed Charge cannot be reused by the originating arc.
    
- The originating arc retains its own explosion DMG.
    
- The originating arc continues any remaining journey.
    
- Individual combination mechanics determine their resulting effects.
    

### Chain Ownership

New Arc Combustion activations directly originating from another Arc Combustion inherit its chain identifier.

Chain inheritance through intervening non-Arc Combustion combinations remains to be determined when developing those individual combinations.

---

## 31. Animation Interruptions

Directly targeted enemies receive a Static Charge-like animation interruption.

### Core Mechanics

- The interruption temporarily pauses the affected animation.
    
- The underlying attack or action is not automatically canceled.
    
- The animation resumes from its interrupted position.
    
- Existing attack damage windows remain preserved.
    
- The interruption does not restart the action.
    

These interactions follow ordinary [[Lightning]] Static Charge mechanics.

### Interruption Strength

The interruption depends on the number of previous direct targeting events against that enemy.

|Direct Targeting Event|Interruption Duration|
|---|---|
|First|Fifth-stack Static Charge duration.|
|Second|Fourth-stack Static Charge duration.|
|Further|Fourth-stack Static Charge duration.|

The exact underlying durations reference the ordinary Lightning design and remain provisional.

### Individual Enemy Tracking

- Every enemy tracks its own direct targeting progression.
    
- Wave number does not independently determine interruption strength.
    
- An enemy first targeted during the second wave receives the fifth-stack interruption.
    
- Repeatedly targeting the same enemy produces the shorter interruption.
    

---

## 32. Simultaneous Interruption Events

Multiple simultaneous arc arrivals belonging to the same chain produce only one animation interruption.

### General Rules

- Simultaneous arcs count as one shared targeting event.
    
- The number of arriving arcs does not multiply the interruption duration.
    
- Their originating Charge values are combined for the applicable protection calculation.
    
- Damage remains independent for each explosion.
    

### Isolated Enemy Example

An isolated boss receives all three arcs in both waves.

#### First Wave

- Three Lightning explosions.
    
- One guaranteed Lightning application.
    
- One Charge harvesting calculation.
    
- One fifth-stack Static Charge interruption.
    

#### Second Wave

- Three Lightning explosions.
    
- One guaranteed Lightning application.
    
- One Charge harvesting calculation.
    
- One fourth-stack Static Charge interruption.
    

### Ordinary Milestone Overlap

If the guaranteed Lightning application also triggers an ordinary Static Charge interruption:

- Only the stronger applicable interruption resolves.
    
- Interruption durations do not add together.
    
- Duplicate Stability Barrier protection costs are avoided.
    

Ordinary Lightning stun interactions remain governed by their established milestone rules.

---

## 33. Recursive Interruption Tracking

Each newly triggered Arc Combustion activation maintains independent interruption progression.

### Established Rules

- Recursive activations can provide new first-hit interruption opportunities.
    
- An enemy previously targeted by the original activation can receive a fifth-stack interruption from a new descendant activation.
    
- Simultaneous arrivals belonging to one chain still resolve only one interruption against the same target.
    

### Combined Arrival Strength

If several simultaneous arrivals possess different eligible interruption strengths, the applicable combined event should resolve only one interruption.

The exact selection rule between first-hit and repeated-hit interruption strengths across overlapping descendant activations remains an implementation detail.

### Balance Consideration

Recursive activation may produce extensive interruption chains.

No additional diminishing-return system or temporary interruption immunity is introduced for initial testing.

---

## 34. Direct Targeting & AoE Damage

Arc arrival interactions and secondary explosion damage are separate mechanics.

### Directly Targeted Enemies

Can receive:

- Guaranteed Lightning application.
    
- Ordinary Lightning milestone effects.
    
- Combination activation.
    
- Charge harvesting.
    
- Animation interruption.
    
- Secondary explosion DMG.
    

### Other Enemies Within Explosion Radius

Receive:

- Secondary explosion DMG.
    

They do not automatically receive:

- Guaranteed Lightning stacks.
    
- Charge harvesting.
    
- Direct arc animation interruptions.
    
- Ordinary Lightning milestone effects.
    

### Overlapping Explosions

Enemies within several explosion radii receive DMG from every applicable explosion.

Overlapping AoE DMG does not independently count as direct electrical arc targeting.

---

## 35. Fire Status Interactions

Arc Combustion's primary explosion follows ordinary Fire consumption and propagation rules.

Secondary Lightning explosions do not inherently interact with surrounding Fire status properties.

### Secondary Explosion Restrictions

They do not ordinarily:

- Consume Fire stacks.
    
- Consume stored Heat.
    
- Consume remembered propagated Heat.
    
- Remove existing Burn.
    
- Apply new Burn.
    
- Propagate Heat.
    
- Trigger ordinary Combustion through DMG alone.
    

### Explicit Exception

A guaranteed Lightning application can activate another eligible Arc Combustion.

The resulting new primary Fire explosion follows its own Fire consumption, Burn and Heat propagation rules.

This allows indirect Fire interactions through legitimate recursive combination activation.

---

## 36. Primary Target Status Consumption

The initial Arc Combustion consumes the relevant completed sets on its primary target.

### Fire Consumption

- Six ordinary Fire stacks.
    
- Their accumulated Heat.
    
- Eligible remembered propagated Heat.
    

The resulting primary Fire explosion applies Burn and propagation through ordinary Combustion mechanics.

### Lightning Consumption

- The eligible completed Lightning set.
    
- Its remembered completed Discharge Charge.
    

### Independently Accumulating Lightning

An existing separately accumulating ordinary Lightning set remains untouched by the initial combination activation.

These ordinary stacks can subsequently be affected by:

- Returning electrical arcs.
    
- Guaranteed Lightning applications.
    
- Charge harvesting.
    
- Other ordinary Lightning mechanics.
    

### Previously Granted Buffs

Existing player-side Lightning Discharge buffs remain active for their remaining duration.

---

## 37. Lightning Discharge Buff Interactions

Arc Combustion does not directly grant or refresh the ordinary Discharge speed buff.

### Activation

When Arc Combustion consumes a newly completed Lightning set:

- The ordinary Discharge payoff is replaced.
    
- No ordinary Discharge stun is granted through the initial activation.
    
- No new ordinary Discharge speed buff is granted through that activation.
    

### Existing Buffs

Previously granted buffs:

- Remain active.
    
- Retain their strength.
    
- Retain their remaining duration.
    
- Are not canceled when their originating completed Charge is consumed.
    
- Are not automatically refreshed by Arc Combustion.
    

### Guaranteed Application Exception

An electrical arc can cause ordinary Lightning Discharge on another enemy if its guaranteed stack reaches six and no eligible combination takes priority.

Such an ordinary Discharge can grant its normal speed buff.

The subsequent consumption of its completed Charge does not remove that granted buff.

See [[Lightning]].

---

## 38. Damage Categories & Damage Types

### Primary Explosion

- Damage Type: Fire.
    
- Damage Categories: Physical and Magical.
    
- Preserves original Heat Damage Category proportions.
    

### Secondary Explosions

- Damage Type: Lightning.
    
- Damage Categories: Physical and Magical.
    
- Preserves original Charge Damage Category proportions.
    

### Universal Lightning Revision

Ordinary Lightning previously did not require stored Charge to preserve physical and magical Damage Category distribution.

Arc Combustion converts Charge into actual DMG.

Therefore, Lightning stacks must now retain:

- Original Damage Category.
    
- Stored Charge.
    
- Original contributor.
    
- Applicable critical properties.
    

Propagated and combined Charge can contain contributions belonging to several Damage Categories.

### Conversion Rules

- Physical Charge becomes Physical Lightning DMG.
    
- Magical Charge becomes Magical Lightning DMG.
    
- Original Damage Categories are not rerolled during conversion.
    
- Combined Charge preserves its original component distribution.
    

This universal revision will be consolidated into [[Lightning]] and [[Status]] after reviewing all combinations.

---

## 39. Critical Strike Interactions

### Primary Explosion

Uses ordinary Combustion critical strike mechanics.

### Originating Arc Charge

- Uses the completed remembered Discharge Charge.
    
- Includes applicable previously calculated Discharge critical properties.
    
- Does not perform a new explosion critical strike roll.
    
- Does not reapply previous critical multipliers.
    

### Newly Completed Charge

When Lightning reaches completion directly through Arc Combustion activation:

- The applicable ordinary Discharge critical calculation occurs.
    
- The resulting Charge becomes the originating arc Charge.
    
- No additional secondary explosion critical roll occurs.
    

### Harvested Charge

- Retains its original critical properties.
    
- Does not inherit a new multiplier from the originating arc's critical properties.
    
- Is converted using the applicable stored Charge.
    

### Guaranteed Lightning Stacks

- Inherit one-sixth of the applicable originating Charge.
    
- Preserve inherited critical properties through their stored value.
    
- Do not independently perform another critical roll.
    

### Recursive Critical Scaling

Further legitimate ordinary Discharge calculations can occur when newly completed sets activate through recursive status progression.

Existing critical multipliers must not be reapplied as separate additional multipliers.

The resulting recursive Charge scaling remains a particular playtesting concern.

---

## 40. Defense & Damage Resistance

### Physical and Magical DEF

Each DMG component follows its applicable Damage Category mitigation.

- Physical Fire DMG follows physical Fire mitigation rules.
    
- Magical Fire DMG follows magical Fire mitigation rules.
    
- Physical Lightning DMG follows applicable physical mitigation.
    
- Magical Lightning DMG follows applicable magical mitigation.
    

### Fire DMG Resistance

Fire DMG Resistance mitigates:

- Primary Fire explosion DMG.
    
- Resulting Burn DMG.
    
- Other applicable ordinary Fire damage components.
    

Fire DMG Resistance does not directly mitigate secondary Lightning explosions.

### Lightning DMG Resistance

Lightning DMG Resistance mitigates:

- Secondary Lightning explosion DMG.
    
- Applicable animation interruption duration.
    
- Ordinary Lightning milestone control effects.
    

Lightning DMG Resistance does not directly reduce the primary Fire explosion's offensive calculation.

### Status Chance Resistance

Guaranteed Lightning applications bypass Status Chance Resistance.

However:

- Lightning DMG Resistance remains applicable.
    
- Interruption resistance remains applicable.
    
- Stability Barrier protection remains applicable.
    

---

## 41. Complete Resistance & Immunity

### Complete Lightning DMG Resistance

An enemy with 100% Lightning DMG Resistance can remain an eligible arc target.

- The enemy receives no applicable Lightning DMG.
    
- Its guaranteed Lightning application can still resolve.
    
- Eligible accumulated Charge can still be harvested.
    
- Its position can serve as the center of the secondary explosion.
    
- Surrounding enemies calculate their own Lightning DMG Resistance.
    
- Applicable interruption duration can be reduced to zero.
    

### Fire Resistance

The primary Fire explosion follows ordinary Combustion resistance rules.

Completely Fire-resistant enemies can still serve as strategically useful explosion centers.

### Interruption Immunity

Arc animation interruptions follow ordinary Static Charge immunity rules.

An enemy immune to the applicable interruption can still:

- Receive secondary explosion DMG.
    
- Receive guaranteed Lightning stacks.
    
- Contribute eligible harvested Charge.
    
- Trigger eligible status combinations.
    

---

## 42. Stability Barrier Interactions

Arc Combustion follows applicable damage and interruption protection rules.

See [[Stability Barrier System]] and [[Lightning]].

### Damage Protection

- Primary Fire explosion follows ordinary Fire barrier interactions.
    
- Secondary Lightning explosions interact with Stability Barriers normally.
    
- Arc Combustion does not inherently bypass barriers.
    
- Overlapping explosions remain independent DMG instances.
    

### Animation Interruption Protection

Stability Barriers can protect directly targeted enemies against arc animation interruptions.

Protection follows the established Lightning interruption-related barrier calculation.

### Charge Basis

The applicable interruption protection cost references:

- Combined originating Charge of eligible arriving arcs.
    
- Eligible locally harvested Charge.
    

### Simultaneous Arrivals

When several eligible arcs resolve as one shared targeting event:

- One interruption protection calculation occurs.
    
- Their applicable Charge is combined.
    
- Harvested Charge is counted only once.
    
- Individual explosion DMG remains independent.
    

### Ordinary Milestone Overlap

If a guaranteed application also triggers an ordinary Static Charge interruption:

- Only the stronger applicable interruption resolves.
    
- Duplicate interruption protection costs are avoided.
    

### Unnecessary Protection

If resistance or immunity already prevents the interruption:

- The barrier does not consume capacity to protect against that interruption.
    

### Balance Concern

High accumulated Charge, overlapping explosions and recursive interruptions may produce significant Stability Barrier pressure.

This interaction requires dedicated testing.

---

## 43. Invulnerability

Invulnerable enemies remain eligible for arc targeting.

### General Rules

- Applicable guaranteed Lightning stacks can still be applied.
    
- Eligible accumulated Charge can still be harvested.
    
- Status combinations can still activate when their requirements are satisfied.
    
- The enemy can still serve as an explosion center.
    
- No actual damage is dealt while applicable invulnerability prevents damage.
    
- Surrounding enemies calculate their own damage interactions.
    

Invulnerability does not automatically preserve Charge that would otherwise be consumed.

Applicable control effects follow the established individual immunity and protection rules.

---

## 44. Cleansing Interactions

### Before Activation

Cleansing can prevent Arc Combustion by removing required Fire or Lightning properties before the combination activates.

### During Arc Travel

Cleansing a selected target:

- Does not cause the arc to retarget.
    
- Does not cancel the approaching arc.
    
- Can reduce or remove available local Charge.
    
- Can prevent a potential recursive combination.
    
- Does not reduce the arc's fixed originating Charge.
    

Charge harvesting references the target's remaining eligible status properties upon arrival.

### Cleansing the Original Target

After Arc Combustion activates:

- Cleansing the original target does not cancel its arcs.
    
- Arcs waiting for their scheduled wave continue normally.
    
- Arcs already traveling continue normally.
    
- Originating Charge remains unchanged.
    

### Cleansing Active Arcs

No dedicated cleansing mechanic for electrical arc objects has been established.

The combination's scheduled explosion sequence is not an ordinary enemy-side status effect.

---

## 45. Multiplayer & Pool Ownership

Arc Combustion follows the shared fundamental status pool system.

### Responsible Pool

- Party members contribute to shared Fire and Lightning pools.
    
- Solo players maintain independent pools.
    
- Separate parties maintain independent pools.
    
- Separate non-allied players maintain independent pools.
    

### Targeting

Arc targeting priority references only Lightning stacks belonging to the responsible pool.

### Guaranteed Applications

Guaranteed Lightning stacks are applied to the responsible pool.

### Charge Harvesting

- Only eligible Charge belonging to the responsible pool is consumed.
    
- Other parties' Lightning stacks remain untouched.
    
- Other parties' completed Charge remains untouched.
    
- Other parties' player-side buffs remain unaffected.
    

### Chain Resolution

Shared party ownership alone does not permit simultaneous arc grouping.

Eligible arcs must also belong to the same Arc Combustion chain reaction.

Independent combinations from the same party resolve separately.

---

## 46. Solo & Cooperative Activation

Arc Combustion is available to solo players and parties.

### Solo Players

- A player can independently prepare the required Fire and Lightning sets.
    
- Distinct contributing players are not mandatory.
    
- Future weapon and ability mechanics can support combination preparation.
    
- Companions may assist with status application.
    

### Party Cooperation

Players can specialize in:

- Preparing Fire Heat.
    
- Preparing completed Lightning sets.
    
- Distributing Lightning stacks across surrounding enemies.
    
- Maintaining enemy positioning.
    
- Creating potential recursive combination targets.
    

### Companions

Companions are intended to contribute DMG and status applications.

Exact companion pool ownership and contribution rules remain undecided.

See [[Companions]], [[Party]] and [[Status]].

---

## 47. Damage Attribution

Arc Combustion preserves individual contributor attribution.

### Primary Fire Explosion

Attribution follows ordinary Fire Heat contribution rules.

- The triggering player does not automatically receive all Fire DMG credit.
    
- Existing propagated Heat preserves its original attribution.
    
- Burn and resulting Heat propagation follow ordinary Fire ownership rules.
    

### Originating Charge

Secondary Lightning explosion DMG preserves the proportional contributions of the completed Charge used to create the arcs.

### Guaranteed Lightning Applications

Newly generated Lightning stacks inherit the proportional contributor attribution of the applicable originating Charge.

Simultaneous arrivals combine attribution proportionally alongside their combined Charge.

### Harvested Charge

Locally harvested Charge preserves its own original contributor attribution.

Its damage credit is not reassigned to the arc's original contributors merely because their arc harvested it.

### Recursive Combinations

Newly triggered Arc Combustions use the contribution information of their own eligible Heat and Charge.

Chain membership does not erase individual ownership.

---

## 48. Attribution Example

An arc possesses 600 originating Charge.

|Contributor|Originating Charge|Relative Contribution|
|---|---|---|
|Player A|400|66.67%|
|Player B|200|33.33%|

The arc harvests an additional 300 Charge.

|Contributor|Harvested Charge|
|---|---|
|Player B|100|
|Player C|200|

The resulting explosion uses:

|Contributor|Total Applicable Charge|
|---|---|
|Player A|400|
|Player B|300|
|Player C|200|
|Total|900|

Using an illustrative Charge-to-DMG coefficient of 1:

- Player A receives credit for 400 pre-mitigation DMG.
    
- Player B receives credit for 300 pre-mitigation DMG.
    
- Player C receives credit for 200 pre-mitigation DMG.
    

The enemy receives a total of 900 pre-mitigation DMG.

Actual attribution must account for applicable final mitigation and Damage Category interactions.

All values are illustrative.

---

## 49. Contributor Death

Electrical arcs persist after their originating contributors die.

### General Rules

- Scheduled waves remain active.
    
- Arcs continue traveling.
    
- Originating Charge remains unchanged.
    
- Stored critical properties remain unchanged.
    
- Damage Category proportions remain preserved.
    
- Individual contributor attribution remains preserved.
    
- Eligible recursive combinations can still activate.
    

Ordinary player-side Lightning Discharge buffs follow their own death-related removal rules.

The death of a contributor does not automatically cancel an already activated Arc Combustion chain.

---

## 50. Status Damage Restrictions

Arc Combustion damage does not perform ordinary Status Chance rolls.

### Primary Fire Explosion

Follows ordinary Combustion's established explicit Burn and Heat propagation mechanics.

It does not automatically apply additional statuses through ordinary damage rolls.

### Secondary Lightning Explosions

- Do not perform ordinary Lightning Status Chance rolls.
    
- Do not perform ordinary Fire Status Chance rolls.
    
- Do not perform ordinary applications of unrelated statuses.
    
- Do not automatically generate ordinary on-hit effects.
    

### Explicit Guaranteed Application

Direct arc arrival is the source of the guaranteed Lightning application.

The explosion DMG itself is not responsible for the application.

### On-Hit Effects

General status damage restrictions remain applicable.

Arc Combustion does not inherently trigger:

- Life Steal.
    
- Stability recovery.
    
- Effects requiring ordinary direct attack hits.
    

Explicitly established exceptions remain possible.

---

## 51. General Resolution Order

### Initial Activation

1. Identify the eligible Fire and Lightning sets.
    
2. Determine the responsible pool.
    
3. Determine whether the activation belongs to an existing Arc Combustion chain.
    
4. Establish its activation identifier and chain identifier.
    
5. Calculate accumulated Fire Heat.
    
6. Calculate eligible completed Lightning Charge.
    
7. Preserve applicable critical properties and contributor attribution.
    
8. Consume the required completed sets.
    
9. Resolve the primary Fire explosion.
    
10. Apply ordinary Burn and Heat propagation.
    
11. Coordinate first-wave target selection.
    
12. Establish the scheduled wave arrivals.
    

### Wave Resolution

At the scheduled wave time:

1. Determine arriving arcs and their valid destinations.
    
2. Identify direct target arrivals.
    
3. Group simultaneous direct arrivals belonging to the same chain and target.
    
4. Calculate combined originating Charge for each eligible arrival group.
    
5. Apply one guaranteed Lightning stack per group.
    
6. Resolve ordinary status progression and combination eligibility.
    
7. Resolve newly triggered combinations or ordinary milestone effects.
    
8. Determine remaining eligible locally harvested Charge.
    
9. Consume that Charge.
    
10. Distribute harvested Charge proportionally among arriving arcs.
    
11. Determine the applicable direct animation interruption.
    
12. Resolve resistance and Stability Barrier protection.
    
13. Resolve the individual Lightning explosions.
    
14. Resolve eligible resulting effects and enemy deaths.
    
15. Coordinate the next wave's target selection where journeys remain.
    

### Recursive Activation

Any Arc Combustion triggered during wave resolution:

- Resolves its own primary Fire explosion immediately.
    
- Inherits the originating chain identifier.
    
- Establishes its own future wave schedule.
    
- Does not cancel the originating arcs.
    

### Implementation Note

The detailed internal ordering of simultaneous AoE damage, ordinary stuns, barrier damage and recursive primary explosions must preserve the established interactions without duplicating consumed Charge.

---

## 52. Reapplication & Cooldown

Arc Combustion possesses no dedicated internal cooldown.

### General Rules

- Fire and Lightning stacks can be rebuilt immediately.
    
- Previously targeted enemies do not receive combination-specific temporary immunity.
    
- Multiple Arc Combustions can remain active simultaneously.
    
- Recursive combinations can activate whenever their requirements are satisfied.
    
- Independent combinations maintain separate chain identifiers.
    
- Existing arcs are not canceled by activating another Arc Combustion.
    

### Natural Limitations

Every activation requires the appropriate eligible status sets.

Charge consumption and ordinary Fire consumption reduce the remaining resources available for future combinations.

---

## 53. Comparison with Ordinary Combustion

|Property|Ordinary Combustion|Arc Combustion|
|---|---|---|
|Required statuses|Fire|Fire + Lightning|
|Primary Fire explosion|Yes|Yes|
|Primary explosion radius|Standard|Standard|
|Primary DMG falloff|Yes|Yes|
|Burn application|Yes|Yes|
|Heat propagation|Yes|Yes|
|Secondary Lightning explosions|None|6|
|Guaranteed Lightning applications|No|Yes|
|Charge harvesting|No|Yes|
|Animation interruptions|No|Yes|
|Recursive combination potential|Ordinary Fire rules|Explicit Arc Combustion chain reactions|
|Primary completed Lightning consumption|No|Yes|
|New direct Discharge buff|No|No|
|Dedicated combination cooldown|Not applicable|None|

---

## 54. Comparison with Cool Combustion

|Property|[[Cool Combustion]]|Arc Combustion|
|---|---|---|
|Secondary element|Ice|Lightning|
|Main identity|Immediate thermal conversion|Cascading electrical explosions|
|Primary explosion radius|1.5× standard|Standard|
|Primary DMG falloff|None|Ordinary falloff|
|Existing Burn consumption|Yes|Ordinary Fire behavior|
|New Burn application|No|Yes|
|Heat propagation|No|Yes|
|Surrounding status consumption|Area-wide Fire consumption|Selective Lightning harvesting|
|Secondary explosions|None|6 per activation|
|Recursive combinations|No direct recursive explosion mechanism|Yes|
|Crowd-control interaction|Sacrifices completed Ice|Generates animation interruptions|
|Offensive timing|Instantaneous|Initial explosion plus timed waves|

### Distinct Identities

Cool Combustion converts prepared area-wide Fire potential into immediate damage.

Arc Combustion distributes electrical energy through targeted paths, harvesting Charge and potentially producing further combinations.

Neither combination should simply replace the other as a universally superior Fire payoff.

---

## 55. Strategic Applications

### Prepared Lightning Targets

Players can distribute ordinary Lightning stacks throughout enemy groups.

Enemies with five ordinary stacks are particularly valuable targets because guaranteed arc applications can immediately complete their next Lightning set.

### Recursive Chain Preparation

Players can attempt to prepare multiple enemies with compatible Fire and Lightning states.

A successful Arc Combustion can then initiate further combinations through its guaranteed Lightning applications.

### Scattered Enemy Groups

Each arc can travel independently across two journeys.

This allows Arc Combustion to reach enemies beyond the initial Fire explosion's radius.

### Isolated Bosses

Against an isolated enemy:

- All six Lightning explosions can concentrate their DMG on one target.
    
- The two waves preserve their scheduled timing.
    
- The target receives two shared guaranteed application events.
    
- The target can experience two applicable interruption events per activation.
    

### Barrier Pressure

High Charge can contribute toward:

- Lightning explosion DMG.
    
- Animation interruption protection costs.
    
- Ordinary Lightning milestone interactions.
    

This may make Arc Combustion effective against Stability Barriers.

### Multiplayer Specialization

Parties can distribute responsibilities between:

- Fire Heat accumulation.
    
- Lightning Charge accumulation.
    
- Preparing nearly completed Lightning sets.
    
- Enemy positioning.
    
- Maintaining offensive pressure between waves.
    

---

## 56. Balance Considerations

Arc Combustion intentionally contains several potentially powerful interactions.

### Originating Charge Reuse

Each of the six secondary explosions references the full originating Charge.

Charge is not divided among the six explosions.

This allows substantial single-target and overlapping AoE DMG.

### Guaranteed Charge Generation

Each direct arrival event applies one guaranteed Lightning stack derived from the arriving Charge.

Simultaneous arrivals can generate particularly strong individual Lightning stacks.

### Charge Harvesting

Locally prepared enemies can significantly increase the resulting explosion DMG.

Harvested Charge is not carried into the next journey, limiting cumulative path scaling.

### Recursive Activation

Arc Combustion can produce additional full Arc Combustion activations.

No maximum recursion depth is currently established.

Potential risks include:

- Rapid growth in active arc count.
    
- Excessive overlapping explosions.
    
- Recursive Charge generation.
    
- Recursive critical scaling.
    
- Extremely high individual guaranteed stack Charge.
    
- Excessive Stability Barrier consumption.
    
- Extended animation interruption chains.
    
- Performance issues against densely grouped enemies.
    
- Rapid enemy deaths obscuring combat readability.
    

### Initial Testing Philosophy

These interactions should be implemented and observed before introducing additional restrictions.

Potential future limitations must be based on actual gameplay results rather than assumed necessity.

---

## 57. Lore

Arc Combustion represents the release of accumulated Heat through a completed electrical Charge state.

The initial Fire explosion releases stored thermal energy.

The electrical Charge then continues moving through surrounding entities, searching for compatible concentrations of Lightning.

Prepared enemies can amplify the resulting explosions or produce further elemental interactions.

The electrical chain can continue through several generations when the surrounding conditions support it.

Unlike ordinary Fire propagation, Arc Combustion moves through selective electrical paths rather than simply distributing Heat throughout a single surrounding area.

Exact lore terminology remains open.

---

## 58. Visual Representation

Arc Combustion should clearly communicate its timed and recursive structure.

### Primary Explosion

- Visually follows ordinary Combustion.
    
- Introduces a recognizable electrical transition.
    
- Establishes the original chain reaction center.
    

### Electrical Arcs

- Three distinct electrical paths originate from each activation.
    
- Arcs visibly travel toward their selected enemies.
    
- Travel presentation adapts to distance.
    
- All arcs arrive at their scheduled wave time.
    
- Each arc's second journey originates from its first destination.
    

### Simultaneous Targeting

Several arcs targeting the same enemy should remain visually distinguishable while communicating their shared Charge interaction.

### Recursive Activation

A newly triggered Arc Combustion should visibly establish:

- Its own primary Fire explosion.
    
- Its newly generated arcs.
    
- Its continuing relationship to the originating electrical chain.
    

### Stationary Arc Resolution

Arcs remaining on an isolated enemy should still communicate:

- Electrical buildup.
    
- First-wave detonation.
    
- Renewed electrical buildup.
    
- Second-wave detonation.
    

### Visual Clarity

The effect must remain readable even when multiple recursive Arc Combustions overlap.

Exact visuals, colors, sound effects and performance limitations remain undecided.

---

## 59. Combat DMG Display

Arc Combustion can generate multiple overlapping damage instances.

### General Rules

- The primary Fire explosion remains its own damage event.
    
- Every secondary Lightning explosion remains an independent damage event.
    
- Simultaneous status interactions do not merge all explosions into one damage instance.
    
- Physical and Magical damage components retain their applicable calculations.
    
- General combat DMG display settings remain applicable.
    

### Potential Display Considerations

- Distinguish Fire and Lightning damage.
    
- Communicate multiple overlapping explosions.
    
- Avoid excessive damage-number clutter.
    
- Communicate particularly strong locally harvested Charge.
    
- Preserve readability during recursive chain reactions.
    

Exact display behavior remains undecided.

---

## 60. Provisional Values

|Property|Current Value|
|---|---|
|Required Fire stacks|6|
|Required Lightning stacks|Eligible completed set|
|Primary Fire explosions per activation|1|
|Electrical arcs per activation|3|
|Journeys per arc|2|
|Secondary Lightning explosions|6|
|Total explosions per activation|7|
|Arc targeting range per journey|5 meters|
|First-wave arrival|1 second after activation|
|Second-wave arrival|2 seconds after activation|
|Secondary explosion radius|0.5× ordinary Combustion radius|
|Primary explosion falloff|Ordinary Combustion|
|Secondary explosion falloff|None|
|Originating Charge per arc|Full completed Charge|
|Guaranteed stack Charge|Combined originating Charge ÷ 6|
|Charge-to-DMG coefficient|Undetermined|
|Locally harvested Charge coefficient|Same as originating Charge|
|Harvested Charge carryover|None|
|Guaranteed applications per simultaneous chain arrival group|1|
|Interruption events per simultaneous chain arrival group|1|
|Harvesting events per simultaneous chain arrival group|1|
|First direct interruption|Fifth-stack Static Charge duration|
|Repeated direct interruption|Fourth-stack Static Charge duration|
|Secondary Burn application|None|
|Secondary Heat propagation|None|
|Recursive Arc Combustion activation|Enabled|
|Other eligible combination activation|Enabled|
|Maximum recursion depth|Unrestricted for testing|
|Combination-specific cooldown|None|
|Combination-specific temporary immunity|None|
|Minimum distinct contributing players|1|

---

## 61. Remaining Design & Implementation Questions

### Numerical Balancing

- Final Charge-to-DMG coefficient.
    
- Final secondary explosion radius.
    
- Final arc targeting range.
    
- Final wave interval.
    
- Final fourth-stack and fifth-stack interruption durations.
    
- Balance against isolated bosses.
    
- Balance against densely grouped enemies.
    
- Balance against enemies with large Stability Barriers.
    
- Potential need for recursive scaling limitations.
    

### Wave & Targeting Implementation

- Exact equal-priority target tie-breaking.
    
- Visual travel behavior for moving enemies.
    
- Visual behavior when arcs remain on one enemy.
    
- Exact simultaneous event ordering between independent chains.
    
- Arc behavior when targets become otherwise invalid without dying.
    
- Interaction with terrain and obstructions where not already established.
    

### Charge Harvesting

- Exact FIFO implementation when completed and accumulating Lightning sets coexist.
    
- Interaction with the established strongest completed Charge rule.
    
- Handling of newly completed ordinary Discharge Charge during harvesting.
    
- Rounding during proportional harvested Charge allocation.
    
- Handling of zero or otherwise invalid originating Charge values.
    
- Preservation of contributor and Damage Category distributions through repeated propagation.
    

### Critical Strike Scaling

- Recursive Discharge critical calculations.
    
- Preventing duplicate application of stored critical multipliers.
    
- Long-term scaling of unusually strong guaranteed Lightning stacks.
    
- Numerical testing of recursive Charge amplification.
    

### Interruptions

- Combined interruption strength when overlapping descendant activations possess different targeting histories.
    
- Ordinary stun overlap with direct arc animation interruptions.
    
- Exact order of simultaneous damage and interruption-related barrier costs.
    
- Potential need for interruption diminishing returns after playtesting.
    

### Recursive Combination Interactions

- Chain inheritance through intervening non-Arc Combustion combinations.
    
- Competing combination priority.
    
- Potential interaction with future combinations that generate guaranteed Fire applications.
    
- Maximum practical number of active arcs.
    
- Performance during large recursive chains.
    

### Multiplayer

- Companion Charge ownership.
    
- Contributor death and long-term participation credit.
    
- Party membership changes during an active chain.
    
- Independent chain resolution ordering.
    
- Final post-mitigation damage attribution implementation.
    

### Visual Representation

- Primary explosion appearance.
    
- Electrical arc animation.
    
- Fixed wave timing presentation.
    
- Combined arrival effects.
    
- Charge harvesting effects.
    
- Recursive chain readability.
    
- Damage number presentation.
    
- Audio feedback.
    
- Performance limitations.
    

---

## 62. Superseded Mechanics

### Fixed Travel Speed

Previous proposal:

- Electrical arcs travel at a fixed speed.
    
- Arrival timing depends on traveled distance.
    

Current:

- Electrical arcs use fixed wave duration.
    
- All three first-wave arrivals occur together.
    
- All three second-wave arrivals occur together.
    
- Travel presentation adapts to distance.
    

### Guaranteed Application Per Individual Arc

Previous proposal:

- Every individual arc applies its own guaranteed Lightning stack.
    

Current:

- Simultaneous arcs belonging to the same chain and targeting the same enemy apply one combined guaranteed stack.
    
- Combined originating Charge determines its strength.
    
- Every explosion still deals independent DMG.
    

### Independent Simultaneous Harvesting

Previous proposal:

- Simultaneous arcs resolve separate stack applications and harvesting calculations.
    

Current:

- Eligible simultaneous chain arrivals share one status progression and harvesting calculation.
    
- Harvested Charge is distributed proportionally among their explosions.
    

### Party-Wide Simultaneous Grouping

Previous proposal:

- All simultaneous arcs belonging to the same party combine their Charge.
    

Current:

- Shared chain reaction membership is also required.
    
- Independently triggered Arc Combustions resolve separately.
    
- No artificial synchronization occurs.
    

### Completed Set Targeting Priority

Previous proposal:

- Completed Lightning sets count as six stacks and receive the highest targeting priority.
    

Current:

- Ordinary incomplete Lightning stack progression determines targeting priority.
    
- Five ordinary stacks receive the highest priority.
    
- Completed sets do not independently increase targeting priority.
    

### Carried Harvested Charge

Previous proposal:

- Harvested Charge could strengthen subsequent journeys.
    

Current:

- Harvested Charge only strengthens the local explosion.
    
- Every arc retains its original originating Charge.
    

### Surrounding Lightning Preservation

Previous proposal:

- Secondary explosions leave all surrounding Lightning stacks untouched.
    

Current:

- Direct arc arrivals apply guaranteed Lightning.
    
- Eligible Charge is harvested after status progression.
    
- Enemies merely caught in AoE retain their Lightning properties.
    

### Restricted Recursive Activation

No initial recursion restriction has been established.

Recursive Arc Combustion activation remains intentionally unrestricted for testing.

---

## 63. Design Status

Arc Combustion's core mechanics are established.

### Established Mechanics

- Fire and Lightning activation requirements.
    
- Ordinary primary Fire Combustion.
    
- Preservation of Burn and Heat propagation.
    
- Three independent electrical arcs.
    
- Two journeys per arc.
    
- Six secondary Lightning explosions.
    
- Fixed wave timing.
    
- Five-meter individual targeting range.
    
- Coordinated target selection.
    
- Prioritization of incomplete Lightning stacks.
    
- Returning arcs.
    
- Isolated enemy behavior.
    
- Target death behavior.
    
- Secondary explosion radius and removal of falloff.
    
- Full originating Charge per arc.
    
- Guaranteed Lightning applications.
    
- Local Charge harvesting.
    
- No harvested Charge carryover.
    
- Combined simultaneous arrival calculations.
    
- Proportional harvested Charge distribution.
    
- Recursive Arc Combustion activation.
    
- Shared chain identifiers.
    
- Independent unrelated chain resolution.
    
- Other eligible status combination interactions.
    
- Animation interruptions.
    
- Ordinary Lightning milestone activation.
    
- Stability Barrier protection.
    
- Resistance and immunity interactions.
    
- Preservation of existing Discharge buffs.
    
- Individual Damage Category preservation.
    
- Critical property preservation.
    
- Individual contributor attribution.
    
- Solo and multiplayer availability.
    
- Contributor death persistence.
    
- No dedicated cooldown.
    
- No initial recursion limit.
    

Further development primarily concerns numerical balancing, implementation details, universal combination interactions and visual representation.

---

## Related Notes

- [[Status]]

- [[Fire]]
- [[Lightning]]
- [[Ice]]
- [[Poison]]

- [[Cool Combustion]]
- [[Toxic Combustion]]
- [[Shattering Voltage]]
- [[Neurotoxin]]
- [[Conductive Wounds]]
- [[Disruption]]
- [[Short Circuit]]
- [[Damage Calculation]]
- [[Critical Hits]]
- [[Stability Barrier System]]
- [[Participation and Loot]]
- [[Party]]
- [[Multiplayer]]
- [[Companions]]