# LinkedIn Content Strategist

Eight skills that make Claude work from **your** LinkedIn numbers instead of general
advice about LinkedIn.

LinkedIn's own analytics tell you what a post got. They do not tell you which of your
post shapes beat your own average, which opener works for an account your size, or
which of your subjects you have already worn out. That comparison is what these skills
read, through the Depost AI connector.

Every measurement is a fair test: each post scored against **its own writer's typical
post**, never against other writers. That is what makes a 2,000-follower account and a
200,000-follower account comparable in the same table — and what stops "this got 10,000
likes" from being mistaken for a good post.

## The eight

| Skill | What it answers |
| --- | --- |
| `what-works` | Which shapes, openers, formats and endings beat your own average, and how your niche compares |
| `performance-review` | What your last 7, 30 or 90 days actually did, and the one change worth making |
| `voice-profile` | How you actually write, derived from your published posts rather than described in adjectives |
| `research-subject` | What you have already said on a subject, what you saved about it, how strong writers handled it |
| `content-plan` | A calendar built from your backlog, your stated priorities and the gaps |
| `write-post` | A draft in your voice, in a shape the numbers support, with its sources recorded |
| `post-critique` | Whether a draft reads as machine-written, and whether its shape works for you |
| `brand-visual` | An image in your own brand look, not a generic template |

A ninth, `connect-depost`, handles setup and tells you what it cannot know until you
connect.

## It needs a Depost account

These skills are instructions for reading data they do not contain. Without the
connector there is nothing to read, and they will say so rather than guess. The
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

- *What works on my LinkedIn, and what am I writing too much of?*
- *Review my last 30 days.*
- *Have I already covered pricing? Give me two angles I have not used.*
- *Draft Thursday's post about the migration, in my voice.*
- *Here is a draft. Does it read as AI, and is this shape right for me?*

## What it does not do

- **Claude never touches LinkedIn.** Depost holds the official LinkedIn connection.
- **Nothing publishes unless you ask for it in that conversation**, and the exact text
  is confirmed first.
- **No profile is scraped.** The data is yours, through your own connection.
- **No invented numbers.** Every figure in a draft comes from a live call, or the skill
  leaves a marked blank and asks you for it.

## Data

The skills send your prompts and the subjects you ask about to your own Depost AI
account through `api.depost.ai`, and read back your brand profile, posts, performance,
saved material and the reference library. Drafts and ideas you ask to keep are stored
in your Depost account. The plugin itself stores nothing and contains no credentials.

## Licence

MIT. The instructions are yours to read, fork and change.
