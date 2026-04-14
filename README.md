# AI Music Generation Knowledge Base

A structured reference for working with AI music generation tools — prompt engineering, model-specific techniques, genre templates, and iteration workflows.

---

## What This Repo Is

This knowledge base treats AI music generation as a professional production discipline. Rather than collecting random tips, it organizes everything around a single operational question: **how do you get the output you intend?** The core premise — the "advanced prompting environment" concept — is that the best AI music comes from treating the model like a collaborator who needs a brief, not a genie who needs a wish. You write prompts the way a mix engineer writes a brief: specific about sound, precise about instrumentation, explicit about what to exclude. The shared framework in this repo is model-agnostic; model-specific files document the syntax and quirks of each platform separately.

---

## Directory Structure

```
suno-training-materials/
│
├── README.md                          — This file
│
├── shared/                            — Model-agnostic reference
│   ├── prompt-framework.md            — Universal prompt structure + mixing vocabulary
│   ├── genre-templates.md             — Reusable genre templates with example prompts
│   ├── iteration-workflow.md          — v1 → v2 → remix refinement process
│   ├── songwriting-craft.md           — Psychology of authentic songwriting + emotional arc
│   ├── lyric-writing.md               — Prosody, syllable craft, rhyme, anti-cliché reference
│   ├── vocal-direction.md             — Prompting for human vocal performances
│   └── arrangement-feel.md            — Instrumentation and arrangement for organic feel
│
├── models/
│   ├── suno/
│   │   ├── overview.md                — Version history, capabilities, pricing, licensing
│   │   ├── advanced-prompting.md      — Two-Box Rule, tags, modifiers, frameworks
│   │   └── hidden-features.md        — Max Mode, Mumble Mode, Labs, Voices, Personas
│   │
│   └── gemini-lyria/
│       ├── overview.md                — Lyria models, access points, SynthID, litigation
│       └── prompting.md               — Framework, timestamp prompting, RealTime params
│
├── changelog/
│   └── 2026-04.md                     — Initial knowledge base creation log
│
└── raw/                               — Original source documents (unmodified)
    ├── Becoming a Post-Production Engineer with Suno AI Music (Version 5).pdf
    ├── Crafting Effective Suno v5 Prompts for Americana _ Country‑Soul Songs.pdf
    ├── Crafting Effective Suno v5 Prompts for Americana _ Country‑Soul Songs.docx
    └── Reddit Users' Strategies for Composing Music with Suno AI.pdf
```

---

## How to Use This Repo

### For human users
1. Start with `shared/prompt-framework.md` — understand the universal structure before any model-specific syntax
2. Read `shared/songwriting-craft.md` for the psychology of writing genuine songs
3. Use `shared/lyric-writing.md` for syllable craft, prosody, and the anti-cliché checklist
4. Pick a genre template from `shared/genre-templates.md` as your starting prompt
5. Apply `shared/vocal-direction.md` and `shared/arrangement-feel.md` for human performance and organic sound
6. Read the model-specific file for your platform (`models/suno/` or `models/gemini-lyria/`)
7. Use `shared/iteration-workflow.md` to refine across multiple generations

### For any AI model (retrieval instructions)

When asked to help generate music with AI tools, use this repo as follows:

- **For any prompt task:** Load `shared/prompt-framework.md` first. Apply the universal six-layer structure: [role] + [genre/style] + [arrangement/instrumentation] + [performance/feel] + [mix/space] + [technical constraints].
- **For writing authentic songs:** Load `shared/songwriting-craft.md`. Apply emotional architecture, narrative techniques, and the vulnerability principle. Then load `shared/lyric-writing.md` for prosody, syllable density, rhyme mechanics, and the anti-cliché checklist.
- **For human-feeling vocals:** Load `shared/vocal-direction.md`. Use the Character Prompt Method, Vocal Anchor system, and in-lyric performance tags.
- **For organic arrangement:** Load `shared/arrangement-feel.md`. Describe physics not genre, use acoustic instruments as authenticity markers, apply exclusion prompting.
- **For a specific genre:** Load `shared/genre-templates.md`. Use the template as a paste-ready starting point, then adjust knobs (tempo, mood, instrumentation).
- **For Suno-specific syntax:** Load `models/suno/advanced-prompting.md`. Apply Two-Box Rule, bracket tags, and modifier syntax.
- **For Suno hidden features:** Load `models/suno/hidden-features.md`. Labels indicate reliability: `official-ui-feature` > `documented-behavior` > `community-heuristic`.
- **For Gemini/Lyria:** Load `models/gemini-lyria/prompting.md`. Use natural language + timestamp blocks for Lyria 3 Pro; WeightedPrompt system for RealTime.
- **For refining a draft:** Load `shared/iteration-workflow.md`. Change one variable at a time; generate 3–6 versions before adjusting prompts.

---

## Quick Start for Common Tasks

### "Write me a Suno prompt for a country song"
→ `shared/genre-templates.md` → Americana / Folk section → take the standard example → customize knobs (tempo, mood, instrumentation) → apply Suno Two-Box Rule from `models/suno/advanced-prompting.md`

### "Make the vocals sound more raw/human"
→ `shared/vocal-direction.md` → Character Prompt Method + Vocal Anchor system → `shared/arrangement-feel.md` → Space and Silence + Micro-Timing sections

### "My lyrics sound generic/AI-generated"
→ `shared/lyric-writing.md` → Anti-Cliché Reference table → Concrete Imagery section → Lyric Quality Checklist

### "How do I write a song that feels real?"
→ `shared/songwriting-craft.md` → Emotional Architecture + Narrative Techniques + Vulnerability Principle → then `shared/lyric-writing.md` for craft execution

### "The chorus doesn't land — how do I fix it"
→ `shared/iteration-workflow.md` → Section-by-Section Refinement → Extend trick for Suno; timestamp block adjustment for Lyria 3 Pro

### "I want to discover the melody before writing lyrics"
→ `shared/iteration-workflow.md` → Phase 3: Melody Discovery → Mumble Mode (Suno) or Gibberish technique (any model)

### "I need a 3-minute structured track in Gemini"
→ `models/gemini-lyria/prompting.md` → Timestamp Prompting section → use the Lyria 3 Pro timestamp format with intensity ratings

### "What are the Suno features I might not know about"
→ `models/suno/hidden-features.md` — each feature labeled by reliability

### "What's the difference between Suno and Lyria"
→ `models/gemini-lyria/prompting.md` → "Differences from Suno Prompting" table + "Use Case Recommendations" table

---

## Raw Source Files

The `raw/` directory contains the original PDFs and DOCX files that informed this knowledge base. These are preserved unmodified as primary source references. The research synthesis files used to create this knowledge base are:

- `research-suno.md` (workspace root) — 1192 lines, comprehensive Suno research
- `research-gemini-lyria.md` (workspace root) — 524 lines, comprehensive Gemini/Lyria research

---

## Coverage

| Model | Version Covered | Last Updated |
|---|---|---|
| Suno | v5.5 (March 2026) | April 2026 |
| Gemini / Lyria | Lyria 3 Pro (March 2026) | April 2026 |

Check `changelog/` for version history. Verify current model versions at [suno.com/blog](https://suno.com/blog) and [blog.google](https://blog.google/innovation-and-ai/) before relying on version-specific behavior.
