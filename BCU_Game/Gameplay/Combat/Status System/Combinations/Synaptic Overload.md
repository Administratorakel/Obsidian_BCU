
**Combination:** [[Lightning]] + [[Poison]] **Category:** Elemental + Elemental **Identity:** Offensive enhancement and retaliation against enemy attacks. **Duration:** 5 seconds **Combination Cooldown:** None

## Activation

- Requires six completed Lightning stacks and six completed Poison stacks.
- Combination eligibility is checked before the ordinary sixth-stack payoff.
- Both completed sets are immediately consumed and stored within Synaptic Overload.
- Synaptic Overload appears as an independent status with its own icon and remaining duration.
- The stored Lightning Charge and Poison damage remain constant throughout the combination's duration.

## Offensive Effects

- Normal attacks against the affected enemy continue to trigger Poison Strike's HP% DMG throughout the five-second duration.
- Eligible players receive the ordinary Lightning attack speed bonus.
- The ordinary Lightning stun follows its established rules.
- Synaptic Overload does not introduce an additional stun.

## Retaliation

- Whenever an affected enemy would successfully hit a player with an attack, Synaptic Overload establishes an electrical connection between the enemy and the player.
- The enemy's incoming attack is nullified and its attack sequence is interrupted.
- The enemy receives retaliatory HP% DMG.
- Retaliatory damage is classified as Magical Poison DMG.
- Retaliatory damage scales with both the stored Lightning Charge and stored Poison damage.
- Retaliation does not consume or reduce either stored value.
- There is no limit on the number of retaliations during the combination's duration.
- There is no per-hit retaliation damage cap for initial testing.

## Melee Attacks

- Synaptic Overload activates at the first successful hit of an attack sequence.
- The incoming hit is nullified and the entire remaining attack sequence is cancelled.
- Missed or dodged attacks do not trigger retaliation or cancellation.
- Successfully blocked attacks trigger retaliation.
- Successful hits that would deal zero damage due to immunity or mitigation still trigger retaliation.

## Ranged and Magical Attacks

- Ranged attacks and magical abilities directed at a player are interrupted immediately before their release or cast completion.
- The enemy may complete the preparation phase of its attack.
- Retaliatory damage is applied at the interruption moment.
- A successful projectile hit is not required when the attack is cancelled before release.
- Enemies protected against cancellation instead trigger retaliation upon successfully hitting a player.

## Multi-Hit and Multi-Target Attacks

- The first successful hit cancels the entire attack sequence of an unprotected enemy.
- Multiple players being hit simultaneously count as one retaliation event.
- If an enemy is protected against cancellation, every separate successful hit triggers retaliation.
- All offensive attack types, including normal attacks and abilities, are eligible.

## Stability Barrier Interaction

- Stability Barriers protect enemies against attack cancellation and damage nullification.
- Protected enemies can continue their attack sequences and damage players normally.
- Every separate successful hit still triggers retaliatory damage.
- Retaliatory damage follows the ordinary Stability Barrier damage absorption rules.

## Boss Interaction

- Bosses are immune to Synaptic Overload's attack cancellation and damage nullification by default.
- Individual boss rules may override this protection.
- Bosses still receive retaliatory HP% DMG whenever they successfully hit a player.
- Separate successful hits within a multi-hit attack trigger separate retaliations.
- Synaptic Overload's duration continues normally during boss immunity and invulnerability phases.

## Status Accumulation

- Ordinary Lightning and Poison stacks can accumulate independently while Synaptic Overload is active.
- The stored elemental values within Synaptic Overload are independent of newly accumulated stacks.
- New ordinary stacks follow their established status rules.

## Reactivation

- Synaptic Overload cannot coexist with another instance of itself on the same target.
- If another Synaptic Overload is activated, the existing instance is immediately replaced.
- The previous stored values are discarded.
- The newly consumed elemental sets determine the replacement instance's strength.
- The duration resets to five seconds.
- No combination-specific cooldown is applied.

## PvP Interaction

- Synaptic Overload is available in both PvE and PvP.
- Players affected by Synaptic Overload follow the same fundamental rules as ordinary enemies.
- All attacks and offensive abilities are eligible to trigger retaliation.
- PvP-specific balancing adjustments may be introduced following testing.

## Visual Representation

- Synaptic Overload possesses a distinct status icon.
- Its remaining duration is displayed.
- The combination possesses a distinct visual identity representing the interaction between Lightning and Poison.
- Retaliation produces a recognizable visual reaction on the affected target.
- Every status and status combination should possess its own visual distinction.

## Numerical Balancing — TBD

- Stored Lightning Charge scaling.
- Stored Poison damage scaling.
- Retaliatory HP% DMG formula.
- Relative contribution of both consumed elemental sets.
- Potential boss-specific adjustments.
- Potential PvP-specific adjustments.

## Remaining Implementation Details

- Critical hit eligibility for retaliatory damage.
- Multiplayer damage attribution.
- Stability Barrier protection cost for attack cancellation.
- Whether a nullified attack consumes the defending player's blocking resources.
- Exact handling of persistent damaging abilities and already-released projectiles.
- Interaction between ordinary Poison Strike and Synaptic Overload's Poison Strike effect when both are active.

## Design Philosophy

Synaptic Overload combines the offensive benefits of Lightning and Poison with a defensive retaliation mechanic.

Lightning establishes the electrical connection and disrupts the enemy's ability to attack, while Poison causes internal HP% DMG through that connection.

The more aggressively an enemy attacks, the more opportunities it creates to damage itself. Against ordinary enemies, Synaptic Overload provides temporary offensive suppression. Against bosses and protected enemies, it functions as a retaliation-based damage amplifier without preventing them from fighting back.

The combination should be balanced primarily through numerical scaling rather than artificial cooldowns, retaliation limits or damage caps.