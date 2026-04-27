# Where Release Management lives and where each operation is handled

This is a location guide for the Release Management module and its key operations.

## Main frontend locations

- App root and routing: `frontend/src/App.tsx`
- Release list page: `frontend/src/pages/release/index.tsx`
- Release page helper/GraphQL utilities: `frontend/src/pages/release/handler.ts`
- Release detail page: `frontend/src/pages/release/ReleaseDetail.tsx`
- Create release modal/page: `frontend/src/components/release/AddReleaseModal.tsx`
- Task creation modal: `frontend/src/components/release/AddTaskModal.tsx`
- Update/interaction components: `frontend/src/components/release/*`
- GraphQL/Apollo client setup: `frontend/src/utils/apolloClient.ts`

## Where each major operation is handled

- Create release  
  Handled in create release modal (`AddReleaseModal.tsx`)

- View releases (list)  
  Handled in `frontend/src/pages/release/index.tsx`

- View release details  
  Handled in `frontend/src/pages/release/ReleaseDetail.tsx`

- Add/manage tasks  
  Handled within release detail page and task modal components

- Acceptance flow (Acceptance Mail)  
  Triggered from release detail/task view actions

- Confirmation flow (Confirmation Mail)  
  Triggered after all tasks are accepted within release detail view

- Release status updates  
  Managed in release detail page (stage transitions)

## Where users interact in UI

- **List and actions:** Release main screen (Release dashboard)
- **Details:** release-specific screen (selected release view)
- **Tasks:** managed inside the release detail page
- **My Tasks:** user-specific assigned tasks view
- **Mutations:** create release, add tasks, send mails, and update status from UI actions

## Where this module sits in DevOpsArk

Release Management is a dedicated module integrated into DevOpsArk, typically available as its own section in the platform.

It is built using shared DevOpsArk UI components such as:

- `Navbar`
- `Sidebar`
- `Table`
- `Form/Modal components`

and follows the same design and interaction patterns as other modules for consistency.
