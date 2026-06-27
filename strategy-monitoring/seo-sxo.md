# SERP Page-Type Fix + Wireframe

**Purpose:** Diagnose mismatches between the content format Google's SERP is rewarding for a query (listicle, comparison, tool, long-form guide, video) and what the current/planned page actually is — then wireframe the correction.

**When to run this:** Per priority pillar/page, alongside `seo-content-brief.md`, especially when a page is well-optimized on-page but still underperforming.

**Inputs needed:**
- Target query + current top 10 SERP results (content format, not just topic)
- Current page (if one exists) or planned brief

**Process:**
1. Classify the dominant SERP format for the target query: is the top 10 mostly listicles, comparison tables, single-answer pages, interactive tools, video, or long-form guides? SERPs are often more format-consistent than topic-consistent.
2. Compare against the existing/planned page's actual format — a long-form narrative guide competing against a SERP dominated by comparison tables is a structural mismatch no amount of on-page optimization fixes.
3. Check for SERP features beyond organic results (video carousel, image pack, shopping units) that signal Google's preferred experience for this query — these are format hints too.
4. Wireframe the corrected structure at a block level (hero/answer block, comparison table, FAQ block, CTA placement) rather than just prose recommendations — wireframes remove ambiguity for design/dev handoff.
5. Flag if the required format is outside current production capacity (e.g., an interactive calculator) so it can be scoped honestly rather than silently downgraded to a blog post.

**Output format:**
SERP format breakdown (% of top 10 by format type) | Current/planned page format | Mismatch verdict | Block-level wireframe (text description per block, top to bottom).

**Quality bar:** Don't wireframe a format the team can't actually build in a reasonable timeframe without flagging the capacity gap explicitly — a wireframe that can't ship isn't a deliverable.
