---
name: salary-you-deserve
description: >-
  Estimate a fair target salary from the user’s resume/background plus live market data
  and comparable listings. Use for what should I make, salary I deserve, am I underpaid,
  compensation check — not for negotiating offer letters as a lawyer.
---

# Salary you deserve

Combine **what you know about them** with **live market signal**.

## Tools
- `get_market_overview` for role + location salary signals
- `search_jobs` with similar titles + `salary_min` exploration; read listed salaries
- `get_job_details` on comps with pay disclosed
- `get_job_keywords` optional if matching leveled titles

## Workflow
1. Extract from chat/resume: title(s), years, location, industry, skills, constraints. Ask once if location or current title missing.
2. Map to 1 primary title + 1–2 comps (level up/down).
3. Pull market overview + 2–3 searches of comparable openings with known pay.
4. Produce a range:
   - **Floor** (don’t go below)
   - **Target** (what to ask)
   - **Stretch** (if evidence supports)
5. Say clearly when data is thin or titles don’t match.

## Guardrails
- Never invent salary numbers — every figure must come from tool results or user-stated current pay.
- Label currency and period (annual vs hourly).
- This is market guidance, not a formal compensation audit.

## Output
Range + 3 comparable live jobs + one-sentence negotiation tip.
