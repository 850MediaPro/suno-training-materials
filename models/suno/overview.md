# Suno AI — Overview

> **Current version as of April 2026:** v5.5 (Pro/Premier subscribers). Free tier receives v4.5.  
> Check [suno.com/blog](https://suno.com/blog) for the latest release.

---

## Model Version History

Source: [Suno Help Center Model Timeline](https://help.suno.com/en/articles/5782721)

| Version | Released | Key Capabilities | Max Generation |
|---|---|---|---|
| V2 | Fall 2023 | Initial public release via Discord | 1 min 20 sec |
| V3 | Spring 2024 | Improved generation quality | 2 min |
| V3.5 | Summer 2024 | Better song structure | 4 min (first gen) |
| V4 | November 2024 | Improved vocal quality; adds Extend, Cover, Persona | 4 min |
| V4.5 | May 2025 | Up to 8-min first gen; improved prompt adherence; smarter style mashups | 8 min |
| V4.5+ | July 2025 | Add Vocals / Add Instrumental production tools | 8 min |
| V5 | September 2025 | Superior audio quality; 44.1kHz stereo; authentic vocals; better prompt following; wide stereo imaging | ~8 min |
| V5.5 | March 26, 2026 | Voices, Custom Models, My Taste; most expressive model | ~8 min |

Source: [Suno Blog](https://suno.com/blog), [The Verge v5.5 coverage](https://www.theverge.com/entertainment/903056/suno-ai-music-v5-5-model)

---

## Core Capabilities (Current Generation)

| Capability | Details |
|---|---|
| **Audio quality** | 44.1kHz stereo output; studio-grade clarity |
| **Vocal quality** | Authentic-sounding human vocals; responsive to tonal and delivery descriptors |
| **Intelligent structure** | Smarter dynamic shifts between sections; better arrangement arc |
| **Adaptive creativity** | Responds to style mashups and unusual genre combinations |
| **Granular control** | Bracket tags, vocal anchor blocks, mixing-language vocabulary in style box |
| **Persistent characters** | Voices (v5.5) and Personas preserve vocal identity across songs |
| **Speed** | Multiple generations in parallel; typical wait under 30 seconds |
| **Studio integration** | Suno Studio (Premier): multitrack editing, stem export, MIDI export |

---

## Platform Architecture

```
CREATION LAYER
├── Standard Create (Simple / Custom mode)
│     ├── Text-to-song with Style box + Lyrics box
│     ├── Voice mode (v5.5, Pro/Premier) — use your trained voice
│     ├── Sounds mode (Beta, Pro/Premier) — generate samples/loops
│     └── Audio Influence / Cover / Sample modes
│
├── Suno Studio (the DAW — Premier + some Pro)
│     ├── Multitrack timeline editing
│     ├── Stem generation and editing
│     ├── BPM / Pitch / Volume control per track
│     ├── Section editing (Quick Replace, add/split/crop, fades)
│     ├── Warp Markers, Remove FX, Alternates (Studio 1.2, Nov 2025)
│     └── Export: audio stems + MIDI (up to 12 stems, Premier)
│
└── MILO-1080 [Labs Preview]
      ├── 16-track step sequencer
      ├── AI-powered sample generator (prompt-based, costs credits)
      ├── Two-oscillator FM synth engine
      ├── Euclidean + probabilistic sequencing
      └── MIDI import/export

PERSONALIZATION LAYER
├── Voices (v5.5, Pro/Premier) — your voice in AI songs
├── Custom Models (v5.5, Pro/Premier, max 3) — train on your catalog
├── My Taste (all users) — learned style preferences
└── Personas — save song "essence" for reuse in Custom mode

DISCOVERY / SOCIAL LAYER
├── Public songs / trending
├── Persona library (public by default unless toggled)
└── Songkick integration [acquired from WMG, Nov 2025 — in development]
```

---

## Strengths and Weaknesses

### Strengths
- Longest generation length (~8 minutes) of any major AI music tool
- 12-stem export (Premier) — unique for AI music generation
- Voices + Custom Models for true personalization
- Suno Studio DAW with MIDI export
- Active community with documented techniques and heuristics
- Wide genre range with strong Western pop/rock/country/hip-hop representation

### Weaknesses
- Vocals can lean too smooth, too reverb-heavy, lacking raw human edges
- Specific rawness and emotional graininess are hard to force consistently
- Some muddiness in remix/mashup workflows
- AI still ignores parts of prompts sometimes — treat techniques as high-probability, not guarantees
- No official public API (as of April 2026)
- MILO-1080 Idea Generator results described as inconsistent

---

## Pricing Tiers and Licensing

Source: [Suno Community Guidelines](https://suno.com/community-guidelines), [Music In Africa policy summary](https://www.musicinafrica.net/magazine/suno-adjusts-ai-music-ownership-terms-after-warner-music-partnership/)

| Tier | Commercial Use | Ownership | Access to Models | Key Features |
|---|---|---|---|---|
| **Free** | Personal/non-commercial only | None | V4.5 only | My Taste; limited generations |
| **Pro** | Commercial license granted | License (not ownership) | V5, V5.5 | Voices, Custom Models (up to 3), Suno Studio (partial) |
| **Premier** | Full commercial license | License (not ownership) | V5, V5.5 | All Pro features + Suno Studio (full), stem/MIDI export (12 stems) |

**Important notes:**
- The word "ownership" was removed from Suno's paid-tier descriptions in 2025. Paid users receive a **perpetual commercial license**, not legal copyright ownership
- Songs made on the free tier do not retroactively become commercially licensed if you later subscribe — the license applies only to songs generated while a paid subscription is active
- Free-tier songs: playable and shareable only; no downloads off the platform
- Paid subscribers: monthly download limits apply

---

## Rights and Licensing Situation

Source: [Reuters](https://www.reuters.com/legal/litigation/warner-music-group-settles-copyright-case-with-suno-licensed-ai-music-2025-11-25/), [Hollywood Reporter](https://www.hollywoodreporter.com/music/music-industry-news/warner-music-group-settles-ai-infringement-suit-with-suno-1236435516/), [MystStats Music Legal Guide 2026](https://mystats.music/blog/suno-ai-legal-guide-2026)

### WMG Settlement (November 2025)
- Warner Music Group settled its copyright infringement lawsuit against Suno — the first major label to do so
- Settlement includes: undisclosed financial terms; Suno acquires Songkick from WMG
- Partnership terms require Suno to introduce "new, more sophisticated and licensed models"
- Artists retain "complete control over the use of names, likeness, voices and compositions in newly generated AI music"
- **As of April 2026:** UMG and Sony lawsuits against Suno remain active

### Copyright
- The US Copyright Office generally does not recognize AI-generated audio as copyrightable
- Paid subscribers can monetize Suno tracks but cannot hold copyright on the raw AI audio
- Adding significant human contribution (re-recorded vocals, live instruments) strengthens copyright claim
- **The work-for-hire path:** Generate → export stems → re-record with human musicians → the re-recorded version is legally defensible

### DDEX AI Disclosure (2026)
- Effective late 2025: Spotify and Apple Music enforce the DDEX Industry Standard for AI Disclosure
- Tracks using Suno-generated audio must be flagged as "Synthetic Content" during upload via distributor (DistroKid, TuneCore, etc.)
- Failure to disclose risks: permanent demonetization, removal from curated playlists, account strikes

### Songs Created via Remix / Cover
Songs created through Suno's in-platform remix/cover feature are treated as joint works and remain **non-commercial** — even for paid users, even with the original creator's permission.

---

## Safety Constraints Summary

Source: [Suno Community Guidelines](https://suno.com/community-guidelines)

Suno blocks generation of:
- Explicit sexual content (zero tolerance for content involving minors)
- Content promoting violence, terrorism, or hate speech
- Content based on protected characteristics (race, religion, gender, sexuality)
- Misinformation, hoaxes
- Content facilitating illegal activities

**IP and privacy:**
- Link-Only content is not truly private — anyone with the link can access and reuse prompts
- Uploading copyrighted audio places all copyright liability on the uploader
- Suno's Terms of Service grant Suno broad rights over content you submit (including training use)

**Enforcement:** temporary suspension → permanent suspension → account deletion. Report: `abuse@suno.com`
