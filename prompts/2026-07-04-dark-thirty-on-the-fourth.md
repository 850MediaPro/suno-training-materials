# Dark-Thirty on the Fourth

Release: July 4, 2026. Follow-up to "Saltwater Sundays." Same Forgotten Coast world, Fourth of July angle: America seen through one salty county, never through anthem language.

Built 2026-07-03 from a 10-agent pipeline: 4 research agents (fresh Suno v5.5 findings, verified local July 4th facts, viral clip mechanics), 3 competing drafts (day-ritual, generations, coming-home), 3-judge panel (anti-AI authenticity, viral mechanics, voice match). Winner: the day-ritual draft, 24/30 across lenses, with the judges' line fixes and the best lines grafted from the losing drafts.

---

## Paste-Ready Prompt

### Style Box (823 chars verified via wc, under the 1,000 ceiling)

```
Weathered male lead vocal, sun-worn rasp, a Gulf Coast working man singing to his hometown crowd from a boat deck at dusk, conversational storytelling verses, chest voice pushed on chorus peaks almost breaking, audible breath, loose behind-the-beat phrasing, rowdy gang vocals answering the hook like a dockside crowd, upbeat southern rock and country-soul anthem, telecaster grit through warm tube amps, greasy slide guitar fills, live drumkit with cracking snare, bass sitting slightly behind the beat, Hammond organ swells, fiddle sawing in on the final chorus, 102 BPM driving groove, celebratory grit, front-porch live session feel, first-take energy, natural timing drift, close-miked vocal forward, warm tape saturation, natural room, full dynamic range, no autotune, no synth pads, no drum machines, no radio polish
```

### Lyrics Box

```
[Vocal: male, weathered mid-baritone, sun-worn rasp, conversational storytelling delivery, loose behind-the-beat phrasing, audible breath between phrases, chest voice pushed on peaks, minimal vibrato, no polish]

[Intro]
*slide guitar over an idling outboard, gulls far off*

[Verse 1]
[Structure: Focused Performance]
First light, I back his trailer down the ramp,
Coffee in a foam cup, air already damp.
Ice rattlin' down the chute at the bait shop,
Loadin' coolers 'til the lids won't drop.
Daddy's boat, but Daddy ain't here,
First Fourth of July in thirty-some years.
His Navy cap still hangin' by the wheel,
Ain't had the heart to, and I doubt I will.

[Chorus]
[Structure: Anthemic Peak]
From the island bridge to Indian Pass,
Raise your boat flag, raise your glass!
{gang vocals: "raise your glass!"}
Lawn chairs in truck beds, babies on hips,
Cold watermelon and salt on our lips.
Every boat in the county anchored offshore,
Waitin' on that first shell's roar,
Keep your Peachtree rooftop shows up north,
We got dark-thirty on the Fourth!
{gang vocals: "dark-thirty on the Fourth!"}

[Verse 2]
[Structure: Focused Performance]
Eleven sharp, golf carts down Gulf Beach Drive,
Squirt guns blazin', whole street soaked alive.
Four straight nights of fireworks, Franklin County style,
Eastpoint to the island, rockets every mile.
Mama's fryin' mullet, grease spittin' loud,
Box fans blowin' on a backyard crowd.
Sparklers in a coffee can out by the door,
Kids beggin' the sun to drop a little more.

[Chorus]
[Structure: Anthemic Peak]
From the island bridge to Indian Pass,
Raise your boat flag, raise your glass!
{gang vocals: "raise your glass!"}
Lawn chairs in truck beds, babies on hips,
Cold watermelon and salt on our lips.
Every boat in the county anchored offshore,
Waitin' on that first shell's roar,
Keep your Peachtree rooftop shows up north,
We got dark-thirty on the Fourth!
{gang vocals: "dark-thirty on the Fourth!"}

[Bridge]
[Structure: Minimalist Breakdown]
[stripped back, voice and one guitar]
We folded his flag in April, thirteen folds tight,
It sits on Mama's mantle, front room, first light.
They trained the boys for D-Day on Carrabelle Beach,
Some came home to shrimp boats... some stayed out of reach.
Now that flag flies off every stern in the bay,
[building intensity]
Reckon that's why we burn the sky this way.

[Final Chorus]
[Structure: Anthemic Peak]
[belting]
From Port St. Joe out to Mexico Beach,
Every dock and jetty within rocket's reach,
Sopchoppy River to the old St. Marks light,
Whole Forgotten Coast is burnin' bright tonight!
[Pause 2s]
First shell cracks the sky at half past nine,
I take his cap down... hold it over this heart of mine.
Fly 'em high, boys, for all he was worth,
It's dark-thirty on the Fourth!
{gang vocals: "dark-thirty on the Fourth!"}
(adlibs: "whoo!, yeah!")

[Outro]
[diminuendo]
Sulfur smoke driftin', boats idlin' home,
Rest easy, old man... your tide runs in me.
Dark-thirty on the Fourth.
[Fade Out]
```

### Exclude Styles field (Advanced Options, more reliable than in-style negatives per 2026 findings)

```
autotune, synth pads, drum machines, EDM, pop polish, choir
```

---

## Variants to A/B

**Variant B, Max Mode conditioning** (community heuristic, see `models/suno/hidden-features.md`): prepend to the Style Box:
`[Is_MAX_MODE: MAX](MAX)[QUALITY: MAX](MAX)[REALISM: MAX](MAX)[REAL_INSTRUMENTS: MAX](MAX)`
Costs 92 chars (total stays under 1,000 at 915) and adds bracket syntax to the style box, which carries bleed risk. The lyrics box is full, which mitigates it. Test 2 to 3 generations against the base prompt. Best fit here: this is exactly the acoustic/rock/country territory where Max Mode reportedly helps.

**Variant C, Persona continuity play.** Make a Persona from the best Saltwater Sundays generation first (three-dot menu, Create, Make Persona, TOGGLE PRIVATE), then generate this song under that Persona. The same recognizable voice singing both songs turns two singles into an artist. Caveat: community reports v5.5 Personas can sound flatter, so A/B Persona vs. non-Persona and keep the better vocal. If the Persona take wins on identity but loses on life, generate without Persona, then Cover with the Persona.

**Variant D, your actual voice.** v5.5 Voices (Pro): record yourself singing 15s to 4min acapella, clean room, no reverb, both low and high register. Your real voice on the track sidesteps the AI-vocal problem entirely. If you use it, DELETE the vocal descriptors from the Style Box and spend those characters on production detail.

---

## Why It Is Built This Way

The Saltwater Sundays engine, reapplied: real place names a stranger could not invent, blue-collar physical detail, AABB couplets with near-rhyme, "we" plus a narrator with stakes, a final chorus that swaps in new places instead of repeating, and an identity payoff line ("your tide runs in me" answering "saltwater runs in my veins" without reusing it).

The Fourth of July angle arrives only through objects and actions: a Navy cap on the wheel, a flag folded thirteen times in April, flags off every stern, hand over heart. Zero abstract patriotism. The bridge does the reframe: personal grief (his flag) zooms out to Camp Gordon Johnston (a quarter-million soldiers trained for amphibious landings at Carrabelle Beach, 1942 to 1946), then lands the song's thesis: "Reckon that's why we burn the sky this way."

The vow turn: Verse 1 "Ain't had the heart to, and I doubt I will" is written as breakable, so the final chorus cap moment lands as a turn instead of a contradiction. That couplet pair is the emotional spine and the 15 to 30 second viral clip.

---

## Local Fact Check (researched 2026-07-03)

| Detail in lyric | Status |
|---|---|
| "dark-thirty" as the fireworks time | Verified: literal phrase in Franklin County event listings (floridasforgottencoast.com, blueparrotsgi.com) |
| SGI water parade, 11 AM, Gulf Beach Drive, squirt guns, golf carts | Verified (collinsvacationrentals.com, sgibeachvacations.com) |
| Four straight nights: Eastpoint 7/1, Carrabelle 7/2, Apalach 7/3, SGI 7/4 | Verified ("Four Days of Freedom Festivities," floridasforgottencoast.com) |
| Camp Gordon Johnston D-Day training at Carrabelle Beach | Verified (campgordonjohnston.com); its parade is in MARCH, so the lyric only references history, no July event |
| Port St. Joe fireworks over St. Joseph Bay; Mexico Beach jetty show; Sopchoppy river fireworks since 1973; St. Marks light | Verified (visitgulf.com, mexicobeach.com, sopchoppy.org, stmarksrefuge.org; St. Marks NWR is doing free entry July 3 to 5, 2026 for America250) |
| Thirteen folds of the flag | Standard military flag-folding ritual |

Traps avoided: Apalachicola's fireworks are July 3, never say otherwise; no Alligator Point organized show exists; Panacea's Blue Crab Festival is fall, not July; Carrabelle's boat parade is December.

---

## Generation Workflow

1. Generate 3 to 6 takes off the base prompt before touching anything. Change ONE variable at a time after that.
2. Pick takes where you can hear breath, loose timing, and the gang vocals answering. Too clean = regenerate.
3. Known v5.5 artifacts to check (community consensus, March to April 2026): harsh sibilance around 3.4 kHz (de-ess in post), style drift and stereo collapse after the 2-minute mark (if the back half goes generic, regenerate or use Extend from the bridge), scattered loud ad-libs. Skip Suno's Remaster; it applies pop compression regardless of genre.
4. Song target length about 3:10 to 3:30. Chorus must land inside the first 45 seconds; if generation gives a long intro, regenerate or trim.
5. If the vocal is right but a section is wrong, fix sections with Replace/Extend in the editor rather than rerolling the whole song.

---

## Release Playbook (July 4, 2026 falls on a Saturday)

1. TONIGHT, July 3: Apalach's fireworks night, the county's biggest crowd is already scrolling at Riverfront Park. Post the pre-game teaser clip tonight.
2. Clip choice: final chorus turn, "First shell cracks the sky at half past nine / I take his cap down... hold it over this heart of mine" into the gang shout. 15 to 30 seconds. Hook audio must hit inside the first 2 seconds of the clip.
3. Burn lyric captions into the clip; most holiday scrolling is sound-off first. Caption formula: "POV: your whole county is in this song" or just "Dark-thirty, y'all."
4. July 4 morning: post the full drop early morning Eastern to catch holiday-morning scroll, second push 7 to 9 PM for Reels prime time, which is exactly when people are anchored waiting on the show.
5. Facebook is the local-share engine: seed to the Forgotten Coast and town groups, the Apalachicola Bay Chamber, SGI groups. Tag the towns. Local anthem spread pattern: locals share out of pride, then chambers and local media amplify (they get free town marketing).
6. Everyone films fireworks at dark-thirty. The song is timestamped to the exact moment thousands of phones are already recording; invite people to use the sound over their own fireworks footage.
7. Skip Sunday, lowest engagement day; save a cut for Monday.
8. Cut 8 to 12 different short clips from the one song and post through the following weeks; a single post is not a strategy.

---

## Research Addendum: What Changed Since the Repo's April 2026 Coverage

Compiled 2026-07-03 via Perplexity plus an independent WebSearch track (two-source rule).

- No new base model. v5.5 (2026-03-26) is current. v6 is rumor only, unverified.
- Advanced Split (2026-06-11, Premier): stems regenerated by the model instead of frequency carving, about 100 instrument choices. Useful for pulling a clean vocal or building performance cutdowns.
- The dedicated Exclude Styles field is more reliable than "no X" inside the Style Box (blakecrosley.com, 2026-03-03). Keep 2 to 4 style-box negatives at the end AND fill the Exclude field.
- Vocal description FIRST in the style box is current consensus ordering; earlier tokens carry more weight (bitwize SKILL.md 2026-01-14, blakecrosley.com 2026-03-03).
- Ad-libs at chorus tails via delivery tags is cited as separating AI-sounding from commercial-grade output (suno.bi, 2026-06-02, unverified percentage claims).
- Tempo lock via redundancy: "102 BPM, driving groove" style pairing holds tempo better than BPM alone (community, unverified).
- iOS 2026-06-04 update: share lyrics from Apple Notes straight into the lyrics form.
- Blog-sourced claims above marked unverified where no official doc confirms; treat as community practice.
