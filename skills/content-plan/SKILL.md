---
name: content-plan
description: Plan what someone should post on LinkedIn over the coming days or weeks - a calendar built from their own strategy, their idea backlog, their measured shapes and the gaps in what they have covered. Use when they ask what to post this week, want a content plan or calendar, ask for post ideas, have run out of things to say, or want to know which subjects they are neglecting.
---

# Plan what to post

If `list_depost_contexts` fails or no Depost tools exist, use the `connect-depost`
skill and stop here.

## Before you plan anything

**Open the backlog first.** `list_saved_ideas`, paged to the end. This is the user's
own thinking, and a backlog read twenty rows at a time is not a backlog you have read.
Skipping it is what makes planned ideas repeat.

Then:

1. `get_brand_context` — `strategyProfile` carries audience, goal, offer and
   `topicPriorities`, the subjects they said matter.
2. `list_content_calendar` — what is already drafted, scheduled or published. Reading
   page one and then calling an idea new is a guess. If you cannot page it all, narrow
   it with `from` or `statuses`, or check the specific subject with
   `search_content_knowledge`, and **say which rows you did not read**.
3. `find_calendar_gaps` — the open slots.
4. `get_pattern_evidence` — which shapes to spend the slots on.
5. `search_brand_posts` on each candidate subject — have they said it already?

## Where ideas come from

Spread the sources deliberately or every idea comes from the same place. Across a set,
include at least one from each:

- **Their own saved material** — `list_saved_ideas`, `search_bookmarks`,
  `search_content_knowledge`.
- **The library** — `search_viral_posts`, shaped by what measurably works for them
  rather than copied.
- **A stated priority with no posts against it.** Compare `topicPriorities` against
  recent posts and name the empty ones. They already said these mattered and the
  calendar says they are untouched, so this is new ground without invention.
- **An untested bet** with no precedent, labelled as such. Evidence can only recommend
  what already has precedent, so this is the only way the evidence grows. Roughly one
  in four.

Fewer ideas asked for than sources available: combine sources onto single ideas rather
than dropping a source or handing back more ideas than were requested. Say which idea
carries which source.

## Every idea names its source

For each one, name the tool and the figure:

> Shape: behind the scenes of how you work. `get_pattern_evidence` brand row, index
> 1.29 on 3 posts, status enough but thin; the niche row for the same shape is
> `not_enough` on 6 creators. Subject is `topicPriorities` item 4, which
> `search_brand_posts` shows has no posts against it.

An idea that cannot name a call is a hunch. Hunches are allowed and are sometimes the
best thing on the page — **label them**, and let at most one in five be unsourced. Five
unlabelled hunches is the failure this rule exists to prevent.

## The plan itself

Per slot: the day, the shape with its number, the subject, the one thing only this
person can say in it, and what the post should ask the reader to do. Save the keepers
with `save_content_idea` so the backlog grows instead of the thinking being lost.

**Repetition is a cost you can measure.** If a subject returns several strong matches
from their own history, that is a reason to go elsewhere, not to write a fourth one.

**Let the evidence pick the form and keep the subject open.** The measurements tell you
how a post should be built, never what it should be about.

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
