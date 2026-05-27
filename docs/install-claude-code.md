# Install For Claude Code

The skill uses the portable `SKILL.md` directory format supported by Claude
Code Skills. This repository records format compatibility; the v1 release has
not been runtime-tested in Claude Code.

## Install

Clone this repository and copy the canonical skill folder into your Claude
skills directory:

```bash
mkdir -p ~/.claude/skills
cp -R ./skills/prioritize-dev-tasks ~/.claude/skills/prioritize-dev-tasks
```

For a project-only installation, place the same directory under the project's
`.claude/skills/` folder instead.

## Invoke

```text
Use the prioritize-dev-tasks skill to classify this sprint backlog and give me the actual execution order.
```

## Compatibility Note

The reusable behavior lives only in
`skills/prioritize-dev-tasks/SKILL.md`. The `agents/openai.yaml` file is Codex
UI metadata and is not required for Claude Code behavior.
