# Viral Wounds — Status Combination

**Identity:** Sustained HP-based damage and escalating damage vulnerability  
**Combination:** [[Poison]] + [[Slash]]  
**Category:** Elemental + Physical  
**Trigger:** Both contributing statuses reach 6 stacks  
**Consumption:** Undecided  
**Maximum Viral stacks:** 4 (provisional)

## Core Mechanics

- Fully stacked Poison and Slash create a **Viral damage-over-time effect** based on the enemy's HP.
- Each successful combination grants **one Viral stack**.
- Repeating the combination builds additional Viral stacks, up to a provisional maximum of **4**.
- Each Viral stack increases **all damage received** by the enemy by **25 percentage points**, additive.

| Viral stacks | Additional damage received |
| --- | --- |
| 1 | +25% |
| 2 | +50% |
| 3 | +75% |
| 4 | +100% |

## Timing and Status Interactions

- Viral can coexist with [[x Frozen Wounds]] and [[Cauterization]], subject to how each combination handles underlying stacks.
- Increased damage taken affects subsequent attacks from allied contributors; exact ownership of the separate Viral DoT remains subject to standard status attribution rules.

## Undecided

- DoT damage per tick, tick frequency, duration, current-vs-maximum HP basis, and how multiple Viral stacks change the DoT.
- Whether Poison and Slash stacks are consumed; whether the four-stack cap remains; boss-specific balancing.

## Shared System Rules

## Activation and Ownership

- The system checks for an eligible combination when a compatible status reaches its full-stack threshold, **before** resolving that status's standalone sixth-stack payoff.
- Only the player's own stacks and eligible **allied** players' stacks can contribute. Non-allied players cannot combine stacks with one another.
- Activation is automatic when the requirements are satisfied; it does not need a separate button press.
- When two allied players supply a combination, damage credit is split **50/50** between them.
- If multiple combinations compete for the same stacks, the first eligible pair to complete resolves first. Truly simultaneous event ordering has not been finalized.
