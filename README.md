# Job Description Screener & Resume Tailor

A browser-based job search tool powered by the Claude API. Paste any job description to get an instant match score, fit analysis, identified gaps, and salary guidance. Optionally generate a tailored resume and cover note. Bring your own Anthropic API key — nothing is stored or transmitted beyond your browser session.

**Live site:** [chrisacannon.github.io/job-description-screener](https://chrisacannon.github.io/job-description-screener)

---

## What it does

**Step 1 — Screen:** Paste a job description and get:
- Match score (1–10) with verdict: apply / review before applying / pass
- Salary recommendation based on the posted range
- Fit reasons and identified gaps
- Plain-language summary of the match

**Step 2 — Tailor (optional, score 5+):** Generates a tailored resume and cover note based on your stored resume and the job description. Also flags any claims worth pressure-testing for accuracy before submitting.

---

## How to use it

1. Get an Anthropic API key at [console.anthropic.com](https://console.anthropic.com)
2. Open the tool and enter your API key in the field at the top
3. Go to the **Resume & rules** tab and paste your resume as plain text
4. Add any custom scoring rules (optional) — role family guidance, known gaps, target salary range
5. Go back to **Screen a role**, paste a job description, and hit Screen

Each screening costs roughly $0.005–$0.01. Resume and cover note generation adds another $0.01–$0.02.

---

## Customizing for your own use

This tool is designed to be repurposed by other job seekers. The only things you need to change are two constants near the top of `index.html`:

**`DEFAULT_RESUME`** — replace with your own resume as plain text. This pre-populates the resume field when you open the tool.

**`DEFAULT_RULES`** — replace with scoring guidance tailored to your background, target roles, and known gaps. The default rules are calibrated for a portfolio strategy and analytics background targeting Dallas-area roles — swap in your own role families, hard disqualifiers, and tool stack.

Everything else stays the same. No backend, no build process, no dependencies — it's a single HTML file.

---

## Privacy

Your API key is entered at runtime and used only in your browser to call the Anthropic API directly. It is never hardcoded, stored, logged, or transmitted anywhere other than the API call itself. No data leaves your browser session.

---

## Files

| File | Purpose |
|---|---|
| `index.html` | The entire tool — single self-contained HTML file |
| `README.md` | This file |

---

## Built by

Chris Cannon · [chrisacannon.github.io](https://chrisacannon.github.io)
