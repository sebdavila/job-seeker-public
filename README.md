# job-seeker

A Claude skill that acts as an expert career coach. Give it a job posting (URL or text) and your CV — it analyzes the match, tailors your resume to the role with ATS-optimized keyword integration, and optionally drafts a referral message and cover letter.

## What it does

1. **Fetches JDs from URLs** — paste a LinkedIn, company portal, or any job posting link
2. **Detects the process language** — generates all content in English or Spanish automatically
3. **Populates an ATS template** from your current CV
4. **Scores the match** — strengths, gaps, and mitigation plan
5. **Reality-checks the role** — daily functions, culture, red flags
6. **Edits the CV for ATS** — exact keyword matching, all experience reframed for the target role, job title updated
7. **Drafts referral messages** — LinkedIn/WhatsApp short version + detailed email/InMail
8. **Writes a cover letter** — structured, persuasive, in the right language

## Installation

### Claude.ai
1. Download [`job-seeker.skill`](https://github.com/sebdavila/job-seeker-public/blob/main/job-seeker.skill)
2. Go to **Settings → Customize → Skills → Upload skill**
3. Upload the file

### Claude Code
```bash
mkdir -p ~/.claude/skills
git clone https://github.com/sebdavila/job-seeker-public.git ~/.claude/skills/job-seeker
```

## Usage

Start a new conversation and paste a job description:

> *"Quiero aplicar a este trabajo: https://jobs.mastercard.com/..."*

or

> *"I want to apply to this role: [paste full JD text]"*

The skill will guide you through the full process step by step.

## How it works

The skill uses `assets/base-cv-ats.docx` — a clean, ATS-optimized Word template — as the structural foundation. When you share your CV, it extracts your information and populates the template before tailoring it to the job description.

No personal data is stored. Each session starts fresh.

## Requirements

- Claude Code or Claude.ai with skills support
- Your current CV (any format — .docx, .pdf, or paste the text)
