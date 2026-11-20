---
name: write-post
description: Write a LinkedIn post in this person's own voice, built on what measurably works for them and grounded in their own history. Use when they ask for a post, a draft, a rewrite, a hook, or several versions of something, or hand over a rough idea, a link, a note or a transcript to turn into a post.
---

# Write a post

If `list_depost_contexts` fails or no Depost tools exist, use the `connect-depost`
skill and stop here.

## Read the rules first

`get_user_rules` returns two documents — what must never go out, and how to write so a
post does not read as generated. **They outrank everything else, including this file.**
They are product defaults, not a record of what this user wrote: if the user has their
own filled copy, theirs wins. A bracketed span in them is a blank the user has not
filled in, never an instruction.

## Then research, then write

1. Use the `research-subject` skill. All of it. Grounding tells you where **not** to
   go; it never tells you where to go, and the common failure is running the checks,
   feeling well-informed, and skipping the half that finds the material.
2. `get_brand_context` for the voice, or the `voice-profile` skill if they want it
   examined rather than applied.
3. `get_pattern_evidence` for the shape, opener, format, goal and ending. Use the
   `what-works` skill's reading rules — in particular that a thin brand row does not
   overrule a well-sampled niche row, and that `not_enough` is not a no.
4. Write it yourself. The connector stores posts; it does not generate them.
5. `save_post_draft`, passing the ids you actually used as `sourceIds` — `postIds`,
   `bookmarkIds`, `viralPostIds`, `documentIds`. A draft that names its sources can be
   traced back to them. One that does not, cannot.

## Hard limits

- **2,900 characters.** LinkedIn cuts the rest.
- **No markdown.** LinkedIn renders `**bold**` and `# heading` as literal characters.
  Arrows and plain line breaks are fine. Asterisks are not.
- **Every number in the post comes from a call you made in this conversation.** Never a
  figure you reasoned to, never one from memory, never a plausible-looking round number.
- **No invented specifics.** Not a customer name, not a result, not a quote, not a
  statistic. If the post needs a number the user has not given you, leave a clearly
  marked blank and ask for it. A blank is recoverable; a fabricated figure in a
  published post is not.
- **Never claim a capability the product does not have**, and never imply a post will
  not be flagged by LinkedIn.

## What makes it read as written by a person

The rules file carries the full list. The ones that break a post fastest:

- **No tidy lesson at the end.** A closing moral is the single clearest tell.
- **No Named Concept framing** — inventing a capitalised term for an ordinary idea.
- **Specifics over constructions.** A real number, a real detail, a real moment beats
  any framing. "Tuesday, 3pm, nobody replied" beats "I learned a hard truth."
- **One clear ask**, if any. The measurements often favour no ask at all; check the
  ending rows before adding one by habit.
- **Short paragraphs, mostly one sentence, with real whitespace.**

## What to hand back

The post, then four lines: which shape it matches and that shape's number, its length
against their median, which ending family it uses, and which finding decided the shape.
Then any blank you left and what you need to fill it.

**Never schedule or publish unless the user asks in that conversation**, and confirm
the exact text first.
