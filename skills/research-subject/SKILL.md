---
name: research-subject
description: Research a LinkedIn subject before writing about it - what this person already published on it and how it did, what they saved as inspiration, and how strong writers in their niche handled it. Use when they name a topic they want to post about, ask whether they have covered something, ask for angles on a subject, want to know what is working on a theme, or ask for examples to model.
---

# Research a subject

Never write first and check afterwards. The checks are cheap and they change the post.

If `list_depost_contexts` fails or no Depost tools exist, use the `connect-depost`
skill and stop here.

## Call these together

Describe the subject as a **phrase**, not one word. One-word queries return
neighbouring topics.

| Question | Call |
| --- | --- |
| What have they published on it, and how did it do? | `search_brand_posts` |
| What did they save from other writers on it? | `search_bookmarks` |
| How do strong writers handle it? | `search_viral_posts` |
| What have they written down about it anywhere? | `search_content_knowledge` |
| What is already in their idea backlog? | `list_saved_ideas` |

## Reading the answers

- **Check the `match` field, not the result count.** Strong or weak. A weak match is a
  neighbouring topic, not the subject. Never build an argument on weak matches without
  saying they are weak.
- **Zero strong matches means untouched** — the clearest new ground there is, and a
  reason to write, not a reason to worry.
- **One or two strong means thin**: go again from a different angle than the one there.
- **Three or more strong means covered**, and the question changes. If those three also
  came in under their typical post, the subject is not what failed — the shape was.
- **An empty answer is a real answer.** Both search tools enforce a relevance floor.
  Report the emptiness. Do not loosen the query until something returns and then
  present it as a match.
- **"Busy" or "unavailable" is not "nothing found."** Say so, or try again.
- **For breadth, change the filters, not the wording.** Two rephrasings of one subject
  return overlapping sets; a different format or hook filter returns a different set.
- **`search_content_knowledge` looks like it replaces the others. It does not** — its
  results carry raw counts and no fair-test multiple. Use it to find out whether
  something exists; use the specific searches to find out how it performed.

## Using other writers' posts

They are reference for **structure, hook and angle**. Never copy their wording, and
never carry their claims or numbers over as this person's own. `list_viral_examples`
answers the narrower question of how a layout is built for an account of a given size
— pass `band` so the examples match.

## Presenting them

A card per post rather than pasted text: author and followers for another writer's,
title and date for theirs, the multiple of that writer's own typical post in bold, the
format and hook, the opening line quoted, and the links — the post, the author's
profile, the avatar, the graphic. The `viral-search` skill's
`references/presenting-posts.md` has the full format. Avatars and graphics are links by
design, not inline pictures.

## What to hand back

Say which of the five you called and which you skipped and why. Then:

- **What they have already said on it**, with how it performed.
- **Which of the three coverage cases you found** — untouched, thin, or covered.
- **Two or three angles**, each naming where it came from.
- **The one thing only this person can say** about the subject. This is usually the
  strongest thing available and by definition has no row in any table.

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
