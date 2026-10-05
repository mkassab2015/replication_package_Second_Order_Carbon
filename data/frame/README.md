# Frame data

- `frame_final.parquet` - the 1,173-repository sampling frame after the
  software-project filter, with per-repository metadata, detected adoption
  signals (`high_conf_signal`, 340 adopters), and retrievable CI-history depth.
- `frame_construction_attrition.json` - counts at each frame-construction
  filtering step (2,025 candidates enriched -> 1,244 with CI -> 1,900 with
  source-ratio >= 0.10 -> 1,173 final frame; 72 doc-like dropped).

The analysis-sample attrition (1,173 -> 614 -> 481 -> 223 -> 179/91) is in
`../../results/attrition.json`.
