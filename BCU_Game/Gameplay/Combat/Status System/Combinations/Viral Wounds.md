# Viral Wounds

**Combination:** [[Poison]] + [[Slash]] **Category:** Elemental + Physical **Identity:** Progressive DMG vulnerability through repeated combination activations. **Duration:** 5 seconds **Maximum Viral Stacks:** 4 **Combination Cooldown:** None

## Activation

- Requires a completed Poison set and [[Slash|Laceration]], representing six stacks of each status.
- Combination eligibility is checked before the ordinary sixth-stack payoff.
- Both completed sets are immediately consumed.
- Their individual damage effects are preserved within Viral Wounds.
- Each successful combination activation grants one Viral stack.
- Viral Wounds exists as an independent combination status.

## Core Mechanics

- Viral Wounds increases all incoming DMG against the affected enemy.
- Each Viral stack grants an additive 12.5% DMG vulnerability.
- Viral Wounds can accumulate up to four stacks.
- The combination does not introduce an additional independent damage source.
- Instead, it complements the existing damage effects of Poison and Slash.

## Viral Stack Progression

|Viral Stacks|DMG Vulnerability|
|--:|--:|
|1|+12.5%|
|2|+25%|
|3|+37.5%|
|4|+50%|

- Each Viral stack requires another complete combination of six Poison and six Slash stacks.
- Reaching four Viral stacks requires four separate combination activations.
- This requires a total of 24 Poison and 24 Slash stacks.
- Applying ordinary Poison or Slash individually does not increase the Viral stack count.
- No additional vulnerability cap is applied beyond the four-stack limit for initial testing.

## DMG Vulnerability

- Viral Wounds increases all applicable incoming DMG.
- The vulnerability applies to:
    - Physical DMG.
    - Magical DMG.
    - Elemental DMG.
    - Normal attacks.
    - Abilities.
    - Damage over Time.
    - Eligible status combination DMG.
- Allied players benefit from the same vulnerability.
- The vulnerability also amplifies the preserved damage effects of Poison and Laceration.
- Viral Wounds represents target-side DMG vulnerability rather than a direct increase to the attacking player's offensive attributes.

## Preserved Laceration

- The consumed Laceration continues dealing its ordinary DoT within Viral Wounds.
- Its stored physical and magical damage categories are preserved.
- Its stored critical results and applicable Critical DMG multipliers are preserved.
- Its ordinary DEF penetration properties remain applicable.
- New ordinary Slash stacks can accumulate independently.
- The preserved Laceration damage effect is renewed upon subsequent Viral Wounds activations.

## Preserved Poison Effects

- The completed Poison set is consumed while its individual damage effects remain functional.
- Poison Strike continues following its established mechanics.
- Applicable Poison damage effects retain their original properties.
- New ordinary Poison stacks can accumulate independently.
- The preserved Poison effects are renewed upon subsequent Viral Wounds activations.

## Duration & Maintenance

- All Viral stacks share one five-second expiration timer.
- Every successful Viral Wounds activation refreshes the shared duration.
- All existing Viral stacks expire simultaneously when the duration reaches zero.
- Viral stacks do not decay individually.
- The duration continues normally during immunity and invulnerability phases.
- Viral Wounds can potentially remain active indefinitely if players consistently fulfill the combination requirements.

## Reactivation

- Each subsequent activation requires another completed Poison set and another Laceration.
- Both newly completed sets are consumed.
- If fewer than four Viral stacks exist, one additional Viral stack is granted.
- If four Viral stacks already exist, the stack count remains unchanged.
- The shared duration resets to five seconds.
- The preserved Poison and Laceration damage effects are renewed.
- No combination-specific cooldown is applied.

## Status Application Rules

- Successful status applications contribute toward the combination according to ordinary status rules.
- Blocked attacks do not apply contributing status stacks.
- Missed or dodged attacks do not apply contributing status stacks.
- Successful, unblocked attacks that deal zero DMG due to resistance or mitigation can still apply statuses.
- Complete DMG resistance does not inherently prevent status accumulation.
- Ordinary Status Chance Resistance remains applicable.

## Independent Status Accumulation

- Ordinary Poison and Slash stacks can accumulate while Viral Wounds is active.
- Newly accumulated stacks are independent of the preserved damage effects.
- Players must rebuild both completed sets to gain another Viral stack or refresh the combination.
- The presence of Viral Wounds does not prevent other eligible status combinations from activating.

## Boss Interaction

- Viral Wounds can affect bosses.
- Boss immunity and invulnerability phases do not pause its duration.
- The combination is particularly effective during sustained combat against high-HP targets.
- Boss-specific vulnerability adjustments may be introduced following testing.

## PvP Interaction

- Viral Wounds is available in both PvE and PvP.
- The same fundamental mechanics apply to affected players.
- PvP-specific balancing adjustments may be introduced following testing.

## Visual Representation

- Viral Wounds possesses a distinct status icon and visual identity.
- The current Viral stack count is displayed.
- The remaining shared duration is displayed.
- Increasing Viral stacks should visually communicate progressive contamination and deterioration of the affected enemy.

## Numerical Balancing — TBD

- Final DMG vulnerability per Viral stack.
- Maximum Viral stack count balancing.
- Final shared duration.
- Potential boss-specific adjustments.
- Potential PvP-specific adjustments.

## Remaining Implementation Details

- Exact renewal and replacement rules for preserved Laceration and Poison damage effects.
- Whether stronger existing damage effects are retained when a weaker combination activates.
- Whether preserved damage effects use independent expiration timers.
- Interaction with independently active ordinary Laceration and Poison Strike.
- Exact order of vulnerability calculations alongside [[Puncture]] and other damage modifiers.
- Whether a newly gained Viral stack amplifies damage occurring during the same activation event.
- Multiplayer damage attribution.
- Stability Barrier interactions.

## Design Philosophy

Viral Wounds represents the progressive deterioration of an enemy through repeated contamination of its existing wounds. Rather than introducing another independent damage source, Viral Wounds complements Poison and Slash by preserving their individual damage effects while increasing the enemy's vulnerability to incoming DMG. Reaching maximum vulnerability requires four complete combination activations, rewarding sustained aggression and coordinated status applications. Maintaining maximum vulnerability requires continued investment in both Poison and Slash. The combination is balanced primarily through its stack requirements, shared duration and numerical vulnerability values rather than artificial cooldowns or restrictions on repeated activation.