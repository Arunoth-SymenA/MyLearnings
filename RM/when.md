# When to use Release Management in DevOpsArk

Use the Release Management module whenever you need to coordinate deployment activities that involve multiple people, groups, or specific timelines.

## Best-fit scenarios
- You have a scheduled production rollout and need a reliable way to assign and track tasks.
- You are handling an emergency fix and need to document sub-tasks and the rollback plan.
- You need a documented audit trail tracked via task acceptance status and confirmation mails.

## When to use each primary action
- **Create (`CreateRelease` / `CreateTaskRelease`):** Starting a new tracked rollout and initially assigning work.
- **Acceptance Mail (`SendTaskAcceptanceEmail`):** When all tasks are drafted and you need assignees to formally acknowledge responsibility.
- **Confirmation Mail (`SendConfirmationEmail`):** After tasks are accepted to move the overall release status.
- **Progress Updates (`UpdateRelease` / `UpdateTaskRelease`):** For transitioning between Draft -> Ready -> In Progress -> Closed.
- **Delete (`DeleteRelease` / `DeleteTaskRelease`):** For test cleanup or aborting invalid rollout plans.
