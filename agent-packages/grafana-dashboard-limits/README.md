# grafana-dashboard-limits

An APM package that teaches the agent to overlay CPU and memory resource
limits onto Grafana resource-usage panels, using
`kube_pod_container_resource_limits` as a red reference line.

## Install

```sh
apm install estetsenko/qubership-istio/agent-packages/grafana-dashboard-limits
```

Or, after registering the marketplace:

```sh
apm marketplace add estetsenko/qubership-istio
apm install grafana-dashboard-limits
```

Then run `apm compile` to merge the trigger into your `AGENTS.md` /
`CLAUDE.md`.

## What you get

- An instruction that fires when you edit a Grafana dashboard `*.json`
  to add resource-limit overlays.
- The [`SKILL.md`](.apm/skills/grafana-dashboard-limits/SKILL.md) — how
  to identify the CPU/memory panels, add the limit targets, and style
  them as red reference lines while leaving the rest of the dashboard
  untouched.
