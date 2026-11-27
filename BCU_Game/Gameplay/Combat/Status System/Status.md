# Status System

## Design Philosophy

- Reward deliberate status application, weapon specialization, build diversity and cooperation between players.
- Allow individual statuses to remain useful without requiring group combinations.
- Provide meaningful progression toward six-stack payoffs and enhanced statuses.
- Encourage strategic preparation through group-exclusive status combinations.
- Differentiate statuses mechanically while maintaining consistent underlying rules.
- Allow party members to cooperate through shared status stack pools.
- Preserve individual damage attribution despite shared status accumulation.
- Connect gradual physical status decay to the world's attempt to stabilize affected entities.
- Prevent excessive scaling, recursive damage generation and unintended multiplayer exploitation.

---

## 1. Damage Categories & Damage Types

Damage Category and Damage Type are independent classifications.

### Damage Categories

- Physical Damage (PH).
- Magical Damage (MA).

The Damage Category determines the corresponding defensive attribute used to mitigate incoming DMG.

- Physical DMG uses Physical DEF.
- Magical DMG uses Magical DEF.
- Individual mechanics may partially or completely ignore corresponding DEF.

See [[Damage Calculation]].

### Status Families

#### Physical

|Status|Enhanced Status|
|---|---|
|[[Slash]]|Laceration|
|[[Impact]]|Fracture|
|[[Puncture]]|Breach|

#### Elemental

|Status|Sixth-Stack Payoff|
|---|---|
|[[Fire]]|Combustion|
|[[Ice]]|Freeze|
|[[Lightning]]|Lightning Discharge|
|[[Poison]]|Poisonous Strikes|

#### Otherworldly

- [[Instability]]
- [[Coptering]]

Otherworldly statuses are currently excluded from universal status combinations.

Their compatibility with universal status mechanics must be determined individually.

### Damage Classification

- Physical statuses can originate from physical or magical DMG.
- Elemental statuses can originate from physical or magical DMG.
- Magic is not inherently elemental.
- Physical DMG is not restricted to physical status types.
- Every attack and ability defines its own damage composition.

|Damage Component|Damage Category|Damage Type|
|---|---|---|
|Physical Slash|Physical|Slash|
|Magical Slash|Magical|Slash|
|Physical Impact|Physical|Impact|
|Magical Impact|Magical|Impact|
|Physical Puncture|Physical|Puncture|
|Magical Puncture|Magical|Puncture|
|Physical Fire|Physical|Fire|
|Magical Fire|Magical|Fire|
|Physical Poison|Physical|Poison|
|Magical Poison|Magical|Poison|

---

## 2. Individual Status Chances

Every applicable Damage Type within an attack or ability possesses its own Status Chance.

### Universal Rules

- Each Damage Type rolls independently.
- Multiple different statuses can be applied simultaneously.
- Physical and magical variants of the same Damage Type share its Status Chance roll.
- There is no universal restriction on how many different statuses may be applied through one hit.
- Status Chances can be individually adjusted for each attack, ability and damage instance.

### Example

|Damage Type|PH DMG|MA DMG|Total DMG|Base Status Chance|
|---|--:|--:|--:|--:|
|Impact|70|30|100|40%|
|Slash|50|0|50|20%|
|Fire|10|40|50|10%|
|Total|130|70|200|70%|

- The attack independently rolls Impact, Slash and Fire.
- It can apply all three statuses, two statuses, one status or no status.
- Combined Status Chance represents the sum of individual Status Chances rather than the probability of applying at least one status.

---

## 3. Base & Final Status Chance

Status Chance modifiers are differentiated through:

- Base Status Chance % (BC%).
- Final Status Chance % (FC%).

### Base Status Chance %

BC% increases individual base Status Chances proportionally.

**Modified Base Chance = Original Base Chance × (1 + BC Modifier)**

### Example — +50% BC

|Damage Type|Original Chance|Modified Chance|
|---|--:|--:|
|Impact|40%|60%|
|Slash|20%|30%|
|Fire|10%|15%|
|Total|70%|105%|

### Final Status Chance %

The proposed implementation adds percentage points to the combined Status Chance and distributes them proportionally across individual Damage Types.

### Proposed Example — +50% FC

|Damage Type|Original Chance|Modified Chance|
|---|--:|--:|
|Impact|40%|68.57%|
|Slash|20%|34.29%|
|Fire|10%|17.14%|
|Total|70%|120%|

The proportional FC distribution and exact interaction between BC% and FC% remain undecided.

---

## 4. Status Chance Above 100%

- Individual Status Chances can exceed 100%.
- Every complete 100% guarantees one stack.
- The remaining percentage represents the probability of applying an additional stack.
- This calculation applies independently to each Damage Type.

|Individual Status Chance|Guaranteed Stacks|Additional Stack Chance|
|---|--:|--:|
|70%|0|70%|
|100%|1|0%|
|115%|1|15%|
|150%|1|50%|
|200%|2|0%|
|245%|2|45%|

- A combined Status Chance exceeding 100% does not necessarily guarantee a status application.
- Stacks guaranteed through Status Chance remain part of the ordinary Status Chance system.
- These are distinct from explicitly guaranteed direct status applications.
- Status Chance Resistance remains applicable to ordinary Status Chance calculations.

---

## 5. Physical & Magical Status Applications

- Physical and magical variants apply the same underlying status.
- Each ordinarily applied stack retains one corresponding Damage Category.
- Hybrid physical-magical stacks do not exist under ordinary application rules.
- Both variants contribute equally toward status thresholds.
- Different party members can contribute different Damage Categories to the same status pool.

### Damage Category Determination

- Each successfully applied stack determines its Damage Category independently.
- The probability is proportional to the originating attack's physical and magical damage distribution for that specific Damage Type.
- Only DMG belonging to the relevant Damage Type is considered.
- Damage distribution is calculated before enemy defenses.
- Multiple stacks originating from the same attack may have different Damage Categories.

### Example

An attack deals:

- 70 Physical Impact DMG.
- 30 Magical Impact DMG.

Each successfully applied Impact stack independently has:

- 70% probability of becoming Physical Impact.
- 30% probability of becoming Magical Impact.

Different Damage Types determine their categories independently.

### Scripted Applications

Guaranteed applications and spreading effects may inherit existing Damage Categories rather than performing an ordinary category roll.

The exact category assignment of newly generated stacks must be determined by the originating mechanic.

---

## 6. Party-Shared Status Stack Pools

### Fundamental Rule

All seven fundamental statuses use party-shared stack pools.

- [[Slash]]
- [[Impact]]
- [[Puncture]]
- [[Fire]]
- [[Ice]]
- [[Lightning]]
- [[Poison]]

Players belonging to the same party can contribute to each other's status stacks.

This replaces the previous exclusively player-specific status pool system.

### Pool Ownership

- Every party maintains its own status pools on every affected enemy.
- Each fundamental status has its own party-specific pool.
- All members of the party contribute to the same corresponding pool.
- Physical and magical variants share the same pool.
- The maximum stack count applies to the shared pool, not individually to each party member.
- Different parties maintain independent pools.
- Solo players maintain independent personal pools.
- Non-allied players cannot contribute to another party's pools.

Status ownership and damage attribution are separate concepts.

### Example — Allied Players

- Player A applies four Slash stacks.
- Player B applies two Slash stacks.
- Both players belong to the same party.

The party reaches six Slash stacks and activates Laceration.

### Example — Non-Allied Players

- Player A applies four Slash stacks.
- Player B applies two Slash stacks.
- The players do not belong to the same party.

Neither pool reaches six stacks.

Laceration does not activate.

### Allied Stack Interaction

Party members can:

- Add stacks to the shared pool.
- Reach stack thresholds together.
- Refresh ordinary shared pool timers.
- Replace existing stacks through FIFO.
- Contribute to completed and enhanced statuses.
- Participate in status combinations.

Individual status rules determine restrictions concerning completed sets, special timers, buffs and combination effects.

### Stored Stack Properties

Depending on the status, individual stacks retain:

- Original contributor.
- Damage Category.
- Original offensive DMG value.
- Critical strike result.
- Applicable Critical DMG multiplier.
- Status-specific effect properties.
- Duration determined upon application.
- Application order.
- Applicable contribution and damage attribution information.

Changes to the originating player's offensive attributes do not modify previously stored offensive properties.

### Shared Attribution

- Sharing a status pool does not duplicate its damage.
- Individual contributors retain credit for their contributions.
- Specialized effects may preserve proportional attribution across several contributors.
- Poison spreading is an established example of multi-contributor attribution.

### Otherworldly Statuses

The party-shared system is not automatically applied to Otherworldly statuses.

Their ownership rules must be established individually.

### Undecided Party Interactions

- Players joining a party while existing personal pools remain active.
- Players leaving a party while shared pools remain active.
- Pool behavior when parties disband.
- Companion ownership.
- Persistence of contributions after disconnecting or leaving the map.

See [[Party]], [[Multiplayer]] and [[Participation and Loot]].

---

## 7. Maximum Stacks & FIFO

All seven fundamental statuses build toward a six-stack threshold.

The threshold applies per party-specific pool or solo player's independent pool.

### Physical Status Progression

|Status|Enhanced Status|Required Stacks|Additional Enhanced Stacks|
|---|---|--:|---|
|[[Slash]]|Laceration|6|None|
|[[Impact]]|Fracture|6|0–6|
|[[Puncture]]|Breach|6|None|

### Elemental Status Progression

|Status|Sixth-Stack Payoff|
|---|---|
|[[Fire]]|Combustion|
|[[Ice]]|Freeze|
|[[Lightning]]|Lightning Discharge|
|[[Poison]]|Poisonous Strikes|

Elemental statuses retain their individually established full-stack mechanics.

### FIFO Replacement

First In, First Out (FIFO) determines ordinary replacement of eligible stacks.

- The oldest eligible stack is removed.
- The newest stack replaces it.
- Replacement occurs within the relevant shared or independent pool.
- A party member can replace a stack originally contributed by another party member.
- Replacement can change the physical and magical composition of the pool.
- Existing stack properties remain unchanged until removal.
- Removed stacks no longer contribute their stored properties.
- Replacement does not increase the maximum stack count.
- Status-specific enhancement, retention, replacement and consumption mechanics can define exceptions.

### FIFO Example

A party possesses six Slash stacks:

- Player A contributed the first four stacks.
- Player B contributed the last two stacks.

Player B applies another Slash stack.

- Player A's oldest eligible stack is removed.
- Player B's newest stack replaces it.
- The pool remains at six stacks.
- The remaining individual damage contributions are updated accordingly.

### FIFO Cleansing

- Partial Slash cleansing removes the oldest eligible stack first.
- Cleansing Poisonous Strikes removes the oldest three completed Poison stacks.
- Other statuses follow their individually established cleansing rules.
- FIFO does not universally override specialized cleansing mechanics.

---

## 8. Status Duration & Decay

### Shared Expiration Timer

- Each ordinary status pool generally maintains its own shared expiration timer.
- The provisional standard base duration is five seconds unless individual mechanics specify otherwise.
- Applying a new stack refreshes the entire relevant ordinary pool duration.
- The newest successfully applied stack determines the refreshed duration.
- A shorter newly applied duration can replace a longer remaining duration.
- Refreshing the timer does not recalculate existing stack properties.
- Any eligible party member can refresh the shared ordinary pool.
- Applying stacks does not refresh another party's independent pools.

### Physical Status Decay

All three physical statuses follow gradual stabilization.

- Physical status stacks do not ordinarily expire simultaneously.
- Expiration removes the oldest eligible stack or enhancement through FIFO.
- The expiration timer restarts after each decay step.
- Enhanced statuses gradually revert to their ordinary forms.
- The status disappears when no stacks remain.

### Physical Status Lifecycles

- Slash (1–5) → Laceration.
- Laceration → Slash (5–1) → No status.
- Impact (1–5) → Fracture (0–6).
- Fracture (6–0) → Impact (5–1) → No status.
- Puncture (1–5) → Breach.
- Breach → Puncture (5–1) → No status.

### Elemental & Otherworldly Decay

- Elemental and Otherworldly statuses retain their individually established duration and decay mechanics.
- Gradual physical-style decay is not automatically applied to these statuses.
- Special completed-set timers and combination timers follow individual rules.
- Ordinary timer refreshing does not automatically extend fixed-duration effects.

### Independent Timers

Statuses may possess multiple independent timers.

Examples include:

- Ordinary stack expiration.
- Status DMG ticks.
- Completed-set duration.
- Separate accumulating-set duration.
- Enhanced effects.
- Combination effects.
- Player buffs.

Lightning and Poison can maintain completed sets alongside independently accumulating sets.

The expiration of one set does not automatically remove another independent set.

### Lore

Gradual physical status decay represents the world attempting to stabilize affected entities again.

Continued status applications actively counteract this stabilization.

---

## 9. Status Damage Tick Timer

Damaging status pools that use damage over time generally maintain shared damage tick timers.

### General Rules

- Active stacks within the same damaging pool deal their accumulated DMG at scheduled ticks.
- Each stack retains its own individual damage properties.
- Applying new stacks does not ordinarily reset the damage tick timer.
- Refreshing the expiration timer does not ordinarily reset the damage tick timer.
- Newly applied stacks contribute to the next scheduled tick.
- Independent pools maintain independent damage tick timers.
- Each damaging status may possess its own predefined tick interval.
- Status-specific mechanics may define additional timers.

### Party-Shared Damage Ticks

- A shared damage tick may include contributions from several party members.
- Damage is calculated using the relevant stored properties.
- Individual contribution and aggro attribution remain preserved.
- Sharing a tick timer does not cause the same damage to be applied separately for every contributor.

### Established Slash Rules

- The initial tick occurs after the first tick interval has passed.
- Simultaneous expiration and damage ticks resolve damage before stack removal.
- Stored base DMG per tick remains constant throughout each stack's lifetime.
- Existing offensive properties remain unchanged.

See [[Slash]].

### Non-Ticking Statuses

Not every damaging status uses a DoT timer.

Examples include:

- Poison's application-triggered maximum HP DMG.
- Instantaneous status payoffs.
- Specific triggered combination effects.

Poison no longer possesses an ordinary DoT tick timer.

Individual elemental status notes determine their applicable timing rules.

---

## 10. Status Damage Calculation

### Fixed Offensive Properties

- Individual offensive properties are determined and stored upon application where applicable.
- Subsequent changes to the originating player's attributes do not modify existing stored properties.
- Shared pools preserve the individual offensive contributions of their members.
- 
### Damage Type Conversion

- DMG Resistance references the final Damage Type rather than its originating Damage Type.
- Converted DMG is affected by the resistance corresponding to its final Damage Type.
- Damage Type conversion does not inherently change its physical or magical Damage Category.
- Individual mechanics may explicitly define exceptions.

### Dynamic Target Properties

Applicable target-side properties are calculated dynamically:

- Current corresponding DEF.
- Current DMG vulnerability.
- Current status-specific DMG resistance.
- Current barrier properties.
- Other applicable target-side modifiers.

### Defense Interactions

- Physical status DMG ordinarily references current Physical DEF.
- Magical status DMG ordinarily references current Magical DEF.
- Status-specific DEF penetration can override ordinary calculations.
- Slash and Laceration provisionally ignore corresponding DEF entirely.
- Poison's maximum HP-based DMG is affected by corresponding DEF.
- Ignoring DEF does not automatically grant Stability Barrier penetration.

### Defense Reduction

Impact and Fracture reduce corresponding DEF.

- Percentage-based reduction is applied before flat reduction.
- Percentage reduction references original positive DEF.
- Percentage reduction has no effect on original DEF values of zero or below.
- Flat reduction can reduce DEF below zero.
- Negative DEF increases corresponding incoming DMG.
- The exact negative DEF calculation remains undecided.
- Impact and Fracture currently have no dedicated total DEF reduction cap.

See [[Impact]].

### DMG Vulnerability

Puncture and Breach increase incoming DMG of their corresponding Damage Category.

- DMG vulnerability is applied after DEF calculations.
- Vulnerability stacks additively with vulnerability from other sources.
- Puncture vulnerability provisionally affects direct DMG, DoT and other applicable corresponding status DMG.
- Existing DoT effects dynamically reference current vulnerability.
- Newly applied Puncture vulnerability provisionally affects subsequent damage instances rather than the triggering attack.
- This application order may be reconsidered when establishing status combinations.

See [[Puncture]].

### Maximum HP-Based DMG

Certain status effects deal damage based on the receiving enemy's maximum HP.

- Their individual mechanics determine the applicable percentage.
- Stored offensive values may modify the percentage.
- Diminishing returns may limit scaling efficiency.
- Maximum HP-based DMG does not automatically ignore resistances or barriers.
- Critical multipliers may apply when explicitly established.

Poison is the primary established example.

See [[Poison]].

### Multiplayer Aggregation

Enemy-wide defensive changes can benefit other players despite independent party ownership.

The aggregation of DEF reduction, DMG vulnerability and similar debuffs originating from several independent pools remains undecided.

---

## 11. Critical Status Damage

Damaging statuses can critically strike.

### Established General Principles

- Critical status damage can be stored within individual stacks.
- Critical stacks retain their applicable critical properties throughout their lifetime.
- Individual DoT ticks do not repeatedly roll for critical strikes.
- Critical and non-critical stacks can coexist within the same pool.
- Different party members can contribute different critical properties.
- Refreshing duration does not modify existing critical properties.
- Critical DMG must not be applied twice.
- Baseline Critical Chance should remain relatively low.

### Slash & Laceration

- Each stack independently rolls its critical strike upon application.
- Base DoT DMG references non-critical, pre-mitigation triggering DMG.
- Multiple applications originating from one attack roll independently.
- Applications to different enemies roll independently.
- Critical DMG remains fixed throughout the stack's lifetime.

### Impact & Fracture

- Impact stack strength is not increased by critical strikes.

### Puncture & Breach

- Puncture stack strength is fixed and is not increased by critical strikes.

### Poison

- Maximum HP-based Poison DMG can be multiplied by the applicable Critical DMG multiplier.
- This interaction remains subject to numerical testing.
- Critical properties must not be applied twice through stored DMG and the resulting HP DMG.
- The exact critical roll behavior of application-triggered Poison DMG remains undecided.

### Other Statuses

- The previous universal rule of inheriting the triggering attack's critical result is superseded for Slash.
- Elemental critical behavior follows the respective individual status notes.
- Newly generated combination damage requires explicitly defined critical properties.

See [[Critical Hits]].

---

## 12. Status Resistance & Vulnerability

Damage mitigation, Status Chance Resistance and Status DMG Resistance are separate mechanics.

### Damage Mitigation

- Physical DEF mitigates physical DMG.
- Magical DEF mitigates magical DMG.
- Individual status mechanics may override ordinary DEF calculations.

### Status Chance Resistance

Status Chance Resistance affects the probability of applying statuses.

It does not directly affect:

- Status DMG.
- Status duration.
- Status potency.
- Maximum stack count.

### General Status Chance Resistance

- Provides baseline resistance against ordinary Status Chance applications.
- Primarily intended for elites and bosses.
- Most ordinary enemies should have no general resistance.

### Individual Status Chance Resistance

- Overrides general resistance for a specific status.
- Allows entities to possess individual resistances or vulnerabilities.
- Ordinary enemies may possess individual resistance where appropriate.
- Physical and magical variants of the same status share its applicable Status Chance Resistance.

### Illustrative Example

|Enemy|General|Fire|Ice|Impact|
|---|--:|--:|--:|--:|
|Wolf|0%|—|—|—|
|Fire Elemental|0%|80%|−25%|—|
|Stone Golem|20%|—|—|60%|
|Boss|40%|—|—|—|

- A dash indicates that General Status Chance Resistance applies.
- Negative individual resistance remains a proposed representation of innate vulnerability.
- All values are illustrative.

### Status Chance Vulnerability

- Directly counteracts Status Chance Resistance.
- Can exceed existing resistance and increase effective incoming Status Chance.
- Distinct from DMG vulnerability.

**Effective Status Chance = Final Status Chance × (1 − Resistance + Vulnerability)**

### Example

Assuming 50% Final Status Chance:

|Resistance|Vulnerability|Effective Chance|
|--:|--:|--:|
|0%|0%|50%|
|30%|0%|35%|
|30%|20%|45%|
|30%|50%|60%|
|0%|50%|75%|

### Status DMG Resistance

- Reduces DMG originating from the corresponding status.
- Does not inherently prevent status applications.
- Applicable resistance is calculated dynamically when status DMG occurs.
- Guaranteed status applications do not inherently bypass Status DMG Resistance.

### Established Slash Interactions

- Slash-specific DMG Resistance is calculated dynamically every tick.
- 100% Slash DMG Resistance prevents Slash DMG but does not prevent stack accumulation.
- Resistance exceeding 100% does not cause Slash to heal the target.
- Complete Slash DMG Resistance does not prevent Laceration or combination eligibility.
- These immunity interactions remain subject to playtesting.

### Established Poison Interactions

- Poison DMG Resistance reduces applicable maximum HP-based Poison DMG.
- Poison spreading bypasses Status Chance Resistance.
- Poison spreading does not bypass Status DMG Resistance.
- Spread damage references the receiving enemy's applicable defensive properties.

Exact interactions with other statuses must be determined individually.

No additional universal elemental damage resistance layer has been established.

---

## 13. Guaranteed Status Applications

Certain weapon mechanics, abilities and effects directly apply predefined status stacks.

### Rules

Guaranteed direct applications do not perform ordinary Status Chance rolls.

They are unaffected by:

- Base Status Chance modifiers.
- Final Status Chance modifiers.
- General Status Chance Resistance.
- Individual Status Chance Resistance.
- Status Chance Vulnerability.

### Additional Rules

- Guaranteed applications apply the explicitly defined number of stacks.
- They cannot generate additional guaranteed stacks through Status Chance bonuses.
- Associated ordinary damage instances may perform separate Status Chance rolls where applicable.
- Guaranteed applications follow ordinary pool ownership and threshold rules unless explicitly stated otherwise.
- Guaranteed application does not inherently bypass DMG Resistance.
- Guaranteed application does not automatically produce an ordinary attack hit.
- Guaranteed application can trigger completed statuses or eligible combinations.

### Weapon-Specific Applications

- Weapon mechanics may directly apply statuses.
- The Shooting Morningstar's guaranteed defense-reduction applications are intended to integrate with Impact.
- Their exact Damage Categories and weapon-specific behavior must be established individually.

### Status-Specific Applications

Certain statuses and combinations can directly apply other status stacks.

Examples:

- Burn applications originating from Fire effects.
- Scripted combination applications.
- Poison spreading.

These applications use their individually defined damage, duration, ownership and targeting rules.

### Poison Spreading

- Applies three guaranteed Poison stacks to each eligible receiving enemy.
- Bypasses Status Chance Resistance.
- Preserves proportional contributor attribution.
- Follows ordinary threshold and overflow resolution.
- Uses a fresh Poison duration.

See [[Poison]].

---

## 14. Independent Status Rolls

Status Chances are independently calculated and rolled:

- Per damage instance.
- Per Damage Type.
- Per affected enemy.

### Multi-Hit Attacks

- Every individual damage instance performs its own applicable Status Chance rolls.
- Different hits of the same attack or ability can possess different Status Chances.
- Fast and multi-hit weapons can therefore be balanced individually.

### Area-of-Effect Attacks

- Every affected enemy independently rolls applicable Status Chances.
- Different enemies can receive different statuses and numbers of stacks.
- Slash stack critical rolls are also independent between affected enemies.

### Status Effect Activation Frequency

The number of applied stacks does not universally determine how often an effect activates.

Individual status effects may trigger:

- Per successful stack.
- Per successful hit.
- Per threshold reached.
- Per completed set.
- Per scheduled damage tick.
- Through another explicitly defined event.

### Poison Example

If one hit successfully applies three Poison stacks:

- Three stacks are added to the relevant pool.
- Eligible additional maximum HP DMG triggers only once for that hit.

Separate successful hits can each trigger the additional damage.

---

## 15. Status Damage Restrictions

Status DMG does not ordinarily behave as a direct attack hit.

### Recursive Status Applications

- Status DMG cannot apply additional statuses through ordinary Status Chance rolls by default.
- Explicitly defined specialized mechanics may override this rule.
- Scripted combination applications are distinct from automatic Status Chance rolls.
- Scripted spreading effects are also distinct from automatic Status Chance rolls.
- Poison's death-spreading mechanic is an intentional exception allowing further status applications.

### On-Hit Effects

Status DMG does not automatically trigger general on-hit effects, including:

- Life Steal.
- Stability recovery.
- Effects requiring direct attack hits.

Status-specific exceptions must be explicitly established.

### Player Death

- Existing statuses persist after their originating contributor dies.
- Stored damage, ownership and remaining duration are not removed or recalculated due to the contributor's death.
- The death of one party member does not automatically remove the party's shared status pools.
- Individual buff behavior after player death must be determined separately.

### Healing & Invulnerability

Established for Slash:

- Ordinary healing does not affect existing stacks.
- Explicit cleansing effects can remove stacks.
- Invulnerability prevents DMG but does not suspend ticking or decay.

Interactions with other statuses follow their individually established rules.

### Enemy Death

- Enemy death ordinarily ends active status effects on that enemy.
- Explicit death-triggered mechanics resolve according to their respective rules.
- Poison spreading transfers eligible stored stack properties to nearby enemies.
- Ordinary status damage does not automatically transfer to another enemy.

---

## 16. Stability Barrier Interactions

The general barrier system is documented in [[Stability Barrier System]].

Individual statuses follow their established barrier interactions.

### General Principles

- Ignoring ordinary DEF does not inherently bypass Stability Barriers.
- Stability Barriers can interact with both damage and interruption effects.
- Barrier protection is only required when the relevant effect would otherwise affect the protected entity.
- Individual mechanics determine whether status application, status damage or status payoff effects are prevented.
- Blocking an effect through barrier protection follows the general barrier cost rules.
- Barrier-specific bonus DMG does not automatically become HP DMG.
- Specialized combinations may introduce additional barrier interactions.

### Slash & Laceration

- Slash and Laceration damage Stability Barriers before HP.
- Slash does not inherently bypass Stability Barriers.

### Puncture & Breach

- Breach increases applicable incoming attack DMG against Stability Barriers.
- The additional barrier DMG applies regardless of the attacking player, weapon or Damage Category.
- Further Puncture applications are not required to benefit from the barrier bonus.
- Additional barrier-specific DMG cannot carry over into HP DMG when a barrier is destroyed.
- Breach's ordinary DMG vulnerability remains applicable.

### Lightning

- Stability Barriers can protect against Lightning's interruption effects.
- Barrier protection follows the established interruption-related barrier cost calculation.
- If an interruption would already be prevented by resistance, the barrier does not need to protect against it.
- Barrier destruction does not inherently cause an additional unrelated effect.
- Exact Lightning interactions follow [[Lightning]] and [[Stability Barrier System]].

### Poison

- Maximum HP-based Poison DMG does not inherently bypass Stability Barriers.
- Applicable barriers protect the receiving enemy against Poison DMG.
- Poison spreading can still apply stacks to barrier-protected enemies.
- Barrier protection does not automatically disqualify an enemy from receiving spreading Poison.
- Receiving enemies calculate their own applicable resistances and barrier interactions.
- Poison combinations may introduce specialized barrier interactions.

### Further Development

- Exact numerical Breach barrier DMG bonus.
- Status-specific barrier interactions not yet individually established.
- Combination-specific barrier effects.
- Further numerical testing of interruption-related barrier costs.

See [[Stability Barrier System]] and [[Stability Barrier]].

---

## 17. Multiplayer Ownership, Contribution & Aggro

### Pool Ownership

- Fundamental status pools belong to the relevant party or independent solo player.
- Allied party members contribute to shared pools.
- Independent parties cannot directly alter each other's ordinary pools.
- Non-allied solo players maintain independent pools.

### Individual Stack Contribution

- Individual stacks preserve their original contributor.
- Shared accumulation does not erase individual damage properties.
- Contributors can possess different offensive attributes.
- Contributors can possess different critical properties.
- Contributors can supply different Damage Categories.

### Damage Attribution

- Ordinary individual status contributions remain attributed to their original contributors.
- Status DMG contributes to enemy aggro like direct DMG.
- Damage originating from a shared status effect must not be duplicated across contributors.
- Shared pool ownership does not automatically grant equal damage credit to every party member.
- Specialized effects can define their own attribution rules.

### Example — Shared Slash Pool

A party's Slash damage tick deals:

|Contributor|Damage Contribution|
|---|--:|
|Player A|80|
|Player B|20|
|Total|100|

The enemy receives 100 damage.

- Player A receives credit for 80 damage.
- Player B receives credit for 20 damage.
- Uninvolved party members do not automatically receive part of the damage attribution.

### Combination Attribution

The previously established rule divides combination damage equally between two allied contributors.

This rule requires reconsideration under party-shared status pools because several players can now contribute to each completed status.

Individual combination attribution may require a separate calculation.

### Poison Spreading Attribution

Poison spreading explicitly preserves proportional stored damage contributions.

- Contributions are distributed according to their relevant stored Poison DMG.
- The number of contributors does not multiply the number of applied stacks.
- Spread stacks may preserve attribution from multiple contributors.
- Future spreading retains and recalculates those proportional contributions.
- Contributors represented through spread stacks can qualify for Poisonous Strikes.

### Buff Eligibility

Shared status accumulation does not automatically grant every status-specific buff to all party members.

Individual status effects define their eligible beneficiaries.

#### Poisonous Strikes

- Every player who contributed to the completed Poison set is eligible.
- Contributing at least one stack is sufficient.
- Party members without contributions do not automatically receive the effect.
- Eligibility is recalculated when a completed set is replaced.

#### Other Status Effects

Fire, Ice, Lightning and individual combinations retain their established beneficiary rules.

Their compatibility with shared accumulation requires consistency review.

### Allied Cooperation

Players can cooperate through:

- Shared status accumulation.
- Status combinations.
- DEF reduction.
- DMG vulnerability.
- Status Chance Vulnerability.
- Shared status thresholds.
- Individual and party buffs.
- Scripted spreading and status propagation.
- Other enemy-wide debuffs.

Aggregation and stacking rules for debuffs originating from independent parties remain undecided.

See [[Multiplayer]], [[Party]] and [[Participation and Loot]].

---

## 18. Status Combination System

### General Rules

- Only groups can trigger status combinations.
- Non-allied players cannot combine their statuses.
- Individual statuses remain useful during solo play.
- Allied players can contribute to shared fundamental status pools.
- Compatible completed sets are required.
- Physical statuses cannot combine with other physical statuses.
- Every physical status should possess a combination with every elemental status.
- Otherworldly statuses are currently excluded.

### Shared Pool Integration

- A completed set may contain contributions from multiple allied players.
- The party can collectively prepare compatible completed statuses.
- Different parties cannot use each other's completed sets.
- The exact requirement for distinct contributors when activating combinations must be reconsidered under shared stacking.

Party-shared accumulation does not automatically remove the established group-exclusive combination requirement.

### Physical Combination Requirements

|Physical Status|Required Enhanced Status|
|---|---|
|Slash|Laceration|
|Impact|Fracture (0–6)|
|Puncture|Breach|

- Ordinary physical status stacks cannot trigger combinations.
- Eligibility begins immediately upon reaching the enhanced state.
- Additional Fracture stacks are not required.
- Combinations retain the names of their originating physical statuses.

### Combination Activation

1. A status reaches its six-stack threshold.
2. Check for eligible combinations with compatible completed sets.
3. Physical statuses reach their enhanced state before participating in combinations.
4. If an eligible combination exists, activate it according to its individual rules.
5. Otherwise, resolve the ordinary sixth-stack behavior.
6. Statuses directly applied through combination effects may themselves build toward further completed sets.

Genuinely simultaneous events require a tie-breaking rule.

### Combination Priority

- Eligible physical statuses follow FIFO combination priority.
- The first physical status to reach its enhanced state receives priority.
- Other eligible physical statuses wait for their own combination opportunities.
- Waiting statuses retain their existing effects.
- Party members can influence priority through the order of their collective status applications.

### Group-Based Combination Limitations

- Each group can maintain only one active combination per physical status per enemy.
- One group can therefore maintain:
    - One Slash combination.
    - One Impact combination.
    - One Puncture combination.
- Different groups can maintain different combinations of the same physical status against the same enemy.
- The limitation is group-based rather than globally enemy-based.
- A global combination limit has not been established.
- Identical combinations originating from multiple groups require individual stacking rules.

### Example

|Physical Status|Group A|Group B|
|---|---|---|
|Slash|Frozen Wounds|Burned Wounds|
|Impact|Corrosion|Shatter|
|Puncture|Short Circuit|Internal Combustion|

All six different combinations could coexist against the same enemy, subject to their individual rules.

### Individual Combination Mechanics

The following mechanics are determined individually:

- Damage calculations.
- Scaling.
- Maximum duration.
- Maximum stacks.
- Stack consumption or preservation.
- Additional status applications.
- Status decay or suspended decay.
- Preservation of originating effects.
- Transition back into ordinary or enhanced statuses.
- Effects upon expiration.
- Effects upon enemy death.
- Spreading.
- Buff eligibility.
- Damage attribution.
- Stability Barrier interactions.

### Combination Damage Categories

- Combinations preserve the original Damage Categories of their contributing damage components.
- Physical components remain physical.
- Magical components remain magical.
- No additional Damage Category roll occurs solely because a combination is triggered.
- Individual components follow their applicable DEF and damage rules.
- Newly generated combination DMG must be defined individually.

### Natural Status Synergies

Natural synergies do not constitute actual status combinations.

Examples:

- Impact reduces DEF, improving applicable direct DMG.
- Puncture increases corresponding incoming DMG.
- Puncture can amplify Slash DoT.
- Attack Speed buffs may increase the frequency of successful Poison-applying hits.

These interactions can occur without reaching enhanced states or triggering group combinations.

---

## 19. Physical Status Overview

### Slash / Laceration

- Accumulating DoT.
- Individually calculated stack strength.
- Independent critical rolls.
- Provisionally ignores corresponding DEF entirely.
- Allied party members contribute to a shared Slash pool.
- Reaching six stacks transforms Slash into Laceration.
- Laceration preserves all six stacks.
- No additional standalone enhanced effect.
- No additional enhanced stacks.
- Enables Slash combinations.
- Gradual FIFO decay.
- Individual damage attribution remains preserved.

See [[Slash]].

### Impact / Fracture

- Individually calculated flat corresponding DEF reduction.
- Stack strength depends on non-critical, pre-mitigation triggering DMG and original corresponding enemy DEF.
- Higher triggering DMG produces stronger reduction.
- Higher original DEF produces weaker reduction.
- Allied party members contribute to a shared Impact pool.
- Reaching six stacks transforms Impact into Fracture (0).
- Fracture preserves six remembered flat reduction values.
- Fracture immediately grants 10% physical and 10% magical DEF reduction.
- Additional Fracture stacks replace remembered values through FIFO.
- Each enhanced stack adds 2.5% corresponding DEF reduction.
- Maximum of six enhanced Fracture stacks.
- During decay, enhanced stacks lose percentage reductions while preserving flat values.
- Fracture (0) decays directly into Impact (5).
- No dedicated total DEF reduction cap for now.
- Enables Impact combinations.

See [[Impact]].

### Puncture / Breach

- Each stack grants 2.5% corresponding DMG vulnerability.
- Individual stack strength is fixed.
- Allied party members contribute to a shared Puncture pool.
- Reaching six stacks transforms Puncture into Breach.
- Breach preserves all six vulnerability values.
- Maximum corresponding vulnerability from one ordinary completed pool is 15%.
- No additional enhanced stacks.
- Further applications replace remembered stacks through FIFO.
- Breach increases applicable incoming attack DMG against Stability Barriers.
- Additional barrier DMG cannot carry over into HP DMG.
- Enables Puncture combinations.
- Gradual FIFO decay.

See [[Puncture]].

---

## 20. Elemental Status Overview

Individual elemental status notes contain the detailed mechanics.

The following sections provide system-level summaries.

### Fire

- Six-stack threshold.
- Allied party members contribute to a shared Fire pool.
- Three stacks apply Burn.
- Burn possesses its own internal timer.
- Six stacks trigger Combustion unless a combination takes priority.
- Ordinary Combustion consumes Fire stacks.
- Combustion can apply Burn to affected enemies.
- Individual Fire rules determine Burn, Combustion, duration, cleansing and combination interactions.

See [[Fire]].

### Ice

- Six-stack threshold.
- Allied party members contribute to a shared Ice pool.
- Three stacks apply Slow.
- Six stacks trigger Freeze unless a combination takes priority.
- Freeze provides control and applicable critical vulnerability effects.
- Its detailed duration, extensions, resistance, cleansing and combination mechanics follow the individual Ice design.
- Shared accumulation must preserve established Freeze beneficiary rules unless explicitly revised.

See [[Ice]].

### Lightning

- Six-stack threshold.
- Allied party members contribute to a shared Lightning pool.
- Three stacks trigger an interruption effect.
- Six stacks trigger Lightning Discharge unless a combination takes priority.
- Lightning Discharge provides a stronger interruption and applicable Attack Speed and Animation Speed buffs.
- A completed set can remain available while a separate set accumulates.
- Completed-set timers cannot ordinarily be extended through further applications.
- A newly completed set replaces the previous completed set.
- Repeated Discharge buffs do not automatically stack their strength.
- Consuming a completed set does not inherently remove an independently granted buff.
- Cleansing removes the completed Lightning set entirely.
- If an independently accumulating set exists, its stack loss follows the individual Lightning cleansing rules.
- Stability Barriers can protect against Lightning interruptions.

See [[Lightning]].

### Poison

#### Identity

- Progressive infection.
- Continued offensive pressure.
- Maximum HP-based application damage.
- Death-triggered spreading.

#### Basic Progression

- Six-stack threshold.
- Allied party members contribute to a shared Poison pool.
- Poison does not deal conventional DoT.
- Successful Poison-applying hits trigger additional maximum HP-based DMG beginning at three stacks.
- The additional damage triggers once per successful hit, regardless of the number of stacks applied.
- No dedicated internal cooldown.

|Stacks|Base Maximum HP DMG|
|---|--:|
|1–2|0%|
|3|0.125%|
|4|0.250%|
|5|0.375%|
|6|0.500%|

#### Stored Damage Scaling

- Individual stacks retain stored offensive Poison DMG.
- Accumulated stored DMG increases the maximum HP DMG percentage.
- Scaling follows diminishing returns.
- Marginal scaling efficiency approaches zero as stored DMG increases.
- Stored DMG does not provide an additional flat damage component.
- Exact scaling formulas and limits remain undecided.

**Additional Poison DMG = Target Maximum HP × Effective Poison HP DMG Percentage**

#### Poisonous Strikes

- Activates at six stacks unless a combination takes priority.
- Fixed five-second duration.
- Cannot be extended through ordinary attacks or further Poison applications.
- References only the active completed set's stored DMG.
- Every contributing player becomes eligible.
- Non-contributing party members do not automatically receive its benefit.
- An independently accumulating second set can coexist.
- The two sets possess independent timers.
- The newest completed set replaces the previous set regardless of relative strength.
- Replacement starts a fresh five-second duration.

#### Expiration & Cleansing

- Natural expiration removes the entire completed six-stack set.
- Independently accumulating stacks remain unaffected by the completed set's natural expiration.
- Cleansing Poisonous Strikes reduces the completed set to three stacks through FIFO.
- The oldest three completed stacks are removed.
- Surviving stacks preserve their stored properties and contributor information.
- Integration of surviving cleansed stacks with an existing accumulating set remains undecided.

#### Spreading

- Occurs exclusively upon enemy death while an eligible completed Poison effect is active.
- Targets a maximum of three closest eligible enemies within a defined radius.
- Each receiving enemy obtains three guaranteed Poison stacks.
- Enemies already possessing six relevant Poison stacks are skipped.
- Spread stacks receive a fresh full duration.
- Spreading bypasses Status Chance Resistance.
- Spread applications follow ordinary threshold and overflow resolution.
- Each receiving enemy inherits half of the completed set's total stored Poison DMG.
- Each spread stack inherits one-sixth of the completed set's stored Poison DMG.
- Proportional contributor attribution is preserved.
- Spread contributors can qualify for Poisonous Strikes.
- Each independent party resolves its spreading separately.
- Receiving enemies calculate maximum HP DMG using their own maximum HP.
- Individual combinations may modify the spreading radius and other explicitly defined properties.

#### Critical Damage & Barriers

- Maximum HP-based Poison DMG can provisionally be multiplied by Critical DMG.
- Maximum HP-based Poison DMG is affected by corresponding DEF.
- Applicable Poison DMG Resistance remains effective.
- Stability Barriers protect against Poison's maximum HP DMG.
- Shielded enemies remain eligible for spreading.

See [[Poison]].

---

## 21. Status Combination Overview

### Elemental Combinations

|Statuses|Combination|
|---|---|
|Fire + Ice|[[Cool Combustion]]|
|Fire + Lightning|[[Arc Combustion]]|
|Fire + Poison|[[Toxic Combustion]]|
|Ice + Lightning|[[x Shattering Voltage]]|
|Ice + Poison|[[x Cryotoxicity]]|
|Lightning + Poison|[[x Neurotoxin]]|

### Slash Combinations

|Element|Combination|
|---|---|
|Fire|[[x Burned Wounds]]|
|Ice|[[x Frozen Wounds]]|
|Lightning|[[x Conductive Wounds]]|
|Poison|[[x Viral Wounds]]|

### Proposed Impact Combinations

|Element|Combination|Proposed Effect|
|---|---|---|
|Fire|[[x Thermal Fracture]]|Heat weakens damaged defensive structures, amplifying flat DEF reduction.|
|Ice|[[x Shatter]]|Brittle defensive structures break upon receiving powerful hits, increasing percentage-based DEF reduction.|
|Lightning|[[x Disruption]]|Interferes with stabilization, slowing defensive restoration and status decay.|
|Poison|[[x Corrosion]]|Gradually increases physical and magical DEF reduction throughout its duration.|

### Proposed Puncture Combinations

|Element|Combination|Proposed Effect|
|---|---|---|
|Fire|[[x Internal Combustion]]|Fire penetrates existing openings, causing additional bursts of internal DMG when attacked.|
|Ice|[[x Frost Penetration]]|Cold penetrates the entity, reducing attack and movement speed.|
|Lightning|[[x Short Circuit]]|Enhances Stability Barrier destruction through additional electrical DMG.|
|Poison|[[x Toxic Infiltration]]|Poison penetrates defensive layers, progressively increasing incoming DMG vulnerability.|

All proposed Impact and Puncture combinations require individual development.

Names and effects are not finalized.

### Combination Design Philosophy

- Slash combinations primarily manipulate wounds and DoT.
- Impact combinations primarily manipulate defensive structures and DEF.
- Puncture combinations primarily exploit openings, DMG vulnerability and Stability Barriers.
- Poison combinations should preserve Poison's infection and spreading identity.

### Poison Combination Revision

The following combinations require review following the redesign of Poison:

- [[x Cryotoxicity]]
- [[x Neurotoxin]]
- [[x Viral Wounds]]
- [[x Corrosion]]
- [[x Toxic Infiltration]]

Previous mechanics relying on conventional Poison DoT are no longer automatically valid.

Poison combinations should ordinarily spread base Poison stacks rather than directly duplicating the entire combination.

Individual combinations determine their exact spreading properties.

### Party-Shared Combination Revision

All existing combinations must be reviewed for:

- Shared stack accumulation.
- Contributor eligibility.
- Contributor-specific damage properties.
- Combination damage attribution.
- Completed-set consumption.
- Buff ownership.
- Party membership changes.

---

## 22. Frozen Wounds & Freeze Interaction

- [[x Frozen Wounds]] replaces the ordinary Freeze critical vulnerability bonus.
- Ordinary Freeze and Frozen Wounds are mutually exclusive as critical vulnerability effects.
- Their Critical Chance bonuses do not stack.
- Their Critical DMG bonuses do not stack.
- Frozen Wounds provides its own critical vulnerability bonus.
- Applicable Freeze mechanics are preserved.
- Exact bonus values remain undecided.

The individual combination and Ice notes determine further interactions.

---

## 23. Status Visibility & Combat Display

### Solo

- Players see their own status stacks and status effects.
- Completed and enhanced statuses are clearly highlighted.
- Independently accumulating and completed sets should be distinguishable.

### Party

- Players see the shared stack count of their party's relevant pools.
- Allied contributions are reflected in the shared stack progression.
- Completed and enhanced statuses are highlighted for eligible party members.
- Players can recognize potential combination opportunities.
- Contributor-specific eligibility should be communicated where relevant.

The exact representation of individual stack contributions within shared pools remains undecided.

### Outside the Party

- Players see status visuals and applicable payoff effects.
- Non-allied individual or party stack counts are not ordinarily displayed.
- Different parties retain independent status effects.
- Certain allied interactions may involve [[Wave Projection]].

See [[Multiplayer]] and [[Companions]].

### Physical Status Representation

- Laceration and Breach are displayed as single enhanced statuses.
- Fracture displays its current enhanced stack count.
- Remembered flat Impact values do not count as displayed Fracture stacks.
- Puncture uses grayish colors for physical stacks and pinkish colors for magical stacks.
- Exact visual representation of individual Damage Categories across all statuses remains undecided.

### Elemental Status Representation

Individual elemental statuses require distinguishable visuals for:

- Ordinary accumulating stacks.
- Completed sets.
- Active payoff effects.
- Combination availability.
- Separate accumulating sets where applicable.

### Poison Representation

Poison visuals should communicate:

- Current Poison stack progression.
- Active Poisonous Strikes.
- Separate accumulating stacks.
- Contributor-specific eligibility.
- Infection spreading to nearby enemies.
- Relevant independent party effects.

Exact visuals remain undecided.

### General Combat DMG Display Settings

- Physical and magical components are calculated independently.
- By default, corresponding simultaneous physical and magical DMG components are displayed as one combined DMG number.
- Players can toggle separate physical and magical DMG numbers.
- The option is always accessible in the settings.
- Players are introduced to this option when Damage Categories are explained during gameplay.
- Accumulated Slash DoT DMG does not highlight individual critical contributions.

---

## 24. Experimental Arcade — Recursive Slash

A future Experimental Arcade test body allows experimentation with recursive status applications.

### Concept

- An experimental version of Slash can apply additional Slash stacks through its own damage ticks.
- The experiment can be activated through a dedicated button.

### Testing Properties

- Predetermined damage values.
- Predetermined Status Chance.
- Predictable initial conditions.
- Observation of recursive stack generation.
- FIFO stack replacement.
- Shared duration refreshing.
- Shared damage tick timing.

This is an explicit experimental exception to the universal rule preventing ordinary status DMG from applying additional statuses.

It is not intended to become a default gameplay mechanic.

---

## 25. Remaining Design & Implementation Questions

### Status Chance

- Finalize FC% distribution.
- Finalize calculation order between BC% and FC%.
- Determine how multiple BC% and FC% modifiers stack.
- Determine whether bonuses can grant Status Chance to Damage Types with zero base Status Chance.

### Status Resistance

- Minimum effective Status Chance.
- Maximum Status Chance Resistance.
- Stacking of multiple Status Chance Vulnerability sources.
- Final implementation of innate negative resistance.
- Player access to Status Chance Resistance.
- Individual status DMG Resistance formulas and limitations.

### Damage Calculation

- Individual status damage coefficients.
- Exact Impact flat DEF reduction formula.
- Exact negative DEF calculation.
- Interaction with General Defense.
- Final Slash DEF penetration after playtesting.
- Remaining elemental critical application behavior.
- Critical properties of guaranteed damaging stacks without originating DMG.
- Damage rounding and minimum damage.
- Potential limitations on accumulated DEF reduction and DMG vulnerability.
- Representative player DMG and enemy HP ranges throughout progression.

### Stack & Timer Resolution

- Ordering of genuinely simultaneous applications.
- Resolution of full-stack thresholds when multiple stacks are applied through one hit.
- Whether individual threshold-triggered damage references pre-application or post-application values.
- Interaction between incomplete sets, completed sets and individual effect timers.
- Status Duration modifiers.
- Potential tick-frequency modifiers for applicable statuses.
- Cleansing interactions beyond established individual status rules.

### Party-Shared Status Pools

- What happens to personal pools when a player joins a party?
- What happens to existing contributions when a player leaves a party?
- What happens to shared pools when a party disbands?
- Can former members retain attribution for previously contributed damage?
- How are existing personal pools integrated when several players form a party?
- How do companion applications contribute?
- How are simultaneous applications from several party members ordered?
- How are party-specific pools represented in the interface?
- How do active effects behave when party membership changes?

### Multiplayer

- Aggregation of DEF reduction and DMG vulnerability from independent pools.
- Companion status ownership.
- Persistence after disconnecting or leaving the map.
- Status damage contribution toward kill credit, experience and loot eligibility.
- Combination ownership when groups change.
- Damage attribution for combinations involving several contributors.
- Whether one group member can independently supply both combination components while belonging to a group.
- Whether combinations require distinct contributing party members.

### Elemental Status Consistency Review

- Update Fire ownership and completed-set interactions for shared stacking.
- Update Ice ownership and Freeze extension behavior for shared stacking.
- Update Lightning ownership and buff interactions for shared stacking.
- Verify individual elemental cleansing rules under shared ownership.
- Verify existing buff eligibility rules where the initiating set contains multiple contributors.
- Resolve remaining elemental numerical balancing questions.

### Poison

- Exact stored Poison DMG calculation.
- Exact diminishing-return scaling formula.
- Initial scaling efficiency.
- Maximum attainable HP DMG percentages.
- Whether separate milestone scaling curves are required.
- Spreading radius.
- Whether threshold-crossing hits use pre-application or post-application stack values.
- Whether the triggering hit's stored DMG contributes to its own additional Poison DMG.
- Whether guaranteed non-hit applications independently trigger additional HP DMG.
- Exact critical roll behavior.
- Physical and magical Damage Category distribution within spread stacks.
- Exact attribution of application-triggered HP DMG.
- Eligibility of newly contributing players during an existing Poisonous Strikes effect.
- Integration of surviving cleansed stacks with an independently accumulating set.
- Duration of surviving stacks after cleansing.
- Cleansing behavior for incomplete Poison sets.
- Target eligibility when an enemy possesses both a completed and accumulating Poison set.
- Numerical testing against elites and bosses.

See [[Poison]].

### Status Combinations

- Exact simultaneous activation priority.
- Resolution of multiple eligible combinations without consuming the same completed set twice.
- Identical combinations originating from different groups.
- Whether active combinations can be overridden.
- Whether upcoming combinations can be prepared while another combination is active.
- How combination priority interacts with statuses already participating in combinations.
- Whether a global combination limit becomes necessary.
- Individual combination durations, scaling, damage calculations and stack retention.
- Finalize the eight proposed Impact and Puncture combinations.
- Review all Poison combinations following the removal of conventional Poison DoT.
- Establish individual combination spreading mechanics.
- Revise combination attribution for party-shared pools.

### Stability Barriers

- Remaining individual status barrier interactions.
- Exact Breach barrier DMG bonus.
- Further balancing of barrier interruption costs.
- Combination-specific barrier effects.
- Testing of maximum HP-based damage against Stability Barriers.

The general barrier mechanics are documented in [[Stability Barrier System]].

### Otherworldly Statuses

- Determine which universal rules apply to Instability and Coptering.
- Establish individual exceptions where necessary.
- Determine whether any Otherworldly statuses use shared pools.

### Visual Representation

- Final physical and magical stack indicators.
- Shared party stack indicators.
- Enhanced status visuals.
- Critical stack indicators where appropriate.
- Completed and accumulating set indicators.
- Contributor-specific buff eligibility.
- Display of simultaneous ticks from multiple contributors.
- Display of individual and combined Status Chances.
- Visibility of enemy resistances.
- Poison spreading visuals.
- Visual representation of combinations originating from different groups.

---

## 26. Superseded System Mechanics

The following previous system rules are no longer valid.

### Individual Status Pools Within Parties

Previous:

- Every player maintained exclusively independent fundamental status pools.
- Party members could not collectively reach a six-stack threshold.
- Ordinary applications could not refresh or replace another party member's stacks.

Current:

- Allied party members contribute to shared fundamental status pools.
- Shared pools collectively reach stack thresholds.
- Eligible allied applications can refresh or replace stacks within the same ordinary pool.
- Individual damage properties and contribution attribution remain preserved.
- Independent parties and solo players retain separate pools.

### Previous Poison Mechanics

Removed:

- Conventional Poison DoT.
- Three-stack DoT totaling 5% maximum HP.
- Six-stack DoT totaling 15% maximum HP.
- Initiator-exclusive 1% maximum HP DMG through ordinary attacks.
- Automatic 0.5% maximum HP DMG bonus for non-contributing party members.
- Poisonous Strikes duration extensions through ordinary attacks.
- Diminishing duration-extension sequence.
- Spreading immediately upon reaching six stacks.
- Unlimited spreading targets.
- Additive flat DMG from stored Poison DMG.
- Fixed stored DMG multipliers of 0.00005 and 0.0001.

Current:

- Application-triggered maximum HP-based DMG.
- Progressive three-to-six-stack damage percentages.
- Stored DMG increases the maximum HP DMG percentage through diminishing returns.
- Contributor-specific Poisonous Strikes eligibility.
- Fixed five-second completed-set duration.
- Independent accumulating and completed sets.
- Death-exclusive spreading.
- Three guaranteed spreading stacks per eligible target.
- Maximum of three closest eligible targets.
- Proportional spreading strength and contributor attribution.

See [[Poison]].

---

## 27. Design Status

### Mechanically Established — Universal System

- Damage Categories and Damage Types.
- Individual Status Chance rolls.
- Status Chance above 100%.
- Physical and magical stack categorization.
- Party-shared fundamental status pools.
- Independent pools between non-allied players and parties.
- Individual stored stack properties.
- Individual contributor attribution.
- Six-stack progression.
- FIFO replacement.
- Shared ordinary expiration timers.
- Gradual physical status decay.
- Guaranteed direct applications.
- Status Chance Resistance and Vulnerability.
- Status DMG Resistance as a separate mechanic.
- Group-exclusive status combinations.
- Group-based physical combination limitations.
- FIFO physical combination priority.
- General combat DMG display settings.
- Status-specific exceptions to ordinary universal mechanics.

### Individual Physical Statuses

|Status|Design Status|
|---|---|
|[[Slash]]|Core mechanics established.|
|[[Impact]]|Core mechanics established.|
|[[Puncture]]|Core mechanics established.|

Remaining questions primarily concern numerical balancing, party-shared consistency, visual representation, Stability Barriers and individual combinations.

### Individual Elemental Statuses

|Status|Design Status|
|---|---|
|[[Fire]]|Individual design documented; shared-pool consistency review required.|
|[[Ice]]|Individual design documented; shared-pool consistency review required.|
|[[Lightning]]|Individual design documented; shared-pool consistency review required.|
|[[Poison]]|Core redesign established; numerical balancing and edge cases remain.|

### Stability Barriers

- General system documented in [[Stability Barrier System]].
- Individual status and combination interactions require continued review.
- Numerical balancing remains necessary.

### Further Development

- Apply party-shared ownership consistently across individual status notes.
- Resolve party membership and ownership edge cases.
- Finalize individual status combinations.
- Reconsider existing Poison combinations.
- Review weapon damage compositions and applicable statuses.
- Establish final numerical balancing through testing.
- Develop status visuals and combat feedback.
- Implement status systems and test multiplayer interactions.

---

## Related Notes

### Combat Systems

- [[Combat]]
- [[Damage Calculation]]
- [[Critical Hits]]
- [[Normal Attacks]]
- [[Attack Principles]]
- [[Ability Principles]]
- [[Status Infusion]]
- [[Stability Barrier System]]
- [[Stability Barrier]]

### Physical Statuses

- [[Slash]]
- [[Impact]]
- [[Puncture]]

### Elemental Statuses

- [[Fire]]
- [[Ice]]
- [[Lightning]]
- [[Poison]]

### Otherworldly Statuses

- [[Instability]]
- [[Coptering]]

### Multiplayer

- [[Multiplayer]]
- [[Party]]
- [[Participation and Loot]]
- [[Companions]]

### Status Combinations

- [[Cool Combustion]]
- [[Arc Combustion]]
- [[Toxic Combustion]]
- [[x Shattering Voltage]]
- [[x Cryotoxicity]]
- [[x Neurotoxin]]
- [[x Burned Wounds]]
- [[x Frozen Wounds]]
- [[x Conductive Wounds]]
- [[x Viral Wounds]]
- [[x Thermal Fracture]]
- [[x Shatter]]
- [[x Disruption]]
- [[x Corrosion]]
- [[x Internal Combustion]]
- [[x Frost Penetration]]
- [[x Short Circuit]]
- [[x Toxic Infiltration]]