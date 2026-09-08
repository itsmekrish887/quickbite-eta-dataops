# Prompt 08 — Data Validation and Automatic Metrics

Improve the Data Ingestion Center by adding a Data Validation Report.

For every uploaded dataset, calculate and display:

- total rows received
- schema validity
- missing-value count
- duplicate-row count
- invalid-value count
- data quality score
- validation status

For order-level ETA data, automatically calculate:

1. Mean Absolute Error (MAE)

MAE = average absolute difference between:
predicted_eta_min and actual_delivery_min

2. P90 Absolute ETA Error

Calculate the 90th percentile of absolute ETA error.

3. Percentage Within ±10 Minutes

Calculate the percentage of orders where the absolute ETA error is less than or equal to 10 minutes.

4. Underprediction Rate

Percentage of orders where:
predicted_eta_min < actual_delivery_min

This represents overly optimistic ETA predictions.

5. Overprediction Rate

Percentage of orders where:
predicted_eta_min > actual_delivery_min

This represents overly conservative ETA predictions.

After a dataset is approved:

- update overall metrics
- update city-level performance
- update cohort-level performance
- update edge-case counts where relevant

Do not modify dashboard metrics before human approval.
