# Install For Codex

`prioritize-dev-tasks` follows the Codex Skill layout and includes Codex UI
metadata in `agents/openai.yaml`.

## Install

From a clone of this repository, copy the skill directory into the personal
Codex skills directory.

### PowerShell

```powershell
New-Item -ItemType Directory -Force "$HOME\.codex\skills" | Out-Null
Copy-Item -Recurse -Force ".\skills\prioritize-dev-tasks" "$HOME\.codex\skills\prioritize-dev-tasks"
```

### POSIX shell

```bash
mkdir -p ~/.codex/skills
cp -R ./skills/prioritize-dev-tasks ~/.codex/skills/prioritize-dev-tasks
```

Restart or reload Codex after installation if the skill does not appear in the
available skills list immediately.

## Invoke

```text
Use $prioritize-dev-tasks to prioritize these unfinished development tasks and recommend an execution order:
- Repair a release-blocking deployment failure
- Fix a permission bypass in the export API
- Adjust spacing on the profile page
```

## Verify

The response should:

- Rank the permission bypass and deployment blocker ahead of visual polish.
- Identify release or security blockage explicitly.
- Recommend deferring or time-boxing the spacing adjustment.
