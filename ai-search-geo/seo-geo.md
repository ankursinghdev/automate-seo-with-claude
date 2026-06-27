# Page AI Overview Citation Fixes

**Purpose:** Diagnose why a specific page isn't getting cited in Google AI Overviews / ChatGPT / Perplexity-style AI answers for queries it should be relevant to, and restructure it to improve citability — without chasing the influencer myths that don't hold up.

**When to run this:** Per priority page, after `seo-ai-search-share-of-voice.md` flags it as underperforming relative to its traditional ranking.

**Inputs needed:**
- Page content + current traditional ranking position for the target query
- Sample AI Overview / AI answer output for the target query (manually checked or via a tracking tool)
- Identity of which competitor/source IS being cited, if any

**Process:**
1. Compare the page's traditional ranking (often fine, even top 3) against whether it's cited in the AI answer (often it's not) — this gap is the actual problem to solve, not general "SEO."
2. Check whether the page leads with a directly extractable answer in the first 1–2 sentences after the H1, or buries the answer under throat-clearing intro paragraphs — AI answer engines favor front-loaded, self-contained statements.
3. Check answer structure: a single clear sentence answering the implicit question, followed by supporting specifics, beats a long narrative paragraph for extraction.
4. Verify the page isn't relying on tactics with weak evidence behind them — an `llms.txt` file alone does not function as a citation lever, content "chunking" for AI doesn't reliably help, and AI-specific keyword rewriting is not a real optimization; don't spend effort there.
5. Check technical accessibility: is the page blocked for AI/GPTBot-style crawlers in robots.txt (sometimes blocked unintentionally when blocking scrapers broadly)? Confirm the page renders its answer content server-side, not solely via client-side JS the crawler may not execute.
6. Rewrite the lead paragraph/section specifically for direct-answer extraction, keeping the rest of the page's depth intact for human readers and traditional ranking.

**Output format:**
`Query | Traditional rank | Currently cited in AI answer (Y/N) | Who is cited instead | Root cause | Specific rewrite (before/after lead paragraph)`.

**Quality bar:** Don't recommend `llms.txt`, content-chunking, or "AI keyword" rewrites as the fix — if that's the only idea on the page, the diagnosis didn't go deep enough.
