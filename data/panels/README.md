# Repository-month panels

Populated by notebook 03A. Expected files:
- `panel_full.parquet` - repository x month outcomes over the full window.
- `panel_windowed.parquet` - event-time window used for the DiD.
- `panel_ci_cleaned.parquet` - CI-minutes panel with retention-truncated
  pre-adoption months masked as missing (not zero).
