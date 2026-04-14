# Suno Hidden and Undocumented Features

> **Classification labels used throughout:**
> - `official-ui-feature` — Visible in the Suno UI, documented by Suno
> - `documented-behavior` — Documented by third parties; consistent with platform behavior
> - `community-heuristic` — Discovered by power users; real behavior, mechanism not officially explained

---

## Max Mode

**Label:** `community-heuristic`  
**Sources:** [Reddit u/CrowMagnuS](https://www.reddit.com/r/SunoAI/comments/1pvnpgp/my_secret_trick_dump_since_my_last_post_says_i/), [YouTube ChillPanic](https://www.youtube.com/watch?v=F7Mn21Q0yX8), [YouTube analysis](https://www.youtube.com/watch?v=D0IBRMq6jyA)

**Background:** A visible "Max Mode" button briefly appeared in Suno's UI during V4 beta — it was described as enabling enhanced audio quality, improved realism for acoustic instruments, and better fidelity. The button was removed. Power user CrowMagnuS (200,000+ generations) claims the underlying code path remains accessible via specific prompt formatting.

**Technical interpretation:** This is likely **semantic conditioning**, not a literal feature toggle. The formatting primes the model's attention toward quality-related training signals. It nudges the model's probability distribution toward quality-oriented outputs — it does not flip a switch.

**To activate:** Paste at the **very top of the Style box, before anything else:**
```
[Is_MAX_MODE: MAX](MAX)
[QUALITY: MAX](MAX)
[REALISM: MAX](MAX)
[REAL_INSTRUMENTS: MAX](MAX)
```

**In the Lyrics box, add above lyrics:**
```
///*****///
```

**Skip intro, start directly with first lyric line (add to Style box):**
```
[Is_MAX_MODE: MAX](MAX)
[QUALITY: MAX](MAX)
[REALISM: MAX](MAX)
[REAL_INSTRUMENTS: MAX](MAX)
[NO_INTRO: TRUE][START: "first words of your first lyric line here"]
```

**Duet with specified starting lines:**
```
[Is_MAX_MODE: MAX](MAX)[QUALITY: MAX](MAX)[REALISM: MAX](MAX)[REAL_INSTRUMENTS: MAX](MAX)
[_START_ON TRUE]
[MALE_START: "first male lyric line"]
[FEMALE_START: "first female lyric line"]
```

**Group preference:**
```
[GIRL_GROUP_ON: TRUE]
[BOY_GROUP_ON: TRUE]
```

**Caveats:**
- Works best for acoustic, folk, country, rock, jazz — genres where instrument realism matters
- Effectiveness varies for electronic music ("realism" terms have less impact there)
- Not verified by Suno officially
- Community consensus: "it helps, but it's not magic"
- Results are probabilistic — test across 3–5 generations before concluding

---

## Mumble Mode

**Label:** `community-heuristic`  
**Source:** [YouTube tutorial](https://www.youtube.com/watch?v=I66rssJsPdc), discovered via Suno's YouTube channel

**What it is:** Generates a song with phonetic mumbling instead of real words — allowing you to hear melodic phrasing and rhythm before committing to actual lyrics. Mirrors the "topline writing" technique used by professional songwriters (including Max Martin).

**How to activate:** In the Lyrics box, enter:
```
[Mumble mode] a
```
(The `a` after the tag is intentional and important.)

**Genre compatibility:** Confirmed working for Atlanta Trap, Future Bass, Classic Rock. Believed to work broadly.

**Use case workflow:**
1. Generate with Mumble Mode
2. Listen to the mumbled melody and rhythm pattern
3. Identify phonetically interesting sections
4. Fill in real words that match the phonetic shape of the mumble
5. Regenerate with actual lyrics

---

## Sounds Beta Mode

**Label:** `official-ui-feature`  
**Source:** [Reddit announcement thread](https://www.reddit.com/r/SunoAI/comments/1ql14no/make_sounds_from_scratch_in_suno/), Suno Discord

**What it is:** A distinct creation mode (separate from Song creation) that generates one-shot samples and loops rather than full songs.

**Access:** Create → click the dropdown arrow next to "Custom" → select **Sounds**

**Available to:** Pro and Premier members only (Beta)  
**Cost:** 2 credits per clip

| Type | Use Case |
|---|---|
| **One-shot** | Single sample (snare hit, glass break, airhorn, footstep) |
| **Loop** | Repeating loop (guitar riff, bass line, synth melody) — set Key and Tempo |

**Usage notes:**
- For spoken word, leave Key and BPM on "Any"
- For musical loops, specify BPM and Key for significantly better output
- Generated sounds integrate directly into Suno Studio sessions
- Can add effects (reverb, echo) in the prompt description
- Pairs with **Sample (Beta)** mode — take a slice of an existing Suno song and use it as a seed

Often categorized as "hidden" because the UI makes the dropdown easy to miss.

---

## Preserve Melody Tags

**Label:** `community-heuristic`  
**Source:** [Reddit CrowMagnuS trick dump](https://www.reddit.com/r/SunoAI/comments/1pvnpgp/my_secret_trick_dump_since_my_last_post_says_i/)

Place in the Style box or Lyrics box to signal the model to maintain structural consistency across sections. Useful when extending a song or generating a second variation, to reduce drift where the model replays a different melody or ignores established motifs.

```
[PRES_MELO]   — preserve melody
[P_VERSE]     — preserve verse melody
[PRES_CHOR]   — preserve chorus melody
[PRES_SOLO]   — preserve solo
[PRES_BRIDGE] — preserve bridge
[VERSE1]      — explicit verse 1 labeling for structure preservation
[VERSE2]      — explicit verse 2 labeling
```

---

## Persona Extension Trick

**Label:** `community-heuristic`  
**Source:** [Reddit CrowMagnuS trick dump](https://www.reddit.com/r/SunoAI/comments/1pvnpgp/my_secret_trick_dump_since_my_last_post_says_i/)

For older songs or uploaded audio that you want to turn into a Persona, but Persona creation is blocked or the clip is too old:

1. Take the song/upload into the Song Editor
2. Use Extend from the very end, with no lyrics or prompts
3. A 2-second extension is generated and credits are refunded
4. Click on the generation → "Get full song" → fills blank seconds
5. This enables Persona creation from the updated clip

Works on both older Suno-generated songs and uploaded audio files.

---

## Suno Labs / MILO-1080

**Label:** `official-ui-feature` (Labs as a platform section), `documented-behavior` (MILO-1080 features)  
**Sources:** [MusicRadar](https://www.musicradar.com/music-tech/suno-takes-another-step-into-music-production-with-ai-step-sequencer-milo-1080), [RouteNote](https://routenote.com/blog/suno-milo-1080-ai-step-sequencer/)

**Suno Labs:** A dedicated section within the Suno platform that serves as an incubator for experimental projects. Located at the bottom of the sidebar. Labs features are previews — unfinished and subject to change. Pro/Premier users are more likely to see new Labs features first.

**MILO-1080 (Model-Integrated Loop Orchestrator):** Browser-based 16-track step sequencer and synthesizer launched ~March 24, 2026.

| Feature | Details |
|---|---|
| **16 Tracks** | AI-generated samples, Suno library clips, or synth-designed sounds |
| **Synth Engine** | Two-oscillator design with FM capabilities and multimode filter |
| **AI Generation** | Generate sounds via text prompt (costs paid credits) |
| **Idea Generator** | Select genre + key → generates sequences with beats and melodies |
| **MIDI** | Import MIDI files; export MIDI from finished sequences |
| **Sequencing Modes** | Euclidean sequencing; probabilistic sequencing |
| **Song Arranger** | Organize multiple sequences before export |
| **Mastering** | Apply master effects before export |

**Target user:** People with music production experience. Developer Kieron Donoghue: "MILO-1080 is a step sequencer. That's not a tool for casual users."

**Note:** The Idea Generator results were described by MusicRadar as inconsistent.

---

## Suno Studio (the DAW)

**Label:** `official-ui-feature`  
**Source:** [Suno Studio Blog](https://suno.com/blog/suno-studio), [Suno Studio Welcome](https://suno.com/studio-welcome)

Launched September 25, 2025 (Premier users). Described as "The world's first generative audio workstation." Built from Suno's acquisition of browser-based DAW Wavtool (June 2025).

**Access:** Desktop only; Premier plan required for full access (Pro gets partial access)

| Capability | Details |
|---|---|
| Multitrack Timeline | Full multitrack editing in the browser |
| Stem Generation | Generate unlimited AI stem variations that fit existing audio |
| Stem Export | Audio AND MIDI; compatible with any DAW; up to 12 stems (Premier) |
| BPM Control | Tempo adjustment |
| Pitch Control | Per-track pitch adjustment |
| Section Editing | Quick Replace, add/split/crop, fades |
| Remaster | Clean up mix, balance EQ, reduce hiss |
| Warp Markers | Added in Studio 1.2 (Nov 2025) |
| Remove FX | Added in Studio 1.2 |
| Alternates | Generate alternate versions of sections (Studio 1.2) |
| Time Signature Support | Added in Studio 1.2 |

**Stem Cover workflow:** Start from an uploaded track or AI-generated song → isolate the stem you want to change → use Cover in Studio to replace with AI-generated or your own audio → re-export.

---

## Voices / Voice-to-Song (v5.5)

**Label:** `official-ui-feature`  
**Source:** [Suno Voices Help](https://help.suno.com/en/articles/11362369), [Suno Hub Voice Guide](https://suno.com/hub/ai-voice-cloning), [v5.5 Blog](https://suno.com/blog/v5-5)

**Requirements:** Pro or Premier only; must be 18+; not available in all regions.  
**Audio input:** Minimum 15 seconds, up to 4 minutes (Suno selects best 2 minutes).  
**Best results:** Acapella recordings (no backing music).

**Setup:**
1. In Create, click **Add Voice**
2. Select source: Suno library song, real-time recording, or uploaded file
3. **Voice Verification:** Suno displays a short phrase you must speak aloud — confirms you're using your own voice (anti-impersonation)
4. Set skill level, add profile image, name the voice
5. Confirm you have rights to the voice → Save

**Using in a song:** Add Voice in Create → select from your list → add lyrics + style → set Audio Influence slider high → Create.

**Best practices:**
- Acapella recordings produce cleanest results
- Record in an acoustically neutral room (minimal reverb)
- Variety in your recording (different pitches, emotions) helps the model generalize
- If desired, download the generated instrumental stem and re-record real vocals over it in a DAW

**Limitations:** Community reports inconsistency with capturing exact personal vocal timbre; works better with clear, stronger voices than soft or highly stylized voices.

---

## Custom Models (v5.5)

**Label:** `official-ui-feature`  
**Source:** [v5.5 Blog](https://suno.com/blog/v5-5)

- Upload at least 6 of your original tracks to train a personalized version of the v5.5 model
- Model learns your style; output sounds more like your music
- Pro and Premier users can create up to 3 custom models
- Trains on your own catalog, not public Suno music

---

## My Taste (v5.5)

**Label:** `official-ui-feature`  
**Source:** [v5.5 Blog](https://suno.com/blog/v5-5)

- Personalization based on what you've generated and liked over time
- Suno learns your preferred genres and moods
- Available to **all users** including free tier
- Passive — improves automatically as you use the platform

---

## Personas and Covers

**Label:** `official-ui-feature`  
**Sources:** [Suno Help Center](https://help.suno.com/), [Jack Righteous Personas Guide](https://jackrighteous.com/blogs/guides-using-suno-ai-music-creation/suno-ai-personas-update-dec-2025-what-changed-how-to-use-it)

**Persona:** Saves the "essence" of a song — vocals, style, character — for reuse across future songs. Works as a voice/style bookmark, not full custom voice training.

**Personas are NOT:**
- Custom voice training on your uploaded recordings (that's the Voices feature)
- Ownership proof of a vocal identity
- A guarantee your genre stack will override Persona style

**Creating a Persona:**
1. Find a song with the voice/style you want to preserve
2. Click three-dot menu → Create → Make Persona
3. **Critical:** Personas are PUBLIC by default — toggle private if needed
4. Name it, optionally add avatar and description

**Using a Persona:**
1. Go to Custom mode in Create
2. Persona area appears above the lyrics field
3. Select Persona → auto-populates style details into "Style of Music" field
4. Always review and edit the auto-populated field rather than accepting defaults
5. Let the Persona carry identity; let your prompt carry only key constraints

**Tips:**
- Run 2–3 short tests with a Persona before committing full-length credits
- For consistent album-like output, lock a Persona + stable prompt recipe and reuse across an EP

**Cover Feature:** Start with an acapella, instrumental, or combo track as a seed. Suno expands into a full song. **Commercial restriction:** Songs created via the in-platform Cover feature are joint works and remain non-commercial even for paid users.

---

## Gibberish Vocal Trick

**Label:** `community-heuristic`  
**Source:** [Reddit r/SunoAI community strategies](https://www.reddit.com/r/SunoAI/)

**What it is:** Fill the lyrics field with phonetic sounds that approximate your desired rhythm and melodic shape (e.g., `da-da-DUM da-da-DUM` or `na-na-NA na-na-NA`). The model often aligns its vocal melody to the phonetic structure of the placeholder text.

**Use case:** You know the rhythmic pattern you want but haven't written lyrics yet. The gibberish placeholder "teaches" the model the prosodic shape.

**Workflow:**
1. Generate with gibberish lyrics
2. Listen to the melody and rhythm that emerges
3. Write real lyrics that match the phonetic shape
4. Regenerate with actual lyrics

This is a more manual version of Mumble Mode — use Mumble Mode first; fall back to gibberish if Mumble Mode doesn't produce the right phrasing.
