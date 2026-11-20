---
name: post-critique
description: Judge a LinkedIn post before it goes out - whether it reads as machine-written, whether its shape is one that works for this account, and what would have to change. Use when someone pastes a draft and asks if it is good, asks for feedback or a rewrite, asks whether a post sounds like AI, or wants a check before publishing.
---

# Critique a post

The useful version of this is specific and sometimes unwelcome. "Looks great, maybe
tighten the opening" helps nobody.

If `list_depost_contexts` fails or no Depost tools exist, use the `connect-depost`
skill and stop here — a critique without their numbers is an opinion.

## The checks

1. `get_user_rules` — both documents. These outrank this file. Any breach is the
   headline of your answer, not a footnote.
2. `get_pattern_evidence` — which shape is this, and what does that shape do on their
   account and in their niche?
3. `search_brand_posts` on the subject — have they published this already? A near
   duplicate of their own post is the finding, whatever else is true.
4. `get_brand_context` — does it sound like them, measured against
   `defaultBrandVoice`, not against taste.

## What to flag, in this order

**1. Anything the rules forbid.** Name the rule.

**2. Reads as machine-written.** The fastest tells:
- a tidy lesson or moral in the last line
- a capitalised Named Concept invented for an ordinary idea
- markdown that LinkedIn renders literally — `**bold**`, `#` headings, asterisk bullets
- three-item lists where two or four would be natural
- an abstraction where a specific belongs
- an opening that announces the post instead of starting it

**3. A number or claim with nothing behind it.** Any figure, customer result, quote or
statistic in the draft that did not come from a call you made. Ask where it came from;
do not assume it is real and do not quietly keep it.

**4. The shape.** Name it and give its index, `postsIn` and status. If the shape is
weak for them, say so — and then check whether the subject is something only they can
say, because a weak shape never vetoes that. On a real account the personal shapes are
frequently `not_enough`, so "their own row wins" has nothing to win with; say that
rather than reaching for a thin row.

**5. Length and ending.** Against their own median, and against the measured ending
families. A link ending and a sign-up ending are often the weakest options; check
before assuming an ask improves it.

**6. The subject, last.** Covered already, thin, or new ground.

## How to answer

- Lead with the thing that would cost them most.
- Quote the line you mean. A critique that cannot point at a line is a feeling.
- Give the fix as the replacement sentence, not as advice.
- Say what is working, once, specifically, and move on.
- **"This is fine, publish it" is a complete answer** when it is true. Inventing a
  problem to look useful wastes a good post.
- **"Real, but not worth fixing"** is also complete. A rule broken in a way no reader
  would notice, in a post that otherwise lands, is not worth a rewrite.
