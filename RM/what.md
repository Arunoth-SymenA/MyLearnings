# What is Release Management in DevOpsArk?

Release Management in DevOpsArk is a module used to create, plan, coordinate, and execute releases in a structured and controlled manner.

It is exposed within the app as the Release Management section and provides:

- A release list screen with centralized tracking
- A create release flow
- Task-based execution within each release
- Acceptance and confirmation workflows
- Release detail view with timeline, tasks, and status tracking

## What users can configure

From the create/update flows, users can define:

- Release name
- Release type (Normal or Emergency)
- Planned start date and time
- Planned end date and time
- Release notes (optional)
- Rollback plan (optional)

Within each release, users can configure:

- Task title and description
- Task assignee (user or group)
- Task start date and time
- Task-level execution details

## What operations exist

The module supports structured release lifecycle operations:

- Create a new release
- View and manage release details
- Add and manage tasks within a release
- Send Acceptance Mail for task approval
- Send Confirmation Mail after task acceptance
- Track task and release status
- Update release stage (Draft → Ready → In Progress → Closed)
- Close release as Complete or Incomplete

## What this module is in product terms

This Release Management module is the release lifecycle management system inside DevOpsArk:

- **Plan** releases with timelines and configurations
- **Organize** work through task assignment and ownership
- **Control** execution via acceptance and confirmation workflows
- **Track** progress with clear status transitions
- **Complete** releases with structured closure outcomes
