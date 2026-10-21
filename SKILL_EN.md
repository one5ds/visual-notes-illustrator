# SKILL_EN.md — English Skill Definition (reference copy) · v1.1.0

> This file is the English translation of `SKILL.md`, kept for international users.
> It intentionally carries **no YAML frontmatter** so it will not register as a duplicate Skill.
> To use it as your active Skill, rename it to `SKILL.md` (replacing the Chinese version, or placing it in a separate folder).

**v1.1.0 — Bright & Focused edition**: vivid warm colors (30–40% coverage), one big hero subject (55–65% of the canvas), restrained information density, and the subject pool expanded from 50 to **200 entries** (20 categories × 10).

---

## Core principles

- **Source-driven**: every element (title, concept words, labels, formulas, annotations) must come from the user's source text. No unrelated words inside the artwork.
- **One subject only**: the composition has exactly one Core Subject — big and prominent; everything else orbits it. Never two co-leads.
- **Never repeat**: re-illustrating the same source text must produce a different subject than last time.
- **Readable in 3 seconds**: restraint beats completeness. If a detail doesn't serve the subject, cut it.

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
- **At most 4** key sub-arguments → zone titles (drop the rest, or fold them into annotations)
- 1 core concept word per argument → **Chinese + English** printed-type label (English in ALL CAPS)
- Optionally pick 2–4 short source phrases as **handwritten annotations** (≤12 characters each)

### Step 3 — 20 subjects, pick one
Sample **20** entries **across categories** from the 200-item pool below (every run must differ). List them as **number + name only, no explanation**:

```
1. Prism refraction tower
2. Gear tree
...
20. Spiral galaxy disc
```
End with: "Reply with a number and I'll build the illustration around it." Wait for the number.

### Step 4 — Build the precise prompt
Fill the template below, show it to the user verbatim, then render.

```
[RATIO] {ratio}, {width}×{height}

[TITLE] {central idea in one sentence} — inside a plaque-style title bar
(gold-trimmed plaque or dark banner) at the top or bottom; bold serif printed type, bilingual, large

[CORE SUBJECT] {chosen subject}, at the visual center, **55–65% of the canvas**, richly detailed:
- Legible, sectionable structure with restrained drafting annotations
  (dimension lines, double arrows, axes, section symbols — only where they matter)
- Around it: **2–3** small design sketches (alternate views or exploded view), clean pencil
  linework + hatching
- [COLOR IS THE STAR] key parts of the subject get **saturated marker flat fills**: pick 3–5
  bright theme colors from vermilion, orange-yellow, lemon yellow, emerald, sky blue, royal blue;
  use gradient color bars, bold colored arrows, solid color blocks; metal/wood/glass parts also
  get light washes (warm brown, teal, water green). Color coverage 30–40% — bright, warm, never gray

[ZONES] bilingual printed short labels (cream/light bars + colored leader lines), **no more than 4**:
① {zone 1 CN} / {EN}
② {zone 2 CN} / {EN}
③ {zone 3 CN} / {EN}
(omit zones below 3)

[CANVAS] off-white/white ground with a very faint graph-paper grid (barely visible), generous
margins, no dark background, no dark border blocks

[LINEWORK] crisp HB/2B graphite linework, hatched shadows that stay bright overall; drafting
annotations restrained, serving only key parts

[ACADEMIC] 2–3 handwritten formulas (strongly on-topic), small and precise

[HANDWRITTEN NOTES] 2–4 scratchy-but-legible pencil annotations with arrows pointing at the subject

[ACADEMIC TEXTURE] at most 2 sticky notes, margin numbering; fewer details beat more

[HIDDEN PATTERN] faintly weave in {pattern name} — Chinese clouds/fret, Greek vase ornament,
Arabic geometric, mandala, Andean textile, or Persian miniature — pale gold or a single faint
color, corners and edges only

[LAYOUT] one dominant subject, ≥30% breathing whitespace, readable in three seconds;
no element pile-up

[NEGATIVE] no real people, no 3D render look, no neon gradients, no large dark background,
no words unrelated to the topic, no typos, no watermark, no crowded composition
```

### Step 5 — Render
Load `ImageGen` via ToolSearch, call it through DeferExecuteTool with the prompt and size.
Present the result. Also give the user a **compact prompt (under 120 words)** for pasting into
Doubao / Jimeng / Midjourney.

### Step 6 — Iterate
Preferred iteration levers: subject number, ratio, bright-color combination, pattern, annotation text.

## Visual spec quick reference (v1.1.0 Bright & Focused)

| Dimension | Spec |
|---|---|
| Color | Bright vivid tones, **30–40% color coverage**; 3–5 saturated theme colors, flat fills + gradient arrows |
| Subject | **55–65%** of canvas, single focal point |
| Zones | **≤ 4** bilingual labels |
| Formulas | **2–3**, strongly on-topic |
| Handwritten notes | **2–4**, ≤12 characters each |
| Surrounding sketches | **2–3** views |
| Whitespace | ≥ 30% |
| Ground | Off-white/white + very faint graph paper |
| Pattern | Pale gold / faint single color, corners only |
| Title | Plaque-style bilingual title bar |

## Subject pool (200 entries, 20 categories × 10)

> Sampling rule: pick 20 across categories; never repeat a subject for the same source text.

**I. Cosmos & Sky**: 1 Solar corona / 2 Moon-phase ring / 3 Saturn ring / 4 Star-trail vortex / 5 Meteor belt / 6 Butterfly nebula / 7 Black-hole accretion disk / 8 Earth–moon orbit / 9 Comet tail / 10 Constellation compass
**II. Light & Mirrors**: 11 Prism refraction tower / 12 Kaleidoscope / 13 Convex-lens focus bench / 14 Periscope pipeline / 15 Fiber-optic bouquet / 16 Magnifier archipelago / 17 Revolving lantern / 18 Rainbow droplet / 19 Mirror hall / 20 Sundial gnomon
**III. Gears & Machines**: 21 Gear tree / 22 Gear heart / 23 Gear compass / 24 Clockwork city / 25 Chain-drive bridge / 26 Steam-piston engine / 27 Watch movement / 28 Differential gear set / 29 Crank linkage / 30 Mechanical bird
**IV. Architecture & Structures**: 31 Stepped pyramid / 32 Arch bridge / 33 Honeycomb dome / 34 Cable-stayed tower / 35 Spiral-ramp tower / 36 Skyscraper skeleton / 37 Dome scaffolding / 38 Parthenon columns / 39 Great-Wall battlements / 40 Folded paper city
**V. Vessels & Containers**: 41 Hourglass engine / 42 Onion-section sphere / 43 Distillation flask / 44 Honey-jar drip / 45 Lighthouse kettle / 46 Thermos cross-section / 47 Funnel splitter / 48 Crucible furnace / 49 Ship in a bottle / 50 Water clock
**VI. Vehicles & Voyages**: 51 Multistage rocket / 52 Hot-air balloon basket / 53 Sailboat mast / 54 Steam locomotive / 55 Ornithopter / 56 Submarine cutaway / 57 Cable-car line / 58 Motorcycle engine / 59 Kite formation / 60 Kayak channel
**VII. Natural Growth**: 61 Root network / 62 Fractal fern / 63 Tree-ring disc / 64 Stump cross-section / 65 Bamboo growth chain / 66 Dandelion scatter / 67 Vine trellis / 68 Coral-reef fan / 69 Swarm array / 70 Seed germination chamber
**VIII. Life & Body**: 71 Neuron coral / 72 Vascular tree / 73 DNA spiral staircase / 74 Heart pump station / 75 Butterfly metamorphosis / 76 Honeycomb alveoli / 77 Cell-division ring / 78 Immune shield array / 79 Bone suspension bridge / 80 Cochlea spiral
**IX. Water & Fluids**: 81 Rippling water / 82 Stepped waterfall / 83 Vortex funnel / 84 Ice crystal lattice / 85 Waterwheel mill / 86 Tidal gears / 87 Siphon bend / 88 Spring-layer well / 89 Raindrop timer / 90 Ocean-trench section
**X. Sound & Instruments**: 91 Tuning-fork resonance / 92 Chime-bell array / 93 Violin string bench / 94 Drum-wave membrane / 95 Bagpipe airbag / 96 Vinyl groove disc / 97 Sonar ripple disc / 98 Wind-chime corridor / 99 Conductor waveform / 100 Pan-flute scale pipes
**XI. Writing & Stationery**: 101 Fountain pen with prayer beads / 102 Pencil-shaving curl / 103 Ink-diffusion bottle / 104 Movable-type tray / 105 Folded map / 106 Stitched book spine / 107 Pushpin flight path / 108 Sticky-note waterfall / 109 Typewriter type drum / 110 Seal imprint bench
**XII. Food & Stoves**: 111 Layered cocktail / 112 Flame pan / 113 Popcorn pressure cooker / 114 Steamer stack tower / 115 Candied-haw stack / 116 Coffee extraction tower / 117 Ice-cream cone swirl / 118 Juicer auger / 119 Zoned hotpot / 120 Noodle-pull ladder
**XIII. Sport & Force**: 121 Lever balance / 122 Pulley block / 123 Ballistic parabola / 124 Dumbbell split / 125 Spring dynamometer / 126 Trampoline parabola / 127 Bow tension arch / 128 Pole-vault arc / 129 Hammer-throw orbit / 130 Climbing-hold wall
**XIV. Tools & Hardware**: 131 Hammer and anvil / 132 Caliper opening / 133 Fuse meltdown / 134 Key-bitting row / 135 Lock pin tumbler / 136 Maglev gyro / 137 Welding spark bench / 138 Grinding wheel / 139 Screw jack / 140 Tool-belt roll
**XV. Lamps & Energy**: 141 Incandescent filament / 142 Solar petal array / 143 Windmill blades / 144 Hydro turbine / 145 Battery layer cell / 146 Lighthouse beam sweep / 147 Campfire cone / 148 Firefly constellation / 149 Geothermal well section / 150 Lightning rod
**XVI. Games & Chance**: 151 Puzzle cube / 152 Labyrinth slab / 153 Domino chain reaction / 154 Dice probability cup / 155 Nesting dolls / 156 Playing-card fan / 157 Dartboard target / 158 Go-board eyes / 159 Marble-run track / 160 Block bearing tower
**XVII. Textiles & Patterns**: 161 Andean woven band / 162 Persian carpet warp / 163 Honeycomb weave grid / 164 Silk reeling bench / 165 Knot-record cord / 166 Origami bird / 167 Kite frame pattern / 168 Embroidery hoop face / 169 Tassel spindle / 170 Woven basket pattern
**XVIII. Circuits & Digital**: 171 Circuit-board mountain / 172 Data waterfall / 173 Chip city grid / 174 Signal-tower topology / 175 Binary cascade / 176 Server ice aisle / 177 Sensor dragonfly / 178 Neural-net vine / 179 Current fork junction / 180 Hologram projector bench
**XIX. Ancient & Relics**: 181 Crystal obelisk / 182 Hatching egg / 183 Double-helix staircase / 184 Floating compass / 185 Shattered mask / 186 Lens eyeball / 187 Oracle-bone turtle / 188 Bronze ding tripod / 189 Agate concentric layers / 190 Dunhuang ribbon
**XX. Geometry & Composites**: 191 Parabolic arch cable / 192 Mobius strip band / 193 Klein-bottle maze / 194 Golden spiral shell / 195 Isometric projection frame / 196 Sierpinski triangle tent / 197 Axonometric exploded view / 198 Wave interference pool / 199 Spiral galaxy disc / 200 Rising bubble tower

## Quality checklist

- [ ] Title equals the central idea, plaque-style bar
- [ ] Exactly one core subject at 55–65%, metaphorically sound
- [ ] **Color coverage 30–40%, bright and warm**, 3–5 saturated theme colors
- [ ] Zones ≤4, formulas ≤3, notes ≤4, sketches ≤3 — restrained
- [ ] Whitespace ≥30%, readable in 3 seconds
- [ ] Bilingual labels complete; no stray words
- [ ] Graph-paper ground + pencil sketch + hatched shadows
- [ ] Drafting annotations restrained
- [ ] Hidden pattern in corners only
