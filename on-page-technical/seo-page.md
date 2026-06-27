# One-URL Keep / Refresh / Kill Verdict

**Purpose:** Given a single URL, render a clear verdict — keep as-is, refresh, consolidate, or kill (410/301) — backed by data, not gut feel. This is the atomic unit every other content-quality file rolls up into.

**When to run this:** Per-URL, as part of a content audit (`seo-content-audit.md`) or whenever someone asks "is this page still worth having?"

**Inputs needed:**
- URL + GSC performance data (impressions, clicks, position, trend over 12 months)
- GA4 engagement data (if available)
- Current ranking keyword(s) and their cluster context

**Process:**
1. Pull 12-month trend: is traffic flat, growing, or declining? Decay alone isn't a kill signal — check if the *query* still has demand (use `seo-niche.md` data) before blaming the page.
2. Check cannibalization: does another URL on the site already rank for the same primary query? If yes, this is a consolidation candidate regardless of its own performance.
3. Check content freshness against the topic's volatility — YMYL, pricing, and "best of [year]" pages decay fast; evergreen how-to content doesn't need the same cadence.
4. Score on four axes: search demand for the topic (still exists?), current performance (trending up/flat/down), competitive position (can it realistically rank top 5?), and business value (does it map to a revenue-generating page?).
5. Render verdict: **Keep** (performing, no action) / **Refresh** (demand exists, content is stale or thin) / **Consolidate** (cannibalizing or redundant — merge into stronger URL, 301 this one) / **Kill** (no demand, no equity, remove and 410).

**Output format:**
`URL | 12mo trend | Cannibalization (Y/N + competing URL) | Verdict | One-line reasoning | If refresh: top 3 fixes`

**Quality bar:** "Refresh" without naming the top 3 specific fixes is not a verdict, it's a deferral.
