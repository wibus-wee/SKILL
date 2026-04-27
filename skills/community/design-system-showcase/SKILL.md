---
name: design-system-showcase
description: Use this skill when the user wants to create a design system showcase project: a portable Agent Skill plus public demo site, design tokens, references, templates, generated assets, PDFs, PNG previews, slide decks, diagrams, packaging scripts, and verification loops. Trigger for requests about building a branded design system repository, extracting a project's visual language, turning product research into reusable templates, or generating polished asset demos from a style system.
---

# Design System Showcase Skill

Create a portable design-system skill package and its showcase site from a real project, product, or brand. The output should feel like a working system: researched visual language, reusable tokens, reference docs, templates, demos, generated assets, and repeatable build checks.

## Core Principles

- Start from real artifacts, not generic taste. Use official product pages, docs, repositories, screenshots, logos, decks, or user-provided materials.
- Keep `SKILL.md` procedural and lean. Put detailed design rules, writing rules, production notes, and token data in `references/`.
- Use progressive disclosure. Tell the agent exactly when to read each reference file.
- Prefer defaults over menus. Pick one primary language path, one build flow, one preview format, and one validation flow unless the user asks for variants.
- Generate assets only after the design language is documented. The demo site and templates must be downstream of the same tokens and rules.
- Never invent brand facts, logos, screenshots, product UI, metrics, dates, or partnerships. Mark gaps or ask once.

## Target Repository Shape

Use this structure unless the host project already has a stronger convention:

```text
.
├── assets
│   ├── demos
│   │   ├── demo-[subject].html
│   │   ├── demo-[subject].pdf
│   │   ├── demo-[subject].png
│   │   └── images
│   ├── diagrams
│   │   └── [diagram-type].html
│   ├── fonts
│   ├── illustrations
│   ├── images
│   │   └── logo.svg
│   └── templates
│       ├── [template].html
│       └── [template]-en.html
├── dist
│   └── [skill-name].zip
├── references
│   ├── design.md
│   ├── production.md
│   ├── tokens.json
│   └── writing.md
├── scripts
│   ├── build.py
│   ├── package-skill.sh
│   └── shared.py
├── index.html
├── index-en.html
├── index-zh.html
├── README.md
├── SKILL.md
├── styles.css
└── vercel.json
```

Add only the files that serve the skill or the showcase. Avoid extra guides such as `INSTALLATION.md`, `QUICKSTART.md`, or process notes unless the user explicitly asks.

## Workflow

### Step 1: Scope the System

Identify the subject and intended outputs.

Record:

- Project name and one-line positioning
- Primary audience
- Supported languages
- Asset types: document templates, web showcase, diagrams, illustrations, slide decks, PDFs, PNG previews
- Runtime constraints: static site, Python PDF generation, PowerPoint generation, image generation, or browser rendering
- Distribution target: local repo, Agent Skill ZIP, hosted demo, or all three

If scope is ambiguous, choose a minimal default:

- `SKILL.md`
- `references/design.md`
- `references/tokens.json`
- `assets/templates/`
- `assets/demos/`
- `scripts/build.py`
- `index.html`
- `README.md`

### Step 2: Gather Source Material

Use primary sources first:

- Official website and docs
- Product screenshots or user-provided captures
- Existing logo, icons, fonts, and brand files
- Repository README, examples, release notes, design files, or landing pages
- Real output samples from the product

Create a short source ledger in working notes before writing design rules:

```markdown
| Source | Type | Date checked | Useful facts | Gaps |
|---|---|---:|---|---|
| [Name](https://example.com) | Official site | YYYY-MM-DD | Logo, tone, product terms | No typography specs |
```

Source rules:

- Current facts such as versions, prices, funding, metrics, launches, and market claims must be checked.
- If sources conflict, use the most official source or ask the user once.
- If a logo, UI screenshot, or product image is missing, mark it as a gap. Do not draw an approximate logo.

### Step 3: Extract the Design Language

Convert the research into a constraint system.

Write `references/design.md` with:

- Design thesis: one sentence that explains the visual system
- Invariants: 8-12 rules the agent should not break casually
- Color tokens: brand, accent, surfaces, text levels, borders, semantic states
- Typography: font stacks, weights, scale, line-height, language fallbacks
- Spacing: base unit, page margins, section rhythm, component padding
- Components: cards, tags, buttons, tables, metrics, quotes, diagrams
- Layout patterns: hero, demo grid, reference page, document page, slide page
- Anti-patterns: concrete mistakes the agent is likely to produce

Write `references/tokens.json` as the machine-readable subset:

```json
{
  "--surface": "#f5f4ed",
  "--panel": "#faf9f5",
  "--brand": "#1B365D",
  "--text": "#141413",
  "--muted": "#6b6a64",
  "--border": "#e8e6dc"
}
```

Token rules:

- Keep token names stable across CSS, templates, and docs.
- Do not allow demo CSS to drift from `tokens.json`.
- Use solid colors for surfaces and badges when rendering to PDF.
- Avoid decorative palettes that are not present in the source material.

### Step 4: Define the Skill Behavior

Write the project `SKILL.md` as an execution guide, not a brochure.

Frontmatter:

- `name`: short kebab-case package name
- `description`: imperative, intent-focused, under 1024 characters
- Mention trigger contexts that users will actually say
- Include near-miss boundaries if the skill should not trigger for generic design chatter

Body:

- Start with the skill's promise in 1-2 lines
- List the reference files and when to read each one
- Define the work sequence from input to output
- Include build and verification commands
- Include gotchas that would otherwise be missed

Use this reference map:

```markdown
## Reference Loading

- Read `references/design.md` before changing colors, typography, spacing, components, or layout.
- Read `references/writing.md` before creating public copy, demo captions, README text, or template prose.
- Read `references/production.md` before exporting PDF, PNG, PPTX, or packaging the skill.
- Read `references/tokens.json` before touching CSS variables or template token blocks.
```

### Step 5: Build Templates and Demos

Create templates after design rules are stable.

Default template families:

- Landing or product overview
- One-page report
- Long-form document
- Resume or profile
- Portfolio or case study
- Slide deck
- Data report
- Changelog or release note
- Diagram primitives

Template rules:

- Templates must be editable source files, not only exported assets.
- Demo files should use realistic content from researched sources or clearly marked fictional samples.
- Each demo should have source HTML or Python plus exported PDF/PNG/PPTX as applicable.
- Reuse the same token names and component rules across all demo types.
- Do not add a template unless it demonstrates a repeatable use case.

### Step 6: Create the Showcase Site

The showcase site should prove the system by displaying real outputs.

Required sections:

- Hero: project name, positioning, core tokens, repository or install link
- Output samples: demo cards linking to PDF/PNG/PPTX or source
- Usage: install and invocation examples
- Design principles: condensed invariants
- Color, typography, spacing, components: visual token reference
- Production notes: how assets are generated and verified

Site rules:

- The first viewport must identify the project and show the design language immediately.
- Use actual generated demo previews, not placeholder rectangles.
- The site must read as a productized system, not a marketing-only page.
- Keep visual decisions synchronized with `references/design.md` and `references/tokens.json`.

### Step 7: Generate Assets

Generate assets in this order:

1. Source templates
2. Demo source files
3. PDFs or slide decks
4. PNG previews
5. Showcase pages
6. Skill ZIP

Use deterministic scripts for repeated work:

- `scripts/build.py`: export demos, verify page counts, check placeholders, scan token usage
- `scripts/shared.py`: central file lists, token lists, target maps
- `scripts/package-skill.sh`: zip tracked files and exclude large or licensed assets

For image generation:

- Use the design thesis and token rules as the prompt base.
- Use real product details from the source ledger.
- Label generated illustrations as illustrations, not screenshots.
- Do not generate replacement logos or fake UI for real products.

### Step 8: Verify and Iterate

Run validation before shipping.

Minimum checks:

```bash
python3 scripts/build.py --check
python3 scripts/build.py --verify
python3 scripts/build.py --check-placeholders assets/demos/demo-[subject].html
./scripts/package-skill.sh
```

Add project-specific checks when needed:

- Token drift: CSS values match `references/tokens.json`
- Page count: PDF outputs stay within target limits
- Font coverage: CJK and mono stacks include fallbacks
- Placeholder scan: no `{{PLACEHOLDER}}` tokens in generated demos
- Visual QA: inspect PNG previews at desktop and mobile widths
- Packaging QA: licensed or oversized assets are excluded from ZIP

If a check fails, fix the source template or token rule first. Do not patch only the exported PDF or PNG.

## Gotchas

- A showcase without real demo assets is not convincing. Create at least one complete demo flow from source to exported preview.
- A skill with only design adjectives is weak. Convert taste into tokens, invariants, templates, and checks.
- A public demo site can drift from the skill. Treat the skill, references, templates, and site as one system.
- PDFs expose small CSS mistakes. Avoid alpha badge backgrounds, hard shadows, unsupported browser-only layout tricks, and missing font fallbacks.
- Large or licensed fonts may belong in the repository for local preview but not in the distributable skill ZIP.
- Do not let `README.md` become the source of truth. The source of truth is `SKILL.md` plus `references/`.
- Do not over-scope the first version. One strong template and one verified demo are better than many unverified placeholders.

## Delivery Checklist

- [ ] `SKILL.md` has accurate frontmatter and concise procedural instructions
- [ ] `references/design.md` captures visual invariants and anti-patterns
- [ ] `references/tokens.json` matches CSS variables
- [ ] `references/production.md` documents export and packaging details
- [ ] `assets/templates/` contains reusable source templates
- [ ] `assets/demos/` contains source files and generated previews
- [ ] `index.html` displays real output samples
- [ ] `scripts/build.py` runs repeatable checks
- [ ] `scripts/package-skill.sh` creates the ZIP and excludes restricted assets
- [ ] README explains what the system is, how to install it, and shows real demos
