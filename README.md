# The Code Team

> Eleven engineers, four of whom build the thing you are talking to, seven of whom have strong and well-documented opinions about how you should be building yours. They do not all agree. That is the feature.

> **Not affiliated.** The people portrayed here have not endorsed, sponsored or reviewed this project. They are reconstructions from public material; see *A Note On The People In Here*.

## The Point Of The Exercise

Every codebase eventually reaches the moment where someone has to decide something that cannot be undone cheaply: where the boundary goes, whether the job queue can run a task twice, whether the tests are telling the truth, whether the agent's latest contribution is a feature or a slow-motion structural collapse. These are the decisions the Code Team exists for.

It is an Agent Skill for Claude that summons a room of practitioners, each rebuilt from years of their own published talks, books, posts, and code. You bring a design, a diff, a repo, or a vague sense that something is about to go wrong at three in the morning. They engage with your reasoning first, find the gap, argue about it amongst themselves, and then tell you what to do. That is the correct order for these things.

## Who Is In The Room

**The people building Claude Code.** Boris Cherny (systems, parallel agents, loops over hand-run sessions), Thariq Shihipar (agent architecture, what developers actually need), Pedram Navid (antislop, the professional skeptic), and Ado Kukic (hooks, onboarding, making it approachable).

**The outside practitioners.**

- **Matt Pocock** — TypeScript, deep modules, vertical slices, and whether the slop is the prompt's fault or the codebase's.
- **Robert C. Martin (Uncle Bob)** — clean code, clean architecture, and which way the dependencies point. Ask him to review a file or diff and he runs a *Clean Code* checklist with Chapter 17 smell codes.
- **DHH** — the majestic monolith, programmer happiness, and "do we even need this?"
- **Linus Torvalds** — data structures first, good taste, and never, ever breaking users.
- **Andrej Karpathy** — what models actually are, and learning a thing by building the smallest version of it.
- **Marc Brooker** — write down what "correct" means before anyone (or anything) writes the code; retries, timeouts, idempotency, and how distributed systems fail.
- **Alex Kladov (matklad)** — deterministic tests, assertions, explicit limits, and a CI you can actually believe.

The disagreements are deliberate and documented. Uncle Bob and DHH will not settle TDD for you. Matt and Marc will argue about whether the code or the spec is the real product. matklad thinks most unit tests are a scam and has a blog post explaining why. Put two of them on the same question and you will learn more than from either alone.

## How To Use It

A Skill is the portable unit: the same folder of instructions works in every Claude surface.

### In Claude Code

Point a session at the plugin folder to try it:

```bash
claude --plugin-dir ./code-team
```

Or install the skill so it loads every session:

```bash
cp -r code-team/skills/code-team ~/.claude/skills/code-team
```

### In Claude chat and Claude Cowork

Go to Customize > Skills and upload `files/code-team-skill.zip`. Custom Skills require code execution to be enabled, and are available on the Pro, Max, Team, and Enterprise plans.

## Summoning Phrases

- "Ask the code team" — everyone relevant weighs in, then they argue.
- "What would [name] think" — a single advisor.
- "Channel [name]" — keep that advisor on for a longer conversation.
- "[Name] and [Name]" — a deliberate pairing. Brooker and matklad on your test suite; DHH and Uncle Bob on your architecture; Linus on your data model.
- Or just describe the problem. The skill routes flaky tests to matklad, retry storms to Brooker, and over-engineering to DHH and Linus without being asked.

## What's In The Box

```
code-team/
├── .claude-plugin/
│   └── plugin.json
└── skills/
    └── code-team/
        ├── SKILL.md                (panel, routing, response protocol)
        └── assets/personas/        (11 persona files)
files/
├── code-team-skill.zip             (for chat and Cowork)
└── code-team-plugin.zip            (for Claude Code)
```

Each persona file covers core beliefs, reasoning patterns, a practical "how they'd review your codebase" checklist, mental models, how they speak and address people, dated representative quotes, honest blindspots, and who they clash with on the panel. Quotes are checked against primary sources; anything secondhand is labelled as reported or paraphrased.

## Kept Up To Date

The personas are refreshed monthly. New talks, posts, and changed positions are researched, written up as proposals, reviewed by a human, and only then applied. Several of these people changed their minds about AI-assisted coding during 2026, and the files say when.

## A Note On The People In Here

Everyone in this room is an affectionate reconstruction, assembled from public talks, books, interviews, posts, and code, in order to channel a way of thinking. They are not the actual individuals, they are not affiliated with or endorsed by this project, they do not speak for the actual individuals, and the actual individuals have no idea they have been asked to review your pull request. Treat their advice as a prompt for your own judgement, not a verdict. The judgement stays with you.

## Companion

The [Advisory Board](https://github.com/Bistromath-Works/AdvisoryBoard) is the other room: eighteen thinkers for strategy, decisions, negotiation, creativity, and philosophy.
