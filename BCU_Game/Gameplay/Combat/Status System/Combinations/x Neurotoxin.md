# Neurotoxin — Status Combination

**Identity:** Timed electrical interruptions while Poison continues dealing damage  
**Combination:** [[Lightning]] + [[Poison]]  
**Category:** Elemental + Elemental  
**Trigger:** 6 Lightning + 6 Poison stacks  
**Consumption:** Undecided  
**Effect duration:** 6 seconds

## Core Mechanics

- Neurotoxin inflicts a guaranteed **0.2-second stun** at each specified time.
- Poison's existing damage over time **continues normally** during Neurotoxin.
- Neurotoxin adds **no independent damage bonus** and no movement slow.
- Stuns are deterministic rather than chance-based.

| Time after activation | Effect |
| --- | --- |
| 0 seconds | 0.2-second stun |
| 2 seconds | 0.2-second stun |
| 4 seconds | 0.2-second stun |
| 6 seconds | 0.2-second stun |

## Timing and Status Interactions

- Four short stuns are scheduled at 2-second intervals, including the initial hit at time 0 and the event at the 6-second boundary.
- If Lightning Discharge's party buff was already activated, a combination does **not** interrupt the buff's remaining duration.

## Undecided

- Consumption of contributing stacks, boss-specific interactions, and exact handling of a stun scheduled at the duration endpoint.

## Shared System Rules

## Activation and Ownership

- The system checks for an eligible combination when a compatible status reaches its full-stack threshold, **before** resolving that status's standalone sixth-stack payoff.
- Only the player's own stacks and eligible **allied** players' stacks can contribute. Non-allied players cannot combine stacks with one another.
- Activation is automatic when the requirements are satisfied; it does not need a separate button press.
- When two allied players supply a combination, damage credit is split **50/50** between them.
- If multiple combinations compete for the same stacks, the first eligible pair to complete resolves first. Truly simultaneous event ordering has not been finalized.
