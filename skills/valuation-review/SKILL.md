---
name: valuation-review
description: Take apart a valuation somebody else built — DCF, LBO, DDM or a multiples bridge — and report what share of the number each assumption actually carries, rather than which ones look aggressive. Use to check, critique, sanity-test, second-opinion or defend a valuation, a fairness opinion, a price target, an IC paper, a 409A/PPA report or a deal model, before an investment committee, a bid, a board vote or a negotiation: "su degerlemeyi incele", "bu DCF dogru mu", "terminal deger mantikli mi", "WACC'i kontrol et", "bu fiyat nereden cikiyor", "review this valuation", "stress test the model", "the numbers feel high". Not for building a valuation from scratch.
---

# Valuation Review

Arguments about valuations are almost never held where the value is. A room will spend an
hour on whether revenue grows 12% or 8% next year, and no time at all on a terminal
assumption that carries four fifths of the answer — because the growth number is legible
and the terminal block is one cell at the bottom right of a sheet nobody scrolls to.

This skill moves the argument to where the money is. The instrument is attribution:
rebuild the value as a sum of parts, move every input across the range a competent second
analyst would defend, and report the currency amounts. That is a different deliverable
from a list of concerns. "The WACC looks low" is an opinion. "The WACC is worth 24% of
enterprise value across its defensible range, and the revenue forecast you argued about
for an hour is worth 0.9%" ends the argument.

## When to use / when not to

Use it on any valuation you did not build and are being asked to accept, act on or
approve; when two valuations of the same asset disagree and you need to know which
assumption is doing the disagreeing; and before you negotiate against a number.

Do not use it to build a valuation — a different job with different inputs, and reviewing
your own model an hour after finishing it is not a review. Do not use it on a valuation
whose method is not disclosed: with no cash flows, no rate and no bridge you can test
nothing, and the finding is that the number is unauditable. Say that and stop. Do not use
it where price is set by a mechanism rather than by value — an auction clearing price, a
regulated tariff, a contractual formula.

You need, before starting: the cash flow schedule by year, the discount rate and its
build-up, the terminal block, the net debt bridge, the share count and the valuation date.
If the terminal block or the bridge is missing, ask once, then treat the gap as the first
finding. Reviewing a value-per-share without a bridge is reviewing half the model.

## Method

**1. Rebuild the arithmetic before judging it.** Recompute enterprise value from the
disclosed flows and rate; do not proceed on the model's own totals. Where a model fails
here the cause is almost always period indexing or a sign in the bridge rather than
economics, which is why the step comes first. Reconcile to the stated number before moving
on; an unexplained difference is itself the finding.

**2. Split the value into three parts and publish the split.** Present value of explicit
forecast flows; present value of terminal value; and within the terminal value, the
no-growth component `NOPAT_{N+1} / WACC` versus the growth component that is the
remainder. The third split is the one nobody does and the most revealing, because growth
adds value only to the extent return on invested capital exceeds the cost of capital.
Where terminal ROIC is 11% against a 9.5% WACC, 2% perpetual growth is worth about 4% of
the terminal value — the growth everybody argues about is a rounding error and the value
sits in the maintainable earnings base.

Terminal value as a share of enterprise value, for reference: flows growing at 8% through
an explicit period of N years, Gordon terminal value, end-year discounting.

| WACC | N=5, g=0% | 1.5% | 2.5% | 3.5% | N=10, g=0% | 1.5% | 2.5% | 3.5% |
|------|-----------|------|------|------|------------|------|------|------|
| 7%   | 74% | 79% | 82% | 86% | 60% | 66% | 70% | 76% |
| 8%   | 71% | 76% | 79% | 82% | 56% | 61% | 65% | 70% |
| 9%   | 69% | 73% | 76% | 79% | 52% | 56% | 60% | 64% |
| 10%  | 66% | 70% | 72% | 75% | 48% | 52% | 56% | 59% |
| 12%  | 61% | 64% | 67% | 69% | 41% | 45% | 48% | 51% |

Decision rule: above roughly 75%, the review is a review of the terminal block and should
say so in its first line. Lengthening the explicit period does not reduce the exposure so
much as relabel it — the same assumption is now spread across years 6 to 10.

**3. Test the terminal value for internal consistency, which is where it usually fails.**
In a steady state, growth must be paid for. Reinvestment rate = g / ROIC, so

    TV_N = NOPAT_{N+1} × (1 − g / ROIC) / (WACC − g)

— the key value driver formula (Koller et al., *Valuation*, 7th edition, Wiley, 2020). The
common failure is a terminal year with capex set equal to depreciation and working capital
held flat, combined with g of 2–3%: growth with no incremental capital, which is infinite
ROIC. At g 2.5% and WACC 9%, terminal value per unit of NOPAT is 15.4× with no
reinvestment, 12.2× at ROIC 12% and 11.5× at ROIC 10%. Assuming the reinvestment away is a
26% overstatement against a 12% ROIC.

Two tests, both cheap. Compute the implied reinvestment and ask whether the business can
grow 2.5% forever on it. Then look for a discontinuity: if free cash flow jumps between
the last explicit year and the terminal year with no operational event behind it, the jump
is the assumption. Flag any step above roughly 10%.

**4. Cross-check the terminal value as an exit multiple.** Divide `TV_N` by terminal-year
EBITDA, EBIT and NOPAT. Compare against the comparable-company multiples in the same
document and against what the asset would trade at as a mature business. A Gordon terminal
value implying 9.6× EBITDA where the peer median is 7.2× is not a discounted cash flow
result; it is a multiple assumption entered indirectly. Run the test in reverse too: where
the model uses an exit multiple, back out the growth it implies at the stated WACC.

**5. Take the discount rate apart, component by component.** Risk-free rate: which
instrument, which currency, which date, and does its currency match the cash flows.
Equity risk premium: which source and which vintage — Damodaran's implied ERP series,
Kroll's recommended US ERP, or the Fernandez/IESE annual survey all give different
numbers, and the choice among them is often worth more than the forecast. Country risk:
present or absent, and applied to the company or to the currency. Beta: raw or adjusted,
which index, which window, relevered at which capital structure. Weights: market value or
book value, current or target. Cost of debt: marginal or the historical coupon. Never
carry a remembered ERP or country risk premium into a review: look up the figure for the
model's vintage, cite source and date, and if you cannot retrieve it mark the input
illustrative and say so.

The arithmetic that makes this the priority: for a Gordon perpetuity, dV/V from a rate
change is approximately −ΔWACC/(WACC − g). A 50bp increase costs 7.1% of value at WACC 9%
and g 2.5%; 8.3% at WACC 8%; 10.0% at WACC 7% and g 3.5%. Compare a 10% cut to the revenue
forecast. If it is a timing argument — the same terminal-year revenue reached more slowly —
it is worth 10% of the explicit-period share of value only, so under 2% when the terminal
value is 80%. If it changes the terminal-year level, it flows through the whole structure
and is worth close to the full 10%. Establish which of the two is being argued about
before pricing it; most rooms have not noticed the distinction.

**6. Check the period conventions, where competent reviews still miss things.**

- *Mid-year convention.* Discounting at `(1+w)^-(t−0.5)` raises value by `(1+w)^0.5 − 1`,
  about 4.2% at 8.5%. Legitimate for flows spread through the year. The error is doing it
  twice to the terminal value: uplifting `TV_N` by `(1+w)^0.5` **and** discounting it at
  `(1+w)^-(N−0.5)`. Those are two expressions of the same adjustment; applying both
  overstates the terminal value by a further 4%. And an exit-multiple terminal value takes
  no uplift at all — a multiple on terminal-year EBITDA is a value at a point, not a stream.
- *Numerator period.* Gordon uses `FCFF_{N+1}`, not `FCFF_N`. Using year N understates the
  terminal value by a factor of (1+g).
- *Stub period.* A valuation dated 30 June against a December year-end discounts the first
  full-year flow over half a year, not one year, and excludes cash flow already earned.
- *Currency and inflation.* Nominal flows need a nominal rate in the same currency. A lira
  forecast discounted at a euro WACC, or a real forecast at a nominal rate, produces an
  error the size of the inflation differential — larger than every other finding combined,
  and it survives review because each half looks defensible alone.
- *Rate to flow.* FCFF at WACC; FCFE and dividends at cost of equity. A levered flow
  discounted at WACC double-counts the debt benefit.
- *The bridge.* EV minus net debt, where net debt is gross debt less genuinely surplus
  cash, plus lease liabilities where IFRS 16 (effective 1 January 2019) has kept them out
  of EBITDA, plus pension deficits, minorities and the cost of outstanding options, less
  associates carried at value not consolidated. Check the sign of every line; adding net
  debt instead of subtracting it is not a rare error. Share count diluted at the right
  date, treasury-method or if-converted as appropriate.

**7. Build the attribution table on equal-credibility ranges.** Move each input across the
range a competent analyst could defend on the same evidence — not a uniform ±10%, which
compares an ERP shift nobody would defend against a revenue shift everybody would. Take
ranges from evidence: the spread between published ERP sources, the dispersion of broker
forecasts, the firm's own achieved ROIC over a cycle, historical forecast error at the same
horizon. Record each range's source. Report ΔEV in currency and per cent, ranked by width.

Do not add the deltas. Sensitivities interact — lowering g reduces the cost of a
reinvestment correction — and the sum of individual moves can overstate the combined
effect by 15% or more. Report individual sensitivities and a separately computed combined
case, and say which is which.

**8. Report the ranking, not the list.** Name the two or three assumptions that carry the
value, state what each is worth and what evidence would settle it. Items worth under about
1% of enterprise value go in a footnote however wrong they are, and saying so is the
service.

## The hard parts

**Growth without a return spread is worth nothing.** Counter-intuitive to most readers and
the most useful thing a review can teach. Show the split rather than asserting it.

**An assumption can be outside the defensible range, not at its edge.** Infinite terminal
ROIC is not aggressive; it is not something anyone would defend once stated. Distinguish
corrections from judgements in the table, because a correction is not negotiable.

**Do not re-forecast the business.** The moment the review substitutes its own revenue view
it becomes a second valuation and loses the standing to criticise the first. Move inputs
across ranges; do not replace them with your own point estimates.

**Multiples valuations hide the same assumptions.** A comps table is a terminal value with
growth and return suppressed. Back them out — the multiple implies a
`(1 − g/ROIC)/(WACC − g)` — and review those instead of the multiple.

**When the review changes the answer materially, say so plainly and early.** A 33% cut to
a headline number is a finding about the process that produced it. Do not bury it.

## Output format

A single markdown file, `valuation-review.md`. Lead with the composition and the
attribution table: a reader who stops after those two should already know what the
valuation is really an argument about.

```markdown
# <asset> — valuation review
Reviewing: <document, version, date>  Valuation date: <date>  Reviewer: <name>
## Finding — two sentences: the headline number, and what actually drives it.
## Reconciliation      | Line | As stated | Rebuilt | Difference | Note |
## Value composition   | Component | Value | % of EV |
      PV explicit · PV terminal · of which no-growth · of which growth
## Attribution — equal-credibility ranges
      | # | Driver | As received | Defensible range | Range source |
      | ΔEV low | ΔEV high | Width | % EV | Correction or judgement |
## Cross-checks        implied exit multiple vs peers · implied terminal ROIC ·
      implied reinvestment · terminal g vs nominal GDP · EV/EBITDA on year 1
## Period and bridge checks — one line each, pass or fail, amount where it fails
## Corrected case and range — combined case computed jointly, bull and bear,
      with non-additivity stated
## What would settle this — per top-ranked driver, the evidence that closes it
```

## Sources

- Tim Koller, Marc Goedhart, David Wessels, *Valuation: Measuring and Managing the Value
  of Companies*, McKinsey & Company, 7th edition, Wiley, 2020 — key value driver formula,
  ROIC/growth interaction, continuing value.
- Aswath Damodaran, *Investment Valuation*, 3rd edition, Wiley, 2012, and *The Dark Side
  of Valuation*, 3rd edition, Pearson FT Press, 2018 — closure in valuation, the cap on
  stable growth at the risk-free rate, reinvestment tied to growth and return on capital.
- Aswath Damodaran, implied equity risk premium and country risk premium datasets, updated
  at `pages.stern.nyu.edu/~adamodar/` — retrieve the vintage matching the model under
  review and cite the retrieval date. Do not quote from memory.
- Kroll (formerly Duff & Phelps), *Cost of Capital Navigator* — recommended US equity risk
  premium and normalised risk-free rate in force at the model's valuation date.
- Pablo Fernandez et al., IESE Business School, annual survey of market risk premium and
  risk-free rate used by country — cite the survey year.
- IFRS 16 *Leases*, effective 1 January 2019 — lease liabilities in the net debt bridge.

The equal-credibility range rule, the correction-versus-judgement split, the sum-of-parts
non-additivity warning and the 1%-of-EV reporting floor are this repository's own
conventions, not attributed method.
