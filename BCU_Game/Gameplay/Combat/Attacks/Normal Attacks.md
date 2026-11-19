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
