# 03 · The five KPIs, and how each one lies

Every metric below is recomputed from totals, never averaged across rows. Averaging averages is
the single most common reporting error I see.

| KPI | Formula | How it lies |
|---|---|---|
| **Spend** | Σ spend | Currency and time zone. Also “spend” vs “billed” — VAT and platform fees live in between. |
| **Conversions** | Σ conversions | Attribution window, duplicates (pixel + API), and events that only fire on a returning visit. |
| **CTR** | Σ clicks ÷ Σ impressions × 100 | Impression counting differs by placement; in-feed “views” inflate the denominator and depress CTR. |
| **CPC** | Σ spend ÷ Σ clicks | Cheap clicks from low-intent placements look excellent and convert at 0. A low CPC is not a result. |
| **Conversion rate** | Σ conversions ÷ Σ clicks × 100 | The denominator is clicks, not sessions. Bots, double clicks and redirects all sit in it. |

## The three rules that keep a report honest

1. **Recompute from raw totals.** If a dashboard averages a column of daily CTRs, it is already wrong.
2. **Every rate needs its denominator visible.** Conversion rate without the click count is a decoration.
3. **Compare against a number you chose in advance.** A target cost per result agreed before launch, not a benchmark copy-pasted from a blog.

## A worked example (bundled sample dataset)

Six campaigns, four weeks, 24 rows:

| Spend | Conversions | CTR | CPC | Conv. rate |
|---|---|---|---|---|
| $1,827.00 | 342 | 1.85% | $0.30 | 5.58% |

Impressions 331,297 · clicks 6,129. Every figure above is derived from those two totals plus
spend and conversions — which is exactly what the [MOUAD dashboard](https://mouadaddoux-cpu.github.io/mouad-analytics/dashboard.html)
computes in the browser from a dropped CSV.
