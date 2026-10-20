# SKILL_EN.md — English Skill Definition (reference copy)

> This file is the English translation of `SKILL.md`, kept for international users.
> It intentionally carries **no YAML frontmatter** so it will not register as a duplicate Skill.
> To use it as your active Skill, rename it to `SKILL.md` (replacing the Chinese version, or placing it in a separate folder).

---

## Core principles

- **Source-driven**: every element (title, concept words, labels, formulas, annotations) must come from the user's source text. No unrelated words inside the artwork.
- **One subject only**: the composition has exactly one Core Subject; everything else orbits it. Never two co-leads.
- **Never repeat**: re-illustrating the same source text must produce a different subject than last time.

## Workflow

### Step 0 — Get the source text
If the user hasn't provided it, ask for it ("paste the paragraph you want visualized").

### Step 1 — Ask for the canvas ratio first (mandatory)
Use AskUserQuestion with fixed options:
1. `16:9 landscape` (wide infographic; blog headers, deck covers)
2. `4:3 landscape` (classic lecture layout)
3. `3:4 portrait` (paper figure / notebook page)
4. `9:16 portrait` (mobile long-form / social poster)

Pixel specs: 16:9 → 1920×1080; 4:3 → 1184×888; 3:4 → 896×1152; 9:16 → 1080×1920.
**Do not skip this step.**

### Step 2 — Decompose the source
Produce a structure-breakdown table:
- Central idea (one sentence) → **main title**
- 3–6 sub-arguments → **zone titles**
- 1–2 core concept words per argument → **on-image labels**
- Every concept word gets a **Chinese + English** printed-type label
- Optionally pick 2–4 short source phrases as **handwritten annotations** (≤12 characters each)

### Step 3 — 20 subjects, pick one
Randomly sample **20** from the 50-item pool below (each run must differ). List them as **number + name only, no explanation**:

```
1. Prism refraction tower
2. Gear tree
...
20. Spiral galaxy disc
```
End with: "Reply with a number and I'll build the illustration around it." Wait for the number.

**50-item pool**: prism refraction tower, gear tree, neuron coral, floating compass, fission nucleus, double-helix staircase, hourglass engine, folded paper city, root network, honeycomb dome, crystal obelisk, origami bird, gear heart, onion-section sphere, fractal fern, lever balance, labyrinth slab, rising bubble tower, pendulum orbit, multistage rocket, crucible furnace, seed germination chamber, magnetic levitation gyro, creeping pipe body, puzzle cube, stepped pyramid, fiber-optic bouquet, swarm array, lock-and-key mechanism, lens eyeball, vortex funnel, shattered mask, arch bridge, windmill blades, tree-ring disc, folded map, vascular tree, ice crystal lattice, volcano section, gear compass, hatching egg, circuit-board mountain, pulley block, rippling water, stepped waterfall, nesting dolls, ballistic parabola, moon-phase disc, sundial gnomon, spiral galaxy disc.

### Step 4 — Build the precise prompt
Fill the template below, show it to the user verbatim, then render.

```
[RATIO] {ratio}, {width}×{height}

[TITLE] {central idea in one sentence} — top of canvas, bold serif printed type, bilingual

[CORE SUBJECT] {chosen subject}, at the visual center, ~40% of canvas, pencil-sketched,
structure legible and sectionable
- Internal cutaway: {2-3 internal layers / components}
- Around it: 3-4 small design sketches — front / side / 45° top / exploded view,
  clean linework + pencil hatching

[ZONES] bilingual printed short labels with leader lines
① {zone 1 CN} / {EN}
② {zone 2 CN} / {EN}
③ {zone 3 CN} / {EN}
④ {zone 4 CN} / {EN}

[CANVAS] white-dominant, faint pale-blue 5 mm graph-paper grid, no dark background,
no dark border blocks

[LINEWORK] crisp HB/2B graphite pencil linework, hatching and cross-hatching for shadow,
drafting annotations: dimension lines, arrows, coordinate axes, angle arcs, data numbers,
vectors, section symbols

[ACADEMIC] 3-5 handwritten formulas relevant to the topic
(e.g. F=ma, E=mc², ΔS≥0, y=f(x), a chemical chain structure, a DNA double helix) —
never off-topic formulas

[COLOR] grayscale base with low-saturation marker accents on key parts only,
marker bars / highlighter strokes on priority info, color coverage < 12%

[INFORMATION FLOW] arrows, numbers, dashed lines and data-flow lines show direction;
numbered tags ①②③ map 1:1 to subject parts

[HANDWRITTEN NOTES] 4-6 scratchy-but-legible pencil annotations: {note 1}, {note 2}, {note 3},
with underlines and circled marks

[ACADEMIC TEXTURE] sticky notes (pale yellow/pale blue, slightly curled, tiny handwriting),
paper clips and tape marks, margin numbering, punch holes, red correction marks

[HIDDEN PATTERN] faintly weave in {pattern name} — Chinese fret / Greek vase ornament /
Arabic geometric / mandala / Andean textile / Persian miniature — as an underlay or surface
texture; never compete with the subject

[LAYOUT] content fills the canvas, high information density but not crowded,
strict grid alignment, breathing whitespace

[NEGATIVE] no real people, no 3D render look, no neon gradients, no large dark background,
no words unrelated to the topic, no typos, no watermark
```

### Step 5 — Render
Load `ImageGen` via ToolSearch, call it through DeferExecuteTool with the prompt and size.
Present the result. Also give the user a **compact prompt (under 120 words)** for pasting into
Doubao / Jimeng / Midjourney.

### Step 6 — Iterate
Preferred iteration levers: subject number, ratio, pattern, annotation text, color coverage.

## Quality checklist

- [ ] Title equals the central idea
- [ ] Exactly one core subject, metaphorically sound
- [ ] Bilingual labels complete; no stray words
- [ ] Graph-paper ground + pencil sketch + hatched shadows
- [ ] Drafting annotations present (arrows / dimensions / axes / angles / vectors)
- [ ] 1–5 discipline-relevant formulas
- [ ] Color coverage under 12%
- [ ] Hidden pattern present
- [ ] Content fills the canvas; no dark margins
