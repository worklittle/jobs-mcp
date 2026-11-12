---
name: job-search
description: >-
  Search live Worklittle jobs with advanced filters (role, salary, visa, remote, company,
  recency). Use when the user wants a precise filtered search or technical role hunt — not
  for vibe-based hire-fast lists.
---

# Job search (technical / precise filters)

## Tools
`search_jobs` → `get_job_details`

## Rules
- Role text in `query`; employers in `company` slugs
- Recency → `posted_within_days` (not stuffed into query)
- Visa → `visa_sponsorship: "yes"`
- Remote only → `remote: true` (plus `country` to keep it to one country); no city or radius
- Place → `near_lat`/`near_lng` + `radius_km` for a city, `state` for a US state, `country` for a country
- Salary floor → `salary_min`
- List rows are snippets — detail before claiming requirements
- `limit` 10–20; paginate with `cursor` + `exclude_ids`

## Output
Ranked shortlist with why each matches the filters.
