# Hammer — Weapon Identity

**Status:** Core identity established; balancing and implementation pending  
**Combat Identity:** Impact Zone Propagation  
**Damage Type:** Physical

## 1. Weapon Identity

The Hammer is a slow, powerful melee weapon specializing in impact, shockwaves, and battlefield control.

Its defining mechanic, **Impact Zone Propagation**, allows the player to create connected areas through abilities and generate shockwaves across them using normal attacks.

The weapon should:
- Reward positioning and battlefield preparation.
- Deliver powerful, deliberate strikes.
- Encourage alternating between abilities and normal attacks.
- Excel at damaging groups through connected Impact Zones.
- Feel distinct from the Fighting Slab's momentum and the 2H Sword's cleaving mechanics.

**Design philosophy:** Abilities establish the battlefield, while normal attacks exploit it.

## 2. Impact Zones

Certain Hammer abilities create circular Impact Zones.

### Zone Properties
- Each newly created Impact Zone lasts **4 seconds**.
- Zones remain separate objects and never merge.
- Overlapping zones function as connected areas for shockwave propagation.
- Multiple overlapping circles can create larger, irregularly shaped areas.

### Overlapping Zones

When a new Impact Zone overlaps an existing zone:
1. The existing overlapping zone gains **2 additional seconds** of duration.
2. The newly created zone starts with its normal 4-second duration.
3. Both zones retain independent durations.
4. Every existing zone overlapping the newly created zone receives the duration extension.
5. Overlapping does not automatically increase damage.

This allows the player to maintain existing zones while extending battlefield coverage.

## 3. Shockwave Generation

Normal Hammer attacks interact with Impact Zones.

### Trigger Conditions

- The **first enemy struck by a normal attack** determines whether a shockwave activates.
- If that enemy is inside an Impact Zone, one shockwave is generated.
- Only one shockwave can be generated per normal attack.
- Additional enemies struck by the same normal attack do not trigger further shockwaves.
- Normal attacks do not need to strike the ground.

### Shockwave Propagation

- Shockwaves originate at the triggering enemy.
- They propagate throughout the connected Impact Zone area.
- Overlapping zones allow shockwaves to travel between them.
- Propagation stops at the boundary of the connected area.
- An enemy can only be damaged once by the same shockwave, even when standing inside multiple overlapping zones.
- Shockwaves do not consume or destroy Impact Zones.

## 4. Shockwave Damage

Shockwave damage decreases with distance from its origin.

The damage approaches **10% of the triggering hit's damage**, but never mathematically reaches that value.

### Proposed Formula

D(d)=D_0(0.1+0.9e^{-kd})

Where:

- (D(d)) = Shockwave damage at distance (d).
- (D_0) = Damage of the normal attack that triggered the shockwave.
- (d) = Distance from the shockwave origin.
- (k) = Damage decay constant (undecided).

### Damage Rules

- Damage is highest near the triggering enemy.
- Damage decreases continuously with distance.
- Damage approaches 10% asymptotically.
- Rounding may eventually produce exactly 10%.
- Enemies in overlapping zones never receive duplicate damage from the same shockwave.
- The decay rate will be balanced during implementation.

**Note:** The formula is provisional. The mathematical behavior is established, but numerical scaling is not finalized.

## 5. Stance Interactions

The Hammer supports the three normal attack stances.

|Stance|Interaction|
|---|---|
|Standard|Balanced damage, reach, and shockwave opportunities|
|Wide|Larger attack coverage and greater potential to strike enemies across Impact Zones|
|Fast|More frequent attacks and potential shockwave activations|

All stances follow the same shockwave generation rules.

No stance-specific Impact Zone mechanic has been established.

## 6. Vector Break / Bulletjump

**Previously established characteristics:**
- Increased damage.
- Reduced travel distance.
- Additional shockwave effect.

Exact interactions between Vector Break and Impact Zones remain undecided.

## 7. Combat Gameplay Loop

1. Use a Hammer ability to create an Impact Zone.
2. Strike an enemy inside the zone with a normal attack.
3. Generate a shockwave that propagates throughout the zone.
4. Create additional overlapping zones to expand coverage and extend existing durations.
5. Continue using normal attacks to exploit the connected area.
6. Reposition or establish new zones as enemies move.

The Hammer rewards maintaining useful battlefield coverage rather than simply stacking abilities in one location.

## 8. Unresolved Questions

- Which abilities create Impact Zones?
- Exact Impact Zone radius.
- Shockwave propagation speed.
- Exact damage decay constant.
- Whether the physical Hammer strike follows standard multi-target damage falloff.
- How shockwave damage interacts with enemy Defense.
- Whether shockwaves apply additional effects such as knockback.
- Impact Zone visual effects and animations.
- Exact interactions with Vector Break.
- Balance between Standard, Wide, and Fast Stances.

These details will be addressed during the Hammer's actual development in Unity.

---

## Core Design Principle

**The Hammer transforms abilities into temporary battlefield coverage and normal attacks into propagating shockwaves.**

Its strength comes from deliberate positioning, connected Impact Zones, and powerful impacts rather than continuous attack momentum.