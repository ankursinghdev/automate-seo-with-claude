# Niche & Seed Keyword Discovery

**Purpose:** Take a vague business description or a single seed keyword and turn it into a defensible list of niche entry-point keywords worth building topical authority around — before any clustering or content planning happens. (Note: this file's description was illegible in the source graphic — this purpose is inferred from its position as the first file in keyword-research/.)

**When to run this:** Start of a new site, a new service line, or a new market (e.g., expanding from .com to .com.au). Always run before `seo-keyword-cluster.md`.

**Inputs needed:**
- Business/service description (2–3 sentences, in the client's own words)
- Target market(s) and language(s)
- 3–5 known competitor domains (if available)
- Any existing GSC query data (optional but preferred)

**Process:**
1. Extract the core "job to be done" from the business description — not the product name, the problem it solves.
2. Generate seed terms across three altitudes: category term (high volume, high competition), use-case term (mid volume, buyer intent), and problem/symptom term (lower volume, top-of-funnel).
3. Run each seed through a keyword tool (Ahrefs/DataForSEO via `seo-api.md`) and pull: volume, KD, CPC, and top 5 ranking domains.
4. Discard terms where all top-5 results are global brands, marketplaces, or sites with 10x+ the client's domain authority — flag as "not winnable in 12 months," don't delete (useful for paid, see `seo-ads.md`).
5. Score remaining terms on Volume × (1/KD) × Commercial Intent (1–3 scale) to rank niche viability, not just raw volume.
6. Pick the top 8–12 as the niche's anchor terms — these become the seeds for `seo-keyword-cluster.md`.

**Output format:**
A ranked table: `Term | Volume | KD | Intent (Info/Comm/Trans) | Winnable (Y/N + why) | Niche Score`

**Quality bar:** Reject any seed list where every term has KD > 40 — that means the niche boundary was drawn too wide. Narrow and re-run.

**Example:** Input "AI automation agency targeting Australian SMEs" → seeds should split into category ("AI automation Australia"), use-case ("automate customer support AI Australia"), and problem ("too many manual data entry tasks small business") — not just "AI agency" repeated three ways.
