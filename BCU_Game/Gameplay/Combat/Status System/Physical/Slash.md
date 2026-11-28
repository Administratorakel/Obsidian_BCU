# Slash & Laceration

**Identity:** Accumulating wounds and sustained DEF-independent DMG  
**Status Family:** Physical  
**Damage Categories:** Physical and Magical  
**Maximum Stacks:** 6  
**Base Stack Duration:** 5 seconds (provisional)  
**Enhanced Status:** Laceration

---

## Slash

### Core Mechanics

- Slash deals sustained Damage over Time (DoT).
- Two variants:
    - **Physical Slash:** Deals physical DoT DMG.
    - **Magical Slash:** Deals magical DoT DMG.
- Both variants belong to the same status.
- Physical and magical variants share a maximum of 6 stacks within each player's individual status pool.
- Each stack possesses its own Damage Category and individually calculated DMG.
- Hybrid stacks do not exist.
- Slash can affect unusual entities, including slimes.

### Stack Progression

|Stacks|Effect|
|---|---|
|1–5|Accumulating DoT DMG based on individual stack strength.|
|6|Immediately transforms into Laceration.|

### Individual Stack Strength

- Base DoT DMG is calculated using the triggering attack's non-critical DMG before mitigation.
    
- The exact scaling formula remains undecided.
    
- Every successfully applied stack receives its full calculated base DoT DMG.
    
- Applying multiple stacks through one attack does not divide the calculated DMG between those stacks.
    
- Each stack retains its calculated base DMG per tick throughout its lifetime.
    
- Subsequent changes to the originating player's offensive attributes do not affect existing stacks.
    

### Stored Stack Properties

Each Slash stack remembers:

- Original owner.
    
- Damage Category.
    
- Individual base DoT DMG.
    
- Critical strike result.
    
- Applicable Critical DMG multiplier.
    
- Application order.
    

### Critical Strikes

- Every Slash stack independently rolls its critical strike upon application.
    
- Slash does not inherit the critical strike result of the triggering attack.
    
- Multiple stacks originating from the same attack roll independently.
    
- Stacks applied to different enemies through AoE attacks roll independently.
    
- Critical stacks retain their critical DMG throughout their lifetime.
    
- Individual DoT ticks do not roll for critical strikes again.
    
- Using non-critical triggering DMG prevents double critical scaling.
    

---

## Laceration

### Core Mechanics

- Laceration is the enhanced version of Slash.
    
- Reaching the sixth Slash stack immediately transforms Slash into Laceration.
    
- Represents six accumulated Slash stacks.
    
- Preserves all six individual stacks and their stored properties.
    
- Does not possess additional enhanced stack progression.
    
- Does not provide an additional standalone effect for now.
    
- Enables Slash status combinations.
    
- Displayed as a single enhanced status icon.
    

### Stack Replacement

- Further successful Slash applications during Laceration replace the oldest remembered stack through FIFO (First In, First Out).
    
- The newly applied stack receives its own independently calculated properties.
    
- Replacement can change the distribution of physical and magical Slash stacks.
    
- Every successful application refreshes the entire status duration.
    
- Other players cannot replace or refresh another player's individual Slash stacks.
    

---

## DMG Calculation

### DEF Penetration

- Slash and Laceration provisionally ignore 100% of corresponding DEF.
    
- Physical Slash ignores physical DEF.
    
- Magical Slash ignores magical DEF.
    
- Positive DEF does not reduce Slash DMG.
    
- Negative DEF does not increase Slash DMG.
    
- Impact and Fracture do not directly enhance Slash DMG through DEF reduction.
    
- Complete DEF penetration will be evaluated during playtesting.
    

### Fixed Offensive Properties

The following properties remain fixed throughout an individual stack's lifetime:

- Base DoT DMG.
    
- Originating player's applicable offensive attributes at application.
    
- Critical strike result.
    
- Critical DMG multiplier.
    
- Damage Category.
    

### Dynamic Target Properties

The following properties are calculated dynamically on every damage tick:

- Corresponding DMG vulnerability.
    
- Slash-specific DMG resistance.
    
- Other applicable target-side DMG modifiers.
    

Changes to the affected entity immediately influence subsequent damage ticks without modifying the stored offensive properties.

### Status Synergies

- Physical Puncture and Breach amplify physical Slash DMG.
    
- Magical Puncture and Breach amplify magical Slash DMG.
    
- This interaction does not require an actual status combination.
    
- Slash cannot form physical-physical status combinations.
    

---

## Duration & Decay

### General

- All stacks within an individual player's Slash pool share one expiration timer.
    
- Physical and magical stacks share the same timer.
    
- Every successful application refreshes the entire status duration.
    
- The newest applied stack determines the refreshed duration.
    
- Stacks decay gradually rather than disappearing simultaneously.
    
- The oldest stack decays first through FIFO.
    
- The expiration timer restarts after each decay step.
    

### Laceration Decay

- When Laceration expires:
    
    - Laceration reverts to Slash with 5 stacks.
        
    - The oldest remembered stack is removed.
        
    - The remaining five stacks retain their individual properties.
        
    - Eligibility for Slash combinations is lost.
        

### Slash Decay

- Each decay step removes the oldest remaining Slash stack.
    
- The status disappears once no stacks remain.
    
- Applying Slash to an enemy with 5 Slash stacks immediately restores Laceration.
    

### Status Lifecycle

- Ascending: Slash (1–5) → Laceration.
    
- Descending: Laceration → Slash (5–1) → No status.
    
- There is no separate active Slash (6) state.
    
- There are no additional Laceration stacks.
    

---

## DoT Tick Mechanics

### Shared Tick Timer

- Each player's Slash pool possesses its own shared DoT tick timer.
    
- All active physical and magical stacks deal their accumulated DMG simultaneously.
    
- Each stack retains its individual DMG value.
    
- Different players maintain independent tick timers.
    

### Tick Timing

- The first DoT tick occurs after the first tick interval has passed.
    
- Applying the initial Slash stack does not immediately deal DoT DMG.
    
- Newly applied stacks contribute to the next scheduled shared tick, regardless of how recently they were applied.
    
- Applying new stacks refreshes only the expiration timer.
    
- The DoT tick timer is not reset by:
    
    - New stack applications.
        
    - FIFO replacement.
        
    - Transformation into Laceration.
        
    - Reversion into Slash.
        
- If expiration and a damage tick occur simultaneously, the damage tick resolves before the oldest stack is removed.
    
- The exact tick interval remains undecided.
    

### Continuous Damage

- Each stack retains its calculated base DMG per tick for as long as it survives.
    
- DMG is not distributed across a predetermined total duration.
    
- Dynamic target-side modifiers continue affecting the final DMG of each tick.
    

---

## Resistance & Immunity

### Status DMG Resistance

- Slash-specific DMG resistance is independent of Status Chance Resistance.
    
- Slash-specific DMG resistance is calculated dynamically every tick.
    
- An enemy with 100% Slash DMG resistance receives no Slash DMG.
    
- Slash DMG resistance exceeding 100% does not heal the affected entity.
    

### Complete DMG Resistance

- Enemies with complete Slash DMG resistance can still accumulate Slash stacks.
    
- Such enemies can still reach Laceration and participate in Slash status combinations.
    
- This behavior is provisional and will be evaluated during playtesting.
    

---

## Additional Interactions

### Recursive Status Applications

- Slash and Laceration DoT ticks cannot apply additional statuses through ordinary Status Chance rolls.
    
- Explicitly defined specialized or experimental mechanics may introduce exceptions.
    
- See [[Status]] for the Experimental Arcade concept.
    

### Attacker Death

- Existing Slash stacks remain active after their originating player dies.
    
- Stored DMG properties, ownership and timers remain unchanged.
    

### Healing

- Ordinary healing does not remove or otherwise influence Slash stacks.
    
- Healing abilities with explicitly defined cleansing effects may remove stacks.
    

### Cleansing

- Partial removal of Slash stacks follows FIFO.
    
- The oldest stack is removed first.
    

### Invulnerability

- Slash continues ticking and decaying normally while the affected entity is invulnerable.
    
- No DMG is dealt during invulnerability.
    
- Invulnerability does not suspend status timers.
    

### Stability Barriers

- Slash and Laceration damage Stability Barriers before damaging HP.
    
- Slash does not inherently bypass Stability Barriers.
    
- Detailed interactions will be established when designing the Stability Barrier system.
    

### Damage Attribution

- Slash DMG is attributed to the player who originally applied the corresponding stacks.
    
- Slash contributes to enemy aggro according to the general [[Status]] rules.
    

---

## Status Combinations

### Requirements

- Ordinary Slash cannot participate in status combinations.
    
- Only its enhanced version, Laceration, enables Slash combinations.
    
- Combinations become available immediately upon reaching Laceration.
    
- Despite requiring Laceration, these combinations are referred to as **Slash combinations**.
    
- Only groups can trigger status combinations.
    
- Slash cannot combine with Impact or Puncture.
    
- General combination priority and group limitations follow [[Status]].
    

### Existing Combinations

|Partner|Combination|
|---|---|
|[[Fire]]|[[Cauterization]]|
|[[Ice]]|[[Frozen Wounds]]|
|[[Lightning]]|[[Conductive Wounds]]|
|[[Poison]]|[[Viral Wounds]]|

### Individual Combination Rules

The following mechanics will be determined individually for each combination:

- DoT preservation.
    
- Stack consumption or preservation.
    
- Stack replacement.
    
- Status decay.
    
- Maximum duration.
    
- Maximum stacks.
    
- Scaling mechanics.
    
- Behavior of additional Slash applications.
    
- Transition back into Slash or Laceration.
    
- Effects upon expiration.
    

---

## Weapon-Specific Interactions

### Adept Scythe

- The Adept Scythe possesses additional mastery-based Slash mechanics at Lv 50 and Lv 100.
    
- See [[Adept Scythe - Reaping Mastery]].
    
- Reaping remains a weapon-specific enhancement.
    
- Reaping is not Laceration's universal sixth-stack payoff.
    

---

## Visual Representation

### Status Display

- Laceration is displayed as a single enhanced status icon.
    
- The exact representation of individual physical and magical stacks remains undecided.
    

### DMG Display

- Physical and magical DMG are displayed as one combined DMG number by default.
    
- Players can enable separate DMG numbers through the general combat display settings.
    
- This option is always accessible.
    
- Players are introduced to this option when physical and magical Damage Categories are explained during gameplay.
    
- Accumulated DoT DMG does not highlight individual critical contributions.
    
- Physical and magical DMG calculations remain independent regardless of the display setting.
    

---

## Lore

- Slash represents accumulating physical or magical wounds within an entity.
    
- Laceration represents a more severely wounded state after six accumulated applications.
    
- Gradual status decay represents the world attempting to stabilize the affected entity again.
    
- Continued Slash applications actively counteract this stabilization.
    
- The transition from Laceration back into Slash represents gradual restoration rather than immediate recovery.
    

---

## Placeholder Values

|Parameter|Value|
|---|---|
|Maximum Slash stacks|6|
|Additional Laceration stacks|None|
|Base status duration|5 seconds (provisional)|
|Corresponding DEF penetration|100% (provisional)|
|Base DoT scaling|Undetermined|
|DoT tick interval|Undetermined|
|Additional Laceration effect|None|

---

## Remaining Open Questions

- Exact individual DoT scaling formula.
    
- Exact DoT tick interval.
    
- Final base duration and decay interval balancing.
    
- Testing complete DEF penetration.
    
- Testing combination eligibility against enemies with complete Slash DMG resistance.
    
- Detailed Stability Barrier interactions.
    
- Individual status combination mechanics.
    
- Final visual representation.
    
- Numerical balancing.