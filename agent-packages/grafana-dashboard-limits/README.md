# grafana-dashboard-limits

An APM package that teaches the agent to overlay CPU and memory resource
limits onto Grafana resource-usage panels, using
`kube_pod_container_resource_limits` as a red reference line.

## Install

```sh
apm install Netcracker/qubership-istio/agent-packages/grafana-dashboard-limits --target claude
```

This deploys the package's primitives into the consuming repo
(`.claude/skills/`, `.claude/commands/`, `.claude/rules/`, and the
merged `CLAUDE.md`). Re-run it to pick up a new version.

## What you get

- An instruction that fires when you edit a Grafana dashboard `*.json`
  to add resource-limit overlays.
- The [`SKILL.md`](.apm/skills/grafana-dashboard-limits/SKILL.md) — how
  to identify the CPU/memory panels, add the limit targets, and style
  them as red reference lines while leaving the rest of the dashboard
  untouched.
- A [`/add-grafana-dashboard-limits`](.apm/prompts/add-grafana-dashboard-limits.prompt.md)
  slash command to run the migration on demand against a dashboard URL,
  file path, or pasted JSON.

## Usage

On demand — run the slash command with a dashboard URL, repo file path,
or pasted JSON:

```text
/add-grafana-dashboard-limits helm-templates/qubership-istio/dashboards/
```

Automatic — the instruction triggers the skill on its own whenever you
ask the agent to add resource limits while it's working on a Grafana
dashboard `*.json`, so no command is required.

Either path produces the same change: a `kube_pod_container_resource_limits`
target on the Memory Usage and CPU Usage panels, styled as a thin red
reference line, with every other panel and all top-level fields left
untouched.
