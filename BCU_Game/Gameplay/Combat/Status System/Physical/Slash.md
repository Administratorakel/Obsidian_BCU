# Slash — Physical Status

**Identity:** Accumulating physical wounds and sustained damage  
**Category:** Physical  
**Damage type:** Physical damage over time (DoT)  
**Maximum stacks:** 6  
**Base stack duration:** 5 seconds (shared timer; refreshed by a successful application)

## Stack Progression

| Stacks | Effect |
| --- | --- |
| 1–5 | Physical wound DoT increases by an equal amount with each stack. |
| 6 | Maximum wound DoT. **No standalone sixth-stack payoff.** Full Slash stacks are available for eligible combinations. |

## Core Mechanics

- Each successful application adds one Slash stack, up to 6.
- All active stacks share a single 5-second expiration timer; another successful application refreshes the timer.
- Slash's DoT **partially ignores Physical Defense**.
- Slash can damage unusual enemies, including slimes; high Defense can still reduce part of its damage.
- Multiple Slash combinations can coexist on one enemy, subject to the general combination and stack-consumption rules.

## Full-Stack Resolution

- On reaching 6 stacks, check for an eligible allied status combination.
- If none is available, Slash simply remains at its maximum DoT until its normal expiry or another eligible interaction.
- Unlike Fire, Slash does not automatically consume its stacks or produce an extra sixth-stack effect.
- reaching full stacks turns Slash into Laceration

## Combinations

| Partner | Combination |
| --- | --- |
| [[Fire]] | [[Burned Wounds]] |
| [[Ice]] | [[Frozen Wounds]] |
| [[Lightning]] | [[Conductive Wounds]] |
| [[Poison]] | [[Viral Wounds]] |

## Weapon-Specific Interaction

- For the Adept Scythe's Lv 50/100 mastery mechanic, see [[Adept Scythe - Reaping Mastery]].
- Reaping is **not** Slash's universal sixth-stack payoff.

## Undecided

- Base DoT damage, tick frequency and exact Physical Defense penetration.
- Exact application chance and unresolved combination-specific stack consumption.

# Slash & Laceration — Updated Mechanics

## Damage Categories

- Slash belongs to the physical status family but supports both Damage Categories.
    - **Physical Slash:** Deals physical DoT DMG.
    - **Magical Slash:** Deals magical DoT DMG.
- Both variants share the same six-stack limit within each player's individual status pool.
- Each stack remembers its corresponding Damage Category.
- Hybrid stacks do not exist.

## Individual Stack Properties

Each Slash stack remembers:

- Original owner.
- Damage Category.
- Individually calculated base DoT DMG.
- Critical strike result.
- Applicable Critical DMG multiplier.
- Application order.

### Individual Stack Strength

- Base DoT DMG is calculated using the triggering attack's non-critical DMG before mitigation.
- The exact DMG scaling formula remains undecided.
- Every successfully applied stack receives its full calculated DoT DMG.
- Applying multiple stacks through one attack does not divide the calculated DMG between those stacks.
- Each stack retains its calculated base DMG per tick throughout its lifetime.
- Subsequent changes to the originating player's offensive attributes do not affect existing stacks.

## DEF Penetration

- Slash and Laceration provisionally ignore 100% of corresponding DEF.
- Physical Slash ignores physical DEF.
- Magical Slash ignores magical DEF.
- Positive DEF does not reduce Slash DMG.
- Negative DEF does not increase Slash DMG.
- Impact and Fracture do not directly enhance Slash DMG through DEF reduction.
- Full DEF penetration will be evaluated during playtesting.

## Critical Strikes

- Every Slash stack independently rolls its critical strike upon application.
- Slash does not inherit the critical strike result of the triggering attack.
- Multiple stacks originating from the same attack roll independently.
- Stacks applied to different enemies through AoE attacks roll independently.
- Critical stacks retain their critical DMG throughout their lifetime.
- Individual DoT ticks do not roll for critical strikes again.
- Using the triggering attack's non-critical DMG prevents double critical scaling.

## Stacking & Replacement

- Maximum of six shared physical and magical stacks per player per enemy.
- Reaching six stacks immediately transforms Slash into Laceration.
- Further successful applications replace the oldest stack through FIFO.
- Replacing a stack removes its stored properties and introduces the properties of the newly applied stack.
- Other players cannot replace or refresh another player's individual Slash stacks.

## Laceration

- Laceration is the enhanced version of Slash.
- Represents six accumulated Slash stacks.
- Preserves all six individual stacks and their properties.
- Displayed as a single enhanced status icon.
- Does not possess additional enhanced stack progression.
- Does not provide an additional standalone effect for now.
- Enables Slash status combinations.
- Further Slash applications maintain Laceration through FIFO replacement and duration refreshing.
- Weapon-specific enhancements, such as the Adept Scythe's Reaping Mastery, remain independent of Laceration's universal mechanics.

## Duration & Gradual Decay

- All stacks share a single expiration timer.
- Every successful application refreshes the entire status duration.
- Upon expiration, the oldest stack is removed through FIFO.
- The expiration timer restarts after each decay step.
- Laceration reverts to Slash with five stacks upon expiration.
- Reversion removes eligibility for status combinations.
- Applying another Slash stack at five stacks immediately restores Laceration.
- Slash disappears once all stacks have decayed.

### Status Lifecycle

- Ascending: Slash (1–5) → Laceration.
- Descending: Laceration → Slash (5–1) → No status.

Gradual decay represents the world attempting to stabilize the affected entity again, consistent with Impact and Puncture.

## DoT Tick Mechanics

- All stacks within an individual player's Slash pool share a single DoT tick timer.
- Physical and magical stacks use the same tick timer.
- The first DMG tick occurs after the first tick interval has passed.
- Applying the initial Slash stack does not immediately deal DoT DMG.
- Newly applied stacks contribute to the next scheduled shared tick, regardless of how recently they were applied.
- Applying additional stacks refreshes only the expiration timer.
- Stack applications do not reset the DoT tick timer.
- FIFO replacement does not reset the DoT tick timer.
- Transforming Slash into Laceration does not reset the DoT tick timer.
- Reverting Laceration into Slash does not reset the DoT tick timer.
- If expiration and a DMG tick occur simultaneously, the DMG tick resolves before the oldest stack is removed.
- The exact tick interval remains undecided.

## Dynamic DMG Calculation

### Fixed Properties

- Individual base DoT DMG.
- Originating player's offensive attributes at application.
- Critical strike result.
- Critical DMG multiplier.
- Damage Category.

### Dynamic Properties

- Current corresponding DMG vulnerability.
- Current Slash-specific DMG resistance.
- Other applicable target-side DMG modifiers.

Changes to the originating player's offensive attributes do not affect existing stacks.

Changes to the affected entity's applicable resistances and vulnerabilities immediately influence subsequent DMG ticks.

## Resistance & Immunity

- Slash-specific DMG resistance is independent of Status Chance Resistance.
- Slash-specific DMG resistance is calculated dynamically every tick.
- An enemy with 100% Slash DMG resistance receives no Slash DMG.
- Slash DMG resistance exceeding 100% does not heal the affected entity.
- Enemies with complete Slash DMG resistance can still accumulate Slash stacks and reach Laceration.
- Such enemies can still participate in Slash status combinations.
- This behavior will be evaluated during playtesting.

## Additional Interactions

### Recursive Status Applications

- Slash and Laceration DoT ticks cannot apply additional statuses.
- Explicit combination mechanics and experimental mechanics may define exceptions.

### Attacker Death

- Existing Slash stacks remain active after their originating player dies.
- Stored DMG properties and ownership remain unchanged.

### Healing

- Ordinary healing does not remove or otherwise influence Slash stacks.
- Healing abilities with explicitly defined cleansing effects may remove stacks.

### Cleansing

- Partial removal of Slash stacks follows FIFO.
- The oldest stack is removed first.

### Invulnerability

- Slash continues ticking and decaying normally while the affected entity is invulnerable.
- No DMG is dealt during invulnerability.
- Invulnerability does not suspend the status timers.

### Stability Barriers

- Slash and Laceration damage Stability Barriers before damaging HP.
- Slash does not inherently bypass Stability Barriers.
- Detailed interactions will be established when designing the Stability Barrier system.

## Status Combinations

- Only Laceration enables Slash status combinations.
- Ordinary Slash stacks cannot trigger combinations.
- Combinations continue to be referred to as **Slash combinations**, despite requiring Laceration.
- Slash cannot combine with Impact or Puncture.
- Natural synergies between physical statuses remain possible.
- Group-based combination limitations and FIFO combination priority follow the general [[Status]] rules.

The following mechanics will be determined individually for each Slash combination:

- DoT preservation.
- Stack consumption.
- Stack replacement.
- Status decay.
- Maximum duration.
- Maximum stacks.
- Scaling.
- Behavior of additional Slash applications.
- Transition back into Slash or Laceration.

## Visual Representation

- Laceration is displayed as a single enhanced status icon.
- Physical and magical DMG are displayed as one combined DMG number by default.
- Players can enable separate DMG numbers through the general combat display settings.
- Accumulated DoT DMG does not highlight individual critical contributions.
- Physical and magical DMG calculations remain independent regardless of the display setting.

## Remaining Open Questions

- Exact base DoT scaling formula.
- DoT tick interval.
- Final base duration and decay interval balancing.
- Testing complete DEF penetration.
- Testing combination eligibility against enemies with complete Slash DMG resistance.
- Detailed Stability Barrier interactions.
- Individual combination mechanics.
- Final visual representation.
- Numerical balancing.