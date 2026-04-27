# How Dashboard works (Frontend perspective)

This document explains the end-to-end frontend flow of the Dashboard using screens, layout components, and GraphQL data integration.

## 1) App routing and entry points

- App basename is `/dashboard`.
- Route `/` renders the `<Dashboard />` component.
- Route `/Dash-board` renders the `<NewDashboard />` component.
- Surrounding these routes are the global layout wrappers: `<Navbar />` and `<Sidebar />` mapping.

## 2) Dashboard layout flow

On load, the Dashboard page:

1. Renders the global `@devopsark/design` layout (Navbar/Sidebar).
2. Reads the organizational context to scope metrics to the current environment.
3. Fetches summary counts for ArkApps, ArkBuilders, Clusters, Scanners, Certificates, and Users.
4. Mounts the real-time WebSocket connection to populate the Change Feed.

The page is visually divided into three main columns:
- **Left:** Summary cards for resources (rendered via `DashBoard-card` components) and the Change Feed.
- **Center:** Quick Actions navigation grid.
- **Right:** Subscription, user seat limit chart, and recent members list.

## 3) Real-time Data Flow (Change Feed)

The Change Feed relies on GraphQL subscriptions:

1. `apolloClient.ts` initializes a `GraphQLWsLink` targeting `wss://<host>/graphql`.
2. The Dashboard component subscribes to platform events.
3. As events (e.g., "New Arkapp UPDATED") are emitted by the backend, the WebSocket pushes them to the client.
4. The UI conditionally renders a "LIVE!" badge and updates the list dynamically (e.g., showing "5 seconds ago").

## 4) Quick Actions Navigation Flow

In the Quick Actions grid:

1. Each card acts as a router link or action dispatcher.
2. Clicking an action (e.g., "Add Cluster") navigates the browser to the dedicated route (`/add-cluster`).
3. For highly integrated flows, such as "Quick Onboard", it triggers `/quick-onboard` which mounts the `QuickonboardProject` wizard interface.

## 5) Supporting UX behavior

- **Browser Validation Suppression:** The app mounts an effect in `App.tsx` that removes native HTML5 validation tooltips to enforce custom, consistent DevOpsArk UI validations.
- **Context Preservation:** Top-level UI components (like Navbar) preserve the organization selection so that navigating out of the Dashboard maintains the right backend data scope.
- **Visual Cues:** Hover states on Quick Action tiles and dynamic timestamp formatting (e.g., "1 hours ago") in the Change Feed.
