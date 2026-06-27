# E-E-A-T Scoring + Publish Verdict

**Purpose:** Score draft or live content against Experience, Expertise, Authoritativeness, Trust signals and render a publish/hold/revise verdict — the gate every piece of content should clear before it goes live, especially for YMYL-adjacent topics.

**When to run this:** Before publishing any new content, and as a batch sweep across existing content during a content audit.

**Inputs needed:**
- Full draft/page content
- Author identity and credentials (if a named author byline exists)
- Source citations used in the piece

**Process:**
1. **Experience** — does the content show first-hand specificity (a named example, a screenshot, a number that couldn't be guessed) versus generic restated knowledge? Score 0–25.
2. **Expertise** — is there a credentialed/named author, or does the content demonstrate domain depth (correct terminology, nuanced caveats, not surface-level)? Score 0–25.
3. **Authoritativeness** — does the content cite primary sources (official docs, original research, named experts) rather than other blogs citing other blogs? Score 0–25.
4. **Trust** — is the information accurate and current, are claims sourced, is there transparency about affiliations/sponsorships where relevant, and does the page avoid manipulative patterns (fake urgency, hidden costs)? Score 0–25.
5. Sum to a /100 score. Render verdict: **Publish** (≥80), **Revise** (60–79, list the specific gaps), **Hold** (<60, needs substantial rework before resubmission).

**Output format:**
`Score breakdown (4 categories /25 each) | Total /100 | Verdict | Specific gaps to close (if Revise/Hold) | Suggested fixes`.

**Quality bar:** A score with no per-category breakdown isn't auditable — always show the 4 numbers, not just the total, so the writer knows exactly what to fix.
