# Lyric Writing — Craft, Prosody, and Authenticity

Model-agnostic. For writing lyrics that sound human when delivered by any AI music generation tool.

---

## The Core Problem: Why AI Lyrics Sound Fake

The failure is measurable and specific. Computational research ([REFFLY, ACL 2025](https://arxiv.org/html/2307.02146v3)) found that human-written lyrics co-locate stressed syllables with long-duration notes 73.44% of the time. Baseline AI models — including GPT-4 — score below 20%. That is a nearly 4x deficit in the most fundamental unit of singability.

On syllable count accuracy per line, general-purpose LLMs achieve **6.67%** versus **98.33%** for specialized prosody-constrained models ([REFFLY, ACL 2025](https://arxiv.org/html/2307.02146v3)). The model can produce grammatically correct, emotionally coherent sentences that are physically impossible to sing without breaking the melody.

The second failure is register. [Werner (2021), *Corpora*](https://www.euppublishing.com/doi/10.3366/cor.2021.0219) analyzed pop lyrics using multi-dimensional linguistic analysis and found they score at 23.12 on conversational involvement — comparable to personal letters and face-to-face speech. Pop lyrics are "pseudo-dialogical": they carry the intimacy of direct address without being actual speech. The unspecified "you" allows any listener to insert themselves as the addressee. AI lyrics regularly fail this by defaulting to formal or "written" register — correct grammar, complete sentences, connective tissue language — that signals a text, not a voice.

The third failure is abstraction. AI generates statistically probable next words. Statistically probable lyric words are clichés — the most-averaged emotional vocabulary in the training corpus. The result sounds like a greeting card: technically accurate, emotionally empty.

**The three-layer fix:** prosody (stress and syllable count aligned to melody), register (conversational grammar, spoken idiom), specificity (concrete sensory detail instead of emotional abstraction).

---

## Syllable Density and Line Length

### The 4–6 Word Rule

Community testing across multiple AI music platforms converges on a working maximum: **4–6 words per line** for most genres ([HookGenius, February 2026](https://hookgenius.app/learn/fix-suno-rushed-lyrics/)). Ballads and slow songs: 3–5. Fast tempo with rhythmically dense lines: up to 7–8, but only when each word is short (one syllable).

The reason is phrase breath. A musical phrase in most popular song structures spans 2–4 seconds. A 10-word line at normal singing tempo does not fit that phrase — the AI will rush syllables together, compress vowels, or clip consonants.

**Before (too many words):**
> "I remember when we used to walk together down that old road"

**After (fits the phrase):**
> "I remember when we walked that old road"

The revision loses nothing meaningful. The long version has eight words doing the work of five.

### Count Syllables, Not Words

"Beautiful" is one word but three syllables. "Old" is one word and one syllable. Line density is a syllable count problem, not a word count problem. Count beats in the melody, count syllables in the line. They must match or be close.

**Rule:** Write the line, count syllables, tap out the beat. If syllables outnumber beats, cut.

### Stressed Syllables on Downbeats

Natural English speech stress must align with musical stress ([University of Washington linguistics, via REFFLY 2025](https://arxiv.org/html/2307.02146v3)). The word "remember" stresses the second syllable: re-MEM-ber. If the word falls in the line such that "re" lands on the downbeat, the delivery will sound wrong.

Read the line aloud with an exaggerated beat. If you find yourself naturally de-emphasizing a word to fit the meter, rewrite the line until the natural stress falls where the beat is.

### Variable Line Length Signals Authenticity

Human songwriters vary line length — sometimes dramatically. Uniform line length (every line the same number of syllables) sounds written, not sung ([Robin Frederick, songwriting pedagogy](https://robinfrederick.com/)). Mix short punchy lines with extended ones. The asymmetry creates forward motion.

**Before (uniform):**
```
I woke up in the morning light
The coffee cold beside my bed
I watched the ceiling fan go round
I didn't get up, I just stayed instead
```

**After (variable):**
```
I woke up
Coffee cold, ceiling fan
Just stayed
```

The short lines hit harder. The silence around them is part of the lyric.

---

## Prosody: Making Lyrics Singable

Prosody is the alignment of lyric syllable stress with melodic and rhythmic stress ([Pat Pattison, Berklee College of Music](https://online.berklee.edu/courses/songwriting-tools-and-techniques)). Pattison calls it "the single most important concept not only in songwriting but in art — this whole notion of everything works together."

### The Alignment Rule

Stressed syllables belong on metrically strong beats (downbeats, beat 3). Unstressed syllables belong on upbeats and pickup notes. Violating this makes the word feel crammed or awkward, regardless of how good the word is.

Test: put the beat on loop. Say the lyric line over the beat with natural speech rhythm. If you have to distort how you say a word to fit the meter, the line needs to be rewritten.

### Enjambment Creates Forward Motion

Enjambment is when a lyric thought carries past the end of a melodic phrase into the beginning of the next. It disrupts the expectation of closure, pulling the listener forward.

**End-stopped (predictable):**
> "I found your letter in the drawer / It wasn't what I thought before"

**Enjambed (creates momentum):**
> "I found your letter in the drawer, wasn't / sure I should read it at all"

The unexpected break after "wasn't" forces the listener to lean in. It also sounds like speech — people talk this way; they do not naturally end thoughts at regular intervals.

### The Read-Aloud Test

Before submitting lyrics to any AI music model, perform the entire lyric at tempo — out loud, at the speed the song will be sung. Anything that makes you stumble, rush, or distort a word will make the AI stumble too. This is the single most reliable quality test for singability.

### Hyphenation for Key Words

Writing hyphens between syllables signals the AI to stretch each syllable rather than compress the word into a single rhythmic unit ([HookGenius, February 2026](https://hookgenius.app/learn/fix-suno-rushed-lyrics/)):

| Instead of | Write |
|------------|-------|
| `tonight` | `to-night` |
| `forever` | `for-ev-er` |
| `beautiful` | `beau-ti-ful` |
| `remember` | `re-mem-ber` |

Use this on emotionally important words — the word you most want the listener to feel. Do not hyphenate everything; overuse makes it mechanical.

### Punctuation as Performance Direction

In AI lyric delivery, punctuation functions as instruction to the vocalist ([Facebook Suno community guide, March 2026](https://www.facebook.com/groups/1118818620292019/posts/1326242769549602/)):

| Mark | Effect |
|------|--------|
| `,` | Quick breath, line keeps moving |
| `...` | Linger, emotional stretch on the last word |
| `—` | Hard cut or accent, staccato hit |
| `!` | Punch and energy |

**Unpunctuated:**
> "I'm running from the dark and it's getting close"

**Punctuated:**
> "I'm running from the dark — and it's getting close..."

The dash makes "dark" a staccato punch. The ellipsis on "close" stretches the word, letting the implication land. These are performance choices embedded in the text.

---

## Conversational Register vs. Poetic Register

### What Register Means

Register is the level of formality and the type of language being used. Academic register: complete sentences, formal vocabulary, connective tissue words (additionally, furthermore, however, significantly). Conversational register: fragments, contractions, filler words, idiomatic phrasing. Pop lyrics belong to conversational register — specifically what Werner (2021) calls ["pseudo-intimacy"](https://www.euppublishing.com/doi/10.3366/cor.2021.0219): lyrics simulate the grammar of face-to-face speech while being scripted and commercially produced. The simulation has to be convincing. AI lyrics frequently fail this by producing formally correct sentences that no one would say.

### The "Common Parlance" Finding

A widely-referenced community discovery: instructing an AI lyric generator to "write in common parlance" produces dramatically more natural output than "write casually" or "make it emotional" ([r/SunoAI, May 2025, u/Ok_Pound_176](https://www.reddit.com/r/SunoAI/comments/1of8wt9/my_complete_workflow_for_writing_authentic_lyrics/)):

> "The output transformed from robotic and overly structured to something that resembled a person sitting on a porch, sharing their thoughts after a long day."

Complementary instruction: **"Don't perform — confess."** This shifts the writing from declaration to disclosure — the difference between announcing an emotion and admitting one.

### Specific Techniques

**Use contractions.** "I'm" not "I am." "Don't" not "do not." "Can't" not "cannot." The rare exception is when the full form carries stress you want ("I *will* not go back there") — but this should be deliberate and uncommon.

**Use sentence fragments.** Fragments are more natural in speech than in writing. "Quarter past seven. Staring at the door." These are not incomplete sentences; they are observations delivered in the rhythm of thought.

**Include filler words strategically.** "Well, I don't know" is more human than "I don't know." "Just one more time" carries different weight than "one more time." "Maybe" and "kinda" soften certainty the way people actually do when speaking. Use one or two per verse — not every line, which becomes stylized.

**Cut connective tissue words.** "Additionally," "over time," "importantly," "significantly" — these signal AI-generated text ([r/SunoAI community discussion, November 2025](https://www.reddit.com/r/SunoAI/comments/1ov930u/why_does_ai_keep_using_words_like_ghost_hum/)). No human sings "additionally."

**The test:** Read the line out loud. Then ask: would you say this exact sentence to someone sitting across from you at a table? If the answer is no, rewrite it until the answer is yes.

**Before (poetic register):**
> "Through the darkness of my sorrow I have wandered, lost and torn / Seeking comfort in the silence of the memories I've worn"

**After (conversational register):**
> "I've been walking around in it
> Can't explain what I'm looking for
> Your coat's still on the hook by the door"

The second version sounds like something a person would say. The first sounds like something an AI thinks a song should sound like.

---

## Concrete Imagery Over Abstract Emotion

### The Specificity Principle

Specificity creates universality. This is counterintuitive but empirically supported ([Berklee Online, Andrea Stolpe](https://online.berklee.edu/takenote/how-to-use-sensory-language-in-lyrics/)) ([r/Songwriting community insight](https://www.reddit.com/r/Songwriting/comments/1emgv4w/how_do_you_guys_make_your_song_more_showing_and/)). A lyric that names a specific object activates the listener's own memory and sensory system — they supply the emotional resonance from their own experience. A lyric that names the emotion bypasses that system entirely.

**Abstract (tells):**
> "I miss you so much it hurts"

**Specific (shows):**
> "Your jacket's on the chair
> I keep meaning to move it"

The jacket on the chair is more devastating than any declaration of missing someone. The listener fills in the grief. They have seen a jacket on a chair.

### Objects Over Emotions

For every emotional state you want to convey, generate three concrete physical images first. Choose the most unexpected or specific one. Do not name the emotion in the same line as the image.

| Emotion | Weak line | Strong line |
|---------|-----------|-------------|
| Loneliness | "I'm so lonely without you" | "Scrolling your old messages at 4:47 a.m." |
| Loss | "I lost something I can't replace" | "I keep dialing your number just to hear it ring" |
| Happiness | "I was so happy that day" | "I walked out with sunlight on my face" |
| Grief | "My heart is shattered" | "I made two cups of coffee again" |

### Specific Times Over Generic Times

"Midnight" and "3 a.m." are AI defaults — overused to signal emotional intensity. Replace with precise times that nobody would invent ([r/SunoAI, November 2025](https://www.reddit.com/r/SunoAI/comments/1ov930u/why_does_ai_keep_using_words_like_ghost_hum/)):

| Cliché time | Human replacement |
|-------------|-------------------|
| midnight | quarter past seven |
| 3 a.m. | 4:47, dawn, just before shift change |
| closing time | last call, after the lot cleared out |

"Quarter past seven" sounds like something that actually happened. "Midnight" sounds like a song cliché.

### The Imagery Typing System

Three types of images serve different lyric functions ([Jack Righteous, December 2025](https://jackrighteous.com/blogs/ai-writing/how-to-use-imagery-to-make-your-lyrics-hit-harder)):

1. **Visual** (verse): What you see. Grounds the listener in place and time.
   - `"Rain on the windshield"` / `"Your jacket on the chair"` / `"Streetlight through the curtains"`

2. **Action** (movement, energy): What is happening. Creates forward motion.
   - `"You slammed the door and swallowed the words"` / `"I folded your note into the pocket of my coat"`

3. **Sensory depth** (what verse can't show with sight alone): What you hear, smell, touch.
   - `"Your perfume stayed longer than the goodbye"` / `"My hands shook like loose change"` / `"Your voice sounded tired in the dark"`

**Section placement:** Verse — use visual and sensory images to build the world. Chorus — keep imagery simple and universal. Bridge — introduce one new image that reframes the meaning of the whole song.

**Contrast imagery** for emotional tension: the collision of incompatible sensory registers creates unease without stating it.

- Warm light in a cold room
- Loud silence after a quiet apology
- A cheerful song coming from the next apartment

The contrast does the emotional work. Name neither side of it directly.

### The AID Method

For any line that risks becoming a "laundry list" of feelings, apply Action + Image + Detail ([r/SunoAI Workflow, October 2025](https://www.reddit.com/r/SunoAI/comments/1of8wt9/my_complete_workflow_for_writing_authentic_lyrics/)):

Instead of: `"I was sad and lonely"`

Write the scene that makes the listener feel sad and lonely:
- **Action:** "I drove to the store"
- **Image:** "parking lot empty at noon"
- **Detail:** "bought one can of soup, forgot the bread"

Assembled: *"Drove to the store at noon / Parking lot empty / Bought one can of soup"*

The listener infers the sadness and loneliness from the evidence. They feel it rather than being told to feel it.

---

## Rhyme Mechanics

### Perfect Rhyme: Use Sparingly

Perfect rhyme (moon/June, fire/desire) is strongest when it arrives unexpected — usually at the end of a chorus hook. Deploying perfect rhyme on every line of every verse signals a constructed, artificial quality. Real conversational speech doesn't rhyme; lyrics that do throughout sound like they're trying ([Robin Frederick, songwriting pedagogy](https://robinfrederick.com/)).

**Rule:** Perfect rhyme is most powerful at the moments of highest emotional resolution. Reserve it.

### Near-Rhyme for Verses

Near-rhyme (also called slant rhyme or approximate rhyme) uses similar but not identical sounds: *time / mine*, *home / alone*, *light / life*. Near-rhyme carries the rhythmic comfort of rhyme without the mechanical click of completion. It sounds like the way speech organically sounds — almost patterned, not constructed.

**Slant examples:**
- door / floor — too perfect, slightly sing-songy
- door / more — acceptable near-rhyme
- door / before — slant on the vowel, more natural

Use near-rhyme throughout verses. Let perfect rhyme close the chorus.

### Internal Rhyme Over End-Rhyme

Internal rhyme places the rhyme within the line rather than at line endings: "I *find* my way back to what I left *behind*." The rhyme is present; the end of the line is free to be honest rather than forced. This produces a musically satisfying line that does not feel imprisoned by its rhyme scheme.

### The Meaning Test

If the rhyme is driving the word choice instead of the meaning driving the word choice, the rhyme wins and the song loses. The question is: did you write this word because it was the true word, or because you needed a rhyme?

If the rhyme forced a weaker word, cut the rhyme. An honest unrhymed line is better than a dishonest rhymed one. Lack of rhyme can add to conversational quality — "it can sound raw and honest, as if the singer just thought of it on the spot" ([Robin Frederick, songwriting pedagogy](https://robinfrederick.com/)).

### Vary the Rhyme Scheme Verse to Verse

Using the same rhyme scheme (ABAB, AABB) in every verse produces predictability. Human songwriters vary their pattern — sometimes rhyming the second and fourth lines, sometimes the first and third, sometimes letting a whole stanza go unrhymed. Variation signals a mind at work, not a template being filled.

### Assonance and Consonance as Alternatives

Assonance (shared vowel sounds: *rain / day*, *cold / home*) and consonance (shared consonant sounds: *dark / drink*, *still / small*) provide sonic texture without the snap of rhyme. Use these to link lines that don't rhyme end-to-end but still feel sonically connected.

---

## Vernacular and Dialect

### Write in the Vocabulary the Character Would Use

A character who works at a grain elevator does not use the same vocabulary as a character who works in an architecture firm. The vocabulary signals the character's world — and when it is wrong, the listener feels the inauthenticity instantly without being able to name it.

Write a draft, then ask: is this how that person talks? Every phrase that sounds like the writer (not the character) is a phrase to revise.

### Immersion Produces What Imagination Cannot

Proximity to lived experience generates vocabulary that cannot be invented. Phrases, idioms, and rhythms specific to a place or community are only available if someone has actually heard them ([Saving Country Music, interview on proximity and craft](https://savingcountrymusic.com/)):

> "There's little things, turns of phrases, and nuances of a lifestyle that if you're off six, seven hours away in a big city, how do you get to witness that if you're not there?"

For AI-assisted lyric writing, the practical equivalent is: seed the lyrics with specific idiomatic phrases from the world of the song before passing them to any AI tool. The AI will cluster around the idiom you supply. Without the seed, it clusters around statistical average.

### Contractions and Grammatical "Errors" Are Not Mistakes

"I ain't done much healing." "They probably right." "Don't go thinking you can leave." These constructions are not grammatical errors in lyric context — they are authenticity signals. They mark a speaker, not a writer. Strip them out in revision and the song loses its voice.

Keep them. The grammar police do not attend concerts.

### The Patois Finding

Using dialect-specific vocabulary and syntax within lyrics produces genre-authentic delivery from AI music models. This has been specifically documented for genres with strong dialect traditions ([r/SunoAI community, May 2025](https://www.reddit.com/r/SunoAI/comments/1of8wt9/my_complete_workflow_for_writing_authentic_lyrics/)). The AI has been trained on music in those dialects; dialect in the lyric text activates those vocal patterns.

The principle generalizes: the linguistic register of your lyrics tells the model what kind of voice to use. Formal language calls a formal voice. Colloquial language calls a colloquial voice. Write in the dialect of the character, not the dialect of careful prose.

### Do Not Code-Switch Without Narrative Purpose

If a song begins in one vocal register and shifts to another mid-lyric, the listener registers the break as error unless the switch is earned — a character under stress, a reveal, a tonal shift at the bridge that reframes everything. Arbitrary register shifts (casual verse into suddenly formal bridge) read as inconsistency, not contrast.

---

## The Anti-Cliché Reference

AI lyric generators reliably cluster around a specific vocabulary of words associated with emotional intensity in song. These words have been deployed so many times they have lost information density — the listener hears them and feels nothing.

**Community-documented cliché blacklist** ([r/SunoAI, November 2025](https://www.reddit.com/r/SunoAI/comments/1ov930u/why_does_ai_keep_using_words_like_ghost_hum/)) with replacements:

| AI default word | Why it fails | Replace with |
|-----------------|-------------|--------------|
| `ghost` | Metaphorical shorthand for absence; reader supplies nothing | Name what is actually absent: an unwashed mug, a chair facing the wrong way |
| `echoes` | Vague sensory abstraction; signals nothing specific | Describe the actual sound: "your keys hitting the counter," "the furnace kicking on at 2" |
| `shimmer` | Decorative adjective; no sensory content | Name what is shimmering and make it specific: "the creek where the road bends by the mill" |
| `whispers` | Cliché emotional softness | Write what is actually being said quietly, or write the silence itself |
| `neon` | Visual atmosphere shorthand | Describe the actual light: "the sign for Hank's Diner, half the letters out" |
| `shadows` | Generic darkness imagery | Name the specific shadow: "your shape behind the curtain," "the long kind at 5 p.m." |
| `symphony` | Poetic elevation of music; never sounds real | Name the actual sound: three chords, a phone vibrating on a table |
| `embrace` | Physical action as emotional abstract | Write the actual physical contact or its absence |
| `endless` | Hyperbolic modifier with no image behind it | Give it a measurement: "long enough that I stopped counting," "five years of Sundays" |
| `kaleidoscope` | Overwrought visual metaphor | Replace with the specific fragmented experience you mean |
| `cage` | Freedom/captivity metaphor, completely worn out | Write the specific restriction: "the same four walls, the same commute, the same excuse" |
| `velvet` | Luxury texture used decoratively | If you mean soft, say what is soft and why it matters |
| `static` | Sonic metaphor for emotional noise | Name what the interference actually is |
| `midnight` | Default emotional time | Use: quarter past seven, 4:47, shift change, last light |
| `3 a.m.` | Same as midnight | Quarter to five, just before dawn, after the last bus |
| `heart shattered on the floor` | Fully worn metaphor | Write the physical correlate: one plate left on the shelf, the voicemail you won't delete |
| `I was lost and found` | Spiritual cliché with no information | Write the specific moment of disorientation and the specific moment of reorientation |
| `we rise above` | Inspirational closure with no imagery | Write the specific thing that was survived |
| `additionally` | Academic register marker | Delete. Never sing "additionally." |
| `I am contemplating the emotional instability` | Formal register, no one says this | "I don't know what I'm feeling tonight" |

**The replacement rule:** For any banned word or phrase, write the physical, specific thing that the cliché was trying to shorthand. One concrete detail always outperforms any number of atmospheric abstractions.

---

## Lyric Quality Checklist

Run every lyric through this checklist before submitting to any AI music model. These are pass/fail checks, not suggestions.

---

**1. Singability**
Perform the lyrics at full tempo, out loud. If you stumble, rush a word, or strain a phrase, the AI will too. Rewrite any line that trips you up.

*Pass:* Every line can be performed at tempo without distorting any word.
*Fail:* Any line requires cramming syllables or rushing to fit.

---

**2. Conversational**
Pick any three lines at random. Would you say those exact words to someone sitting across from you? Not perform them — say them, in ordinary speech.

*Pass:* All three lines pass the face-to-face test.
*Fail:* Any line sounds written rather than spoken.

---

**3. Specific**
Count the concrete sensory details (named objects, specific times, physical actions, sensory impressions) per verse. Minimum: three per verse.

*Pass:* At least three specific, physical details per verse.
*Fail:* Verses rely on emotional abstractions and generic imagery.

---

**4. Variable**
Count syllables across the lines of the first verse. Are they all the same, or do they vary?

*Pass:* Line lengths vary — at least two lines differ significantly in syllable count.
*Fail:* Every line is approximately the same length.

---

**5. Earned**
For each metaphor or emotional declaration in the chorus, count how many specific evidential details appeared in preceding verses. A chorus that declares grief without establishing it is unearned.

*Pass:* At least three specific details have been established before any emotional declaration.
*Fail:* The chorus announces a feeling the verse never built a case for.

---

**6. Clean**
Scan for words from the AI cliché blacklist: `ghost, shimmer, echoes, neon, whispers, shadows, symphony, embrace, endless, kaleidoscope, cage, velvet, static, midnight, 3 a.m.`

*Pass:* None of these words appear, or any that do appear are used in a specific, non-decorative way that could not be replaced without loss.
*Fail:* One or more appear as atmospheric decoration with no grounding image behind them.

---

**7. Arc**
Read the verse 1 lyric, then the final chorus lyric. Has the emotional weight shifted? The song should end in a different emotional place than it began — not necessarily resolved, but moved.

*Pass:* The emotional intensity, perspective, or understanding has changed by the final chorus.
*Fail:* The first verse and final chorus carry the same emotional weight without development.

---

**8. Point of View**
Identify the grammatical person and character voice of the first line. Check every subsequent section: does POV remain consistent? Any pronoun shift must be narratively motivated (a letter structure, a dialogue, a second character speaking).

*Pass:* Point of view is maintained consistently, or any shift is clearly intentional.
*Fail:* Pronoun shifts occur without narrative justification (I to we, you to they, present to past with no transition).

---

**9. Stress Alignment**
Read the first line of each section aloud, placing exaggerated stress on the beat positions (beat 1, beat 3 in 4/4). Do the naturally stressed syllables of words land on those beats, or do they land off-beat?

*Pass:* Stressed syllables in key words fall on metrically strong positions.
*Fail:* Words are stress-distorted — their natural accent lands on the weak beat.

---

**10. Register Consistency**
Does the lyric maintain its chosen register from beginning to end? If the verse is colloquial, is the chorus also colloquial? If the register is raw and confessional, does the bridge stay in that register rather than suddenly becoming literary?

*Pass:* Register is consistent within each section; any shifts are deliberate and have narrative function.
*Fail:* Academic or formal language intrudes in otherwise conversational sections, or the register shifts arbitrarily between sections.

---

## Prompt Terminology Reference

When submitting lyrics to an AI music model, the style prompt encodes performance and production context. Use the normalized structure:

```
[role] + [genre/style] + [arrangement/instrumentation] + [performance/feel] + [mix/space] + [technical constraints]
```

**Lyric-relevant fields:**

- **[role]:** Who is singing and from what emotional position. Not a genre tag — a person with a specific situation. "A singer who has been awake for three days" produces different delivery than "a singer in grief."
- **[performance/feel]:** Conversational delivery tags. `laid-back`, `loose phrasing`, `off-beat`, `slow-drawled`, `breathy on quiet lines`, `unhurried`. These interact directly with lyric pacing.
- **[technical constraints]:** Exclusion instructions that prevent AI defaults. `no overcompression`, `no radio polish`, `no generic hooks`, `avoid cliché imagery`.

**Important:** Describing the *sound* of a voice produces more reliable results than naming a vocal type. Instead of "raw female vocals," write what raw sounds like: "weathered, airy on quiet lines, pushes chest voice at the peak, audible breath between phrases." The lyric text and the vocal description must agree — a confessional, fragmented lyric asking for a polished performance will fight itself.

---

*Sources: [REFFLY (Zhu et al., ACL 2025)](https://arxiv.org/html/2307.02146v3) | [Werner (2021), Corpora](https://www.euppublishing.com/doi/10.3366/cor.2021.0219) | [Pattison / Berklee Online](https://online.berklee.edu/courses/songwriting-tools-and-techniques) | [Stolpe, Berklee Online Take Note](https://online.berklee.edu/takenote/how-to-use-sensory-language-in-lyrics/) | [Robin Frederick, songwriting pedagogy](https://robinfrederick.com/) | [HookGenius, February 2026](https://hookgenius.app/learn/fix-suno-rushed-lyrics/) | [r/SunoAI community workflows, 2025–2026](https://www.reddit.com/r/SunoAI/comments/1of8wt9/my_complete_workflow_for_writing_authentic_lyrics/) | [Jack Righteous imagery guide, December 2025](https://jackrighteous.com/blogs/ai-writing/how-to-use-imagery-to-make-your-lyrics-hit-harder) | [Facebook Suno community guide v5, March 2026](https://www.facebook.com/groups/1118818620292019/posts/1326242769549602/) | [Alberhasky & Durkee (2024), PLOS ONE](https://pmc.ncbi.nlm.nih.gov/articles/PMC11098490/) | [Larrouy-Maestri et al. (2024), Perspectives on Psychological Science](https://pmc.ncbi.nlm.nih.gov/articles/PMC12231869/) | [Saving Country Music, on immersion in craft](https://savingcountrymusic.com/)*
