# Status System

## Design Philosophy

The Status System rewards deliberate status application, weapon specialization, build diversity and cooperation between players without making solo play ineffective.

Statuses build toward meaningful payoffs and can interact with other statuses to produce unique combinations.

The system distinguishes between Damage Categories, Damage Types, Status Chances, Status Resistance and Status Vulnerability.

---

# 1. Damage Categories and Damage Types

Damage Category and Damage Type are two independent classifications.

## Damage Categories

- **Physical Damage (PH)**
- **Magical Damage (MA)**

The Damage Category determines which defensive attribute mitigates the incoming damage.

- Physical Damage is calculated against Physical Defense.
- Magical Damage is calculated against Magical Defense.

Further defensive calculations are defined in [[Damage Calculation]].

## Damage Types and Status Families

### Physical

- [[Slash]]
- [[Impact]] — provisionally established.
- Puncture — undecided.

### Elemental

- [[Fire]]
- [[Ice]]
- [[Lightning]]
- [[Poison]]

### Otherworldly

- [[Instability]]
- [[Coptering]]

Otherworldly statuses are currently excluded from universal status combinations.

Their compatibility with the universal status rules must be determined individually.

## Damage Classification

The classification of a status as physical or elemental is independent of its originating Damage Category.

|Damage Component|Damage Category|Damage Type|
|---|---|---|
|Physical Slash|Physical|Slash|
|Magical Slash|Magical|Slash|
|Physical Impact|Physical|Impact|
|Magical Impact|Magical|Impact|
|Physical Fire|Physical|Fire|
|Magical Fire|Magical|Fire|

Every attack and ability defines its own damage composition.

### Weapon Examples

- [[Sword]] — Physical Slash.
- [[Adept Scythe]] — Magical Slash.
- [[Shooting Morningstar]] — Physical and Magical Impact.

Physical and Magical variants of the same Damage Type apply the same underlying status.

Magic is not inherently elemental, and Physical Damage is not restricted to physical status types.

---

# 2. Individual Status Chances

Every applicable Damage Type within an attack or ability possesses its own Status Chance.

There is no single universal status roll that selects one status from all available Damage Types.

## Universal Rules

- Each Damage Type rolls independently.
- Multiple different statuses can be applied simultaneously.
- Physical and Magical variants of the same Damage Type share its Status Chance roll.
- There is no universal restriction on how many different statuses may be applied through one hit.
- Status Chances can be individually adjusted for each attack, ability and damage instance.

## Example

|Damage Type|PH DMG|MA DMG|Total DMG|Base Status Chance|
|---|--:|--:|--:|--:|
|Impact|70|30|100|40%|
|Slash|50|0|50|20%|
|Fire|10|40|50|10%|
|**Total**|**130**|**70**|**200**|**70%**|

The attack independently rolls Impact, Slash and Fire.

It can apply all three statuses, two statuses, one status or no status.

The combined Status Chance represents the sum of the individual Status Chances rather than the probability of applying at least one status.

---

# 3. Base and Final Status Chance

Status Chance modifiers are differentiated through:

- Base Status Chance % (BC%).
- Final Status Chance % (FC%).

## Base Status Chance %

BC% increases the individual base Status Chances proportionally.

### Formula

Modified Base Chance = Original Base Chance × (1 + BC Modifier)

### Example — +50% BC

|Damage Type|Original Chance|Modified Chance|
|---|--:|--:|
|Impact|40%|60%|
|Slash|20%|30%|
|Fire|10%|15%|
|**Total**|**70%**|**105%**|

## Final Status Chance %

FC% modifies the final Status Chance.

The proposed implementation adds percentage points to the combined Status Chance and distributes them proportionally across the individual Damage Types.

### Proposed Example — +50% FC

|Damage Type|Original Chance|Modified Chance|
|---|--:|--:|
|Impact|40%|68.57%|
|Slash|20%|34.29%|
|Fire|10%|17.14%|
|**Total**|**70%**|**120%**|

The proportional FC distribution and the exact interaction between BC% and FC% remain to be confirmed.

---

# 4. Status Chance Above 100%

Individual Status Chances can exceed 100%.

Every complete 100% guarantees one stack.

The remaining percentage represents the probability of applying an additional stack.

|Individual Status Chance|Guaranteed Stacks|Additional Stack Chance|
|--:|--:|--:|
|70%|0|70%|
|100%|1|0%|
|115%|1|15%|
|150%|1|50%|
|200%|2|0%|
|245%|2|45%|

This calculation applies independently to each Damage Type.

A combined Status Chance exceeding 100% does not necessarily guarantee a status application.

Stacks guaranteed through a Status Chance exceeding 100% remain part of the normal Status Chance system and are distinct from directly applied guaranteed stacks.

---

# 5. Physical and Magical Status Applications

Physical and Magical variants of a Damage Type apply the same underlying status while retaining their originating Damage Category.

Each successfully applied stack determines its Damage Category proportionally to the originating attack's Physical and Magical damage distribution for that specific Damage Type.

## Rules

- Only damage belonging to the relevant Damage Type is considered.
- Damage distribution is calculated before enemy defenses.
- Each successfully applied stack independently determines its Damage Category.
- Multiple stacks applied through the same hit may have different Damage Categories.
- Different Damage Types determine their categories independently.

## Example — Shooting Morningstar

An attack deals:

- 70 Physical Impact Damage.
- 30 Magical Impact Damage.

Every successfully applied Impact stack has:

- 70% probability of becoming Physical Impact.
- 30% probability of becoming Magical Impact.

If the attack applies two Impact stacks, both independently determine their Damage Category.

The possible outcomes are:

- Two Physical Impact stacks.
- One Physical and one Magical Impact stack.
- Two Magical Impact stacks.

An attack containing Impact and Fire independently determines the category of each successfully applied Impact and Fire stack.

---

# 6. Player-Specific Status Stack Pools

Each player maintains their own status stack pools on every affected enemy.

Status stacks are not universally shared between players.

## Universal Rules

- Every player possesses a separate stack pool for each status on each enemy.
- Physical and Magical variants belong to the same player-specific status pool.
- Both Damage Categories share the same maximum stack count within that pool.
- Both Damage Categories contribute equally toward status thresholds.
- Other players cannot replace, refresh or extend a player's stacks through ordinary applications.
- Allied players can activate eligible status combinations together.
- Non-allied players cannot combine their statuses.

## Example — Slash

Player A applies four Slash stacks.

Player B applies three Slash stacks.

The enemy has:

- Four Slash stacks belonging to Player A.
- Three Slash stacks belonging to Player B.

Neither player has reached their six-stack threshold.

The seven total Slash stacks do not activate a completed six-stack set.

## Stored Stack Properties

Every applied stack retains its individual properties, including:

- Original owner.
- Damage Category.
- Original offensive damage value.
- Critical hit result.
- Applicable Critical Damage multiplier.
- Status-specific effect properties.
- Duration determined upon application.
- Application order.

Changes to the originating player's attributes do not modify the stored offensive properties of existing stacks.

---

# 7. Maximum Stacks and FIFO Replacement

The existing five universal statuses build toward six stacks:

- Slash.
- Fire.
- Ice.
- Lightning.
- Poison.

Impact's final maximum stack count remains undecided.

When a status pool reaches its maximum stack count, further applications ordinarily replace the oldest stack.

This follows the **First In, First Out (FIFO)** principle.

## Rules

- The oldest stack is removed.
- The newest stack takes its place.
- Replacement occurs only within the originating player's own status pool.
- Replacement can change the Physical/Magical composition of the pool.
- Replacement does not increase the maximum stack count.
- Status-specific payoff, retention and consumption mechanics can define exceptions.

## Example — Impact

Assuming a provisional maximum of four Impact stacks:

P = Physical Impact.

M = Magical Impact.

|New Application|Stack Order — Oldest to Newest|
|---|---|
|Physical|P|
|Physical|P · P|
|Magical|P · P · M|
|Magical|P · P · M · M|
|Magical|P · M · M · M|
|Magical|M · M · M · M|

Each individual stack retains its original properties until removed, replaced, consumed or expired.

---

# 8. Status Duration

Every player-specific status pool maintains its own shared expiration timer.

The existing universal statuses ordinarily have a base stack duration of five seconds, unless their individual mechanics specify otherwise.

## Rules

- Applying a new stack refreshes the duration of the originating player's entire status pool.
- The refreshed duration is determined by the newest applied stack.
- The newest stack's duration replaces the previous remaining duration, even if it is shorter.
- Refreshing the duration does not recalculate existing stack properties.
- All stacks within the pool expire simultaneously when its shared expiration timer ends.
- Applying stacks does not refresh other players' status pools.

## Example

Player A applies Slash with a duration of five seconds.

Player A applies another Slash stack with a duration of seven seconds.

Player A's entire Slash pool now has seven seconds remaining.

Player A subsequently applies a Slash stack with a duration of four seconds.

Player A's entire Slash pool now has four seconds remaining.

Player B's Slash pool remains unaffected throughout this process.

Special completed-set timers and combination effects follow their respective individual rules.

---

# 9. Status Damage Tick Timer

Damaging statuses maintain a shared damage tick timer within each player-specific status pool.

## Rules

- All active stacks within the same pool deal damage simultaneously.
- Each stack retains its individual damage properties.
- Applying a new stack does not reset the damage tick timer.
- Refreshing the pool's expiration timer does not reset the damage tick timer.
- Newly applied stacks participate in the next scheduled damage tick.
- Different players maintain independent damage tick timers.
- Each status can possess its own predefined tick interval.

---

# 10. Status Damage Calculation

Status damage uses fixed offensive properties and dynamic enemy defenses.

## Fixed Offensive Properties

The offensive properties of each stack are determined and stored upon application.

Subsequent changes to the originating player's attributes do not modify existing stacks.

## Dynamic Defensive Properties

Every damage tick is calculated using the enemy's current corresponding defense.

- Physical status damage uses current Physical Defense.
- Magical status damage uses current Magical Defense.

Existing status-specific defense penetration mechanics remain applicable where explicitly defined.

Defense changes occurring after a status has been applied can influence subsequent damage ticks.

## Example

Player A applies Physical Slash.

Player B subsequently reduces the enemy's Physical Defense through Physical Impact.

Player A's existing Physical Slash stacks benefit from the enemy's reduced Physical Defense on subsequent damage ticks.

The original offensive damage values of Player A's Slash stacks remain unchanged.

Although status pools are player-specific, defense changes affect the enemy itself and can therefore benefit other players.

The aggregation of defense reductions originating from multiple players remains to be established.

---

# 11. Critical Status Damage

Status damage can critically strike.

Damaging status stacks inherit the critical result of the damage instance that applied them.

## Rules

- A critical hit applying a damaging status creates a critical status stack.
- A non-critical hit creates a non-critical status stack.
- A critical status stack deals critical damage throughout its entire lifetime.
- Individual damage ticks do not roll for Critical Chance again.
- Critical and non-critical stacks can coexist within the same status pool.
- Refreshing the pool's duration does not change existing critical properties.
- Enemy defenses remain dynamically calculated.
- Critical Damage must not be applied twice.

The critical properties of a stack remain unchanged until that stack is removed or replaced.

## General Balancing Principle

Baseline Critical Chance should remain relatively low.

Critical hits should be meaningful rather than becoming the default outcome of most attacks.

Dedicated critical builds may achieve higher values through investment.

See [[Critical Hits]] for the existing provisional critical attributes and further balancing.

---

# 12. Status Resistance and Status Vulnerability

Damage mitigation and status application resistance are independent systems.

## Damage Mitigation

- Physical Defense reduces Physical Damage.
- Magical Defense reduces Magical Damage.

## Status Application

- General Status Resistance.
- Individual Status Resistance.
- Status Vulnerability.

No additional universal elemental damage resistance system is currently necessary.

## General Status Resistance

Provides baseline resistance against Status Chance applications.

General Status Resistance is primarily intended for elites and bosses.

Most ordinary enemies should have no General Status Resistance.

## Individual Status Resistance

Overrides General Status Resistance for a specific status.

This allows enemies to possess unique resistances or vulnerabilities appropriate to their identity.

Ordinary enemies may possess individual resistances when appropriate.

### Illustrative Example

|Enemy|General|Fire|Ice|Impact|
|---|--:|--:|--:|--:|
|Wolf|0%|—|—|—|
|Fire Elemental|0%|80%|−25%|—|
|Stone Golem|20%|—|—|60%|
|Boss|40%|—|—|—|

A dash indicates that General Status Resistance applies.

Negative individual resistance is a proposed method of representing innate status vulnerability.

All values are illustrative.

## Status Vulnerability

Status Vulnerability directly counteracts Status Resistance.

Status Vulnerability can exceed the enemy's existing resistance, increasing the effective incoming Status Chance.

### Formula

Effective Status Chance = Final Status Chance × (1 − Resistance + Vulnerability)

### Example

Assuming a Final Status Chance of 50%:

|Resistance|Vulnerability|Effective Chance|
|--:|--:|--:|
|0%|0%|50%|
|30%|0%|35%|
|30%|20%|45%|
|30%|50%|60%|
|0%|50%|75%|

## Universal Resistance Rules

Status Resistance affects application chance only.

It does not affect:

- Status damage.
- Status duration.
- Status potency.
- Maximum stack count.

Physical and Magical variants of the same status are affected by the same corresponding Status Resistance.

Separate Physical and Elemental Status Resistance layers are not required.

---

# 13. Guaranteed Status Applications

Certain weapon mechanics, abilities and effects directly apply predefined status stacks.

Guaranteed applications do not perform Status Chance rolls.

## Rules

Guaranteed status applications are unaffected by:

- Base Status Chance modifiers.
- Final Status Chance modifiers.
- General Status Resistance.
- Individual Status Resistance.
- Status Vulnerability.

Guaranteed applications always apply the explicitly defined number of stacks.

They cannot generate additional stacks through Status Chance bonuses.

Ordinary damage instances associated with these mechanics can still perform separate Status Chance rolls where applicable.

## Example — Shooting Morningstar

The [[Shooting Morningstar]] possesses guaranteed armor-reduction applications through specific attacks and mastery effects.

These direct applications remain reliable against elites and bosses regardless of their Status Resistance.

Their integration into the universal Impact status must be defined individually.

---

# 14. Independent Status Rolls

Status Chances are independently calculated and rolled:

- Per damage instance.
- Per Damage Type.
- Per affected enemy.

## Multi-Hit Attacks

Every individual damage instance performs its own applicable Status Chance rolls.

Status Chances may be adjusted individually for different hits of the same attack or ability.

This allows multi-hit attacks and fast-attacking weapons to be balanced without restricting them to one status roll per attack.

## Area-of-Effect Attacks

Every enemy affected by an attack independently rolls the applicable Status Chances.

Different enemies struck by the same attack may receive different statuses and different numbers of stacks.

---

# 15. Status Damage Restrictions

Status damage does not behave as a conventional direct attack hit.

## Recursive Status Applications

Status damage cannot apply additional statuses through Status Chance rolls by default.

Explicitly defined specialized mechanics may override this rule.

Directly scripted status applications from combination effects are distinct from automatic Status Chance rolls on status damage.

## On-Hit Effects

Status damage does not trigger general on-hit effects.

Examples:

- Life Steal.
- Stability recovery.
- Effects requiring direct attack hits.

## Player Death

Status effects persist after the player who applied them dies.

The status's damage, ownership and remaining duration are not removed or recalculated because of the originating player's death.

---

# 16. Multiplayer Ownership and Aggro

Every player's status pools remain separate.

All individual stacks retain their originating ownership.

## Damage Attribution

Status damage is attributed to the player who originally applied the corresponding stacks.

## Aggro

Status damage contributes to enemy aggro just like direct damage.

The aggro contribution is assigned to the original owner of the corresponding status damage.

## Allied Cooperation

Although players maintain separate status pools, allied players can cooperate through:

- Status combinations.
- Defense reduction.
- Status Vulnerability.
- Other enemy-wide debuffs.

The aggregation and stacking rules for enemy-wide debuffs originating from multiple players must be defined individually.

---

# 17. Status Combination System

Status combinations occur when compatible completed status sets interact.

## Combination Eligibility

- Players can combine their own compatible completed status sets.
- Allied players can combine compatible completed status sets.
- Non-allied players cannot combine their status sets.
- Individual stacks from different players do not collectively count toward one player's completed set.

## Combination Activation

1. When a status reaches six stacks, check for an eligible combination first.
2. If a compatible completed six-stack set belonging to the same player or an eligible ally exists, the combination activates automatically.
3. Otherwise, resolve the status's own sixth-stack behavior.
4. Statuses are resolved in the order they reach six stacks.
5. The first eligible pair combines.
6. Statuses directly applied by combination effects can themselves build toward six stacks and trigger further combinations.
7. When two allied players contribute to a combination, its damage credit is split equally between them.

A genuinely simultaneous event tie-breaker remains to be established.

Combination effects follow their individual duration, retention and consumption rules.

There is no universal rule requiring every completed status set to remain active after its sixth-stack payoff.

## Combination Damage Categories

Status combinations preserve the original Physical and Magical Damage Categories of their contributing damage components.

### Example

Physical Slash combines with Magical Fire.

- The Slash damage component remains Physical.
- The Fire damage component remains Magical.
- Each component is calculated against its corresponding current defense.

Status combinations do not automatically convert all participating damage into a single Damage Category.

No additional Damage Category roll is necessary solely because a combination occurs.

The calculation of newly generated combination damage must be defined individually.

---

# 18. Existing Sixth-Stack Behaviors

## Fire

[[Fire]] triggers immediate Combustion and consumes its stacks when no eligible combination takes priority.

Fire Combustion against a currently frozen target can trigger [[Cool Combustion]].

## Ice

[[Ice]] triggers Freeze for three seconds.

Additional Ice hits extend Freeze by one second, once per source.

Freeze grants the party increased Critical Chance and Critical Damage against the affected enemy.

## Lightning

[[Lightning]] triggers Discharge.

Discharge immediately applies:

- A one-second stun.
- A five-second party Attack Speed and Animation Speed buff.

One completed Lightning set remains eligible for combinations for five seconds while new Lightning stacks can build separately.

A newly completed set replaces the previous completed set.

A new Discharge buff replaces the previous buff rather than stacking with it.

A combination consuming Lightning does not prematurely remove an already granted Discharge buff.

## Poison

[[Poison]] triggers Poisonous Strikes.

See the individual Poison note for its percentage-HP damage over time, attack bonuses and provisional duration-extension progression.

## Slash

[[Slash]] reaches its maximum damage over time at six stacks.

Slash does not possess a standalone sixth-stack payoff.

A completed Slash set remains available for eligible combinations.

---

# 19. Existing Universal Combinations

|Statuses|Result|
|---|---|
|Fire + Ice|[[Cool Combustion]]|
|Fire + Lightning|[[Arc Combustion]]|
|Fire + Poison|[[Toxic Combustion]]|
|Fire + Slash|[[Burned Wounds]]|
|Ice + Lightning|[[Shattering Voltage]]|
|Ice + Poison|[[Cryotoxicity]]|
|Ice + Slash|[[Frozen Wounds]]|
|Lightning + Poison|[[Neurotoxin]]|
|Lightning + Slash|[[Conductive Wounds]]|
|Poison + Slash|[[Viral Wounds]]|

Impact combinations have not yet been established.

Puncture has not yet been established as a universal status.

Physical-to-physical status combinations remain undecided.

---

# 20. Impact — Provisional Universal Status

[[Impact]] is intended to become a universal defense-reduction status.

## Physical Impact

Reduces the enemy's Physical Defense.

## Magical Impact

Reduces the enemy's Magical Defense.

Both variants contribute toward the same player-specific Impact stack pool.

## Illustrative Example

Assuming a provisional maximum of four stacks and 5% defense reduction per stack:

|Stack Composition|PH Defense Reduction|MA Defense Reduction|
|---|--:|--:|
|P|5%|0%|
|P · M|5%|5%|
|P · P · M|10%|5%|
|P · P · M · M|10%|10%|
|M · M · M · M|0%|20%|

These values are illustrative and do not represent finalized balancing.

## Shooting Morningstar Integration

The Shooting Morningstar's existing armor-reduction mechanic is intended to become part of the universal Impact status.

Relevant application sources include:

- Focused Shooting Star.
- Other Focused normal attacks.
- Level 50 Gravitational Impact.
- Level 100 Gravitational Field.

The existing guaranteed applications remain guaranteed.

The Damage Category of each guaranteed application remains to be determined.

## Undecided

- Maximum stack count.
- Base duration.
- Defense reduction per stack.
- Maximum possible defense reduction.
- Aggregation of Impact effects from multiple players.
- Elemental combinations.
- Physical status combinations.

---

# 21. Frozen Wounds — Freeze Interaction

[[Frozen Wounds]] replaces the ordinary Freeze critical vulnerability bonus.

Ordinary Freeze and Frozen Wounds are mutually exclusive as critical vulnerability effects.

## Rules

- Their Critical Chance bonuses do not stack.
- Their Critical Damage bonuses do not stack.
- Frozen Wounds provides its own critical vulnerability bonus.
- Frozen Wounds retains the applicable Freeze mechanics.

The exact Critical Chance and Critical Damage bonuses remain undecided.

---

# 22. Status Visibility

## Solo

- The player sees their own status stacks and status effects.
- Completed status sets are clearly highlighted.

## Party

- The player's own building stacks are clearly visible.
- Allies' building stacks appear as smaller, muted indicators.
- Completed status sets are highlighted for their owner and eligible allies.

This allows allied players to recognize potential status combination opportunities.

## Outside the Party

Players see status visuals and payoff effects but do not see non-allied players' individual stack counts.

Certain allied interactions may involve [[Wave Projection]].

See [[Multiplayer]] and [[Companions]].

## Undecided

- Visual distinction between Physical and Magical stacks.
- Visual distinction between critical and non-critical stacks.
- Display of simultaneous status damage ticks.
- Display of individual and combined Status Chances.
- Visibility of enemy Status Resistance.

---

# 23. Experimental Arcade — Recursive Slash

A future Experimental Arcade test body allows the player to experiment with recursive status applications.

## Concept

An experimental version of Slash can apply additional Slash stacks through its own damage ticks.

The experiment may be activated through a dedicated button.

## Testing Properties

- Predetermined damage values.
- Predetermined Status Chance.
- Predictable initial conditions.
- Observation of recursive stack generation.
- FIFO stack replacement.
- Shared duration refreshing.
- Shared damage tick timing.

This experiment is an explicit exception to the universal rule preventing status damage from applying additional statuses.

It is not intended to become a default gameplay mechanic.

---

# 24. Remaining Design and Implementation Questions

## Status Chance

- Finalize FC% distribution.
- Finalize the interaction and calculation order between BC% and FC%.
- Determine how multiple BC% and FC% modifiers stack.
- Determine whether bonuses can grant Status Chance to Damage Types with zero base Status Chance.

## Status Resistance

- Minimum effective Status Chance.
- Maximum Status Resistance.
- Stacking of multiple Status Vulnerability sources.
- Final implementation of innate negative resistance.
- Player access to Status Resistance.

## Damage Calculation

- Offensive damage source used to calculate individual status stack damage.
- Status-specific damage coefficients.
- Interaction with General Defense.
- Status-specific defense penetration.
- Dynamic interaction with enemy-wide damage vulnerability.
- Critical properties of directly applied damaging stacks without an originating critical hit.
- Damage rounding and minimum damage.

## Stack and Timer Resolution

- Initial damage tick timing.
- Ordering of simultaneous damage ticks and expiration.
- Ordering of simultaneous applications for FIFO replacement.
- Resolution of full-stack thresholds when multiple stacks are applied through one hit.
- Interaction between incomplete sets, completed sets and individual effect timers.
- Status Duration modifiers.
- Potential tick-frequency modifiers.
- Status removal and cleansing.

## Multiplayer

- Aggregation of defense reduction and other enemy-wide debuffs originating from multiple players.
- Companion status ownership.
- Status persistence after disconnecting or leaving the map.
- Status damage contribution toward kill credit, experience and loot eligibility.

## Status Combinations

- Exact ordering of genuinely simultaneous status applications.
- Resolution of multiple eligible combinations without consuming the same completed set twice.
- Individual combination durations.
- Individual combination damage calculations.
- Individual stack consumption and retention rules.
- Interaction between Physical and Magical damage components within individual combinations.

## Individual Status Development

- Finalize Impact.
- Decide whether Puncture should be introduced.
- Establish Impact combinations.
- Determine whether physical statuses can combine with one another.
- Reconcile Magical Slash with existing Slash defense-penetration mechanics.
- Determine which universal rules apply to otherworldly statuses.
- Finalize individual status values, durations and payoffs.

---

# Design Status

The universal Status System framework is established.

Player-specific status ownership is retained.

Individual Status Chances, Physical and Magical stack categories, FIFO replacement, shared player-specific timers, dynamic enemy defenses, inherited critical status damage, Status Resistance, Status Vulnerability and guaranteed direct applications are established.

The detailed numerical balancing and individual status mechanics remain under development.

Impact is provisionally established as a universal defense-reduction status.

Puncture remains undecided.

The precise FC% calculation requires further confirmation.



# Physical Status Combinations

## General Combination Rules

- The three physical statuses are:
    - Slash.
    - Impact.
    - Puncture.
- Physical statuses cannot form combinations with other physical statuses.
- All three physical statuses should have individual combinations with every elemental status.
- Physical statuses can still naturally synergize with one another without forming an actual status combination.
- Only groups can trigger status combinations.
- The enhanced version of a physical status is required before a combination can occur.

## Combination Priority

- Physical statuses follow a First In, First Out (FIFO) priority system for combinations.
- The first physical status to reach its enhanced state receives combination priority.
- Other eligible physical statuses wait for their own combination opportunity.
- Waiting physical statuses retain their existing effects.
- Players can influence combination priority through the order in which they apply statuses.

## Combination Limitations

- Each group can maintain only one active combination per physical status per enemy.
- A single group can therefore maintain a maximum of three physical-elemental combinations on one enemy:
    - One Slash combination.
    - One Impact combination.
    - One Puncture combination.
- Different groups can maintain different combinations of the same physical status against the same enemy simultaneously.
- The combination limitation is group-based rather than globally enemy-based.
- This encourages groups to plan their weapon selection, elemental distribution and desired combinations before approaching stronger enemies.

### Example

|Physical Status|Group A|Group B|
|---|---|---|
|Slash|Frozen Wounds|Burned Wounds|
|Impact|Corrosion|Shatter|
|Puncture|Short Circuit|Internal Combustion|

- All six combinations could coexist on the same enemy.
- Neither group can simultaneously maintain another combination of an already combined physical status.

---

## Impact Combinations — Proposed

|Element|Combination|Proposed Effect|
|---|---|---|
|Fire|Thermal Fracture|Heat weakens damaged defensive structures, amplifying flat DEF reduction.|
|Ice|Shatter|Brittle defensive structures break upon receiving powerful hits, increasing percentage-based DEF reduction.|
|Lightning|Disruption|Interferes with the world's stabilization process, slowing defensive restoration and status decay.|
|Poison|Corrosion|Gradually increases physical and magical DEF reduction throughout the combination's duration.|

## Puncture Combinations — Proposed

|Element|Combination|Proposed Effect|
|---|---|---|
|Fire|Internal Combustion|Fire penetrates existing openings, causing additional bursts of internal DMG when attacked.|
|Ice|Frost Penetration|Cold penetrates the entity, reducing attack and movement speed.|
|Lightning|Short Circuit|Enhances Stability Barrier destruction through additional electrical DMG.|
|Poison|Toxic Infiltration|Poison penetrates defensive layers, progressively increasing incoming DMG vulnerability.|

- All proposed combinations will be discussed and developed individually.
- Names and effects are not yet finalized.

---

## Design Philosophy

- Slash combinations primarily manipulate wounds and DoT.
- Impact combinations primarily manipulate defensive structures and DEF.
- Puncture combinations primarily exploit openings, DMG vulnerability and Stability Barriers.
- Physical statuses should complement each other naturally without requiring physical-physical combinations.
- Group-based combination limitations encourage strategic preparation, weapon diversity and cooperation between multiple groups.
- Different groups can specialize in complementary combinations when fighting stronger enemies.

## Remaining Open Questions

- Whether identical combinations from different groups can stack their effects.
- Whether identical combinations require individual stacking limitations.
- Whether active combinations can be overridden.
- Whether the next combination can be prepared while an existing combination is active.
- How combination priority interacts with physical statuses already participating in combinations.
- How status and combination ownership is tracked between groups.
- Whether a global combination limit will eventually be necessary.
- Individual combination mechanics, scaling, duration, stacking and decay.
- Visual representation of combinations belonging to different groups.
  
  
  ## Physical Status Progression

|Status|Enhanced Status|Required Stacks|Additional Enhanced Stacks|
|---|---|--:|--:|
|[[Slash]]|Laceration|6|None|
|[[Impact]]|Fracture|6|0–6|
|[[Puncture]]|Breach|6|None|

All three physical statuses:

- Support physical and magical Damage Categories.
- Maintain player-specific status pools.
- Share six stacks between both Damage Categories within each pool.
- Retain individual stack properties.
- Follow FIFO replacement.
- Follow FIFO gradual decay.
- Reach their enhanced state upon receiving the sixth stack.
- Require their enhanced state to participate in status combinations.
- Cannot combine with other physical statuses.
- Can naturally synergize with other physical statuses.

## Gradual Status Stabilization

- Physical statuses no longer lose all stacks simultaneously upon expiration.
- Expiration removes the oldest stack or enhancement according to the individual status's decay mechanics.
- The expiration timer restarts after each decay step.
- Enhanced statuses gradually revert to their ordinary forms.
- This process represents the world attempting to stabilize affected entities again.
- Elemental and otherworldly decay mechanics remain individually defined.

## Status Damage Calculation

- Offensive properties are fixed upon application.
- Applicable target-side defensive properties, DMG resistances and DMG vulnerabilities are calculated dynamically.
- Individual status mechanics may ignore corresponding DEF entirely.
- DMG vulnerability applies after DEF calculations.
- DMG vulnerability from multiple sources stacks additively, provisionally.
- Newly applied Puncture vulnerability affects subsequent DMG instances rather than the triggering attack.
- This application order may be reconsidered when establishing status combinations.

## Status Damage Resistance

- Status DMG resistance and Status Chance Resistance are separate mechanics.
- Status Chance Resistance affects the probability of applying a status.
- Status DMG resistance affects DMG dealt by the corresponding status.
- Status DMG resistance does not inherently prevent status applications.
- Status-specific resistance and immunity interactions are defined individually.

## General Combat DMG Display Settings

- Physical and magical DMG components are calculated independently.
- By default, corresponding simultaneous physical and magical DMG components are displayed as one combined DMG number.
- Players can toggle separate physical and magical DMG numbers.
- This option is always available in the settings.
- The player is introduced to this option when physical and magical Damage Categories are explained during gameplay.
- Accumulated Slash DoT DMG does not highlight individual critical contributions.