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

## Planned contents

Nothing here is built yet. This table is the intended shape, and the daily loop
fills it in one item at a time.

| # | Skill | What it does |
| --- | --- | --- |
| 001 | [valuation-review](skills/valuation-review) | Take apart someone else's valuation and report what is really driving it — usually the terminal assumption and the discount rate, rarely the forecast everybody argued about. |
| 002 | [investment-memo](skills/investment-memo) | Write the case so it can be judged: the thesis, what has to be true, what would falsify it, and the price at which the answer changes. |
| 003 | [assumption-register](skills/assumption-register) | Extract every assumption from a model into a register with its source, its vintage, its owner and the sensitivity of the answer to it. |
| 004 | [diligence-questions](skills/diligence-questions) | Generate the questions worth asking before the model matters, ordered by how much each answer would move the decision. |
| 005 | [comparables-with-honesty](skills/comparables-with-honesty) | Build a comparables set and state plainly why each member is and is not comparable, since a peer set assembled without that is an argument dressed as data. |
| 006 | [capital-structure-review](skills/capital-structure-review) | What the current structure costs, what it constrains, and what would have to change for a different one to be worth the friction. |
| 007 | [scenario-narrative](skills/scenario-narrative) | Turn a scenario table into three stories a board can argue with, rather than three columns nobody reads. |
| 008 | [model-review-checklist](skills/model-review-checklist) | The review pass over a financial model: circularity, sign conventions, period alignment, hardcodes inside formulas, and the checks that should exist and do not. |
| 009 | [client-update-note](skills/client-update-note) | The short regular note that says what changed, what it means and what needs deciding — the deliverable clients actually read. |

## Licence

MIT. See [LICENSE](LICENSE).
