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
| PwC | jobs-ta.pwc.com (PwC's actual ATS — pwc.com/in/en/careers itself is not search-indexed) |

Add more companies or specific board URLs here any time — the agent reads this file fresh on every run.

## Change log

- **2026-09-17:** Fixed the PwC entry. `site:pwc.com/in` returned zero postings on 3 straight days (09-14, 09-15, 09-16); broadening to `site:pwc.com OR site:jobs-ta.pwc.com` on 09-17 surfaced 10+ real Bengaluru postings — PwC's actual careers/ATS domain is `jobs-ta.pwc.com`, not `pwc.com/in`. Use `jobs-ta.pwc.com` directly going forward.
- **Still open:** Microsoft (`careers.microsoft.com`) and KPMG (`kpmg.com/in/en/careers`) have returned zero postings on all 4 runs so far (09-14 through 09-17). Unlike PwC this hasn't been root-caused yet — may be a similar wrong-domain issue (e.g. Microsoft's actual ATS may differ from careers.microsoft.com's indexed pages) or a genuine indexing gap. Needs the same kind of broadened-query investigation PwC got today.

## Search notes

- Always filter to Bengaluru, India. Discard anything else, including "PAN India" or multi-city listings unless Bengaluru is explicitly one of the listed locations.
- Prefer each company's own career portal over third-party aggregators to reduce stale/duplicate listings.
- If a company's career site blocks search indexing, fall back to a general web search scoped with `site:<domain>` plus role keywords from `profile.md`.
