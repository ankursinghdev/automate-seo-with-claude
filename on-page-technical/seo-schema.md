# JSON-LD — Detect, Validate, Generate

**Purpose:** Inventory existing structured data, validate it against current schema.org and Google requirements, and generate missing/corrected JSON-LD — the same blueprint already used for Ellocent Labs' blog schema rollout.

**When to run this:** Per page-template (not per page) when launching new content types, and sitewide as part of `seo-technical-audit.md`.

**Inputs needed:**
- Rendered HTML for each page template (schema must be checked post-render, not in source if client-side injected)
- Business data needed for schema fields (org details, author bios, product specs, FAQ content, review counts)

**Process:**
1. Detect existing JSON-LD blocks per template and identify the schema type(s) used (Article, Organization, Product, FAQPage, BreadcrumbList, LocalBusiness, etc.).
2. Validate against required and recommended properties for each type — flag missing required fields (these can cause rich result eligibility loss) separately from missing recommended fields (lower priority).
3. Check for the common failure modes: placeholder/lorem data left in from a template, mismatched data between visible page content and schema (e.g., schema price ≠ displayed price — a policy violation risk), and duplicate/conflicting schema blocks on the same page.
4. For templates with no schema, generate appropriate JSON-LD based on page type — match content already on the page, don't invent data points.
5. Validate every generated block against Google's Rich Results Test logic before handing off (required fields present, no syntax errors, types correctly nested).

**Output format:**
`Template | Schema type(s) found | Validation status | Missing required fields | Missing recommended fields | Generated/corrected JSON-LD block (ready to paste)`.

**Quality bar:** Never output schema with fabricated values (fake review counts, invented prices, placeholder author names) — that's the exact pattern that gets sites manually penalized for structured data spam.
