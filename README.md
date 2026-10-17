# job-skill-au

Job search assistant for people living in Australia, built as a Claude Skill. Works for any
profession, not just tech.

Searches the common Australian job boards (Seek, LinkedIn, Indeed AU, Jora, CareerOne, Glassdoor,
Adzuna, Workforce Australia), APSJobs and every state and territory government board, plus niche
boards by industry (tech and startups, graduates, not-for-profit, healthcare, education,
universities, mining and FIFO). It scores each job against your resume, verifies every link,
tracks applications in a spreadsheet, and can create a resume and cover letter tailored to each job.

## Commands

- `/job-skill-au help` — usage guide
- `/job-skill-au search` — search the boards for jobs matching your profile
- `/job-skill-au status` — update application statuses (from Gmail if connected, otherwise by asking)
- `/job-skill-au automate` — schedule a recurring search with a short report

Natural language also works, e.g. "find casual barista jobs in Fitzroy", "any new nursing jobs in
Brisbane this week?", "write a cover letter for this Seek job: <link>".

## Key features

- First run collects your resume and preferences (roles, locations, work type, salary in AUD, work
  rights, security clearance) and saves them to `au_job_profile.md`, so it never asks again
- Filters out jobs needing citizenship, a clearance or a licence you don't have
- Fit score per job with a one-line reason and any gaps
- **Job-specific resumes, your choice**: at setup, pick "ask me each time", "always" or "never".
  Resumes follow Australian conventions (2–3 pages, no photo or date of birth, Australian spelling,
  ATS-friendly layout) and never invent skills or experience. Optional cover letters, and
  selection-criteria answers (STAR) for government roles
- Every apply link is checked live; expired listings are dropped
- Tracker `job_tracker_au.xlsx` with status flow Found → Applied → Interview → Offer / Rejected
- Scheduled searches handle every Australian time zone (AEST/AEDT, ACST/ACDT, AWST)

## Installation

Copy `SKILL.md` into `~/.claude/skills/job-skill-au/SKILL.md`:

```bash
mkdir -p ~/.claude/skills/job-skill-au && curl -L https://raw.githubusercontent.com/mcaupybugs/job-skill/main/SKILL.md -o ~/.claude/skills/job-skill-au/SKILL.md
```

Then run `/job-skill-au search` in Claude Code from the folder where you want your profile,
tracker and resumes saved.
