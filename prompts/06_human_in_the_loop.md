# Prompt 06 — Human-in-the-Loop Governance

Add explicit human-in-the-loop controls to the agent workflow.

AI agents should provide recommendations, but they must not automatically trigger production-impacting actions.

Human approval should be required before:

- launching large-scale data collection
- assigning data to external vendors
- changing annotation strategy
- initiating retraining
- promoting a candidate model
- deploying a model to production

For every AI recommendation, provide three actions:

- Approve
- Modify
- Reject

Add an "AI Decision Trace" for each recommendation.

Show:

1. Signal detected
2. Threshold breached
3. Affected cohort
4. Suspected root cause
5. Data coverage gap
6. Recommended action
7. Proposed sample size
8. Confidence score
9. Human decision
10. Decision timestamp

Clearly label AI-generated diagnoses as recommendations, not facts.

The UI should make it clear that human judgment remains the final control point.
