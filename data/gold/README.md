# Gold Set

Validation material for the G1 adoption detector (Section V of the paper).

- `CODEBOOK.txt` - the labeling instrument both annotators applied.
- `gold_labeling_coderA.csv`, `gold_labeling_coderB.csv` - the two independent
  annotators' label sheets over the 250-repository stratified gold set
  (150 detector-positive, 100 detector-negative), with the evidence columns
  shown during labeling and each annotator's ADOPTED/NOT_ADOPTED/UNSURE label.
  Disagreements and UNSURE cases were adjudicated to a single label per
  repository; detector precision/recall against the adjudicated labels are
  reported in `../../results/TABLE1_g1_validation.csv`
  (precision = recall = 1.00, Wilson 95% lower bound 0.975; Cohen's kappa 0.991).

No annotator identities are recorded. Repository identifiers are retained so the
labels can be checked against the public repositories.
