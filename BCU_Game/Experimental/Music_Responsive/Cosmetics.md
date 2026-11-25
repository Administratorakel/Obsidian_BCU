# Music-Responsive Cosmetics

**Status:** Future Concept
**Priority:** Low
**Category:** Cosmetics / Audio System

## Core Concept

- Skins that dynamically react to the rhythm of the
  currently playing background music.
- Compatible with both official BCU soundtracks and
  player-imported music.
- Visual reactions occur independently of regular
  character animations.
- Purely cosmetic, without gameplay advantages.

## Custom Background Music

- Players can import their own background music
  through a dedicated local folder.
- Supported file formats (provisional):
  - MP3
  - OGG
  - WAV
- The game patcher provides direct access to the folder.
- The game automatically detects compatible additions.
- Newly detected music is highlighted in the game options.
- Players can enable or disable individual songs.
- Imported music remains local.

### Potential Extensions

- Custom playlists.
- Music assigned to specific situations:
  - Exploration
  - Combat
  - Boss fights
  - Villages
  - Dungeons

## Rhythm Recognition System

A universal audio analysis system that extracts
musical information from any compatible soundtrack.

### Pre-Analysis

- Estimated BPM.
- Beat timestamps.
- Rhythm and tempo changes.
- Analysis results are cached locally.
- Allows visual effects to anticipate upcoming beats.

### Real-Time Analysis

- Frequency spectrum.
- Bass intensity.
- High frequencies.
- Volume intensity.
- Sudden musical transitions.
- Silence detection.

Both methods work together to create synchronized
and dynamic visual reactions.

## Music-Responsive Skin

Potential visual effects:

- Armor fragments moving according to the rhythm.
- Pulsating emissive textures.
- Rhythm-synchronized procedural animations.
- Floating elements that expand and contract.
- Stability particles reacting to strong beats.
- Color changes based on musical intensity.
- Reduced movement during quiet sections.

Each song can produce a different visual experience
without requiring individually designed animations.

## Potential Lore Connection

- The cosmetic consists of Stability that resonates
  with sound and musical frequencies.
- Lore explanation remains provisional.

## Technical Considerations

- Unity AudioSource.GetSpectrumData().
- Unity AudioSource.GetOutputData().
- Additional beat-detection algorithms.
- Independent cosmetic animation layers.
- Local caching of analyzed soundtracks.
- Irregular rhythms may be difficult to recognize
  accurately.

## Future Applications

The audio analysis system should be independent
of the cosmetic itself, allowing it to influence:

- Other skins.
- Weapon cosmetics.
- Visual effects.
- Environmental decorations.
- Ambient particles.
- Potential music-responsive environments.

## Design Principle

Develop one universal music analysis system that
multiple cosmetic and environmental systems can use.


Later in developing state:

| Note                            | Suggested location     |
| ------------------------------- | ---------------------- |
| Music-Responsive Cosmetics      | `Equipment/Cosmetics/` |
| Custom Background Music         | `Development/Audio/`   |
| Universal Audio Analysis System | `Development/Audio/`   |
