# Phased Quarter-by-Quarter SEO Roadmap

**Purpose:** Roll up the outputs of every other file in this repo into a single phased roadmap with sequencing, dependencies, and resourcing — the document a client or stakeholder actually reads, versus the 26 working files behind it.

**When to run this:** Quarterly planning cycle, and once at project kickoff to set the baseline 4-quarter view.

**Inputs needed:**
- Latest outputs from `seo-technical-audit.md`, `seo-competitor-gap-analysis.md`, `seo-content-audit.md`, and `seo-niche.md`/`seo-keyword-cluster.md`
- Available resourcing (dev hours, content production capacity, budget)

**Process:**
1. Pull the top findings from each input file and bucket by type: technical fixes, content creation, content refresh/consolidation, link building, local/paid.
2. Sequence by dependency first, impact second — e.g., fix indexation/crawl issues (`seo-technical-audit.md`) before investing in new content the crawler can't reach; resolve cannibalization (`seo-subdomain.md`, `seo-page.md`) before building more content into the same cluster.
3. Assign each workstream to a quarter based on realistic capacity, not aspiration — a roadmap that assumes 3x current content output is a wish list, not a plan.
4. Set one or two measurable goals per quarter (e.g., "resolve top 10 technical findings," "publish 8 cluster-mapped articles," "close top 5 competitor content gaps") rather than a vague "improve rankings."
5. Build in a checkpoint at the start of each quarter to re-run `seo-drift.md` and adjust the plan based on what actually happened, not just what was planned.

**Output format:**
4-quarter roadmap: `Quarter | Workstream | Specific deliverables | Owner | Dependency | Success metric`.

**Quality bar:** If a quarter's plan doesn't reference specific outputs from the underlying audit files (URLs, keywords, named issues), it's strategy theater — every line should trace back to a real finding.
