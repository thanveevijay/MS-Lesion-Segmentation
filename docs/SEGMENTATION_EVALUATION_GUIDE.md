# Lesion segmentation evaluation guide

Use this guide to make segmentation experiments reproducible. Metric values must come from actual evaluation runs; this document does not assert model performance.

## Data split
- Split at the patient level so slices from one patient cannot appear in both training and test sets.
- Keep a fixed test set and document the random seed or split manifest.
- Apply augmentation only to training images and masks together.
- Verify that image and mask dimensions, orientation, and spatial alignment match.

## Metrics
Report Dice coefficient and intersection over union (IoU) for each case, then summarize the distribution across patients. Include sensitivity/recall for lesion pixels and specify how empty ground-truth masks are handled. Do not rely on pixel accuracy alone because background pixels can dominate.

## Visual review
Inspect overlays for representative small, large, and irregular lesions. Include failure cases and note whether errors are false positives, missed regions, or boundary inaccuracies.

## Reproducibility record
Record preprocessing, image spacing, normalization, model configuration, checkpoint, software versions, and patient-level split identifiers. Avoid publishing identifiable clinical images or metadata.
