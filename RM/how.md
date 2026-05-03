# How Release Management works (End-to-End Flow)

This document explains the step-by-step frontend workflow mapping to the GraphQL tier.

## 3) Acceptance Workflow
1. Once ready, the user triggers the "Send Acceptance Mail", firing the `SendTaskAcceptanceEmail` mutation.
2. Assignees locate their assignments via `listtaskReleasebytaskAssignedToPerson` in the **My Tasks** screen.
3. Upon accepting, `UpdateTaskRelease(input)` changes the specific task status from Draft to **Accepted**.
4. With all sub-tasks accepted, the UI unlocks the **Send Confirmation Mail** action (`SendConfirmationEmail`). Success shifts overall tasks to **Accepted**.

## 4) Execution (Ready to Closed)
1. Returning to the main Release page, the stage becomes **Ready**.
2. To begin, the user selects **In Progress**, which triggers `UpdateRelease` (and optionally `SendProgressEmail`) to inform stakeholders.
3. Upon finishing the release activities, the user closes it out using `UpdateRelease`, designating it as **Closed Complete** or **Closed Incomplete**.
