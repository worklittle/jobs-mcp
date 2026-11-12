---
name: apply-to-jobs-instantly
description: >-
  Apply to jobs straight from the chat: pick the job, confirm, and Worklittle fills out
  the employer's application. Use for apply for me, apply to this job, send my application,
  apply to these — not for browsing jobs only (use job-search) or writing a resume.
---

# Apply to jobs instantly

## Tools
`search_jobs` / `get_job_details` → `get_my_resume` → `apply_for_job` → `check_application_status`
(`submit_application`, `steer_application`, `list_applications`, `list_active_applications`, `stop_application`, `upload_my_resume` as needed)

## Workflow
1. **Find the job.** Use the job the user named or the one from the last search. Read `get_job_details` right before applying; a closed job should not be applied to.
2. **Check eligibility.** Every `search_jobs` result can be applied to. For a job from anywhere else, `can_apply` on `get_job_details` is the only check. Do not guess from the employer's site. If it is false, give the job's `apply_url` and say the user applies there.
3. **Check the resume.** `get_my_resume`. If it is missing, ask the user to attach one, save it with `upload_my_resume`, then continue.
4. **Confirm once.** Applying submits a real application. Say the job title and company, then start only after the user agrees. A clear "apply to this" already counts.
5. **Start.** `apply_for_job` with the `job_id`. Share the live view link so the user can watch. It submits by default (the user's `auto_submit` setting). If the user wants to review first, pass `auto_submit: false`.
6. **Follow through.** `check_application_status` until it ends. Only `completed` means submitted. If it is waiting on the user (`awaiting_input`), ask the user the question and pass the answer with `steer_application`. If it stopped for review (`awaiting_submit`), show the answers and call `submit_application` only after the user says to send it. Say plainly when it failed.

## Rules
- Applying to the same job twice is safe: `apply_for_job` returns `already_applied: true` and is not billed. Check `list_applications` first so you can tell the user it was already sent.
- Never invent answers, employers, or experience. Use the saved resumes and profile only; ask when something is unknown.
- `stop_application` cancels the application in progress and it cannot be resumed. Use it only when the user asks to stop.
- For several jobs, pass up to 10 at once as `job_ids` and report each result.

## Output
One line per application: job, company, status, and the link to watch or the original posting.
