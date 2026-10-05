# Data Provenance and Ethics

## Sources
All data derive from public GitHub surfaces accessed via the official REST and
GraphQL APIs:
- repository metadata and search (sampling frame);
- commit metadata and messages (adoption signals, commit activity);
- repository file trees (configuration-artifact signals, source-file ratio);
- pull-request metadata (PR activity);
- GitHub Actions workflow-run records (CI runs and durations).

## Scope and ethics
- Only public repositories are used. No private repositories, no authenticated
  user data beyond public commit metadata.
- No human-subjects research is involved; the gold set is labeled by the
  authors against a published codebook. No personal data about contributors is
  collected, analyzed, or redistributed beyond what is public commit metadata.
- Carbon figures are model-based estimates (operational emissions only), not
  measured energy; conversion factors and their ranges are in
  `../results/carbon_factors.json`.

## Retention constraint (documented limitation)
GitHub Actions run histories age out of the platform's retention window
(~12-14 months in our probe). CI outcomes are therefore analyzed only on
repositories with a genuine retrievable pre-adoption baseline, and truncated
pre-baseline months are treated as missing rather than zero.

## Reproducibility
The pipeline caches API responses and checkpoints per repository, so a re-run
reproduces the same frame without additional API cost. Collection spans
multiple sessions under standard authenticated rate limits.
