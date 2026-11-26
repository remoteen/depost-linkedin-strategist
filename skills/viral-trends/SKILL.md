---
name: viral-trends
description: Read what is rising in someone's niche on LinkedIn right now - which subjects, formats and hook types are performing in recent months against earlier ones, and which of them this account could credibly write. Use when asked what is trending, what to write about now, what is working in their industry lately, whether a format is still worth using, or what topics are heating up.
---

# What is rising in the niche

There is no trend tool. This builds a trend read out of dated library searches and the
niche measurements, which works — but has limits you must state rather than hide.

If `list_depost_contexts` fails or no Depost tools exist, use the `connect-depost`
skill and stop here.

## Be honest about what this can and cannot see

Say this once, plainly, in every answer:

- **`search_viral_posts` returns at most 10 posts per call.** A window comparison rests
  on tens of posts, not thousands. It is **directional**, not a measurement. Never
  report a percentage change from it.
- **The niche rows in `get_pattern_evidence` cover one fixed window** that you cannot
  move. They tell you what is working lately, not what changed. Quote the window.
- **The library is what was collected, not all of LinkedIn.** A subject missing from it
  is missing from the library.

A directional read, labelled as one, is useful. The same read presented as a
measurement is the thing that gets someone to bet a month of content on nothing.

## The sequence

1. `get_brand_context` for their `industries` and `strategyProfile`. Every search below
   is filtered to their industry — a trend in another market is noise.

2. **Now against earlier.** Run the same query twice, once recent and once older:

   ```
   search_viral_posts query="<their subject>" industries=[...] publishedAfter="<~3 months ago>" limit=10
   search_viral_posts query="<their subject>" industries=[...] publishedAfter="<~12 months ago>" limit=10
   ```

   Read the difference in what comes back and in the multiples, not in the counts.

3. **Which formats are carrying the niche.** Loop a handful of candidate `formats`
   through a recent-window search and compare the multiples. Then check them against
   `get_pattern_evidence` scope `niche`, which measures formats properly across
   creators and is the stronger evidence wherever the two overlap.

4. **Which openings are landing.** Same approach with `hookTypes`. Openers are measured
   for the niche in `get_pattern_evidence` and never on this brand's own posts, so this
   is where the library earns its place.

5. **Visual trends**, when they care how it looks: `list_viral_examples` with a `band`
   matching their follower size, paging to 25, grouped by `layoutType`.

6. **What they could credibly write.** Cross every candidate against
   `search_brand_posts`. A rising subject they have already covered three times is not
   an opportunity; a rising subject with nothing of theirs against it is.

## What to hand back

1. **Three subjects rising in their niche**, each with the window, how many posts you
   actually saw, and the range of multiples. Labelled directional.
2. **The format carrying it**, with the niche row from `get_pattern_evidence` beside
   the library read — and say which of the two you trust more and why.
3. **The opening type that is landing**, with its population.
4. **What is fading**, if the two windows show it. This is often the more useful half,
   and it is the half people skip.
5. **The one of these this account can credibly write**, naming what only they could
   say in it. A trend they have no standing in is a trend for someone else.
6. **What you could not see.** The sample size, the fixed window, anything the library
   had nothing on.

## The thing to resist

A trend tells you what a crowd is already doing. By the time a subject is measurably
rising in a library, writing it makes someone the twentieth person on it. Say that
where it applies, and keep one suggestion that has no precedent at all — the untested
bet is the only way anyone gets there first.
