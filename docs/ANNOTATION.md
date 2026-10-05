# Annotation Protocol (G1 Validation)

The detector is validated against a 250-repository gold set labeled by two
independent annotators using `../data/gold/CODEBOOK.txt`.

1. **Calibration round.** Both annotators label a shared ~25-repository batch
   independently, then meet to reconcile understanding of edge cases. The
   codebook is refined if systematic ambiguity is found.
2. **Independent labeling.** Each annotator labels the full gold set from the
   repository's own public evidence (commit history, file tree, README/
   CONTRIBUTING), without seeing the detector's verdict or the other
   annotator's labels.
3. **Adjudication.** Disagreements and UNSURE cases are resolved against the
   codebook to a single label per repository.
4. **Metrics.** Cohen's kappa is computed over decided pairs; detector
   precision/recall/F1 are computed against the adjudicated labels with Wilson
   95% confidence intervals. The pre-registered gate requires the precision
   Wilson lower bound >= 0.90.

Reported: kappa = 0.991; precision = recall = 1.00 (Wilson lower bound 0.975);
confusion 150/0/0/100.
