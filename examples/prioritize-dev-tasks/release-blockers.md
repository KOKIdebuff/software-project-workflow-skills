# Release Blockers Example

## Scenario

The product is planned for release tomorrow. QA and release engineering are
waiting for a go/no-go decision.

## Prompt

```text
Use $prioritize-dev-tasks to prioritize the unfinished work for tomorrow's release.

Project phase: pre-release testing
Version objective: release checkout improvements tomorrow

Tasks:
1. Fix an authorization bypass that lets a support user export another tenant's orders.
2. Repair the deployment pipeline failure that prevents staging promotion.
3. Update spacing and hover colors on the account settings page.
4. Add an index suggested for a reporting screen that is slow but still usable.
5. Rewrite a release-note paragraph requested by marketing before announcement.
```

## Expected Signals

- The authorization bypass is treated as a highest-priority security issue.
- The pipeline failure is identified as a release blocker.
- Cosmetic styling does not appear among the top priorities.
- The answer uses the full-output structure because release and security risk
  are present.
