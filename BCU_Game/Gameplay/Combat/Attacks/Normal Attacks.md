- Normal attack behavior
- Combo progression
- Attack range
- Attack timing
- Weapon-specific attack sequences
- Interaction with movement
- Attack interruption rules

[[Attack Principles]]
[[Combat Feedback]]
[[Weapon Mastery]]
[[Weapon Mastery Progression]]

## Current melee attack prototype
- Four working attack animations, with additional slots intended to unlock through Weapon Mastery.
- Click input queues **at most one** additional attack after an adjustable late input window (prototype ~50% into the current attack).
- Holding the attack button through a later commitment threshold (~80%) allows continued attack looping; releasing before commitment stops automatic continuation.
- Short end-of-attack input forgiveness/buffer (~0.2 seconds) is prototyped.
- Manual WASD movement is blocked during an attack; new attack loops can re-evaluate held movement direction at their start.
- Attack-only animation root motion is being prototyped; current motion-direction correction is temporary, not a definitive animation pipeline.
- These percentages/seconds are **prototype tuning values**, not immutable game balance.


### Stances and Combo Books

The player initially possesses a balanced four-attack combo.

**Initial stance books:**

|Book|Effect|
|---|---|
|Wide Sword Stance Book|Unlocks wide variants of the initial four attacks|
|Focused Sword Stance Book|Unlocks focused variants of the initial four attacks|
|Sword Stance Combo Book|Allows individual customization of the initial four attacks|

The Sword Stance Combo Book can be consumed before Lv 20.

For example, the player could configure their attacks as:

1. Default
2. Wide
3. Wide
4. Default

The corresponding attack variants must already be unlocked.

**Additional combo slots:**

|Mastery|Unlock|
|---|---|
|Lv 20|Fifth attack slot|
|Lv 45|Sixth attack slot|
|Lv 70|Seventh attack slot|

Each additional attack has a Wide and Focused Combo Book.

Unlocking the slot does not automatically grant an attack. The corresponding book must first be obtained and consumed.

Books are consumed only once to unlock their associated options.

There are currently **nine different Sword Stance/Combo Books**.