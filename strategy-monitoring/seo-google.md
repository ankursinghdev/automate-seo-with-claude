# Google GSC/PSI/CrUX/GA4 First-Party Data Pull

**Purpose:** Standardize the pull of first-party Google data sources into one consistent dataset other files in this repo can rely on — instead of every audit re-deriving its own ad-hoc export.

**When to run this:** As a scheduled pull (weekly/monthly) feeding `seo-drift.md`, `seo-technical-audit.md`, and `seo-plan.md`; not a one-off task.

**Inputs needed:**
- GSC property access
- GA4 property access
- PageSpeed Insights / CrUX API access (see `seo-api.md` for integration pattern)

**Process:**
1. Pull GSC Performance data (queries, pages, clicks, impressions, CTR, position) at both query-level and page-level granularity — page-level alone hides which queries drive a page's traffic.
2. Pull GSC Coverage/Indexing data (indexed, excluded, with exclusion reasons) — this is the ground truth for indexation status, more reliable than crawl-inferred guesses.
3. Pull CrUX field data (real-user CWV) per URL/template where volume allows, falling back to PSI lab data for low-traffic pages CrUX doesn't have enough data for — label clearly which source each number came from, lab and field data can disagree meaningfully.
4. Pull GA4 engagement data (engaged sessions, conversion events, landing page performance) joined to the same URL set as GSC for a unified view.
5. Normalize all of it into one dataset keyed by URL + date, so downstream files aren't each writing their own export logic.

**Output format:**
A unified dataset/table: `URL | Date | Clicks | Impressions | CTR | Avg position | Indexed (Y/N + reason if N) | CWV (field/lab, labeled) | GA4 engaged sessions | Conversions`.

**Quality bar:** Never blend lab and field CWV data into one number without labeling the source — they measure different things and disagreement between them is itself diagnostic information.
