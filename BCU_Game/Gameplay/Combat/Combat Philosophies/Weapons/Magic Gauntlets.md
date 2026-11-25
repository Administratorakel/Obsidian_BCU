[[Adept]]
# Magic Gauntlets — Weapon Identity

**Design Status:** Core weapon identity established  
**Weapon Identity:** Palm Force (provisional name)  
**Damage Type:** Magical  
**Combat Philosophy:** Enemy displacement, battlefield manipulation and terrain interaction  
**Combat Style:** Short-range magical attacks with controlled pushing mechanics

---

## 1. Core Weapon Identity

The Magic Gauntlets specialize in manipulating enemy positions through manifestations of magical force resembling hands and palms.

Rather than relying on physical contact, the player releases short-range magical force through their gauntlets.

The weapon rewards deliberate positioning, gathering enemies and utilizing terrain to increase offensive effectiveness.

Its defining characteristics are:

- Short-range magical normal attacks.
- Stance-dependent magical hand manifestations.
- Enemy displacement through selected normal attacks and abilities.
- Gathering enemies along predetermined pushing lines.
- Additional damage through terrain collisions.
- Enemy grouping through Vector Break.
- Creation of magical terrain at Mastery Level 50.
- Magical shockwaves at Mastery Level 100.

The Magic Gauntlets do not rely on a weapon-specific stacking mechanic. Their effectiveness primarily comes from manipulating the battlefield.

---

## 2. Normal Attacks

### General Characteristics

- Normal attacks release short-range magical force.
- Physical contact with enemies is not required.
- All normal attacks deal magical damage.
- Magical hand shapes vary depending on the stance and attack animation.
- Exact attack ranges, speeds and damage values remain undecided.

### Displacement Attacks

Only the **fourth and seventh normal attacks** of each original stance possess the weapon-specific pushing mechanic.

|Attack Animation|Pushing Effect|
|---|---|
|Attack 1|No|
|Attack 2|No|
|Attack 3|No|
|Attack 4|Yes|
|Attack 5|No|
|Attack 6|No|
|Attack 7|Yes|

The fourth and seventh attacks manifest larger magical hands that displace enemies through a Pushing Line.

The exact appearance, direction, width and pushing distance depend on their respective animations.

---

## 3. Attack Stances

The Magic Gauntlets possess three normal attack stances.

### Default Stance — Balanced Force

- Balanced attack coverage.
- Moderate pushing distance.
- Moderate pushing width.
- Potential visual representation through an open magical palm.

### Wide Stance — Expansive Force

- Wider attack coverage.
- Wider pushing area.
- Shorter pushing distance compared to Focused Stance.
- Potential visual representation through a hand with spread fingers.

### Focused Stance — Concentrated Force

- Narrower attack coverage.
- Greater pushing distance.
- Concentrates magical force into a smaller area.
- Potential visual representation through a fist or concentrated finger formation.

The exact hand shapes and finger positions are intentionally left open.

All stance-specific pushing properties will be established alongside their respective animations.

---

## 4. Pushing Line

The Pushing Line is the central displacement mechanic of the Magic Gauntlets.

A pushing attack manifests magical force that travels along a defined path toward a predetermined endpoint.

### General Rules

- Enemies initially struck by the magical hand are pushed along the Pushing Line.
- Additional enemies encountered along the path join the push.
- All gathered enemies are pushed toward the attack's predetermined endpoint.
- The pushing force does not weaken as additional enemies are collected.
- The number of gathered enemies does not reduce the intended pushing distance.
- The Pushing Line's dimensions depend on the respective attack or ability.

Enemies do not individually transfer knockback through collisions. Instead, they become part of the same magical pushing force.

### Damage Rules

Every enemy collected by the Pushing Line receives the original attack's magical damage.

- Initially struck enemies receive the attack's magical damage.
- Enemies collected later along the path also receive the original magical damage.
- Each enemy can receive this original attack damage only once per pushing attack.
- Collisions between gathered enemies do not cause additional collision damage.

Additional collision damage occurs when enemies are pushed against terrain.

---

## 5. Terrain Collision Damage

Enemies pushed against terrain receive additional damage.

### General Rules

- Collision damage requires forced displacement.
- Enemies walking into terrain do not receive collision damage.
- Enemies colliding with other enemies do not trigger collision damage.
- Enemies already standing directly against terrain can still receive collision damage from subsequent pushing attacks.
- A pushing palm pressing enemies against terrain constitutes a valid collision.
- Each enemy receives collision damage once per pushing attack.

### Multiple Enemy Scaling

Collision damage increases slightly depending on the number of enemies pushed against terrain.

Gathering larger groups therefore provides an additional offensive reward without excessively multiplying the damage.

The exact scaling formula remains undecided.

### Valid Terrain

Collision damage can be triggered using:

- Natural terrain.
- Walls and other valid environmental obstacles.
- Magical terrain created by the player.
- Magical terrain created by other players.

This allows multiple Magic Gauntlet users to cooperate through their manifested terrain.

---

## 6. Enemy Action and Knockback Rules

### Normal Attack Displacement

The fourth and seventh normal attacks displace enemies without interrupting their current actions.

- Existing enemy attack animations continue.
- Enemies retain their ability to act during displacement.
- Enemy attacks may miss due to their changed position.
- No inherent stun or stagger is applied.

This follows the distinction between displacement and action-interrupting crowd control.

### Ability Displacement

Whether a pushing ability interrupts enemy actions will be determined individually during ability design.

Not all pushing abilities necessarily apply the same interruption rules.

### Knockback-Resistant Enemies

Enemies resistant or immune to displacement:

- Receive the original magical attack damage.
- Are not displaced by the Pushing Line.
- Do not obstruct the Pushing Line.
- Do not prevent additional enemies behind them from being collected.

This allows the Magic Gauntlets to remain useful during encounters involving bosses or displacement-resistant enemies.

---

## 7. Vector Break — Dual Palm Push

The Magic Gauntlets' [[Vector Break]] specializes in gathering enemies and positioning them for subsequent attacks.

### Visual and Movement Identity

During Vector Break:

- The player extends both palms forward.
- Two large magical palms manifest in front of the player.
- The manifestations move alongside the player throughout Vector Break.
- Enemies struck by the palms are pushed forward.

### Enemy Gathering

- Enemies can be gathered throughout the entire Vector Break movement.
- Enemies encountered later join the existing push.
- All collected enemies are pushed toward the same final positioning line.
- Gathered enemies are slightly compressed horizontally toward the center.
- The final positioning line is located in front of the player, within normal attack range.

The purpose is to leave enemies conveniently positioned for follow-up attacks.

### Damage

Vector Break deals magical damage to collected enemies.

It also follows the established terrain collision damage rules:

- Additional damage when enemies are pushed against terrain.
- Slightly increased collision damage when multiple enemies are gathered.
- Original attack damage applies once per enemy.

### Action Interruption

Unlike the fourth and seventh normal attacks, Vector Break:

- Applies knockback.
- Interrupts enemy actions.
- Creates an opportunity for follow-up attacks.

This makes Vector Break an effective combat initiation and enemy-grouping tool.

### Intended Combat Sequence

**Vector Break → Gather Enemies → Normal Attack Loop → Pushing Attacks → Terrain Collision**

---

## 8. Weapon Mastery Level 50 — Magical Terrain

**Provisional Mastery Name:** Magical Terrain

At Weapon Mastery Level 50, selected Magic Gauntlet abilities gain the ability to create temporary manifestations of magical terrain.

These manifestations function as physical obstacles exclusively for eligible enemies.

### Creation Rules

- Selected abilities create magical terrain.
- Not every ability necessarily creates terrain.
- Terrain creation is ability-specific.
- Shapes, dimensions and placement patterns depend on the respective ability.
- Multiple magical terrain manifestations can coexist simultaneously.

Potential terrain manifestations may include stationary magical hands, but their appearance is not restricted to a universal shape.

### Duration

- Magical terrain remains active for a few seconds.
- Each manifestation has its own expiration timer.
- Collisions do not destroy the manifestation.
- Multiple pushing attacks can utilize the same manifestation before it expires.

Exact durations remain undecided.

### Collision Properties

|Entity|Collides With Magical Terrain|
|---|:-:|
|Player who created it|No|
|Other players|No|
|Regular enemies|Yes|
|Certain bosses|No|
|Projectiles|No|

Magical terrain exclusively obstructs enemy movement.

Eligible enemies must navigate around it rather than walk through it.

The manifestation does not function as a projectile-blocking defensive barrier.

### Boss Exceptions

Certain bosses can ignore magical terrain entirely, passing through it in the same manner as players.

These exceptions will be determined individually during boss design.

### Combat Interaction

The player can create magical terrain using one ability and subsequently push enemies against it using:

- Fourth normal attacks.
- Seventh normal attacks.
- Other pushing abilities.
- Vector Break.

This allows the Magic Gauntlets to utilize terrain collision damage even in environments without naturally occurring obstacles.

---

## 9. Weapon Mastery Level 100 — Collision Shockwave

**Provisional Mastery Name:** Collision Shockwave

At Weapon Mastery Level 100, magical terrain created by the player gains an additional offensive interaction with pushing attacks.

Whenever a pushing palm strikes the player's own magical terrain, the manifestation releases a magical shockwave.

The underlying concept is that the magical hand transfers its energy into the manifested terrain, causing it to release that energy radially.

### Activation Conditions

A Collision Shockwave can be triggered in two ways:

**Direct Impact**

- A pushing palm directly strikes the player's magical terrain.
- No enemies need to be present.
- The shockwave deals its base damage.

**Impact With Enemies**

- A pushing palm forces enemies against the player's magical terrain.
- The enemies receive ordinary collision damage.
- The manifestation releases a shockwave.
- Shockwave damage increases slightly depending on the number of enemies pushed against it.

### Ownership Restriction

Collision Shockwaves exclusively activate through the player's own magical terrain.

|Terrain Type|Collision Damage|Collision Shockwave|
|---|:-:|:-:|
|Natural terrain|Yes|No|
|Own magical terrain|Yes|Yes|
|Other player's magical terrain|Yes|No|

Other players' magical terrain can still be used for ordinary terrain collision damage.

However, it cannot activate the attacking player's Level 100 Mastery effect.

---

## 10. Collision Shockwave — Mechanical Rules

### Shockwave Origin

The shockwave originates from the **center of the magical terrain manifestation**, regardless of where the pushing hand or enemies collide with it.

This provides predictable radial coverage and makes deliberate terrain placement more meaningful.

### Damage

- The shockwave deals magical damage.
- Enemies that triggered the collision can receive shockwave damage.
- Surrounding enemies within the shockwave's coverage also receive damage.
- Damage increases slightly with each additional enemy pushed against the manifestation.
- A direct palm impact without enemies triggers the base shockwave damage.

### Activation Limit

Each individual pushing attack can trigger a maximum of **one shockwave per magical terrain manifestation**.

Multiple enemies colliding with the same manifestation increase the shockwave's damage rather than generating additional shockwaves.

If a pushing attack strikes multiple valid manifestations, each manifestation can independently release one shockwave.

### No Additional Displacement

Collision Shockwaves exclusively deal damage.

They do not:

- Push enemies.
- Apply knockback.
- Trigger additional terrain collisions through displacement.
- Create further Collision Shockwaves through chain reactions.

### Terrain Preservation

Releasing a shockwave does not destroy the magical terrain.

The manifestation remains active until its normal expiration timer ends.

---

## 11. Weapon Mastery Overview

|Mastery Level|Unique Mechanic|
|---|---|
|Base|Pushing Lines and terrain collision damage|
|Level 50|Selected abilities create temporary magical terrain|
|Level 100|Pushing palms striking owned magical terrain generate Collision Shockwaves|

Both Mastery bonuses directly expand the weapon's existing identity.

Level 50 reduces dependence on natural terrain, while Level 100 turns the player's own terrain manifestations into additional offensive tools.

---

## 12. Damage Interaction Examples

### Example A — Ordinary Push

The player performs a fourth normal attack.

Three enemies are collected along the Pushing Line.

- All three receive the original magical attack damage once.
- All three are pushed toward the predetermined endpoint.
- No additional collision damage occurs if no terrain is encountered.

### Example B — Natural Terrain Collision

The player pushes three enemies against a natural wall.

All three receive:

- Original magical attack damage.
- Terrain collision damage.
- A slight collision damage increase from gathering multiple enemies.

No Collision Shockwave occurs.

### Example C — Magical Terrain Collision at Level 100

The player creates magical terrain using an ability and subsequently pushes three enemies against it.

All three receive:

- Original magical attack damage.
- Terrain collision damage.
- Collision Shockwave damage, provided they are within its coverage.

Other nearby enemies can also receive shockwave damage.

The magical terrain remains intact.

### Example D — Direct Magical Terrain Impact

The player performs a pushing attack against their own magical terrain without collecting any enemies.

- The magical hand strikes the manifestation.
- One shockwave originates from its center.
- Nearby enemies receive the base shockwave damage.
- No enemy-count damage bonus applies.
- The manifestation remains intact.

### Example E — Cooperative Terrain Usage

Player A creates magical terrain.

Player B pushes enemies against Player A's manifestation.

- Player B's attack deals its original magical damage.
- Enemies receive ordinary terrain collision damage.
- Player B does not trigger a Collision Shockwave from Player A's terrain.

---

## 13. Pushing Attack Comparison

|Property|Normal Attacks 4 & 7|Vector Break|Pushing Abilities|
|---|:-:|:-:|:-:|
|Magical Damage|Yes|Yes|Ability-dependent|
|Enemy Displacement|Yes|Yes|Yes|
|Additional Enemy Gathering|Yes|Yes|Ability-dependent|
|Terrain Collision Damage|Yes|Yes|Yes|
|Action Interruption|No|Yes|Ability-dependent|
|Horizontal Compression|Animation-dependent|Slight|Ability-dependent|
|Magical Terrain Creation at Lv. 50|No|Not established|Selected abilities|
|Collision Shockwave at Lv. 100|Yes|Yes|Yes|

Individual ability exceptions remain possible during ability design.

---

## 14. Visual Identity

The Magic Gauntlets should visually communicate the manipulation of magical force through the player's hands.

### Normal Attacks

- Short-range manifestations of magical force.
- Hand shapes corresponding to individual attack animations and stances.
- Larger manifestations during displacement attacks.

### Vector Break

- Both palms extended forward.
- Two large magical palms moving with the player.
- Enemies visibly gathered and repositioned by the manifestations.

### Magical Terrain

- Ability-specific magical constructs.
- Clearly distinguishable from natural terrain.
- Visually communicates its temporary existence.
- Potentially shaped like stationary magical hands.

### Collision Shockwaves

- Originate from the center of the magical terrain.
- Visually communicate the transfer and release of magical energy.
- Do not visually imply further enemy displacement.

Exact visual effects, hand formations and animations remain open for development.

---

## 15. Intended Combat Rhythm

### Before Mastery Level 50

**Gather Enemies → Position Near Terrain → Push → Collision Damage → Repeat**

### At Mastery Level 50

**Create Magical Terrain → Gather Enemies → Push Against Manifestation → Collision Damage → Repeat Before Expiration**

### At Mastery Level 100

**Create Magical Terrain → Gather Enemies → Palm Impact → Collision Damage + Shockwave → Reposition → Repeat**

The Magic Gauntlets reward players who:

- Understand their normal attack loops.
- Anticipate upcoming displacement attacks.
- Utilize natural terrain effectively.
- Deliberately position groups of enemies.
- Create magical terrain in advantageous locations.
- Combine terrain-creating abilities with pushing attacks.
- Utilize multiple manifestations before they expire.

---

## 16. Remaining Design Questions

### Normal Attacks

- Exact attack range and speed.
- Individual attack animations.
- Exact magical hand shapes.
- Stance-specific pushing distances and widths.
- Interaction between customized attack loops and displacement attacks.

### Pushing Mechanics

- Exact displacement speed.
- Pushing Line dimensions.
- Enemy positioning and spacing at the endpoint.
- Terrain collision damage formula.
- Multiple-enemy collision damage scaling.
- Interaction with irregular terrain.

### Vector Break

- Magical palm size.
- Exact damage.
- Horizontal compression strength.
- Final enemy positioning distance.
- Knockback and interruption duration.

### Mastery Level 50

- Which abilities create magical terrain.
- Individual terrain shapes and dimensions.
- Manifestation duration.
- Potential maximum number of simultaneous manifestations.
- Enemy navigation implementation.
- Boss-specific terrain immunity.

### Mastery Level 100

- Base shockwave damage.
- Shockwave radius.
- Additional damage per gathered enemy.
- Potential damage scaling limitations.
- Visual and audio effects.

These details are intentionally left open until individual ability design, implementation and playtesting.

---

## 17. Final Weapon Identity

**The Magic Gauntlets are a short-range magical weapon that transforms enemy positioning and terrain into offensive power.**

Their defining mechanic is the ability to gather and displace enemies through manifestations of magical hands, dealing additional damage by pushing enemies against terrain.

Vector Break specializes in gathering and positioning enemies for follow-up attacks.

Weapon Mastery gradually allows the player to create their own battlefield obstacles and transform them into sources of magical shockwaves.

Unlike weapons that rely on accumulating stacks or consuming additional resources, the Magic Gauntlets reward spatial awareness, deliberate positioning and creative battlefield manipulation.

**Design Status: Core Weapon Identity Complete.**