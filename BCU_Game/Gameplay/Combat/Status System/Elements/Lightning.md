# Lightning, Static Charge & Lightning Discharge

**Identity:** Electrical Charge accumulation, combat interruptions and group empowerment  
**Status Family:** Elemental  
**Damage Categories:** Physical and Magical  
**Maximum Building Stacks:** 6  
**Base Stack Duration:** 5 seconds (provisional)  
**Third-Stack Payoff:** Stun  
**Fourth- and Fifth-Stack Payoff:** Static Charge  
**Sixth-Stack Payoff:** Lightning Discharge

---

## Lightning

### Core Mechanics

- Lightning represents the accumulation of electrical Charge within an affected entity.
    
- Every successful Lightning application stores an individually calculated Charge value.
    
- Lightning supports physical and magical applications.
    
- Both Damage Categories contribute equally toward accumulated Charge.
    
- Lightning does not need to preserve the physical and magical distribution of stored Charge for its ordinary effects.
    
- Players belonging to the same group contribute toward one shared Lightning pool per enemy.
    
- Lightning stacks do not provide additional DMG per hit.
    
- Accumulated Charge determines the strength of Lightning Discharge's speed buff.
    
- Crowd-control effects have predefined strengths and durations independent of accumulated Charge.
    
- Stability Barrier protection costs scale with accumulated Charge.
    

### Stack Progression

|Stacks|Effect|
|---|---|
|1–2|Accumulate electrical Charge.|
|3|Accumulate Charge and trigger a 0.5-second stun.|
|4|Accumulate Charge and trigger a brief Static Charge interruption.|
|5|Accumulate Charge and trigger a longer Static Charge interruption.|
|6|Accumulate Charge and trigger Lightning Discharge.|

- Every stack contributes its Charge before resolving its corresponding milestone.
    
- Eligible status combinations take priority over ordinary sixth-stack resolution.
    
- Individual milestone effects do not consume ordinary Lightning stacks before the sixth-stack payoff.
    

---

## Electrical Charge

### Individual Stack Strength

- Each Lightning stack stores an individually calculated Charge value.
    
- Charge references the corresponding non-critical, pre-mitigation Lightning DMG of the triggering attack.
    
- Each Charge application independently rolls its critical strike.
    
- Charge is calculated before target-side mitigation and vulnerability.
    
- The exact Charge scaling formula remains undecided.
    

### Calculation Order

1. Reference the triggering attack's corresponding non-critical Lightning DMG.
    
2. Resolve the Charge application's independent critical strike.
    
3. Calculate the resulting Charge using applicable offensive properties and scaling.
    
4. Store the resulting Charge value.
    

The following do not influence Charge storage:

- Physical DEF.
    
- Magical DEF.
    
- Lightning DMG Resistance.
    
- DMG vulnerability.
    

### Stored Properties

Each Lightning stack remembers:

- Original contributor.
    
- Individual calculated Charge value.
    
- Application order.
    

Physical and magical Charge values contribute equally toward Lightning's ordinary effects.

### Critical Charge

- Every successful Charge application independently determines whether it critically strikes.
    
- The calculated critical DMG is stored directly within the Charge value.
    
- Critical multipliers are not stored as additional modifiers that need to be reapplied.
    
- Previously calculated critical DMG remains part of the stored Charge.
    
- Subsequent changes to the originating player's attributes do not modify existing Charge values.
    
- Changes to the affected entity's defenses, resistances or vulnerabilities do not modify stored Charge.
    

---

## Third-Stack Stun

### Core Mechanics

- Reaching three Lightning stacks immediately triggers a stun.
    
- The provisional base stun duration is 0.5 seconds.
    
- The third stack contributes its Charge before the stun resolves.
    
- The stun does not consume any accumulated Lightning stacks or Charge.
    
- Players can continue building toward Lightning Discharge afterward.
    

### Stun Behavior

- Prevents voluntary actions during its duration.
    
- Immediately cancels ongoing enemy attacks.
    
- Canceled attacks do not automatically resume when the stun ends.
    
- Lightning DMG Resistance reduces the stun duration.
    
- Stun immunity prevents the effect entirely.
    
- Stability Barriers can block the stun at the cost of Barrier capacity.
    

---

## Static Charge

### Core Mechanics

- Reaching the fourth and fifth Lightning stacks immediately triggers a brief animation interruption.
    
- Static Charge does not create an ongoing interruption effect.
    
- Each milestone triggers its own individual interruption.
    
- The fifth-stack interruption lasts longer than the fourth-stack interruption.
    
- Exact interruption durations remain undecided.
    

### Animation Interruption

Unlike ordinary stuns:

- Static Charge temporarily pauses the affected animation.
    
- The underlying attack or action is not canceled.
    
- The animation resumes from the point at which it was interrupted.
    
- Remaining attack damage windows are preserved.
    
- Static Charge does not restart the interrupted attack.
    

### Resistance & Immunity

- Lightning DMG Resistance reduces Static Charge interruption duration.
    
- Active interruptions dynamically respond to changes in Lightning DMG Resistance.
    
- Stun immunity does not inherently prevent Static Charge interruptions.
    
- Static Charge can therefore affect enemies that cannot ordinarily be stunned.
    
- Stability Barriers can block Static Charge interruptions at the cost of Barrier capacity.
    

### Design Intent

- Static Charge provides a distinct form of temporary enemy restriction.
    
- It delays enemy actions without removing their underlying attacks.
    
- It provides meaningful fourth- and fifth-stack effects without introducing additional DMG per hit.
    

---

## Lightning Discharge

### Core Mechanics

- Lightning Discharge is Lightning's sixth-stack payoff.
    
- Reaching six Lightning stacks triggers Discharge unless an eligible status combination takes priority.
    
- The sixth stack contributes its Charge before Discharge resolves.
    
- Discharge calculates its strength from all six accumulated Charge values.
    
- Lightning Discharge applies:
    
    - A 1-second stun to the affected enemy.
        
    - A group speed buff.
        
    - A highlighted completed Lightning set.
        

### Critical Discharge

- Lightning Discharge performs an independent critical strike roll.
    
- A critical Discharge multiplies the accumulated Charge used to calculate the resulting buff.
    
- Previously stored critical Charge remains part of the calculation.
    
- Previous critical multipliers are not reapplied separately.
    
- The resulting Discharge Charge is stored as a calculated value.
    

Lightning can therefore benefit from two layers of critical strikes:

1. Individual Charge application critical strikes.
    
2. Lightning Discharge's independent critical strike.
    

### Charge Consumption

- Discharge consumes all six ordinary Lightning stacks.
    
- Accumulated building Charge is consumed during resolution.
    
- The calculated Discharge Charge is retained within the completed Lightning set.
    
- A new ordinary Lightning buildup can begin immediately afterward.
    
- The completed set and new building set coexist.
    

### Discharge Stun

- Provisional base duration: 1 second.
    
- Immediately cancels ongoing enemy attacks.
    
- Lightning DMG Resistance reduces its duration.
    
- Stun immunity prevents the stun.
    
- Stability Barriers can block the stun.
    
- Preventing the stun does not prevent the resulting group speed buff.
    

---

## Completed Lightning Set

### Core Mechanics

- One highlighted completed Lightning set can exist per group per enemy.
    
- The completed set remembers its calculated Discharge Charge.
    
- The remembered Charge includes the applicable Discharge critical calculation.
    
- The completed set remains available for eligible status combinations.
    
- A separate ordinary Lightning set can accumulate while the completed set remains active.
    

### Strongest Completed Charge Rule

When another Lightning Discharge activates:

- Calculate the new Discharge Charge.
    
- Compare it with the previously remembered completed Charge.
    
- A higher calculated value replaces the previous remembered value.
    
- An equal or lower calculated value preserves the existing higher value.
    
- The completed Lightning set's duration is refreshed.
    
- The strongest remembered Charge determines the strength of the newly granted Discharge buff.
    

### Example

|Discharge|Newly Calculated Charge|Retained Completed Charge|
|---|---|---|
|First|4,000|4,000|
|Second|2,000|4,000|
|Third|6,000|6,000|
|Fourth|3,000|6,000|

- Weaker Discharges can maintain a previously established stronger Charge value.
    
- Newly affected players can receive buffs calculated from the retained stronger Charge.
    
- A weaker Discharge does not reduce the completed set's strength.
    
- This behavior is intentionally experimental.
    

### Completed Charge Removal

The remembered completed Charge disappears when:

- The shared Lightning expiration timer ends.
    
- The completed set is consumed by a status combination.
    
- The completed set is removed through cleansing.
    

Removing the completed set does not prematurely remove previously granted player buffs.

---

## Lightning Discharge Buff

### Core Mechanics

Lightning Discharge increases:

- Attack Speed.
    
- Animation Speed.
    
- Movement Speed.
    

All three speed bonuses provisionally use the same calculated strength.

### Buff Scaling

The speed bonus scales with the retained completed Discharge Charge.

**Provisional coefficient:**

- 0.005% increased speed per point of calculated Charge.
    

**Formula:**

Speed Bonus (%) = Retained Discharge Charge × 0.005

**Illustrative values:**

|Retained Charge|Speed Bonus|
|---|---|
|100|0.5%|
|500|2.5%|
|1,000|5%|
|2,000|10%|
|5,000|25%|
|10,000|50%|
|20,000|100%|

### Speed Calculation

- Speed bonuses apply multiplicatively.
    
- The Discharge bonus multiplies the player's applicable speed values.
    
- Attack Speed, Animation Speed and Movement Speed follow this principle.
    
- Exact interaction between Attack Speed and Animation Speed must be reconciled with the general animation system to avoid unintended duplicate acceleration.
    

**Illustrative formula:**

Resulting Speed = Existing Speed × (1 + Retained Discharge Charge × 0.00005)

### Experimental Scaling

- No guaranteed minimum speed bonus exists.
    
- Zero stored Charge can result in zero speed bonus.
    
- No dedicated maximum speed bonus has been established.
    
- The initial implementation intentionally allows experimentation with very weak and extremely powerful Discharge buffs.
    
- Scaling limitations will be evaluated during playtesting.
    

### Ability Interactions

- The buff accelerates applicable normal attack animations.
    
- The buff accelerates applicable ability animations.
    
- The buff increases Movement Speed.
    
- Ability cooldown durations remain unaffected.
    
- Animation acceleration remains subject to combat-flow testing.
    

---

## Buff Distribution

### Discharge Radius

- Lightning Discharge distributes its buff around the affected enemy.
    
- The provisional buff radius is 5 meters.
    
- Eligible group members within this radius receive the buff.
    
- Players do not need to have personally contributed Lightning stacks to receive the buff.
    

### Triggering Player

- The player who triggers Lightning Discharge receives the buff regardless of distance from the affected enemy.
    
- Ranged weapons are therefore not disadvantaged when triggering Discharge from outside the ordinary buff radius.
    

### Buff Persistence

- Players retain received buffs after leaving the original Discharge radius.
    
- The buff does not require continuous proximity to the affected enemy.
    
- Players retain received buffs after leaving the responsible group.
    
- Player death removes the affected player's received Discharge buff.
    

### Enemy Resistance

- Lightning DMG Resistance does not reduce the strength of the Discharge buff.
    
- Lightning DMG Resistance does not reduce its duration.
    
- Stun immunity does not prevent eligible players from receiving the buff.
    
- Stability Barrier protection does not prevent buff distribution.
    

---

## Individual Buff Ownership

### Strongest Buff Rule

Each player individually maintains their strongest received Discharge buff.

When another Discharge buff is received:

- A stronger buff replaces the existing buff.
    
- An equally strong buff refreshes the existing buff.
    
- A weaker buff refreshes the existing buff without reducing its strength.
    
- Multiple ordinary Discharge buffs do not stack in strength.
    

### Independent Buff Tracking

Different players can possess Discharge buffs of different strengths and durations.

Example:

|Player|Existing Buff|Incoming Buff|Result|
|---|---|---|---|
|A|20%|10%|20%, refreshed|
|B|None|10%|10%|
|C|5%|10%|10%, replaces previous buff|

The incoming buff strength is calculated from the responsible enemy's retained completed Discharge Charge.

### Buff Duration

- Provisional base duration: 5 seconds.
    
- Every successfully received Discharge buff refreshes the corresponding player's buff duration.
    
- Ordinary Lightning applications do not refresh player-side buffs.
    
- Only receiving another Discharge buff refreshes the duration.
    
- The player-side buff timer is independent of the enemy-side Lightning timer.
    
- Consuming or cleansing the enemy's completed set does not remove existing player-side buffs.
    

---

## Duration & Expiration

### Shared Enemy-Side Timer

Each group maintains one shared Lightning expiration timer per enemy.

The following share this timer:

- Ordinary building stacks.
    
- Accumulated building Charge.
    
- Completed Lightning set.
    
- Remembered completed Discharge Charge.
    

### Duration Refreshing

- Every successful Lightning application refreshes the shared enemy-side duration.
    
- Building new stacks also refreshes the completed Lightning set.
    
- Triggering another Lightning Discharge refreshes the shared duration.
    
- Ordinary applications can maintain the completed set without triggering another Discharge.
    
- Maintaining the completed set does not automatically maintain player-side buffs.
    

### Simultaneous Expiration

Unlike the physical statuses, Lightning does not follow gradual stack decay.

When the shared enemy-side timer expires:

- All ordinary building stacks disappear.
    
- All building Charge disappears.
    
- The completed Lightning set disappears.
    
- Remembered completed Discharge Charge disappears.
    

Previously granted player-side buffs continue until their individual expiration.

### Independent Crowd-Control Timers

- Third-stack stuns use their own duration.
    
- Static Charge interruptions use their own duration.
    
- Discharge stuns use their own duration.
    
- Ordinary Lightning applications do not inherently refresh active crowd-control durations.
    

---

## Resistance & Immunity

### Status Chance Resistance

- Lightning Status Chance Resistance influences the probability of successfully applying Lightning stacks.
    
- It does not reduce the Charge stored by successfully applied stacks.
    
- Guaranteed direct applications follow the general [[Status]] rules.
    

### Lightning DMG Resistance

Lightning DMG Resistance affects:

- Ordinary incoming Lightning DMG.
    
- Third-stack stun duration.
    
- Fourth-stack Static Charge interruption duration.
    
- Fifth-stack Static Charge interruption duration.
    
- Sixth-stack Discharge stun duration.
    
- Stability Barrier protection costs for these effects.
    

Lightning DMG Resistance does not affect:

- Stored electrical Charge.
    
- Retained completed Discharge Charge.
    
- Discharge buff strength.
    
- Discharge buff duration.
    
- Maximum stack count.
    

### Proportional Duration Reduction

- Lightning DMG Resistance proportionally reduces applicable stun and interruption durations.
    
- The exact numerical scaling remains subject to testing.
    

Illustrative values:

|Lightning DMG Resistance|Third-Stack Stun|Discharge Stun|
|---|---|---|
|0%|0.5s|1s|
|25%|0.375s|0.75s|
|50%|0.25s|0.5s|
|75%|0.125s|0.25s|
|100%|0s|0s|

### Dynamic Resistance

- Active stuns and Static Charge interruptions dynamically respond to changes in Lightning DMG Resistance.
    
- Gaining resistance can shorten an active interruption or stun.
    
- Losing resistance can increase its remaining duration.
    
- Exact dynamic timer implementation will follow the principles established for [[Ice]].
    

### Stun Immunity

- Stun immunity prevents ordinary Lightning stuns.
    
- Stun immunity does not inherently prevent Static Charge interruptions.
    
- Stun-immune enemies still enable Lightning Discharge buffs.
    
- Intrinsic immunity prevents unnecessary Stability Barrier consumption.
    

### Complete Lightning DMG Resistance

Enemies with 100% Lightning DMG Resistance:

- Can accumulate ordinary Lightning stacks.
    
- Can accumulate Charge normally.
    
- Can trigger Lightning Discharge.
    
- Do not receive effective Lightning stuns.
    
- Do not receive effective Static Charge interruptions.
    
- Do not consume Stability Barrier capacity through ineffective Lightning crowd control.
    
- Still grant full calculated Discharge buffs.
    
- Retain the completed Lightning set normally.
    
- Remain eligible for compatible status combinations.
    

Unlike completely resistant [[Ice]] targets, Lightning does not immediately lose its completed set.

---

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
    

---

## Cleansing

### Ordinary Building Set

- Ordinary Lightning cleansing follows FIFO (First In, First Out).
    
- The oldest ordinary Lightning stack is removed first.
    
- Its corresponding stored Charge is removed.
    
- Remaining stacks retain their original individual Charge values.
    
- Cleansing does not trigger milestone effects.
    

### Completed Lightning Set

When the completed Lightning set is cleansed:

- The completed set is removed entirely.
    
- Its remembered Discharge Charge is removed.
    
- No previously consumed stacks are restored.
    
- No completed stacks are converted back into ordinary stacks.
    

### Simultaneous Building Set

If an ordinary building set exists alongside the completed set:

- The completed set is removed entirely.
    
- The oldest ordinary building stack is also removed through FIFO.
    
- Remaining building stacks retain their original properties.
    

### Cleansing Progression

|Completed Set|Building Stacks Before Cleansing|Remaining Ordinary Stacks|
|---|---|---|
|Active|0|0|
|Active|1|0|
|Active|2|1|
|Active|3|2|
|Active|4|3|
|Active|5|4|

### Additional Rules

- Cleansing does not trigger the third-stack stun.
    
- Cleansing does not trigger Static Charge.
    
- Cleansing does not trigger Lightning Discharge.
    
- Previously granted Discharge buffs remain unaffected.
    
- The remaining ordinary stacks can continue building toward another Discharge.
    

---

## Multiplayer & Group Ownership

### Shared Lightning Pool

- Players belonging to the same group contribute toward one shared Lightning pool per enemy.
    
- Physical and magical applications contribute equally.
    
- Every ordinary stack retains its original contributor.
    
- Group members collectively accumulate Charge.
    
- Each group maintains a maximum of one completed set per enemy.
    
- A separate ordinary building set can coexist with that completed set.
    

### Independent Groups

Different groups maintain independent:

- Ordinary Lightning stacks.
    
- Building Charge.
    
- Completed Lightning sets.
    
- Retained completed Discharge Charge.
    
- Shared enemy-side expiration timers.
    
- Combination eligibility.
    

Ordinary Lightning applications from one group do not refresh another group's Lightning pool.

### Overlapping Crowd Control

- Multiple groups can independently apply Lightning crowd control.
    
- Overlapping stuns do not add their durations together.
    
- Overlapping Static Charge interruptions do not add their durations together.
    
- The affected entity remains restricted according to its currently applicable active crowd-control effects.
    
- Exact resolution between simultaneous stuns and animation interruptions remains subject to implementation.
    

### Group Membership Changes

- Previously contributed Charge remains within its original group if its contributor leaves.
    
- Stored Charge is not removed or recalculated.
    
- Previously received Discharge buffs remain active on players who leave the group.
    

### Player Death

- Existing Lightning stacks and Charge remain active after their contributors die.
    
- Previously contributed Charge remains within the group pool.
    
- The deceased player's individual Discharge buff is removed.
    
- Other players' buffs remain unaffected.
    

The universal multiplayer status ownership system will be consolidated after reviewing all individual statuses.

---

## Additional Interactions

### Recursive Status Applications

- Lightning's ordinary status effects cannot generate additional ordinary status applications.
    
- Lightning Discharge does not perform additional Status Chance rolls.
    
- Explicitly defined specialized combination mechanics may introduce exceptions.
    

### Invulnerability

- Invulnerability does not inherently prevent Lightning status applications.
    
- Invulnerable enemies can still be stunned or interrupted if they lack corresponding resistance or immunity.
    
- Existing Lightning timers continue normally during invulnerability.
    
- Discharge buffs remain available to eligible players.
    

### Natural Status Synergies

#### Ice & Freeze

- Final Critical Chance vulnerability from [[Ice]] can improve Lightning Charge critical rolls.
    
- Final Critical Chance vulnerability can improve Lightning Discharge's critical strike chance.
    
- Previously stored Charge is not retroactively modified.
    

#### Fire & Burn

- Increased Attack Speed and Animation Speed may allow players to apply Fire stacks more frequently.
    
- This can accelerate Heat accumulation and Combustion progression.
    

#### Physical Statuses

- Discharge's speed buff can accelerate applicable physical status applications.
    
- Faster attacks can help maintain [[Slash]], [[Impact]] and [[Puncture]].
    
- These interactions do not require actual status combinations.
    

---

## Status Combinations

### Requirements

- Lightning can participate in compatible elemental and physical-elemental combinations.
    
- Eligible combinations take priority over ordinary sixth-stack resolution.
    
- A completed Lightning set remains eligible while its shared enemy-side timer is active.
    
- Ordinary Lightning applications can maintain this combination availability.
    
- Physical statuses require their enhanced states before combining with Lightning.
    
- General group-based combination rules follow [[Status]].
    

### Completed Charge Consumption

When a combination consumes the completed Lightning set:

- The completed set is removed.
    
- Its remembered Discharge Charge is removed.
    
- Existing player-side Discharge buffs remain active for their remaining durations.
    
- Ordinary building stacks remain subject to the individual combination's rules.
    

### Existing Elemental Combinations

|Partner|Combination|
|---|---|
|[[Fire]]|[[Arc Combustion]]|
|[[Ice]]|[[x Shattering Voltage]]|
|[[Poison]]|[[Synaptic Overload]]|

### Physical Status Combinations

|Partner|Required State|Combination|
|---|---|---|
|[[Slash]]|Laceration|[[Conductive Wounds]]|
|[[Impact]]|Fracture|Disruption (proposed)|
|[[Puncture]]|Breach|Short Circuit (proposed)|

### Individual Combination Rules

The following mechanics will be determined individually:

- Stored Charge scaling.
    
- Completed Charge consumption or preservation.
    
- Ordinary building stack consumption or preservation.
    
- Discharge buff interactions.
    
- Crowd-control effects.
    
- Stability Barrier protection costs.
    
- Critical strike behavior.
    
- Duration.
    
- Additional Lightning applications.
    
- Effects upon expiration.
    

Existing Lightning combinations must be reconciled with the redesigned Charge accumulation system.

---

## Lore

- Lightning represents accumulating electrical energy within an affected entity.
    
- Repeated applications build toward temporary electrical disruption.
    
- The third-stack milestone disrupts the entity sufficiently to interrupt its current actions.
    
- Static Charge causes brief interruptions without completely canceling underlying actions.
    
- Lightning Discharge releases accumulated electrical energy.
    
- The responsible players benefit from the released energy through increased combat and movement speed.
    
- The enemy's ability to resist electricity does not inherently reduce the energy available to the players.
    
- Continued Lightning applications maintain the completed electrical state.
    
- Unlike physical structural damage, accumulated Lightning disappears simultaneously when its duration expires.
    

---

## Placeholder Values

|Parameter|Value|
|---|---|
|Maximum ordinary Lightning stacks|6|
|First stun threshold|3 stacks|
|Static Charge thresholds|4 and 5 stacks|
|Lightning Discharge threshold|6 stacks|
|Base shared enemy-side duration|5 seconds|
|Third-stack stun duration|0.5 seconds|
|Fourth-stack interruption duration|Undetermined|
|Fifth-stack interruption duration|Longer than fourth-stack interruption|
|Discharge stun duration|1 second|
|Discharge buff duration|5 seconds|
|Discharge buff radius|5 meters|
|Speed scaling coefficient|0.005% per Charge|
|Minimum speed bonus|None|
|Maximum speed bonus|Undetermined|
|Maximum completed sets per group per enemy|1|
|Strongest completed Charge preservation|Yes|
|Strongest individual buff preservation|Yes|
|Ordinary stun base Barrier cost|50%|
|Static Charge base Barrier cost|0%|
|Stored Charge Barrier coefficient|0.000005|
|Maximum Barrier protection cost|100%|

All numerical values remain provisional.

---

## Remaining Open Questions

### Numerical Balancing

- Exact individual Charge scaling formula.
    
- Final Discharge speed scaling coefficient.
    
- Potential maximum speed bonus.
    
- Final Attack Speed and Animation Speed interaction.
    
- Final Movement Speed scaling.
    
- Fourth-stack Static Charge interruption duration.
    
- Fifth-stack Static Charge interruption duration.
    
- Final buff radius.
    
- Final ordinary stack and buff durations.
    

### Experimental Mechanics

- Maintaining exceptionally powerful completed Discharges through weaker applications.
    
- Maintaining exceptionally powerful individual buffs.
    
- High-DMG Lightning builds.
    
- Interactions with accelerated ability animations.
    
- Potential duplicate animation acceleration.
    
- Crowd-control chains involving multiple groups.
    
- Interactions with Ice's Final Critical Chance vulnerability.
    

### Stability Barriers

- Final crowd-control protection formulas.
    
- Incorporating crowd-control duration into protection costs.
    
- Resistance adjustment and rounding.
    
- Exact simultaneous Barrier break and crowd-control resolution.
    
- General Barrier capacity and generation mechanics.
    

### Status Combinations

- Rework existing Lightning combinations around Charge accumulation.
    
- Finalize Disruption.
    
- Finalize Short Circuit.
    
- Establish combination-specific Charge and buff interactions.
    
- Establish combination-specific Barrier protection costs.
    

### Implementation

- Multiple Lightning applications crossing several milestones within one damage instance.
    
- Exact simultaneous crowd-control resolution.
    
- Dynamic stun and interruption timer calculation.
    
- Shared duration behavior following cleansing.
    
- Group membership and buff eligibility tracking.
    
- Critical attribute source for group-based Discharge rolls.
    

### Visual Representation

- Ordinary Lightning stack indicators.
    
- Stored Charge representation.
    
- Highlighted completed Lightning set.
    
- Separate ordinary building set indicator.
    
- Static Charge interruption visuals.
    
- Lightning Discharge visual effects.
    
- Individual speed buff indicators.
    
- Buff strength representation.
    
- Stability Barrier protection feedback.
    
- Group-specific status indicators.
    

---

## Design Status

Lightning's fundamental mechanics are established.

The previous additional DMG per hit system has been removed and replaced with electrical Charge accumulation.

Lightning's defining mechanics are:

- Shared group-based Charge accumulation.
    
- Pre-mitigation Charge storage.
    
- Independent critical Charge applications.
    
- Third-stack stun.
    
- Fourth- and fifth-stack Static Charge interruptions.
    
- Sixth-stack Lightning Discharge.
    
- DMG-based multiplicative speed buffs.
    
- Preservation of the strongest completed Charge.
    
- Preservation of the strongest individually received buff.
    
- Parallel completed and building stack sets.
    
- Shared enemy-side expiration timer.
    
- Independent player-side buff timers.
    
- Stability Barrier depletion through crowd-control protection.
    

Further development primarily concerns numerical balancing, experimental speed scaling, Stability Barriers, implementation, visual representation and individual status combinations.