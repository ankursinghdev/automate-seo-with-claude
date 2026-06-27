# automate-seo-with-claude

A 27-file prompt/playbook library for running SEO end-to-end with Claude: keyword research, competitive intel, backlinks, on-page/technical, content quality, AI-search (GEO/AEO), local & paid, and strategy/monitoring.

This is a **flat template library**, not a formal Anthropic Skill package — every file is plain markdown, designed to be pasted into Claude.ai, Claude Code, Cowork, or any agent without configuration. See "Going further" below if you later want these wrapped as auto-invoked Claude Skills.

## Structure

```
keyword-research/        Find and cluster what to target
competitive-intel/       Where rivals beat you, and where you can beat them back
backlinks/                Link profile health + acquisition targets
on-page-technical/       Crawl, index, CWV, schema, images, hreflang
content-quality/         E-E-A-T scoring + agency/landing pages
ai-search-geo/           Citability in AI Overviews / ChatGPT / Perplexity
local-and-paid/          GBP/local pack + paid SERP intel
strategy-monitoring/      Roadmap, regression tracking, data pipeline, API recipes
```

27 files total. Most reference each other directly — e.g. `seo-plan.md` rolls up the outputs of the audit files; `seo-api.md` is the shared data layer most others assume.

## Fixes made vs. the original planning graphic

The source graphic this repo was built from claimed "26 SEO Skills" but listed 27 rows, with one naming collision:

- `competitive-intel/` originally listed **two** files both named `seo-subdomain.md` — one meant "X vs Y comparison pages," the other "subdomain ownership + cannibalization map." These are genuinely different tasks, so both were kept and the first was renamed to `seo-comparison-pages.md`.
- `seo-niche.md` had no legible description in the source graphic; its purpose was inferred from its position as the entry point of `keyword-research/`.

If you'd rather collapse back to exactly 26, the cleanest cut is to fold `seo-comparison-pages.md` into `seo-competitor-pages.md` as a sub-section — they're adjacent tasks.

## How to use a file

Open the `.md` file, paste its contents (or the relevant section) into Claude as context, then give Claude the specific inputs the file asks for. Each file follows the same shape: Purpose, When to run, Inputs needed, Process, Output format, Quality bar.

## Going further: wrapping these as real Claude Skills

If you want Claude Code or Cowork to auto-invoke these without you pasting them manually, each file becomes a folder: `skills/<slug>/SKILL.md` with YAML frontmatter (`name`, `description` with trigger phrases). Don't do this until the content above has actually been used and refined — tuning trigger phrases for 27 untested skills is wasted effort. There's already a mature, working example of this exact pattern public on GitHub (aaron-he-zhu/seo-geo-claude-skills) worth studying before building your own frontmatter from scratch.

## License

MIT — see LICENSE.
