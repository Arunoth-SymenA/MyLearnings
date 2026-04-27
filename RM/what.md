# What is Release Management in DevOpsArk?

Release Management is a centralized module designed to help teams plan, coordinate, track, and execute releases efficiently. It ensures that all tasks, teams, and timelines are aligned, making the release process more structured, transparent, and reliable.

## What users can configure

When creating or managing a release, users can define:
- Release Name
- Release Type (`Normal` or `Emergency`)
- Planned Start Date and Time
- Planned End Date and Time
- Release Notes (Optional)
- Rollback Plan (Optional)

## What data operations exist

The frontend uses GraphQL to operate on releases, tasks, and communications:

**Release Operations:**
- `listreleasebyparent` to load project-scoped releases
- `CreateRelease` to create a new release
- `UpdateRelease` to update an existing release or change its stage
- `DeleteRelease` to safely purge selected release(s)

**Task Operations:**
- `listtaskReleasebyparent` to fetch tasks scoped to a specific release
- `listtaskReleasebytaskAssignedToPerson` to fetch tasks specifically for the "My Tasks" view
- `CreateTaskRelease` to create new tasks under a release
- `UpdateTaskRelease` to update task data (e.g., status changes like Accepted)
- `DeleteTaskRelease` to purge task(s)

**Workflow Operations:**
- `SendTaskAcceptanceEmail` to notify assignees to accept their tasks
- `SendConfirmationEmail` to finalize acceptance
- `SendProgressEmail` to notify stakeholders when the release moves In Progress
