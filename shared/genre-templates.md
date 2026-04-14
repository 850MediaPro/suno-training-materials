# Genre Templates

Reusable, model-agnostic prompt templates for common genres. Each template includes:
- **Structure** — typical song arrangement
- **Knobs** — tempo, mood, and instrumentation variables
- **Example prompt** — paste-ready, works with any AI music model

For model-specific syntax (bracket tags for Suno, timestamp blocks for Lyria 3 Pro), see the model-specific files in `models/`.

---

## Americana / Folk / Roots

### Structure
`Intro (acoustic fingerpicking) → Verse 1 → Verse 2 → Chorus → Bridge (sparse, emotional peak) → Final Chorus → Outro (fade)`

### Knobs
| Variable | Range |
|---|---|
| Tempo | 70–100 BPM |
| Mood | Melancholic, hopeful, wistful, nostalgic, reverent |
| Instrumentation | Acoustic guitar, harmonica, brushed drums, upright bass, banjo, fiddle, dobro, mandolin |

### Artist Reference Tags
| Artist Style | Tags |
|---|---|
| Zach Bryan | `Americana Folk, Raw Acoustic Sound, Storytelling Lyrics, Minimalist Production` |
| Tyler Childers | `Americana Folk, Raw Acoustic Sound, Appalachian Influence, Emotional Lyrics` |
| Gillian Welch | `Folk Americana, Minimalist Acoustic Sound, Vintage Feel, Storytelling Mastery` |
| Willie Nelson | `Outlaw Country, Laid-Back Feel, Emotional Storytelling, Classic Americana` |
| Jason Isbell | `Americana, Emotional Storytelling, Clean Instrumentals, Soulful Feel` |
| John Prine | `Folk Americana, Witty Lyrics, Acoustic Storytelling, Simple Production` |

### Standard Example Prompt
```
Americana, warm, 95 BPM, acoustic fingerpicked guitar, harmonica, brushed drums, 
upright bass, storytelling male vocal, emotionally direct delivery, intimate room, 
warm tape saturation, subtle vinyl crackle, mono-leaning mix, one-take performance feel,
no modern pop polish, no electric instruments
```

### Old-Time / Appalachian Variant
```
Traditional Appalachian folk, clawhammer banjo, old-time fiddle, simple acoustic guitar,
natural unprocessed vocals, 80 BPM waltz feel, mountain music atmosphere,
single-mic capture, natural room, no drums, no overdubs, timeless feel
```

### Full Production Example (mixing-language grade)
```
Americana folk-country, warm, 88 BPM, fingerpicked acoustic guitar, harmonica fills,
brushed snare, warm upright bass, storytelling male vocal with slight rasp and emotional
directness, intimate close-mic room, dusty vinyl texture, light wow and flutter,
mono-leaning mix, one-take performance, fret squeak on transitions,
no auto-tune, no electric guitar, no modern drum production
```

---

## Country-Soul

### Structure
`Intro (guitar/organ) → Verse 1 → Pre-Chorus → Chorus (full band) → Verse 2 → Chorus → Bridge (breakdown, peak emotion) → Final Chorus (biggest) → Outro`

### Knobs
| Variable | Range |
|---|---|
| Tempo | 75–95 BPM |
| Mood | Soulful, gritty, emotionally raw, longing, triumphant |
| Instrumentation | Acoustic + electric guitar blend, organ, lap steel, warm bass, live drums with brushed snare |

### Artist Reference Tags
| Artist Style | Tags |
|---|---|
| Chris Stapleton | `Bluesy Country Rock, Soulful Vocals, Organic Sound, Live Feel` |
| Brandi Carlile | `Americana Folk, Powerful Storytelling, Emotional Depth, Acoustic Energy` |
| Kane Brown (modern) | `Country R&B Fusion, Smooth Vocals, Pop Production, Modern Energy` |

### Example Prompt
```
Bluesy country soul, warm tube amp overdrive, acoustic and electric guitar blend,
organ swells, live drumkit with brushed snare, lap steel guitar fills,
soulful male raspy vocals, one-take feel, intimate studio, slight tape warmth,
85 BPM, natural dynamics, full dynamic range, no digital compression artifacts,
no modern country pop production
```

---

## Rock

### Classic 80s Rock Ballad
**Structure:** `Intro (guitar) → Verse (restrained) → Chorus (full band) → Verse → Chorus → Guitar Solo → Final Chorus (climax) → Outro (fade with guitar sustain)`

```
Classic Hard Rock Ballad, Overdriven Guitars with Warm Tube Amp Tone, Electric Bass,
Acoustic Drum Kit, Snare Reverb Long Tail, 80 BPM, Male Rock Vocal Powerful yet Emotional,
Melismatic Delivery, Harmonized Backing Vocals in Chorus, Guitar Solo with Delay,
Stadium Reverb, 80s Power Ballad Energy, Emotional Storytelling, Full Dynamic Range,
Guitar and Vocal Crescendo at Final Chorus, Analog Mastered Mix for Streaming
```

### Power Ballad / Anthemic Rock
**Structure:** `Quiet verse → building pre-chorus → explosive chorus → repeat with layers → stadium climax`

```
Anthemic Rock Power Ballad, 92 BPM, 4/4 Time, Distorted Rhythm Guitars, Lead Guitar
with Crying Sustain, Driving Bass, Punchy Drum Kit, Strong Snare and Cymbal Crashes,
Male Rock Vocal with Emotional Power, Layered Backing Vocals, Background Choir Texture,
Stadium Reverb, Modern Rock Mastering, Melodic Hook Emphasis, Powerful Build to Climax,
Guitar Feedback Outro, Hopeful yet Nostalgic Feel, Final Chorus Repeated with Full Energy
```

### Blues Rock (Intimate)
**Structure:** `Sparse verse (guitar only) → verse with rhythm section → solo break → final verse → fade`

```
Soft Blues Rock Ballad, Electric Guitar Clean Tone, Gentle Bass Guitar, Light Acoustic Drums,
Subtle Ride Cymbal, Warm Reverb Vocals, Male Rock Vocal Smooth Melismatic Delivery,
Deep Dynamic Range, Intimate Studio Ambience, Slow Tempo 62 BPM, Emotional Harmonic
Progression, Expressive Guitar Fills, Cinematic Room Reverb, Touch of Analog Tape Warmth,
Romantic Despair and Acceptance Theme, Ending Fade with Guitar Sustain
```

### Alternative Rock
**Structure:** `Quiet verse → loud chorus (wall of sound) → quiet verse → loud chorus → breakdown → climax`

**Knobs:**
| Variable | Range |
|---|---|
| Tempo | 120–145 BPM |
| Mood | Angsty, introspective, cathartic, raw |
| Instrumentation | Distorted guitar, bass, drums, layered vocals |

```
Alternative rock, loud-quiet dynamic, 130 BPM, distorted power chords, clean verse guitars,
heavy chorus wall of sound, driving bass, crashing cymbals on downbeats,
emotionally pushed male vocals with slight grit, layered harmonies on chorus,
modern analog-digital hybrid production, wide stereo chorus, tight dry verse,
no overpolished radio sheen
```

---

## Trap / Hip-Hop

### Structure
`Intro (hook teaser) → Hook → Verse 1 → Hook → Verse 2 → Hook → Bridge/switch → Hook → Outro`

### Knobs
| Variable | Range |
|---|---|
| Tempo | 130–150 BPM (with half-time feel) |
| Mood | Dark, cinematic, aggressive, melodic, atmospheric |
| Instrumentation | 808 sub-bass, hard kick, hi-hat rolls, dark minor melody loop, sparse pads/keys |

### Example Prompts (by variant)

**Modern Trap:**
```
Modern trap, punchy drums, heavy 808, hard bars, anthem hook, clean mix,
late-2020s Atlanta production, 140 BPM, dark cinematic atmosphere
```

**Dark Trap:**
```
Dark trap, trap drums, heavy 808, aggressive delivery, chant hook, gritty,
minor key loop, eerie keys, sparse arrangement
```

**Melodic Trap:**
```
Melodic trap, airy keys, heavy 808, melodic rap delivery, hook repeat, clean mix,
emotional atmosphere, soft pads behind vocal
```

**Trap Soul:**
```
Trap soul, smooth chords, trap drums, sub bass, emotional hook, clean mix,
R&B vocal influence, vulnerable delivery, late-night feel
```

### Full Production Example (mixing-language grade)
```
High-fidelity 44.1kHz stereo mix, crystal-clear dynamics, precise instrument separation,
heavy rumbling 808 sub-bass dominating the low end, crisp hi-hats and sharp snares with
bright but controlled treble, late-2020s Atlanta trap production, 140 BPM head-nod groove,
dark cinematic atmosphere, dry urban studio reverb, wide stereo dispersion with
thoughtful panning, centered lead vocals, intentional rhythmic delivery,
no algorithmic clipping or hiss, no narrow mono imaging, no lo-fi mud,
avoid generic pop polish
```

---

## Orchestral / Cinematic / Classical

### Structure
Varies by sub-genre. For cinematic: `Theme statement → Development → Rising tension → Climax → Resolution`

### Knobs
| Variable | Range |
|---|---|
| Tempo | 40–160 BPM (highly variable by form) |
| Mood | Triumphant, melancholic, tense, ethereal, heroic, intimate |
| Instrumentation | Full symphony, string quartet, solo piano, chamber ensemble, brass section, choir |

### Example Prompts by Sub-Genre

```
Orchestral, cinematic, full symphony, triumphant crescendo, film score style         [Hans Zimmer]
Baroque, harpsichord, string ensemble, ornate, 1700s, contrapuntal                   [Bach influence]
Romantic piano, solo instrument, emotional, rubato, Chopin-inspired                  [19th-century piano]
String quartet, intimate, chamber music, emotional dialogue, classical form           [Beethoven quartets]
Minimalist classical, repetitive patterns, slowly evolving, meditative, modern        [Philip Glass]
Orchestral trailer, epic percussion, brass fanfare, building intensity, heroic         [Two Steps from Hell]
Neoclassical, piano and strings, contemporary, emotional, cinematic ambient           [Nils Frahm]
Opera aria, soprano vocals, dramatic, Italian style, passionate                       [Puccini]
Impressionist, dreamy, piano with orchestral color, subtle, Debussy-like              [French impressionism]
Choral, mixed voices, sacred atmosphere, reverberant, soaring harmonies              [Cathedral sound]
```

### Full Production Example
```
Neoclassical orchestral, intimate and emotionally expansive, 72 BPM, string quartet
with solo piano, cello carrying main melody, violin harmonies, piano providing
sparse rhythmic accents, wide dynamic range from pianissimo to fortissimo,
hall reverb with natural decay, no drums, no synthetic sounds, warm and organic,
cinematic but not bombastic
```

---

## Pop / Synth-Pop

### Structure
`Intro (hook or drop element) → Verse (low energy) → Pre-Chorus (build) → Chorus (full energy) → Post-Chorus → Verse 2 → Chorus → Bridge → Final Chorus (peak)`

### Knobs
| Variable | Range |
|---|---|
| Tempo | 100–130 BPM |
| Mood | Euphoric, bittersweet, confident, playful, wistful |
| Instrumentation | Synth pads, four-on-the-floor kick, polished bass, melodic lead synth, layered backing vocals |

### Contemporary Pop Example
```
Mainstream pop, contemporary production, 118 BPM, upbeat catchy feel, polished synth pads,
electronic drums with punchy kick, melodic bass line, hooky lead synth, female soprano
with flirty delivery, layered harmonies on chorus, wide stereo imaging, modern radio mastering,
bright clear highs, controlled low end
```

### 80s Synth-Pop Example
```
80s synth-pop, vintage synthesizers, arpeggio sequences, four-on-the-floor drum machine,
gated reverb snare, warm analog bass, 124 BPM, anthemic feel, male or female vocal
with slight reverb, new wave energy, chorus-effected guitar optional, neon-bright production
```

### Dark Pop / Alt-Pop Example
```
Dark pop, minor key, atmospheric synth layers, 110 BPM, understated verse, dramatic chorus,
female vocal with emotional restraint building to belting, reverb-heavy mix, moody,
controlled dynamics, contemporary production with cinematic undertones
```

---

## R&B / Neo-Soul

### Structure
`Intro (groove) → Verse 1 (intimate) → Pre-Chorus → Chorus (soulful peak) → Verse 2 → Chorus → Bridge (ad-lib/melisma showcase) → Final Chorus → Outro (vamp)`

### Knobs
| Variable | Range |
|---|---|
| Tempo | 70–95 BPM |
| Mood | Sensual, introspective, empowered, longing, late-night intimate |
| Instrumentation | Rhodes/keys, warm bass, crisp hi-hats, live or programmed drums, guitar stabs, strings optional |

### Neo-Soul Example
```
Neo-soul, warm Rhodes piano, smooth jazz-influenced chords, live drums with crisp hi-hats,
warm bass groove, 80 BPM, soulful female vocal with light melisma, breathy and intimate
on verses, powerful on chorus, late-night atmosphere, subtle reverb,
close-mic warmth, no overproduction, organic feel
```

### Contemporary R&B Example
```
Contemporary R&B, 88 BPM, 2010s R&B warmth, warm electric piano, smooth bass,
programmed drum groove with live elements, female vocal smooth and soulful,
airy on quiet lines, powerful natural belting on peaks, crystal-clear pronunciation,
contemporary R&B inflection, emotional vibrato, subtle backing harmonies,
wide stereo, polished but not overcompressed
```

### Classic Soul / Motown-Influenced
```
Classic soul, Motown-influenced, 95 BPM, upright bass, live drums, brass section stabs,
piano, soulful female lead vocal with full vibrato, male backing vocal group,
call and response between lead and backing, vintage studio reverb, mono or narrow stereo,
1960s–70s soul production feel, analog warmth
```

---

## Quick Reference: Genre → Mix Language Pairings

| Genre | Key Mix Language |
|---|---|
| Americana / Folk | `warm tape saturation, dusty vinyl crackle, mono-leaning, intimate room, one-take performance` |
| Country-Soul | `warm tube amp tone, tape warmth, live feel, natural dynamics, no digital artifacts` |
| Classic Rock | `stadium reverb, warm tube amp, snare reverb long tail, analog compression, wide stereo` |
| Trap / Hip-Hop | `heavy 808 sub, crisp hi-hats, dry urban studio reverb, wide stereo, no narrow mono` |
| Orchestral | `wide dynamic range, hall reverb, instrument separation, no synthetic sounds` |
| Pop / Synth-Pop | `wide stereo imaging, modern mastering, bright clear highs, tight low end, polished` |
| R&B / Neo-Soul | `close-mic warmth, subtle reverb, 2010s warmth, organic, no overcompression` |
