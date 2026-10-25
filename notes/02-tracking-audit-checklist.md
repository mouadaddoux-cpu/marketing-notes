# 02 · Tracking audit checklist

An audit is not a report — it is an hour of finding out whether the numbers can be trusted at
all. I run this before touching bids or budgets.

## 1. Events

- [ ] List every conversion event in the platform, with its volume for the last 30 days.
- [ ] For each: **what actually fires it** (page load? button? server event?).
- [ ] Check for duplicates: pixel + Conversions API both firing without deduplication.
- [ ] Check for missing low-volume events — a “purchase” counted only when the user returns to the site is invisible.
- [ ] Test one event manually, end to end, and screenshot the platform's confirmation.

## 2. Attribution

- [ ] Write down the attribution window on **each** platform (they differ, and they change).
- [ ] Same conversion, two platforms: compare totals. Two platforms claiming the same sale is normal — someone must decide which one owns it.
- [ ] Check whether platform-reported conversions are being compared to a backend / CRM number. If yes, quantify the gap before blaming media.

## 3. Traffic quality

- [ ] UTM parameters present on every paid link: `utm_source`, `utm_medium`, `utm_campaign`, plus `utm_content` for creative.
- [ ] Naming is lowercase and consistent — `Google` and `google` are two sources in most tools.
- [ ] Check GA4 (or equivalent) for “(not set)” in campaign dimensions. That number is your untagged spend.
- [ ] Bot / invalid traffic: check the platform's own exclusion settings and, if available, one session-quality metric.

## 4. Reporting plumbing

- [ ] One source of truth for spend — usually the platform export, not a manually typed sheet.
- [ ] Currency consistent. Platform currency ≠ billing currency is a classic silent error.
- [ ] Time zone consistent across platform, analytics and spreadsheet.
- [ ] A daily export that lands somewhere (even a Sheets script) — manual pulls rot within two weeks.

## Output of the audit

Three lists, in this order:
1. **Blockers** — things that make the data unusable (broken event, wrong currency, no UTM).
2. **Distortions** — things that bias the numbers (double counting, window mismatch).
3. **Hygiene** — naming, time zones, dashboards.

Nothing gets scaled until list 1 is empty.
