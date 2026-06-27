# Competitor Coverage Gap Analysis

**Purpose:** Side-by-side comparison of your domain against 3–5 named rivals to surface ranking and content gaps — the foundation report everything else in this folder builds on.

**When to run this:** Quarterly, and any time a competitor launches a major content push or you're scoping new work.

**Inputs needed:**
- Your domain + 3–5 competitor domains
- Backlink/rank data source (Ahrefs/DataForSEO via `seo-api.md`)

**Process:**
1. Pull organic keyword sets for every domain in the comparison.
2. Build a coverage matrix: for each keyword, who ranks (you, them, both, neither in top 20).
3. Bucket gaps into three types: **content gaps** (they have a page, you don't), **rank gaps** (you both have a page, they outrank you), and **format gaps** (same topic, different content type — they have a calculator, you have a blog post).
4. Weight every gap by commercial intent and volume, not volume alone — a 200-volume transactional gap usually beats a 2,000-volume informational one.
5. Hand content gaps to `seo-content-brief.md`, rank gaps to `seo-content-audit.md` (refresh candidate), format gaps to strategy review.

**Output format:**
`Keyword | Vol | Your rank | Competitor + their rank | Gap type | Priority (1-5)`

**Quality bar:** Don't report a gap you can't act on this quarter — a 50-item backlog nobody will touch isn't intelligence, it's noise.
