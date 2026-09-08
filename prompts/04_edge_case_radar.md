# Prompt 04 — Edge Case Radar

Add a section called:

"AI Edge Case Radar"

Its purpose is to identify emerging operational scenarios before they become widespread model failures.

Monitor synthetic signals including:

- city-level ETA error
- restaurant preparation-time distribution
- rider reassignment rate
- traffic conditions
- weather
- order-size distribution
- new restaurant onboarding
- new city launches
- festivals or major events

Create example alerts such as:

- Mumbai heavy rain + dinner peak
- Bengaluru rider reassignment spike
- Hyderabad new restaurant cluster

For every alert show:

- signal detected
- baseline value
- current value
- percentage deviation
- affected cohort
- severity
- business impact
- confidence
- suspected root cause
- recommended Data Ops action

Rank alerts using:

- P0
- P1
- P2

Do not create alerts without recommended next steps.

Every high-priority alert should result in a targeted data recommendation.
