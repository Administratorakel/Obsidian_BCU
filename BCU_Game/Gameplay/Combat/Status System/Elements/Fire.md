# Fire — Elemental Status

**Identity:** Damage over time and explosive payoff  
**Category:** Elemental  
**Maximum stacks:** 6  
**Base stack duration:** 5 seconds (shared timer; refreshed by a successful application)

## Stack Progression

| Stacks | Effect |
| --- | --- |
| 1–2 | Small Fire damage per hit. |
| 3 | Applies **Burn**, which has its own internal timer. |
| 4–5 | Moderate Fire damage per hit. |
| 6 | **Combustion:** a large Fire burst around the target; applies Burn to enemies hit; consumes the Fire stacks. |

## Full-Stack Resolution

- On reaching 6 stacks, check for an eligible allied status combination **before** ordinary Combustion.
- If a combination is available, activate it according to that combination's rules.
- Otherwise, Combustion occurs immediately and consumes Fire stacks.
- Fire has **no independently established holding window** after ordinary Combustion.
- When the target is already frozen, Combustion can instead resolve as [[Cool Combustion]].

## Combinations

| Partner | Combination |
| --- | --- |
| [[Ice]] | [[Cool Combustion]] |
| [[Lightning]] | [[Arc Combustion]] |
| [[Poison]] | [[Toxic Combustion]] |
| [[Slash]] | [[Burned Wounds]] |

## Undecided

- Damage values, Burn duration/tick rate, Combustion radius and scaling.
- Interactions between Burn's independent timer and refreshed Fire stacks.
