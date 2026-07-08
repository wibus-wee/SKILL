---
name: text-safe-background-prompts
description: generate, refine, and batch midjourney-style prompts for text-safe illustrated background images used in browser new tabs, landing pages, settings pages, presentations, posters, and ui surfaces. use when the user asks for background prompt cookbooks, style systems, bulk image-generation prompts, naming schemes, or adaptations of references such as pastel meadow, fantasy mountain, shanshui, risograph collage, monet, seurat, linocut, topographic, or minimal 3d architecture backgrounds. prioritize clean overlay space, decorative edge composition, low-noise centers, coherent palettes, and production-ready prompt variants.
---

# Text-Safe Background Prompt Generator

Create image-generation prompts for decorative backgrounds that can safely hold UI text, titles, cards, search bars, widgets, or other overlays.

The output should favor reusable production prompts over one-off pretty images. The core rule is:

**layout first, style second, subject third.**

A background is successful only if it is usable behind content.

## Core Principles

Always optimize for these properties:

1. **Text-safe composition**
   - Keep the center or requested text area clean.
   - Put visual density on edges, corners, bottom, or far background.
   - Avoid faces, large foreground subjects, text, signs, logos, and busy center details.

2. **Large negative space**
   - Use phrases like:
     - `large clean empty center area`
     - `large blank paper area`
     - `low contrast center`
     - `text-safe composition`
     - `decorative details around the edges`
     - `main visual elements concentrated along the bottom edge`

3. **Layered but quiet depth**
   - Foreground: flowers, grass, paper fragments, contour lines, architecture, foliage.
   - Midground: hills, ponds, terraces, paths, rivers, cliffs.
   - Background: mountains, clouds, moon, sea, mist, skyline silhouettes.
   - Keep the text area low-detail even when the scene has depth.

4. **Cohesive palette**
   - Use 3–5 named color families.
   - Prefer muted, pastel, or controlled high-saturation palettes.
   - Avoid uncontrolled rainbow colors unless the user explicitly wants playful/festival imagery.

5. **Illustrated, not photographic**
   - Prefer painterly, watercolor, gouache, ink wash, risograph, linocut, impressionist, pointillist, anime background art, or matte 3D render styles.
   - Avoid photorealism unless explicitly requested.

6. **Production constraints**
   - Include `no text, no logo, no watermark`.
   - For Midjourney, default to `--ar 16:9 --v 6.1 --style raw`.
   - Use `--s 150-300` for reliable UI backgrounds.
   - Use `--s 300-600` only when the user wants more expressive or dreamy results.

## Default Output Behavior

When the user asks for prompts, provide:

1. A short style diagnosis if reference images or filenames are provided.
2. A reusable prompt formula.
3. 3–8 production prompts, depending on the request.
4. A fixed negative prompt block.
5. Optional batch/permutation prompt if the user wants many assets.
6. Optional naming scheme if the user is organizing generated files.

Do not over-explain basic Midjourney concepts unless the user asks.

## Prompt Formula

Use this structure:

```text
wide text-safe background for [SURFACE], [SCENE], large clean empty [TEXT_AREA] for overlay text, main visual elements concentrated in [ANCHOR_AREA], [DECORATIVE_ELEMENTS], [DEPTH_ELEMENTS], [LIGHTING], [COLOR_PALETTE] palette, [STYLE], [TEXTURE], low contrast center, elegant negative space, no text, no logo, no watermark --ar [ASPECT_RATIO] --v 6.1 --style raw --s [STYLIZE]
```

Default values:

```text
[SURFACE] = browser new tab page
[TEXT_AREA] = center area
[ANCHOR_AREA] = bottom edge and corners
[ASPECT_RATIO] = 16:9
[STYLIZE] = 250
```

## Reliable Text-Safe Phrases

Use these phrases often:

```text
wide text-safe background
large clean empty center area
large blank area for UI overlay
low contrast center
simple soft background shapes
decorative details around the edges
main visual elements concentrated along the bottom edge
airy negative space
quiet composition
subtle texture
no busy details in the middle
```

For left-aligned UI:

```text
large clean empty left-center area
main visual elements concentrated on the right edge and lower right corner
```

For centered UI:

```text
large clean empty center area
decorative elements framing the bottom edge and corners
```

For top-aligned UI:

```text
large empty upper center area
visual elements arranged along the lower third
```

For dark mode:

```text
large clean dark center area
low contrast dark background
subtle moonlit highlights
muted dark palette
```

## Negative Prompt

Use this fixed negative block unless the user asks otherwise:

```text
--no text, words, letters, logo, watermark, signature, title, caption, UI, button, people close-up, face, busy center, cluttered center, high contrast center, harsh shadows, photorealistic, modern city, cars, screenshots
```

For very clean UI backgrounds, add:

```text
--no sharp foreground object, large character, centered subject, readable signs, dense pattern, noisy texture
```

## Style Recipes

### Pastel Meadow / Soft Countryside

Use for calm, gentle, feminine, spring, onboarding, children’s products, wellness, or light UI backgrounds.

```text
wide text-safe illustrated background, soft pastel countryside meadow, large empty cream-colored sky and clean center area for overlay text, wildflowers along the bottom edge, tiny blue butterflies, distant rolling hills, small cottage far on the right, soft morning light, ivory, pale blue, sage green and soft yellow palette, romantic countryside mood, watercolor and oil paint texture, delicate brush strokes, peaceful ethereal atmosphere, vintage storybook illustration, no text, no logo, no watermark --ar 16:9 --v 6.1 --style raw --s 300
```

### Fantasy Mountain / Anime Adventure

Use for epic, AI, game, exploration, technology, launch pages, or expressive hero backgrounds.

```text
wide cinematic text-safe fantasy background, two tiny explorers walking on a mountain trail near the lower left, colossal snow-capped mountain in the distance, vast blue valley layers, glowing alpine flowers along the foreground, large clean sky area for title text, pale moon in the sky, pink sunset clouds, dramatic sense of scale, cobalt blue, cyan and rose pink palette, anime background art, fantasy concept art, painterly digital illustration, atmospheric perspective, breathtaking adventure mood, no text, no logo, no watermark --ar 16:9 --v 6.1 --style raw --s 300
```

### Whimsical Flower Field / Cartoon Storybook

Use for playful, festival, education, children’s products, cheerful marketing, or soft decorative banners.

```text
wide colorful whimsical text-safe background, dreamy cartoon meadow landscape, clean bright center area for large title text, rolling green hills, fluffy pastel clouds, colorful flowers and leaves framing the bottom and corners, soft rainbow-like lighting, playful magical atmosphere, pastel turquoise, lime green, pink, yellow and lavender palette, cute storybook illustration, soft gouache texture, smooth painterly shapes, cheerful spring mood, no text, no logo, no watermark --ar 16:9 --v 6.1 --style raw --s 350
```

### White Risograph Mechanical Collage

Use for editorial, product settings pages, experimental tools, creative coding, scientific notebook, vintage tech, or collage systems.

```text
wide text-safe background, warm off-white handmade paper texture, huge clean empty space on the left and center for UI text, decorative vintage mechanical collage concentrated on the right edge and bottom right corner, thin pipes, gears, valves, clockwork parts, hot air balloon, architectural blueprint fragments, mountain cutout, abstract torn paper shapes, muted teal, faded ochre, rust orange and beige palette, risograph print texture, halftone dots, subtle ink grain, antique scientific notebook aesthetic, airy minimal composition, low contrast center, no text, no logo, no watermark --ar 16:9 --v 6.1 --style raw --s 250
```

### White Shanshui Ink Landscape

Use for calm, elegant, scholarly, minimal, Asian-inspired, document, writing, or knowledge product backgrounds.

```text
wide text-safe background, traditional Chinese shanshui ink wash landscape, vast empty warm white rice paper sky, mountains and mist arranged along the bottom edge, small pavilion on the left cliff, terraced hills in the foreground, distant lake and pale mountain silhouettes, delicate ink linework, muted sage green, warm gray, faded ochre and ivory palette, soft watercolor wash, aged paper texture, elegant negative space, peaceful minimal composition, low contrast center area for overlay text, no calligraphy, no text, no logo, no watermark --ar 16:9 --v 6.1 --style raw --s 200
```

### Dark Shanshui Moonlit

Use for dark mode, quiet focus, night themes, reading products, meditation, premium dashboards, or minimal atmospheric UI.

```text
wide text-safe dark background, moonlit Chinese shanshui ink wash landscape, deep navy night sky with large clean empty center area, misty mountains along the lower third, pale moon, subtle lake reflection, small pavilion silhouette on one side, ink wash texture, muted indigo, charcoal, moonlit silver and dark teal palette, elegant negative space, quiet nocturne mood, no calligraphy, no text, no logo, no watermark --ar 16:9 --v 6.1 --style raw --s 220
```

### Monet Field White

Use for light new-tab backgrounds, soft landing pages, calm onboarding, garden products, and classic painterly themes.

```text
wide text-safe background, soft impressionist flower field, large empty pale sky and clean center area, wildflowers and grass along the bottom edge, distant trees and rolling fields, warm morning light, ivory, pale blue, sage green and soft yellow palette, loose oil paint brush strokes, canvas texture, Monet-inspired impressionist landscape, airy peaceful mood, low contrast center, no text, no logo, no watermark --ar 16:9 --v 6.1 --style raw --s 300
```

### Monet Coastal White

Use for coastal, travel, lifestyle, writing, and relaxed productivity surfaces.

```text
wide text-safe background, soft impressionist coastal landscape, large clean empty sky, pale sea and distant cliffs near the lower third, subtle waves and flowers along the bottom edge, bright hazy daylight, ivory, seafoam, pale blue and sandy beige palette, loose oil paint brush strokes, canvas texture, Monet-inspired coastal painting, elegant negative space, no text, no logo, no watermark --ar 16:9 --v 6.1 --style raw --s 280
```

### Monet Lily Pond White

Use for calm, nature, wellness, creative tools, and high-end soft UI backgrounds.

```text
wide text-safe background, impressionist lily pond landscape, clean empty upper center for UI text, water lilies and soft reflections along the lower edge, willow branches lightly framing one side, misty garden background, ivory, pale green, lavender and soft blue palette, loose oil paint texture, gentle brush strokes, Monet-inspired garden pond painting, calm airy composition, no text, no logo, no watermark --ar 16:9 --v 6.1 --style raw --s 300
```

### Dark Monet Lily Nocturne

Use for dark mode, premium calm, nighttime focus, reading, or music-style surfaces.

```text
wide text-safe dark background, impressionist nocturne lily pond, large clean dark sky and center area, water lilies and reflections along the lower edge, faint moonlight, soft garden silhouettes, deep navy, muted violet, dark teal and pale moonlit blue palette, loose oil paint brush strokes, Monet-inspired night garden painting, calm mysterious atmosphere, low contrast UI-safe composition, no text, no logo, no watermark --ar 16:9 --v 6.1 --style raw --s 300
```

### Seurat Riverside White

Use for pointillist, calm, park, editorial, cultural, or refined light backgrounds.

```text
wide text-safe background, quiet riverside park scene, large empty pale sky and clean center area, river and trees arranged along the lower third, tiny distant figures if any, soft pointillist dots, muted pastel palette, ivory, pale blue, sage green and warm beige, Seurat-inspired pointillist landscape, delicate stippled texture, low contrast UI-safe composition, no text, no logo, no watermark --ar 16:9 --v 6.1 --style raw --s 250
```

### White Linocut Topographic

Use for map-like, outdoor, data, infrastructure, geography, systems, or technical editorial backgrounds.

```text
wide text-safe background, minimal topographic mountain landscape, large clean ivory paper area in the center, contour lines and carved mountain shapes along the bottom and corners, subtle map-like terrain pattern, linocut print texture, muted gray, sage, beige and faded blue palette, handmade ink impression, quiet editorial design, low contrast UI-safe composition, no text, no numbers, no labels, no logo, no watermark --ar 16:9 --v 6.1 --style raw --s 220
```

### Dark Linocut Topographic

Use for dark technical surfaces, maps, infrastructure products, observability, or developer tools.

```text
wide text-safe dark background, topographic mountain landscape in linocut style, large clean dark navy center area for UI text, contour lines and carved terrain patterns along the bottom and edges, subtle glowing ridge lines, muted teal, charcoal, deep blue and faded copper palette, handmade ink print texture, atmospheric map aesthetic, elegant minimal composition, no text, no labels, no logo, no watermark --ar 16:9 --v 6.1 --style raw --s 240
```

### White 3D Architecture

Use for clean product UI, settings pages, abstract spatial backgrounds, design tools, and calm SaaS pages.

```text
wide text-safe background, minimal white 3D architectural landscape, large clean empty center area, abstract arches, stairs, columns and soft geometric structures arranged along the bottom and right edge, matte plaster material, soft ambient daylight, ivory, warm gray, pale beige and subtle blue palette, calm gallery-like atmosphere, elegant negative space, low contrast center, no text, no logo, no watermark --ar 16:9 --v 6.1 --style raw --s 180
```

## Batch Generation

When the user wants many prompts, use a permutation prompt:

```text
wide text-safe background for a browser new tab page, {Monet-inspired impressionist field, Monet-inspired coastal landscape, Monet-inspired lily pond, Seurat-inspired riverside park, Chinese shanshui ink wash mountains, risograph mechanical paper collage, linocut topographic mountain map, minimal white 3D architecture}, large clean empty {center area, upper center, left center} for UI overlay, main visual elements concentrated along the {bottom edge, bottom left corner, bottom right corner, right edge}, {warm handmade paper texture, rice paper texture, canvas oil paint texture, risograph grain, linocut ink texture, matte plaster texture}, muted cohesive palette, elegant negative space, low contrast center, soft atmospheric depth, no text, no logo, no watermark --ar 16:9 --v 6.1 --style raw --s {180,240,300}
```

For batch outputs, produce a table with:

```markdown
| Name | Theme | Style | Prompt |
|---|---|---|---|
| cradle-newtab-white-shanshui | white | shanshui | ... |
```

## Naming Scheme

Use this naming pattern:

```text
[product]-[surface]-[theme]-[style]-[scene]-[layout]-[version].webp
```

Default examples:

```text
cradle-newtab-white-shanshui-mountains-bottom-v01.webp
cradle-newtab-white-risograph-mechanical-right-v01.webp
cradle-newtab-dark-linocut-topographic-bottom-v01.webp
cradle-newtab-white-monet-field-bottom-v01.webp
cradle-settings-light-monet-landscape-soft-v01.webp
```

Use `-thumb` only for thumbnail versions:

```text
cradle-newtab-white-shanshui-mountains-bottom-v01-thumb.webp
```

## Theme Groups

Use these groups when organizing a collection.

### White / Soft

```text
monet-field-white
monet-coastal-white
monet-lily-pond-white
seurat-park-white
seurat-riverside-white
shanshui-white
risograph-collage-white
linocut-topographic-white
3d-architecture-white
```

### Dark / Atmospheric

```text
shanshui-moonlit-dark
linocut-topographic-dark
monet-lily-nocturne-dark
fantasy-mountain-dark
cloudscape-dark
architectural-courtyard-dark
```

### Colorful / Expressive

```text
anime-fantasy-mountain
pastel-meadow
whimsical-flower-field
sky-island
dream-valley
```

### Utility / Low Noise

```text
paper-texture-collage
soft-topographic-map
abstract-gradient-landscape
minimal-architectural-forms
```

## Parameter Defaults

Use these defaults unless the user specifies otherwise:

```text
Web hero / landing page:
--ar 16:9 --v 6.1 --style raw --s 200

Browser new tab:
--ar 16:9 --v 6.1 --style raw --s 220

PPT / Keynote background:
--ar 16:9 --v 6.1 --style raw --s 250

Mobile wallpaper:
--ar 9:16 --v 6.1 --style raw --s 300

Poster / social image:
--ar 4:5 --v 6.1 --style raw --s 350

More dreamy:
--s 400-600

More stable:
--s 150-250 --style raw
```

## Prompt Adaptation Workflow

When adapting from a reference image, filename, or user description:

1. Identify the background family:
   - meadow
   - mountain fantasy
   - shanshui
   - risograph collage
   - impressionist
   - pointillist
   - linocut
   - 3D architecture
   - abstract texture

2. Identify the layout:
   - center-safe
   - left-safe
   - right-safe
   - top-safe
   - bottom-safe
   - edge-framed

3. Identify the visual anchor:
   - bottom edge
   - lower left
   - lower right
   - right edge
   - left edge
   - far background

4. Identify the palette:
   - white/pastel
   - dark/nocturne
   - blue/pink fantasy
   - ivory/sage/ochre
   - teal/rust collage
   - navy/silver moonlit

5. Generate the prompt using the formula.

6. Add the fixed negative prompt.

7. Run a self-check before finalizing.

## Self-Check

Before final output, verify:

```markdown
- [ ] Is the requested text area explicitly clean?
- [ ] Are visual details pushed to edges, corners, bottom, or distance?
- [ ] Does the prompt forbid text, logos, and watermarks?
- [ ] Is the center low-contrast?
- [ ] Is the palette coherent?
- [ ] Is the style specific enough to reproduce?
- [ ] Is the aspect ratio suitable for the user’s surface?
- [ ] Would this work behind UI without manual cleanup?
```

If any item fails, revise the prompt.

## Common Mistakes

Avoid these failures:

1. **Only describing a beautiful scene**
   - Bad: `beautiful fantasy landscape`
   - Better: `wide text-safe fantasy background, large clean empty center area, decorative details along the bottom edge`

2. **Putting the subject in the center**
   - Bad for UI backgrounds.
   - Move subject to the lower left, lower right, right edge, or far background.

3. **Forgetting to ban text**
   - Always include `no text, no logo, no watermark`.

4. **Using too much style language without layout constraints**
   - Layout constraints matter more than style adjectives.

5. **Overcrowding the center**
   - Explicitly say `low contrast center` and `no busy details in the middle`.

6. **Overusing famous artist names**
   - Use them as broad style anchors only when useful.
   - Also describe the actual visible style: brush strokes, pointillist dots, ink wash, halftone grain, linocut texture.

## Output Templates

### Single Prompt

```markdown
**Style diagnosis:** [one concise sentence]

```text
[prompt]
```

**Negative prompt:**

```text
[negative prompt]
```
```

### Prompt Set

```markdown
| Name | Use Case | Prompt |
|---|---|---|
| [asset-name] | [where it fits] | `[prompt]` |
```

### Production Batch

```markdown
## Batch Prompt

```text
[permutation prompt]
```

## Fixed Negative Prompt

```text
[negative prompt]
```

## Naming Convention

```text
[naming pattern]
```
```

## Tone

Be direct and practical. The user is usually trying to generate usable background assets, not learn art theory.

Prefer compact explanations and copy-ready prompts.