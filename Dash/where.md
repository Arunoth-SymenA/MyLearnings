# Where Dashboard lives and where its components are

This is a location guide for the Dashboard frontend implementation and its key dependencies.

## Where navigation commands point

The Quick Actions grid navigates to various sibling modules within the `src/pages/` directory:

- `Add ArkApp`
- `Add ArkBuilder`
- `Add Cluster`
- `Quick Onboard`

## Where users interact in UI

- **Global Navigation:** The top navbar allows switching the Organization context, which impacts the Dashboard's scope.
- **Left Column:** Users view aggregate metric badges.
- **Center Column:** Users click Quick Action buttons to initiate CRUD workflows.
- **Right Column:** Users interact with plan details and view recent active team members.
- **Change Feed:** Provides read-only, live scrolling updates of platform events.

## Where this module sits in DevOpsArk

The Dashboard is the default entry point of the application (`/dashboard/`). Unlike localized resource modules (like FAAS), it wraps the entire application context, sitting structurally beneath the global Redux and Apollo Providers as defined in `App.tsx`.
