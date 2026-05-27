# Sprint Backlog Example

## Scenario

An integration sprint is in progress. The team needs an execution order, not
only quadrant labels.

## Prompt

```text
Use $prioritize-dev-tasks to order this integration sprint backlog.

Project phase: integration
Version objective: complete account creation and onboarding flow

Tasks:
1. Provide the finalized account-creation API response contract; mobile and web are waiting.
2. Wire the web onboarding UI after the contract is finalized.
3. Run onboarding regression tests after integration is complete.
4. Rename two internal helper functions for readability.
5. Add an optional avatar cropping enhancement.
```

## Expected Signals

- The API contract is ordered ahead of the dependent UI and regression work.
- The response explains dependency order even if several tasks share a
  quadrant.
- The avatar enhancement and helper renames are candidates for deferral.
