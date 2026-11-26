---
name: brand-visual
description: Make an image for a LinkedIn post in this brand's own look - an infographic, a quote card, a comparison, a chart or a carousel panel. Use when someone asks for a graphic, an image, an infographic or a visual for a post, asks what their post should look like, or wants something drawn in their brand style.
---

# Make the visual

Depost stores and learns the look. You draw it.

If `list_depost_contexts` fails or no Depost tools exist, use the `connect-depost`
skill and stop here. `list_visual_looks` and `get_visual_look` also need the visual
read permission, which is off unless it was switched on when the key was made — a 403
here means a new key, not a missing feature.

## The sequence

1. `get_brand_visual_kit` — palette, type, logo and footer rule. **Never invent a
   palette when a kit exists.** Each piece says what kind of image it handed over:
   `file` is the piece itself; `reference_crop` is a crop of a graphic the brand
   published, so match the look from it but do not treat it as a clean logo file.
2. `list_visual_looks` for the look to draw in, then `get_visual_look`. A look is a
   style, not a finished picture. `derivedStylePrompt` and `negativeRules` are written
   for an image model — follow them as they are.
3. `list_viral_examples` with a `band` matching their audience size, when the question
   is how a layout is built rather than what colour it is. Pass `layoutType` or
   `shape` to narrow it. Those posts' numbers belong to their own writers, never to
   this brand.
4. Draw it.
5. `attach_post_image_from_url` if it is already at a public URL, otherwise
   `get_post_media_upload_instructions`, hand the user the browser upload link if you
   cannot send files, then `confirm_post_media_upload` with the uploadId.

## Reading the looks list

`list_visual_looks` answers in the same five rows the user sees in Depost's own look
picker and **defaults to `mine`** — the looks they confirmed as their own, usually a
short list. The others are `published` (learned from graphics they already posted),
`generated`, `uploads`, and `library` (the shared look library, which is what to
borrow from when they have none of their own yet). Pass `scope` to reach them.

**Report the row the question asked about, never a sum.** Every answer carries `counts`
with one total per row. "How many looks do I have" means `counts.mine`. Adding the rows
together, or paging `all` and counting what you collected, produces a number the user
cannot find anywhere on their screen.

## What makes a LinkedIn image work

- **One idea per image.** A graphic carrying three points carries none.
- **Readable at thumbnail size.** Most people see it small and never tap.
- **The words do the work.** Decide the text first, then the layout. A beautiful card
  with a vague line on it is a wasted slot.
- **Real numbers beat made-up ones**, and a made-up number on a branded card is worse
  than no card. Every figure comes from a call you made in this conversation. If the
  user has not given you the number, leave the space and ask.
- **Their look, not a better one.** Consistency across posts is the point of a kit.

## Carousels

Decide the panel count from the content, not a template. One idea per panel, the first
panel carrying the whole promise, the last carrying the ask. Keep every panel in the
same look.

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
