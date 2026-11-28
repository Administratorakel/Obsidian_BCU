

**Combination:** [[Lightning]] + [[Slash]] **Category:** Elemental + Physical **Identity:** Attack-triggered electrical propagation through electrically charged wounds. **Duration:** 5 seconds **Propagation Radius:** 5 meters **Combination Cooldown:** None

## Activation

- Requires a completed Lightning set and [[Slash|Laceration]], representing six stacks of each status.
- Combination eligibility is checked before the ordinary sixth-stack payoff.
- Both completed elemental and physical sets are immediately consumed.
- Their stored properties are transferred into an independent Conductive Wounds status.
- Conductive Wounds preserves the consumed Laceration's DoT.
- The consumed Lightning Charge and Laceration DMG determine the strength of the combination.

## Core Mechanics

- Conductive Wounds turns the affected enemy into an electrical conductor.
- Successful attacks against the affected enemy cause electrically charged blood to scatter, potentially transmitting electricity to nearby enemies.
- The triggering attack does not need to contain Lightning DMG.
- The triggering attack does not need to successfully apply a status.
- Conductive Wounds possesses its own independent propagation chance.
- Both normal attacks and abilities can trigger propagation attempts.
- There is no maximum number of propagation attempts per second.

## Independent Propagation Chance

- Propagation chance scales with both:
    - Total consumed Lightning Charge.
    - Stored Laceration DMG.
- The propagation chance is independent of the attacking player's ordinary Status Chance.
- A successful probability roll initiates electrical propagation.
- The same probability roll determines whether Lightning is propagated and applied.
- Lightning propagation and application are not guaranteed on every attack.
- The exact scaling formula remains subject to balancing.

## Eligible Attacks

- Successful normal attacks and abilities can trigger propagation.
- Missed or dodged attacks cannot trigger propagation.
- Successful attacks that deal zero DMG due to resistance, immunity or mitigation remain eligible.
- The triggering attack's damage type does not influence its eligibility.

## Electrical Propagation

- Each successful propagation selects one random nearby hostile enemy.
- The initial propagation radius is five meters.
- The affected enemy acts as the initial origin of the electricity.
- Propagation deals Magical Lightning DMG.
- Propagated DMG is calculated from the total consumed Lightning Charge.
- Laceration DMG contributes to propagation chance rather than directly increasing propagated Lightning DMG.
- No additional combination-specific damage amplification is introduced for initial testing.
- Propagated damage naturally scales with the strength of the consumed Lightning set.

## Electrical Bouncing

- Electricity can redirect when encountering an enemy that already possesses a completed Lightning set.
- The electricity selects another random nearby enemy.
- Each enemy can only be visited once during an individual propagation event.
- Electricity can bounce through multiple enemies with completed Lightning sets.
- No fixed maximum number of bounces is applied.
- Propagation continues until:
    - An eligible receiving enemy is reached.
    - No unvisited eligible enemy remains within range.
- Previously visited enemies cannot be selected again during the same propagation event.
- Separate propagation events maintain independent visited-enemy records.
- This prevents infinite bouncing without introducing an artificial bounce limit.

## Lightning Stack Application

- Successful electrical propagation can apply Lightning stacks.
- Propagated Lightning stacks follow the established Lightning status rules.
- Propagated stacks can contribute toward completed Lightning sets.
- Reaching the required Lightning threshold through propagation can activate other eligible status combinations.
- Enemies already possessing completed Lightning sets redirect the electricity instead of receiving another ordinary Lightning application from that propagation.

## Preserved Laceration DoT

- The consumed Laceration's original DoT continues within Conductive Wounds.
- Its stored physical and magical damage categories are preserved.
- Its original critical results and applicable damage properties are preserved.
- The preserved DoT remains active throughout Conductive Wounds' five-second duration.
- Newly applied ordinary Slash stacks accumulate independently of the preserved Laceration.

## Independent Status Accumulation

- Ordinary Lightning and Slash stacks can accumulate while Conductive Wounds is active.
- New ordinary stacks follow their established status rules.
- Players must rebuild both completed sets to reactivate Conductive Wounds.
- Newly accumulated stacks do not directly modify the existing Conductive Wounds instance.

## Reactivation

- Reactivation requires another completed Lightning set and another Laceration.
- A new activation replaces or refreshes the existing Conductive Wounds instance.
- The duration resets to five seconds.
- Multiple independent Conductive Wounds instances do not stack on the same target.
- Conductive Wounds can potentially remain active indefinitely through repeated successful combination activations.
- No combination-specific cooldown is applied.
- Whether weaker reactivations replace stronger stored values remains undecided.

## PvP Interaction

- Conductive Wounds is available in both PvE and PvP.
- The same fundamental mechanics apply.
- PvP-specific balancing adjustments may be introduced following testing.

## Visual Representation

- Conductive Wounds possesses a distinct status icon and visual identity.
- Its remaining duration is displayed.
- The affected enemy visually displays electrically charged wounds.
- Successful propagation produces a recognizable electrical transmission effect between enemies.
- Redirected electricity should visually communicate its bouncing behavior.

## Numerical Balancing — TBD

- Independent propagation chance formula.
- Lightning Charge contribution to propagation chance.
- Laceration DMG contribution to propagation chance.
- Propagated Lightning DMG scaling.
- Stored Charge of propagated Lightning stacks.
- Potential propagation chance diminishing returns.
- Final propagation radius balancing.
- Potential PvP-specific adjustments.

## Remaining Implementation Details

- Exact handling of Status Chance Resistance during propagation.
- Whether propagation can apply multiple Lightning stacks through excess Status Chance.
- Whether redirected electricity deals damage to enemies it bounces off.
- Whether the five-meter radius is recalculated from each subsequent bounce origin.
- Environmental and enemy obstruction.
- Critical strike calculation for propagated Lightning DMG.
- Exact multiplayer damage attribution.
- Preserved Laceration tick timing.
- Whether individual DoT ticks can trigger electrical propagation.
- Handling of weaker Conductive Wounds reactivations.
- Whether propagated electrical strikes can trigger another existing Conductive Wounds.

## Design Philosophy

Conductive Wounds transforms an enemy into a persistent electrical conductor that players actively trigger through continued aggression. Unlike [[Arc Combustion]], which releases automatically timed electrical waves, Conductive Wounds depends on successful follow-up attacks and its independently calculated propagation chance. Its primary strength lies in spreading Lightning across groups of enemies, supporting subsequent status applications and combinations. The electrical bouncing mechanic allows electricity to search for suitable targets without repeatedly visiting the same enemy or requiring an artificial bounce limit. Preserving Laceration's original DoT ensures that both contributing statuses retain offensive value. Players can maintain Conductive Wounds through continuous combat, provided they repeatedly fulfill both combination requirements.