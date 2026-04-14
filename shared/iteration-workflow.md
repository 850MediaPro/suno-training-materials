# Iteration Workflow: v1 → v2 → Remix

How to refine AI-generated songs across multiple generations without wasting credits or losing direction.

---

## Core Principle: Isolate Variables

Every refinement pass should change **one variable at a time**. This is A/B testing. If you change BPM, vocal style, and instrumentation simultaneously, you cannot know which change caused the improvement.

---

## Phase 1: First Pass — Quantity Before Quality

**Goal:** Establish a baseline. Do not optimize yet.

1. Write a prompt using the universal framework: [genre/style] + [arrangement/instrumentation] + [performance/feel] + [mix/space]
2. Generate **3–6 versions** of the same prompt without changing anything
3. Listen to all versions before acting — variance across generations is normal
4. Pick the best 1–2 as your working drafts
5. Do not regenerate endlessly with the same prompt hoping for a different result

> **Why 3–6?** AI generation is probabilistic. One bad result doesn't mean the prompt is wrong. Three bad results in a row means the prompt needs adjustment.

**What to note from v1:**
- Which instruments appeared / didn't appear
- Tempo (does it match your intent?)
- Vocal character (gender, tone, delivery)
- Overall energy arc (does it build, drop, resolve?)
- Any section that works particularly well — note the exact timestamp

---

## Phase 2: Targeted Refinement — One Variable at a Time

**Change priority order (fix in this sequence):**

1. **Genre / style anchor** — if the overall vibe is wrong, fix this first
2. **Instrumentation** — add or remove specific named instruments
3. **Tempo / groove** — adjust BPM or groove descriptors
4. **Vocal style** — gender, register, delivery, timbre
5. **Mix language** — era references, room, analog texture
6. **Exclusions** — add negatives for elements that keep appearing unwanted

**Rule:** Do not touch the lyrics until the sonic identity is locked.

### Testing Checklist Per Iteration
- [ ] Did the target element change in the direction intended?
- [ ] Did anything else change unintentionally?
- [ ] Is this version better, worse, or different-but-equivalent?

---

## Phase 3: Melody Discovery — Gibberish / Mumble First

> Best used when: you have a sonic idea but no lyrics, or you want to discover a melodic phrasing before committing words.

This technique mirrors professional "topline writing" (used by Max Martin and most Scandinavian pop writers). Melody and rhythm come first; lyrics fill the shape.

<!-- model:suno -->
> **model:suno** — Use **Mumble Mode**: In the lyrics box, enter `[Mumble mode] a` (the `a` after the tag is intentional). Suno generates phonetic mumbling that reveals melodic phrasing and rhythm without committing to words.

**Mumble workflow:**
1. Generate with Mumble Mode (or gibberish syllables if Mumble Mode is unavailable)
2. Listen to the mumbled melody — note the rhythm and phrasing shape
3. Identify phonetically interesting sections
4. Write lyrics that match the phonetic shape of the mumble
5. Regenerate with actual lyrics

**Gibberish vocal trick (general):** Fill the lyrics field with phonetic sounds that approximate the rhythm you want (e.g., `da-da-DUM da-da-DUM`) — the model will often align its vocal melody to the phonetic structure of the placeholder.

---

## Phase 4: Section-by-Section Refinement

Once you have a full draft you like overall but want to fix specific sections:

### Extend Trick (Chorus Refinement)

<!-- model:suno -->
> **model:suno** — To force the model to develop a chorus more fully: generate the song up to the pre-chorus, then use **Extend** from that point with only the chorus content in the lyrics box and a chorus-specific style note. This isolates the chorus generation.

**General principle for any model:** Break long prompts into sections and generate each section separately, then assemble.

### Section-by-Section Notes
- Fix the verse first — it sets up the listener's expectation
- Fix the chorus second — it's the most repeated element and the emotional anchor
- Fix the bridge last — it should contrast, so finalize the chorus character before writing the bridge

---

## Phase 5: Cover / Remix Workflows

### What "Cover" Means for AI Models

<!-- model:suno -->
> **model:suno** — Suno's Cover feature uses an uploaded acapella, instrumental, or full track as a seed and expands it into a full song. **Commercial restriction:** Songs created via Suno's in-platform remix/cover feature are treated as joint works and remain non-commercial even for paid subscribers.

**General cover workflow (any model):**
1. Generate a reference/instrumental track that matches your desired groove
2. Export or download the instrumental
3. Write your own lyrics over it outside the AI tool
4. Re-import or reference the instrumental as a seed for a new vocal generation

### Remix for Style Transfer

To take an existing song and remake it in a different genre:
1. Write a new prompt that describes the target genre/style layer + the original song's key structural elements (tempo, chord feel, melodic character)
2. Do NOT upload the original song if you don't own it (copyright risk)
3. Describe the elements you want to preserve in the prompt

---

## Phase 6: Hybrid AI + DAW Workflows

The cleanest final products come from treating AI generation as a starting point, not a finished product.

### Export → Re-record Workflow

```
AI generation (best draft)
  ↓
Export stems (if available) or full mix
  ↓
Import into DAW (Ableton, Logic, FL Studio, Pro Tools)
  ↓
  ├── EQ and compress to taste
  ├── Replace weakest stems with live recordings
  ├── Re-record lead vocals over the AI instrumental
  ├── Layer additional live instruments
  └── Automate dynamics, mix for final delivery
```

<!-- model:suno -->
> **model:suno** — Suno Studio (Premier plan) exports up to 12 stems as audio and MIDI. Use the Remaster tool first to clean up the mix before exporting. Stems are described as "surprisingly clean for AI-generated audio" and usable in professional contexts.

<!-- model:gemini -->
> **model:gemini** — Lyria does not support stem separation. Export the mixed-down track and use a third-party stem separator (Demucs, Stem Separation by Moises) if you need individual elements.

### When to Use a DAW vs. Stay in AI Tools

| Situation | Approach |
|---|---|
| Vocals are slightly off | Re-record over AI instrumental in DAW |
| Overall groove is good but mix is muddy | AI remaster tool first; then DAW EQ |
| One instrument sounds wrong | AI: use stem replacement if available; DAW: replace with sample or live recording |
| Need radio-ready master | Always go to DAW — AI mastering is a starting point, not a final master |
| Lyrics need editing but melody is perfect | DAW: time-stretch / pitch-correct the AI vocal, then write new lyrics to match |

---

## Metadata and Notes to Carry Forward

Keep a running log for each song project. Include:

| Field | What to Record |
|---|---|
| **Prompt v1, v2, ...** | Full prompt text for each generation |
| **BPM** | Confirmed BPM from each version |
| **What worked** | Specific sections or elements that succeeded |
| **What didn't** | Specific elements to remove or change |
| **Variable changed** | The one thing you changed between v1 and v2 |
| **Generation IDs** | Save the song IDs / links in the platform |
| **Target direction** | What you're trying to achieve in the next pass |

A simple text file or note per song is enough. The goal is to never lose a good prompt.

---

## When to Regenerate vs. When to Fix in Post

| Situation | Regenerate | Fix in Post |
|---|---|---|
| Wrong genre entirely | ✓ | |
| Tempo is off by more than 10 BPM | ✓ | |
| Vocals are wrong gender or register | ✓ | |
| Mix is slightly too bright/dark | | ✓ EQ in DAW |
| One word in lyrics is mispronounced | | ✓ Phonetic edit or re-record |
| Intro is weak but chorus is great | ✓ Extend from the chorus | |
| The vibe is 90% right | | ✓ Mix adjustments, stem replacement |
| A specific instrument is out of tune | | ✓ Pitch correction in DAW |
| The hook isn't memorable | ✓ | |
| Dynamics too flat (over-compressed feel) | | ✓ Dynamic compression changes in DAW |

---

## Iteration Loop Summary

```
1. Generate 3–6 versions with initial prompt
2. Select best 1–2 drafts
3. Identify ONE thing to change
4. Generate 3 new versions with that one change
5. Compare new vs. old — did the change work?
6. Repeat until sonic identity is locked
7. If melody is uncertain → Mumble/Gibberish pass
8. Section refinement (extend trick) for weak sections
9. Export → DAW for final mix, re-records, and mastering
10. Log everything
```
