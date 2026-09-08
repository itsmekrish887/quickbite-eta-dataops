# Prompt 05 — Add Agentic Workflow

Add an AI-assisted workflow for each high-priority incident.

Use four logical AI agents:

1. Detection Agent
Responsibilities:
- detect model-performance anomalies
- detect drift
- detect threshold breaches
- detect unusual operational patterns

2. Triage Agent
Responsibilities:
- segment the issue
- identify the most affected cohorts
- compare current performance against baseline
- identify likely contributing factors

3. Data Strategy Agent
Responsibilities:
- identify data coverage gaps
- recommend what data should be sourced next
- propose sample size
- propose sampling strategy
- assign priority

4. Evaluation Agent
Responsibilities:
- evaluate candidate models
- compare against baseline
- assess affected cohorts
- check regression risk
- recommend whether the model should progress

Show the workflow:

Detection Agent
→ Triage Agent
→ Data Strategy Agent
→ Human Approval
→ Data Preparation / Annotation
→ Evaluation
→ Retraining
→ Production

Use completed, active and pending states.

This is a prototype, so the agents may use simulated logic and synthetic data.
