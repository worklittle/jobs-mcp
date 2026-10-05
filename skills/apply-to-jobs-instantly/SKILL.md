---
name: apply-to-jobs-instantly
description: >-
  Apply to jobs with AI straight from the chat: pick the job, confirm, and Worklittle fills out
  the employer's application. Use for apply for me, apply to this job, send my application,
  apply to these — not for browsing jobs only (use job-search) or writing a resume.
---

# Apply to jobs instantly

## Tools
`search_jobs` / `get_job_details` → `get_my_resume` → `apply_for_job` → `check_application_status`
(`list_active_applications`, `stop_application`, `upload_my_resume` as needed)

## Workflow
1. **Find the job.** Use the job the user named or the one from the last search. Read `get_job_details` right before applying; a closed job should not be applied to.
2. **Check eligibility.** `apply_with_ai_eligible` on the job is the only check. Do not guess from the employer's site. If it is not true, give the job's `apply_url` and say the user applies there.
3. **Check the resume.** `get_my_resume`. If it is missing, ask the user to attach one, save it with `upload_my_resume`, then continue.
4. **Confirm once.** Applying submits a real application. Say the job title and company, then start only after the user agrees. A clear "apply to this" already counts.
5. **Start.** `apply_for_job` with the `job_id`. Share the live view link so the user can watch.
6. **Follow through.** `check_application_status` until it ends. Only `completed` means submitted. If it is waiting on the user (`awaiting_input`), ask the user the question, then continue. Say plainly when it failed.

## Rules
- Never start the same job twice. Check `list_active_applications` or the status first, since a retry can submit a duplicate.
- Never invent answers, employers, or experience. Use the saved resume and profile only; ask when something is unknown.
- `stop_application` cancels the application in progress and it cannot be resumed. Use it only when the user asks to stop.
- For several jobs, apply one at a time and report each result.

## Output
One line per application: job, company, status, and the link to watch or the original posting.
