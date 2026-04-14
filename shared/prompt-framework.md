# Universal Prompt Framework for AI Music Generation

Model-agnostic. Applies to Suno, Gemini/Lyria, and any future text-to-music model. Model-specific syntax is tagged with `<!-- model:suno -->` or `<!-- model:gemini -->`.

---

## The Universal Prompt Structure

Every music prompt is composed of six layers, applied in this order:

```
[role] + [genre/style] + [arrangement/instrumentation] + [performance/feel] + [mix/space] + [technical constraints]
```

| Layer | What It Controls | Example |
|---|---|---|
| **role** | The "voice" of the prompt — who is describing this music | "Mix engineer brief:", "Producing a track for..." |
| **genre/style** | Musical category, era, and stylistic language | "Late-2020s Atlanta trap", "1970s Americana folk" |
| **arrangement/instrumentation** | Named instruments, ensemble size, how they interact | "Fingerpicked acoustic guitar, brushed drums, harmonica" |
| **performance/feel** | Tempo, groove, energy arc, emotional delivery | "85 BPM, laid-back head-nod groove, emotionally raw vocals" |
| **mix/space** | Stereo field, reverb, room character, spatial placement | "Intimate close-mic room, mono-leaning, dusty vinyl crackle" |
| **technical constraints** | Exclusions, format limits, fidelity floor, distribution targets | "No auto-tune warble, 44.1kHz stereo, no brickwall compression" |

**Minimum viable prompt:** genre/style + arrangement/instrumentation + performance/feel.  
**Production-grade prompt:** all six layers.

---

## How to Decompose a Song Idea into These Layers

Start with your idea in plain language, then translate each element into the correct layer.

**Example idea:** "A sad country song about leaving home, recorded like it was caught on tape in the 70s."

| Idea fragment | Layer | Translated |
|---|---|---|
| "sad country" | genre/style | `Americana country, minor key, melancholic` |
| "leaving home" | performance/feel | `storytelling delivery, slow 70 BPM, emotional male vocal` |
| "caught on tape in the 70s" | mix/space | `warm tape saturation, light wow and flutter, mono-leaning, dusty vinyl crackle` |
| "recorded" (implies organic) | arrangement | `acoustic guitar, brushed snare, upright bass, sparse` |
| Implied quality floor | technical constraints | `no modern pop compression, no digital gloss` |

**Resulting prompt:**
```
Americana country, melancholic, 70 BPM, acoustic fingerpicked guitar, upright bass, 
brushed snare, storytelling male vocal, emotionally raw delivery, warm tape saturation, 
light wow and flutter, mono-leaning intimate room, dusty vinyl crackle, 
no modern pop compression, no digital gloss
```

---

## The "Describe Sound, Not Genre" Rule

> **Never rely on a genre label alone. Describe the sounds that define that genre.**

Genre labels are shorthand — models blend genre embeddings loosely. Describing the actual sounds forces more precise output.

| Instead of | Write |
|---|---|
| "Trap music" | "Heavy rumbling 808 sub-bass, punchy modern kick, fast hi-hat rolls, dark minor loop, late-2020s Atlanta production" |
| "Classical music" | "String quartet, intimate chamber arrangement, slow rubato, emotional dialogue between violin and cello" |
| "Folk" | "Fingerpicked acoustic guitar, simple brushed percussion, storytelling vocal, natural room, no overdubs" |
| "Pop" | "Polished synth pads, four-on-the-floor kick, hooky melody, wide stereo, contemporary radio mastering" |
| "R&B" | "Warm Rhodes piano, sub-bass groove, soulful female vocal with light melisma, crisp hi-hats, late-night intimacy" |

Add genre labels **after** the description as a clarifying anchor, not as the primary signal.

---

## The Post-Production Engineer Mindset

**Think of the style/prompt field as a brief to a mixing/mastering engineer — not a song request to a musician.**

A mix engineer doesn't decide what notes to play. They shape:
- Fidelity and clarity
- Instrument separation
- Low-end and high-end balance
- Spatial placement (stereo field, reverb, room)
- Energy and dynamics
- Era/production reference
- What gets cut (negatives)

Your prompt does the same. The model generates the composition; your prompt shapes how it sounds.

**Style box = mix engineer brief.** Write it like one.

<!-- model:suno -->
> **model:suno** — The style box and lyrics box are separate fields. The mix engineer brief goes in the **style box only**. Never put mix-language in the lyrics box. See `models/suno/advanced-prompting.md` for the Two-Box Rule.

<!-- model:gemini -->
> **model:gemini** — Lyria accepts the full brief as a single prompt. Mix language, genre anchors, and vocal direction are all written together. See `models/gemini-lyria/prompting.md`.

---

## Core Formula for the Style/Mix Brief

```
[Fidelity] + [Separation & Clarity] + [Low-end] + [High-end] + 
[Era / Production Style] + [Energy & Dynamics] + [BPM & Groove] + 
[Spatial / Room] + [Vocal Direction] + [Exclusions]
```

**Full working template:**
```
High-fidelity 44.1kHz stereo mix, crystal-clear dynamics, precise instrument separation,
[low-end description], [high-end description], [era/style]-era [genre] production,
[energy/dynamics description], [BPM] BPM [groove feel], [mood adjectives],
[room + spatial description], focused intentional performance,
no artifacts/hiss/clipping, avoid [specific negatives].
```

---

## Mixing-Language Vocabulary

Use this vocabulary in the **mix/space** and **technical constraints** layers of any prompt.

### Fidelity / Clarity
- `high-fidelity 44.1kHz stereo mix`
- `studio-grade clarity`
- `clean signal`
- `crystal-clear dynamics`
- `precise instrument separation`
- `layered elements that breathe`

### Low End
- `heavy rumbling 808 sub-bass`
- `sub-bass rumble`
- `warm bass`
- `tight low end`
- `focused sub`
- `deep 808s`

### High End
- `crisp hi-hats and sharp snares`
- `bright but controlled treble`
- `shimmering airy highs`
- `clear highs`
- `restrained highs` ← for vintage/analog vibe

### Stereo / Spatial
- `wide stereo dispersion`
- `thoughtful panning`
- `clear left-right imaging`
- `immersive panning`
- `wide immersive field`
- `limited stereo / mono-leaning mix` ← vintage/mono
- `narrow stereo` ← mono-adjacent
- `outdoor festival openness`
- `sweaty club tightness`
- `dry urban studio reverb`
- `expansive hall reverb`

### Analog Warmth & Saturation
- `warm tape saturation`
- `analog warmth / harmonic grit`
- `tape warmth`
- `preamp edge distortion`
- `light wow and flutter` ← tape pitch variation
- `very subtle wow and flutter`
- `vinyl crackle`
- `subtle vinyl texture`
- `dusty vinyl crackle`
- `tape hiss`
- `vinyl noise bed`
- `noise floor` ← faint analog background

### Room / Acoustic Environment
- `small room acoustics`
- `intimate room`
- `close mic presence`
- `off-axis mic placement`
- `proximity effect extra low up close`
- `single-mic capture`
- `ribbon mic tone`
- `natural room`
- `live room feel`

### Performance Realism
- `one-take performance`
- `timing drift / human micro-rubato`
- `natural dynamics (no brickwall feel)`
- `pick noise (attack, scrape)`
- `fret squeak (string slides)`
- `finger movement noise on strings`
- `chair creak / body shift`
- `light mic handling noise (very subtle)`
- `slight rasp`
- `tiny pitch variations`

### Dynamics & Energy
- `full dynamic range`
- `focused mid-tempo`
- `explosive builds`
- `anthemic peaks`
- `intimate drops`
- `slow build`
- `cinematic warmth`

### Era / Production Style References
- `late-2020s [genre] production`
- `1990s boom-bap revival`
- `2010s R&B warmth`
- `current hyperpop sheen`
- `80s power ballad energy`
- `80s–90s rock influence`
- `vintage amp tone`

### Negatives / Exclusions
- `no cheesy auto-tune warble`
- `no algorithmic clipping or hiss`
- `no narrow mono imaging`
- `no lo-fi mud`
- `avoid generic pop polish`
- `no brickwall feel`
- `no robotic artifacts`
- `no overcompressed squash`
- `no musical theater drama`
- `no boxy center pile-up`

---

## When to Use Each Layer

| Situation | Focus layers |
|---|---|
| Getting genre character right | genre/style + arrangement/instrumentation |
| Fixing vocal feel or performance | performance/feel |
| Sounding "too digital" or "too polished" | mix/space (add analog warmth vocabulary) |
| Avoiding specific AI artifacts | technical constraints (negatives) |
| Era-specific sound | genre/style + mix/space (era references) |
| Energy arc (quiet → loud → quiet) | performance/feel (describe the arc explicitly) |
| Realism for acoustic instruments | mix/space (performance realism vocabulary) |

---

## Layer Interaction Rules

1. **Genre/style anchors the model** — always lead with this.
2. **Instrumentation overrides genre defaults** — if you don't name instruments, the model auto-selects for the genre.
3. **Performance/feel shapes delivery** — tempo and groove interact with genre; mismatch intentionally for effect (e.g., trap beat at 70 BPM for a slowed-down sound).
4. **Mix/space is additive** — adding analog texture does not cancel clarity; combine them.
5. **Negatives must use "no" / "avoid"** — listing an element without negation may cause the model to include it.
6. **Too many layers at once causes prompt blur** — in a single generation, prioritize genre + arrangement + 2–3 mix descriptors. Add the rest in iteration.

---

## Prompt Length Guidelines

| Context | Target length |
|---|---|
| Simple clip / social post | 15–30 words |
| Standard song (any model) | 60–150 words |
| Production-grade brief (Suno) | 100–200 words in style box |
| Timestamp-structured (Lyria 3 Pro) | 200–400 words total |
| Loop-based / electronic genres | Under 100 words (more is not better here) |

---

## Model-Specific Notes

<!-- model:suno -->
> **model:suno** — Use the GMIV Framework, 5-Signal Framework, or 4-Part Template as structured alternatives to the universal framework. Place mix-language in the Style box. Use bracket tags in the Lyrics box for section control. See `models/suno/advanced-prompting.md`.

<!-- model:gemini -->
> **model:gemini** — Use the `[Genre + Era] + [Mood] + [Instrumentation] + [Tempo] + [Vocal style] + [Lyrics]` format. Add timestamp blocks for Lyria 3 Pro. The "Anchor Formula" (genre+era → mood → instrumentation+dynamics) maps to layers 2–4 of this framework. See `models/gemini-lyria/prompting.md`.
