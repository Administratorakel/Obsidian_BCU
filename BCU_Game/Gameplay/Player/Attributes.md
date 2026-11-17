
| Attribute | Primary purpose                       | Secondary effects            |
| --------- | ------------------------------------- | ---------------------------- |
| VIT       | HP                                    | knockback resistance         |
| STR       | Physical DMG, Physical Defense        | Knockback strength           |
| INS       | Magical DMG, Magical Defense          | Status Chance, Elemental DMG |
| AGI       | Attack speed, Movement responsiveness | Critical Chance              |


- Attribute allocation
- Automatic attributes
- Manual attributes
- Attribute reset mechanics
- Numerical scaling
- Connections to [[Character Progression]]



| VIT gives | Max HP                             | +30   |     |
| --------- | ---------------------------------- | ----- | --- |
|           | HP Reg                             | +0.1% |     |
|           | Knockback Res                      | +0.3% |     |
|           |                                    |       |     |
| STR gives | Ph. Attack                         | +1    |     |
|           | Shield W. Damage                   | +0.8  |     |
|           | Knockback                          | +0.5% |     |
|           | H. Attack Impact                   | +0.3% |     |
|           | Stagger Chance?                    | +0.2% |     |
|           |                                    |       |     |
| AGI gives | Attack Speed                       | +0.5% |     |
|           | Movement Speed                     | +0.3% |     |
|           | Critical Chance                    | +0.2% |     |
|           | Animation Recovery Speed?          | +0.3% |     |
|           |                                    |       |     |
| INS gives | Ma. Attack                         | +1    |     |
|           | Stability Energy Regen             | +0.2% |     |
|           | Status Effect Potency              | +0.3% |     |
|           | Status Chance                      | +0.2% |     |
|           | Rift Interaction Efficiency        | +0.3% |     |
|           | Vector Break Conversion Efficiency | +0.2% |     |

### Stat scaling

- **VIT:** HP bonus increases with level. Current idea: **+5 HP per player level** to the VIT HP contribution.
- **STR:** Fixed physical-damage increase per point.
- **INS:** Fixed magical-damage increase per point.
- **AGI:** Small fixed increase to Crit per point.
- **AGI Movement Speed:** Fixed increase per point.
- **No hard stat caps for now.**

### Player movement

- Running speed = 20
- Walking speed = 10
- Walking is toggleable
- Instant acceleration/deceleration
- Instant 180° direction changes
- No sprint
- No stamina
- No jumping
- Movement speed can be modified
- Walk toggle = “Shift”
- Movement modifiers stack additively and multiplicatively

### Attack Speed

Attack Speed affects **all three**:

- Attack animation time
- Attacks per second
- Recovery time


### Movement Speed

AGI-derived Movement Speed affects:

- Normal running
- Click-to-move
- Attack movement
- **Dash speed**


Critical Scaling through AGI


## Stat points
- Each level-up grants **4 attribute points** during the normal progression framework.
- **First Journey:** 2 manual points + 2 automatic points per level.
- The automatic two points are influenced by overall progress **across all weapon masteries**, rather than only the currently equipped weapon or highest mastery.
- The precise allocation algorithm is **undecided**: a possible combination of proportional influence and mastery milestones, not yet finalized.
- **After the first Journey Repeat:** all 4 points per level are manually allocatable. No automatic allocation.
- Manual points can be distributed when the player chooses.
## Defense
- Physical (**PH**) and Magical (**MA**) Defense are the current categories.
- Exact formulas and how these defenses are derived remain **undecided**.
- Older proposals about generic flat-plus-percentage defense and diminishing returns should **not** be treated as current confirmed calculations.
## Additional notes
- AGI affects responsiveness; no fixed running-speed or critical-damage bonus from earlier drafts is confirmed.
- Exact attribute damage coefficients and stat caps require future balance decisions.