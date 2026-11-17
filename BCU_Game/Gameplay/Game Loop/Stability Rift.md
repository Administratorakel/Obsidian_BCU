Rifts lose HP slowly over time. 
That is how the "Silent Agreement" Achievement can be gained.

Rare Instances:
[Floating ÷0 Fragments]
[Honest Rift]
[KillaQ Afterimage Event]
[Safe Rift]


Stability Rifts (World system):

**

- Slight [[BCU Game/Gameplay/Player/Stability]] regen boost inside
    
- Increased [[Instability Fragment]] drop rates
    
- Encourages farming + grouping
    

**

**

[[Game Progression]] & [[Economy System]] [[Stability Fragments]]:

- Mastery-specific [[upgrade materials]]
    
- Drop from Stability Rifts
    
- Core economy driver
    

**

**

To avoid power inflation issues:

Stability Breaches must be the ONLY reliable source of high-tier upgrade materials

Meaning:

- no passive farming abuse
    
- no trivial grinding elsewhere
    
- progression always tied to instability risk
    

****

CORE LOOP (FINALIZED STRUCTURE)

Stability Breach produces:

- Shields (rare drop = “manifested instability objects”)
    
- Upgrade resources (instability fragments)
    
- Energy (combat fuel for Vector Break)
    

Player uses these to:

- level Shield
    
- unlock Vector Break abilities
    
- evolve movement identity
    

****

🌌 2. STABILITY BREACH = RESOURCE ENGINE

You are essentially defining Breaches as:

“Instability condensers”

They don’t just spawn enemies — they generate structured progression material.

****

Stability Breach Drops:

A) Shield Drop (rare, identity-defining)

- physical manifestation of instability
    
- determines Vector Break style
    
- acts as long-term equipment base
    

---

B) Stability Fragments (common resource)

Used for:

- Shield leveling
    
- Vector Break upgrades
    
- unlocking modifiers
    

---

C) Energy Residue (combat loop resource)

- fuels immediate Vector Break usage
    
- recovered through combat
    

**

- Rift spawning
- Rift HP
- Duration
- Enemy waves
- Threshold triggers
- Rewards
- Stability regeneration
- Rift destruction

 **Stability Fragment:** single general fragment resource obtainable from Stability Rifts for now; no active variant list.
# Stability Rifts and Participation

**Status:** Rift lore and map scaling confirmed; reward calculation preserved as a working framework.  
**Related:** [[Movement and Vector Break]], [[Multiplayer and Instances]], [[Companions]], [[Equipment and Items]]

## Lore and map levels
- Rifts originate from **KillaQ's instability**, but their manifestations vary with **local surroundings and circumstances**.
- All such phenomena use the term **Stability Rift**.
- A map's Rifts have levels corresponding to the levels of its local enemies.
- **Map 1** hosts beginner-level enemies and beginner-level Rifts; later maps may have higher-level enemies and Rifts.
- Stability Rifts are **shared encounters in their map instance**, not private per-player enemy copies.
- They can provide **Stability Fragments**; only a single universal fragment type is presently established.

## Participation-based reward framework
Working previously discussed model: player contribution yields a hidden **Participation Score** (PS) from such sources as level-adjusted damage, statuses, control/opportunity creation, combos and combat milestones. Anti-exploit adjustments discourage artificial farming. Earlier discussions included a `0.9^n` dampening concept after repeated six-stack cycles, but detailed coefficients/conditions are not freshly finalized in this review.

The share used when choosing a recipient for a dropped item is:

`Share(player i) = PS_i / sum(PS of eligible players)`

**Roll order:** First roll whether an item drops; then, if it does, select **one recipient** using weighted Participation Shares. The specific item drop chance remains independent of the share distribution.

Example: with PS of 500/300/200, the respective shares are 50%/30%/20%. If a single item has 20% drop chance, its effective one-drop recipient probabilities are 10%/6%/4%.

- Participation values are not necessarily displayed publicly.
- Companions' damage and control might count toward their owner's score, but this attribution rule requires confirmation.
- Exact contribution weights, eligibility rules, party interactions and reward edge cases remain for the upcoming dedicated formula discussion.