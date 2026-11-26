# Status System

## Design Philosophy

- Reward deliberate status application, weapon specialization, build diversity and cooperation between players.
    
- Allow individual statuses to remain useful without requiring group combinations.
    
- Provide meaningful progression toward six-stack payoffs and enhanced statuses.
    
- Encourage strategic preparation through group-exclusive status combinations.
    
- Differentiate statuses mechanically while maintaining consistent underlying rules.
    
- Connect gradual physical status decay to the world's attempt to stabilize affected entities.
    

---

## 1. Damage Categories & Damage Types

Damage Category and Damage Type are independent classifications.

### Damage Categories

- **Physical Damage (PH)**
    
- **Magical Damage (MA)**
    

The Damage Category determines the corresponding defensive attribute used to mitigate incoming DMG.

- Physical DMG uses Physical DEF.
    
- Magical DMG uses Magical DEF.
    
- Individual mechanics may partially or completely ignore DEF.
    

See [[Damage Calculation]].

### Status Families

#### Physical

|Status|Enhanced Status|
|---|---|
|[[Slash]]|Laceration|
|[[Impact]]|Fracture|
|[[Puncture]]|Breach|

#### Elemental

- [[Fire]]
    
- [[Ice]]
    
- [[Lightning]]
    
- [[Poison]]
    

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
|---|---|---|---|---|
|Impact|70|30|100|40%|
|Slash|50|0|50|20%|
|Fire|10|40|50|10%|
|**Total**|**130**|**70**|**200**|**70%**|

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

**Formula:**

Modified Base Chance = Original Base Chance × (1 + BC Modifier)

### Example — +50% BC

|Damage Type|Original Chance|Modified Chance|
|---|---|---|
|Impact|40%|60%|
|Slash|20%|30%|
|Fire|10%|15%|
|**Total**|**70%**|**105%**|

### Final Status Chance %

The proposed implementation adds percentage points to the combined Status Chance and distributes them proportionally across individual Damage Types.

### Proposed Example — +50% FC

|Damage Type|Original Chance|Modified Chance|
|---|---|---|
|Impact|40%|68.57%|
|Slash|20%|34.29%|
|Fire|10%|17.14%|
|**Total**|**70%**|**120%**|

The proportional FC distribution and exact interaction between BC% and FC% remain undecided.

---

## 4. Status Chance Above 100%

- Individual Status Chances can exceed 100%.
    
- Every complete 100% guarantees one stack.
    
- The remaining percentage represents the probability of applying an additional stack.
    
- This calculation applies independently to each Damage Type.
    

|Individual Status Chance|Guaranteed Stacks|Additional Stack Chance|
|---|---|---|
|70%|0|70%|
|100%|1|0%|
|115%|1|15%|
|150%|1|50%|
|200%|2|0%|
|245%|2|45%|

- A combined Status Chance exceeding 100% does not necessarily guarantee a status application.
    
- Stacks guaranteed through Status Chance remain part of the ordinary Status Chance system.
    
- These are distinct from explicitly guaranteed direct status applications.
    

---

## 5. Physical & Magical Status Applications

- Physical and magical variants apply the same underlying status.
    
- Each successfully applied stack retains one corresponding Damage Category.
    
- Hybrid stacks do not exist.
    
- Both variants contribute equally toward status thresholds.
    

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

---

## 6. Player-Specific Status Stack Pools

- Every player maintains separate status pools on every affected enemy.
    
- Each status has its own player-specific pool.
    
- Physical and magical variants share the same pool.
    
- Both variants share the maximum stack count within that pool.
    
- Other players cannot replace, refresh or extend a player's stacks through ordinary applications.
    
- Individual stacks from different players do not collectively count toward one player's completed set.
    
- Allied players can cooperate through eligible status combinations.
    

### Example

- Player A applies 4 Slash stacks.
    
- Player B applies 3 Slash stacks.
    
- Neither player reaches Laceration.
    
- The combined total of 7 stacks does not activate a completed six-stack set.
    

### Stored Stack Properties

Depending on the status, individual stacks retain:

- Original owner.
    
- Damage Category.
    
- Original offensive DMG value.
    
- Critical strike result.
    
- Applicable Critical DMG multiplier.
    
- Status-specific effect properties.
    
- Duration determined upon application.
    
- Application order.
    

Changes to the originating player's offensive attributes do not modify stored properties.

---

## 7. Maximum Stacks & FIFO

All seven fundamental statuses build toward a six-stack threshold.

### Physical Status Progression

|Status|Enhanced Status|Required Stacks|Additional Enhanced Stacks|
|---|---|---|---|
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

First In, First Out (FIFO) determines ordinary replacement of completed stack pools.

- The oldest eligible stack is removed.
    
- The newest stack replaces it.
    
- Replacement occurs within the originating player's own pool.
    
- Replacement can change the physical and magical composition of the pool.
    
- Existing stack properties remain unchanged until removal.
    
- Replacement does not increase the maximum stack count.
    
- Status-specific enhancement, retention and consumption mechanics can define exceptions.
    

### FIFO Cleansing

- Partial Slash cleansing removes the oldest stack first.
    
- Other status-specific cleansing interactions remain subject to individual rules.
    

---

## 8. Status Duration & Decay

### Shared Expiration Timer

- Each player-specific status pool maintains its own shared expiration timer.
    
- The provisional standard base duration is 5 seconds unless individual mechanics specify otherwise.
    
- Applying a new stack refreshes the originating player's entire pool duration.
    
- The newest stack determines the refreshed duration.
    
- A shorter newly applied duration can replace a longer remaining duration.
    
- Refreshing the timer does not recalculate existing stack properties.
    
- Applying stacks does not refresh other players' pools.
    

### Physical Status Decay

All three physical statuses follow gradual stabilization.

- Physical status stacks do not expire simultaneously.
    
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

- Elemental and otherworldly statuses retain their individually established duration and decay mechanics.
    
- Gradual physical-style decay is not automatically applied to these statuses.
    
- Special completed-set timers and combination timers follow individual rules.
    

### Lore

Gradual physical status decay represents the world attempting to stabilize the affected entity again.

Continued status applications actively counteract this stabilization.

---

## 9. Status Damage Tick Timer

Damaging status pools generally maintain shared damage tick timers.

### General Rules

- All active stacks within the same pool deal their accumulated DMG simultaneously.
    
- Each stack retains its own individual damage properties.
    
- Applying new stacks does not reset the damage tick timer.
    
- Refreshing the expiration timer does not reset the damage tick timer.
    
- Newly applied stacks contribute to the next scheduled tick.
    
- Different players maintain independent damage tick timers.
    
- Each damaging status may possess its own predefined tick interval.
    
- Status-specific mechanics may define additional timers.
    

### Established Slash Rules

- The initial tick occurs after the first tick interval has passed.
    
- Simultaneous expiration and damage ticks resolve damage before stack removal.
    
- Stored base DMG per tick remains constant throughout each stack's lifetime.
    
- Existing offensive properties remain unchanged.
    
- See [[Slash]] for further details.
    

Equivalent timing and damage rules for elemental statuses will be confirmed during their individual reviews.

---

## 10. Status Damage Calculation

### Fixed Offensive Properties

- Individual offensive properties are determined and stored upon application.
    
- Subsequent changes to the originating player's attributes do not modify existing stacks.
    

### Dynamic Target Properties

Applicable target-side properties are calculated dynamically:

- Current corresponding DEF.
    
- Current DMG vulnerability.
    
- Current status-specific DMG resistance.
    
- Other applicable target-side modifiers.
    

### Defense Interactions

- Physical status DMG ordinarily references current physical DEF.
    
- Magical status DMG ordinarily references current magical DEF.
    
- Status-specific DEF penetration can override ordinary calculations.
    
- Slash and Laceration provisionally ignore corresponding DEF entirely.
    
- Impact and Fracture therefore do not directly amplify Slash through DEF reduction.
    

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
    
- Puncture vulnerability provisionally affects direct DMG, DoT and other corresponding status DMG.
    
- Existing DoT effects dynamically reference current vulnerability.
    
- Newly applied Puncture vulnerability provisionally affects subsequent damage instances rather than the triggering attack.
    
- This application order may be reconsidered when establishing status combinations.
    

See [[Puncture]].

### Multiplayer Aggregation

Enemy-wide defensive changes can benefit other players despite individual status ownership.

The aggregation of DEF reduction, DMG vulnerability and similar debuffs from multiple players remains undecided.

---

## 11. Critical Status Damage

Damaging statuses can critically strike.

### Established General Principles

- Critical status damage can be stored within individual stacks.
    
- Critical stacks retain their critical properties throughout their lifetime.
    
- Individual DoT ticks do not repeatedly roll for critical strikes.
    
- Critical and non-critical stacks can coexist within the same pool.
    
- Refreshing duration does not modify existing critical properties.
    
- Critical DMG must not be applied twice.
    
- Baseline Critical Chance should remain relatively low.
    

### Slash & Laceration

- Each stack independently rolls its critical strike upon application.
    
- Base DoT DMG references non-critical, pre-mitigation triggering DMG.
    
- Multiple applications originating from one attack roll independently.
    
- Applications to different enemies roll independently.
    
- Critical DMG remains fixed throughout the stack's lifetime.
    

### Other Statuses

- The previous universal rule of inheriting the triggering attack's critical result is superseded for Slash.
    
- Critical application behavior for elemental statuses will be confirmed individually.
    
- Impact stack strength is not increased by critical strikes.
    
- Puncture stack strength is fixed and is not increased by critical strikes.
    

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
|---|---|---|---|---|
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
    

**Formula:**

Effective Status Chance = Final Status Chance × (1 − Resistance + Vulnerability)

### Example

Assuming 50% Final Status Chance:

|Resistance|Vulnerability|Effective Chance|
|---|---|---|
|0%|0%|50%|
|30%|0%|35%|
|30%|20%|45%|
|30%|50%|60%|
|0%|50%|75%|

### Status DMG Resistance

- Reduces DMG originating from the corresponding status.
    
- Does not inherently prevent status applications.
    
- Slash-specific DMG resistance is calculated dynamically every tick.
    
- 100% Slash DMG resistance prevents Slash DMG but does not prevent stack accumulation.
    
- Resistance exceeding 100% does not cause Slash to heal the target.
    
- Complete Slash DMG resistance does not prevent Laceration or combination eligibility.
    
- These Slash immunity interactions remain subject to playtesting.
    
- Exact interactions with other statuses must be confirmed individually.
    

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
    

Additional rules:

- Guaranteed applications apply the explicitly defined number of stacks.
    
- They cannot generate additional guaranteed stacks through Status Chance bonuses.
    
- Associated ordinary damage instances may perform separate Status Chance rolls where applicable.
    

### Weapon-Specific Applications

- Weapon mechanics may directly apply statuses.
    
- The Shooting Morningstar's guaranteed defense-reduction applications are intended to integrate with Impact.
    
- Their exact Damage Categories and weapon-specific behavior must be established individually.
    

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
    

---

## 15. Status Damage Restrictions

Status DMG does not behave as an ordinary direct attack hit.

### Recursive Status Applications

- Status DMG cannot apply additional statuses through ordinary Status Chance rolls by default.
    
- Explicitly defined specialized mechanics may override this rule.
    
- Scripted combination applications are distinct from automatic Status Chance rolls.
    

### On-Hit Effects

Status DMG does not trigger general on-hit effects, including:

- Life Steal.
    
- Stability recovery.
    
- Effects requiring direct attack hits.
    

### Player Death

- Existing statuses persist after their originating player dies.
    
- Stored damage, ownership and remaining duration are not removed or recalculated due to the originating player's death.
    

### Healing & Invulnerability

Established for Slash:

- Ordinary healing does not affect existing stacks.
    
- Explicit cleansing effects can remove stacks.
    
- Invulnerability prevents DMG but does not suspend ticking or decay.
    

Interactions with other statuses will be confirmed individually where necessary.

---

## 16. Stability Barrier Interactions

The general Stability Barrier system remains under development.

### Established Interactions

- Slash and Laceration damage Stability Barriers before HP.
    
- Slash does not inherently bypass Stability Barriers.
    
- Breach increases all incoming attack DMG against Stability Barriers.
    
- Breach's additional barrier DMG applies regardless of the attacking player, weapon or Damage Category.
    
- Further Puncture applications are not required to benefit from the barrier bonus.
    
- Additional barrier-specific DMG cannot carry over into HP DMG when a barrier is destroyed.
    
- Breach's ordinary DMG vulnerability remains applicable.
    

### Undecided

- General Stability Barrier calculation rules.
    
- Exact Breach barrier DMG bonus.
    
- Barrier interactions with other statuses.
    
- Barrier-specific mitigation.
    
- Detailed damage overflow calculations.
    
- Combination-specific barrier effects.
    

---

## 17. Multiplayer Ownership & Aggro

### Ownership

- Every player maintains independent status pools.
    
- Individual stacks retain their originating ownership.
    
- Ordinary applications cannot alter another player's stacks.
    

### Damage Attribution

- Status DMG is attributed to the original owner.
    
- Status DMG contributes to enemy aggro like direct DMG.
    
- Aggro contribution is assigned to the original owner.
    
- When two allied players contribute to a combination, its DMG credit is split equally between them.
    

### Allied Cooperation

Players can cooperate through:

- Status combinations.
    
- DEF reduction.
    
- DMG vulnerability.
    
- Status Chance Vulnerability.
    
- Other enemy-wide debuffs.
    

Aggregation and stacking rules for debuffs originating from multiple players remain undecided.

---

## 18. Status Combination System

### General Rules

- Only groups can trigger status combinations.
    
- Non-allied players cannot combine their statuses.
    
- Individual statuses remain useful during solo play.
    
- Individual stacks belonging to different players do not collectively count toward a completed set.
    
- Compatible completed sets are required.
    
- Physical statuses cannot combine with other physical statuses.
    
- Every physical status should possess a combination with every elemental status.
    
- Otherworldly statuses are currently excluded.
    

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
    
- Players can influence priority through the order of status applications.
    

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
    
- These interactions can occur without reaching enhanced states or triggering group combinations.
    

---

## 19. Physical Status Overview

### Slash / Laceration

- Accumulating DoT.
    
- Individually calculated stack strength.
    
- Independent critical rolls.
    
- Provisionally ignores corresponding DEF entirely.
    
- Reaching six stacks transforms Slash into Laceration.
    
- Laceration preserves all six stacks.
    
- No additional standalone enhanced effect.
    
- No additional enhanced stacks.
    
- Enables Slash combinations.
    
- Gradual FIFO decay.
    

See [[Slash]].

### Impact / Fracture

- Individually calculated flat corresponding DEF reduction.
    
- Stack strength depends on non-critical, pre-mitigation triggering DMG and original corresponding enemy DEF.
    
- Higher triggering DMG produces stronger reduction.
    
- Higher original DEF produces weaker reduction.
    
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
    
- Reaching six stacks transforms Puncture into Breach.
    
- Breach preserves all six vulnerability values.
    
- Maximum corresponding vulnerability from one pool is 15%.
    
- No additional enhanced stacks.
    
- Further applications replace remembered stacks through FIFO.
    
- Breach increases all incoming attack DMG against Stability Barriers.
    
- Additional barrier DMG cannot carry over into HP DMG.
    
- Enables Puncture combinations.
    
- Gradual FIFO decay.
    

See [[Puncture]].

---

## 20. Elemental Status Overview

The following mechanics retain their existing design pending individual elemental status reviews.

### Fire

- Six-stack threshold.
    
- Three stacks apply Burn.
    
- Burn possesses its own internal timer.
    
- Six stacks trigger Combustion unless a combination takes priority.
    
- Ordinary Combustion consumes Fire stacks.
    
- Combustion can apply Burn to affected enemies.
    
- No independently established holding window after ordinary Combustion.
    

See [[Fire]].

### Ice

- Six-stack threshold.
    
- Three stacks apply Slow.
    
- Six stacks trigger Freeze unless a combination takes priority.
    
- Freeze lasts 3 seconds.
    
- Additional Ice hits extend Freeze by 1 second, once per source.
    
- Freeze grants the party increased Critical Chance and Critical DMG against the affected entity.
    
- Ice stacks restart from zero for the relevant source after Freeze ends.
    

See [[Ice]].

### Lightning

- Six-stack threshold.
    
- Three stacks trigger a 0.5-second stun.
    
- Six stacks trigger Lightning Discharge unless a combination takes priority.
    
- Discharge applies:
    
    - A 1-second stun.
        
    - A 5-second party Attack Speed and Animation Speed buff.
        
- One completed set remains available for combinations for 5 seconds.
    
- The completed-set timer cannot be extended through ordinary applications.
    
- A separate set can accumulate during this window.
    
- A newly completed set replaces the previous completed set.
    
- A new Discharge buff replaces the previous buff rather than stacking its strength.
    
- Consuming the completed set does not prematurely remove an already granted Discharge buff.
    

See [[Lightning]].

### Poison

- Six-stack threshold.
    
- Three stacks apply Poison DoT totaling 5% of maximum HP over its duration.
    
- Six stacks trigger Poisonous Strikes unless a combination takes priority.
    
- Poisonous Strikes applies Poison DoT totaling 15% of maximum HP over its duration.
    
- The initiator gains 1% HP DMG through Normal Attacks.
    
- Party members gain 0.5% HP DMG through Normal Attacks.
    
- Duration-extension progression:
    
    - +1.0, +0.8, +0.6, +0.4, +0.2, +0.05, 0.
        
- The exact extension trigger remains to be clarified.
    

See [[Poison]].

---

## 21. Status Combination Overview

### Existing Elemental Combinations

|Statuses|Combination|
|---|---|
|Fire + Ice|[[Cool Combustion]]|
|Fire + Lightning|[[Arc Combustion]]|
|Fire + Poison|[[Toxic Combustion]]|
|Ice + Lightning|[[Shattering Voltage]]|
|Ice + Poison|[[Cryotoxicity]]|
|Lightning + Poison|[[Neurotoxin]]|

### Existing Slash Combinations

|Element|Combination|
|---|---|
|Fire|[[Burned Wounds]]|
|Ice|[[Frozen Wounds]]|
|Lightning|[[Conductive Wounds]]|
|Poison|[[Viral Wounds]]|

### Proposed Impact Combinations

|Element|Combination|Proposed Effect|
|---|---|---|
|Fire|Thermal Fracture|Heat weakens damaged defensive structures, amplifying flat DEF reduction.|
|Ice|Shatter|Brittle defensive structures break upon receiving powerful hits, increasing percentage-based DEF reduction.|
|Lightning|Disruption|Interferes with stabilization, slowing defensive restoration and status decay.|
|Poison|Corrosion|Gradually increases physical and magical DEF reduction throughout its duration.|

### Proposed Puncture Combinations

|Element|Combination|Proposed Effect|
|---|---|---|
|Fire|Internal Combustion|Fire penetrates existing openings, causing additional bursts of internal DMG when attacked.|
|Ice|Frost Penetration|Cold penetrates the entity, reducing attack and movement speed.|
|Lightning|Short Circuit|Enhances Stability Barrier destruction through additional electrical DMG.|
|Poison|Toxic Infiltration|Poison penetrates defensive layers, progressively increasing incoming DMG vulnerability.|

All proposed Impact and Puncture combinations require individual development.

Names and effects are not finalized.

### Combination Design Philosophy

- Slash combinations primarily manipulate wounds and DoT.
    
- Impact combinations primarily manipulate defensive structures and DEF.
    
- Puncture combinations primarily exploit openings, DMG vulnerability and Stability Barriers.
    

---

## 22. Frozen Wounds & Freeze Interaction

- [[Frozen Wounds]] replaces the ordinary Freeze critical vulnerability bonus.
    
- Ordinary Freeze and Frozen Wounds are mutually exclusive as critical vulnerability effects.
    
- Their Critical Chance bonuses do not stack.
    
- Their Critical DMG bonuses do not stack.
    
- Frozen Wounds provides its own critical vulnerability bonus.
    
- Applicable Freeze mechanics are preserved.
    
- Exact bonus values remain undecided.
    

---

## 23. Status Visibility & Combat Display

### Solo

- Players see their own status stacks and status effects.
    
- Completed and enhanced statuses are clearly highlighted.
    

### Party

- The player's own building stacks are clearly visible.
    
- Allied building stacks appear as smaller, muted indicators.
    
- Completed and enhanced statuses are highlighted for their owner and eligible allies.
    
- Players can recognize potential combination opportunities.
    

### Outside the Party

- Players see status visuals and payoff effects.
    
- Non-allied individual stack counts are not displayed.
    
- Certain allied interactions may involve [[Wave Projection]].
    

See [[Multiplayer]] and [[Companions]].

### Physical Status Representation

- Laceration and Breach are displayed as single enhanced statuses.
    
- Fracture displays its current enhanced stack count.
    
- Remembered flat Impact values do not count as displayed Fracture stacks.
    
- Puncture uses grayish colors for physical stacks and pinkish colors for magical stacks.
    
- Exact visual representation of individual Damage Categories across all statuses remains undecided.
    

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
    
- Individual status DMG resistance formulas and limitations.
    

### Damage Calculation

- Individual status damage coefficients.
    
- Exact Impact flat DEF reduction formula.
    
- Exact negative DEF calculation.
    
- Interaction with General Defense.
    
- Final Slash DEF penetration after playtesting.
    
- Elemental status critical application behavior.
    
- Critical properties of guaranteed damaging stacks without originating DMG.
    
- Damage rounding and minimum damage.
    
- Potential limitations on accumulated DEF reduction and DMG vulnerability.
    

### Stack & Timer Resolution

- Ordering of genuinely simultaneous applications.
    
- Resolution of full-stack thresholds when multiple stacks are applied through one hit.
    
- Individual elemental decay mechanics.
    
- Interaction between incomplete sets, completed sets and individual effect timers.
    
- Status Duration modifiers.
    
- Potential tick-frequency modifiers.
    
- Cleansing interactions beyond established individual status rules.
    

### Elemental Status Review

- Fire's Burn timer interactions.
    
- Ice's Freeze extension mechanics across multiple players.
    
- Lightning buff interactions across multiple players.
    
- Poisonous Strikes duration-extension trigger.
    
- Poisonous Strikes stack consumption and combination availability.
    
- Poison initiator and party bonus interaction.
    
- Elemental damage values, durations and individual payoff mechanics.
    
- Confirm which Slash damage and timing principles also apply to elemental statuses.
    

### Multiplayer

- Aggregation of DEF reduction and DMG vulnerability from multiple players.
    
- Companion status ownership.
    
- Persistence after disconnecting or leaving the map.
    
- Status damage contribution toward kill credit, experience and loot eligibility.
    
- Combination ownership when groups change.
    
- Whether one group member can independently supply both combination components while belonging to a group.
    

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
    

### Stability Barriers

- General barrier system.
    
- Barrier mitigation and overflow calculations.
    
- Exact Breach barrier DMG bonus.
    
- Status-specific barrier interactions.
    
- Combination-specific barrier interactions.
    

### Otherworldly Statuses

- Determine which universal rules apply to Instability and Coptering.
    
- Establish individual exceptions where necessary.
    

### Visual Representation

- Final physical and magical stack indicators.
    
- Enhanced status visuals.
    
- Critical stack indicators where appropriate.
    
- Display of simultaneous ticks from multiple players.
    
- Display of individual and combined Status Chances.
    
- Visibility of enemy resistances.
    
- Visual representation of combinations originating from different groups.
    

---

## Design Status

### Mechanically Established

- Damage Categories and Damage Types.
    
- Individual Status Chance rolls.
    
- Status Chance above 100%.
    
- Physical and magical stack categorization.
    
- Player-specific stack ownership.
    
- Six-stack progression.
    
- FIFO replacement.
    
- Shared expiration timers.
    
- Gradual physical status decay.
    
- Guaranteed direct applications.
    
- Status Chance Resistance and Vulnerability.
    
- Group-exclusive status combinations.
    
- Group-based physical combination limitations.
    
- FIFO physical combination priority.
    
- General combat DMG display settings.
    

### Individual Physical Statuses

- Slash / Laceration: Mechanically established.
    
- Impact / Fracture: Mechanically established.
    
- Puncture / Breach: Mechanically established.
    

Remaining questions primarily concern numerical balancing, visual representation, Stability Barriers and individual combinations.

### Elemental Statuses

- Fire: Established core mechanics; individual review pending.
    
- Ice: Established core mechanics; individual review pending.
    
- Lightning: Established core mechanics; individual review pending.
    
- Poison: Established core mechanics; individual review pending.
    

### Further Development

- Finalize remaining elemental mechanics.
    
- Establish the general Stability Barrier system.
    
- Review weapon damage compositions and applicable statuses.
    
- Develop individual status combinations.
    
- Establish final numerical balancing through testing.