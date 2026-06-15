---
description: Overlay CPU/memory resource limits onto a Grafana dashboard's resource-usage panels.
argument-hint: <dashboard URL | file path | pasted JSON>
---

Apply the `add-grafana-dashboard-limits` skill to add resource-limit overlays
to a Grafana dashboard.

Dashboard source: $ARGUMENTS

If no source was given above, ask which dashboard to adapt (a URL, a repo
file path, or pasted JSON).

Follow the skill exactly:

1. Obtain the dashboard JSON from the source.
2. Identify the Memory Usage and CPU Usage panels, and copy the
   `container` / `pod` selectors from their existing targets.
3. Add the memory and CPU `kube_pod_container_resource_limits` targets
   (next unused `refId`) plus the matching red, unfilled
   `byFrameRefID` overrides.
4. Leave every other panel and all top-level fields untouched.
5. Write the adapted JSON back to its source file and report the panels
   and `refId`s you changed.
