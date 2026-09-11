upgrades to [[Vector Break]] after equipping a [[Shield Core]]

**

### Base Dash

- Available without weapon
    
- Still called Dash with weapon equipped
    
- 2 charges maximum
    
- Each charge has independent 5-second cooldown
    
- Cooldown starts when Dash begins
    
- Only one Dash active at a time
    
- Second Dash can start immediately after first finishes
    
- 3-unit range for now
    
- 1-second duration for now
    
- Current movement input determines direction
    
- No input → character's current forward
    
- Character immediately faces Dash direction
    
- Camera does not rotate
    
- Dash cannot be cancelled
    
- Initial invulnerability frames
    
- 0.5 seconds invulnerability duration
    
- No collision behavior with enemies
    
- Dash can cross small gaps (as long as walkable ground in range)
    

**### Weapon-modified Dash

- Every weapon modifies Dash
    
- Weapon determines physical Dash properties
    
- Weapon can modify distance/speed/damage/etc.
    
- Weapon can add physical effects
    
- Final Sword Dash behavior (?)
    
- Final modifiers for other weapons later (?)
    
- How weapon attack animation controls movement (?)
    
- Dash uses % weapon dmg
    

****

### Dash gap behavior

1. Dash follows physics
    

- The player moves forward according to Dash speed/duration.
    
- Gravity still applies during the Dash.
    
- No jumping or manual air contro (Magic Gauntlets might have an active input during VB).
    

3. Small gaps can be crossed
    

- If the Dash carries the player over a gap and a valid walkable surface exists at the landing point, the Dash succeeds.
    

5. Invalid landing = Dash stops
    

- If there is no valid ground at the end of the Dash, the player cannot complete the traversal.
    
- The player should stop at the last valid position rather than fall.
    

7. No wall phasing
    

- Walls still stop the player's physical movement.
    
- The Dash animation continues to its end.
    

9. Dash remains skill-based
    

- Players can use Dash to reach small hidden areas or shortcuts.
    
- Larger gaps remain inaccessible without a future mechanic specifically designed for them.
    

So the core rule is:

Dash may cross empty space, but it may only finish if the destination has valid ground.

### Dash gap scaling — food for thought

The valid landing detection stays universal, but the distance a Dash can physically traverse can vary.

For example:

- Normal Dash: small gaps
    
- Long-range weapon Dash: medium gaps
    
- High-speed Dash: potentially larger gaps
    
- Special weapon Dash: could have unique traversal behavior
    
- Vector Break: Core effects could potentially further modify traversal
    

A longer Dash doesn't automatically allow crossing a gap. It simply gives the physics simulation more distance/time to reach a valid landing point.

If a Dash has no valid landing, it continues until it reaches the maximum physically permitted position (e.g. an invisible wall/cliff boundary), then stops.

That also means a longer Dash variant could potentially reach farther before being stopped.

### Dash landing rule

The Dash has a maximum movement distance and continuously looks for a valid place where the player could stand.

- It always attempts to travel its full Dash distance.
    
- If it encounters a gap:
    

- If there is a walkable surface within the remaining Dash distance → land there.
    
- If there isn't → stop at the edge/boundary before the gap.
    

- If there are multiple gaps, it can only progress through them if each required landing point is reachable within the remaining Dash distance.
    

Your example:

START ───── GAP ───── LANDING ───── GAP ───── LANDING

  │                         │

  └──── Dash range ─────────┘

### Every gap requires a landing calculation

The Dash system always asks:

“Can I continuously travel to a surface the player can stand on?”

A tiny gap:

█████  ░  █████

      ↑

   gap

If the other side is reachable → Dash crosses it.

A large gap:

█████          ░          █████

               ↑

          unreachable

→ Dash stops at the edge.

Advantages:

- One consistent system.
    
- No arbitrary “tiny gap” threshold.
    
- Weapon Dash variants automatically behave correctly.
    
- Easy to reason about later.
    

  

Require a small amount of safe ground around the player — e.g. the player's entire capsule must fit on the surface.

### Dash into slopes

  

If the player can walk on the slope, the Dash can travel over it. If the slope is not walkable, it acts as a barrier.

No separate Dash slope rules.

### Downward gaps

What if the Dash goes downward rather than across a gap?

For example:

START █████

          \

           \____ █████

                LANDING

Good. Downward traversal is allowed.

So Dash doesn't care whether the valid landing surface is:

- roughly level,
    
- slightly higher,
    
- or significantly lower,
    

as long as the player can normally walk on the destination surface and the Dash can physically reach it.

  

If the player can walk on it, the Dash works on it.

So no separate Dash incline restriction.

### Future modifier idea

Terrain inclination could modify effective Dash distance:

- ⬆️ Uphill → shorter Dash
    
- ➡️ Flat → normal Dash
    
- ⬇️ Downhill → longer Dash
    

We'll keep that as food for thought, not a finalized mechanic.

  

Dash gets its effective distance locked at the moment it starts, based on the starting incline.

For example:

- Flat start → normal Dash distance.
    
- Starting uphill → shorter predetermined distance.
    
- Starting downhill → longer predetermined distance.
    
- During the Dash, the terrain can change and the Dash follows it to a degree.
    
- If the terrain becomes too steep to follow → the Dash stops there, rather than recalculating its range or climbing indefinitely.
    

So importantly, the Dash's range isn't continuously recalculated during the Dash.

  

If the Dash encounters terrain too steep to follow:

It behaves like a wall. The player moves against it until the Dash ends.

So the Dash does not stop abruptly, and it does not recalculate its range.

  

So from a cliff edge:

- Dash can immediately leave the ground.
    
- It searches for a valid landing within its predetermined Dash range.
    
- If it finds one → it reaches that landing.
    
- If it finds no walkable surface within range → it travels outward until the cliff/world boundary prevents further movement.
    
- It never falls just because the player started a Dash at an edge.
    

This gives us a pretty coherent traversal model now.

### walkable surface below the cliff. Example:

START █████

              \

               \

               █████  ← walkable lower area

  
  

So vertical height itself isn't a restriction. If the lower surface is within the Dash's predetermined effective range and the player can normally walk on it, it's a valid landing.

One important distinction we've established:

- Walkability determines whether terrain can be followed/landed on.
    
- Dash range determines how far the Dash can reach.
    
- Starting incline determines the Dash's effective range.
    
- Terrain encountered during the Dash does not change that range.
    
- Too-steep terrain behaves like a wall.
    
- No reachable landing → Dash continues to the physical/world boundary rather than falling.
    

### Obstacles

Normal environmental obstacles stop the Dash like walls.

That gives us a very consistent rule:

Dash ignores enemy collision, but respects world/environment collision.

  

Dash passes through enemies completely. The weapon/Dash effect determines what happens to them.

And we'll keep large enemies potentially blocking Dash as a future consideration.

  

Enemies have no collision with the player's body or with other enemies. So there's no need for the Dash system to calculate enemy avoidance at all.

The Dash only needs to care about:

- 🌍 Environment collision → walls/obstacles stop it.
    
- 🏔️ Walkable terrain → can be followed/landed on.
    
- 🕳️ Gaps → search for a valid landing.
    
- 📐 Incline → affects initial Dash distance; too-steep terrain acts as a wall.
    
- 👾 Enemies → completely ignored for movement.
    

  

So our movement collision model is becoming very clean:

- Environment ↔ Player: collision
    
- Environment ↔ Dash: collision
    
- Enemy ↔ Player: no collision
    
- Enemy ↔ Enemy: no collision
    
- Player ↔ Player: no collision
    
- Dash ↔ Enemy: no collision
    
- Dash ↔ Player: no collision
    

  

Suppose there's something like a pressure plate, hidden trigger, quest area, pickup, or special object in the Dash path.

Should Dash still activate/pass through those normally?

Triggers do not interfere with Dash by default. Individual objects can override this later if needed.

  

Dash can cancel an attack, but an attack or ability cannot cancel an active Dash.

That gives Dash a strong commitment once activated.

### Dash chaining

During the active Dash:

- Normally, Dash cannot be interrupted.
    
- Near the end of the Dash, there is a small input window.
    
- If Dash is pressed during that window → the next Dash activates immediately when the current one ends.
    
- Pressing it earlier does nothing/doesn't queue it.
    

**