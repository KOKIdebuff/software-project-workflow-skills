# Contributing

Thank you for improving Software Project Workflow Skills.

## Contribution Rules

- Keep each skill focused on one repeatable software project workflow.
- Use lowercase, hyphen-separated skill directory names; the directory and
  frontmatter `name` must match.
- Keep one canonical implementation at `skills/<skill-name>/SKILL.md`.
- Keep platform-specific setup in `docs/` or product metadata files, not in
  duplicated skill instructions.
- Write formal skill sources and repository documentation in English.
- For user-facing outputs, preserve or add an instruction to respond in the
  user's language when language should not change the workflow.

## Required Skill Files

A new skill requires:

```text
skills/<skill-name>/
└── SKILL.md
```

For Codex-facing skills, also add `agents/openai.yaml`. For ClawHub releases,
include `.clawhubignore` when product-specific metadata should not be
published.

## Validation

Before submitting a change:

1. Validate the affected Skill structure.
2. Add or update evaluation cases under `tests/<skill-name>/`.
3. Add an example input under `examples/<skill-name>/` for a new behavior.
4. Confirm that high-risk work is not incorrectly displaced by cosmetic or
   speculative tasks.
5. Confirm that an input in another language receives an answer in that
   language when the skill promises language matching.

## Versioning

- Use semantic versions for public releases.
- Treat changes that materially alter classification or priority behavior as a
  release-worthy change.
- Publish each ClawHub skill independently from its canonical directory.

## Licensing

By contributing, you agree that your contribution is provided under the
repository's MIT-0 license.
