# Suno Advanced Prompting

> **model:suno** — All techniques in this file are Suno-specific unless noted.

---

## The Two-Box Rule

Suno's Custom mode has two separate input fields. They have different roles and must not be confused.

| Field | Role | What goes here |
|---|---|---|
| **Style box** (top) | Global sonic "world" — genre, production era, instruments, mix character | Mix engineer brief; GMIV tags; genre/style/instrumentation/mix language |
| **Lyrics box** (below) | Section behavior and delivery | Bracket structural tags + actual lyric lines |

**Rule:** Never put section structure tags in the Style box. Never put mix language in the Lyrics box. The style box is global; the lyrics box is sectional.

**Bleed warning:** If the style box contains lyric-like formatting (line breaks, quoted phrases, bracketed section markers), Suno may begin singing the style box as if it were lyrics. Keep the style box as compact noun-phrase metadata.

---

## Framework Approaches

### GMIV Framework
Source: [ChillPanic GMIV tutorial](https://www.youtube.com/watch?v=ck6IwiJkEP8)

**G** — Genre (1–2 main + specific subgenres)  
**M** — Mood (emotional vibe: "Dark," "Euphoric," "Melancholic")  
**I** — Instruments (3–4 key instruments for that genre)  
**V** — Vocals (gender, personality, register, delivery)

**Example (Mainstream Pop):**
```
Mainstream Pop, Contemporary Pop | Upbeat, Catchy | Synths, Electronic Drums | Female Soprano, Flirty Delivery
```

### 5-Signal Framework
Source: [Jack Righteous Prompt Guide](https://jackrighteous.com/blogs/guides-using-suno-ai-music-creation/bookmark-this-suno-ai-a-z-prompts-guide-a-to-c)

1. Genre — sets rhythmic and structural language
2. Mood/Energy — shapes delivery tone
3. BPM — controls pacing and groove intensity
4. Instrumentation — defines tonal palette
5. Optional structural intent — influences arrangement emphasis

### 4-Part Template (Reddit consensus)
```
Genre: "<specific subgenres>"
Exclude: "<elements to avoid>"
Instruments: "<key instruments + vocal treatment>"
Tags: "<BPM; mood; drop type; extras>"
```

### Post-Production Engineer Formula
Source: [Reddit Byerley904 v5 guide](https://www.facebook.com/groups/1118818620292019/posts/1326242769549602/)

```
[Fidelity] + [Separation & Clarity] + [Low-end] + [High-end] + 
[Era / Production Style] + [Energy & Dynamics] + [BPM & Groove] + 
[Spatial / Room] + [Vocal Direction] + [Exclusions]
```

**Full working example (trap):**
```
High-fidelity 44.1kHz stereo mix, crystal-clear dynamics, precise instrument separation,
heavy rumbling 808 sub-bass dominating the lows, crisp hi-hats and sharp snares with
bright but controlled treble, late-2020s Atlanta trap production, mid-tempo focused
energy with gradual builds, 140 BPM head-nod groove, dark cinematic atmosphere,
dry urban studio reverb, wide stereo dispersion with thoughtful panning, centered lead
vocals, intentional rhythmic delivery, no cheesy auto-tune warble, no algorithmic
clipping or hiss, no narrow mono imaging, no lo-fi mud, avoid generic pop polish.
```

See `shared/prompt-framework.md` for the full mixing-language vocabulary.

---

## Structural Tags Reference

Place each tag on **its own line** in the Lyrics box. Do NOT inline tags with lyric text.

### Standard Section Tags
```
[Intro]
[Verse 1]
[Verse 2]
[Pre-Chorus]
[Build-up]
[Chorus]
[Bridge]
[Outro]
[Transition]
[Instrumental]
[Instrumental Break]
[Final Chorus]
[Hook]
[Drop]
[Solo]
```

### Global Parameter Tags
Can go in the Lyrics box header or Style box:
```
[Title: Song Name Here]
[Genre: Electronic, Hip-Hop, Drill]
[Tempo: 140 BPM]
[Style: Aggressive, Futuristic, Gritty]
```

### Structure Tags for Energy Control
```
[Structure: Focused Performance]   — tight, medium energy, clean
[Structure: Build-up]              — rising tension, layering in
[Structure: Anthemic Peak]         — big hook, max energy
[Structure: Minimalist Breakdown]  — stripped back, emotional
[Structure: Rhythmic Bridge]       — groove switch
[Structure: Emotional Arc]         — full arc behavior
[Structure: Generative Drop]       — AI-directed drop
```

---

## Vocal Performance Tags

Place inside section blocks (on their own line, before or after lyric content in that section):

```
[intimate]           [soft]              [breathy]
[close mic]          [rising tension]    [more space]
[big lift]           [open vowels]       [anthem]
[repeat hook]        [light harmonies]   [conversational]
[slightly stronger]  [build faster]      [more urgency]
[dropout]            [confession]        [whisper then grow]
[return full]        [biggest]           [more harmonies]
[adlibs light]       [strip back]        [one last line]
```

---

## Vocal Anchor Block

Place at the **very top of the Lyrics box** to anchor the entire song's vocal character. Examples:

```
[Vocal: male, deep husky timbre, relaxed but intense delivery, clear diction, precise rhythm, minimal vibrato, modern rap-adjacent tone, subtle breath on soft lines]
```

```
[Vocal: female, smooth and soulful, airy on quiet lines, powerful natural belting on peaks, crystal-clear pronunciation, contemporary R&B inflection, emotional vibrato]
```

```
[Vocal: male, slightly nasal pop-punk edge, emotionally pushed delivery, high-register grit, subtle roughness, not overly radio-polished]
```

---

## Instructional Modifier Syntax

Three punctuation types control delivery and effects within lyric lines.

### Parentheses `( )` — Adlibs, whispered/spoken cues, vocal emphasis, dynamics
```
(whispered: "Secrets of the code...")
(spoken: "Activate the system now!")
(murmured: "feel the pulse...")
(LOUD: "RISE UP!")
(softly: "let it flow")
(urgent: "now or never!")
(adlibs: "uh-huh, yeah!")
(vocal chop: "oh-oh")
(echoed: "echo... echo...")
(dreamily: "floating through neon skies")
```

### Braces `{ }` — Backup vocals, layered effects, harmonies, sound effects
```
{backup vocals: "Break the code!"}
{adlibs: "Yeah, yeah, yeah!"}
{harmony: "la-la, la-la"}
{layered vocals: "we are unstoppable"}
{counter-melody: "rise, rise, rise"}
{background vocal: "ooh, ooh, ooh"}
{sound effect: "static interference"}
{effect: "robotic modulation"}
{add reverb: "medium"}
{auto-tune: "subtle"}
{delay: "200ms echo"}
{ambient vocal: "whispering winds"}
```

### Asterisks `* *` — Sound effects, instrumental cues, ambient textures, transitions
```
*laser sweeps and digital beeps*
*heavy bass drop, rapid hi-hat rolls*
*soft vinyl scratch and distant crowd cheer*
*record scratch effect*
*synth arpeggio cascade*
*sudden stop*
*synth swell*
*fading echo*
*robotic voice modulation*
*steady drum fill with soft backing keys*
*soft cymbal crashes and gentle fade-out*
```

---

## Arrangement / Instrumentation Tags

Use in Style box or Lyrics box:

```
[Riff]                        — Generic repeated instrumental phrase
[Guitar Riff]                 — Distorted electric guitar riff
[Bass Riff]                   — Groovy syncopated bass line
[Acoustic Guitar Riff]        — Soft rhythmic picking
[Synth Riff]                  — 80s-style looping electronic melody
[Solo Riff]                   — Extends into short solo
[Call & Response Riff]        — Alternates vocals and instrument
[Layered Riff]                — Multiple instrument lines
[Dynamic Guitar Riff]         — Guitar bends + volume swells
[Complex Progression]         — Intricate chords beyond standard structures
[Dynamic Complex Progression] — Intensity shifts + expressive riffs
[Epic Complex Progression]    — Cinematic, orchestral layering
[Orchestral Swell]            — Large orchestral backdrop swell
[Orchestral Strings]          — String ensemble emphasis
[Cinematic Orchestration]     — Grand dramatic orchestral feel
[Instrumental Break]          — Specified instrumental-only section
```

---

## Punctuation Behavior in Lyrics

| Symbol | Function |
|---|---|
| `,` (comma) | Quick breath / brief pause |
| `...` (ellipsis) | Linger / emotional stretch |
| `—` (em dash) | Hard cut / accent |
| `!` (exclamation) | Energy punch |

**Example:** `I'm running from ghosts — but they're gaining... Heart slamming — like war drums in my chest!`

---

## Exclusion / Negative Prompting

- Use the **Exclude Styles** field (if present in UI) for dedicated exclusions
- Alternatively, add exclusions at the end of the Style box using explicit `no`:
  - `no choir-like ahhs`
  - `no drums`
  - `no auto-tune warble`
  - `no algorithmic clipping or hiss`
  - `no narrow mono imaging`
  - `no lo-fi mud`
  - `avoid generic pop polish`

**Warning:** Listing an element in the style box **without** negation may cause Suno to include it. The model treats any mentioned element as potentially desired.

---

## Avoiding Lyric / Prompt Bleed

**The problem:** The Style box generates lyric-like behaviors (singing style prompts as if they were lyrics).

**Bleed triggers — avoid these in the Style box:**
- Lyric-like formatting with line breaks
- `[Verse]` / `[Chorus]` section structure
- Poetic phrasing or clean sentences in quotes
- Bracketed tags that look like section markers
- An empty Lyrics field (model then "sings" the Style box)

**Safe Style box pattern:** Compact noun phrases, no line breaks, no quotes, no performable-looking syntax.

| Bad (triggers bleed) | Good (safe) |
|---|---|
| `"Verse: A man walks alone at night, thinking of her..."` | `acoustic country singersongwriter, warm fingerpicked guitar, emotional male vocal` |
| `[Chorus] Big anthemic hook` | `anthemic chorus energy, layered backing vocals` |

---

## Phonetic Spelling for Pronunciation

When Suno mispronounces a word, write it phonetically:

- `bureaucracy` → `byoo-ROCK-ruh-see`
- `ephemeral` → `eh-FEM-er-uhl`

Use capital letters to indicate stressed syllables. Write exactly how you want the model to sing it.

---

## Americana / Country-Soul Specifics

Source: [DAILG Music Country Cheat Sheet](https://dailgmusic.com/blogs/suno-ai-tricks-tips/posts/7566216/suno-ai-artist-style-cheat-sheet-country-folk-americana)

### Americana / Folk Core Tags
- `folk`, `acoustic guitar`, `fingerpicked`, `warm vocals`, `storytelling`, `intimate recording`, `authentic`
- For Appalachian/Old-Time: `traditional folk`, `clawhammer banjo`, `old-time`, `mountain music`, `Appalachian`, `natural vocals`
- **Avoid** steel guitar tags and modern country production if targeting traditional folk

### Americana Mixing Language
`warm tape saturation`, `subtle vinyl crackle`, `mono-leaning mix`, `intimate room`, `dusty vinyl texture`, `light wow and flutter`, `warm bass`, `restrained highs`, `ribbon mic tone`, `natural room`, `single-mic capture`, `one-take performance`

### Country-Soul Core Tags
`country soul`, `soulful vocals`, `organic sound`, `live feel`  
`bluesy country rock` — for Chris Stapleton-style output  
`warm tube amp tone`, `lap steel guitar`, `organ`, `warm bass`

**Style box example:**
```
Bluesy country soul, warm tube amp overdrive, acoustic and electric guitar blend,
organ swells, live drumkit with brushed snare, soulful male raspy vocals,
one-take feel, intimate studio, slight tape warmth, 85 BPM, natural dynamics
```

---

## Best Practices

1. **Put each bracket tag on its own line.** Do NOT inline tags with lyric text.
2. **Use 2–4 tags per section maximum.** More causes confusion or gets ignored.
3. **If vocals ignore your brackets:** tags are probably not on separate lines, or you're using too many.
4. **Fix section behavior (Lyrics box) before touching the Style box** — brackets first, style last.
5. **Keep chorus shorter than verse.** Repeat one hook phrase at least twice.
6. **Style box: 4–7 descriptors** is optimal for most genres. Electronic/loop genres: fewer.
7. **Lyrics box handles micro-behavior.** Style box handles macro-character. Never swap roles.
8. **Total Style box length:** 100–200 words for production-grade prompts; under 100 words for electronic/loop genres.
9. **Always include at least a placeholder in the Lyrics box** to prevent style-box bleed.
