# Why the Dashboard exists in DevOpsArk

The Dashboard exists to aggregate operational metadata into a digestible format, preventing users from feeling overwhelmed by the sheer volume of modules and resources within DevOpsArk.

## Core reasons

- **Situational Awareness:** Users shouldn't have to visit five different pages (ArkApp, ArkBuilder, Clusters, etc.) just to know what is currently running and what has recently failed.
- **Workflow Acceleration:** The "Quick Actions" grid provides direct access to creation forms, reducing the "time-to-action" for common tasks like adding a secret or a new cluster.
- **Real-Time Responsiveness:** The live Change Feed gives users immediate feedback that their background operations (like pipeline runs or system logins) are actively being processed by the DevOpsArk platform.
- **Resource Governance:** By surfacing the seat limits and DevOpsArk Plan details right on the home screen, administrators are constantly aware of their subscription utilization.

## Why it is useful for DevOpsArk platform goals

DevOpsArk aims to centralize delivery operations. The Dashboard is the physical manifestation of that centralization:

- It proves the platform's value immediately upon login by showing exactly how much infrastructure is currently being managed.
- It unifies the look and feel by heavily utilizing the internal `@devopsark/design` system to present complex data cleanly.

## Why real-time WebSocket architecture matters here

The dashboard uses the `graphql-ws` setup configured in `apolloClient.ts` to power the Change Feed. 
This is critical because:
- Polling for changes across the entire platform would be API intensive and slow.
- WebSockets provide a true "Live" experience out-of-the-box, ensuring users don't miss transient events (like quick build failures) while they are stationed on the dashboard making administrative decisions.
