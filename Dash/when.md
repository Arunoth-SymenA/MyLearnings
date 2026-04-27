# When to use the Dashboard in DevOpsArk

Use the Dashboard when your team needs immediate situational awareness of their DevOps resources and a centralized jumping-off point for platform operations.

## Best-fit scenarios

- You have just logged into DevOpsArk and need to check the overall health and status of your project.
- You need to quickly navigate to a specific resource creation form (like a new ArkApp or Kubernetes Cluster) without navigating nested menus.
- You want to monitor recent activities in the platform, such as who recently logged in or what pipelines finished, in real-time.
- You need to check if you are approaching your organization's user seat limit or resource capacity.

## When it is most useful in delivery lifecycle

- **Daily Standups:** Quickly view how many ArkBuilders failed or succeeded recently.
- **Initial Setup:** Using the "Quick Onboard" action to bootstrap a new application and cluster configuration rapidly.
- **Platform Auditing:** Watching the live Change Feed for immediate confirmation that a deployment or configuration update went through.
- **Resource Management:** Checking if you need to scale up your DevOpsArk plan based on seat utilization.

## When to use each primary action

- **Summary Cards (Metrics)**  
  When you need a macro-level count of existing entities (e.g., seeing that there are 47 namespaces and 105 pods active across clusters).

- **Quick Actions Grid**  
  When an operator needs to execute a common provisioning task immediately without relying on the sidebar (e.g., clicking "Add DNS" or "Add Secret").

- **Change Feed**  
  When waiting for asynchronous backend jobs to broadcast their completion status to the frontend.

## Practical rule of thumb

If the task is “get a bird's-eye view of the system or quickly jump to a creation flow,” the Dashboard is the right place to be.
