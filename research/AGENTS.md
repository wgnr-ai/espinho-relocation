# `research/` — Research findings library across 8 relocation workstreams

## Purpose

The `research/` folder holds the consolidated research library for the Espinho relocation project, spanning 8 workstreams that mirror the sub-directories under `docs/`. Files in this folder are raw research outputs, source-cited notes, and methodology documentation used to inform the workstream-specific docs in `docs/<workstream>/`.

This is one of 4 ungoverned peer folders in the project (per the 2026-06-17 DOX audit). The 2 ungoverned findings were `budget/` and `research/`; this AGENTS.md closes the governance gap for `research/`.

## Ownership

- **Owner:** the `espinho-researcher` agent (per the active project context)
- **Co-owner:** Wagner dos Santos (the Principal) for source-verification and final decisions
- **Active maintenance obligation:** none on a regular cadence; updated as new research is added or as the 8 workstreams evolve
- **Custodial obligation:** review quarterly; archive or purge stale findings older than 12 months

## Local Contracts

### File naming
- Format: `YYYY-MM-DD-<topic>.md` (date prefix, ISO 8601)
- Examples: `2026-05-27-portugal-healthcare-system-overview.md`, `2026-06-10-espinho-rental-market-data.md`
- Use kebab-case for the topic segment; no spaces, no underscores

### Source-citation format
- Every claim MUST be cited to a primary source (URL, document title, page number, or interview reference)
- Inline citation format: `[Source: <title>, <publisher>, <date>, <url-or-page>]`
- Use the `> wOS Directive 11` rule: every specific value in the document is either cited, marked UNVERIFIED, or stripped
- Confidence level per file: `High` (multiple primary sources), `Medium` (one primary source), `Low` (secondary source only), `UNVERIFIED` (no source)

### Date stamps
- Each file has a `Last updated: YYYY-MM-DD` header
- Each file's `Research period:` indicates the time window the research covers (e.g., `2026-04-01 to 2026-06-15`)
- Currency-rate-sensitive claims include the snapshot date inline

### Confidence levels
- `High`: 2+ independent primary sources, no contradictions
- `Medium`: 1 primary source, no obvious contradictions
- `Low`: 1 secondary source OR primary source is dated (>12 months old)
- `UNVERIFIED`: no source — claims must be either cited or stripped per wOS Directive 11

## Work Guidance

- **Naming convention:** `YYYY-MM-DD-topic.md` where topic is a kebab-case phrase
- **Link back to docs:** every research file should reference which `docs/<workstream>/` doc it informs. Use a `## Informs` section at the top: `## Informs\n- docs/housing/ — rental market findings\n- docs/finance-taxes/ — cost-of-living comparison`
- **Cross-reference, don't duplicate:** if a finding is workstream-specific, place it in `docs/<workstream>/research-notes.md` and link from `research/`. The `research/` folder is for cross-workstream findings (e.g., comparative data, methodology, common sources).
- **Update by appending:** new findings become new dated files. Do not rewrite prior files; if a finding is corrected, write a new file with `2026-MM-DD-correction-<topic>.md` and reference the prior file.
- **Use the `espinho-researcher` agent** for new research. Wagner does manual research only for high-stakes decisions (visa, tax, healthcare).

## Verification

- **Every claim cited or stripped** per wOS Directive 11 — no unsourced claims allowed
- **Source quality verified** — primary sources preferred (government, institutional, official); secondary sources (blogs, forums) marked as such
- **Recency check** — claims older than 12 months are flagged with `(stale, $date)` annotation; a re-verification file is created for the same topic
- **Cross-workstream consistency** — if a finding affects multiple workstreams, all `docs/<workstream>/` files that depend on it are updated to reflect the new finding
- **No fabricated values** — per the wOS v0.7.3 Check H citation audit, every specific value (number, name, date, ranking, capability claim) must be cited or stripped

## Child DOX Index

| Path | Scope |
|---|---|
| (no sub-folders; flat structure) | All research files live at the top level of `research/` with the date-prefix naming convention |
