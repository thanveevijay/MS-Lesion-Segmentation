# Segmentation error analysis

Use this template after evaluating a fixed test cohort.

## Cohort summary
- Dataset version:
- Number of patients:
- Number of scans or slices:
- Patient-level split identifier:
- Exclusion criteria:

## Quantitative results
Report per-patient Dice and IoU, plus the mean, median, and spread. Include sensitivity for lesion pixels and explain how empty masks are handled. Keep the metric implementation and thresholding rule fixed across comparisons.

## Qualitative review
For each representative failure, record:
- Non-identifying case ID.
- Error type: missed lesion, false-positive region, boundary mismatch, or preprocessing issue.
- Relevant image characteristics.
- Whether the issue is isolated or repeated.
- Proposed follow-up experiment.

## Interpretation
Discuss class imbalance, small lesions, image quality, and cohort limitations. Do not generalize beyond the evaluated population without external validation.
