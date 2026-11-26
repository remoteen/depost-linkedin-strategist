---
name: voice-profile
description: Build or check a profile of how someone actually writes on LinkedIn - their sentence rhythm, openers, endings, recurring subjects and the things they never say. Use when they ask you to learn or match their voice, say AI writing does not sound like them, want a style guide for a ghostwriter or teammate, or ask what their writing is recognisable for.
---

# Voice profile

The complaint this answers is the loudest one in the category: the AI sounds generic
because it never learned how you write. A voice derived from someone's own published
posts is a different thing from a voice described in adjectives.

If `list_depost_contexts` fails or no Depost tools exist, use the `connect-depost`
skill and stop here.

## The sequence

1. `get_brand_context` — `defaultBrandVoice` is compiled from their real posts, and
   `persona` carries how they describe themselves. These two disagree often.
2. `get_top_performing_posts` with `metric` engagement and `windowDays` 90 — their best
   posts are the truest sample of the voice that works, not just the voice they have.
3. `search_brand_posts` on two or three of their recurring subjects, to see the voice
   under different pressure.
4. `get_pattern_evidence` with `dimension` `opener` and `ending` for the measured half.

## The disagreements to look for

These are the findings. A profile without them is a description.

- **`persona.preferredPostFormats` is most-used, not best-performing.** Check it
  against `get_content_breakdown`. The gap between what someone writes most and what
  works for them is usually the single most useful sentence in the profile.
- **`communication.ctaStyle` is an intention; `defaultBrandVoice.ctaFamilies` shares
  are measured.** Follow the measurement and say once that the two disagree.
- **Their stated subjects against their published ones.**
  `strategyProfile.topicPriorities` is what they said matters;
  `search_brand_posts` shows what they actually wrote.

## What to hand back

- **Sentence shape**: typical length, paragraph size, how much whitespace, measured
  from the posts you read — not adjectives.
- **How they open**, with two or three real openers quoted from their own posts.
- **How they close**, and which ending family the measurements favour for them.
- **Recurring subjects**, and which stated priority has nothing against it.
- **The tells**: punctuation habits, whether they use emoji, lists, questions, numbers.
- **What they never do.** This is the half that protects the voice. If they have a
  filled rules file, it outranks everything here.

Quote their own sentences as evidence. A voice profile that cannot point at a real
line of theirs is a guess with confidence.

## Keep it theirs

A profile is a description of a person, so it does not get improved. If their posts
break a rule of good writing and still work, the rule is what is wrong. Record it and
move on.

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
