# LinkedIn Content Strategist

A content system that works from **your** LinkedIn numbers instead of general advice
about LinkedIn. Six agents and eight workflows, over the Depost AI connector.

LinkedIn's own analytics tell you what a post got. They do not tell you which of your
post shapes beat your own average, which opener works for an account your size, or
which of your subjects you have already worn out. That comparison is what this reads.

Every measurement is a fair test: each post scored against **its own writer's typical
post**, never against other writers. That is what makes a 2,000-follower account and a
200,000-follower account comparable in the same table — and what stops "this got 10,000
likes" from being mistaken for a good post.

## Start here

> *Run my LinkedIn audit.*

One agent, four analyses, one written report: where the account stands, the three
shapes that measurably work, the format that is costing you, how you actually sound,
the gaps, and three things to do next — each with the number behind it. Including the
section most reports leave out: what could not be measured, and why.

## The six agents

Each one takes a job, works on its own, and comes back with a result.

| Agent | What it does |
| --- | --- |
| `linkedin-audit` | The full audit. Performance, evidence, voice and gaps in one report |
| `evidence-analyst` | Which shapes, openers, formats and endings beat your own average, at your follower size and across your niche |
| `performance-review` | What a period actually did, which posts won and lost, the one change worth making |
| `voice-profiler` | How you actually write, derived from your published posts rather than described in adjectives |
| `content-researcher` | What you have already said on a subject, what you saved about it, how strong writers handled it |
| `content-planner` | A plan built from your backlog, your stated priorities and the gaps |

## The eight workflows

The same work, available directly in a conversation — and three things the agents
deliberately leave alone, because they need you in the room.

| Workflow | What it answers |
| --- | --- |
| `what-works` | Which patterns beat your own average, and how your niche compares |
| `performance-review` | What your last 7, 30 or 90 days did |
| `voice-profile` | What your writing is recognisable for |
| `research-subject` | Whether you have covered a subject, and what angles are left |
| `content-plan` | What to post, and when |
| `write-post` | A draft in your voice, in a shape the numbers support, sources recorded |
| `post-critique` | Whether a draft reads as machine-written, and whether its shape works for you |
| `brand-visual` | An image in your own brand look, not a generic template |

Writing, critique and visuals are workflows and not agents on purpose. Each needs your
judgement partway through — a blank only you can fill, a draft you paste in, a picture
you look at — and a job that goes away and comes back is the wrong shape for that.

## Where each part loads

Claude's surfaces load different things, so this is worth knowing before you install.

| | Claude chat | Cowork | Claude Code |
| --- | --- | --- | --- |
| The eight workflows | yes | yes | yes |
| The six agents | no | yes | yes |

Nothing breaks in chat — the workflows cover the same ground, you just drive them in
the conversation instead of handing a job over. Ask *what works on my LinkedIn* rather
than *run the evidence analyst*.

## It needs a Depost account

These are instructions for reading data they do not contain. Without the connector
there is nothing to read, and every part will say so rather than guess. The
measurements come from your own published posts, so a brand with no imported history
has nothing to measure yet.

What is behind the connector: your own posts and their performance, a voice compiled
from your writing, your saved ideas and knowledge base, and a reference library of
146,745 high-performing posts from 660 creators, each scored against its own writer's
typical post.

## Install

**Claude (chat, desktop, mobile)**

1. **Customize → Plugins → Add → Add marketplace**, and paste this repository's URL.
2. Install **LinkedIn Content Strategist**.
3. In Depost AI, open **Settings → MCP**, create a key, and copy the connection URL.
4. Add that URL in Claude as a custom connector.
5. Ask: *what works on my LinkedIn?*

**Claude Code**

```bash
claude plugin marketplace add remoteen/depost-linkedin-strategist
claude plugin install depost-linkedin-strategist@depost
```

Then add the connector:

```bash
claude mcp add --transport http depost "https://api.depost.ai/mcp" \
  --header "Authorization: Bearer YOUR_DEPOST_KEY"
```

Your key starts `dp_mcp_`. Treat it as a password: it does not go in a repository, a
post, or a message to anyone.

## Try it

- *Run my LinkedIn audit.*
- *What am I writing too much of?*
- *Review my last 30 days.*
- *Have I already covered pricing? Give me two angles I have not used.*
- *Draft Thursday's post about the migration, in my voice.*
- *Here is a draft. Does it read as AI, and is this shape right for me?*

## What it does not do

- **Claude never touches LinkedIn.** Depost holds the official LinkedIn connection.
- **Nothing publishes unless you ask for it in that conversation**, and the exact text
  is confirmed first.
- **No profile is scraped.** The data is yours, through your own connection.
- **No invented numbers.** Every figure comes from a live call, or the agent leaves a
  marked blank and asks you for it. Including the figures that are unflattering.

## Data

This sends your prompts and the subjects you ask about to your own Depost AI account
through `api.depost.ai`, and reads back your brand profile, posts, performance, saved
material and the reference library. Drafts and ideas you ask to keep are stored in your
Depost account. The plugin itself stores nothing and contains no credentials.

## Licence

MIT. The instructions are yours to read, fork and change.
