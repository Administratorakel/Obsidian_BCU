## 1. Graphics and Art Direction

### Overall visual style

- The game should retain the nostalgic appeal of older MMORPGs such as Metin2.
- Graphics should be somewhat better than Metin2, without aiming for modern AAA realism.
- **All 3D elements should have a pixelated visual style.**
- The appearance should be attractive, distinctive, and achievable for a relatively inexperienced developer.
- The visual style must remain consistent across different cultural and environmental themes.
- The game should not be restricted to Asian or medieval aesthetics.
- Characters, equipment, buildings, and environments should follow shared visual rules.

### Visual priorities

- Combat readability and satisfying visuals take priority over excessive environmental detail.
- Fast movement and combat should remain visually understandable.
- Environments should still feel beautiful and atmospheric.
- Recognizable silhouettes are important, especially for characters and enemies.

### Character proportions

- **Human characters retain realistic body proportions.**
- The pixelated style should not require exaggerated, cartoonish anatomy.
- Character silhouettes and individual body types should remain distinguishable.

### Not yet finalized

- Exact pixel density and texture resolutions.
- Whether pixelation will be achieved primarily through textures, rendering, or a combination.
- Final lighting and shader specifications.
- Precise polygon budgets.
- Final UI art style.


## 2. Character Faces and Expressions

This is one of the major decisions missing from my previous summary.

### 3D character faces

- Characters should have relatively simple 3D faces.
- Their faces must nevertheless remain expressive.
- Facial expressions can be represented using changeable textures or other relatively simple methods.
- Body language and animations should contribute to emotional expression.
- Complex facial geometry and sophisticated facial rigs are not required as the initial approach.

### Dialogue portraits

- Dialogue interfaces should include expressive 2D character faces.
- The dialogue box should appear near the bottom of the screen.
- Portrait expressions should communicate the character's current emotions.
- These portraits can be more detailed and expressive than the simplified in-world faces.

### Player expressions

- Players should eventually be able to select expressions during dialogue.
- A selected expression may subtly affect an NPC's reaction.
- Expressions should not exist exclusively during dialogue.
- Characters should also have a general or default expression that persists independently of conversations.
- The player's in-world appearance should reflect their expression state where appropriate.

### Custom-drawn faces

- **Long-term goal:** Allow players to draw their own expressions.
- Players should eventually be able to create a personal set of facial expressions.
- Custom expressions should work for both the 3D character face and the 2D dialogue portrait.
- This is a future customization feature, not necessarily something required for the first playable version.

### Implementation ideas, not finalized

- Swapping facial textures according to expression.
- Using a shared expression library for 3D faces and 2D portraits.
- Providing predefined expressions before introducing user-drawn ones.
- Defining a common expression format so custom faces can be supported later.