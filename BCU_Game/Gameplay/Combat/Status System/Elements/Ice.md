# Ice, Slow & Freeze

**Identity:** Progressive crowd control and offensive opportunities  
**Status Family:** Elemental  
**Damage Categories:** Physical and Magical  
**Maximum Stacks:** 6  
**Base Stack Duration:** 5 seconds (provisional)  
**Third-Stack Payoff:** Slow  
**Sixth-Stack Payoff:** Freeze

---

## Ice

### Core Mechanics

- Ice progressively restricts the affected entity's ability to move and act.
    
- Ice supports physical and magical applications.
    
- Both Damage Categories contribute equally toward the same Ice stack pool.
    
- Ice's utility effects are independent of the originating Damage Category.
    
- Ice does not store individual offensive DMG values.
    
- Ice does not need to remember the physical and magical distribution of its applications for ordinary utility effects.
    
- Slow, Freeze and Final Critical Chance bonuses have predefined strengths.
    
- The DMG of the triggering attack does not influence the strength of Ice's utility effects.
    
- Ice stacks do not provide additional DMG per hit.
    
- Players belonging to the same group contribute toward one shared Ice pool per enemy.
    

### Stack Progression

|Stacks|Effect|
|---|---|
|1–2|Buildup toward Slow.|
|3|Initial Slow.|
|4|Increased Slow strength.|
|5|Further increased Slow strength.|
|6|Freeze and Final Critical Chance vulnerability.|

- Reaching three stacks activates Slow.
    
- The fourth and fifth stacks progressively strengthen Slow.
    
- Reaching six stacks activates Freeze unless an eligible status combination takes priority.
    
- Freeze-resistant and Freeze-immune entities follow individually established resistance rules.
    
- Multiple applications originating from one damage instance resolve sequentially.
    

---

## Slow

### Core Mechanics

Slow reduces the affected entity's:

- Movement Speed.
    
- Attack Speed.
    
- Animation Speed.
    

### Progressive Strength

- Ice stacks 1–2 do not provide ordinary Slow.
    
- Three stacks activate the initial Slow.
    
- Four stacks increase its strength.
    
- Five stacks further increase its strength.
    
- Exact Slow values remain undecided.
    
- The reductions are predefined and independent of triggering DMG.
    

### Duration

- Slow remains active while the corresponding Ice stacks are maintained.
    
- Successful Ice applications refresh the ordinary shared stack duration.
    
- Slow expires when its corresponding Ice stacks expire.
    
- Cleansing immediately adjusts Slow strength according to the remaining stack count.
    
- Reducing Ice below three stacks removes ordinary Slow.
    

### Dynamic Resistance

- Ice-specific DMG Resistance also reduces Slow strength.
    
- Slow dynamically references the affected entity's current Ice DMG Resistance.
    
- Gaining Ice DMG Resistance immediately weakens active Slow.
    
- Losing Ice DMG Resistance immediately strengthens active Slow.
    
- Resistance provisionally reduces Slow strength proportionally.
    

### Multiple Slow Effects

- Different groups can maintain independent Ice pools on the same enemy.
    
- Slow effects from different groups do not add their strengths together.
    
- Only the strongest currently applicable Slow affects the enemy.
    
- Weaker Slow effects remain active internally and continue their respective timers.
    
- When the strongest Slow expires, the next strongest active Slow becomes effective immediately.
    

---

## Freeze

### Core Mechanics

- Freeze is Ice's ordinary sixth-stack payoff.
    
- Freeze completely prevents voluntary movement, attacks and abilities.
    
- Freeze immediately cancels ongoing enemy attacks and abilities.
    
- Canceled attacks do not automatically resume when Freeze ends.
    
- Freeze immediately stops voluntary movement and existing momentum.
    
- Frozen enemies remain susceptible to externally caused movement.
    

### External Movement

Freeze does not inherently prevent:

- Knockback.
    
- Pushing.
    
- Pulling.
    
- Other externally applied repositioning effects.
    

Players can therefore reposition frozen enemies through compatible mechanics.

### Base Duration

- Freeze possesses a provisional base duration of 3 seconds.
    
- Freeze maintains its completed six-stack Ice set throughout its duration.
    
- The completed Ice icon remains visible.
    
- Freeze replaces the ordinary three-to-five-stack Slow.
    
- When Freeze ends naturally, all six Ice stacks belonging to that group disappear simultaneously.
    

### Full-Stack Resolution

Upon reaching six Ice stacks:

1. Complete the six-stack Ice set.
    
2. Check for an eligible status combination.
    
3. If an eligible combination exists, resolve it according to its individual rules.
    
4. Otherwise, activate Freeze or its applicable resistance-based alternative.
    
5. Apply Final Critical Chance vulnerability.
    
6. Begin the completed-set duration.
    

---

## Freeze Extensions

### Individual Extension Opportunities

- Additional successful Ice applications can extend an active Freeze.
    
- Each individual source can extend Freeze once per Freeze cycle.
    
- Every player belonging to the responsible group has one extension opportunity.
    
- The player who triggered Freeze can also use their extension opportunity.
    
- The provisional extension is 0.5 seconds per source before resistance calculations.
    

### Extension Restrictions

- Once a source uses its extension opportunity, further ordinary Ice applications from that source have no additional effect during the current Freeze cycle.
    
- Additional applications do not create a new ordinary Ice buildup while Freeze remains active.
    
- Applications from other groups contribute to their own independent Ice pools.
    
- Reaching a new Freeze cycle restores the extension opportunities.
    

### Multiple Applications

- An attack can apply multiple Ice stacks through one damage instance.
    
- Applications resolve sequentially.
    
- Excess applications after reaching the sixth stack can immediately trigger the corresponding source's extension.
    
- The source cannot receive multiple extensions through the same damage instance.
    

### Extension Resistance

- Extensions are affected by the enemy's current Ice DMG Resistance.
    
- The resistance applicable at the moment of extension determines its immediate effective duration.
    
- Subsequent resistance changes can dynamically affect the remaining Freeze duration.
    

### Illustrative Maximum Duration

Assuming zero Ice DMG Resistance and every source successfully using its extension:

|Contributing Sources|Base Duration|Total Extension|Total Duration|
|---|---|---|---|
|1|3s|0.5s|3.5s|
|2|3s|1s|4s|
|4|3s|2s|5s|
|6|3s|3s|6s|
|8|3s|4s|7s|
|12|3s|6s|9s|

- Maximum party size remains undecided.
    
- No separate hard Freeze duration cap has been finalized.
    
- Potential additional limitations will be evaluated during multiplayer balancing.
    

---

## Final Critical Chance Vulnerability

### Core Mechanics

- Reaching Ice's sixth-stack payoff grants increased Final Critical Chance against the affected entity.
    
- The bonus exclusively benefits the group responsible for the completed Ice set.
    
- Ordinary Freeze does not provide additional Critical DMG.
    
- Individual status combinations may provide additional Critical DMG where appropriate.
    

### Calculation

- The bonus is applied as additional Final Critical Chance %.
    
- The exact bonus value remains undecided.
    
- Its strength is independent of the DMG that applied the Ice stacks.
    
- Ice DMG Resistance does not reduce the strength of the Final Critical Chance bonus itself.
    
- Ice DMG Resistance can reduce its effective duration by reducing the corresponding Freeze duration.
    

### Applicable Critical Rolls

The Final Critical Chance bonus can benefit:

- Ordinary attacks.
    
- Abilities.
    
- Slash applications.
    
- Fire Heat applications.
    
- Burn activation.
    
- Combustion activation.
    
- Other compatible status-related critical strikes.
    

### Duration

- Final Critical Chance vulnerability shares the effective duration of Freeze or its enhanced Slow alternative.
    
- Freeze extensions also extend the vulnerability duration.
    
- Dynamic resistance changes affect its remaining duration.
    
- Cleansing the sixth-stack effect removes its vulnerability.
    
- The vulnerability disappears when the corresponding completed Ice set expires.
    

### Multiple Groups

- Each group's vulnerability is tracked independently.
    
- Players only benefit from the vulnerability generated by their own group.
    
- Vulnerability bonuses from different groups do not stack for individual players.
    

---

## Ice Resistance & Immunity

### Status Chance Resistance

- Ice Status Chance Resistance influences the probability of successfully applying Ice stacks.
    
- It does not directly reduce the strength of successfully applied utility effects.
    
- Guaranteed direct applications follow the general [[Status]] rules.
    

### Ice DMG Resistance

Ice DMG Resistance affects:

- Incoming Ice DMG.
    
- Ordinary Slow strength.
    
- Enhanced Slow strength.
    
- Freeze duration.
    
- Freeze extensions.
    
- The duration of Final Critical Chance vulnerability through the corresponding sixth-stack effect.
    

Ice DMG Resistance does not affect:

- Maximum Ice stack count.
    
- The strength of Final Critical Chance vulnerability.
    
- The number of stacks removed by cleansing.
    
- Status application chance directly.
    

A separate universal Status Effect Resistance attribute is not required.

### Proportional Resistance Scaling

Ice DMG Resistance provisionally reduces applicable utility strength and duration proportionally.

|Ice DMG Resistance|Relative Slow Strength|Base Freeze Duration|Extension Per Source|
|---|---|---|---|
|0%|100%|3s|0.5s|
|25%|75%|2.25s|0.375s|
|50%|50%|1.5s|0.25s|
|75%|25%|0.75s|0.125s|
|100%|0%|0s|0s|

Values are provisional and subject to balancing.

### Dynamic Freeze Duration

- Active Freeze dynamically responds to changes in Ice DMG Resistance.
    
- Gaining resistance can shorten the remaining duration.
    
- Losing resistance can increase the remaining duration.
    
- Previously elapsed duration and used extension opportunities remain relevant.
    
- Resistance changes cannot generate additional extension opportunities.
    
- The effective duration cannot exceed the available unmitigated duration from the base effect and its accumulated extensions.
    
- The exact dynamic timer implementation remains undecided.
    

---

## Freeze Immunity

### Core Mechanics

- Freeze Immunity is an individually defined enemy property.
    
- Freeze Immunity is primarily intended for bosses and selected special enemies.
    
- Ordinary enemies should not freely possess complete Freeze Immunity.
    
- Freeze Immunity is independent of Ice DMG Resistance and Ice Status Chance Resistance.
    
- Freeze Immunity does not inherently grant Slow immunity.
    
- Freeze-immune enemies can still receive normal Ice DMG according to their applicable defenses.
    

### Enhanced Slow

When a Freeze-immune enemy reaches six Ice stacks:

- Freeze is replaced by enhanced Slow.
    
- Enhanced Slow has a predefined strength halfway between ordinary third-stack Slow and complete immobilization.
    
- Enhanced Slow affects Movement Speed, Attack Speed and Animation Speed.
    
- Enhanced Slow remains affected by Ice DMG Resistance.
    
- The responsible group receives the ordinary Final Critical Chance vulnerability.
    

### Shared Sixth-Stack Mechanics

Enhanced Slow follows the same completed-set mechanics as Freeze:

- Base duration.
    
- Individual extension opportunities.
    
- Extension resistance.
    
- Dynamic resistance adjustments.
    
- Final Critical Chance vulnerability.
    
- Combination availability.
    
- Natural expiration.
    
- Cleansing behavior.
    

### Gaining Freeze Immunity

If an enemy gains Freeze Immunity during an active Freeze:

- Freeze immediately transitions into enhanced Slow.
    
- Existing elapsed duration is preserved.
    
- Remaining duration is preserved subject to applicable resistance calculations.
    
- Previously used extension opportunities remain used.
    
- Final Critical Chance vulnerability remains active.
    

### Losing Freeze Immunity

If an enemy loses Freeze Immunity during active enhanced Slow:

- Enhanced Slow immediately transitions into Freeze.
    
- Existing elapsed duration and extension usage remain preserved.
    
- Final Critical Chance vulnerability remains active.
    
- Freeze applies its ordinary interruption and movement restrictions.
    

Changing Freeze Immunity does not start a new Freeze cycle.

---

## Complete Ice DMG Resistance

### Reaching Six Stacks

Enemies with 100% Ice DMG Resistance can still accumulate Ice stacks.

When such an enemy reaches six stacks:

1. The completed Ice set briefly appears.
    
2. Check for an eligible status combination.
    
3. If an eligible combination exists, resolve it according to its individual rules.
    
4. Otherwise, the enemy immediately breaks out of Freeze.
    
5. All six Ice stacks disappear simultaneously.
    

### Breakout Behavior

- No sustained Freeze remains.
    
- No sustained enhanced Slow remains.
    
- No sustained Final Critical Chance vulnerability remains.
    
- Combination eligibility exists during the immediate completed-set resolution.
    
- The completed Ice icon appears and breaks to communicate the resistance interaction visually.
    

### Gaining Complete Resistance During Freeze

If an enemy gains 100% Ice DMG Resistance while affected by Freeze or enhanced Slow:

- Perform a final eligible combination check.
    
- Otherwise, the enemy immediately breaks out of the completed effect.
    
- All six Ice stacks are removed.
    
- Final Critical Chance vulnerability is removed.
    
- Remaining extension opportunities are lost with the current cycle.
    

### Immunity Comparison

|Property|Freeze Immunity Without Ice Resistance|100% Ice DMG Resistance|
|---|---|---|
|Ice stack accumulation|Yes|Yes|
|Ordinary Ice DMG|Normally mitigated|No Ice DMG|
|Third-stack Slow|Yes|No effective Slow|
|Sixth-stack effect|Enhanced Slow|Immediate breakout|
|Final Critical Chance bonus|Yes|No sustained bonus|
|Combination eligibility|During completed-set duration|Immediate resolution check|
|Extensions|Yes|No sustained effect to extend|

---

## Duration & Expiration

### Ordinary Ice Stacks

- Each group maintains one shared ordinary Ice expiration timer per enemy.
    
- The provisional base stack duration is 5 seconds.
    
- Successful Ice applications refresh the entire ordinary stack duration.
    
- Ordinary Ice stacks expire simultaneously.
    
- Ice does not follow gradual physical-style stack decay.
    
- Slow expires alongside its corresponding ordinary Ice stacks.
    

### Completed Ice Set

- Reaching six stacks transitions the ordinary Ice timer into the completed-set duration.
    
- Freeze or enhanced Slow determines the active completed-set duration.
    
- Ordinary Fire-style duration refreshing does not apply during Freeze.
    
- Additional Ice applications follow the individual extension rules.
    
- When the completed-set duration expires, all six Ice stacks disappear simultaneously.
    
- Final Critical Chance vulnerability expires with the completed set.
    

### Status Lifecycle

- Ice (1–2): Buildup.
    
- Ice (3): Initial Slow.
    
- Ice (4): Increased Slow.
    
- Ice (5): Further increased Slow.
    
- Ice (6): Freeze or enhanced Slow.
    
- Natural expiration: No Ice stacks.
    
- Cleansing completed Ice: Ice (3).
    

---

## Cleansing

### Ordinary Ice Cleansing

- Cleansing ordinary Ice stacks follows FIFO (First In, First Out).
    
- The oldest applied stack is removed first.
    
- Slow strength immediately adjusts according to the remaining stack count.
    
- Reducing the Ice pool below three stacks removes ordinary Slow.
    
- Ice DMG Resistance does not influence cleansing strength.
    

### Completed Ice Cleansing

Cleansing Freeze or its enhanced Slow alternative:

- Immediately ends the completed sixth-stack effect.
    
- Removes the three oldest Ice stacks through FIFO.
    
- Leaves three ordinary Ice stacks.
    
- Removes Final Critical Chance vulnerability.
    
- Restores ordinary third-stack Slow.
    
- Restarts the ordinary shared Ice duration.
    
- Ends the current Freeze cycle.
    

### Rebuilding Freeze

- Three additional successful Ice applications are required to rebuild the completed Ice set.
    
- Reaching six stacks again begins a new Freeze cycle.
    
- All individual extension opportunities become available again.
    

### Cleansing Progression

|Initial State|Cleansing Result|
|---|---|
|Ice (1)|No Ice|
|Ice (2)|Ice (1)|
|Ice (3)|Ice (2), Slow removed|
|Ice (4)|Ice (3), reduced Slow|
|Ice (5)|Ice (4), reduced Slow|
|Freeze / Enhanced Slow|Ice (3), completed effect removed|

---

## Multiplayer & Group Ownership

### Shared Ice Pool

- Players belonging to the same group contribute toward one shared Ice pool per enemy.
    
- Physical and magical applications contribute equally.
    
- Ice's utility strength is independent of individual contribution DMG.
    
- Individual applications retain ownership and application order where necessary for FIFO and source tracking.
    
- Each group's completed Ice set possesses its own duration.
    
- Each source has one extension opportunity per completed-set cycle.
    

### Independent Groups

Different groups maintain independent:

- Ice stacks.
    
- Ordinary stack timers.
    
- Slow progression.
    
- Freeze or enhanced Slow duration.
    
- Extension opportunities.
    
- Final Critical Chance vulnerability.
    
- Combination eligibility.
    

### Overlapping Crowd Control

- Multiple groups can independently Freeze the same enemy.
    
- Freeze durations overlap rather than adding together.
    
- An enemy remains frozen while at least one effective Freeze remains active.
    
- When one Freeze expires, other active Freeze effects remain unaffected.
    
- If no Freeze remains, the strongest applicable remaining Slow becomes effective immediately.
    
- Multiple groups can freeze an already frozen enemy without additional restrictions for now.
    

### Continuous Freeze Testing

- Independent group timers may allow coordinated players to maintain Freeze for extended periods.
    
- Potential continuous Freeze scenarios are intentionally permitted during early testing.
    
- Additional crowd-control limitations will be considered if necessary.
    

### Group Membership Changes

- Previously contributed Ice stacks remain within their original group if a contributing player leaves.
    
- Existing Ice stacks are not removed because their original contributor leaves the group.
    
- Detailed group membership and extension-eligibility interactions will be consolidated with the universal multiplayer status system.
    

### Attacker Death

- Ice stacks remain active after their original contributors die.
    
- Freeze and enhanced Slow remain active.
    
- Existing timers and ownership are unaffected.
    

---

## Additional Interactions

### Invulnerability

- Invulnerability does not inherently prevent Ice applications, Slow or Freeze.
    
- Invulnerable enemies can still receive applicable crowd-control effects.
    
- Existing Ice timers continue normally during invulnerability.
    
- Corresponding resistance and immunity rules remain applicable.
    

### Stability Barriers

- Whether Stability Barriers protect against Slow or Freeze remains undecided.
    
- This interaction will be established when designing the general Stability Barrier system.
    

### Damage Categories

- Ordinary Ice DMG retains its corresponding physical or magical Damage Category.
    
- Ordinary Ice DMG is calculated using the applicable defenses.
    
- Ice's utility effects do not require stored Damage Category proportions.
    
- Individual status combinations may define additional Damage Category requirements where necessary.
    

---

## Status Combinations

### Requirements

- Ice can participate in compatible elemental and physical-elemental combinations.
    
- Ice requires its completed six-stack set to enable combinations.
    
- Eligible combinations take priority over ordinary sixth-stack resolution.
    
- The completed Ice set remains eligible for combinations throughout Freeze or enhanced Slow.
    
- Duration extensions also extend combination availability.
    
- Completely Ice-resistant enemies receive an immediate combination check before their completed set breaks.
    
- Physical statuses require their enhanced states before combining with Ice.
    
- General group-based combination rules follow [[Status]].
    

### Existing Elemental Combinations

|Partner|Combination|
|---|---|
|[[Fire]]|[[Cool Combustion]]|
|[[Lightning]]|[[x Shattering Voltage]]|
|[[Poison]]|[[Venomous Stasis]]|

### Physical Status Combinations

|Partner|Required State|Combination|
|---|---|---|
|[[Slash]]|Laceration|[[Frozen Wounds]]|
|[[Impact]]|Fracture|[[x Shatter]] (proposed)|
|[[Puncture]]|Breach|[[x Frost Penetration]] (proposed)|

### Cool Combustion

- An eligible Fire Combustion against a completed Ice set can trigger Cool Combustion.
    
- Its existing mechanics must be reviewed alongside Fire's redesigned Heat accumulation and propagation system.
    

### Frozen Wounds

- Frozen Wounds replaces the ordinary Freeze critical vulnerability bonus.
    
- Ordinary Freeze and Frozen Wounds critical vulnerability bonuses do not stack.
    
- Frozen Wounds provides its own independently defined critical bonuses.
    
- Additional Critical DMG may be introduced through this or other individual Ice combinations.
    
- Exact effects remain subject to individual combination development.
    

### Individual Combination Rules

The following mechanics will be determined individually:

- Freeze preservation or consumption.
    
- Slow preservation or replacement.
    
- Critical Chance bonuses.
    
- Additional Critical DMG bonuses.
    
- Combination duration.
    
- Extension opportunities.
    
- Ice resistance interactions.
    
- Freeze Immunity interactions.
    
- Cleansing behavior.
    
- Additional Ice applications.
    
- Transition back into ordinary Ice or Freeze.
    
- Effects upon expiration.
    

---

## Lore

- Ice represents the progressive restriction of an entity's ability to act and move.
    
- Initial Ice applications build toward a meaningful restriction threshold.
    
- Continued applications increasingly restrict movement and actions.
    
- Freeze represents the temporary complete restriction of the affected entity.
    
- Coordinated applications can maintain this restriction for longer.
    
- Freeze-immune entities resist complete immobilization but may still experience significant restriction.
    
- Completely Ice-resistant entities immediately break out of the completed effect.
    
- Externally applied forces can still reposition frozen entities.
    
- Unlike physical statuses, Ice loses its accumulated effect simultaneously when its duration expires.
    

---

## Placeholder Values

|Parameter|Value|
|---|---|
|Maximum Ice stacks|6|
|Initial Slow threshold|3 stacks|
|Increased Slow thresholds|4 and 5 stacks|
|Freeze threshold|6 stacks|
|Ordinary base duration|5 seconds (provisional)|
|Base Freeze duration|3 seconds (provisional)|
|Extension per source|0.5 seconds (provisional)|
|Extensions per source per cycle|1|
|Stacks removed when cleansing Freeze|3|
|Remaining stacks after cleansing Freeze|3|
|Third-stack Slow strength|Undetermined|
|Fourth-stack Slow strength|Undetermined|
|Fifth-stack Slow strength|Undetermined|
|Enhanced Slow strength|Halfway between third-stack Slow and immobilization|
|Final Critical Chance bonus|Undetermined|
|Ordinary Freeze Critical DMG bonus|None|
|Maximum party size|Undetermined|
|Additional Freeze duration cap|Undetermined|

---

## Remaining Open Questions

### Numerical Balancing

- Exact third-stack Slow strength.
    
- Exact fourth-stack Slow strength.
    
- Exact fifth-stack Slow strength.
    
- Exact Final Critical Chance bonus.
    
- Final ordinary stack duration.
    
- Final Freeze duration.
    
- Final extension duration.
    
- Final proportional resistance scaling.
    
- Maximum party size.
    
- Potential hard Freeze duration limit.
    

### Crowd Control & Implementation

- Exact dynamic Freeze timer calculation.
    
- Interactions with enemy-specific actions.
    
- Potential continuous Freeze limitations.
    
- Simultaneous Freeze and cleansing resolution.
    
- Extension eligibility when group membership changes.
    
- Stability Barrier interactions.
    
- Final implementation of resistance values exceeding 100%.
    

### Status Combinations

- Rework existing Ice combinations.
    
- Review Cool Combustion with redesigned Fire mechanics.
    
- Finalize Frozen Wounds critical bonuses.
    
- Finalize Shatter.
    
- Finalize Frost Penetration.
    
- Establish combination-specific duration, resistance and cleansing mechanics.
    

### Visual Representation

- Ordinary Ice stack indicators.
    
- Progressive Slow visuals.
    
- Freeze visual effects.
    
- Enhanced Slow representation.
    
- Completed-set breakout animation.
    
- Remaining extension opportunities.
    
- Group-specific indicators.
    
- Final Critical Chance vulnerability representation.
    

---

## Design Status

Ice's fundamental mechanics are established.

The previous additional DMG per hit system has been removed.

Ice's defining mechanics are:

- Shared group-based progression.
    
- Fixed utility strength independent of triggering DMG.
    
- Third-stack Slow.
    
- Progressively stronger fourth- and fifth-stack Slow.
    
- Sixth-stack Freeze.
    
- Group-specific Final Critical Chance vulnerability.
    
- Individual 0.5-second extension opportunities.
    
- Dynamic Ice DMG Resistance interactions.
    
- Enhanced Slow against Freeze-immune enemies.
    
- Immediate completed-set breakout against completely Ice-resistant enemies.
    
- Three-stack cleansing of completed Ice.
    
- Simultaneous natural expiration.
    

Further development primarily concerns numerical balancing, crowd-control testing, Stability Barriers, visual representation and individual status combinations.