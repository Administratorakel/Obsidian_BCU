****  
**

### Dash damage interaction — finalized

- During the dodge window, qualifying hits are dodged completely.
    
- Hits outside that window can damage the player.
    
- A hit that successfully damages the player can also interrupt the Dash.
    
- Displacement follows the same principle: if the player successfully avoids the hit, they avoid its displacement; if the hit connects, its displacement can interrupt the Dash.
    
- Exactly which attacks can be dodged/what the window is will be defined later.
    

This fits the physics-based Dash much better.

### Dash dodge window

Dash dodge window: short window around the start of the Dash. ✅

For now:

- Dash begins → brief dodge window
    
- After that → Dash is vulnerable
    
- A successful hit during the vulnerable portion can damage and interrupt the Dash.
    
- Exact duration can be tuned later.
    

### What happens when Dash is interrupted?

stop immediately, then apply the hit's displacement/knockback. ✅

So the sequence is:

Dash → hit connects → Dash stops → damage applies → displacement applies.

### Dash and status effects

If a hit during the vulnerable part of Dash applies a status effect that normally causes stun, slow, freeze, etc., should the status:

Dash status effects: apply normally after the Dash is interrupted. ✅

So a successful hit during the vulnerable portion can:

1. Interrupt the Dash.
    
2. Deal its damage.
    
3. Apply its displacement.
    
4. Apply its status effect normally.
    

### Dash into enemy attacks

If the player Dashes through an enemy's active attack hitbox during the dodge window, should the Dash's dodge:

  

completely avoids the hit. ✅

### Dash/Vector Break dodge feedback — finalized

- Normal attacks: no special dodge feedback.
    
- Special attacks specifically designed to be dodged/countered by Dash/Vector Break: show dedicated feedback.
    
- The exact effect/sound can be designed together with each special attack.
    
- Successful dodging still fully avoids the hit.
    

### Counter attacks

For special attacks that Vector Break is specifically designed to counter, should a successful dodge:

decided individually by the weapon. ✅

So Vector Break can have different outcomes depending on the equipped weapon:

- Some weapons → purely dodge.
    
- Some → dodge + counterattack.
    
- Some → dodge + special effect.
    
- Some special attacks may interact uniquely with specific weapons.
    

That fits the weapon-identity approach nicely.

****

### Crowd control after Dash

Dash is not globally invulnerable. The Dash has a specific damage-dodge window.

**
### Knockback during Dash

Dash is immune to both damage and displacement (EDIT: in the first few frames).

So while Dashing:

- Damage → ignored.
    
- Knockback/push → ignored.
    
- Pull → ignored.
    
- Normal enemy collision → ignored.
    
- Dash continues according to its movement/collision rules.
    

**

Near the end of Dash:

- Attack input can be accepted.
    
- Ability input can be accepted.
    
- The action starts immediately after the Dash finishes.
    
- Before that window, the Dash has priority and cannot be interrupted.
    

This should make movement → attack → movement feel responsive without removing commitment from the Dash.

+

We'll use a small input buffer generally:

- Attack → attack input slightly early → next attack starts when available.
    
- Ability → ability input slightly early → activates when available.
    
- Dash → next Dash input slightly before the end → chains immediately.
    
- Inputs outside the buffer window are ignored rather than queued indefinitely.
    
- Exact buffer duration can be tuned later.
    

****

### Dash during an attack

Dash immediately cancels the attack. ✅

So Dash remains the special movement cancel in combat:

- Normal movement → waits for attack to finish.
    
- Click-to-move → waits for attack to finish.
    
- Dash → immediately cancels the attack.
    
- Ability input → follows the normal input-buffer rules.
    

**