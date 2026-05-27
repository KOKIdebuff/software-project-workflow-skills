# Software Project Workflow Skills

Reusable Agent Skills for practical software project decisions: prioritization,
delivery risk, blockers, and maintainable execution order.

[GitHub Repository](https://github.com/KOKIdebuff/software-project-workflow-skills) |
[Prioritize Dev Tasks on ClawHub](https://clawhub.ai/kokidebuff/prioritize-dev-tasks) |
[MIT-0 License](LICENSE)

## Why This Project Exists

Software teams rarely fail because they cannot write a backlog. They struggle
because a backlog mixes very different kinds of work:

- A security vulnerability next to a visual adjustment
- A release blocker next to a useful but deferrable performance improvement
- A dependency that blocks several people next to a task with a loud deadline
- Technical debt that matters, but does not need to interrupt today's release

A simple "urgent / not urgent" sort can produce unsafe decisions. This
collection provides reusable skills that help an AI assistant reason like a
careful engineering collaborator: identify real risk first, expose
dependencies, protect the current delivery goal, and explicitly name work that
can wait.

## Available Skill

### `prioritize-dev-tasks`

**Prioritize unfinished software development work using risk, blocking
relationships, delivery objectives, and effort-to-value judgment.**

| Item | Details |
|---|---|
| Canonical source | [`skills/prioritize-dev-tasks/SKILL.md`](skills/prioritize-dev-tasks/SKILL.md) |
| Marketplace | [ClawHub: Prioritize Dev Tasks](https://clawhub.ai/kokidebuff/prioritize-dev-tasks) |
| Release | `v1.0.0` |
| Language behavior | The distributed instructions are English; the skill answers in the user's language. |

Use this skill for:

- Backlog prioritization
- Bug triage before a release
- Sprint execution ordering
- Technical-debt planning
- Release-readiness task review
- Requirement-pool cleanup
- Identifying tasks to defer, merge, or remove

## What The Skill Does

The skill accepts a detailed project status or a rough task list. It then:

1. Identifies the project phase and current version objective.
2. Detects security, data, production, release, and collaboration risks that
   should override ordinary scheduling.
3. Assesses each task by business impact, urgency, blocking, risk, cost and
   value, and dependency order.
4. Presents a four-quadrant classification for clarity.
5. Produces an actual execution order driven by risk and dependencies, not
   merely quadrant names.
6. Names blockers and the work they prevent.
7. Names work that can be deferred, merged, time-boxed, or removed.
8. Asks only for missing facts that could materially change the ranking.

This matters because classification and execution order are not always the
same. Two tasks can both be "important and urgent", while one must happen
first because it unlocks testing, integration, or safe release approval.

## Decision Model

The skill uses an Eisenhower-style quadrant view as a communication tool, but
does not use it as a simplistic scoring algorithm. Actual execution order
follows this precedence:

| Priority Driver | Examples | Expected Treatment |
|---|---|---|
| Security and data safety | Authorization bypass, data corruption, sensitive-data exposure, incorrect monetary records | Treat as highest-priority candidates unless risk is demonstrably isolated |
| Production or core-flow availability | Checkout unavailable, core API continually failing, application crash | Restore safe usability first |
| Delivery and collaboration blockers | Deployment pipeline broken, acceptance blocked, API contract blocking multiple clients | Remove the blocker early to restore progress |
| Current version objective | MVP-critical feature, required demo path, committed release scope | Prioritize after immediate risk and blockage |
| Cost-to-value ratio | Small fix unblocks several people; costly enhancement has weak present value | Prefer work that releases meaningful value or constraint |
| Polish and future improvement | Cosmetic changes, speculative features, premature optimization | Defer unless directly required for delivery |

### Mandatory Escalation Signals

The skill is designed to conservatively elevate work involving:

- Data loss, corruption, or money-impacting data errors
- Authorization bypass, privilege escalation, or sensitive-data exposure
- Production crashes or unavailable core flows
- Completely blocked build, deployment, acceptance, or release processes
- Tasks blocking multiple developers, integration, or critical tests
- Failures with no practical rollback or unusually costly rollback

These signals prevent serious defects from being ranked below low-risk work
simply because that work is faster or has a visible deadline.

### Four-Quadrant Presentation

| Quadrant | Interpretation | Typical Action |
|---|---|---|
| Important and urgent | Core objective, severe risk, or active blockage requires action now | Handle immediately or reduce to the minimum safe fix |
| Important but not urgent | Reliability, quality, or future efficiency matters without blocking today | Put into an explicit sprint or scheduled time block |
| Urgent but not important | Timing pressure exists, but impact is limited or a workaround exists | Time-box, delegate, or simplify |
| Neither important nor urgent | Weak connection to current objectives and limited value | Defer, merge, return to the pool, or remove |

## Inputs And Outputs

### Minimal Input Works

Users can paste only a list:

```text
Use $prioritize-dev-tasks to prioritize these tasks:
- Fix export permission bypass
- Repair deployment pipeline
- Tune account page button spacing
```

When information is missing, the skill gives a preliminary judgment, clearly
marks uncertainty, and avoids inventing deadlines, impact, cost, or
dependencies.

### More Context Improves Accuracy

For a more actionable result, include:

```text
Project phase:
Current version objective:
Release or demo date:

Tasks:
1. Task name
   - Impact:
   - What it blocks:
   - Consequence if skipped:
   - Estimated effort:
   - Current status:
```

### Output Shape

For small, low-risk lists, the skill uses a compact answer:

- Overall judgment
- Ranked task table
- Blockers and deferrals
- Only the critical questions still worth confirming

For release, security, data, production, or multi-person blocking situations,
it expands the response:

- Overall risk and version-goal judgment
- Four-quadrant classification table
- Up to three highest-priority items
- Explicit blocking relationships
- Defer, merge, or remove candidates
- Recommended execution sequence
- Only material information gaps

## Example: Release Readiness

Input:

```text
Use $prioritize-dev-tasks to prioritize tomorrow's release tasks:
- Fix an authorization bypass allowing cross-tenant exports
- Repair a deployment pipeline failure preventing staging promotion
- Update spacing and hover colors on the settings page
- Add an index for a slow but usable reporting view
```

Expected result:

| Order | Task Type | Why |
|---|---|---|
| 1 | Authorization bypass | Direct security and tenant-data exposure risk |
| 2 | Deployment pipeline failure | Blocks release validation and promotion |
| 3 | Reporting index | Useful but not currently blocking if the page remains usable |
| 4 | Visual styling | Cosmetic work unrelated to safe release |

The answer should also identify the release blocker, recommend deferring
visual polish, and ask whether the authorization risk has already been
isolated if that fact was not provided.

More evaluation fixtures:

| Scenario | Fixture | What It Tests |
|---|---|---|
| Security and release blocking | [`release-blockers.md`](examples/prioritize-dev-tasks/release-blockers.md) | High-risk escalation and cosmetic deferral |
| Dependency-aware sprint ordering | [`sprint-backlog.md`](examples/prioritize-dev-tasks/sprint-backlog.md) | Sequencing work that unlocks other tasks |
| Planned technical debt | [`technical-debt.md`](examples/prioritize-dev-tasks/technical-debt.md) | Avoiding fabricated urgency |
| Chinese-language request | [`chinese-request.md`](examples/prioritize-dev-tasks/chinese-request.md) | Returning the analysis in the user's language |

## Installation And Platform Support

One canonical `SKILL.md` is used across platforms. Product-specific setup is
kept outside the decision rules so the skill does not drift between
ecosystems.

| Platform | Support Level | Installation Guide |
|---|---|---|
| Codex | Structure and behavioral scenarios tested | [Install for Codex](docs/install-codex.md) |
| Claude Code | Compatible with its Skills directory format; runtime test pending | [Install for Claude Code](docs/install-claude-code.md) |
| OpenClaw | Published on ClawHub; runtime test pending | [Install for OpenClaw](docs/install-openclaw.md) |
| Hermes Agent | Compatible with GitHub tap layout; runtime test pending | [Install for Hermes](docs/install-hermes.md) |

### Codex Invocation

```text
Use $prioritize-dev-tasks to classify this backlog and recommend the actual execution order.
```

### OpenClaw Marketplace

The first published skill is available at:

[https://clawhub.ai/kokidebuff/prioritize-dev-tasks](https://clawhub.ai/kokidebuff/prioritize-dev-tasks)

## Quality And Validation

This repository treats task prioritization as a decision-quality problem, not
only a prompt-writing exercise.

The current release has been checked for:

- Valid Codex Skill structure and frontmatter
- Codex behavior on security and release blockers
- Dependency-aware ordering in an integration sprint
- A technical-debt scenario where not every task should become urgent
- A Chinese-language scenario where the English-distributed skill responds in
  Chinese
- Separation between the portable skill source and Codex-only UI metadata

Behavioral acceptance criteria are documented in
[`tests/prioritize-dev-tasks/evaluation-cases.md`](tests/prioritize-dev-tasks/evaluation-cases.md).

The repository deliberately does **not** claim runtime testing in Claude Code,
OpenClaw, or Hermes Agent until those platform runs have actually been
performed.

## Repository Design

```text
software-project-workflow-skills/
├── skills/
│   └── prioritize-dev-tasks/
│       ├── SKILL.md              # Canonical portable behavior
│       ├── .clawhubignore        # Excludes product-specific publish metadata
│       └── agents/
│           └── openai.yaml       # Codex-facing display metadata
├── docs/                         # Per-platform installation guides
├── examples/                     # Human-readable usage and evaluation inputs
├── tests/                        # Behavioral acceptance criteria
├── CONTRIBUTING.md
└── LICENSE
```

### Single-Source Policy

`skills/<skill-name>/SKILL.md` is the only authoritative behavior definition
for each skill. Platform documentation may explain installation and testing,
but should not fork or duplicate the decision rules. This keeps future
maintenance auditable when more workflow skills are added.

## Future Series Direction

This repository is structured to grow into a focused software project workflow
series. Potential additions may include:

- Release-risk auditing
- Technical-debt assessment
- Sprint planning
- Project progress audits
- Requirement breakdown

New skills should be introduced only when they solve a distinct recurring
workflow problem and include behavioral examples and acceptance criteria.

## Contributing

Contributions, issue reports, and practical backlog examples are welcome.
Before proposing a change:

1. Read [CONTRIBUTING.md](CONTRIBUTING.md).
2. Keep each skill focused and portable.
3. Add or update an evaluation case when changing decision behavior.
4. Avoid claims of platform support that have not been runtime-verified.

## License

This repository is distributed under the [MIT-0 License](LICENSE). Skills
published through ClawHub are also distributed under MIT-0 under ClawHub's
publication policy.
