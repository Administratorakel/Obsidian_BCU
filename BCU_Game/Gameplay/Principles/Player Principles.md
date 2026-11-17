********

105 — Death penalty: EXP loss + Coptering debuff ✅  
Coptering is a temporary debuff inspired by the DracoVentus/KillaQ confusion incident where the Borakel started coptering. While active, kills grant 50% of their normal EXP.

That's a very BCU-style death penalty. 😄

**

### What happens when the player dies?

If the player reaches 0 HP during an attack or ability, should the action:

A) Stop immediately and the death animation takes over  
  

Death during an action: A — action stops immediately. ✅

At 0 HP:

- Current attack/ability stops immediately.
    
- Death state takes over.
    
- No further buffered actions execute.
    
- Dash is also stopped if the killing hit connects.
    

### Death and target state

  

Death and target state: C — clear the target focus on respawn. ✅

So while dead, the target can technically remain stored, but the target UI/active targeting state is reset when the player respawns.

### Enemy death

When the targeted enemy dies, should the target UI:

  

Enemy death: B — briefly remain at 0 HP, but immediately replaceable. ✅

So:B with being able to be replaced immediately by the next target

- Target UI remains briefly after death.
    
- HP shows 0.
    
- Clicking another enemy immediately replaces the dead target.
    
- No automatic target switching.
    
- If nothing else is selected, the dead target eventually clears.
    

**

### Enemy attacks and player abilities

If an enemy lands a special attack that normally causes displacement, but the player is currently performing an ability, should the ability be interrupted and displaced as we established?

  

Enemy displacement vs. abilities: B — abilities can have specific resistance. ✅

General rule:

- Normal displacement → interrupts and moves the player.
    
- An ability can be flagged as displacement-resistant, allowing it to continue.
    
- This resistance is separate from ordinary damage resistance.
    

**

### Knockback / displacement

it moves the player and cancels the current attack/ability. ✅

That gives displacement a meaningful combat impact without making ordinary damage interruptive.

**