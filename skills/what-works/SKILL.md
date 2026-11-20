---
name: what-works
description: Find what measurably works for this person on LinkedIn - which post shapes, openers, formats, goals and endings beat their own average, and how creators in their niche compare. Use when they ask what kind of post works for them, what to write more or less of, why their reach dropped, which hook or ending to use, whether a format is worth trying, or what the data says about their content.
---

# What measurably works

This is the skill the rest of the plugin leans on. It answers "what should I write"
with a measured number instead of received wisdom.

If `list_depost_contexts` fails or no Depost tools exist, use the `connect-depost`
skill and stop here.

## The call

```
get_pattern_evidence                     # all five dimensions, brand and niche
get_pattern_evidence audienceBand=mine   # the niche narrowed to their follower band
```

Running it with no `dimension` returns all five at once — opener, shape, format, goal
and ending. Pulling only openers is not pulling the evidence.

Run it twice: once at the default `all` band, once at `mine`. A pattern that wins
across every account size and also wins among accounts their size is a far stronger
recommendation than one that only wins at the top. Where the two disagree, their own
band is the one they can actually act on — say both numbers.

## Reading it

Read `references/reading-the-numbers.md` before you report anything. The short
version, and every line of it has cost someone a wrong decision:

- **1.00 is that writer's own normal post.** 1.23 means 23% above their own average.
  Raw counts mostly measure audience size, not quality.
- **Their own row beats the niche row — if it rests on enough posts.** `status:
  enough` fires at three. Check `postsIn` and `restsOnFewPosts`. A thin row of three
  does not overrule a niche row built on hundreds. Read the `notes` field, which names
  any thin row that contradicts a well-sampled one.
- **`not_enough` is not a no.** It is a fact about sample size and says nothing about
  the pattern. Never report it as "this does not work for you". This is the most
  common way a good idea gets killed.
- **Openers are measured for the niche only.** Never imply their own openers were
  tested.
- **Name the population.** Brand rows carry `index`, `postsIn`, `postsOut`, `status`
  and no percentage. Niche rows add `pctBetter`, `creators`, `posts`. Quote what the
  payload holds; never turn `postsIn` into a percentage to round out a sentence.

## What to hand back

Five lines, not a table dump:

1. **Their strongest shape**, with its index, how many of their posts it rests on, and
   whether that is thin.
2. **Their weakest shape that they write often** — the costly one. Cross-check with
   `get_content_breakdown` and with `persona.preferredPostFormats` from
   `get_brand_context`, which is most-used, not best-performing. The format someone
   writes most is frequently the one serving them worst, and naming that is the single
   most useful thing this skill does.
3. **The opener and ending** the niche measures as working, with the population.
4. **One pattern their niche rewards that they have never tried** — a `not_enough` row
   on their side against a well-sampled niche row is exactly this.
5. **What the evidence cannot tell them:** it measures how a post is built, never what
   it is about. Subject is not in these tables. Say so, every time, or they will
   converge on three shapes and go stale while each post still looks fine.
