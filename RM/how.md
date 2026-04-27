# How Release Management works (Frontend perspective)

This document explains the end-to-end frontend flow using screens, interactions, and lifecycle stages.

## 1) App routing and entry points

- Release Management is accessible within the main DevOpsArk app.
- Release list page opens the main dashboard.
- Selecting a release opens the release detail page.

## 2) List page flow

On load, the release list page:

1. Fetches all releases for the selected project/context.
2. Displays them in a table with status and timeline.
3. Allows selection for viewing and actions.

The list page provides actions:

- **Add New Release** -> opens create release form/modal  
- **Select Release** -> navigates to release detail page  

## 3) Create flow (Release creation)

In the create release form:

1. User enters:
   - Release name  
   - Release type (Normal/Emergency)  
   - Start and end date/time  
   - Optional notes and rollback plan  
2. UI validates required fields.
3. On save, release is created in **Draft** stage.
4. Release appears in the list and is ready for further configuration.

## 4) Task management flow

Inside the release detail page:

1. User adds tasks with:
   - Title and description  
   - Assignee (user/group)  
   - Schedule (start date/time)  
2. Tasks are listed and tracked within the release.
3. Users can view assigned tasks under **My Tasks**.

## 5) Acceptance flow

1. User triggers **Acceptance Mail**.
2. Assigned users receive and accept tasks.
3. Task status moves from **Draft → Accepted**.
4. System ensures all tasks are accepted before proceeding.

## 6) Confirmation flow

1. Once all tasks are accepted, **Confirmation Mail** becomes available.
2. User sends confirmation.
3. Upon acceptance, overall task/release readiness is confirmed.

## 7) Execution flow

1. Release stage moves from **Draft → Ready**.
2. User starts the release by marking it **In Progress**.
3. Tasks are executed and progress is tracked.

## 8) Tracking and visibility

- Users monitor assigned work via **My Tasks**.
- Release detail page shows:
  - Task statuses  
  - Overall release stage  
  - Timeline progress  

## 9) Closure flow

After execution:

1. User selects closure status:
   - **Closed Complete** (all tasks successfully done)  
   - **Closed Incomplete** (partial or failed execution)  
2. Release stage updates accordingly.
3. Release is finalized and recorded.

## 10) Supporting UX behavior

- Table-based release listing with status indicators  
- Form-based creation and task assignment  
- Stage-based workflow visibility  
- Mail-triggered approval system (Acceptance & Confirmation)  
- Real-time status updates across tasks and releases  
- Clear lifecycle transitions for controlled execution
