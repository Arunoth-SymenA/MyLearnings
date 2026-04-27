# Why Release Management exists in DevOpsArk

Release Management exists to bridge the gap between people and technical execution. By organizing people and tracking tasks via explicit GraphQL-backed actions, you guarantee smoother rollouts.

## Core reasons

- **Transparency:** Centralized lists (`listreleasebyparent` and `listtaskReleasebyparent`) provide a single source of truth rather than disconnected chats.
- **Alignment:** Using mutations like `SendTaskAcceptanceEmail` ensures timelines and responsibilities are formally agreed upon before work begins.
- **Operational consistency:** The module uses DevOpsArk's shared primitives (Tables, Modals, Action Buttons), while applying safe bulk mutations (like `DeleteRelease`/`DeleteTaskRelease`) with error handling mapped out to toasts.
