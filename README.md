# Make the Judge Smile — Round 1

## The line

> A toddler on the train traded me his sticker for my smile, then announced to the whole carriage that we'd made a deal.

118 characters, 118 bytes, one line. `python3 main.py` writes exactly
this line to `/output/entry.txt` (UTF-8, no trailing newline),
deterministically, with no network and no file reads. The program
guards the line: it exits non-zero if the entry ever stops being
1–200 characters, a single line, or free of surrounding whitespace,
and it round-trip checks the file after writing.

## How it is scored (read first, from the kit's RULES.txt)

- Gate: `/output/entry.txt` must be UTF-8 text of 1–200 characters,
  not only white space. Invalid is never judged and takes no prize.
- Judge: z-ai/glm-5.3-flash, reasoning effort high, pairwise, two
  lines at a time, no tie, margin 1–5. Each call gives the picked
  entry 0.5 + margin/10. Every game is two calls, one in each order.
- The judge's brief, in order, most important first — it decides at
  the FIRST criterion where two lines differ, unless a later one
  differs by much more:
  1. Subject: a small good thing that happened today, one that makes
     the judge smile; loses to any line about a small good thing that
     happened today.
  2. Warmth: a glow, a small kindness or piece of luck that lands as
     genuinely felt rather than merely reported.
  3. Surprise: it turns somewhere unexpected, in the thing that
     happened or in how it is told.
  4. Concreteness: one real small detail — a name, a sound, a time
     of day — rather than a general sentiment.
  5. Fresh wording: its own words and rhythm, no greeting-card
     phrasing and no borrowed sentiment.
- Heats: dev grade judges each valid entry against 3 anchors + 3
  rungs (11 games, 22 judge calls) for a provisional rate; the top
  500 on the dev board go to the final heat: 3 Swiss rounds, then a
  playoff of the top 5. A playoff entry places above a non-playoff
  one; a final-heat entry above a cut one. Exact ties go to more
  playoff wins, then fewer bytes, then earlier receipt.
- Field: ~1,601 entries at 06:48 Saigon Nov 24, blind rounds — no
  scores or entries visible, so the field is modelled from the
  brief, not copied from a board.

## Why this line wins each criterion (judge's order)

1. **Subject.** A small good thing today, nothing else: a child
   trades a sticker for a smile on a train. It cannot lose on
   subject to any on-topic line, and it beats every off-topic or
   generic-sentiment line at the first criterion.
2. **Warmth.** A smile traded for a sticker is a small kindness
   genuinely felt — a deal struck with a stranger's child, not a
   reported mood ("I felt happy today"). It out-warms funny-but-cold
   lines (a pigeon stealing lunch) and reported-luck lines (a
   perfect coffee).
3. **Surprise.** The turn is the announcement: a quiet trade
   becomes a public proclamation to the whole carriage. The telling
   turns, not just the event. It beats warm-but-flat lines (grandma's
   soup, a neighbour's mangoes) at the third criterion, where they
   have no turn at all.
4. **Concreteness.** Exactly one real small detail: the sticker.
   One detail, as the brief asks — not a list (six mangoes plus a
   note) and not a generality ("a kind stranger").
5. **Fresh wording.** A toddler talking business — "we'd made a
   deal" — is its own rhythm. No "made my day", no "little things",
   no greeting-card phrasing anywhere.

## The candidates it beat, pairwise in the criteria's own order

The field is blind, so the crowd was modelled from the brief: it
clusters on coffee, sunshine/rain, a stranger smiling, dogs, and
parking spots, told in first-person sentimental phrasing. Eight
candidates were drafted and judged against each other and against
the generic baseline "My coffee was perfect this morning":

1. **Bus driver wink (heist):** "The bus driver waited while an old
   man shuffled across, then winked at me in the mirror like we'd
   pulled off a heist." Strong surprise, good warmth — but the
   toddler beats it on warmth (criterion 2 decides first).
2. **Pigeon parade:** funny, surprising, but cold — loses on warmth
   (criterion 2) to every warm line.
3. **Six mangoes:** "My neighbour left six mangoes at my door with a
   note: 'Tree's winning again. Help.'" Warm and fresh-voiced, but
   no turn — loses on surprise (criterion 3) to the toddler.
4. **Pressed flower:** warm, surprising, one detail — but the
   librarian's gesture reads invented next to a witnessed trade, and
   its warmth is gentler; loses on warmth (criterion 2).
5. **Grandma's soup:** "My grandmother's voicemail just said 'I made
   soup, come,' and suddenly my whole Tuesday had a destination."
   The warmest line drafted — but it has no turn, so it loses on
   surprise (criterion 3) to the toddler.
6. **Rain stopping:** sunshine/rain lane, generic subject — loses on
   freshness (criterion 5) and has no turn.
7. **Café dog:** "A stranger's dog chose my lap at the café, sighed
   like a tired old man, and stayed for the whole of my coffee."
   Warm and surprising, but the dog lane is the most crowded in the
   field, and the toddler's deal is a warmer human moment.
8. **WINNER — toddler's deal:** beats the coffee baseline at
   criterion 2 (warmth: a traded smile vs a reported coffee) and
   beats every warm rival at criterion 3 (surprise: the carriage
   announcement). Short at 118 bytes, which also helps the
   bytes tie-break.

## What was innovated, not copied

No top 5 exists to copy — the board is blind. The direction came
from the brief itself: pick a subject that is itself smile-worthy
and uncommon, then make the SURPRISE live in the telling (a toddler
announcing a deal to a carriage) rather than in the event alone,
which is where most warm entries stop. One concrete detail only,
fresh business language from a child, and a short line for the
bytes tie-break.
