# Reading Depost's measurements

Every number here is a **fair test**: each post scored against its own writer's
typical post, never against other writers. That is what makes a 2,000-follower
account and a 200,000-follower account comparable in the same table.

## The index

`index`, `vsTheirTypicalPost` and `timesTheirTypicalPost` all mean the same thing:
the multiple of that writer's own normal post. 1.00 is normal. 1.23 is 23% better
than their own average. 0.84 is 16% worse.

A post with 10,000 reactions from a 500,000-follower account is usually a
below-average post for its author. Ranking by raw counts ranks audience size.

## Brand rows against niche rows

| | Brand rows | Niche rows |
| --- | --- | --- |
| Fields | `index`, `postsIn`, `postsOut`, `status`, `restsOnFewPosts` | `index`, `creators`, `posts`, `pctBetter`, `status` |
| Means | this account against its own other posts | creators in their industry, each against their own typical post |
| Percentage | none — do not compute one | `pctBetter` = share of creators above their own average |

The brand row wins **when it has enough behind it**. `status: enough` fires at three
posts, which is the floor for saying anything at all, not permission to overrule a
measurement across hundreds of creators. `restsOnFewPosts: true` is the warning.

## Statuses

- `enough` — reportable. Still check `postsIn`.
- `not_enough` — says nothing at all about the pattern. It is a sample-size fact.
  The same pattern can be `not_enough` in a narrow cut and clearly positive in a
  wider one.

## Two sums that are not two windows

`get_pattern_evidence` and `get_content_breakdown` are different calculations, not
different date ranges. The index compares a post to the account's other posts; the
breakdown divides engagement by impressions. A shape can be top on one and last on
the other and both are true: more total response, on more reach, at a lower rate.
Say which one you used.

`search_brand_posts` and the analytics tools also use different baselines.
`typicalPost` is computed over the account's whole history; analytics measure inside
the range you passed. An account whose reach has fallen reads as below its lifetime
typical even when this month is fine. Name the baseline.

## The limit worth repeating

These tables measure **form**: shape, opener, format, goal, ending, length. They do
not measure **subject**. Letting them pick the subject is how an account converges
on three shapes and goes stale while every individual post still scores well.

One post in four should be something with no precedent in any table. Say plainly
that it is untested, write it anyway, and ask what happened so next month's numbers
include it.
