****
****

### Answers 111–115

111 — Spawn selection: C ✅  
Each spawn group uses the map's enemy pool with its own weighted selection.

112 — Rare enemies: C ✅  
Rare enemies should be visibly distinguishable — through size and/or visual enhancements, plus potentially their name/title.

113 — Elite abilities: C ✅  
Mix of recognizable player-like abilities and completely unique enemy abilities.

114 — Enemy awareness: C ✅  
Enemy waits at the player's last known location. After some time, if the player is still within the leash area, it searches a random possible location around the player.

115 — Group aggression: A ✅  
Once one enemy alerts its group, the entire group becomes aggressive immediately.

Let's switch topics a bit.

**

### Answers 107–110

107 — Enemy rarity: Not really a rarity system. Instead, enemies have different spawn probabilities within the map's enemy pool. ✅

108 — Elite enemies: Better stats + better loot + potentially special resources + somewhat higher equipment drop chance. If they wield a weapon, they may also use an ability. ✅

109 — Enemy levels: D — mostly fixed, with certain enemies dynamically scaling. ✅

110 — Enemy awareness: C — enemy-dependent. Some enemies can have different detection behavior. ✅

  

I actually like this much more than simply increasing the cooldown after every kill.

It creates a dynamic spawn rhythm based on how the area is being played:

- Enemies die quickly → shorter respawn cooldown.
    
- Enemies take a long time to defeat → longer respawn cooldown.
    
- A complete enemy group must still be dead before the next group can spawn.
    
- The system therefore naturally supports fast grinding without overwhelming the player during a difficult fight.
    

The interesting part is that the system doesn't really punish the player for being strong. If you're efficiently clearing groups, the game effectively says "good, here's the next group."

I'd just be careful about one thing: don't base the cooldown purely on the duration of the fight. A player could intentionally stall an enemy and manipulate the timer. Instead, I'd use something like the group's average combat duration / time between first engagement and group death, with sensible minimum and maximum limits.

It could even create a nice natural rhythm:

Fast clear → short wait → fast clear → short wait  
Difficult group → longer fight → longer preparation window

That feels particularly appropriate for a grinding-focused game.

I would mark 106 as:

106 — Dynamic group respawn: The respawn cooldown is influenced by how quickly the previous group was defeated. Fast clears reduce the cooldown; prolonged fights increase it. Exact formula/limits TBD. ✅

And I'd keep this separate from the spawn pool probabilities we established.

Yes, Dynamic group respawn. 111 C 112 Might be C, definitely visual, size and/or visual enhancement 113 C 114 C wait at the last known location and after some time check randomly a possible location around the player if still close. 115A

Perfect. These are all clear.

**
The group-based respawn system can make the world feel more alive without having individual enemies popping back into existence beside the player.

For the extra cooldown: yes, it could become annoying if it directly increases every time the player kills something, especially during grinding. But your idea can work if the purpose is to prevent a player from completely clearing an area and immediately getting the same group again.

I'd frame it as:

- A group has to be completely cleared before it can respawn.
    
- Once cleared, a respawn timer starts.
    
- The timer can have some variation rather than always being identical.
    
- Potentially, repeated rapid clearing could influence the timer, but I'd avoid making it grow indefinitely.
    

That gives you controlled enemy density without making grinding feel artificially throttled.

**

### Enemy movement while Auto-Attacking

If the target starts moving while the player is already attacking it, should the player:

A) Finish the current attack, then reposition for the next attack  
D) Depend on the weapon/attack type

A, but D in the future

Enemy movement during Auto-Attack: A for now. ✅

- Current attack always finishes.
    
- Afterward, the player repositions toward the moving target.
    
- Future: individual weapons/attacks may have different reactions.
    

### Enemy stops moving

If the enemy stops moving while the player is repositioning toward it, should the player:

A) Continue to the calculated attack position, then attack  
B) Immediately recalculate the ideal attack position  
C) Stop movement immediately and attack if in range  
D) Recalculate only if the enemy's new position significantly changes the required movement  
E) Decide individually by weapon later

E

Enemy stops moving: E — weapon/attack-specific later. ✅

We'll keep the general Auto-Attack framework flexible enough for different weapon behaviors.

****

### Auto-Attack and player movement input

We established that manual movement temporarily overrides Auto-Attack movement. When the player releases WASD, should Auto-Attack:

  

Auto-Attack after manual movement: A — resume immediately. ✅

- WASD pressed → manual movement takes control.
    
- WASD released → Auto-Attack movement resumes immediately.
    
- Target remains selected throughout.
    

### Manual movement while in attack range

If Auto-Attack is ON, the target is already in attack range, and the player uses WASD to move away from the target, should Auto-Attack:

  
C) Let manual movement override, but resume chasing once the attack ends  
Manual movement while in attack range: C — manual movement overrides, Auto-Attack resumes after the attack ends. ✅

S0o the player can deliberately reposition without Auto-Attack constantly fighting their input.

  

### Auto-Attack and Dash

If Auto-Attack is ON and the player manually presses Dash, we've established Dash is independent and uses the player's current facing.

After Dash ends, should Auto-Attack:

Auto-Attack after Dash: A — immediately resumes. ✅

So Dash is a temporary manual override, but it doesn't disable Auto-Attack.

### Auto-Attack and abilities

  

Auto-Attack after an ability: B — resume only if the target is still valid and reachable. ✅

So the ability temporarily takes control, then Auto-Attack checks:

- Target still exists/alive
    
- Target is still selected
    
- Target is reachable
    
- Attack conditions are satisfied
    

If so → resume immediately.

  

### Auto-Attack and target switching after an ability

If the player selects a new target while an ability is playing, should Auto-Attack use:

Target switching during an ability: A — new target is used immediately when the ability ends. ✅

The ability itself finishes its current action, but the target state can change immediately. Auto-Attack then uses the newly selected target.

### Target switching while navigating

If Auto-Attack is navigating toward Enemy A and you click Enemy B, we've said movement redirects immediately.

What if Enemy B is behind terrain and unreachable, while Enemy A is still reachable?

  

B becomes the sole focus. Enemy A is forgotten and will not be used again unless the player selects it again.

  

When the player manually clears the target with the X button, what should happen if Auto-Attack is ON?

clearing the target immediately stops all attacking and automatic movement. ✅

  

### Targeting & Auto-Attack rules are now well-defined

- Targeting, target switching and clearing
    
- Target UI and out-of-sight behavior
    
- Click-to-move interaction
    
- WASD priority
    
- Auto-Attack behavior
    
- Attack/ability interruption rules
    
- Dash interaction
    
- Enemy death/unreachability
    
- Manual target switching
    
- Combat action buffering
    

****

### Answers 101–105

101 — Enemy aggression: D, enemy-dependent ✅  
Some enemies are naturally aggressive; others won't initiate combat.

102 — Enemy leash: A ✅  
Enemies return once they exceed a defined leash distance from their original area.

103 — Loot: C ✅  
Ground drops are the default, while certain quests/items can use automatic inventory rewards.

104 — Group aggression: A ✅  
Attacking one enemy can cause nearby enemies in the group to become aggressive.

**