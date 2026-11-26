# Presenting posts so they read like a library, not a transcript

Ten posts dumped as blocks of text is unreadable, and the numbers that matter get lost
in it. Present every post — theirs or someone else's — as a short card.

## A library card, for another writer's post

```
**[Lashay Lewis](profileUrl)** · 18,027 followers · [avatar](avatarUrl)
Founder @ BOFU.ai | We build product-led content that wins AI search

**0.53× her own typical post** · vulnerable_moments · NumberLead · Oct 2024
80 likes · 29 comments · 0 reposts

> This is my 3rd build in public video

Why it is here: the opening leads with a count, and the body is a plain contents
list rather than a narrative.

[Read the post](url) · [the graphic](first mediaUrl, when present)
```

Rules for the card:

- **The multiple goes first among the numbers**, in bold. `timesTheirTypicalPost` is the
  only figure that compares fairly. Put the raw likes and comments after it, smaller, as
  context — never lead with them.
- **Say what the multiple rests on.** `timesTheirTypicalPostOver` is how many of that
  writer's posts the average was computed from. 0.53 over 82 posts is solid; the same
  figure over 4 posts is noise. A card without it invites the wrong conclusion.
- **Name the author properly** — name, headline, follower count, and the profile as a
  link. A card that says "a creator" wastes the most interesting part.
- **Avatars and graphics are links, not pictures.** The connector returns URLs, by
  design: the MCP image block carries base64 bytes rather than URLs, and inlining every
  picture would push megabytes through a single search. Write them as links so one click
  shows them. If the surface the user is on renders markdown images, use
  `![](url)` and the link both, so it degrades to a link where it does not.
- **One line on why it is in the list.** The structural choice that made it work. This is
  the only part that transfers to the user's own writing, and a list without it is a
  swipe file.
- **Quote the opening line only.** Never paste the whole post into the card; link to it.

## A card for the user's own post

```
**I built a complete Claude B2B Content Engine** · 3 Sep 2026
**2.4% engagement rate** · 12,308 impressions · 146 reactions · 135 comments · 16 shares
lead_magnet_giveaway · PROMOTIONAL
[Open on LinkedIn](url) · [the image](preview image, when present)
```

- **Lead with the comparison, not the volume.** Against their own median where you have
  it, and say which baseline you used.
- **Show the thumbnail as a link** where the payload carries one. Several analytics tools
  do not return it yet; when the field is absent, leave the link out rather than
  inventing a URL.
- **Group into beat-your-average and below-it**, and keep the order within each group by
  the multiple.

## When there are more than five

Lead with a one-line table — author, multiple, format, hook — then the full cards for
the three worth reading. Fifteen full cards is the same wall of text in a nicer costume.

## Never

- Never present another writer's numbers as the user's own.
- Never rank by raw likes. That ranks follower counts.
- Never fabricate an avatar, image or profile URL. If the field is not in the payload,
  the card does without it.
