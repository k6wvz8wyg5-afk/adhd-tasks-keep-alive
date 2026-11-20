# Brain Dump keep-alive

Requests only the public health endpoint at https://adhd-tasks.onrender.com/api/health every five minutes, at minutes 2, 7, 12, …, 57. No app code, task data, credentials, checkout, artifacts, caches, or write permissions are used.

Standard GitHub-hosted runners in public repositories are free. This workflow uses `ubuntu-latest`, with no paid services or larger runners. The health request reports failure if the app or its database is unavailable.

## Limits

This reduces idle spin-down; it does not guarantee continuous availability. GitHub schedules can be delayed or dropped, and scheduled workflows in public repositories are disabled after 60 days without repository activity. Re-enable the schedule through Actions when needed; this workflow does not automatically prevent that expiration. Render's free service limits still apply, including 750 shared instance hours per workspace per calendar month. Other free services can consume the same allowance. The workflow can also be started manually through Actions.

Configured scheduling, a successful manual run, and an observed scheduled run are separate verification steps. Check Actions for actual results; the presence of this file alone is not proof of operation.

Sources:
- https://docs.github.com/en/billing/concepts/product-billing/github-actions
- https://docs.github.com/en/actions/reference/workflows-and-actions/events-that-trigger-workflows#schedule
- https://render.com/docs/free
