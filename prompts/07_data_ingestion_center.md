# Prompt 07 — Data Ingestion Center

Add a new feature called:

"Data Ingestion Center"

The goal is to allow an AI Data Operations Manager to upload new operational data and validate it before it affects dashboard metrics.

Support:

1. CSV upload
2. JSON upload
3. Manual edge-case entry

For uploaded CSV or JSON files, use this workflow:

Upload
→ Schema Validation
→ Data Quality Checks
→ Preview
→ Data Classification
→ Human Approval
→ Ingestion

Supported dataset types:

A. Order-Level ETA Data

Expected fields:
- order_id
- city
- predicted_eta_min
- actual_delivery_min
- weather
- traffic_level
- restaurant_load
- rider_reassignment
- data_segment

B. Edge-Case Incident Data

Expected fields:
- incident_id
- city
- scenario
- severity
- affected_metric
- baseline_value
- current_value
- recommended_action

After upload:

- detect the dataset type automatically
- validate required columns
- flag missing values
- flag invalid values
- count duplicate rows
- show row count
- show validation status
- display a preview of the first rows

Allow the user to approve or reject ingestion.

Only approved data should update dashboard metrics.

For the prototype:
- use synthetic or local data only
- do not require a production backend
- do not require external APIs
