---
name: write-human
description: Write or fix a LinkedIn post so it does not read as machine-written - the formatting tells, the structural tells, the vocabulary, and the one test that matters. Works with no account and no data. Use when writing any LinkedIn post, when a draft sounds like AI, when asked to make something sound human or more like a person, or before anything is published.
---

# Write so it does not read as generated

**This works with nothing connected.** No account, no data, no setup. It is craft, and
craft does not need your numbers.

Read `references/reads-as-generated.md` before you write or judge anything. It is the
full standard — every formatting tell, every structural tell, the vocabulary, and the
research behind each one. What follows is the part you must not get wrong.

## The one test

**Could any other person in this field have published this exact post?**

If yes, there is no first-hand material in it, and every other rule is just a symptom.
If no, the post survives most rules being broken.

So before drafting, find the number, the decision, the thing that went wrong, or the
opinion someone could argue with. If there is none, say so and ask for one. A post with
nothing of the writer's own in it is not ready, with or without a model.

## The mechanical tells — fix these every time

**LinkedIn does not render Markdown.** `**bold**` and `-` list dashes paste in as those
characters and sit in the published post. It reads as carelessness, which is worse than
reading as AI.

- Strip every `**` and every `-` list marker. Arrows and plain line breaks are fine.
- Replace em dashes with a full stop, a comma or a bracket.
- Straight quotes, not curly.
- Keep it under **2,900 characters**. LinkedIn cuts the rest.

## The five tells readers actually flag

1. **An opening that sets a scene without making a claim.** Nothing to agree with, so
   nothing to read on for.
2. **Lists of three where two would do.** Three sounds complete. People write two
   things when they have two things.
3. **"It's not X, it's Y."** Sounds like insight, contains none.
4. **A tidy lesson at the end.** The line telling the reader what to conclude.
5. **A question as the last line.** It reads as a request for engagement, and the
   reader can tell.

Measured against each writer's own typical post, the question opener came last of
eleven kinds; a plain claim someone could argue with was the only opener above average.

## Instead

- **One job per post.** A draft with a general observation, a personal story and a tip
  list has three posts hiding in it.
- **End on the last concrete thing that happened**, or the decision made.
- **Say what I did**, rather than what you should do.
- **Let it be lumpy.** Real accounts of real work have uneven parts, because some parts
  mattered more. Equal-length bullets are a tell.
- **No Named Concept.** Naming a thing implies it was tested and taught. If it was not,
  the name is a costume.

## Before it goes out

1. Read it aloud. A sentence that makes you wince is one of the tells.
2. Strip the Markdown, the em dashes, the curly quotes.
3. First line: a claim, or a scene being set?
4. Last line: the point, or a lesson, or a question?
5. Any list of three — does the third item earn its place?
6. Could anyone else in this field have published it?

If six is yes, put something in it that only this person knows. That is the whole
standard in one sentence.

## What this cannot do

Say it plainly rather than implying otherwise. This makes a post read as human. It
cannot tell you:

- whether this **shape** works for this person, because that needs their own posts
  measured against each other
- which **opening** works for an account their size, because that can only be measured
  across many accounts
- what they **already said** about this subject, and how it did

Those need their history. The `linkedin-scorecard` skill does the first from a file they
export themselves; the rest need the Depost connector.

## How to present this

The full standard is the `present-results` skill. The non-negotiables:

- **The finding in the first line.** No preamble, no narrating which tools you are about
  to call.
- **Never read out an internal key.** Every measured row carries a human `label` beside
  its `key` — use the label. "a giveaway with a real asset", never
  `lead_magnet_giveaway`; "not enough posts yet to say", never `not_enough`. Where
  `label` is null, describe the key rather than printing it.
- **One shape for every number:** the comparison in bold, then what it rests on —
  **1.23× their typical post**, from 13 posts. Raw counts come after, as context. Two
  significant figures; `1.289` is false precision.
- **Scannable, not prose.** Short labelled lines or a small table of three to six
  columns. Group before you rank: what beat the average, then what did not.
- **Caveats sit beside the number**, not in a closing paragraph. A caveat at the end is
  a caveat nobody read.
- **One line on what you skipped** and why.
- **End on one next step**, not a menu of four.
