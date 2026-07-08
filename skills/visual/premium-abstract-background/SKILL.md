---
name: premium-abstract-background
description: generate reusable prompts for premium minimalist soft 3d abstract backgrounds for product cards, subscription cards, telecom/app marketing visuals, ui hero images, and image generation workflows. use when the user wants controlled text-safe areas, adjustable whitespace placement, soft frosted polymer materials, milky acrylic, silicone-gel forms, translucent folded films, airbrushed gradients, calm pastel 3d objects, or high-end technology advertising aesthetics. also use when analyzing reference images to extract reusable background prompt patterns without copying text, logos, ui labels, or brand-specific content.
---

# Premium Abstract Background Prompting

## Goal

Create reusable image-generation prompts for high-end minimalist soft 3D abstract backgrounds.

The prompts must control:

1. where the visual object appears
2. where the text-safe area appears
3. approximately how much space each zone occupies
4. how the object fades into the text-safe area
5. the material, color, lighting, and fine-detail behavior
6. negative constraints that prevent clutter, fake text, logos, UI elements, hard glass, or cheap gradient wallpaper

Do not generate an image unless the user explicitly asks for image generation. Usually, produce reusable prompts.

## Core visual formula

Use this formula as the default:

```text
clean white or very light gray background
+ controlled text-safe area
+ partially cropped soft 3d abstract object zone
+ frosted translucent polymer, milky acrylic, silicone-gel, or soft folded film
+ airbrushed pastel gradients
+ high-key diffused studio lighting
+ broad blurred highlights
+ gentle fade into white
+ no text, no logo, no UI elements
````

The result should feel like a premium mobile app, telecom subscription card, security/VPN card, cloud product card, or high-end consumer technology campaign.

## Important material correction

Do not default to hard glass.

The reference style is usually softer than glass. Prefer:

```text
soft frosted polymer
milky acrylic
silicone-gel material
soft translucent plastic film
frosted gel shapes
airbrushed translucency
cloudy interior
diffused translucency
matte-gloss surface
cushioned rounded forms
```

Use hard-glass terms only when explicitly needed for a more reflective style. Avoid defaulting to:

```text
hard glass
crystal
sharp refraction
sharp caustics
mirror-like reflection
jewelry-like transparency
```

If a prompt uses “glass,” soften it with:

```text
frosted, milky, diffused, soft, cloudy, low-contrast, airbrushed, not sharp, not crystalline
```

## Layout model

Always describe the composition as three zones:

```text
Text-safe area: clean low-detail area where typography can be overlaid.
Visual object zone: where the abstract 3D object or material appears.
Fade transition zone: the soft gradient between the object zone and the text-safe area.
```

Do not only say “large negative space.” Specify the text-safe area position and approximate percentage.

## Text-safe area rules

Use this module in most prompts:

```text
Reserve a clean text-safe area occupying approximately [XX%] of the canvas, located at [POSITION].
This area must remain mostly white or very light gray, with only a faint pastel haze or soft gradient.
Keep it free of detailed shapes, folds, shadows, strong highlights, texture, objects, icons, logos, UI elements, and text.
Keep all colorful abstract forms outside this region, or let them enter only as a very soft low-contrast fade.
```

Recommended values:

```text
[XX%] = 40–60%
[POSITION] = left side, right side, bottom third, lower half, center, upper third
```

Common choices:

```text
left 55–60% text-safe area, right 40–45% visual object zone
bottom 40–45% text-safe area, upper 55–60% visual object zone
center 45–55% text-safe area, subtle objects near edges or corners
right 55–60% text-safe area, left 40–45% visual object zone
```

## Visual object zone rules

Use this module to control the decorative 3D object:

```text
Place the main abstract 3D form in the opposite region from the text-safe area, occupying approximately [YY%] of the canvas.
The form should be partially cropped by the frame.
Keep the strongest color, soft volume, folds, highlights, shadows, and fine details inside the visual object zone.
The form should not invade the text-safe area except through a very soft fade.
```

Recommended value:

```text
[YY%] = 30–50%
```

Use cropping deliberately. A partially cropped object usually feels more premium and less like centered clip art.

## Material vocabulary

Choose one material family per prompt unless the user asks for mixed variants.

Good material phrases:

```text
soft frosted polymer primitives
milky acrylic discs and capsules
silicone-gel rounded forms
floating frosted gel objects
soft translucent polymer film
folded milky acrylic ribbon
airbrushed translucent membrane
soft glossy gel sheet
cloudy blue gel primitives
milky pink gel membrane
silk-like translucent gel sheet
pearl-like liquid surface
single translucent liquid droplet
```

Default material behavior:

```text
smooth, thick, cushioned, semi-transparent, softly luminous, slightly cloudy inside, matte-gloss, low-contrast, airbrushed, with broad diffused highlights, soft shadow blooms, and shallow depth of field
```

Avoid making the object look like a cheap toy, flat wallpaper, hard plastic render, crystal, or realistic product object.

## Lighting rules

Use:

```text
high-key diffused studio lighting
broad blurred highlights
soft ambient occlusion
gentle shadow blooms
low contrast
clean high-key exposure
creamy overexposed white fade
soft focus
airy atmosphere
airbrushed tonal transitions
```

Avoid:

```text
hard shadows
harsh contrast
dark cinematic lighting
realistic room lighting
dirty texture
heavy grain
sharp plastic toy look
hard glass reflections
crystalline caustics
overly complex surfaces
```

## Color rules

Use restrained pastel-to-medium gradients, with color strongest in the object zone and fading toward the text-safe area.

Good palettes:

```text
baby blue, powder blue, pale azure, soft cyan, cool gray-blue, milky white
cyan, azure blue, turquoise, violet, lavender, magenta, warm yellow, soft green
blush pink, peach, coral red, rose, pale lavender, soft violet, milky white
lime green, pale yellow, soft chartreuse, pearl white, very light gray
lavender, pearl white, soft blue, pale violet
```

The color should appear to come from soft volume, cloudy translucency, overlapping layers, or diffused internal gradients. Avoid flat painted surfaces.

## Fine-detail rules

Fine detail should be subtle and soft. Do not overuse sharp caustics.

Good fine-detail phrases:

```text
broad blurred highlights
soft internal tonal variation
airbrushed gradient transitions
cloudy interior
very faint rim glow
soft blue shadow blooms
pale diffused shadows
subtle lens-like softness
faint curved contour lines
extremely sparse air-bubble-like specks
overlapping translucent layers
```

Use these only when needed for specific material:

```text
thin soft rim highlights along folded edges
subtle internal diffusion
soft caustic-like color transitions
faint radial light streaks
tiny glossy highlight lines
```

Avoid:

```text
sharp caustics
crisp glass refraction
hard rim lights
mirror highlights
busy micro-detail
dirty speckles
```

## Master prompt template

Use this when the user asks for a reusable prompt.

```text
Create a premium minimalist soft 3D abstract background for a high-end technology product card.

Canvas layout:
Reserve a clean text-safe area occupying approximately [XX%] of the canvas, located on the [POSITION].
This area should remain mostly white or very light gray, with only a faint pastel haze or soft gradient.
Keep it free of detailed shapes, shadows, strong highlights, texture, icons, logos, UI elements, and text.

Visual object:
Place the main abstract 3D form in the opposite region, occupying approximately [YY%] of the canvas.
The form should be partially cropped by the frame and should not enter the text-safe area except as a very soft low-contrast fade.
Use [MATERIAL TYPE], with [STRUCTURE DETAILS].

Material and lighting:
The material should look smooth, thick, cushioned, semi-transparent, softly luminous, slightly cloudy inside, and matte-gloss rather than hard glass.
Use high-key diffused studio lighting, broad blurred highlights, gentle shadow blooms, subtle ambient occlusion, shallow depth of field, clean high-key exposure, airy atmosphere, and low contrast.

Color:
Use [COLOR PALETTE].
The color intensity should be strongest near the abstract object and fade gently toward the text-safe area.

Style:
Premium mobile app subscription card background, telecom product advertising, futuristic consumer technology visual, clean, calm, airy, friendly, high-end.

Negative:
No text, no typography, no logo, no icons, no UI buttons, no people, no hands, no phone mockup, no product object, no realistic room, no landscape, no hard glass, no crystal, no sharp refraction, no sharp caustics, no mirror reflections, no hard shadows, no harsh contrast, no cheap plastic toy look, no busy pattern, no heavy grain, no dirty texture, no watermark.
```

## Layout variants

### Left text-safe area, right object

Use for upgrade cards, pricing cards, and marketing copy placed on the left.

```text
Reserve the left 55–60% of the canvas as a clean text-safe area.
Keep it pure white or very light gray, low contrast, and free of detailed shapes.
Place the main abstract soft translucent 3D form on the right 40–45%, partially cropped by the top, right, and bottom edges.
The strongest color, soft folds, shadow blooms, and highlights should stay on the right and softly fade toward the left.
```

### Bottom text-safe area, top object

Use for vertical cards, captions, feature cards, and centered bottom copy.

```text
Reserve the bottom 40–45% of the canvas as a clean text-safe area.
Keep it mostly white or very light gray, with only a faint pastel haze and no detailed shapes.
Place the main abstract soft translucent 3D form in the upper 55–60%, partially cropped by the top or side edges.
Use a vertical fade from soft colored volume at the top into clean white at the bottom.
```

### Center text-safe area, edge objects

Use for centered headlines.

```text
Reserve the center 45–55% of the canvas as a clean text-safe area.
Keep the center pale, low-detail, and readable.
Place soft translucent abstract forms near the outer edges or corners only.
The forms should remain subtle and should not compete with the center content.
```

### Right text-safe area, left object

Use for right-aligned copy.

```text
Reserve the right 55–60% of the canvas as a clean text-safe area.
Place the abstract soft translucent 3D form on the left 40–45%, partially cropped by the left and top edges.
Let the colors and soft volume be strongest on the left and fade gently toward the right.
```

## Background type: soft floating blue polymer primitives

Use this when the user wants a calm premium technology background with abstract floating blue objects, suitable for security, VPN, eSIM, cloud, protection, privacy, or network-related product cards.

This is not a glass style. The objects should look like frosted translucent polymer, milky acrylic, or silicone-gel.

```text
Create a calm premium 3D abstract background for a telecom feature card.

Canvas layout:
Use a vertical rounded-card composition.
Reserve the lower 42–45% of the canvas as a clean near-white text-safe area with only a faint pale-blue haze.
Keep this area low-contrast, smooth, readable, and free of detailed shapes, shadows, highlights, icons, logos, UI elements, and text.

Visual object:
In the upper 45–55% of the image, arrange a sparse set of floating soft rounded blue primitives near the top edge, partially cropped by the frame.
Include:
- one hollow ring at the upper left, partially cropped
- one short diagonal capsule rod near the top center-left
- one circular disc near the upper center-right
- one larger soft rounded disc at the upper right
- one blurred circular form behind them near the center

Material:
Use soft frosted translucent polymer, milky acrylic, and silicone-gel material.
The objects should feel thick, smooth, cushioned, slightly cloudy inside, and softly luminous.
They should not look like hard glass, crystal, or sharply reflective material.

Shape and surface behavior:
Use rounded edges, thick soft profiles, airbrushed tonal transitions, subtle internal blue variation, and broad blurred highlights.
The surfaces should be smooth and matte-glossy, with no sharp specular reflections.
The objects should feel weightless and gently floating.

Lighting and shadows:
Use high-key diffused studio lighting with very low contrast.
Add broad diffused highlights and soft blue shadow blooms underneath the objects.
The shadows should be blurry, light, atmospheric, and fade downward into the background before reaching the text-safe area.
Use shallow depth of field and slight background blur.

Color:
Use a restrained monochrome palette centered on baby blue, powder blue, pale azure, cool gray-blue, and milky white.
The upper area should have slightly stronger blue saturation, fading smoothly into near-white in the lower text-safe area.

Style:
Premium minimalist telecom product card, calm, clean, airy, futuristic, trustworthy, soft, elegant.

Negative:
No text, no logo, no icons, no UI elements, no people, no hands, no phone mockup, no realistic room, no metallic surface, no hard glass, no crystal, no sharp reflections, no strong refraction, no harsh contrast, no hard shadows, no busy pattern, no heavy grain, no dirt, no watermark.
```

Short version:

```text
Premium minimalist 3D abstract background for a mobile app or telecom card. Vertical rounded-card layout. Reserve the lower 42–45% as a clean white text-safe area with a faint pale-blue haze. In the upper 45–55%, place a sparse cluster of floating soft rounded 3D primitives, partially cropped by the top edge: a hollow ring on the upper left, a diagonal capsule rod near the top center-left, a circular disc near the upper center-right, a larger rounded disc on the upper right, and one blurred circular form in the center background. Use soft frosted translucent polymer, milky acrylic, and silicone-gel material. Smooth thick cushioned forms, rounded edges, slightly cloudy interiors, airbrushed tonal transitions, broad soft highlights, very soft blue shadow blooms, shallow depth of field, high-key studio lighting, low contrast. Use monochrome baby blue, powder blue, pale azure, milky white, and cool gray-blue. Calm, airy, clean, trustworthy, premium. No text, no logo, no icons, no UI, no people, no hard glass, no crystal, no sharp reflections, no harsh shadows, no watermark.
```

## Background type: soft folded iridescent polymer ribbon

Use this when the user wants a premium telecom or subscription upgrade card, with copy on the left and a large colorful abstract object on the right.

This style can be more saturated than the blue primitives, but it should still feel soft and translucent, not hard or crystalline.

```text
Create a premium minimalist 3D abstract background for a high-end technology subscription card.

Canvas layout:
Reserve the left 55–60% of the canvas as a clean text-safe area. Keep it pure white or very light gray, low contrast, and free of detailed shapes, shadows, highlights, texture, icons, logos, UI elements, and text.

Visual object:
Place a large stacked iridescent soft translucent polymer ribbon structure on the right 40–45% of the canvas, partially cropped by the top, right, and bottom edges.
The form should look like overlapping folded sheets of flexible acrylic film or soft translucent polymer ribbon, with multiple curled layers, looped edges, and sweeping diagonal folds.

Important structure details:
Use several semi-transparent ribbon layers crossing over each other.
Include soft rim glow along the folded edges, blurred internal color transitions, and gentle tonal shifts where layers overlap.
The object should have a dominant blue and cyan mass in the lower right, with magenta, violet, lavender, turquoise, warm yellow, and soft green reflections in the upper folds.
Keep the strongest color, folds, volume, and highlights entirely on the right side, fading gently toward the left text-safe area.

Material and lighting:
The material should be soft, semi-transparent, glossy, smooth, luminous, and slightly milky, like thin flexible polymer film.
Use diffused studio lighting, broad soft highlights, gentle shadows, subtle ambient occlusion, shallow depth of field, and clean high-key exposure.
Do not make the ribbon look like sharp crystal glass.

Color:
Use saturated but clean gradients of cyan, azure blue, turquoise, violet, magenta, lavender, warm yellow, and soft green.
The colors should come from overlapping translucent layers and soft internal gradients, not from flat painted surfaces.

Style:
Premium mobile carrier subscription card, futuristic consumer technology advertising, clean app-store product visual, elegant, airy, high-end.

Negative:
No text, no typography, no logo, no icons, no UI buttons, no people, no hands, no phone mockup, no product object, no realistic room, no landscape, no hard glass, no crystal, no sharp refraction, no sharp caustics, no hard shadows, no harsh contrast, no cheap plastic toy look, no busy pattern, no grain, no noise, no watermark.
```

Short version:

```text
Premium minimalist 3D abstract background for a technology subscription card. Reserve the left 55–60% as a clean white text-safe area. On the right 40–45%, place a large stacked iridescent soft translucent polymer ribbon structure, partially cropped by the top, right, and bottom edges. Overlapping folded sheets of flexible acrylic film, curled layers, looped edges, sweeping diagonal folds. Dominant cyan and azure blue mass in the lower right, with magenta, violet, lavender, turquoise, warm yellow, and soft green internal gradients in the upper folds. Soft rim glow along folded edges, blurred color transitions where transparent layers overlap. Diffused studio lighting, broad soft highlights, subtle ambient occlusion, shallow depth of field, clean high-key exposure, premium telecom subscription card aesthetic. No text, no logo, no icons, no people, no phone, no hard glass, no crystal, no sharp reflections, no clutter, no watermark.
```

## Background type: milky pink gel membrane

Use this when the user wants a soft pink/violet feature card with visible but subtle internal material details and a bottom text-safe area.

```text
Create a premium minimalist 3D abstract background for a high-end mobile app or telecom subscription card.

Canvas layout:
Reserve the lower 40–45% of the canvas as a text-safe area.
Keep it very light, mostly white with a soft milky blush-pink haze, low contrast, and readable for overlay text.
Allow only extremely subtle pastel fog in this area, with no strong shapes.

Visual composition:
Place a translucent pink gel-like acrylic membrane across the upper half of the image, concentrated toward the upper right and partially cropped by the top and right edges.
The form should feel like a soft flexible glossy film or liquid gel sheet, not a hard object.
Use broad blurred folds, curved transparent layers, and overlapping soft gradients.

Important fine details:
Add subtle internal material details inside the membrane: faint radial light streaks near the upper-center area, tiny glossy highlight lines, soft lens-like distortions, and very faint curved contour lines on the left side.
Include a few extremely sparse tiny specks or air-bubble-like imperfections to make the translucent material feel physical, but keep them minimal and elegant.

Material and lighting:
The material should be semi-transparent, glossy, smooth, softly luminous, slightly milky, and low-contrast, with subtle subsurface scattering.
Use diffused studio lighting, broad soft highlights, low contrast, shallow depth of field, and a creamy overexposed white fade toward the bottom.

Color:
Use blush pink, peach, coral red, rose, pale lavender, soft violet, and milky white.
The strongest saturation should appear in the upper-right object zone, with a faint violet-magenta band near the right edge.
Fade all color smoothly into white and pale pink toward the lower text-safe area.

Style:
Premium consumer technology advertising background, soft futuristic mobile subscription card aesthetic, airy, glossy, elegant, minimal, high-end.

Negative:
No text, no typography, no logo, no icons, no UI buttons, no people, no hands, no phone mockup, no product object, no realistic room, no landscape, no hard glass, no crystal, no sharp caustics, no hard shadows, no harsh contrast, no busy pattern, no heavy grain, no dirty texture, no watermark.
```

Short version:

```text
Premium minimalist 3D abstract background for a mobile subscription card. Lower 40–45% reserved as a light text-safe area, mostly white with soft milky blush-pink haze. Upper half contains a translucent pink gel-like acrylic membrane, concentrated in the upper right and partially cropped by the top and right edges. Soft flexible glossy film, liquid gel sheet, blurred folds, overlapping transparent layers. Add subtle internal material details: faint radial light streaks near the upper center, tiny glossy highlight lines, soft lens-like distortions, faint curved contour lines, and a few extremely sparse air-bubble-like specks. Blush pink, peach, coral red, rose, pale lavender, violet, and milky white gradients. Diffused studio lighting, broad soft highlights, low contrast, shallow depth of field, creamy overexposed white fade toward the bottom. No text, no logo, no icons, no phone, no people, no hard glass, no crystal, no clutter, no watermark.
```

## Background type: lavender liquid droplet

Use this when the user wants a calm single-object background with a soft droplet, glossy gel surface, and bottom text-safe area.

```text
Create a premium minimalist 3D abstract background with a pale lavender and white gradient.

Canvas layout:
Reserve the bottom 45% of the canvas as a clean text-safe area, mostly white, low contrast, and free of detailed shapes, icons, logos, UI elements, and text.

Visual object:
Place a single translucent soft liquid droplet near the upper center, resting on a glossy gel-like surface with very soft ripple depressions.
The object zone should occupy the upper 40–50% of the canvas and fade smoothly into white before reaching the text-safe area.

Material and lighting:
The material should be smooth, softly luminous, milky, lightly translucent, and ethereal, with diffused highlights, subtle ambient occlusion, shallow depth of field, and gentle shadows.
Avoid hard glass or crystal clarity.

Color:
Use pearl white, pale lavender, soft blue, and milky violet undertones.
Keep the color subtle and calm, fading into clean white toward the bottom.

Style:
Premium mobile app feature card, calm international roaming or connectivity visual, soft futuristic consumer technology aesthetic.

Negative:
No text, no logo, no icons, no UI buttons, no people, no product mockup, no realistic environment, no hard glass, no crystal, no sharp reflection, no hard shadows, no harsh contrast, no busy pattern, no watermark.
```

Short version:

```text
Premium minimalist 3D abstract background with a pale lavender and white gradient. Reserve the bottom 45% as a clean white text-safe area. Place a single translucent soft liquid droplet near the upper center on a glossy gel-like surface with soft ripple depressions. Smooth luminous milky material, pearl white, pale lavender, soft blue undertones, diffused highlights, gentle shadows, shallow depth of field, airy overexposed white fade. No text, no logo, no icons, no people, no product mockup, no hard glass, no crystal, no clutter, no watermark.
```

## Background type: lime translucent gel sheet

Use this when the user wants a bright energetic green card with a soft flexible sheet and bottom text-safe area.

```text
Create a premium minimalist 3D abstract background for a vertical technology marketing card.

Canvas layout:
Reserve the bottom 45% of the image as a clean text-safe area, almost white, with only a faint lime-to-white gradient.
Keep it low-detail and readable.

Visual object:
Place a bright lime green translucent glossy gel sheet across the upper 55% of the frame, partially cropped by the top and side edges.
The sheet should feel soft, flexible, semi-transparent, and silk-like, with smooth folds, subtle broad highlights, and blurred edges.

Material and lighting:
Use diffused studio lighting, broad soft highlights, gentle shadows, subtle ambient occlusion, shallow depth of field, and a smooth white fade toward the bottom.
The material should be soft gel or translucent polymer, not hard glass.

Color:
Use lime green, pale yellow, soft chartreuse, pearl white, and very light gray.
Keep the strongest color and texture in the upper object zone, fading gently into white toward the bottom.

Style:
Premium mobile app feature card, bright futuristic consumer technology advertising, clean, minimal, energetic, high-end.

Negative:
No text, no logo, no icons, no UI buttons, no people, no phone mockup, no hard glass, no sharp reflections, no clutter, no hard shadows, no harsh contrast, no grain, no watermark.
```

Short version:

```text
Premium minimalist 3D abstract background for a vertical technology marketing card. Reserve the bottom 45% as a clean white text-safe area with faint lime haze. Upper 55% contains a bright lime green translucent glossy gel sheet, partially cropped by the top and side edges. Soft flexible silk-like membrane, smooth folds, broad soft highlights, diffused studio lighting, shallow depth of field, white fade toward the bottom. No text, no logo, no icons, no people, no phone, no hard glass, no clutter, no watermark.
```

## Innovation pattern: soft connectivity shield

Use this when the user asks for a new concept based on the reference style, not a direct replication.

```text
Create a premium minimalist soft 3D abstract background for a high-end mobile connectivity, eSIM, VPN, or telecom subscription card.

Canvas layout:
Reserve the lower 42–45% of the canvas as a clean text-safe area.
Keep this area mostly white or very light gray, with only a faint milky blue-pink haze.
It must remain readable, low-contrast, and free of detailed shapes, strong shadows, highlights, texture, icons, logos, UI elements, and text.

Visual composition:
Place the main abstract composition in the upper 55–58% of the canvas, slightly biased toward the upper right and partially cropped by the top and right edges.
The composition should feel soft, airy, and weightless, like a set of floating frosted polymer forms and folded translucent films.

Object structure:
Create a loose cluster of soft rounded floating forms: frosted blue gel spheres, oval discs, capsule rods, hollow rings, and smooth circular pads.
Combine them with one or two broad folded translucent polymer ribbons that curve gently through the upper-right area.
The forms should look inflated, cushioned, and softly molded rather than sharp or hard.

Material:
Use soft translucent silicone, frosted acrylic, milky polymer film, and glossy gel material.
The surfaces should be smooth, diffused, semi-transparent, softly luminous, and slightly cloudy inside.
Avoid hard glass behavior. Any translucency should be blurred and creamy, not sharp or crystalline.

Edges and details:
Use soft rounded edges, feathered silhouettes, broad blurred highlights, gentle internal color gradients, and subtle depth blur.
Add only very faint rim glow along some folded edges.
Include soft shadow blooms and pale blue diffused shadows beneath the floating objects, fading before they reach the text-safe area.

Lighting:
Use high-key diffused studio lighting, low contrast, soft ambient occlusion, creamy overexposed white fade, shallow depth of field, and an airy app-store advertising look.
Highlights should be large, smooth, and blurred, never sharp.

Color:
Use a calm premium palette of sky blue, cyan, powder blue, pale azure, turquoise, lavender, soft violet, blush pink, peach, and milky white.
Keep the strongest saturation in the upper object zone.
Let all colors fade smoothly into white and pale blue-pink haze toward the lower text-safe area.

Style:
Premium mobile carrier subscription card, eSIM protection feature card, VPN security card, soft futuristic consumer technology advertising, clean, calm, friendly, elegant, high-end.

Negative:
No text, no typography, no logo, no icons, no UI buttons, no people, no hands, no phone mockup, no product object, no realistic room, no landscape, no hard glass, no crystal, no sharp refraction, no sharp caustics, no metallic surface, no hard shadows, no harsh contrast, no cheap plastic toy look, no busy pattern, no heavy grain, no dirty texture, no watermark.
```

## Prompt refinement rules

If the output looks too hard or glassy:

```text
Remove glass, crystal, refraction, and caustics.
Add: soft frosted polymer, milky acrylic, silicone-gel, cloudy interior, diffused translucency, broad blurred highlights, matte-gloss, airbrushed gradients.
Add negative terms: no hard glass, no crystal, no sharp reflections, no sharp refraction.
```

If the output looks too flat:

```text
Add: soft 3D volume, cushioned rounded forms, subtle ambient occlusion, soft shadow blooms, shallow depth of field, broad blurred highlights.
```

If the output looks too busy:

```text
Increase the text-safe area percentage and explicitly keep detailed shapes outside that area.
```

If the model invents text or UI:

```text
Strengthen the negative prompt: no text, no typography, no logo, no icons, no UI buttons, no interface elements.
```

If the result looks cheap or toy-like:

```text
Add: premium technology advertising, high-key diffused studio lighting, low contrast, airy, restrained palette, milky translucency, not a plastic toy.
```

If the object becomes too centered:

```text
Add: partially cropped by the frame, placed near the edge, object zone only, opposite the text-safe area.
```

If the text-safe area gets contaminated:

```text
Add: keep the text-safe area mostly pure white, low contrast, and free of folds, objects, shadows, highlights, texture, and detailed gradients.
```

## Output behavior

When the user asks for a reusable prompt, return:

1. one final prompt
2. optional negative prompt
3. optional layout parameters if useful

When the user asks for a specific layout, ask for no clarification unless the requested position is ambiguous. Choose a sensible percentage:

```text
left copy layout: left 55–60% text-safe area
right copy layout: right 55–60% text-safe area
bottom copy layout: bottom 40–45% text-safe area
center copy layout: center 45–55% text-safe area
```

When the user provides reference images, analyze only the background style. Do not copy text, logos, UI labels, brand names, exact commercial copy, or exact brand layout.

When the user asks for multiple variants, vary only one or two dimensions at a time:

```text
layout position
material type
color palette
object scale
crop direction
fine-detail level
softness level
```

Do not produce many unrelated visual styles in the same answer.

## Default concise output format

Use this format unless the user asks for detailed analysis:

```text
Prompt:
[final image-generation prompt]

Negative:
[negative constraints]

Layout parameters:
- text-safe area: [position and percentage]
- visual object zone: [position and percentage]
- fade direction: [direction]
- material family: [material]
- softness level: [soft / very soft / ultra-soft]
```
