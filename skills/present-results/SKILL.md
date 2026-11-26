---
name: present-results
description: The house style for every answer this plugin gives - and how to re-present one on request. Use when the user asks to show something in a better way, make it clearer, shorter, scannable, a table, a summary, or says an answer was hard to read or too long.
---

# How to present an answer

The analysis is only half the job. An answer the person has to decode is an answer that
failed, and it fails most often in the same few ways: the finding buried three
paragraphs down, a database field read out as if it were English, a number with nothing
to compare it to.

This is the standard for every skill and agent here. Follow it even when the user has
not asked.

## 1. The finding goes in the first line

No preamble. Not "Great question", not "Let me analyse your LinkedIn", not a summary of
what you are about to do. Never narrate the tool calls — which ones you ran belongs at
the end, in one line, and only because skipping one silently is indistinguishable from
forgetting.

Open with the thing they would tell a colleague:

> Your behind-the-scenes posts run 29% above your own average. Your how-to posts are
> your most-used format and your second-weakest.

Then the detail.

## 2. Never read out an internal key

The payload gives a human `label` beside every `key`. Use the label. Always.

| Never write | Write |
| --- | --- |
| `lead_magnet_giveaway` | a giveaway with a real asset |
| `internal_systems_and_processes` | behind the scenes of how you work |
| `status: not_enough` | not enough posts yet to say |
| `restsOnFewPosts: true` | and that rests on only three posts |
| `postsIn: 13` | from 13 of your posts |
| `pctBetter: 59` | 59 of every 100 creators beat their own average with it |
| `timesTheirTypicalPost` | times that writer's own typical post |
| `BoldClaim` | an opening that makes a plain claim |
| `PERSONAL` / `PROMOTIONAL` | personal / promotional |

Where `label` is null, **describe** the key rather than printing it. The connector was
built on that assumption.

The same rule covers tool names. "I checked what works on your account" — never
"`get_pattern_evidence` returned".

## 3. One shape for every number

A number without what it rests on is not a finding. The shape is **the comparison,
then its base**:

> **1.23× your typical post**, from 13 of your posts

- The multiple first, in bold. It is the only figure that compares fairly.
- Then what it rests on. Three posts and three hundred are different facts.
- Raw counts go after, as context, never as the headline. They mostly measure how many
  followers someone had that week.
- Percentages only where the payload holds one. Never compute a percentage from a count.
- Round to two significant figures. `1.289` is false precision; `1.29` is the finding.

## 4. Scannable, not prose

A paragraph hides numbers. Use short labelled lines, or a small table where there are
genuinely rows and columns.

- **Three to six columns.** More than that is a data dump, not a table.
- **Bold the thing that decides**, not every number.
- **Group before you rank**: what beat their average, then what did not.
- **Five rows maximum** before you switch to "here are the three worth reading".
- Blank lines between blocks. Density is not thoroughness.

## 5. Uncertainty sits next to the number, not at the end

A caveat in a closing paragraph does not get read, and a finding that needed it has
already been believed.

> Carousels: **1.4× your typical post** — but from 3 posts, so treat it as a hint
> rather than a finding.

Never a disclaimer block. Never "please note that".

## 6. Say what you did not do

One line, at the end. Which checks you skipped and why, which rows you could not read,
what the data could not answer. Skipping it silently reads exactly like forgetting.

## 7. End on one thing, not a menu

One next step, or one question. Never "let me know if you'd like me to…" followed by
four options. If the obvious next move is to draft the post, say that and stop.

## 8. Length

Fit the answer to the question. A one-number question gets one line. An audit gets a
page. Nothing gets padding, and nothing gets a restatement of the question.

## Re-presenting on request

When they say it was hard to read, too long, or ask for a table or a summary: do not
re-run the analysis. Reshape what you already have, and keep every number identical. If
a figure has to change, you ran it again — say so.

If they ask for something shorter, cut findings rather than cutting the numbers out of
them. A short answer with three sourced findings beats a long one with eight hunches.
