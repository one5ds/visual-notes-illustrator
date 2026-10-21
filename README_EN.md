<div align="center">

## AIOpenVC · Open AI Toolkit for Investment

**Academic Visual-Notes Illustrator — AI Skill**

*Reshaping how primary-market information gets expressed, with AI · by Yijue*

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](./LICENSE)
[![Stars](https://img.shields.io/github/stars/one5ds/visual-notes-illustrator?style=flat-square&label=Stars&color=yellow)](https://github.com/one5ds/visual-notes-illustrator/stargazers)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](./CONTRIBUTING.md)
[![i18n](https://img.shields.io/badge/lang-中文%20%2F%20English-blue.svg)](./README.md)

⭐ **If this method helps you, hit Star in the top-right corner — it's the best support you can give.** ⭐

</div>

---

> Turn any paragraph into an academic, hand-drawn "visual notes" illustration — and get a precise, ready-to-paste image-generation prompt.

[简体中文 README →](./README.md) · [Example prompt →](./examples/perovskite-visual-note-prompt.md) · [Contributing →](./CONTRIBUTING.md)

![Example: perovskite "tunable threshold" visual note, 9:16 portrait](./assets/perovskite-example.png)

---

## 1. The problem

Ask an AI to "illustrate this text" and you usually get a pretty image full of nothing: random elements, garbled text, little connection to the source.

This Skill turns text → illustration into a **controlled pipeline**: pick the canvas ratio first, decompose the argument structure second, **you personally choose the core subject** from 20 candidates third, and only then generate the prompt and the image. You sign off on the subject, so the output is the picture you actually wanted.

## 2. Five-step workflow

| Step | What happens | Output |
|---|---|---|
| ① Ratio | Choose 16:9 / 4:3 / 3:4 / 9:16 | Layout + pixel spec |
| ② Decompose | Central idea → title; sub-arguments → zones; concepts → bilingual labels | Structure breakdown table |
| ③ Subject | 20 subjects sampled across categories from a **200-item pool**, listed by number | One core subject |
| ④ Prompt | Fill the template → full version + 120-word compact version | Ready-to-use prompt |
| ⑤ Render | Generate the image; iterate on individual elements | Finished illustration |

## 3. Canvas specs

| Ratio | Pixels | Best for |
|---|---|---|
| 16:9 landscape | 1920×1080 | Blog headers, deck covers, widescreen |
| 4:3 landscape | 1184×888 | Classic lecture layout, embedded docs |
| 3:4 portrait | 896×1152 | Paper figures, notebook pages |
| 9:16 portrait | 1080×1920 | Mobile long-form, social posters |

## 4. Visual specification (v1.1.0 — Bright & Focused)

> v1.1.0 recalibrates the whole style toward the author's own renders: **vivid colors, one big hero subject, restrained information**. The old "grayscale-dominant, <12% color" spec is retired.

- **Color is the star**: 3–5 saturated theme colors (vermilion, orange-yellow, lemon yellow, emerald, sky blue, royal blue) with marker flat fills, gradient bars and bold colored arrows; warm-brown / teal washes on metal, wood and glass — **color coverage 30–40%**
- **Subject**: the core subject fills **55–65%** of the canvas, richly detailed, the single focal point
- **Restraint**: bilingual labels **≤ 4**, formulas **≤ 3**, handwritten notes **≤ 4**, surrounding sketches **≤ 3**; whitespace **≥ 30%** — readable in three seconds
- **Title**: plaque-style bilingual title bar (gold-trimmed or dark banner)
- **Canvas**: off-white/white + very faint graph paper, generous margins, no dark ground
- **Line work**: crisp HB/2B graphite, hatched shadows that stay bright; drafting annotations only where they matter
- **Academic texture**: at most 2 sticky notes, margin numbering — fewer details beat more
- **Hidden pattern**: Chinese clouds/fret, Greek vase, Arabic geometric, mandala, Andean textile, Persian miniature — pale gold, corners only
- **Text discipline**: printed bilingual labels only — no words unrelated to the source text

## 5. The 200-item subject pool (20 categories × 10, 20 sampled across categories each run)

> Never repeat a subject for the same source text. To add entries, see [CONTRIBUTING](./CONTRIBUTING.md).

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

## 6. Install

```bash
# WorkBuddy (user level)
git clone https://github.com/one5ds/visual-notes-illustrator.git \
  ~/.workbuddy/skills/visual-notes-illustrator

# Claude Code (user level)
git clone https://github.com/one5ds/visual-notes-illustrator.git \
  ~/.claude/skills/visual-notes-illustrator
```

You can also just drop `SKILL.md` into your skills directory — the YAML frontmatter `name` / `description` drives auto-triggering. English users: rename `SKILL_EN.md` to `SKILL.md` first (the English copy ships without frontmatter so it won't double-register alongside the Chinese one).

## 7. Usage

```
Use the visual-notes-illustrator skill to turn this into a 9:16 portrait illustration:
<paste your text>
```

The Skill asks for the ratio, decomposes the structure, gives you 20 numbered subjects, you reply with a number, and it produces the prompt and the image.

## 8. Repository layout

```
visual-notes-illustrator/
├── SKILL.md                 # Skill definition (Chinese, with frontmatter — ready to use)
├── SKILL_EN.md              # English reference copy (no frontmatter; rename to SKILL.md to use)
├── README.md                # Chinese README
├── README_EN.md             # This file
├── LICENSE                  # MIT
├── CONTRIBUTING.md          # Contributing guide (subject-pool entries)
├── .gitignore
├── assets/
│   ├── perovskite-example.png    # Case A render (hourglass engine)
│   ├── perovskite-example-b.png  # Case B render (stepped pyramid)
│   └── gallery/
│       ├── vc-landscape-2026.png       # 2026 VC landscape reshuffle
│       ├── compass-imperfect-path.jpg  # Trace a perfect path in imperfection
│       ├── evolution-journey.jpg       # Evolution journey
│       ├── pen-wisdom-labels.jpg       # Pen & prayer beads — annotated concept
│       └── pen-wisdom-blueprint.jpg    # Pen & prayer beads — drafting sheet
└── examples/
    ├── perovskite-visual-note-prompt.md    # Case A prompt (hourglass engine)
    └── perovskite-visual-note-prompt-b.md # Case B prompt (stepped pyramid)
```

## 9. Gallery

One visual spec, different source texts → different core subjects, different hidden motifs. Each subject was chosen through the "pick 1 of 20" step.

<table>
  <tr>
    <td align="center" width="50%">
      <img src="./assets/perovskite-example.png" alt="Perovskite tunable threshold"><br>
      <sub><b>Perovskite: the material with a tunable threshold</b><br>Subject: hourglass engine · Motif: Chinese fret · 9:16</sub>
    </td>
    <td align="center" width="50%">
      <img src="./assets/gallery/vc-landscape-2026.png" alt="2026 VC landscape reshuffle"><br>
      <sub><b>2026 China VC reshuffle: state capital leads, hard tech rises, M&amp;A rules exits</b><br>Subject: horseshoe magnet (magnetic field = capital gravity) · Motif: fret + auspicious clouds · 16:9</sub>
    </td>
  </tr>
  <tr>
    <td align="center" width="50%">
      <img src="./assets/gallery/compass-imperfect-path.jpg" alt="Trace a perfect path in imperfection"><br>
      <sub><b>Trace a Perfect Path in Imperfection</b><br>Subject: drafting compass · Motif: mandala · landscape</sub>
    </td>
    <td align="center" width="50%">
      <img src="./assets/gallery/evolution-journey.jpg" alt="Evolution journey"><br>
      <sub><b>EVOLUTION JOURNEY</b><br>Subject: dinosaur skeleton cutaway · Motif: Greek vase ornament · landscape</sub>
    </td>
  </tr>
  <tr>
    <td align="center" width="50%">
      <img src="./assets/gallery/pen-wisdom-labels.jpg" alt="Wisdom of enlightenment, annotated"><br>
      <sub><b>Wisdom of Enlightenment, Mortal in the Market (annotated concept)</b><br>Subject: fountain pen wrapped in prayer beads · Motif: mandala · 16:9</sub>
    </td>
    <td align="center" width="50%">
      <img src="./assets/gallery/pen-wisdom-blueprint.jpg" alt="Wisdom of enlightenment, drafting sheet"><br>
      <sub><b>Wisdom of Enlightenment, Mortal in the Market (drafting sheet)</b><br>Subject: fountain pen with multi-view sketches and dimension callouts · 16:9</sub>
    </td>
  </tr>
</table>

> The same source text supports multiple iterations: the last row shows two render directions — an annotated concept sheet and a drafting sheet — for one theme.

### Same text, different subject = different picture (Case A / B)

Identical source text, title and information zones — only the core subject and hidden motif change:

<table>
  <tr>
    <td align="center" width="50%">
      <img src="./assets/perovskite-example.png" alt="Case A hourglass engine"><br>
      <sub><b>Case A · Hourglass Engine</b><br>Metaphor: photons filtered through an adjustable valve · Motif: Chinese fret</sub>
    </td>
    <td align="center" width="50%">
      <img src="./assets/perovskite-example-b.png" alt="Case B stepped pyramid"><br>
      <sub><b>Case B · Stepped Pyramid</b><br>Metaphor: step height raised and lowered · Motif: Arabic geometric</sub>
    </td>
  </tr>
</table>

Full prompts: [Case A](./examples/perovskite-visual-note-prompt.md) · [Case B](./examples/perovskite-visual-note-prompt-b.md)

## 10. License

MIT © AIOpenVC
