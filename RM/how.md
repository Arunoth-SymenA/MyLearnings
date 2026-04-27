# How Release Management works (End-to-End Flow)

This document explains the step-by-step frontend workflow mapping to the GraphQL tier.

## 1) Initialization (The Draft Stage)
1. User clicks **Add New Release**, triggering the `AddModal`.
2. Upon saving valid input (Dates, Name, Note, Rollback), the frontend fires `CreateRelease(input)`. 
3. The table refreshes via `listreleasebyparent()`. The release is placed in the **Draft** stage.

## 2) Task Assignment
1. Selecting the release routes the user to the Task List.
2. Clicking 'Add Task' opens a modal. Saving fires `CreateTaskRelease(input)` to bind sub-tasks to the specific release.

## 3) Acceptance Workflow
1. Once ready, the user triggers the "Send Acceptance Mail", firing the `SendTaskAcceptanceEmail` mutation.
2. Assignees locate their assignments via `listtaskReleasebytaskAssignedToPerson` in the **My Tasks** screen.
3. Upon accepting, `UpdateTaskRelease(input)` changes the specific task status from Draft to **Accepted**.
4. With all sub-tasks accepted, the UI unlocks the **Send Confirmation Mail** action (`SendConfirmationEmail`). Success shifts overall tasks to **Accepted**.

## 4) Execution (Ready to Closed)
1. Returning to the main Release page, the stage becomes **Ready**.
2. To begin, the user selects **In Progress**, which triggers `UpdateRelease` (and optionally `SendProgressEmail`) to inform stakeholders.
3. Upon finishing the release activities, the user closes it out using `UpdateRelease`, designating it as **Closed Complete** or **Closed Incomplete**.
