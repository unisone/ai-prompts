# Style Consistency Framework

> Create multiple images that look like they belong together.

## When to Use

- Brand asset creation
- Social media series
- Product line visuals
- Cohesive marketing campaigns
- Character/mascot consistency

## Why It Works

AI generates each image independently, leading to inconsistent styles. By codifying your style into specific, repeatable parameters, you create a "style template" that produces visually cohesive results across multiple generations.

## The Prompt

### Style Definition Template

```
I need to establish a consistent visual style for multiple images.

**Style Name**: [Give it a name for reference]

**Core Visual Elements**:
- Color palette: [List 3-5 hex codes or color names]
- Lighting style: [Soft/hard/dramatic/flat]
- Contrast level: [Low/medium/high]
- Saturation: [Muted/normal/vibrant]
- Texture: [Smooth/grainy/detailed]

**Artistic References**:
- Similar to: [Artist, photographer, or style]
- Era/period: [Modern/vintage/futuristic]
- Medium feel: [Photography/illustration/3D/mixed]

**Consistent Elements**:
- Always include: [Recurring elements]
- Never include: [Elements to avoid]
- Composition style: [Centered/rule of thirds/dynamic]

**Technical Specs**:
- Aspect ratio: [16:9 / 1:1 / 4:5]
- Quality: [Resolution, detail level]

Now create an image of [SUBJECT] in this style.
```

### Quick Style Capture

```
Analyze this reference image and extract the style:

[DESCRIBE REFERENCE IMAGE OR PASTE URL]

Extract:
1. Color palette (list specific colors)
2. Lighting characteristics
3. Composition style
4. Texture/detail level
5. Mood/atmosphere
6. Unique stylistic elements

Then provide a prompt template I can reuse to generate new images in this exact style.
```

## Example: Brand Style Guide

```
BRAND VISUAL STYLE: "TechMinimal"

**Color Palette**:
- Primary: Deep navy (#1a1f36)
- Secondary: Electric blue (#4f7cff)
- Accent: Soft white (#f5f5f7)
- Neutral: Warm gray (#9ca3af)

**Photography Style**:
- Clean, minimal compositions
- Abundant negative space
- Soft, diffused lighting
- Slight blue color cast
- Shot on Sony A7, 35mm lens
- Shallow depth of field

**Consistent Elements**:
- Always: Clean backgrounds, modern props, tech objects
- Never: Clutter, warm tones, harsh shadows, text in images

**Mood**: Professional, innovative, calm, premium

---

Generate an image of a laptop on a desk in the TechMinimal style.
```

## Style Categories & Parameters

### Minimalist Modern
```
Style parameters:
- Lots of white/negative space
- Limited color palette (2-3 colors)
- Clean lines, simple shapes
- Soft, even lighting
- No clutter or busy backgrounds
- Geometric composition
```

### Warm Editorial
```
Style parameters:
- Golden/warm color temperature
- Natural lighting, golden hour feel
- Film-like grain texture
- Rich, saturated colors
- Lifestyle/candid feeling
- Shallow depth of field
```

### Dark & Moody
```
Style parameters:
- Low-key lighting
- Deep shadows, high contrast
- Desaturated colors with accent color
- Cinematic 2.35:1 aspect ratio
- Atmospheric haze/fog
- Dramatic rim lighting
```

### Bright & Playful
```
Style parameters:
- High key, bright exposure
- Saturated, vibrant colors
- Pastel or primary color palette
- Flat, even lighting
- Clean, graphic composition
- Energetic, dynamic angles
```

## Character/Subject Consistency

```
Create a consistent character across multiple images:

**Character Definition**:
- Physical: [Age, build, hair, skin tone, distinguishing features]
- Clothing style: [Always wears X]
- Expression tendency: [Confident/friendly/serious]
- Color association: [Colors always present]

**Fixed Elements** (never change):
- [Element 1 - e.g., red scarf]
- [Element 2 - e.g., round glasses]
- [Element 3 - e.g., specific hairstyle]

**Variable Elements** (can change):
- Pose
- Background
- Activity
- Lighting

Generate [CHARACTER] doing [ACTIVITY] in [SETTING], maintaining all fixed elements.
```

## Seed & Reference Techniques

### For Midjourney
```
Use the same seed for consistency:
--seed [NUMBER]

Reference a previous image:
[image URL] [prompt] --iw 2

Style reference:
--sref [style reference URL]
```

### For DALL-E
```
Include this in every prompt:
"Consistent with previous images in this series: [describe style]"

Or reference:
"In the same style as: [describe your reference image in detail]"
```

### For Stable Diffusion
```
Use same:
- Seed number
- Model/checkpoint
- Sampler settings
- CFG scale

Add style LoRA for consistency
```

## Style Documentation Template

```markdown
# [PROJECT NAME] Visual Style Guide

## Quick Reference
**One-line style**: [e.g., "Minimal tech aesthetic with soft blue tones"]

## Color Palette
| Color | Hex | Usage |
|-------|-----|-------|
| | | |

## Lighting
- Type: 
- Direction:
- Quality:

## Composition Rules
1. 
2.
3.

## Prompt Template
```
[SUBJECT] in [SETTING],
[your consistent style elements],
[your consistent technical specs]
```

## Do's and Don'ts
✅ Do: 
❌ Don't:
```

## Pro Tips

1. **Document everything** — Create a style guide you can reference
2. **Use seeds when available** — Same seed = more consistency
3. **Create a base prompt** — Add only subject/scene changes
4. **Test with simple subjects first** — Verify style before complex images
5. **Save successful prompts** — Build a prompt library

## Effectiveness

| Use Case | Consistency Level |
|----------|-------------------|
| Color palette matching | ⭐⭐⭐⭐⭐ |
| Lighting style | ⭐⭐⭐⭐ |
| Overall mood | ⭐⭐⭐⭐ |
| Character consistency | ⭐⭐⭐ |
| Exact face matching | ⭐⭐ (still difficult) |

---

*The key to cohesive AI-generated visual campaigns*
