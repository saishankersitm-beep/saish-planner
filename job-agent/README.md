# Daily Job Matching Agent

Automates a daily search for Bengaluru-only roles at Saishanker's target companies, matches them against his profile, and tailors a resume for strong matches.

## How it works

1. A scheduled Routine fires once a day into a Claude Code session (chat), carrying the instructions below.
2. Claude reads `profile.md` (candidate background + target companies + Bengaluru-only constraint) and `job-sources.md` (which career sites to check).
3. Claude searches those sources for current openings, filters to Bengaluru, and scores each against the profile.
4. Strong matches get posted as a digest in chat (title, company, location, link, why it's a fit).
5. For each strong match, Claude tailors a resume from `resume-base.md` using the `bespoke-jd` skill and saves it under `tailored-resumes/`.
6. Claude sends a notification once the day's run (search + any resumes) is complete.

## Files

- `profile.md` — candidate background, target companies, Bengaluru-only constraint, target titles.
- `resume-base.md` — factual resume baseline (never embellished with invented facts).
- `job-sources.md` — companies/career sites to check daily; editable any time.
- `tailored-resumes/` — output folder for JD-tailored resumes, one per strong match.

## Editing the agent

- To add/remove target companies: edit `job-sources.md`.
- To update career facts: edit `resume-base.md` (re-upload a cleanly-parsing resume and ask Claude to refresh it).
- To change match criteria (seniority, titles, location): edit `profile.md`.
- To change the schedule or wording of the daily run: ask Claude to update the Routine (`daily-job-matching-agent`).

## Known limitation

Three of the four originally uploaded resume files didn't parse in this environment (missing PDF tooling for large multi-page PDFs). `resume-base.md` is built from the one file that parsed cleanly. If those other files contain different or more recent facts, they should be reconciled into `resume-base.md` manually.
