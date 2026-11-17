- Damage contribution
- Support contribution
- Eligibility
- Loot distribution
- Participation rewards

Loot uses:

Potential Participation Weight

Factor:

- Damage contribution
    
- Status contribution
    
- Milestone contributions
    
- Player level vs  enemy/rift level
    

Goals:

- Reward actual participation
    
- Avoid pure DPS ownership
    
- Encourage cooperation
    

Loot:

- Single winner per item
    
- Some events/rifts can have multiple winners
    
- Items are tradable
    

Dead players:

- Participation freezes
    
- If they win loot:
    
- → party members can pick up for them
    
- → first ally pick it up receives for the player
    

**

[[Stability Rift]]

# BCU — Loot Distribution Formula

**Version:** 0.2  
**Last updated:** 15.11.2026  
**Status:** Work in Progress

## 1. Participation Score (PS)

Each player earns a Participation Score based on five contribution categories.

$$  
PS_i=(D_i+S_i+M_i+C_i+O_i)\cdot A_i  
$$

|Symbol|Category|Base Value|
|---|---|---|
|D|Damage|Relative damage contribution|
|S|Status Effects|1 per stack|
|M|Status Milestones|2 at 3 stacks, 4 at 6 stacks|
|C|Status Combinations|5 per combination|
|O|Opportunity/Control|2 per enemy controlled|
|A|Anti-exploit adjustments|R × P × AD|

- D, S, M, C and O are normalized individually between 0 and 1, relative to other eligible participants.
    
- Unused categories contribute 0.
    
- No +1 baseline.
    

## 2. Damage (D)

Damage contribution is adjusted by **1% per level difference**, capped at ±25 levels.

$$  
W_i=1+0.01\cdot\operatorname{clamp}(L_t-L_i,-25,25)  
$$

$$  
D_i=\frac{DMG_i\cdot W_i}{\sum_j(DMG_j\cdot W_j)}  
$$

- 25+ levels below target: +25%
    
- Same level: 0%
    
- 25+ levels above target: −25%
    
- Only affects loot contribution, not actual damage.
    

## 3. Status Effects (S)

- 1 point per applied status stack.
    
- Repeated applications have diminishing returns.
    
- Decay: `0.9^n`
    
- Maximum decay stacks: 10.
    
- Minimum multiplier: approximately 0.349.
    

$$  
S_{\text{raw},i}=\sum_{n=0}^{N_i-1}0.9^{\min(n,10)}  
$$

## 4. Status Milestones (M)

|Milestone|Points|
|---|---|
|3rd status stack|2|
|6th status stack|4|

$$  
M_{\text{reward}}=M_{\text{base}}\cdot0.9^{\min(n,6)}  
$$

- Maximum decay stacks: 6.
    
- Milestone rewards are shared equally among contributing party members.
    
- Players outside a party cannot see other players' status stacks.
    
- Reaching the same milestone repeatedly increases decay.
    

## 5. Status Combinations (C)

- 5 points per triggered combination.
    
- Decay: `0.9^n`
    
- Maximum decay stacks: 6.
    

$$  
C_{\text{reward}}=5\cdot0.9^{\min(n,6)}  
$$

## 6. Opportunity/Control (O)

- 2 points per enemy successfully crowd-controlled.
    
- Examples: stun, freeze, knockback, pull.
    
- AoE abilities award points separately for each affected enemy.
    
- Decay: `0.9^n`
    
- Maximum decay stacks: 4.
    

$$  
O_{\text{reward}}=2\cdot0.9^{\min(n,4)}  
$$

## 7. Anti-Exploit Adjustments (A)

$$  
A_i=R_i\cdot P_i\cdot AD_i  
$$

### R — Repetition

$$  
R_i=0.85^{\min(r_i,4)}  
$$

- Maximum decay stacks: 4.
    
- Minimum multiplier: approximately 0.522.
    
- Exact conditions triggering repetition penalties are undecided.
    

### P — Participation

$$  
P_i=\frac{T_{\text{active},i}}{T_{\text{potential},i}}  
$$

- Compares active combat time against potential combat time.
    
- Example: 80 seconds active during a 100-second encounter = 0.8.
    
- Exact criteria for active participation are undecided.
    

### AD — Action Diversity

$$  
AD_i=1  
$$

- Remains 1 as long as contribution categories are balanced.
    
- Players should not be forced to diversify their combat roles.
    

## 8. Loot Distribution

Each dropped item is assigned to one eligible participant according to their Participation Score.

### Formula A — Contribution-Based

$$  
L_i=\frac{PS_i}{\sum_j PS_j}  
$$

100% of loot probability is determined by relative participation.

### Formula B — Balanced (50/50)

$$  
L_i=0.5\left(\frac{PS_i}{\sum_j PS_j}\right)+\frac{0.5}{N}  
$$

- 50% based on Participation Score.
    
- 50% distributed equally among eligible participants.
    
- N = number of eligible participants.
    
- Applies across parties and solo players.
    

**Final choice between Formula A and B is pending.**

## 9. Loot Rules

- Each item independently rolls whether it drops.
    
- Each dropped item has exactly one recipient.
    
- Different items can have different recipients.
    
- Party members can collect items belonging to defeated allies.
    
- Participation Scores and loot probabilities are hidden from players.
    

## 10. Open Questions

- Define repetition penalty triggers (R).
    
- Define detection of active combat participation (P).
    
- Establish minimum loot eligibility requirements.
    
- Choose between original and 50/50 distribution.
    
- Balance normalized contributions across categories.
    
- Test the system with multiple player builds and party configurations.
    

## 11. Important Design Principle

The system should reward **meaningful combat participation**, not simply raw damage.

Damage dealers, status specialists, combo-focused players, and crowd-control players should all have opportunities to earn loot.

Each contribution category is normalized independently. Therefore, the original point values determine relative contributions _within_ a category, while every active category has equal total weight.

The system should remain resistant to exploitation without unfairly penalizing specialized builds.

### Current design

The original formula distributes rewards according to each player's Participation Score:

\[ P_i=\frac{PS_i}{\sum_j PS_j} \]

You are now considering a hybrid approach between the original formula and a **50/50 distribution system**.

One possible interpretation is:

- **50% participation-based:** Players receive a weighted chance based on their contribution.
- **50% equal distribution:** Every eligible participant receives an equal share of the remaining probability.

For example, with three players:

|Player|Participation|Original formula|50/50 hybrid|
|---|--:|--:|--:|
|A|60%|60%|46.67%|
|B|30%|30%|31.67%|
|C|10%|10%|21.67%|

The hybrid formula would be:

\[ \boxed{P_i=0.5\frac{PS_i}{\sum_j PS_j}+0.5\frac{1}{N}} \]

Where \(N\) is the number of eligible participants.

This preserves the advantage of contributing more while giving lower-contributing players a better chance of receiving rewards.