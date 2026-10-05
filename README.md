# Replication Package

**The Second-Order Carbon Footprint of AI Coding Tools: A Difference-in-Differences Study in Open Source**

*Anonymized for double-blind review.*

This package contains the full, re-runnable pipeline, the validation gold set and
codebook, the analysis-ready panels, and every table and figure reported in the
paper. The study mines public GitHub data only; no human-subjects data and no
private repositories are used. The entire pipeline runs in Google Colab on openly
collectable data.

---

## 1. What this package reproduces

Every quantitative claim in the paper maps to an artifact here:

| Paper element | Artifact |
|---|---|
| Detector validation (Table I: precision/recall 1.0, CI [0.975,1.0], kappa 0.991) | `results/TABLE1_g1_validation.csv`, `data/gold/` |
| Attrition (Table II: 1,173 -> 614 -> 481 -> 223 -> 179/91) | `results/attrition.json`, `data/frame/`, `data/cohort/` |
| DiD estimates (Table III) | `results/did_main.csv` |
| Event study (Fig. 1) | `results/event_study_ci_minutes.csv`, `figures/event_study_ci_minutes.png` |
| Trend-adjusted reanalysis (level +11.2%, slope +47.7%, placebo -5.2%) | `results/reframed_claim.json` |
| Heterogeneity (+371%/+161%/+73%; by language) | `results/heterogeneity_ci_minutes.csv` |
| Carbon band (0.10/1.86/6.41 tCO2e) | `results/carbon_band_adopter_cohort.csv`, `results/carbon_factors.json` |
| Attribution gap (Fig. 2; ~6x) | `results/attribution_gap.csv`, `figures/attribution_gap.png` |
| Carbon-conversion factors (Table IV) | `results/carbon_factors.json` |

## 2. Pipeline overview

The pipeline is five sequential Colab notebooks under `notebooks/`. Each is
resumable and checkpoints to persistent storage, so an interrupted run resumes
without data loss or repeated API cost.

| Notebook | Purpose | Produces |
|---|---|---|
| `01_setup_prereg_feasibility.ipynb` | Pre-registration, project setup, resilient GitHub client, feasibility probe | `PREREGISTRATION.txt`, `config.json`, probe outputs |
| `02_frame_and_G1_validation.ipynb` | Stratified sampling frame + software-project filter; the G1 adoption-detector validation gate | `data/frame/`, `data/gold/`, `results/TABLE1_g1_validation.csv` |
| `03A_adoption_dating_and_panels.ipynb` | Adoption dating, control pseudo-dating, repository-month panel construction | `data/cohort/`, `data/panels/` |
| `03B_matching_did_eventstudy.ipynb` | Matching + balance, two-way FE DiD, event study, placebo, heterogeneity | `results/did_main.csv`, `results/event_study_ci_minutes.csv`, `results/heterogeneity_ci_minutes.csv` |
| `04_carbon_accounting.ipynb` | CI-minutes -> energy -> CO2e band; attribution gap | `results/carbon_band_adopter_cohort.csv`, `results/attribution_gap.csv`, `results/carbon_factors.json` |

## 3. How to run

1. Open the notebooks in Google Colab in numeric order.
2. In `01`, add a GitHub personal access token (public-repo read scope) via
   Colab Secrets as `GITHUB_TOKEN`. No other credentials are needed.
3. Run each notebook top to bottom. Notebooks `01`-`03A` perform data
   collection (multi-session; resumable). Notebooks `03B` and `04` are pure
   analysis and run in minutes on the collected panels.
4. The G1 validation gate in `02` requires two human annotators to label the
   gold set against `data/gold/CODEBOOK.txt`; see `docs/ANNOTATION.md`.

A frozen environment is pinned in `requirements.txt`.

## 4. Data provenance and ethics

All data derive from the public GitHub REST and GraphQL APIs and public
repository contents. No private repositories, no personal data beyond public
commit metadata, and no human-subjects protocol are involved. The adoption gold
set was labeled by the authors. See `docs/DATA_PROVENANCE.md`.

## 5. License

Code: MIT (see `LICENSE`). Data derived from GitHub is redistributed under the
terms of the source repositories; see `docs/DATA_PROVENANCE.md`.
