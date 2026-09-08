# QuickBite ETA Data Ops Control Tower — Requirements

## 1. Problem Statement

QuickBite uses a machine learning model to predict delivery ETA at checkout and continuously update the estimate as an order moves through restaurant preparation, rider pickup, and delivery.

ETA accuracy directly affects customer trust and conversion:

* Overly optimistic ETAs create broken promises.
* Overly conservative ETAs may reduce orders.
* ETA performance can degrade differently across cities, restaurants, weather conditions, traffic patterns, and operational scenarios.

The purpose of this prototype is to design an AI-assisted Data Operations Control Tower that helps an AI Data Operations Manager monitor the complete data pipeline, detect model-performance gaps, identify emerging edge cases, and convert those signals into targeted data actions.

---

## 2. Primary User

Senior AI Data Operations Manager

The user needs to understand:

1. Is the data pipeline healthy?
2. Is the ETA model performing within acceptable thresholds?
3. Which cohorts are underperforming?
4. What may be causing the degradation?
5. What data should be sourced or evaluated next?
6. Which operational or vendor issues require intervention?

---

## 3. Core Dashboard Capabilities

### 3.1 Model Performance Monitoring

Track:

* Mean Absolute Error (MAE)
* P90 ETA error
* Percentage of orders delivered within ±10 minutes of predicted ETA
* Underprediction rate
* Overprediction rate
* Performance by city
* Performance by operational cohort

Example cohorts:

* Normal weekday
* Lunch peak
* Dinner peak
* Heavy rain
* New restaurant
* Rider reassignment
* Large order

---

## 3.2 Data Pipeline Monitoring

Track the status of:

Production data
→ ingestion
→ validation
→ segmentation
→ annotation/data preparation
→ QA
→ evaluation
→ retraining
→ production

Each stage should display:

* status
* volume
* quality
* SLA
* errors or blockers

---

## 3.3 Batch and Vendor Operations

Track:

* Batch ID
* Vendor
* Dataset type
* Assigned volume
* Completed volume
* Turnaround time
* SLA status
* QA score
* Rework rate
* Current status

---

## 3.4 Data Segmentation

Training and evaluation data must be divided into three major categories.

### Stable / Long-Term Data

Examples:

* Normal weekday demand
* Normal traffic
* Standard restaurant preparation behavior
* Established restaurants and cities

Purpose:

Maintain representative baseline coverage.

### Seasonal / Cyclical Data

Examples:

* Monsoon
* Festivals
* Weekends
* Lunch and dinner peaks
* Holiday periods

Purpose:

Capture predictable distribution changes.

### Edge-Case Data

Examples:

* Rider reassignment
* Road closure
* Extreme weather
* New restaurant
* New city
* Unusual traffic spike
* Large group order

Purpose:

Improve model robustness against rare or emerging scenarios.

These categories should use different sampling, refresh, annotation, and evaluation strategies.

---

## 3.5 Targeted Data Acquisition

The system should prioritize the most valuable next dataset instead of simply collecting more data.

Candidate prioritization should consider:

* model error
* business impact
* frequency
* model uncertainty
* data coverage gap
* recency

Example:

Heavy rain + dinner peak in Mumbai

Model impact:
High

Coverage:
Low

Recommended action:
Sample 2,000 recent orders for targeted evaluation.

Priority:
P0

---

## 3.6 Proactive Edge-Case Discovery

The prototype should include an Edge Case Radar.

Potential signals include:

* sudden ETA error increase
* traffic distribution shift
* weather changes
* restaurant preparation-time shift
* rider reassignment increase
* new city launch
* new restaurant onboarding
* festival or major-event calendar
* unusual order-size distribution

The system should attempt to surface emerging scenarios before they create widespread model failures.

---

## 3.7 AI-Assisted Operational Workflow

The proposed workflow will contain four logical AI agents.

### Detection Agent

Identifies anomalies, drift, or threshold breaches.

### Triage Agent

Segments the issue and identifies the most affected cohorts.

### Data Strategy Agent

Recommends which targeted data should be sourced or evaluated.

### Evaluation Agent

Assesses whether a candidate model improves affected cohorts without introducing regressions.

---

## 3.8 Human-in-the-Loop Controls

AI recommendations should not automatically trigger production-impacting actions.

Human approval should be required before:

* launching large data-collection batches
* changing annotation strategy
* initiating retraining
* approving model promotion
* production deployment

Proposed workflow:

AI detection
→ AI triage
→ AI recommendation
→ human approval
→ execution
→ evaluation
→ deployment decision

---

## 4. Synthetic Data

This prototype will use synthetic data only.

No QuickBite production data or confidential information will be used.

Synthetic datasets will simulate:

* orders
* ETA predictions
* actual delivery times
* city
* restaurant
* weather
* traffic
* rider behavior
* batch/vendor operations
* edge-case incidents

---

## 5. Prototype Success Criteria

The prototype should allow an operator to answer the following within approximately 10 seconds:

* Is the system healthy?
* Where is model performance degrading?
* What cohort is responsible?
* What is the likely operational cause?
* What action should Data Ops take?
* What data should be prioritized next?

The prototype should prioritize operational decision-making over visual complexity.
