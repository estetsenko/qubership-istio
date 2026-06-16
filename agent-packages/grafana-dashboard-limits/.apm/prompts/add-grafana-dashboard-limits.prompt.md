---
description: Overlay CPU/memory resource limits onto a Grafana dashboard's resource-usage panels.
argument-hint: <dashboard URL | file path | pasted JSON>
---

Apply the `grafana-dashboard-limits` skill to add resource-limit overlays
to a Grafana dashboard.

Dashboard source: $ARGUMENTS

If no source was given above, ask which dashboard to adapt (a URL, a repo
file path, or pasted JSON), then obtain the JSON and apply the skill's
procedure to it.
