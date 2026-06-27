# Keywords Rivals Rank, You Don't

**Purpose:** A narrower, faster cut of gap analysis — pure "they rank top 10, you're not in top 50 anywhere" — built for rapid triage when you don't have time for the full matrix.

**When to run this:** Weekly/biweekly monitoring cadence, between full quarterly `seo-competitor-gap-analysis.md` runs.

**Inputs needed:**
- Your domain + competitor domain(s)
- Rank tracking snapshot (current week vs prior)

**Process:**
1. Pull each competitor's top 10 rankings, filter to keywords where you don't appear in the top 50 at all.
2. Cross-reference against your existing cluster map (`seo-keyword-cluster.md`) — if the term fits an existing pillar, it's a spoke you missed, not a new pillar.
3. Flag any term that's new this week (competitor just started ranking) separately — that's a leading indicator of their content roadmap, worth more attention than long-standing gaps.
4. Cap the output at the top 15 by volume × intent — this is a triage list, not an archive.

**Output format:**
`New-this-week (Y/N) | Keyword | Vol | Competitor rank | Fits existing cluster? | Action (new spoke / new pillar / ignore)`

**Quality bar:** If more than half the list is "fits existing cluster," your `seo-keyword-cluster.md` output is stale — re-run clustering before triaging gaps.
