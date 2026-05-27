# Software Project Workflow Skills

Reusable Agent Skills for practical software project workflow decisions. The
collection focuses on delivery risk, dependency blocking, engineering
priorities, and maintainable execution plans.

Repository: [KOKIdebuff/software-project-workflow-skills](https://github.com/KOKIdebuff/software-project-workflow-skills)

## Included Skill

| Skill | Purpose | Status |
|---|---|---|
| [`prioritize-dev-tasks`](skills/prioritize-dev-tasks/SKILL.md) | Prioritize backlogs, bugs, technical debt, and release blockers by risk, dependencies, and value. | v1.0.0 |

`prioritize-dev-tasks` uses an Eisenhower-style quadrant view for presentation,
while its execution order is driven by security and data risk, production
impact, release blockers, dependencies, and version goals.

## Supported Platforms

The core skill is a single portable `SKILL.md` source.

| Platform | Support level | Installation |
|---|---|---|
| Codex | Tested target | [Install for Codex](docs/install-codex.md) |
| Claude Code | Structure-compatible with official Skills layout | [Install for Claude Code](docs/install-claude-code.md) |
| OpenClaw | Structure-compatible; ClawHub publication pending | [Install for OpenClaw](docs/install-openclaw.md) |
| Hermes Agent | Structure-compatible with GitHub tap installation | [Install for Hermes](docs/install-hermes.md) |

The skill instructions are written in English for portable distribution. The
skill must answer in the language used by the user, so Chinese and other
non-English requests remain supported.

## Quick Example

Invoke the skill with a task list:

```text
Use $prioritize-dev-tasks to prioritize the following release tasks and
recommend an execution order:
- Fix a permission bypass in the admin export endpoint
- Repair the CI deployment pipeline, which blocks release
- Adjust spacing on the profile settings page
```

Expected behavior: security and release-blocking work is promoted above visual
polish, blockers are identified, and low-value work is explicitly deferred.

## Repository Layout

```text
skills/      Portable skill sources
docs/        Platform installation instructions
examples/    Example task inputs for evaluation and demonstration
tests/       Behavioral acceptance cases
```

Each capability has one canonical `SKILL.md`. Platform-specific instructions
and Codex UI metadata do not duplicate the decision rules.

## Contributing

Contributions are welcome. Read [CONTRIBUTING.md](CONTRIBUTING.md) before
proposing a skill or changing behavior. Changes to decision rules should add
or update a behavioral evaluation case.

## License

This repository is released under [MIT-0](LICENSE). Skills published to
ClawHub are also distributed under MIT-0 under ClawHub's publication policy.
