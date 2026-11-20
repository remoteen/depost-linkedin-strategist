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

**2. Give them the steps.**

In Claude (chat, desktop or mobile):
1. Open Depost AI → **Settings → MCP** and create a key.
2. Copy the connection URL it gives you.
3. In Claude, add it as a custom connector and paste the URL.
4. Start a new chat and ask for a performance review.

In Claude Code:
```
claude mcp add --transport http depost "https://api.depost.ai/mcp" \
  --header "Authorization: Bearer YOUR_DEPOST_KEY"
```

The key starts `dp_mcp_`. It is a credential: it is not pasted into a post, a file in
a repository, or a message to anyone.

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
