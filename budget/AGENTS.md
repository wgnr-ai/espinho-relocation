# `budget/` — Financial planning and cost tracking

## Purpose

The `budget/` folder holds the financial planning, cost projections, and currency tracking (USD↔EUR) for the Espinho relocation project. Files in this folder document the expected move costs, ongoing cost-of-living differences, exchange-rate assumptions, and the financial case for the relocation decision.

This is one of 4 ungoverned peer folders in the project (per the 2026-06-17 DOX audit). The 2 ungoverned findings were `budget/` and `research/`; this AGENTS.md closes the governance gap for `budget/`.

## Ownership

- **Owner:** Wagner dos Santos (the Principal)
- **Active maintenance obligation:** none on a regular cadence; updated when financial assumptions change or when major cost categories need to be revised
- **Custodial obligation:** quarterly review during the relocation planning window (active until Jan 2027); semi-annual after that

## Local Contracts

### File naming
- Format: `YYYY-MM-DD-<topic>.md` (date prefix, ISO 8601)
- Examples: `2026-05-27-initial-relocation-budget.md`, `2026-08-15-cost-comparison-pt-vs-us.md`
- Currency symbols: `USD` for US dollars, `EUR` for euros; never `$` or `€` alone (ambiguous at parse time)

### Currency handling
- All amounts MUST be dated (use `as of YYYY-MM-DD` prefix when rates matter)
- USD↔EUR conversion rule: use the European Central Bank reference rate for the date of the amount, not today's rate
- Both currencies shown side-by-side for the same item, e.g., `EUR 1,500 (USD 1,650 as of 2026-05-27)`
- Exchange-rate assumption files (e.g., `fx-assumptions.md`) reference ECB rate snapshots; snapshot date in filename

### Amount types
- One-time (move costs, deposits, visa fees)
- Recurring (rent, utilities, insurance, taxes)
- Variable (food, transport, healthcare)
- Reserves (3–6 months operating buffer)

## Work Guidance

- **Link to docs:** `docs/finance-taxes/` is the canonical workstream for Espinho-side tax and banking. Cross-link any budget file that depends on a tax assumption to the corresponding `docs/finance-taxes/` doc.
- **Currency consistency:** when an item is shown in both currencies, both values must be in the same time-period. Mixing `monthly EUR` with `annual USD` is a violation; tag every amount with its period.
- **Total reconciles to checklist milestones:** the grand total in the budget should reconcile to the cost categories in `checklists/` (pre-move, during-move, post-move). If they don't reconcile, update one or the other — do not have two sources of truth.
- **Updates: append-only.** Each update is a new dated file. Do not rewrite prior files; if a number changes, write a new file with the new date and a note explaining the change.

## Verification

- **Currency consistency check:** every amount in every file has both a currency code (USD/EUR) and a period (monthly/annual/one-time)
- **Total reconciles to checklist:** sum of one-time costs in `budget/` matches sum of pre-move + during-move + post-move entries in `checklists/`
- **Exchange-rate freshness:** no amount older than 90 days uses a rate from a snapshot older than 90 days
- **No duplicate currency assumption:** each fx rate snapshot appears in exactly one file (canonical); other files reference it by date

## Child DOX Index

| Path | Scope |
|---|---|
| (no sub-folders; flat structure) | All budget files live at the top level of `budget/` with the date-prefix naming convention |
