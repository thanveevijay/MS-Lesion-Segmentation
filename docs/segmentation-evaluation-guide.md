# Segmentation Evaluation Guide

## Core overlap metrics

For predicted mask P and reference mask G:

- Dice coefficient: measures overlap, with stronger emphasis on correctly capturing the target region.
- Intersection over Union (IoU): intersection divided by union.
- Sensitivity: fraction of reference-positive voxels correctly identified.
- Precision: fraction of predicted-positive voxels that are reference-positive.

Report the metric definitions and the foreground-label convention used by the experiment.

## Evaluation practices
1. Compute metrics separately for each patient or scan.
2. Define how empty reference masks and empty predictions are handled.
3. Aggregate patient-level scores using clearly stated mean or median statistics.
4. Include the number of evaluated cases alongside every summary.
5. Inspect representative false-positive and false-negative regions.

## Reporting
A useful evaluation report includes:
- Dataset split and patient count
- Model checkpoint and preprocessing version
- Per-case metrics
- Aggregate metrics and variability
- Qualitative overlays for representative cases
- Known limitations and failure cases

Do not interpret a high overlap score as proof of clinical suitability. Segmentation outputs require appropriate expert validation before clinical use.
