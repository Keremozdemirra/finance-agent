# finance-agent

Agents and skills for financial advisory work.

Financial advice fails in two directions. Either the model is
sophisticated and the assumptions behind it were never argued, or the judgement
is sound and the arithmetic quietly does not hold. Both look convincing in a
meeting.

This repository holds the agents and skills for closing that gap: reviewing a
valuation for what is actually driving the answer, writing an investment case
that states what would make it wrong, and running the diligence questions that
are worth asking before the number matters.

The calculation engines live in `analyst-toolkit`. This repository is the
judgement layer on top of them.

## What this is not

It is not investment advice and produces none. Everything here is
analysis for someone else to decide on.

It does not implement valuation mathematics — `analyst-toolkit` does, and where
these skills need a number they call it.

It does not have access to market data. Every figure has to arrive with a source
and a date.

## How to use this

These are skills for Claude, not a command-line tool. There is nothing to
install and nothing to import — you describe the work and the matching skill
fires on its own.

**In Claude Code or Cowork**, once the skills are on your machine:

```bash
bash ~/Desktop/agent/_setup/sync-skills.sh
```

That clones every agent repository and links its `skills/` into `~/.claude/skills`,
so they are available in every session and every folder. Re-run it whenever the
daily loop ships something new — it pulls rather than re-clones.

Then simply ask. Each skill's `description` frontmatter is written to match how
the request actually gets phrased, in English or Turkish, so you do not name the
skill and generally should not have to think about which one applies.

**If nothing fires**, that is a defect in the skill rather than in how you
asked. The description was written for the wrong phrasing. Say what you asked
and what you expected, and it gets fixed — that feedback is more valuable than
working around it.

**What is actually built** is listed under Contents below and in the Done
section of [BACKLOG.md](BACKLOG.md). Everything under Queue is planned and does
not exist yet.

## Layout

```
agents/
  <name>.md           one specialist, its brief and its boundaries
skills/
  <name>/
    SKILL.md          the instruction, with triggering description frontmatter
    scripts/          only where deterministic code beats instruction
examples/
  <name>/             worked example on real input, with the output committed
```

## Roadmap

See [BACKLOG.md](BACKLOG.md). The first unchecked item is the one being built.

## Contents

| Skill | What it does |
| --- | --- |
| [valuation-review](skills/valuation-review) | Take apart someone else's valuation and report what is really driving it. |

Everything still under Queue in [BACKLOG.md](BACKLOG.md) does not exist
yet. The daily loop builds one item a day.
## Licence

MIT. See [LICENSE](LICENSE).
