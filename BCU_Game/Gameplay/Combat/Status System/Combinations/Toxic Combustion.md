# Toxic Combustion — Status Combination

**Identity:** Combustion spreads Poison's HP-based pressure  
**Combination:** [[Fire]] + [[Poison]]  
**Category:** Elemental + Elemental  
**Trigger:** Fire's Combustion hits a target with 6 Poison stacks  
**Consumption:** Fire stacks are consumed by Combustion; Poison consumption is undecided

## Core Mechanics

- Combustion spreads **50% of the fully stacked Poison damage-over-time effect** to nearby enemies.
- The vault also records that poisoned enemies hit can receive a **party bonus to percentage-HP damage per hit**.
- Poison's sixth-stack [[Poison]] effect, **Poisonous Strikes**, currently provides **1% HP damage with [[Normal Attacks]]** to the initiator and **0.5%** to party members.

## Timing and Status Interactions

- Toxic Combustion is an interaction with **Fire's Combustion**, rather than an independently established Fire holding window.
- The party's percentage-HP on-hit bonus and transferred DoT are distinct effects; their precise stacking and duration rules are not yet described.

## Undecided

- Whether Poison is consumed; spread range, timing, and exact DoT calculation.
- How the party's percentage-HP bonus is propagated, its duration, and how it interacts with Poisonous Strikes.

## Shared System Rules

## Activation and Ownership

- The system checks for an eligible combination when a compatible status reaches its full-stack threshold, **before** resolving that status's standalone sixth-stack payoff.
- Only the player's own stacks and eligible **allied** players' stacks can contribute. Non-allied players cannot combine stacks with one another.
- Activation is automatic when the requirements are satisfied; it does not need a separate button press.
- When two allied players supply a combination, damage credit is split **50/50** between them.
- If multiple combinations compete for the same stacks, the first eligible pair to complete resolves first. Truly simultaneous event ordering has not been finalized.
