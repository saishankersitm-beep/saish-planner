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

- **2026-09-18:** Microsoft gap re-diagnosed — it was a query problem, not a real absence of postings. Searching `careers.microsoft.com/v2/global/en/locations/bengaluru.html` directly (instead of a generic keyword `site:` query) surfaces real Bengaluru PM/TPM postings via aggregators. The reason none have been "strong matches" so far isn't indexing — Microsoft's Bengaluru Product Manager postings skew either below the profile's seniority bar (e.g. "Product Manager II", pitched at 5-7 yrs vs. the candidate's 14+) or into deep technical-IC territory (e.g. Senior TPM for Windows Manageability/MDM, which needs OS engineering depth the profile doesn't have) rather than the Big-4-style "Manager" band this profile targets. Keep checking, but temper expectations — this may just be a genuine fit gap, not a discovery gap.
- **2026-09-17:** Fixed the PwC entry. `site:pwc.com/in` returned zero postings on 3 straight days (09-14, 09-15, 09-16); broadening to `site:pwc.com OR site:jobs-ta.pwc.com` on 09-17 surfaced 10+ real Bengaluru postings — PwC's actual careers/ATS domain is `jobs-ta.pwc.com`, not `pwc.com/in`. Use `jobs-ta.pwc.com` directly going forward.
- **Still open:** KPMG (`kpmg.com/in/en/careers`) has returned zero postings on all 5 runs so far (09-14 through 09-18), including today's attempt guessing at Workday-hosted domains (`kpmg.wd3.myworkdayjobs.com`, `kpmgindia.wd3.myworkdayjobs.com`) — neither resolved. Domain-guessing hasn't worked here the way it did for PwC. If you know KPMG India's actual careers/ATS URL, add it here directly — that would resolve this faster than further guessing.

## Search notes

- Always filter to Bengaluru, India. Discard anything else, including "PAN India" or multi-city listings unless Bengaluru is explicitly one of the listed locations.
- Prefer each company's own career portal over third-party aggregators to reduce stale/duplicate listings.
- If a company's career site blocks search indexing, fall back to a general web search scoped with `site:<domain>` plus role keywords from `profile.md`.
