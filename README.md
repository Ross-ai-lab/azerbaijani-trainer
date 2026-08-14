# AzeriStep

An Azerbaijani vocabulary trainer with Russian and English question and answer
lanes, published as a free public Cloudflare Pages site. It is useful to anyone
in Azerbaijan learning Azerbaijani from Russian or English.

## Live

| | |
|---|---|
| **Site** | https://azeristep.pages.dev |
| **Source** | https://github.com/Ross-ai-lab/azerbaijani-trainer |
| **Host** | Cloudflare Pages |

## What's in it

**2,222 words across 30 categories** (the full deck).

- **The trainer** runs as an endless practice flow. It supports RU → AZ, AZ → RU, EN → AZ, and AZ → EN. The answer format switches between **Choose** (four options) and **Write** (type it).
- The **A1 → C2** slider is cumulative, so a B1 session includes A1, A2, and B1 words. Progress is saved in the browser.
- **Typing mode** accepts valid synonyms, either half of a slash- or semicolon-separated gloss, and answers typed without Azerbaijani diacritics. When a missing diacritic is accepted, the app shows the correct spelling.
- **Every word has an emoji** used as a memory hook. Pictures may be repeated, approximate, or metaphorical, but they should not contradict the word. All glyphs are checked at card size so unsupported characters do not quietly appear as empty boxes.

**Music** is a local `audio/study-loop.ogg` conversion of [Relaxing Music](https://pixabay.com/music/ambient-relaxing-music-119247/)
by RelaxingTime. Pixabay lists it as ambient, 22:04 long, and free for use under
its [Content License](https://pixabay.com/service/license-summary/). The floating
`Music` button pauses or resumes it.

## "Words you know" counter

The counter tracks words answered correctly at least once across the whole deck,
independent of the current level filter. Moving the slider therefore does not
make the progress number jump backward or forward.

The level filter is cumulative and saves to `localStorage` under `azeri-maxlvl`.
The current counts are:

| Slider at | Words in play |
|---|---:|
| A1 | 319 |
| A2 | 710 |
| B1 | 1,081 |
| B2 | 1,496 |
| C1 | 1,854 |
| C2 | 2,222 |

## Vocabulary and answer handling

The vocabulary set was reviewed before release. Shared Russian glosses are kept
when they represent real Azerbaijani words; the app handles those collisions in
code so a valid answer is not presented as a bad distractor or marked wrong in
typing mode.

The deck uses six cumulative proficiency bands from A1 through C2. Some
Russian-transparent loanwords remain in the upper bands; they are valid
Azerbaijani, even if they are quicker for a Russian speaker to recognise.

## Source and extending the deck

`index.html` is the source of truth for the public page. The public deployment
uses this file directly.

The word pool is defined by one `CATS` array of category objects:
`{id, icon, az, ru, ac, words:[{az, ru, emoji}] | groups}`. Additions should be
checked for spelling, meaning, level, duplicates, and appropriate emoji before
they are released.

## Hosting

The public site is served by Cloudflare Pages.

## Not built yet

- Spoken audio for each word.
- Narrower Russian glosses for the small number of genuine synonym pairs.
- Further curation of transparent loanwords in the upper levels.
