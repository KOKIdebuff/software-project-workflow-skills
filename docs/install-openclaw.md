# Install For OpenClaw

`prioritize-dev-tasks` is structured as an Agent Skill for OpenClaw and is
prepared for distribution through ClawHub. The repository records format
compatibility; OpenClaw runtime testing is not part of the initial local
verification.

## Install From ClawHub

After the initial market release:

```bash
openclaw skills install prioritize-dev-tasks
```

OpenClaw recommends its native command for discovering and installing skills.
The separate `clawhub` CLI below is for publisher-authenticated workflows.

## Publish From This Repository

Maintainers publish only the canonical skill directory:

```bash
clawhub skill publish ./skills/prioritize-dev-tasks \
  --slug prioritize-dev-tasks \
  --name "Prioritize Dev Tasks" \
  --version 1.0.0 \
  --changelog "Initial release" \
  --tags latest
```

The local `.clawhubignore` omits Codex-specific `agents/` metadata from the
market package. ClawHub publications are distributed under MIT-0.

## Verify

Run the release-blocker example after installation. Security and
release-blocking tasks must rank ahead of cosmetic enhancements.
