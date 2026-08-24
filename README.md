# Job Description Screener & Resume Tailor

A single-file web tool that screens job postings against a resume and drafts a tailored resume + cover note for the roles worth applying to. Runs entirely in the browser, powered by the Claude API.

**This is the general-purpose version.** Anyone can open the page, paste in their own resume, and answer a short set of guided questions about how they want roles scored — no code editing required. It's a template meant to be picked up and used with someone else's background, not tied to any one person's job search.

**Live:** https://chrisacannon.github.io/job-screener/ *(update this once your repo/Pages URL is set)*

## What it does

1. **Screen a role** — paste a job posting and get a 1–10 match score, a verdict (apply / review / pass), a salary recommendation, fit reasons, gaps, and a plain-language summary.
2. **Tailor (score 5+)** — generates a first-draft tailored resume and cover note based on your resume, the posting, and your own scoring rules. Flags any claims worth double-checking before you submit.

## Getting started

1. Open the page — it starts blank, with no one's data pre-loaded. The first visit walks through a short setup:
   - Paste your resume (there's a "See an example resume" link if you want a reference point — it won't touch your own field).
   - Optionally answer a set of scoring-rule questions — target roles, hard disqualifiers, skills that shouldn't count against you, language rules for tailored drafts, etc. Skip anything that doesn't apply.
2. Enter your own Anthropic API key (get one at [console.anthropic.com](https://console.anthropic.com)). It's used only to call the API directly from your browser and is never saved — you'll re-enter it each visit.
3. Paste a job description and screen it.

Each screening costs roughly $0.005–0.01 in API usage; generating tailored materials adds another $0.01–0.02.

## Your data

- Your resume and rule answers are saved in **your browser's local storage only**, tied to this page's URL. Nothing is uploaded to a server.
- The only network call this page makes is directly from your browser to Anthropic's API, using your own key.
- Use **Start over** (in the Resume & rules tab) to clear your saved data and redo setup — useful if you want to screen for someone else, or start fresh.
- Because storage is per-browser, everyone who visits this page gets their own private setup — nothing is shared between visitors.

## Customizing this for someone else

This is built to be reused. Everything a new user needs is collected through the in-app setup flow — no code changes required to use it yourself.

If you're maintaining a copy of this repo for someone else (or want to swap out the built-in example), the only things to touch are two constants near the top of the `<script>` block in `index.html`:
- `EXAMPLE_RESUME` — the resume shown behind the "See an example" link.
- `EXAMPLE_RULE_ANSWERS` — the worked-example answers shown behind "See how [name] answered these."

Everything else — the questions themselves, the scoring logic, the tailoring prompt — is generic and applies to any user's own input.

## Tech notes

- Single static HTML file. No build step, no backend, no dependencies beyond the Anthropic API.
- Model: `claude-sonnet-4-6` via `POST https://api.anthropic.com/v1/messages`, called directly from the browser.

---

Built by Chris Cannon · [chrisacannon.github.io](https://chrisacannon.github.io)
