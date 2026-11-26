---
name: connect-depost
description: Set up or troubleshoot the Depost AI connector that every skill in this plugin needs. Use when a Depost tool call fails, when no Depost tools are available, when the user asks how to connect their LinkedIn data, when they see a 401 or 403 from Depost, or when they ask what this plugin needs in order to work.
---

# Connecting Depost

Every other skill here reads the user's own LinkedIn history through the Depost AI
connector. Without it there is no data, and these skills have nothing to work from.

## Check first

Call `list_depost_contexts`. What comes back decides everything:

- **It returns an account and a brand** — connected. Say which brand you are working
  for and carry on with whatever the user asked.
- **No Depost tools exist in this conversation** — not connected. Run *Not connected*
  below.
- **A 401** — the key was deleted or the owner lost access. They need a new
  connection URL from Settings → MCP.
- **A 403 on a specific tool** — the key was created without that permission. They
  create a new key at Settings → MCP with the permission switched on. Name the
  permission the failing tool needed.

## Not connected

Do not apologise and stop. Do this instead, in this order.

**1. Show them what is missing.** This is the useful part, so do it properly. Say
plainly that you can still write a LinkedIn post, and then name what you cannot know
without their account:

- which of their own post shapes beat their own average, and by how much
- which opener, format, goal and ending measurably work for them
- what their last 90 days actually did — impressions, engagement, which post won
- how they sound, derived from their own published posts rather than guessed
- what they have already published on a subject, and how it did
- which of their stated priorities has no post against it yet
- how creators in their niche handle the same shape, each scored against their own
  typical post
- what they saved as inspiration and never used

Then say the honest version: anything you write without those is a guess that reads
well. LinkedIn's own analytics do not score a post against the writer's median by
shape, opener or ending. That comparison is what the connector carries.

**2. Give them the steps, with the links.**

They need a Depost account with LinkedIn connected and the history imported, because
that history is what every measurement is computed from.

1. Sign up at **https://app.depost.ai/signup** — the analysis needs no card.
2. Connect LinkedIn in Depost and let the post history import.
3. Create a key at **https://app.depost.ai/settings/mcp**. It starts `dp_mcp_`, and
   the page hands back a connection URL with the key in it.
4. Connect it:
   - **Claude chat, desktop or mobile:** Settings → Connectors → Add custom connector,
     and paste the connection URL.
   - **Claude Code:**
     ```
     claude mcp add --transport http depost "https://api.depost.ai/mcp" \
       --header "Authorization: Bearer YOUR_DEPOST_KEY"
     ```
5. Start a new chat and ask for a performance review.

The full walkthrough with screenshots is at
**https://depost.ai/blog/connect-claude-to-linkedin** — send them there rather than
retyping it if they want pictures.

**Which permissions to tick.** A new key gets context, content and analytics read plus
drafts write, and those four cover almost everything here. Three are off and worth
knowing about:

- **Visual read** — needed by `brand-visual` for their brand kit and looks.
- **Media write** — needed to attach a generated image to a draft.
- **Publishing** — needed only to schedule or publish. **It is off when the key is
  made.** Say this plainly, because it is the answer to "will this post things without
  me": with the default key it cannot. Recommend leaving it off; everything except
  scheduling still works.

The key is a credential. It is not pasted into a post, a file in a repository, or a
message to anyone. If they share a screenshot of the MCP page, the URL in it contains
the key and they should make a new one.

**3. Say what the account needs.** The measurements come from the user's own published
posts, so a brand with no imported history has nothing to measure yet. They connect
LinkedIn inside Depost, let the history import, and run the analysis once. Until then
every skill here will tell them which rows are thin rather than inventing a number.

## What this plugin never does

Say this whenever someone asks whether it is safe, because the answer is the
architecture, not a reassurance:

- Claude never touches LinkedIn. Depost holds the official LinkedIn connection.
- Nothing is published without the user asking for it in that conversation.
- No profile is scraped. The data is the user's own, through their own connection.

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
