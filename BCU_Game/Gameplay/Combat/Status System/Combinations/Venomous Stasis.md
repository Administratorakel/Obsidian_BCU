# Venomous Stasis

**Combination:** [[Ice]] + [[Poison]] **Category:** Elemental + Elemental **Identity:** Sustained offensive damage and prolonged crowd control through repeated attacks. **Duration:** Extendable with diminishing returns **Combination Cooldown:** None

## Activation

- Requires six completed Ice stacks and six completed Poison stacks.
- Combination eligibility is checked before the ordinary sixth-stack payoff.
- Both completed elemental sets are immediately consumed and stored within Venomous Stasis.
- Venomous Stasis exists as an independent combination status.
- The stored Ice and Poison damage determine the strength of the combination.

## Core Mechanics

- Venomous Stasis applies Freeze to the affected enemy, subject to ordinary crowd-control protection rules.
- Every successful normal attack against the affected enemy:
    - Deals additional Poison DMG.
    - Extends the remaining duration of Venomous Stasis.
    - Extends its associated Freeze or Slow, if applicable.
- Additional Poison DMG is dealt immediately upon each successful hit.
- Damage is not accumulated for a delayed burst.
- Every individual successful hit of a multi-hit attack triggers both effects.

## Additional Poison DMG

- Additional Poison DMG scales with both:
    - Stored Ice DMG.
    - Stored Poison DMG.
- Both elemental sets contribute to the offensive strength of Venomous Stasis.
- Additional damage per hit remains constant throughout the combination's duration.
- Repeated damage applications do not consume the stored elemental values.
- Diminishing duration extensions do not reduce additional Poison DMG.

## Diminishing Duration Extension

- Every successful eligible hit extends the remaining duration by a fixed amount.
- The amount of time added diminishes with every successive extension.
- Eventually, the extension value reaches zero.
- Once the extension value reaches zero, subsequent hits continue dealing additional Poison DMG but no longer extend the duration.
- The diminishing extension progression is shared by all eligible attackers.
- The progression resets only when a new Venomous Stasis activates.
- Ordinary Freeze applications do not reset the progression.
- Exact extension values and their diminishing progression remain subject to balancing.

## Crowd Control

- Ordinary enemies are affected by Freeze.
- Enemies immune to Freeze may receive Slow instead.
- Successful hits extend the associated crowd-control duration alongside Venomous Stasis.
- Crowd-control immunity does not prevent Venomous Stasis itself from functioning.
- Existing Ice resistance and crowd-control protection rules remain applicable.

## Boss Interaction

- Bosses immune to Freeze receive Slow if they are susceptible to it.
- Bosses immune to both Freeze and Slow remain affected by Venomous Stasis without experiencing crowd control.
- Additional Poison DMG remains fully functional.
- Successful hits continue extending the combination's duration through the ordinary diminishing extension mechanic.
- This ensures that Venomous Stasis remains useful against fully crowd-control-immune enemies.

## Independent Status Duration

- Venomous Stasis possesses its own duration independently of the effectiveness of its associated crowd control.
- Preventing Freeze or Slow does not prevent additional Poison DMG.
- Duration extensions remain functional even when no crowd control is applied.

## Status Accumulation

- Ordinary Ice and Poison stacks can accumulate independently while Venomous Stasis is active.
- Newly accumulated stacks do not modify the stored elemental values of the existing combination.
- New stacks follow their ordinary status rules.
- Players can continue building toward subsequent combinations without restrictions.

## Reactivation

- Only one instance of Venomous Stasis may exist on a target at a time.
- A new activation immediately replaces the existing instance.
- The previously stored elemental values are discarded.
- The newly consumed Ice and Poison sets determine the replacement instance's strength.
- The duration resets to its initial value.
- The diminishing duration extension progression resets completely.
- No combination-specific cooldown is applied.

## PvP Interaction

- Venomous Stasis is available in both PvE and PvP.
- The same fundamental mechanics apply to affected players.
- PvP-specific balancing adjustments may be introduced following testing.

## Visual Representation

- Venomous Stasis possesses a distinct status icon and visual identity.
- Its remaining duration should be displayed.
- Successful hits should produce a recognizable additional Poison damage effect.

## Numerical Balancing — TBD

- Initial combination duration.
- Initial duration extension per hit.
- Diminishing extension formula.
- Maximum achievable additional duration.
- Stored Ice DMG coefficient.
- Stored Poison DMG coefficient.
- Additional Poison DMG formula.
- Slow effectiveness against Freeze-immune enemies.

## Remaining Implementation Details

- Physical or Magical classification of additional Poison DMG.
- Whether abilities can also trigger additional damage and duration extensions.
- Critical hit eligibility and critical damage calculation.
- Multiplayer damage attribution.
- Exact Stability Barrier interactions.
- Interaction with Freeze's Final Critical Chance vulnerability.
- Interaction with other independently active Freeze and Poison effects.

## Design Philosophy

Venomous Stasis rewards sustained aggression and high attack frequency against a target affected by Ice and Poison.

Rather than immediately shattering Ice, as [[Shattering Voltage]] does, Venomous Stasis rewards players for preserving the frozen condition for as long as possible.

Repeated attacks simultaneously deal additional Poison DMG and prolong the opportunity to deal further damage.

Diminishing duration extensions naturally prevent an individual activation from maintaining indefinite crowd control without requiring an artificial cooldown or limiting the number of damage applications.

Even against enemies immune to crowd control, the combination retains its offensive value through additional Poison DMG and extendable duration.