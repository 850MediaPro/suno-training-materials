# Gemini / Lyria Prompting Guide

> **model:gemini** — All techniques in this file are Gemini/Lyria-specific unless noted.

---

## Core Prompt Framework

Lyria uses a **single unified prompt field** — there is no two-box system like Suno. Write the full brief as one block.

**Framework:**
```
[Genre + Era] + [Mood] + [Instrumentation] + [Tempo] + [Vocal style] + [Lyrics]
```

This maps to the universal framework as follows:

| Universal Layer | Lyria Equivalent |
|---|---|
| genre/style | Genre + specific era (e.g., "early 90s West Coast hip-hop") |
| arrangement/instrumentation | Named instruments (critical — Lyria auto-selects genre defaults if not specified) |
| performance/feel | Tempo, rhythm, mood, dynamic arc |
| mix/space | Adjectives describing room, reverb, intimacy (less granular than Suno) |
| technical constraints | "Instrumental" or "no vocals" explicitly stated; negative prompts via API |

**Key difference from Suno:** Lyria understands natural language — you do not need special bracket syntax or shorthand tags. Write descriptively and specifically.

---

## The "Anchor Formula" for Structured Prompts

For Lyria 3 Pro (longer tracks), use this three-part anchor before adding structural details:

1. **Genre + specific era** — sets the structural skeleton (e.g., "late-2000s indie folk")
2. **Mood / emotional intent** — directional guide (e.g., "nostalgic and tender")
3. **Instrumentation + dynamics** — technical execution (e.g., "fingerpicked guitar, soft cello, sparse brushed drums, quiet verse building to open chorus")

Then add timestamp blocks for precise arrangement control.

---

## Four Core Rules

Source: [Google Cloud Blog – Ultimate Prompting Guide](https://cloud.google.com/blog/products/ai-machine-learning/ultimate-prompting-guide-for-lyria-3-pro)

1. **Be descriptive and specific.** Adjectives are your primary lever. "Warm, slightly overdriven Fender Rhodes" beats "piano."
2. **Reference genres and eras.** Anchor the model in a well-defined cultural context. "Early 90s West Coast hip-hop" is far more directive than "hip-hop."
3. **Name key instruments.** If you don't specify, Lyria auto-selects genre defaults — which may not match your intent.
4. **Iterate.** Generation is non-deterministic. Refine by adding, removing, or changing keywords.

---

## Prompt Elements Reference

| Element | Description | Examples |
|---|---|---|
| **Genre & Style** | Primary category and era | "Cinematic orchestral fantasy", "early 90s hip-hop", "K-pop with Motown edge" |
| **Mood & Emotion** | Atmospheric intent | "Tense and suspenseful", "warm and intimate", "dreamy", "nostalgic", "ethereal" |
| **Instrumentation** | Named instruments | "Nylon-string guitar", "Fender Rhodes", "808 bassline", "brass section" |
| **Tempo & Rhythm** | Speed and rhythmic character | "120 BPM", "slow ballad", "driving beat", "syncopated rhythm" |
| **Vocal style** | Gender, range, timbre, delivery | "Breathy female soprano", "commanding baritone", "raspy", "gravelly" |
| **Language** | Sung vocal language | English, German, Spanish, French, Hindi, Japanese, Korean, Portuguese |
| **Lyrics** | Custom or AI-generated | `Lyrics:` prefix for custom; describe theme for AI-generated |
| **Song key** | Musical key | "A major", "D minor" |
| **Instrumental** | Suppress all vocals | Write "instrumental" or "no vocals" explicitly |

Source: [Google Cloud Docs – Lyria Prompt Guide](https://docs.cloud.google.com/vertex-ai/generative-ai/docs/music/music-gen-prompt-guide)

---

## Custom Lyrics Syntax

**Custom lyrics:** Prefix with `Lyrics:` — everything after is treated as lyrics.

```
Lyrics: Let's go (go)
```

The parenthetical `(go)` creates a backing vocal echo.

**Backing vocals in lyrics:** Add parenthetical instructions or specify in the main prompt:
- In lyrics: `Tonight the distance dissolves (dissolves)`
- In prompt: "backing singers echo the main vocal line"

**AI-generated lyrics:** Describe a theme without using the `Lyrics:` prefix:
- "a love song about long-distance relationships"
- "a happy birthday song for my best friend"

Source: [Google DeepMind – Lyria Prompt Guide](https://deepmind.google/models/lyria/prompt-guide/)

---

## Timestamp Prompting (Lyria 3 Pro)

> **model:gemini** — Lyria 3 Pro only. No equivalent in Lyria 3 Clip or Lyria RealTime.

Use `[mm:ss - mm:ss]` format to specify what happens in each time window. For shorter events, use a single timestamp: `[00:30]`.

**Example: Jazz-R&B Fusion**

Source: [Google Cloud Docs – Lyria Prompt Guide](https://docs.cloud.google.com/vertex-ai/generative-ai/docs/music/music-gen-prompt-guide)

```
[0:00 - 0:12] Intro: Begin atmospherically with just the Fender Rhodes
playing soft, hazy chords. Intensity: 1/10 (Very Low)

[0:12 - 0:24] Verse 1: The laid-back drum beat enters with a simple kick
and snare. A soft, ethereal synth pad swells in. Intensity: 3/10 (Low)

[0:24 - 0:36] Build: The groove deepens as a gentle, syncopated hi-hat
is added. Intensity: 5/10 (Medium)

[0:48 - 1:00] Outro: The drums and bass drop out completely. The track
fades. Intensity: 2/10 (Very Low)
```

**Intensity ratings** (e.g., `Intensity: 5/10 (Medium)`) give fine-grained energy control at each section.

**Best practice:** Always provide a chronological roadmap for 3-minute tracks — without timestamps, Lyria 3 Pro tends to default to repetitive loops.

---

## Negative Prompts (API)

> **model:gemini** — API only. Not surfaced in the Gemini app UI.

Available in the legacy `lyria-002` API and Vertex AI documentation:

```json
{
  "instances": [
    {
      "prompt": "A calm acoustic folk song with a gentle guitar melody and soft strings.",
      "negative_prompt": "drums, electric guitar",
      "seed": 98765
    }
  ],
  "parameters": {
    "sample_count": 1
  }
}
```

Use `negative_prompt` to explicitly exclude elements. To suppress vocals in the Gemini app, write "instrumental" or "no vocals" in your prompt text.

---

## Image-to-Music Inputs

Lyria accepts up to 10 reference images in AI Studio / API. The model uses visual content, composition, and color to derive mood and style — not specific musical notation.

**When to use:** When you have a mood board, character artwork, landscape, or visual concept and want music that matches the atmosphere.

**How to use in AI Studio:** Upload images alongside your text prompt. The image influence is blended with the text description.

**Also supported:** PDF files (for emotional baseline), video (Gemini app — generates matching soundtrack).

Source: [Google Blog – Build with Lyria 3](https://blog.google/innovation-and-ai/technology/developers-tools/lyria-3-developers/)

---

## Example Prompts by Complexity Level

**Simple (Lyria 3 Clip, 30 seconds):**
```
Create a '90s skate punk rock track to tell my roommate Ryan to wash the dishes; 
high energy, fast drums.
```

**Intermediate (Lyria 3 Clip or Pro):**
```
A dreamy indie pop track with a breathy female vocal. Instruments: soft synth pads, 
acoustic guitar, gentle beat. Slow tempo, nostalgic mood, spacious reverb.
```

**Advanced (Lyria 3 Pro with custom lyrics and vocal duet):**
```
A romantic fusion of classic Bossa Nova and modern R&B. The mood is intimate, warm, 
and deeply affectionate. Features a gentle acoustic nylon-string guitar, warm electric 
piano chords, and a crisp, laid-back modern hip-hop drum beat. A slow, swaying tempo.
Featuring a vocal duet: a smooth male vocalist singing in English, and a soft, breathy 
female vocalist singing in French. 
Lyrics: Tonight the distance dissolves (dissolves). We speak in the space between words (between words).
```

**Timestamp-structured (Lyria 3 Pro — full arrangement control):**
```
Genre: Late-80s dream pop with ambient influence. Mood: Melancholic and expansive.

[0:00 - 0:20] Intro: Reverb-drenched electric guitar arpeggios only. Very sparse. No drums.
[0:20 - 0:50] Verse 1: Breathy female vocal enters, singing softly. Minimal bass. Brushed snare at low volume. Intensity: 2/10
[0:50 - 1:10] Pre-Chorus: Bass thickens. Hi-hats appear. Vocal gets more intense. Intensity: 5/10
[1:10 - 1:40] Chorus: Full band. Layered vocals. Bright, wide stereo. Emotional peak. Intensity: 8/10
[1:40 - 2:00] Break: Drops to just guitar and voice. Intimate. Intensity: 2/10
[2:00 - 2:30] Final Chorus: Full band returns. Extra harmonies. Maximum energy. Intensity: 9/10
[2:30 - 3:00] Outro: Gradual fade. Guitar arpeggio remains. Reverb tail dissolves.
```

Sources: [Google Cloud Blog – Ultimate Prompting Guide](https://cloud.google.com/blog/products/ai-machine-learning/ultimate-prompting-guide-for-lyria-3-pro), [Google Blog – 6 Tips for Prompting Lyria 3](https://blog.google/products-and-platforms/products/gemini/tips-prompting-lyria-3/)

---

## Lyria RealTime Parameters

> **model:gemini** — Lyria RealTime only. Continuous streaming via WebSocket; instrumental only (no vocals).

Source: [Gemini API – Lyria RealTime Docs](https://ai.google.dev/gemini-api/docs/realtime-music-generation)

| Parameter | Type | Range | Description |
|---|---|---|---|
| `guidance` | float | 0.0–6.0 (default: 4.0) | Prompt adherence. Higher = better adherence, more abrupt transitions. |
| `bpm` | int | 60–200 | Beats per minute. Requires `reset_context()` to take effect. |
| `density` | float | 0.0–1.0 | Note density. Lower = sparser arrangement. |
| `brightness` | float | 0.0–1.0 | Tonal quality. Higher = brighter/higher frequencies emphasized. |
| `scale` | Enum | All 12 keys (major/minor) | Musical key and mode. Requires `reset_context()`. |
| `mute_bass` | bool | — | Reduces bass output. |
| `mute_drums` | bool | — | Reduces drums output. |
| `only_bass_and_drums` | bool | — | Steers output to bass and drums only. |
| `music_generation_mode` | Enum | QUALITY, DIVERSITY, VOCALIZATION | VOCALIZATION treats voice as an instrument (no lyrics). |
| `temperature` | float | 0.0–3.0 (default: 1.1) | Randomness/creativity level. |
| `top_k` | int | 1–1000 (default: 40) | Diversity of token sampling. |

### WeightedPrompt System

Blend multiple text prompts with float weights. Morph between styles in real-time by shifting weights while the stream plays:

```python
await session.set_weighted_prompts(prompts=[
    WeightedPrompt(text="Upbeat jazz", weight=0.8),
    WeightedPrompt(text="Reggae groove", weight=0.2)
])
```

Any non-zero weight value is valid; 1.0 is the starting default.

---

## Composer Mode in Google AI Studio

AI Studio offers a dedicated **Composer mode** for Lyria 3 Pro — build a song section-by-section through a visual interface instead of writing one long prompt. Set timing, intensity, and description for each section individually.

Access: AI Studio (aistudio.google.com) → model selector dropdown → Lyria 3 Pro → Composer mode

Source: [Google Blog – Build with Lyria 3](https://blog.google/innovation-and-ai/technology/developers-tools/lyria-3-developers/)

---

## What Works Well vs. What Doesn't

| Works Well | Doesn't Work Well |
|---|---|
| Genre blending ("Bossa Nova and modern R&B fusion") | Vague "vibe" prompts for Pro ("happy pop" alone) |
| Specific vocal direction ("breathy female soprano that gets quieter as track progresses") | Naming a specific artist to clone their sound (filters redirect to "broad inspiration") |
| Dynamic arc descriptions ("quiet piano builds into explosive chorus") | Single massive run-on paragraphs for complex tracks |
| Timestamp structure for 3-minute tracks | Assuming genre defaults (always name your instruments) |
| Image inputs for emotional baseline | Mixing languages without declaring intent |
| Multi-vocal, multi-language prompts | Expecting stem separation or audio reference input (not supported) |
| Intensity ratings within timestamps | Attempting to extend or edit existing generations (single-turn only) |

---

## Differences from Suno Prompting

| Dimension | Suno | Gemini / Lyria |
|---|---|---|
| Input structure | Two-box (Style box + Lyrics box) | Single unified prompt |
| Syntax | Bracket tags `[Chorus]`, modifier syntax `( )` `{ }` `* *` | Natural language; timestamp blocks for Pro |
| Section control | Bracket tags in Lyrics box | Timestamp blocks with `[mm:ss - mm:ss]` |
| Vocal personalization | Voices feature, Custom Models | Prompt-based only; no voice cloning |
| Max length | ~8 minutes | ~3 minutes (Pro); 30 sec (Clip) |
| Stems | Up to 12 stems (Premier) | None |
| Audio reference | Upload audio as seed/cover | No audio input (images/video only) |
| Negative prompts | `no [element]` in Style box; Exclude field | `negative_prompt` API parameter only |
| Extension / editing | Section editing, Extend, Quick Replace | No — single-turn generation only |
| API availability | No official public API | Full Gemini API + Vertex AI |

---

## Use Case Recommendations

| Use Case | Recommended |
|---|---|
| Quick 30-second social clip | **Lyria 3 Clip** (Gemini app, free) |
| Full song for personal / creator use | **Suno v5.5** — better hooks, longer tracks |
| Video scoring with precise timing | **Lyria 3 Pro** — timestamp control matches scene cuts |
| DAW integration / stem editing | **Suno** — 12-stem export; Lyria has no stem support |
| API integration / production app | **Lyria** — full Gemini API + Vertex AI |
| Enterprise / branded content at scale | **Lyria** (Vertex AI) — SynthID compliance, Google ecosystem |
| Live / interactive performance | **Lyria RealTime** — only AI music streaming model |
| Voice personalization | **Suno** (Voices + Custom Models) |
| Multi-language songs | **Lyria** — 8 languages, vocal duet support |
| Image-inspired soundtrack | **Lyria** — multimodal image input not offered by Suno |
