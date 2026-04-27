# Where Release Management lives and where tasks are handled

This is a location guide for the Release Management frontend and its GraphQL operations.

## Main frontend locations

- **App root and routing:** `frontend/src/App.tsx` (Route `/releasemanagement`)
- **Release list dashboard:** `frontend/src/pages/releasemanagement/index.tsx`
- **Release/Task Detail View:** `frontend/src/pages/taskRelease/taskRelease/index.tsx`
- **My Tasks View:** `frontend/src/pages/taskRelease/UserTask/UserTaskList.tsx`

## Where each major GraphQL call is used

- `listreleasebyparent`
  Used in `src/pages/releasemanagement/handler.ts` (populating the main release dashboard).
- `CreateRelease`
  Used in `src/components/addModal.tsx`.
- `UpdateRelease`
  Used across `src/components/updateModal.tsx` and stage transitions (like `ReleaseProgressButtonModal`).
- `listtaskReleasebyparent`
  Used in `src/pages/taskRelease/taskRelease/handler.ts` (drilling down into a release).
- `CreateTaskRelease` / `UpdateTaskRelease`
  Used in `taskRelease/addModal/addModal.tsx`, `updateModal.tsx`, and acceptance action modals.
- `listtaskReleasebytaskAssignedToPerson`
  Used in `src/pages/taskRelease/UserTask/handler.ts` for individual workloads.
- Email Mutations (`SendTaskAcceptanceEmail`, `SendConfirmationEmail`, `SendProgressEmail`)
  Triggered from specialized modal components inside `taskRelease/acceptanceModal/` and `confirmationEmail/`.

## Where users interact in UI
The primary flow happens between the main Release List (`/releasemanagement`), drilling down into Task Lists (`/releasemanagement/:releaseID`), and tracking personal obligations on My Tasks. Status transitions happen through modals containing explicit UX (like `acceptanceModal` and `confirmationEmail`).
