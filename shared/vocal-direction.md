# Vocal Direction — Prompting for Human Performance

Model-agnostic framework with model-specific syntax tagged inline. For getting AI vocal performances that sound like a real person singing with genuine emotion.

---

## Why Vocal Direction Matters Most

Vocals are where listeners detect "AI" fastest. The reason is well-documented: a [2025 arXiv listener-perception study](https://arxiv.org/html/2506.02856v1) found that participants associated humanness specifically with "imperfection, flow, and 'soul'" — and that tracks sounding "too perfect, too contrived" were immediately flagged as non-human. The scholarly parallel is [Ayyildiz et al. (2025) in *Scientific Reports*](https://pmc.ncbi.nlm.nih.gov/articles/PMC12373897/), which confirmed that micro-timing deviations — tiny variations in dynamics and articulation that no conscious mind registers — are what make a performance sound "lifelike, organic, and authentic, rather than mechanical."

The community finding is consistent: generic vocal prompts like "emotional female vocals" or "powerful chorus" produce generic results. As documented in the [r/SunoAI Character Prompt Method thread (November 2025)](https://www.reddit.com/r/SunoAI/comments/1ouiswb/advanced_technique_the_character_prompt_method/):

> "We often use it for lyrics, but we forget to apply that storytelling to the performance. Treat the vocalist as a character in a musical narrative rather than just a sound."

The fix in both cases is the same: direct the vocal performance the way a producer directs a session singer. Describe the person, the moment, and the physical sound — not the genre and not the emotional adjective.

---

## The Character Prompt Method

This is the single highest-impact technique from community research. Instead of describing a voice, describe a person in a specific moment.

**The formula:**

```
[Musical Style] featuring a vocalist who is [Character Description].
The singer's performance is [Performance Context & Emotion].
```

**Before (generic):**
```
Emotional female vocals, powerful chorus, melancholic feel.
```

**After (Character Prompt):**
```
The vocalist is a woman in her late 20s, singing from the floor
of a dimly lit room after a long, exhausting day. Her voice is
weathered but controlled, filled with raw resignation. There's
a slight rasp, and she pushes her chest voice on the chorus,
almost breaking but never losing control.
```

Why it works: words like "dimly lit room," "weathered," and "raw resignation" cluster into a coherent aesthetic signal in the model's training data, producing more consistent and nuanced vocal performance than adjectives alone. This is confirmed by the [PLOS One biometric study (Fišer et al., 2025)](https://pmc.ncbi.nlm.nih.gov/articles/PMC12194076/), which found that sophisticated, contextual prompts achieved significantly better emotional congruence than simple dimensional descriptors.

**How to write character descriptions that don't lock to a specific person:**

- Anchor to a specific emotional *situation*, not a recognizable name or catalog of familiar traits
- Use physical-world details: a room, a time of day, a physical action the singer is performing
- Name the emotional stakes: what does this person *want* or *fear* in this moment?
- Describe the body: tired, tense, breathless, grounded, shaking slightly

**The total character inhabitation principle:** Decide who is singing and why before writing any lyrics. From the [research-artist-techniques source](https://jackrighteous.com/blogs/ai-writing/how-to-use-imagery-to-make-your-lyrics-hit-harder), the most compelling vocal performances are those where the singer has fully inhabited a character's inner life — the performance follows from that inhabitation, not from technical instruction.

---

## The Vocal Anchor System

A Vocal Anchor is a tag placed at the very top of the lyrics box — before any section tags or lyric lines — that locks vocal identity for the entire track.

<!-- model:suno -->
**Placement rule:** Place it before everything else. As documented in the [Facebook Suno community guide (March 2026)](https://www.facebook.com/groups/1118818620292019/posts/1326242769549602/): "Suno gives more weight to the initial part of your prompt compared to what follows." The anchor sets vocal DNA in the first one to two seconds of generation.

**Format:**
```
[Vocal: gender/range, timbre descriptors, delivery style, breath behavior, vibrato preference]
```

**Five example anchors (no genre locking — applicable across contexts):**

1. Deep, authoritative presence with warmth:
```
[Vocal: male, deep baritone, warm resonant timbre, unhurried deliberate delivery, audible breath between phrases, minimal vibrato]
```

2. Intimate, breathy vulnerability:
```
[Vocal: female, soft alto, airy breathy tone, close-miked intimacy, slow legato delivery, emotional vibrato on held notes]
```

3. Weathered, effortful rawness:
```
[Vocal: male, mid-tenor with grit, weathered raspy texture, strained at peaks, slightly rough on consonants, no polish]
```

4. Clear, forward, emotionally pushed:
```
[Vocal: female, bright clear soprano, emotionally pushed delivery, high-register grit, precise rhythm, restrained vibrato]
```

5. Conversational, behind-the-beat:
```
[Vocal: male, mid-range, slightly nasal quality, loose phrasing, laid-back timing, spoken-word adjacent delivery, subtle breath]
```

6. Smoky, chest-dominant, measured:
```
[Vocal: female, deep smoky chest voice, gravelly lower register, slow-drawled delivery, full stops between phrases, raw and unpolished]
```

---

## Describing Voice in Physical Terms

Community testing documented in the [r/SunoAI Prompting Tips thread (April 2026)](https://www.reddit.com/r/SunoAI/comments/1sf9jfz/prompting_tips/) found that prompting with "male" or "female" alone fails roughly 60% of the time. Describing the voice in physical and tonal terms achieves approximately 90% accuracy.

The scholarly basis: [Larrouy-Maestri et al. (2024) in *Perspectives on Psychological Science*](https://pmc.ncbi.nlm.nih.gov/articles/PMC12231869/) distinguishes *naturalness* (absence of artifacts) from *authenticity* (perceived honesty, emotional genuineness). Physical descriptors target both: they shape the acoustic output *and* signal the kind of expressive idiosyncrasy that listeners read as authentic.

### Timbre Descriptors
`airy` · `breathy` · `warm` · `raw` · `gritty` · `raspy` · `smoky` · `weathered` · `gravelly` · `resonant`

### Texture Descriptors
`whispered` · `velvety` · `dreamy` · `nasal` · `brassy` · `rough-edged` · `chilled` · `close-miked`

### Style Descriptors
`staccato` · `legato` · `vibrato-heavy` · `melismatic` · `syncopated` · `spoken-word` · `falsetto runs` · `call-and-response`

### Timing / Feel Descriptors
`laid-back` · `loose phrasing` · `off-beat` · `slow-drawled` · `freeform` · `patient delivery` · `behind-the-beat`

**Anti-pattern:** "tight rhythm" and "on-beat" produce mechanical results. "Loose phrasing" and "laid-back" are the most consistently cited terms for human feel, per the [Facebook Voice Tags Master List (December 2025)](https://www.facebook.com/groups/1673444546790462/posts/2044144026387177/).

**Key substitutions:**

| Instead of | Use |
|---|---|
| `male vocals` | `deep baritone, gravelly rasp, slow-drawled delivery` |
| `female vocals` | `soft breathy tone, alto female, smooth legato style` |
| `smooth vocals` | `warm, close-miked, intimate` |
| `powerful vocals` | `chest voice pushed, raw at peaks, strained upper register` |
| `emotional vocals` | Use the Character Prompt Method — describe the person and moment |

---

## Dynamic Contrast as Composition

Real singers do not deliver every line at the same level. The scholarly basis for this is Juslin's [BRECVEMA framework (*Psychological Bulletin*, 2013)](https://pubmed.ncbi.nlm.nih.gov/23769678/), which identifies emotional contagion — the listener mirroring the physical effort and emotional state of the performer — as a primary mechanism of musical emotion. A voice that never varies its effort gives the listener nothing to mirror.

From the cross-artist technique analysis: the dynamic shift *is* the meaning. Moving from near-whisper to full-bodied chest voice between verse and chorus is the musical equivalent of moving from description to declaration.

**The basic arc:** Begin quieter than you think you should. The first verse is the most interior, most stripped moment. Let the full arrangement — and the full voice — arrive later, so it earns its arrival.

**Four dynamic patterns to direct explicitly:**

1. **Quiet verse / powerful chorus** — the most impactful basic arc. Pull the verse *back* to make the chorus feel inevitable.

2. **Build within a single verse** — start the verse at a low dynamic, let it build line by line so the chorus is already arrived at before it's named.

3. **Whisper-to-belt progression** — reserve full volume for the final chorus or the last line only. Everything before it is a setup.

4. **Restraint at the emotional peak** — pulling back just before the highest-intensity moment is more powerful than staying at full volume. The listener leans in.

**Breath and imperfection as punctuation:** Allow audible breaths between phrases. Allow the voice to show physical effort at climactic moments. A [MusicRadar vocal technique analysis](https://www.musicradar.com/) notes that retaining audible breath — which many producers edit out — communicates sincerity. Vocal fry, slight rasp on stressed words, and register cracks are not failures. They are sonic evidence that the performance is embodied.

---

## In-Lyric Performance Tags

<!-- model:suno -->
Place these tags in `[brackets]` directly before the lyric line they should affect. They direct performance moment-by-moment, overriding the model's default interpretations.

### Emotional Tags
- `[whispered]` — intimate, close, interior delivery
- `[vocal break]` — crack in the voice at a point of peak vulnerability
- `[breathy]` — soft, air-heavy, close-miked quality
- `[raspy]` — edge and grit on the delivery
- `[sobs]` — audible emotional break (use at most once per track)
- `[laughs]` — adds warmth and personality when the lyric earns it (use sparingly)

### Intensity Tags
- `[belting]` — full chest voice, pushed to the top of the range
- `[building intensity]` — progressive energy increase within the tagged section
- `[crescendo]` — place before a build-up section
- `[diminuendo]` — soften for a reflective or closing section
- `[dynamic shift]` — signals a sudden energy change (e.g., quiet verse into punchy hook)

### Pause and Silence Tags
- `[Pause 2s]` — use before a drop, a verse shift, or an emotional moment
- `[Intro Silence 4s]` — clean start; useful for sparse or acoustic openings
- `[Fade Out]` — natural ending for ballads and reflective outros

When combining, all tags go in one bracket set: `[Pause 2s, Fade Out]`

From [Jack Righteous, "Master Pauses & Silence in Suno AI" (February 2025)](https://jackrighteous.com/blogs/guides-using-suno-ai-music-creation/master-pauses-silence-in-suno-ai-pause-intro-silence-song-flow): pauses before emotional peaks are among the highest-impact single techniques available.

### Punctuation as Performance Direction

<!-- model:suno -->
In AI music generation, punctuation is not grammar — it is instruction to the vocalist. From the [Facebook Suno community guide (March 2026)](https://www.facebook.com/groups/1118818620292019/posts/1326242769549602/):

| Punctuation | Effect |
|---|---|
| `,` | Quick breath; line keeps moving |
| `...` | Linger; emotional stretch on the last word |
| `—` | Hard cut or staccato accent |
| `!` | Punch and energy |

**Example — before:**
```
I'm running from ghosts but they're gaining on me heart slamming like war drums
```

**Example — after:**
```
I'm running from ghosts — but they're gaining... Heart slamming — like war drums in my chest!
```

Read lyrics aloud before submitting. Add punctuation for natural pauses, rushes, and punches. You are conducting the singer.

---

## Three Human Vocal Tricks

<!-- model:suno -->
These are in-lyric notation techniques documented in the [YouTube "3 SUNO Tricks for Human-Like Vocals" tutorial (November 2025)](https://www.youtube.com/watch?v=YA0-7W3U_mY). They add the texture and idiosyncrasy that generic prompts cannot produce.

### 1. Spelling
Write a word with dashes between its letters. The model sings it letter by letter.

```
L-O-V-E
```

When to use: moments that need playfulness, irony, or deliberate emphasis. Works well in hooks, bridges, and moments where the lyric is commenting on itself.

Limit: one to two instances per track. More than that becomes a gimmick.

### 2. Stretching
Extend repeated letters on a word to sustain the note.

```
knowwwww
stayyyyed
```

When to use: emotional peaks, the last word before a chorus drop, any word the vocalist should lean into. Has the effect of a singer holding the note beyond where the rhythm would release it.

Placement: strategic only. Apply to the single most important word in a section, not to every emotionally significant word.

### 3. Vocal Spice
Add non-lyrical human sounds between or within lines.

```
Mmmmm
Ooh-ooh
Hmm
```

When to use: to fill space between lines with human texture rather than a clean rest; to add soul to a section that feels too clinical; in the outro when lyrics have ended but the melody hasn't.

Why it works: maintains the human presence through sections where a purely instrumental gap would break the connection. As the tutorial notes, it "deepens the emotional feel" by keeping the voice in the room.

---

## Silence and Space

What the singer does not do is compositional. From the [vocal.media analysis of silence in songwriting](https://vocal.media/art/the-art-of-silence-and-space-in-songwriting): "when a songwriter pauses for a few moments, we are essentially given the microphone and are free to sing along however we see fit." Space creates participation.

**Operational principles:**

- **Leave space between phrases.** Silence between lines lets each line land before the next arrives. Dense, wall-to-wall lyric delivery produces mechanical results even with perfect words.

- **Use instrumental breaks to let vocal nuance breathe.** The vocal is the densest informational element in a track. Keep the instrumentation sparse enough — at least in verses — that every dynamic shift and textural detail in the voice is audible. An over-produced arrangement buries performance.

- **Pause before emotional peaks.** Identify the most important word in the chorus. Ensure that the phrasing or a `[Pause 2s]` tag creates a brief silence immediately before it. The silence increases the weight of what follows.

- **Let silence carry the final line.** The most common structure failure is over-extending the outro. Cut the vocal earlier than feels comfortable. Let the last line echo in space rather than being followed immediately by more sound.

---

## Pacing and Delivery Control

Rushed delivery is the most common technical failure in AI vocal performance. From [HookGenius, "Fix Suno Rushing Lyrics" (February 2026)](https://hookgenius.app/learn/fix-suno-rushed-lyrics/): "Rushed lyrics happen when too many words fit the musical phrase. Four to six words per line maximum for most genres."

**Word count per line:** Count syllables before submitting. Lines with ten or more syllables tend to be crowded and rushed. Four to six words gives the vocal room to breathe and adds natural pauses.

| Rushed | Better |
|---|---|
| "I remember when we used to walk together down that old road" | "I remember when we walked that old road" |
| "There's something about the way you look at me that makes me feel alive" | "The way you look at me... makes me alive" |

**Hyphenation for syllabic stretching:** Writing hyphens between syllables signals the model to elongate each one.

<!-- model:suno -->
```
to-night   for-ev-er   beau-ti-ful   re-mem-ber
```

Use on emotionally important words, not structurally. One or two per section is enough.

**Style-box delivery tags:**
<!-- model:suno -->
Use these in the Style box to control overall pacing: `slow tempo` · `laid-back delivery` · `relaxed pacing` · `space between phrases` · `breathing room` · `unhurried` · `patient delivery` · `drawn out` · `lingering`

Avoid pairing high-energy tags (`upbeat`, `driving`, `fast-paced`) with human-feel goals without balancing them with `space` or `patient delivery`.

---

## Common Vocal Prompting Failures

| Problem | Cause | Fix |
|---|---|---|
| Mechanical, rushed pacing | Too many syllables per line; no breathing room | Cut to 4–6 words per line; add `...` pauses; hyphenate key words |
| Generic output despite "emotional" prompt | Adjective-only prompting; no person or moment defined | Use the Character Prompt Method — describe who is singing and why |
| Wrong gender or range | Used "male" or "female" alone | Describe physical timbre: `deep baritone, slow-drawled` or `soft alto, airy breathy tone` |
| Over-polished, no rawness | Used `smooth`, `polished`, or `crisp` | Replace with `raw`, `intimate`, `weathered`, `rough-edged` |
| No dynamic range; flat delivery | No performance tags in lyrics; every line at same intensity | Add `[whispered]` before quiet lines and `[belting]` before peaks; use behavior tags |
| Vocal identity inconsistent across sections | No Vocal Anchor at top of lyrics | Place `[Vocal: ...]` tag before all other content in the lyrics box |
| Singer sounds robotic on key words | Dense syllable clusters, no breath signals | Add `—` and `...` punctuation; apply hyphenation to critical words |
| Track feels thin despite strong lyrics | Instrumentation competing with voice | Use `sparse arrangement`, `close-miked vocal`, `dry studio room` in style box |

---

## Quick Reference: Tag Inventory

<!-- model:suno -->

**Vocal Anchor (top of lyrics box):**
```
[Vocal: {range/gender}, {timbre}, {delivery style}, {breath behavior}, {vibrato}]
```

**In-lyric performance tags (before target line):**
```
[whispered]  [vocal break]  [breathy]  [raspy]  [belting]
[building intensity]  [crescendo]  [diminuendo]  [dynamic shift]
[sobs]  [laughs]
```

**Pause/silence tags (in lyrics body):**
```
[Pause 2s]  [Intro Silence 4s]  [Fade Out]
[Pause 2s, Fade Out]
```

**Structure behavior tags (replacing plain section labels):**
```
[Structure: Focused Performance]     — tight storytelling, medium energy
[Structure: Build-up]                — rising tension, instruments layering in
[Structure: Anthemic Peak]           — highest energy, full commitment
[Structure: Minimalist Breakdown]    — stripped back, maximum space
[Structure: Emotional Arc]           — signals the whole-song emotional journey
```

**Notation tricks (in lyrics):**
```
L-O-V-E         (sung letter by letter — limit 1–2 per song)
knowwwww        (sustained note — strategic placement only)
Mmmmm / Ooh-ooh (vocal texture — fills space between lines)
```

**Punctuation as direction:**
```
,    quick breath, keep moving
...  linger, stretch the last word
—    hard cut, staccato accent
!    punch, energy
```

---

*Sources: [Ayyildiz et al. (2025), *Scientific Reports*](https://pmc.ncbi.nlm.nih.gov/articles/PMC12373897/) · [Juslin BRECVEMA, *Psychological Bulletin* (2013)](https://pubmed.ncbi.nlm.nih.gov/23769678/) · [Larrouy-Maestri et al. (2024), *Perspectives on Psychological Science*](https://pmc.ncbi.nlm.nih.gov/articles/PMC12231869/) · [arXiv listener perception study (2025)](https://arxiv.org/html/2506.02856v1) · [Fišer et al., PLOS One (2025)](https://pmc.ncbi.nlm.nih.gov/articles/PMC12194076/) · [r/SunoAI Character Prompt Method (Nov 2025)](https://www.reddit.com/r/SunoAI/comments/1ouiswb/advanced_technique_the_character_prompt_method/) · [Facebook Voice Tags Master List (Dec 2025)](https://www.facebook.com/groups/1673444546790462/posts/2044144026387177/) · [Facebook Suno community guide v5 (March 2026)](https://www.facebook.com/groups/1118818620292019/posts/1326242769549602/) · [HookGenius, "Fix Suno Rushing Lyrics" (Feb 2026)](https://hookgenius.app/learn/fix-suno-rushed-lyrics/) · [YouTube "3 SUNO Tricks for Human-Like Vocals" (Nov 2025)](https://www.youtube.com/watch?v=YA0-7W3U_mY) · [YouTube "How to Add Emotion to Suno AI Songs" (March 2026)](https://www.youtube.com/watch?v=NeUYHqO_qjU) · [Jack Righteous, Suno Pauses & Silence (Feb 2025)](https://jackrighteous.com/blogs/guides-using-suno-ai-music-creation/master-pauses-silence-in-suno-ai-pause-intro-silence-song-flow) · [r/SunoAI Prompting Tips (April 2026)](https://www.reddit.com/r/SunoAI/comments/1sf9jfz/prompting_tips/)*
