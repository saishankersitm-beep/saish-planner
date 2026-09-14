# Job Sources

The daily agent checks these companies' own career sites / official job boards (via web search, `site:` queries against each domain) rather than scraping LinkedIn Jobs directly. Search each of these for **Bengaluru-only** openings matching `profile.md`:

| Company | Career site to search |
|---|---|
| Microsoft | careers.microsoft.com |
| Google | careers.google.com |
| Rakuten | corp.rakuten.co.jp/careers, rakuten.wd1.myworkdayjobs.com |
| KPMG | kpmg.com/in/en/careers |
| Deloitte | careers.deloitte.com |
| EY | careers.ey.com |
| PwC | pwc.com/in/en/careers |

Add more companies or specific board URLs here any time — the agent reads this file fresh on every run.

## Search notes

- Always filter to Bengaluru, India. Discard anything else, including "PAN India" or multi-city listings unless Bengaluru is explicitly one of the listed locations.
- Prefer each company's own career portal over third-party aggregators to reduce stale/duplicate listings.
- If a company's career site blocks search indexing, fall back to a general web search scoped with `site:<domain>` plus role keywords from `profile.md`.
