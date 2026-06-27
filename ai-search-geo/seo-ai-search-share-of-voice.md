# Share of Voice Across LLMs

**Purpose:** Measure how often your brand/site is mentioned or cited across AI answer engines (ChatGPT, Perplexity, Google AI Overviews, Gemini) for a defined set of category queries — the AI-era equivalent of rank tracking.

**When to run this:** Monthly, against a fixed query set so trend is comparable over time.

**Inputs needed:**
- Defined query set (category + comparison + "best X" style queries relevant to the niche, from `seo-niche.md`)
- Brand name + key competitor names to track

**Process:**
1. Run the fixed query set against each AI platform on a consistent cadence (same day each month minimizes day-to-day volatility noise).
2. For each query/platform pair, record: was the brand mentioned at all, was it cited as a source/link, what sentiment/framing was used, and which competitors appeared instead.
3. Calculate Share of Voice as (queries where you appear) / (total queries) per platform — track separately per platform, since they cite very differently; don't average them into one misleading number.
4. Identify queries where a competitor is consistently cited and you're absent — feed these directly into `seo-geo.md` for page-level diagnosis.
5. Track trend over time, not single-month snapshots — AI answer engines are volatile month to month; a single bad month is noise, three consecutive bad months is signal.

**Output format:**
`Query | Platform | Brand mentioned (Y/N) | Cited as source (Y/N) | Competitors mentioned instead | Trend (vs last month)` — plus a rolled-up Share of Voice % per platform per month.

**Quality bar:** Don't report a single blended "AI visibility score" across platforms — it hides which platform actually needs the work.
