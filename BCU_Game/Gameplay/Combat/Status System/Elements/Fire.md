# Fire, Burn & Combustion

**Identity:** Heat accumulation, sustained burning and explosive propagation  
**Status Family:** Elemental  
**Damage Categories:** Physical and Magical  
**Maximum Stacks:** 6  
**Base Stack Duration:** 5 seconds (provisional)  
**Third-Stack Payoff:** Burn  
**Sixth-Stack Payoff:** Combustion

---

## Fire

### Core Mechanics

- Fire represents the accumulation of Heat within an affected entity.
    
- Every successful Fire application stores an individually calculated amount of potential Heat DMG.
    
- Fire supports two Damage Categories:
    
    - **Physical Fire:** Stores physical Heat.
        
    - **Magical Fire:** Stores magical Heat.
        
- Both variants belong to the same status and share a maximum of 6 stacks.
    
- Each stack possesses its own Damage Category.
    
- Hybrid stacks do not exist.
    
- Fire stacks do not provide additional DMG per hit.
    
- Accumulated Heat contributes toward Burn and Combustion.
    
- Heat storage is independent of the affected entity's defenses, resistances and vulnerabilities.
    

### Stack Progression

|Stacks|Effect|
|---|---|
|1–2|Accumulate Heat.|
|3|Accumulate Heat and trigger Burn.|
|4–5|Continue accumulating Heat and refresh Burn.|
|6|Accumulate Heat, trigger Combustion and apply stronger Burn.|

- Every stack contributes toward accumulated Heat.
    
- The third and sixth stacks contribute their own Heat before resolving their respective payoffs.
    
- Multiple stacks applied through one damage instance resolve their thresholds sequentially.
    
- Both Burn and Combustion can activate through the same originating damage instance.
    
- Eligible status combinations take priority over ordinary sixth-stack resolution.
    

---

## Heat Storage

### Individual Stack Strength

- Each Fire stack stores an individually calculated amount of potential Heat DMG.
    
- Stored Heat references the originating attack's corresponding Fire DMG before target-side mitigation.
    
- Heat applications independently roll their own critical strike.
    
- Stored Heat is calculated before all target-side mitigation and vulnerability.
    
- The exact Heat scaling formula remains undecided.
    

### Calculation Order

1. Reference the corresponding non-critical, pre-mitigation Fire DMG of the triggering attack.
    
2. Resolve the Heat application's independent critical strike.
    
3. Calculate the resulting Heat contribution using the applicable offensive properties and Heat scaling.
    
4. Store the calculated Heat value.
    

The following do not influence Heat storage:

- Physical DEF.
    
- Magical DEF.
    
- Fire DMG Resistance.
    
- DMG vulnerability.
    

These modifiers are instead applied when accumulated Heat produces actual DMG.

### Stored Properties

Each Fire stack remembers:

- Original contributor.
    
- Damage Category.
    
- Final calculated Heat value.
    
- Application order.
    

### Critical Heat

- Each Heat application can independently critically strike.
    
- The resulting critical DMG is stored directly as the calculated Heat value.
    
- Critical multipliers are not stored as additional modifiers that need to be reapplied.
    
- Previously calculated critical DMG remains part of stored Heat.
    
- Stored Heat is not recalculated when the originating player's attributes change.
    
- Stored Heat is not influenced by changes to the affected entity's defenses, resistances or vulnerabilities.
    

### Accumulated Heat

The total available Heat consists of:

- Heat stored within ordinary Fire stacks.
    
- Remembered Heat originating from surrounding Combustions.
    

Both sources contribute toward Burn and Combustion.

Propagated Heat does not count toward the six-stack threshold.

---

## Burn

### Core Mechanics

- Burn deals sustained Damage over Time (DoT).
    
- Ordinary Burn activates upon reaching three Fire stacks.
    
- Burn calculates its strength from accumulated Heat.
    
- Burn preserves the physical and magical Damage Categories of its contributing Heat.
    
- Burn can contain both physical and magical DMG components.
    
- Burn itself does not count toward Fire stacks.
    
- Burn can remain active while the affected entity possesses fewer than three Fire stacks through Combustion propagation and subsequent Fire applications.
    

### Ordinary Burn

- Reaching three Fire stacks triggers ordinary Burn.
    
- Burn references the accumulated Heat of all three contributing stacks.
    
- Remembered propagated Heat also contributes toward ordinary Burn.
    
- Burn performs an additional independent critical strike roll upon activation.
    
- The resulting calculated Burn strength is stored.
    
- Additional Fire applications refresh Burn's duration.
    
- Ordinary duration refreshing does not recalculate Burn strength.
    

### Combustion Burn

- Combustion applies a stronger version of Burn.
    
- Combustion Burn references accumulated Heat from all six Fire stacks and any remembered propagated Heat.
    
- Combustion's critical strike result also affects its resulting Burn.
    
- Combustion Burn does not require existing Fire stacks.
    
- Subsequent Fire applications refresh Combustion Burn even when rebuilding from one Fire stack.
    

### Strongest Burn Rule

Each group maintains one active Burn per enemy.

When another Burn is generated:

- A stronger Burn replaces the existing Burn.
    
- An equally strong Burn refreshes the existing Burn.
    
- A weaker Burn refreshes the existing Burn without reducing its strength.
    
- Multiple Burn effects from the same group do not stack independently.
    
- Burn strength comparisons reference calculated stored DMG, including critical contributions, before target-side mitigation.
    
- Ordinary Fire applications refresh the existing Burn without requiring new strength calculations.
    

The strongest Burn can therefore be maintained throughout multiple Combustion cycles.

### Burn DMG Calculation

Burn preserves its calculated offensive properties upon creation.

Every DoT tick dynamically references:

- Corresponding physical or magical DEF.
    
- Fire-specific DMG Resistance.
    
- Corresponding DMG vulnerability.
    
- Other applicable target-side modifiers.
    

Unlike [[Slash]], Burn does not inherently ignore DEF.

### Burn Critical Strikes

Burn can benefit from two layers of critical strikes:

1. Critical DMG already contained within accumulated Heat.
    
2. The independent critical strike of the Burn payoff.
    

The resulting calculated DMG is stored without retaining additional critical multipliers for repeated application.

Individual Burn ticks do not roll for critical strikes again.

---

## Burn Tick Mechanics

### Shared Tick Timer

- Each group's Burn maintains its own DoT tick timer.
    
- Physical and magical Burn components share the same tick timer.
    
- Different groups maintain independent tick timers.
    
- The first DoT tick occurs after the first tick interval has passed.
    

### Timer Preservation

The Burn tick timer is not reset by:

- Ordinary Fire applications.
    
- Duration refreshing.
    
- Replacement with a stronger Burn.
    
- Refreshing through a weaker Burn.
    
- Combustion applying a new Burn while Burn is already active.
    

### Tick Resolution

- Physical and magical DMG components are calculated independently.
    
- Stored base Burn DMG remains unchanged unless replaced or altered through cleansing.
    
- Applicable target-side modifiers are calculated dynamically every tick.
    
- If expiration and a damage tick occur simultaneously, the damage tick resolves before expiration.
    
- The exact Burn tick interval remains undecided.
    

These timing mechanics follow the established principles of [[Slash]].

---

## Combustion

### Core Mechanics

- Combustion is Fire's sixth-stack payoff.
    
- Reaching six Fire stacks triggers Combustion unless an eligible status combination takes priority.
    
- Combustion calculates its strength from all accumulated Heat.
    
- The sixth Fire stack contributes its own calculated Heat before Combustion activates.
    
- Remembered propagated Heat also contributes toward Combustion.
    
- Combustion deals immediate AoE Fire DMG.
    
- Combustion applies Burn to affected enemies.
    
- Combustion consumes all six Fire stacks and all accumulated Heat belonging to the triggering group's pool.
    
- The resulting Burn remains active independently of ordinary Fire stacks.
    
- A new Fire buildup can begin immediately afterward.
    

### Combustion Center

- The primary target's position at the moment of activation determines the explosion's center.
    
- The primary target receives the full calculated Combustion effect before its own mitigation.
    
- Surrounding enemies receive reduced effects based on their distance from the center.
    

### Critical Strikes

- Combustion performs one independent critical strike roll for the entire explosion.
    
- Individual affected enemies do not roll separate Combustion critical strikes.
    
- The shared critical result affects:
    
    - Immediate Combustion DMG.
        
    - Resulting Burn strength.
        
    - Propagated Heat contribution.
        
- Previously stored critical Heat remains part of the accumulated DMG.
    
- Previous critical multipliers are not reapplied separately.
    

### Damage Categories

- Combustion preserves the physical and magical distribution of its accumulated Heat.
    
- Physical Heat contributes toward physical Combustion DMG.
    
- Magical Heat contributes toward magical Combustion DMG.
    
- Actual DMG components are calculated independently against their corresponding DEF.
    
- Combustion does not convert accumulated Heat into a single Damage Category.
    

### Outgoing Combustion Strength

- Combustion calculates its outgoing strength before applying any affected enemy's defenses.
    
- The primary target's mitigation does not influence the outgoing explosion strength.
    
- Every affected enemy independently mitigates the DMG it receives.
    
- A resistant primary target cannot reduce the outgoing Heat, Burn strength or Combustion DMG directed toward surrounding enemies.
    

---

## Combustion AoE & Falloff

### Primary Target

- Receives 100% of calculated Combustion DMG before individual mitigation.
    
- Receives 100% of calculated Combustion Burn strength.
    

### Secondary Targets

- Receive between 80% and 50% of calculated Combustion effects.
    
- The maximum secondary-target strength is 80%, even when standing directly at the explosion's center.
    
- The minimum strength is 50% at the edge of the explosion's radius.
    

### Provisional Linear Falloff

|Distance from Center|Effect Strength|
|---|---|
|Primary target|100%|
|Secondary target at center|80%|
|25% of radius|72.5%|
|50% of radius|65%|
|75% of radius|57.5%|
|Edge of radius|50%|

### Applicable Effects

The same distance-based falloff applies to:

- Immediate Combustion DMG.
    
- Combustion Burn strength.
    
- Stored propagated Heat.
    

The exact Combustion radius and falloff curve remain subject to numerical balancing.

### Individual Target Resolution

1. Determine the outgoing Combustion strength.
    
2. Apply the shared Combustion critical result.
    
3. Determine the corresponding distance-based falloff for each affected enemy.
    
4. Calculate the resulting potential DMG and propagated Heat.
    
5. Apply each enemy's individual defenses, resistances and vulnerabilities to its actual incoming DMG.
    

Target-side mitigation never reduces the stored propagated Heat.

---

## Heat Propagation

### Core Mechanics

When a secondary enemy is affected by Combustion:

- Receives immediate Combustion DMG.
    
- Receives Burn.
    
- Receives a remembered propagated Heat contribution.
    
- Does not receive ordinary Fire stacks.
    
- Existing Fire stacks remain intact.
    
- Existing Fire stack duration is refreshed.
    
- Existing Burn follows the strongest Burn rule.
    
- Propagated Heat can contribute toward future Burn and Combustion payoffs.
    

### Propagated Heat Storage

- Propagated Heat exists alongside ordinary Fire stacks.
    
- Propagated Heat does not count toward status thresholds.
    
- Propagated Heat can exist on enemies without ordinary Fire stacks.
    
- Propagated Heat preserves its physical and magical Damage Categories.
    
- Propagated Heat remembers the original contributors and their respective DMG contributions.
    
- Propagated Heat includes the applicable Combustion critical result.
    
- Propagated Heat includes the applicable AoE falloff.
    

Propagated Heat is unaffected by:

- The primary target's DEF.
    
- The primary target's Fire DMG Resistance.
    
- The receiving target's DEF.
    
- The receiving target's Fire DMG Resistance.
    
- DMG vulnerability.
    

### Strongest Propagation Rule

- Each group maintains one remembered propagated Heat contribution per enemy.
    
- Multiple propagated Heat contributions do not accumulate independently.
    
- A stronger contribution replaces the previous contribution.
    
- An equally strong or weaker contribution refreshes the duration without reducing the stored value.
    
- Ordinary Fire applications refresh the remembered propagated Heat.
    

### Heat Consumption

When an enemy triggers its own Combustion:

- All six ordinary Fire stacks are consumed.
    
- All Heat stored within those stacks is consumed.
    
- Remembered propagated Heat is consumed.
    
- The combined Heat contributes toward the resulting Combustion and Burn.
    

---

## Recursive Propagation

### Exponential Experiments

- Previously propagated Heat can contribute toward future Combustions.
    
- These Combustions can propagate their resulting Heat to additional enemies.
    
- Repeated Combustions can therefore create increasingly powerful Heat propagation chains.
    
- Each new Combustion can introduce additional Heat from ordinary Fire applications.
    
- Previously stored critical DMG remains part of the inherited Heat.
    
- Newly triggered Combustions can independently critically strike again.
    

### Existing Limitations

- Secondary-target propagation is limited to 80–50% strength.
    
- Only the strongest propagated Heat contribution is remembered.
    
- Propagated Heat does not independently apply Fire stacks.
    
- Six successful ordinary Fire stack applications are still required to trigger Combustion.
    
- Propagated Heat expires with the shared Fire duration.
    
- Combustion consumes its accumulated Heat.
    

### Design Intent

- Recursive propagation is intentionally permitted during early testing.
    
- Potential exponential scaling should be discovered and evaluated early in development.
    
- The revised pre-mitigation Heat system removes target-side defenses as a limitation on Heat accumulation and propagation.
    
- Additional limitations will only be introduced if testing demonstrates that they are necessary.
    
- No dedicated recursive propagation cap is currently established.
    

---

## Duration & Expiration

### Shared Expiration Timer

Each group maintains one shared Fire expiration timer per enemy.

The following share this timer:

- Ordinary Fire stacks.
    
- Stored Heat.
    
- Active Burn.
    
- Remembered propagated Heat.
    

### Duration Refreshing

- Every successful ordinary Fire application refreshes the shared duration.
    
- Combustion propagation refreshes the receiving enemy's existing Fire duration for the contributing group.
    
- Existing Burn and propagated Heat are refreshed alongside ordinary stacks.
    
- Burn and propagated Heat can maintain the shared timer even when no ordinary Fire stacks exist.
    

### Simultaneous Expiration

Unlike the physical statuses, Fire does not follow gradual stack decay.

When the shared expiration timer ends:

- All ordinary Fire stacks disappear simultaneously.
    
- All accumulated Heat disappears.
    
- Remembered propagated Heat disappears.
    
- Active Burn expires.
    

Fire must be continuously maintained to preserve its accumulated potential.

### Status Lifecycle

- Fire (1–2): Heat accumulation.
    
- Fire (3): Burn activation.
    
- Fire (4–5): Continued Heat accumulation and Burn maintenance.
    
- Fire (6): Combustion.
    
- Following Combustion: Burn without ordinary Fire stacks.
    
- New Fire applications restart the buildup while maintaining Burn.
    
- Shared timer expiration removes all remaining Fire-related effects.
    

---

## Cleansing

### FIFO Principle

- Fire cleansing follows FIFO (First In, First Out).
    
- Partial cleansing removes the oldest ordinary Fire stack and its corresponding stored Heat.
    
- Cleansing can also remove older propagated Heat and its associated Burn.
    
- Cleansing does not perform new critical strike rolls.
    

### Ordinary Burn Cleansing

If ordinary Burn is active:

- Removing contributing Heat reduces the corresponding Burn DMG.
    
- Remaining Heat values preserve their previously calculated DMG.
    
- Burn strength is recalculated from the remaining applicable Heat.
    
- If cleansing reduces ordinary Fire below the three-stack ignition requirement, the associated ordinary Burn can be removed.
    

### Combustion Burn Cleansing

If older Combustion Burn exists alongside newer ordinary Fire stacks:

- A single-stack cleansing effect removes the oldest ordinary Fire stack.
    
- The older Combustion Burn is also removed.
    
- Associated older propagated Heat is removed where applicable.
    

### Example

An enemy possesses:

- Burn originating from an earlier Combustion.
    
- Remembered propagated Heat.
    
- Two subsequently applied ordinary Fire stacks.
    

A single-stack cleansing effect removes:

- The oldest ordinary Fire stack.
    
- Its corresponding Heat.
    
- The older propagated Heat.
    
- The associated Combustion Burn.
    

The newest ordinary Fire stack remains.

### Cleansing Without Ordinary Stacks

If an enemy possesses only propagated Heat and Burn:

- A single-stack cleansing effect removes both.
    
- Ordinary Fire stacks are not required for cleansing these effects.
    

---

## DMG Calculation & Mitigation

### Modifier Interactions

|Modifier|Heat Storage|Actual Burn & Combustion DMG|
|---|---|---|
|Critical DMG|Yes|Yes|
|Corresponding DEF|No|Yes|
|Fire-specific DMG Resistance|No|Yes|
|Corresponding DMG vulnerability|No|Yes|
|Combustion AoE falloff|Yes, for propagated Heat|Yes|

### Potential Heat vs. Actual DMG

- Heat represents accumulated potential energy.
    
- Actual DMG represents the affected entity's response to that energy.
    
- The ability to withstand Heat does not reduce the amount of Heat present.
    
- DEF and Fire DMG Resistance only mitigate actual incoming DMG.
    
- DMG vulnerability only amplifies actual incoming DMG.
    
- Target-side mitigation and vulnerability do not influence ordinary or propagated Heat storage.
    
- The previous double-mitigation system has been removed.
    

### Natural Status Synergies

#### Impact & Fracture

- Corresponding DEF reduction improves applicable Burn and Combustion DMG.
    
- DEF reduction does not increase stored Heat.
    
- Changes to DEF dynamically influence subsequent Burn ticks.
    

#### Puncture & Breach

- Corresponding DMG vulnerability improves Burn and Combustion DMG.
    
- DMG vulnerability does not increase Heat storage.
    
- Breach's applicable Stability Barrier interactions remain independently defined.
    

#### Ice & Freeze

- Final Critical Chance vulnerability from [[Ice]] can improve the responsible group's Heat application critical rolls.
    
- Final Critical Chance vulnerability can also improve Burn and Combustion activation critical rolls.
    
- Previously stored Heat and Burn values are not retroactively modified.
    

These interactions do not require actual status combinations.

---

## Multiplayer & Group Ownership

### Shared Fire Pool

- Players belonging to the same group contribute toward one shared Fire pool on each enemy.
    
- Physical and magical Fire applications share the same six-stack threshold.
    
- Every contributing stack retains its original contributor.
    
- Group members collectively accumulate Heat.
    
- One group maintains one shared Burn per enemy.
    
- One group maintains one remembered propagated Heat contribution per enemy.
    

### Separate Groups

Different groups maintain completely independent:

- Fire stacks.
    
- Accumulated Heat.
    
- Burn.
    
- Propagated Heat.
    
- Expiration timers.
    
- Burn tick timers.
    

Applications from one group do not ordinarily refresh or modify another group's Fire pool.

### Group Membership Changes

- Previously contributed Heat remains within its original group pool if a contributing player leaves the group.
    
- Stored Heat is not removed or recalculated because its contributor leaves.
    
- Previously stored contribution ownership remains intact.
    

### DMG Attribution

Burn and Combustion DMG credit is distributed proportionally according to each player's stored Heat contribution.

|Player|Stored Heat|DMG Credit|
|---|---|---|
|A|600|60%|
|B|300|30%|
|C|100|10%|
|Total|1,000|100%|

Proportional attribution applies to:

- Burn DMG.
    
- Combustion DMG.
    
- Propagated Heat.
    
- Subsequent effects originating from remembered Heat.
    
- Aggro generation.
    

### Propagated Ownership

- Propagated Heat retains the original contribution distribution.
    
- Future Combustions can contain contributions from ordinary Fire stacks and propagated Heat.
    
- The player applying the sixth stack does not automatically receive all Combustion DMG credit.
    

The universal multiplayer status ownership system will be consolidated after reviewing all individual statuses.

---

## Resistance & Immunity

### Status Chance Resistance

- Fire Status Chance Resistance influences the probability of successfully applying Fire stacks.
    
- It does not reduce the amount of Heat stored by successfully applied stacks.
    
- Guaranteed direct applications follow the general [[Status]] rules.
    

### Fire DMG Resistance

- Fire DMG Resistance is independent of Status Chance Resistance.
    
- Fire DMG Resistance mitigates actual Fire DMG, Burn DMG and Combustion DMG.
    
- Fire DMG Resistance does not influence ordinary Heat storage.
    
- Fire DMG Resistance does not influence propagated Heat storage.
    
- Burn dynamically references current resistance during each tick.
    
- Combustion independently references each affected enemy's current resistance upon dealing DMG.
    

### Complete DMG Resistance

- An enemy with 100% Fire DMG Resistance can still accumulate Fire stacks.
    
- Heat accumulates normally regardless of Fire DMG Resistance.
    
- The enemy can still reach six stacks and trigger Combustion.
    
- The enemy can visibly burn without receiving Burn DMG.
    
- Complete resistance prevents actual Fire DMG rather than preventing Heat from existing.
    
- Complete resistance does not inherently prevent status progression or eligible combinations.
    

### Resistant Combustion Centers

- Fire-resistant enemies can serve as Combustion centers against surrounding enemies.
    
- The primary target's resistance only protects the primary target.
    
- Surrounding enemies receive their own independently calculated portion of the explosion.
    
- A completely resistant primary target can receive zero Combustion DMG while surrounding vulnerable enemies receive significant DMG.
    
- Propagated Heat remains independent of all affected enemies' defenses.
    

### Illustrative Example

Assuming an outgoing Combustion strength of 1,000 and disregarding DEF and vulnerability:

|Target|Potential DMG|Fire Resistance|Actual DMG|
|---|---|---|---|
|Primary target|1,000|100%|0|
|Secondary target at center|800|0%|800|
|Secondary target at edge|500|20%|400|

The primary target's immunity does not affect the surrounding enemies' incoming DMG or their stored propagated Heat.

---

## Additional Interactions

### Recursive Status Applications

- Burn ticks cannot apply ordinary statuses through Status Chance rolls.
    
- Combustion bursts cannot apply ordinary Fire stacks through Status Chance rolls.
    
- Heat propagation is an explicitly defined mechanic rather than an ordinary Status Chance application.
    
- Specialized status combinations may define explicit additional applications.
    

### Invulnerability

- Fire stacks, stored Heat, Burn and propagated Heat continue their expiration timers during invulnerability.
    
- Burn continues its normal tick timing.
    
- Invulnerable enemies receive no DMG during invulnerability.
    
- Invulnerability does not suspend Fire's timers.
    

### Attacker Death

- Existing Fire contributions remain active after their originating player dies.
    
- Stored Heat and contribution ownership remain unchanged.
    
- General status persistence rules apply.
    

### Stability Barriers

- Burn and Combustion damage Stability Barriers before HP.
    
- Neither inherently bypasses Stability Barriers.
    
- Detailed interactions remain subject to the general Stability Barrier system.
    

---

## Status Combinations

### Requirements

- Fire can participate in compatible elemental and physical-elemental combinations.
    
- Eligible combinations take priority over ordinary Combustion resolution.
    
- Ordinary physical statuses require their enhanced states before combining with Fire.
    
- General group-based combination limitations follow [[Status]].
    

### Existing Elemental Combinations

|Partner|Combination|
|---|---|
|[[Ice]]|[[Cool Combustion]]|
|[[Lightning]]|[[Arc Combustion]]|
|[[Poison]]|[[Toxic Combustion]]|

### Physical Status Combinations

|Partner|Required State|Combination|
|---|---|---|
|[[Slash]]|Laceration|[[Burned Wounds]]|
|[[Impact]]|Fracture|[[Thermal Fracture]] (proposed)|
|[[Puncture]]|Breach|[[Internal Combustion]] (proposed)|

### Individual Combination Rules

The following mechanics will be determined individually:

- Heat consumption or preservation.
    
- Burn consumption or preservation.
    
- Propagated Heat interactions.
    
- Combination DMG calculation.
    
- Critical strike behavior.
    
- AoE and propagation mechanics.
    
- Duration.
    
- Additional Fire applications.
    
- Transition back into ordinary Fire or Burn.
    
- Effects upon expiration.
    

Existing Fire combinations must be reconciled with the redesigned Heat accumulation system.

---

## Lore

- Fire represents accumulated thermal energy within an entity.
    
- Repeated Fire applications introduce additional Heat.
    
- Reaching the ignition threshold causes the entity to burn.
    
- Continued accumulation eventually exceeds the entity's ability to contain the stored Heat.
    
- Combustion violently releases this accumulated energy.
    
- Surrounding entities absorb part of the released Heat, allowing Fire to propagate.
    
- An entity's resistance determines how much the Heat affects it, not how much Heat exists.
    
- Resistant entities can therefore remain covered in flames and release powerful Combustions without suffering corresponding damage themselves.
    
- Continued Fire applications maintain existing thermal instability.
    
- Unlike physical structural damage, accumulated Heat dissipates simultaneously when its duration expires.
    

---

## Placeholder Values

|Parameter|Value|
|---|---|
|Maximum Fire stacks|6|
|Burn activation threshold|3 stacks|
|Combustion activation threshold|6 stacks|
|Base shared duration|5 seconds (provisional)|
|Primary-target Combustion strength|100%|
|Maximum secondary-target strength|80%|
|Minimum secondary-target strength|50%|
|Maximum active Burns per group per enemy|1|
|Maximum remembered propagated Heat contributions per group per enemy|1|
|Heat scaling coefficient|Undetermined|
|Ordinary Burn scaling coefficient|Undetermined|
|Combustion Burn scaling coefficient|Undetermined|
|Combustion burst scaling coefficient|Undetermined|
|Burn tick interval|Undetermined|
|Combustion radius|Undetermined|
|Recursive propagation cap|None for now|

---

## Remaining Open Questions

### Numerical Balancing

- Exact ordinary Heat scaling formula.
    
- Exact ordinary Burn scaling formula.
    
- Exact Combustion Burn scaling formula.
    
- Exact Combustion burst scaling formula.
    
- Burn tick interval.
    
- Shared base duration.
    
- Combustion radius.
    
- Final AoE falloff curve.
    
- Balancing pre-mitigation Heat accumulation.
    
- Balancing two-layer critical strikes.
    
- Balancing interactions with Ice's Final Critical Chance vulnerability.
    

### Propagation Experiments

- Potential exponential Heat growth.
    
- Repeated propagation between densely grouped enemies.
    
- Recursive critical scaling.
    
- Potential future propagation limitations.
    
- Maximum practical stored Heat values.
    
- Combustion strategies using completely Fire-resistant enemies.
    

### Cleansing & Implementation

- Exact ordering of simultaneously applied Heat contributions.
    
- Burn recalculation after partial cleansing.
    
- Handling multiple stacks crossing thresholds within one damage instance.
    
- Stability Barrier interactions.
    
- Group ownership changes and contribution tracking.
    

### Status Combinations

- Rework existing Fire combinations around Heat storage.
    
- Finalize Thermal Fracture.
    
- Finalize Internal Combustion.
    
- Establish combination-specific Burn and propagation mechanics.
    

### Visual Representation

- Representation of ordinary Fire stacks.
    
- Representation of accumulated Heat.
    
- Burn visual effects.
    
- Combustion visual effects.
    
- Representation of remembered propagated Heat.
    
- Visibility of stronger Burn applications.
    
- Group-specific Fire indicators.
    
- Burning effects on completely Fire-resistant enemies.
    
- DMG display for accumulated physical and magical Burn components.
    

---

## Design Status

Fire's fundamental mechanics are established.

The previous additional DMG per hit system has been removed and replaced with Heat accumulation.

The previous post-mitigation Heat storage system has been replaced with pre-mitigation Heat storage.

Fire's defining mechanics are:

- Shared group-based Heat accumulation.
    
- Heat storage independent of target-side mitigation and vulnerability.
    
- Independent critical Heat applications.
    
- Third-stack ignition.
    
- Sixth-stack Combustion.
    
- Strongest Burn preservation.
    
- Simultaneous expiration.
    
- Recursive Heat propagation.
    
- Independent mitigation for every affected enemy.
    
- Combustion propagation through Fire-resistant enemies.
    
- Proportional multiplayer DMG attribution.
    

Further development primarily concerns numerical balancing, propagation experiments, implementation, visual representation and individual status combinations.