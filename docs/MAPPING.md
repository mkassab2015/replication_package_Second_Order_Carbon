# Paper-to-Artifact Mapping

| Paper claim / element | Value | Artifact |
|---|---|---|
| Frame size | 1,173 repos | results/attrition.json |
| Adopters / non-adopters | 340 / 833 | results/attrition.json |
| Detector precision/recall | 1.00 (CI 0.975-1.00) | results/TABLE1_g1_validation.csv |
| Inter-annotator kappa | 0.991 | results/TABLE1_g1_validation.csv |
| Activity DiD (commits) | +4.0%, p=0.67 | results/did_main.csv |
| Activity DiD (PRs) | -6.5%, p=0.43 (p_bh=0.57) | results/did_main.csv |
| Naive CI runs | +93.6%, p_bh<0.01 | results/did_main.csv |
| Naive CI-minutes | +134.9%, p_bh<0.01 | results/did_main.csv |
| Pre-trend joint test | F=4.54, p=0.012 | results/event_study_ci_minutes.csv |
| Pre-existing rise | +24%/period, p=0.011 | results/reframed_claim.json |
| Trend-adj. level | +11.2%, p=0.65 | results/reframed_claim.json |
| Trend-adj. slope | +47.7%, p=0.074 | results/reframed_claim.json |
| Placebo | -5.2%, p=0.68 | results/reframed_claim.json |
| Heterogeneity (band) | +371/+161/+73% | results/heterogeneity_ci_minutes.csv |
| Carbon band | 0.10/1.86/6.41 tCO2e | results/carbon_band_adopter_cohort.csv |
| Carbon factors | see table | results/carbon_factors.json |
| Attribution gap | 0.10 vs 0.02 tCO2e (~6x) | results/attribution_gap.csv |
