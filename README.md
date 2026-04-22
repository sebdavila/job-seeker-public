# job-seeker

> **[Leer en Español →](README.es.md)**

A Claude skill that acts as an expert career coach. Give it a job posting (URL or text) and your CV — it evaluates the match across 5 dimensions, generates a tailored ATS-optimized HTML resume, drafts referral messages, and prepares you for the interview with STAR stories.

**No Node.js, no Playwright, no infrastructure required.** Install the `.skill` file and start from Claude Desktop.

---

## What's new in v2.0

| Feature | v1 | v2 |
|---|---|---|
| CV format | DOCX template (XML editing) | HTML template (print to PDF from Chrome) |
| Offer evaluation | Basic match score | 5-dimension weighted scoring with 🟢/🟡/🔴 verdict |
| Onboarding | None | Saves `cv.md` + `profile.md` — no re-entering data |
| Company research | ❌ | Optional deep research step (WebSearch) |
| Referral messages | Written as the applicant | Written in 1st person **as the internal contact** |
| Interview prep | ❌ | Optional STAR+R stories, saved per company |
| Language detection | ✅ | ✅ (EN/ES auto-detect) |

---

## What it does

1. **Loads your profile** — first run sets up `cv.md` and `profile.md` once; subsequent runs load them silently
2. **Fetches the JD** — paste a URL (LinkedIn, Greenhouse, Workday, etc.) or the full JD text
3. **Optional company research** — deep dive on culture, financials, and red flags (you decide)
4. **Evaluates the match** across 5 dimensions with a weighted score and a clear verdict
5. **Reality check** — confirms you still want to proceed before generating anything
6. **Generates the CV** — fills the ATS-optimized HTML template; open in Chrome → Print → Save as PDF
7. **Drafts referral messages** — short (LinkedIn/Slack, ≤300 chars) + formal email, written as your internal contact to send to HR
8. **Cover letter** — optional, structured, in the correct language
9. **Interview prep** — optional STAR+R stories saved to `interview-prep/[company]-[role].md`

---

## Installation

Download the `.skill` file from [Releases](../../releases/latest) and install it in Claude:

- **Claude Desktop:** Settings → Skills → Install from file
- **Claude.ai:** Settings → Skills → Upload `.skill` file

---

## Usage

Start a conversation and paste a job posting:

> *"Quiero aplicar a este trabajo: https://linkedin.com/jobs/..."*

or

> *"I want to apply to this role: [paste full JD text]"*

The skill guides you through the full pipeline step by step. If it's your first run, it will ask for your CV and a few quick profile questions — this only happens once.

---

## How the CV works

The skill fills `assets/cv-template.html` with `{{PLACEHOLDER}}` substitution. Open the resulting HTML in Chrome and print it as PDF (Cmd+P → Save as PDF → Margins: Minimum). The template uses Google Fonts and works completely offline once fonts are cached.

No personal data is stored between sessions beyond the `cv.md` and `profile.md` files you control.

---

## Evaluation dimensions

| Dimension | Weight |
|---|---|
| Profile & Skills match | 30% |
| Level & Seniority | 20% |
| Compensation alignment | 20% |
| Culture & Motivation | 15% |
| Gaps & risks | 15% |

Scores below 3.0/5.0 trigger a strong recommendation against applying.

---

## Requirements

- Claude Desktop or Claude.ai with skills support
- Your current CV (any format — .pdf, .docx, or paste the text)
- Chrome or Chromium to print the HTML CV as PDF

---

## Source

```
skills/
├── job-seeker/          # v1 source
│   ├── SKILL.md
│   ├── assets/
│   │   └── base-cv-ats.docx
│   └── references/
│       └── reglas-ats.md
└── job-seeker-v2/       # v2 source
    ├── SKILL.md
    ├── assets/
    │   └── cv-template.html
    └── references/
        └── reglas-ats.md
```

---

## Credits

Parts of the skill structure and logic were inspired by and adapted from [**career-ops**](https://github.com/santifer/career-ops) by [@santifer](https://github.com/santifer). Thank you for the open contribution to the community.
