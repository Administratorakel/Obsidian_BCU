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

---
# Player Head Design

**Status:** Initial visual direction established. Implementation and final topology pending.

**Related:** [[Character Faces]], [[Overall visual style]], [[Boracle]], [[Core Philosophy]]

## 1. Base Head — 100 Triangles

The player character's base head will target **100 triangles**.

This applies to the head geometry itself, excluding hairstyles and optional accessories.

### Visual Characteristics

- Low-poly 3D geometry.
    
- Realistic human proportions.
    
- Angular, simplified facial structure.
    
- Flat-shaded appearance.
    
- No anime-style proportions.
    
- Compatible with the BCU's nostalgic, slightly pixelated visual identity.
    

The base model should remain recognizable from different viewing angles despite its low polygon count.

## 2. Facial Design

The base head should have a relatively flat, featureless facial surface.

Facial details can be developed separately.

Possible approaches include:

- Facial textures.
    
- Interchangeable facial appearances.
    
- Different expressions for dialogue portraits.
    
- Additional facial geometry where necessary.
    

**Not yet decided:** The final method of implementing facial features and expressions.

The initial reference designs explored both detailed faces and completely featureless heads.

## 3. Hairstyles

Hairstyles will use separate geometry from the base head.

Their triangle counts are not included in the 100-triangle head budget.

This allows extravagant hairstyles without increasing the base head's geometric complexity.

### Explored Hairstyles

- Short and conventional hairstyles.
    
- Long hairstyles.
    
- Ponytails and braids.
    
- Spiky hairstyles.
    
- Asymmetrical cuts.
    
- Mohawks.
    
- Large, exaggerated hairstyles.
    
- Horn-like hair silhouettes.
    
- Bald and very short hairstyles.
    

The experiments suggested that unusual hairstyles can remain recognizable with relatively simple geometry, particularly when their silhouettes are distinctive.

Exact hairstyle polygon budgets remain undecided.

## 4. Connection to BCU Lore — 100%

The decision to target 100 triangles is partly inspired by the BCU's recurring **100% concept**.

The number 100 already appears symbolically within the setting and its mechanics.

The 100-triangle head can therefore function as a subtle connection between the player's physical appearance and the BCU's underlying philosophy.

### Symbolic Interpretation

- **100 triangles:** The foundation of the player's physical appearance.
    
- **100% Stability:** The maximum value of the player's Stability resource.
    
- **100%:** A recurring concept associated with completeness within the BCU.
    

This relationship is currently a symbolic design reference, not a gameplay mechanic.

The geometry does not inherently grant special abilities or affect Stability.

## 5. Modeling Considerations

The generated images are visual references, not verified 3D meshes.

Their stated triangle counts should not be interpreted as exact topology measurements.

When creating the model in Blender:

- Aim for approximately 100 triangles for the base head.
    
- Keep the hairstyle as a separate mesh.
    
- Maintain the intended silhouette.
    
- Minimize unnecessary facial geometry.
    
- Evaluate appearance at normal gameplay camera distance.
    
- Confirm the actual triangle count in Blender.
    

## 6. Open Decisions

- Exact head topology.
    
- Whether the neck is included in the 100-triangle budget.
    
- Male and female head variations.
    
- Final facial expression implementation.
    
- Texture resolution and pixelation.
    
- Hairstyle polygon budgets.
    
- Compatibility with helmets and other equipment.
    
- Whether the 100-triangle count must be exact or approximate.
    

## Design Goal

Create a recognizable, customizable low-poly player head that supports expressive characters and extravagant hairstyles while maintaining the BCU's visual identity.

**The 100-triangle target combines practical visual simplicity with a subtle reference to the BCU's 100% concept.**