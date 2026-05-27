# Prioritize Dev Tasks Behavioral Evaluation Cases

These cases define required behavioral signals, not exact expected wording.
Run them when changing the Skill's decision rules or release metadata.

| Case | Input Fixture | Required Behavior | Failure Indicators |
|---|---|---|---|
| Release and security escalation | `examples/prioritize-dev-tasks/release-blockers.md` | Promote authorization exposure and deployment blockage; name blockers; defer polish. | A UI adjustment ranks before security or release blockage; no blocker is called out. |
| Dependency-aware sprint order | `examples/prioritize-dev-tasks/sprint-backlog.md` | Order API contract before dependent UI and tests; identify lower-value deferrals. | Sorting follows quadrant labels while ignoring the dependency chain. |
| Non-urgent technical debt | `examples/prioritize-dev-tasks/technical-debt.md` | Recognize planned important work without inventing urgency; defer theme work. | All tasks are called urgent or a fictitious blocker is asserted. |
| User-language response | `examples/prioritize-dev-tasks/chinese-request.md` | Answer in Chinese; promote security and build blocker; defer cosmetic/future work. | Answer is English or safety-critical items are not prioritized. |

## Acceptance Checklist

- The Skill structure validates with the Codex skill validator.
- Codex loads the Skill by `prioritize-dev-tasks` and follows the expected
  behavior for every fixture.
- Documentation describes Claude Code, OpenClaw, and Hermes as
  structure-compatible until separately runtime-tested.
- ClawHub publication contains the portable Skill instructions and excludes
  Codex-only UI metadata.
