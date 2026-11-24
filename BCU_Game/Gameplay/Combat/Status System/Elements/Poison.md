# Poison — Elemental Status

**Identity:** Pressure over time  
**Category:** Elemental  
**Maximum stacks:** 6  
**Base stack duration:** 5 seconds (shared timer; refreshed by a successful application)

## Stack Progression

| Stacks | Effect |
| --- | --- |
| 1–2 | Small Poison damage per hit. |
| 3 | Small Poison damage and a Poison DoT totaling **5% of the target's maximum HP** over its duration. |
| 4–5 | Moderate Poison damage per hit. |
| 6 | **Poisonous Strikes:** Poison DoT totaling **15% of maximum HP** over its duration; initiator gains **1% HP damage** with [[Normal Attacks]], and party members gain **0.5% HP damage** with [[Normal Attacks]]. |

## Full-Stack Resolution

- On reaching 6 stacks, check for an eligible allied combination **before** ordinary Poisonous Strikes.
- Otherwise, Poisonous Strikes activates according to the established sixth-stack behavior.
- Recorded duration-extension progression: **+1.0, +0.8, +0.6, +0.4, +0.2, +0.05, 0**. The exact event that advances this sequence should be documented before implementation.

## Combinations

| Partner | Combination |
| --- | --- |
| [[Fire]] | [[Toxic Combustion]] |
| [[Ice]] | [[Cryotoxicity]] |
| [[Lightning]] | [[Neurotoxin]] |
| [[Slash]] | [[Viral Wounds]] |

## Undecided

- DoT tick frequency and distribution across the duration.
- Poisonous Strikes duration and the precise duration-extension trigger.
- Stack consumption and continued combination availability after Poisonous Strikes activates.
- Whether the initiator receives the party bonus in addition to their own 1% bonus.
