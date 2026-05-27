# Technical Debt Example

## Scenario

The service is stable and no release is imminent. The team wants to plan
engineering improvements without claiming that everything is urgent.

## Prompt

```text
Use $prioritize-dev-tasks to assess these maintenance tasks.

Project phase: maintenance
Version objective: improve reliability over the next quarter

Tasks:
1. Add automated tests for the payment reconciliation rules.
2. Reduce duplicated validation logic across three order endpoints.
3. Replace an old monitoring dashboard theme.
4. Investigate a memory increase observed in a low-traffic batch job.
```

## Expected Signals

- Important reliability work may be classified as important but not urgent.
- The response does not manufacture an immediate release blocker.
- Dashboard theming is a deferrable low-value item unless new evidence is
  supplied.
