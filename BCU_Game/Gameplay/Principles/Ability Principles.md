******

### Ability damage resistance

Should abilities also be able to have specific resistance to damage interruption, even though the default is that damage doesn't interrupt them?

A) No — damage never interrupts abilities anyway  
  

Ability damage resistance: A — no separate mechanic needed. ✅

Normal damage never interrupts abilities. Only displacement/status effects can interrupt them, unless an ability has its own specific resistance.

**

### Getting hit during an ability

ability continues normally unless a status effect interrupts it. ✅

So normal damage doesn't cause combat actions to flinch. Status effects are the exception.

**

### Ability during another ability, Ability chaining — finalized for now

- Abilities normally cannot be canceled immediately by another ability.
    
- There is a small input buffer window near the end of an ability.
    
- Pressing the next ability during that window makes it activate immediately when the current ability ends.
    
- This allows smooth ability → ability combos without requiring perfect timing.
    
- Some abilities may explicitly allow cancellation by another ability. We'll define those individually later.
    
- Dash remains the universal emergency/cancel movement and can interrupt abilities where allowed by the ability's rules.
    

We won't create a global rule for repeating the same ability.

Ability recasting will be handled individually based on:

- cooldown,
    
- whether it can chain,
    
- whether it can cancel another ability,
    
- and its specific behavior.
    

That keeps the combat system flexible. Some abilities might have stacks, so chaining could be possible.

**