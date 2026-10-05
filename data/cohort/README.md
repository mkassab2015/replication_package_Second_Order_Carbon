# Cohort data

Populated by notebook 03A. Expected files:
- `adoption_dates.parquet` - per-adopter adoption date and dating source.
- `cohort.parquet` - treated + control cohort with (pseudo-)adoption dates,
  CI-eligibility flags, and matching covariates.
- `covariates_matched.parquet` - matched sample with propensity scores and
  SMD balance.
