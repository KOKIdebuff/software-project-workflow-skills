# Install For Hermes Agent

Hermes supports reusable Skill directories sourced from GitHub taps. This
repository uses a `skills/<skill-name>/SKILL.md` layout suitable for that
distribution model. The v1 release documents structural compatibility without
claiming local Hermes runtime verification.

## Install From A GitHub Tap

```bash
hermes skills tap add KOKIdebuff/software-project-workflow-skills
hermes skills install KOKIdebuff/software-project-workflow-skills/skills/prioritize-dev-tasks
```

The first command adds the series repository as a tap. The second command uses
Hermes's documented direct repository-path form to install this specific
skill.

## Invoke

```text
Use prioritize-dev-tasks to identify the blockers in this release backlog and give a safe development order.
```

## Verify

Use a mixed backlog containing a deployment failure, a technical-debt item,
and a UI enhancement. The response should resolve blocking work first and
identify deferrable work.
