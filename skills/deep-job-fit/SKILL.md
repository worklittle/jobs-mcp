---
name: deep-job-fit
description: >-
  Find jobs that match the user's real experience (resume, profile or what they said in chat), in the
  place they want to work: a city, a state, a whole country, or remote. Also surfaces adjacent roles
  they haven't considered. Use for "jobs that fit me", "what should I apply for", personalized
  recommendations, hidden fits, what am I missing.
---

# Jobs that match your experience

## Tools
`get_my_resume` / `get_my_profile` (when signed in), `search_jobs`, `get_job_details`, `get_market_overview`

## 1. Know their experience
- Signed in: `get_my_resume` (resume text) and `get_my_profile` (location, desired role, desired salary).
- Otherwise use the resume or background they shared in chat. Never invent experience.
- Note: current and past titles, years, skills, degree or licenses, desired salary.

## 2. Pick where to search
Ask once, with their profile location as the suggested default, unless they already said:
> "Where should I look: **[their city]**, all of **[their state]**, anywhere in **[their country]**, or **remote**?"

| Choice | search_jobs fields |
| --- | --- |
| City | `near_lat` + `near_lng` (the city's coordinates), `radius_km` 25–50, `location` as the label |
| State | `state` (US two-letter code, e.g. `TX`) |
| Country | `country` (ISO code, e.g. `US`, `GB`) |
| Remote | `remote: true` (add `country` to keep it to one country). No other place fields. |

Several choices (e.g. "Austin or remote") → one search per choice, then merge.

## 3. Search
- 2–4 focused searches: their current title, the next step up, and 1–2 adjacent titles their experience transfers to.
- Role text only in `query`. Salary floor → `salary_min`. Visa need → `visa_sponsorship: "yes"`.
- `get_job_details` on the best 3–5 before claiming requirements.

## 4. Answer
Ranked shortlist, each with: why it fits their experience (name the matching role or skill), any gap, pay, and place or remote. Then 1–2 adjacent roles worth a look. Offer to apply (`apply_for_job`) to the ones they pick.

## Guardrails
Every opening comes from tool results; no made-up job ids. Do not apply without the user's go-ahead.
