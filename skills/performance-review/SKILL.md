---
name: performance-review
description: Review how someone's LinkedIn account is actually doing - impressions, engagement, which posts won and lost, what changed since last period, and what to do about it. Use when they ask how their LinkedIn is performing, why reach is down, what their best post was, how this month compares to last, or for a weekly or monthly content report.
---

# Performance review

If `list_depost_contexts` fails or no Depost tools exist, use the `connect-depost`
skill and stop here.

## The sequence

1. `get_performance_summary` with `windowDays` 7, 30 or 90 — the headline movement.
2. `compare_analytics_periods` when they asked a "this month against last" question.
   It returns the per-metric deltas directly, so do not compute them by hand.
3. `get_content_breakdown` with `groupBy` `contentType`, then `format`, then `pillar`
   — what kind of content is carrying the account.
4. `get_top_performing_posts` for the winners, and `list_analytics_posts` to find the
   losers, which are where the lesson usually is.
5. `get_analytics_post_detail` on the single best and single worst post.
6. `get_pattern_evidence` to turn the observation into a recommendation. A review that
   says "video did well" is a description; one that says "video is 1.3 against your
   own average on 11 posts" is a finding.

Definitions, so the numbers match what they see in Depost: engagement is clicks +
reactions + comments + shares + saves. Engagement rate is engagement ÷ impressions
× 100.

## What a good review says

Six lines. A dashboard they already have is not a review.

1. **The movement**, with the window named: impressions and engagement rate against
   the period before.
2. **The post that won**, and the one thing about it that was different.
3. **The post that lost**, same treatment. Do not skip this to be encouraging.
4. **The pattern across them**, from `get_content_breakdown` plus
   `get_pattern_evidence` — not from the two posts alone.
5. **The one change** worth making next week. One, with its number.
6. **What the numbers cannot say.** If reach fell across every shape, the shape is not
   the cause and you should say so rather than inventing a content explanation for a
   distribution change.

## Presenting his own posts

A card per post, not a paragraph. Title, date, then **the comparison first** — against
their own median where you have it, with the baseline named — then impressions,
reactions, comments and shares as context, then the content type, then a link to the
post on LinkedIn and to its image where the payload carries one.

Group into beat-your-average and below-it, ordered by the multiple within each group.
Lead with volume and the reader learns nothing; lead with the comparison and the list
reads itself.

Several analytics tools do not return a preview image yet. When the field is absent,
leave the link out — never guess a URL.

## Honesty rules

- **Every number you state comes from a call you made in this conversation.** Not from
  earlier in the chat, not from memory.
- **Read `total`, not page one.** Every `list_*` tool answers with `page`, `limit`,
  `total` and `hasNext`. Saying "you have 20 posts" when `total` is 340 is wrong.
- **A fall in impressions with flat engagement rate is a distribution story, not a
  content story.** Say which one the data supports.
- **Never present a thin sample as a trend.** Two posts is not a pattern.
- Unflattering numbers are reported, not softened. A review that only finds good news
  is not worth running.
