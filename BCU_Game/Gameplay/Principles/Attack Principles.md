****

### Attack after target death

If the enemy dies during the player's attack animation, should the attack:

  
C) Continue and potentially hit another enemy in the attack's area/range  
D) Depends on the weapon/attack type

C and D

Good. C + D fits the weapon-specific combat design.

### Target death during an attack — finalized

- The current attack continues normally.
    
- If the attack can naturally hit another enemy, it may do so.
    
- Whether it actually transfers/hits another enemy is weapon/attack-specific.
    
- Single-target attacks can simply finish with no additional target.
    
- AoE, cone, piercing, sweeping, etc. can potentially hit other enemies according to their individual rules.
    
- The dead target can immediately be replaced by selecting another target.
    

### Auto-Attack and target death

If Auto-Attack is ON and the current target dies, should the player:

A) Immediately stop attacking and movement  
  

Auto-Attack after target death: A — immediately stop attacking and movement. ✅

No automatic target switching. The player must choose the next enemy manually.

### Auto-Attack and target becoming unreachable

If Auto-Attack is ON and the target becomes unreachable because of terrain, we've established the player tries to navigate around it.

What should happen if pathfinding cannot find a route?

Stop temporarily, but resume if the target becomes directly reachable again

  

Unreachable target: E — stop temporarily, but resume when reachable again. ✅

So Auto-Attack doesn't give up or clear the target just because navigation fails.

### How often should Auto-Attack retry?

If the target remains unreachable, should the game:

A) Continuously check for a route  
B) Check periodically, e.g. every 0.5–1 second  
C) Only retry when the target moves  
D) Only retry when the player moves  
E) Leave the exact retry behavior for implementation later

Retry after the enemy finished moving, but Also e

Retry behavior: E — leave the exact implementation behavior for later, with one design guideline:

- If the enemy is actively moving, don't constantly recalculate.
    
- Once the enemy finishes its movement, retry the route/reachability.
    
- The exact fallback/retry timing can be decided during implementation.
    

**

### Normal attack movement

Melee weapons

- Normal attacks generally move the player slightly forward.
    
- They continue doing so until the attack reaches its intended range.
    
- This helps maintain contact with an enemy if the player was pushed backward.
    
- The amount of movement can vary by weapon/attack.
    

Ranged weapons  
Instead of three movement states, we can make it a two-direction distance system:

- Too far from target → move toward target while attacking.
    
- Close enough / too close → move backward while attacking.
    

So the weapon has an ideal attack distance/range, and the attack movement tries to maintain that distance.

For example:

TOO FAR             IDEAL RANGE              TOO CLOSE

Player →→→ Enemy        Player → Enemy        Player ←← Enemy

   move forward            attack              move backward

That's a really interesting way to make combat naturally maintain spacing without requiring the player to manually micro-adjust every attack.

I'd keep the exact thresholds and strength of this movement open for later, because they'll probably differ significantly between Bow, Dual Guns, Warfans, Whip, Glaive/Chakram, etc.

  

### Attack targeting

Default mode

- Attack follows the player's current facing direction.
    
- No target is required.
    
- Movement/attack input determines where you're attacking.
    

Target mode — toggleable

- Player clicks an enemy → that enemy becomes the target.
    
- Attacks are directed toward that enemy.
    
- The player continues attacking that target until:
    

- the player clicks somewhere else / removes the target, or
    
- the enemy dies/disappears.
    

The ranged distance-management system can then use the selected target when target mode is active.

One thing I'd clarify later is what happens to the player's facing/rotation while targeting—whether the character automatically faces the target or only attacks toward it while movement remains independent.

### Target movement

- No target: attacks follow facing/input direction.
    
- Target selected: attacks automatically face/manage distance toward that target.
    
- Melee: generally moves slightly toward the target until the intended attack range is reached.
    
- Ranged: automatically moves toward or away depending on current distance.
    
- Auto-distance movement: enabled by default, with a future toggle.
    

### Auto-attack toggle

OFF

- Selecting an enemy can still be possible.
    
- The player does not automatically chase.
    
- Attacks only happen when the player gives the attack input.
    
- Distance-management movement during an attack can still exist according to our previous rule.
    

ON

- The selected enemy becomes the active combat target.
    
- The character automatically moves toward/away from it.
    
- When within attack range, the character automatically attacks.
    
- If the enemy moves away, the character follows it.
    

### Ranged auto-attack positioning

For ranged weapons, instead of simply stopping at the minimum attack range:

The character tries to maintain a distance where it can perform at least two attacks in succession.

That's particularly useful if the first two attacks of an attack loop are faster. It means the player doesn't constantly interrupt the attack sequence by chasing after the target.

We can later define this per weapon because Bow vs Dual Guns vs Warfans, etc. may want different preferred distances.

### Auto-attack and Target death

- Target dies/disappears → stop attacking immediately.
    
- Stop automatic movement toward that target.
    
- No automatic target switching.
    

And B is a potential separate farming feature, rather than part of the normal Auto-Attack system. That could be interesting for players who deliberately want to let their character farm while they're doing something else.

### Auto-target farming

If you eventually add the automatic nearest-enemy behavior as a separate feature, should it be something the player actively unlocks/earns, rather than simply being available from the beginning?

For example:

- premium/convenience feature
    
- late-game unlock
    
- quest reward
    
- item/equipment
    
- subscription/service
    
- something else
    

  

After reaching Mastery 100 and performing the first mastery reset, the player unlocks an optional automatic farming/target-switching feature.

We'll leave the exact implementation and whether/how it is monetized for later.

### Target selection range

Target selection has no distance restriction:

- If the player can click the enemy, it can become the target.
    
- The target system itself doesn't care about distance.
    
- The weapon's attack range and auto-movement determine what happens afterward.
    
- This also works nicely with long-range weapons.
    

  

### Target behind terrain

- Target stays selected.
    
- Auto-Attack doesn't attack through terrain.
    
- The character attempts to move around the terrain to regain a clear path.
    
- While repositioning, no attacks occur.
    
- Once the target is visible/reachable again → attacking resumes.
    
- The character doesn't switch targets automatically.
    

This also gives the automatic combat system a basic navigation behavior without requiring a full MMO-style AI.

****

### Ability during an attack

Ability during an attack: A — ability immediately cancels the normal attack. ✅

That gives us a clear priority:

Dash / Ability > Normal Attack > Movement

****

### Getting hit during an attack

Getting hit during an attack: A — continue the attack, unless a status effect specifically causes an interruption/control effect.

So normal enemy damage doesn't stop the player's attack animation or action.

**