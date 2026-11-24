# Status System

**Design philosophy:** Build stacks toward meaningful payoffs, reward deliberate status application, and support cooperation without making solo play ineffective.

## Categories

**Elemental:** [[Fire]], [[Ice]], [[Lightning]], [[Poison]]  
**Physical:** [[Slash]]  
**Otherworldly:** [[Instability]], [[Coptering]]

[[Instability]] and [[Coptering]] are **excluded** from universal combinations for now.

## Universal Rules

- Statuses can be applied through [[Normal Attacks]] and abilities capable of applying the relevant status; see [[Archetypes]].
- A successful application depends on Status Chance.
- The five universal statuses build toward **6 stacks**; incomplete sets ordinarily share a **5-second duration** refreshed by new applications.
- Each player maintains **their own** status stacks on each enemy.
- A player sees their own building stacks clearly. Allies see others' building stacks as smaller, muted indicators. A completed 6-stack set is clearly highlighted for its owner and allies.
- The completed-set behavior differs by status. In particular, [[Lightning]] can retain **one highlighted completed set** while immediately building a new set.
- Non-allied players cannot combine their status stacks with a player's stacks.

## Combination Activation

1. When a status reaches 6 stacks, **check for an eligible combination first**.
2. If a compatible allied status is already at 6 completed stacks, the combination activates **automatically**.
3. Otherwise, apply that status's own sixth-stack behavior.
4. Statuses are resolved in the order they reach 6 stacks; the first eligible pair combines. A simultaneous-event tie-breaker remains to be defined for implementation.
5. Statuses applied by combination effects can themselves build toward 6 and trigger further combinations.
6. When two allied players contribute to a combination, **damage credit is split equally** between them.
7. Combinations follow their **individual** duration and consumption rules; there is no blanket rule that every status retains a completed set after its sixth-stack effect.

### Distinct Sixth-Stack Behaviors

- **Fire:** Immediate Combustion and stack consumption when no combination qualifies; Fire on a currently frozen target can trigger [[Cool Combustion]].
- **Ice:** Freeze for 3 seconds; additional Ice hits extend Freeze by **1 second once per source**.
- **Lightning:** Discharge immediately applies a 1-second stun and 5-second party Attack Speed / Animation Speed buff. One completed set remains eligible for combinations for 5 seconds while new stacks build separately. A fresh completed set replaces the previous one; a new buff replaces, rather than stacks with, the previous buff. A combination consuming Lightning does not end the already-granted buff early.
- **Poison:** Poisonous Strikes; see [[Poison]] for its percentage-HP DoT, attack bonuses and provisional duration-extension progression.
- **Slash:** Maximum DoT without a standalone sixth-stack effect; see [[Slash]].

## Visibility

- **Solo:** Own stacks and status effects visible.
- **Party:** Own stacks and allies' stacks visible, with highlighted completed sets.
- **Outside party:** Players see status visuals and payoff effects, not other players' stack counts.
- Certain allied interactions may involve [[Wave Projection]]; see [[Multiplayer]] and [[Companions]].

## Universal Combinations

| Statuses | Result |
| --- | --- |
| Fire + Ice | [[Cool Combustion]] |
| Fire + Lightning | [[Arc Combustion]] |
| Fire + Poison | [[Toxic Combustion]] |
| Fire + Slash | [[Burned Wounds]] |
| Ice + Lightning | [[Shattering Voltage]] |
| Ice + Poison | [[Cryotoxicity]] |
| Ice + Slash | [[Frozen Wounds]] |
| Lightning + Poison | [[Neurotoxin]] |
| Lightning + Slash | [[Conductive Wounds]] |
| Poison + Slash | [[Viral Wounds]] |

## Implementation Questions Still Open

- Exact order for genuinely simultaneous status applications.
- Which incomplete, completed, and effect timers each status maintains when other effects trigger.
- How combinations interact with one another when several are eligible in one update; resolve without consuming the same stack set twice.
- Individual combination durations, damage values and unresolved consumption rules.
