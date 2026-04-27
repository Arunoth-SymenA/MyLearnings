# Where Dashboard lives and where its components are

This is a location guide for the Dashboard frontend implementation and its key dependencies.

## Main frontend locations

- App root and routing: `frontend/src/App.tsx` and `frontend/src/main.tsx`
- Dashboard main pages: 
  - `frontend/src/pages/Dashboard.tsx`
  - `frontend/src/pages/NewDashboard.tsx`
- Dashboard sub-components: `frontend/src/pages/DashboardContent/`
- Reusable UI cards: `frontend/src/components/DashBoard-card/`
- Quick Onboard wizard: `frontend/src/pages/QuickonboardProject/`
- GraphQL/Apollo client setup (for live feeds): `frontend/src/utils/apolloClient.ts`
- External Design Library: `@devopsark/design` (provides Navbar and Sidebar)

## Where navigation commands point

The Quick Actions grid navigates to various sibling modules within the `src/pages/` directory:

- `Add ArkApp` -> `frontend/src/pages/AddArkapp/AddArkappPage.tsx`
- `Add ArkBuilder` -> `frontend/src/pages/AddBuilder/AddArkbuilderPage.tsx`
- `Add Cluster` -> `frontend/src/pages/AddCluster/AddKubernetesClusterPage.tsx`
- `Quick Onboard` -> `frontend/src/pages/QuickonboardProject/Quickonboard.tsx`

## Where users interact in UI

- **Global Navigation:** The top navbar allows switching the Organization context, which impacts the Dashboard's scope.
- **Left Column:** Users view aggregate metric badges.
- **Center Column:** Users click Quick Action buttons to initiate CRUD workflows.
- **Right Column:** Users interact with plan details and view recent active team members.
- **Change Feed:** Provides read-only, live scrolling updates of platform events.

## Where this module sits in DevOpsArk

The Dashboard is the default entry point of the application (`/dashboard/`). Unlike localized resource modules (like FAAS), it wraps the entire application context, sitting structurally beneath the global Redux and Apollo Providers as defined in `App.tsx`.
