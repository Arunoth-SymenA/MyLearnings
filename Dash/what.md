# What is the Dashboard in DevOpsArk?

The Dashboard in DevOpsArk is the primary frontend landing module designed to provide a centralized, high-level overview of all cloud and platform resources within a selected organization or project.

It is exposed in the app at the root route (`/`) and as `/Dash-board`, providing:

- Live statistical summary cards for active resources (ArkApps, ArkBuilders, Clusters, Scanners, etc.)
- A real-time "Change Feed" showing live system events
- A "Quick Actions" grid for rapid navigation to creation flows
- User and subscription usage metrics in a unified view

## What users can see and interact with

From the Dashboard interface, users can:

- View aggregate counts of ArkApps, ArkBuilders, Kubernetes Clusters, Scanners, Certificates, and Users & Groups.
- Monitor real-time activity (e.g., "New User LOGIN", "New Arkapp UPDATED") via the live feed.
- Trigger "Quick Onboard" workflows or directly navigate to add resources (`Add ArkApp`, `Add ArkBuilder`, `Add Cluster`, etc.).
- Check their current DevOpsArk plan, accepted member counts, and seat limits.
- Switch organization context from the top navigation bar.

## What data operations exist

The frontend relies mostly on aggregations and realtime subscriptions for the Dashboard:

- Subscriptions/Polling to update the "Change Feed" dynamically without page reloads.
- GraphQL queries to fetch total counts for the summary cards (e.g., retrieving node/pod counts for Clusters, build statuses for ArkBuilders).
- Queries for user profile, organizational plan details, and member seat limits.

## What this module is in product terms

The Dashboard is the operational "single pane of glass" inside DevOpsArk:

- **Monitor** platform vitals across diverse modules from one screen.
- **Navigate** efficiently to cross-functional workflows using Quick Actions.
- **Stay Updated** via real-time notifications about pipeline updates, deployments, and access events.
- **Understand** overall DevOpsArk subscription usage.
