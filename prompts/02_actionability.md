# Prompt 02 — Make the Dashboard Actionable

The current dashboard is too descriptive.

Modify it so that when model performance degrades, the dashboard recommends a concrete Data Operations action.

For each issue, show:

- affected city or cohort
- performance degradation
- suspected cause
- severity
- recommended action
- proposed sample size
- priority

Example:

Scenario:
Heavy rain + dinner peak in Mumbai

Observed issue:
ETA MAE increased by 30%.

Possible cause:
Restaurant preparation-time variance under high demand.

Recommended Data Ops action:
Sample 2,000 recent heavy-rain dinner orders and create a targeted evaluation dataset.

Priority:
P0

The dashboard should help answer:

"What should the AI Data Operations Manager do next?"

Do not only show alerts.
Every major alert should lead to a recommended operational action.
