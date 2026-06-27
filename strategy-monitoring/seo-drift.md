# Baseline + SEO Regression Tracking

**Purpose:** Catch silent regressions — a deploy that strips a schema block, flips a page to noindex, changes a canonical, or drops title tags — before they show up as a ranking drop weeks later.

**When to run this:** Continuously/on a schedule (daily or per-deploy if hooked into CI), not just when something already looks wrong.

**Inputs needed:**
- A stored baseline snapshot of key SEO elements per page (title, meta description, canonical, robots directive, schema presence, H1, status code)
- Current crawl to diff against the baseline

**Process:**
1. Establish a baseline snapshot of every tracked page's critical SEO elements — this is the reference state, captured when the page is known-good.
2. On each check, re-crawl and diff against baseline: flag any change to noindex/robots directives, canonical target, schema block presence/type, title or meta description, and status code.
3. Severity-rank diffs: a new noindex on an indexed, ranking page is **Critical** (fix immediately); a title tag change is **Warning** (verify intentional); a meta description change is **Info** (log only).
4. For sites built on no-code/headless platforms (the pattern already seen with CMS rendering failures and base64 image bloat on prior audits), check specifically for CMS-injected defaults overwriting custom SEO fields on republish — this is a recurring, platform-specific failure mode worth a dedicated check.
5. Update the baseline only after a flagged change is confirmed intentional — don't auto-accept the new state, or regressions become invisible "baseline drift" over time.

**Output format:**
`Page | Element changed | Previous value | Current value | Severity | Confirmed intentional? (Y/N/pending)`.

**Quality bar:** A drift report with no severity tiering trains the team to ignore it — Critical findings need to be visually and procedurally distinct from Info-level noise.
