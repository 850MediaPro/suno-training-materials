# Gemini / Lyria — Overview

> **Current versions as of April 2026:** Lyria 3 (Clip), Lyria 3 Pro, Lyria RealTime  
> Check [blog.google](https://blog.google/innovation-and-ai/) for the latest releases.

---

## What Is Lyria?

Lyria is Google DeepMind's family of generative AI music models. It generates full musical compositions — including instrumentation, vocals, and lyrics — entirely from scratch, not by stitching together pre-recorded loops. ([Google Blog – Lyria 3 launch](https://blog.google/innovation-and-ai/products/gemini-app/lyria-3/))

### Relationship to Gemini
Lyria is a specialized DeepMind model **integrated into the Gemini ecosystem** but is distinct from Gemini's language model. In the Gemini app, music generation is accessed via the "Music" tool (music note icon in the toolbar).

- Gemini app in **Fast mode** → uses Lyria 3 (Clip, 30 seconds)
- Gemini app in **Thinking / Pro mode** → uses Lyria 3 Pro (up to ~3 minutes)

Google acquired ProducerAI (formerly Riffusion) in February 2026 to expand Lyria's reach to professional musicians. ([TechCrunch – Lyria 3 Pro](https://techcrunch.com/2026/03/25/google-launches-lyria-3-pro-music-generation-model/))

### Model Lineage
- **MusicLM** (2023): Google's first public text-to-music research model; initially withheld due to copyright concerns
- **Lyria 1/2**: Research and limited-access predecessors; `lyria-002` remains the legacy Vertex AI API model ID
- **Lyria 3** (February 18, 2026): Current-generation model; auto-generates lyrics; greater style/vocal/tempo control
- **Lyria 3 Pro** (March 25, 2026): Full structural awareness (intro, verse, chorus, bridge); up to ~3 minutes

---

## Model Variants Table

| Variant | API Identifier | Duration | Best For |
|---|---|---|---|
| **Lyria 3 (Clip)** | `lyria-3-clip-preview` | 30 seconds | Quick clips, social media, rapid prototyping |
| **Lyria 3 Pro** | `lyria-3-pro-preview` | Up to ~3 minutes | Full songs, structured compositions, long-form |
| **Lyria RealTime** | `models/lyria-realtime-exp` | Infinite stream | Live performance, interactive apps, DJ tools |
| **Lyria 2 (legacy)** | `lyria-002` | 30 seconds (instrumental only) | Vertex AI legacy API integrations |

Sources: [Google Blog – Build with Lyria 3](https://blog.google/innovation-and-ai/technology/developers-tools/lyria-3-developers/), [Google Cloud Docs – Lyria API](https://docs.cloud.google.com/vertex-ai/generative-ai/docs/model-reference/lyria-music-generation)

---

## Access Points

### Consumer Surfaces

| Surface | Model(s) | Tier Required | Notes |
|---|---|---|---|
| **Gemini App** (gemini.google.com) | Lyria 3 Clip (Fast mode), Lyria 3 Pro (Thinking/Pro mode) | Free for Clip; paid (AI Plus/Pro/Ultra) for Pro | Generates track + auto cover art. Share/download supported. 18+, 8 languages. |
| **ProducerAI** | Lyria 3 Pro | Free and paid tiers | Agentic experience for artists and producers ([Google Blog](https://blog.google/innovation-and-ai/technology/ai/lyria-3-pro/)) |
| **Google Vids** | Lyria 3 and Pro | Google Workspace AI Pro & Ultra subscribers | Auto-score custom music for videos. Rolling out April 2026. |
| **YouTube Dream Track** | Lyria 3 | YouTube Creators (all countries as of Feb 2026) | AI-generated Shorts soundtracks |

### Developer / Enterprise Surfaces

| Surface | Model(s) | Notes |
|---|---|---|
| **Google AI Studio** | Lyria 3 Clip, Pro, RealTime | Paid API key. Playground with Composer mode UI. |
| **Gemini API** | Lyria 3 Clip, Pro, RealTime | Public preview. Build custom apps. |
| **Vertex AI** | Lyria 3, Lyria 3 Pro | Public preview. Enterprise scale. Gaming soundtracks, creative platforms. ([Google Cloud](https://cloud.google.com/blog/products/ai-machine-learning/lyria-3-and-lyria-3-pro-on-vertex-ai)) |

---

## Capabilities and Constraints

| Feature | Lyria 3 (Clip) | Lyria 3 Pro | Lyria RealTime |
|---|---|---|---|
| Vocals + lyrics | ✓ | ✓ | ✗ (instrumental only) |
| Instrumentals | ✓ | ✓ | ✓ |
| Custom provided lyrics | ✓ | ✓ | ✗ |
| AI-generated lyrics | ✓ | ✓ | ✗ |
| Multi-language vocals | ✓ (8 langs) | ✓ (8 langs) | ✗ |
| Structured composition (intro/verse/chorus/bridge) | Limited | ✓ Full | N/A (streaming) |
| Timestamp-driven arrangement | ✗ | ✓ | ✗ |
| Image-to-music | ✓ | ✓ | ✗ |
| Video-to-music | ✓ | ✓ | ✗ |
| Stem separation / export | ✗ | ✗ | ✗ |
| Negative prompts | ✓ (API only) | ✓ (API only) | ✗ |
| Max duration | 30 sec | ~3 min | Infinite stream |
| Audio quality | 48kHz stereo | 48kHz stereo | 48kHz stereo PCM |

**Major capability gaps vs. Suno:**
- No stem separation (Suno exports up to 12 stems)
- No voice cloning or custom model training
- No audio reference input (Lyria accepts images/PDF/video as mood reference, not audio)
- No song continuation or in-place editing (single-turn generation only)
- Maximum 3 minutes (vs. ~8 minutes for Suno)

---

## SynthID Watermarking

Source: [SynthID deep dive – lyria-3.pro](https://lyria-3.pro/blog/synthid-how-google-watermarks-ai-generated-music)

**Every track generated by any Lyria model is automatically watermarked.** This is not optional and cannot be disabled.

SynthID embeds a digital signature **directly into the audio waveform** — inaudible to humans but detectable by software even after compression, format conversion, and light editing.

**Scope:** Over 10 billion pieces of content watermarked globally as of late 2025. Applied across all Google AI generative modalities: audio (Lyria), images (Imagen), video (Veo), text (Gemini).

**Verification:** In the Gemini app, upload any audio file and ask "Is this AI-generated?" — Gemini scans for SynthID and returns a response.

**Implications for creators:**
- Any distributed Lyria track carries a persistent signal identifying it as AI-generated
- YouTube's Content ID system is designed to integrate with SynthID signals — intended to reduce false copyright strikes
- Relevant for streaming platform audits, copyright disputes
- If you attempt to register a Lyria track with the US Copyright Office, you must disclose AI involvement

**Regulatory context:** Positioned for compliance with EU AI Act Article 50 (AI content disclosure requirement). SynthID is a detection watermark, not a C2PA provenance manifest.

---

## Licensing and Usage Rights

Source: [Google Gemini API Terms](https://ai.google.dev/terms), [RightsDocket – Commercial Use Guide](https://www.rightsdocket.com/insights/google-lyria-3-commercial-use-copyright), [Lyria3app.com](https://www.lyria3app.com/lyria-3-copyright-commercial-use-guide)

| Tier | Commercial Use |
|---|---|
| Gemini app (free) | YouTube-compatible content; royalty-free within Google's ecosystem |
| Paid (AI Plus/Pro/Ultra) | Broader commercial use including ads and marketing |
| API / Vertex AI | Enterprise commercial use explicitly supported |

**Ownership:** Google does not claim ownership of user-generated output. However, purely AI-generated works generally cannot receive US copyright protection without substantial human creative contribution. Greater human input (prompt craft, arrangement decisions, lyrical direction) strengthens potential copyright claims.

---

## Active Litigation Note

As of March 2026, a group of independent artists filed a **118-page class action lawsuit** (US District Court, Northern District of Illinois) against Google, alleging that Lyria 3 was trained on copyrighted recordings from YouTube without permission — "44 million clips and 280,000 hours of music."

The suit alleges: copyright infringement, removal of copyright management information, circumvention of technological access controls, false endorsement (Lanham Act), and Illinois Biometric Information Privacy Act violations.

Google has stated training used materials it has the right to use "under terms of service, partner agreements, and applicable law."

**The lawsuit is ongoing as of April 2026.** This does not affect user rights to generated output but creates legal uncertainty around the underlying model. Source: [Music Business Worldwide](https://www.musicbusinessworldwide.com/indie-artists-sue-google-claiming-it-used-youtubes-own-catalog-to-train-lyria-3-ai-music-tool/)

---

## Strengths and Limitations Summary

### Strengths
- Deep Google ecosystem integration (Gemini, Vids, YouTube, Workspace)
- Lyria RealTime: unique continuous streaming model with no equivalent in the market
- Timestamp-driven structural composition — most precise arrangement control available
- 48kHz stereo audio quality
- SynthID watermarking for regulatory compliance and platform transparency
- Strongest API/enterprise offering (Vertex AI)
- Multimodal inputs: image, video, PDF
- Multi-language, multi-vocal compositions (8 languages)
- Fast generation (~10–20 seconds)

### Limitations
- No stem separation — major gap for producers
- 3-minute maximum (vs. ~8 minutes for Suno)
- No voice cloning or custom model training
- No audio reference input
- Mandatory SynthID watermark (cannot be disabled)
- Single-turn generation only (no in-place editing or extension)
- Active copyright litigation over training data
- Lyria RealTime is instrumental only
