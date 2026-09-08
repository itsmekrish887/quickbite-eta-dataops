# Prompt 03 — Separate Stable, Seasonal and Edge-Case Data

The current system treats training and evaluation data as a single category.

Change this.

Introduce three explicit dataset types:

1. Stable / Long-Term Data
Examples:
- normal weekday demand
- normal traffic
- standard restaurant preparation behavior
- established restaurants
- established cities

2. Seasonal / Cyclical Data
Examples:
- monsoon
- festivals
- weekends
- lunch peaks
- dinner peaks
- holiday periods

3. Edge-Case Data
Examples:
- rider reassignment
- road closures
- extreme weather
- new restaurants
- new cities
- unusual traffic spikes
- large group orders

For each data category show:

- current coverage
- desired coverage
- sampling strategy
- annotation priority
- refresh frequency
- evaluation importance

Make it visually clear that these three data types should not be sourced, sampled, refreshed, or weighted identically.

Add this information into the Targeted Data Acquisition section.
