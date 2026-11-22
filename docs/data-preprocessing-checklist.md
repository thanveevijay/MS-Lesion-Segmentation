# MRI Data Preprocessing Checklist

## Dataset integrity
- Keep patient-level identifiers separate from model input features.
- Check that image files can be opened and decoded.
- Confirm image dimensions, channel conventions, and voxel spacing where available.
- Identify missing images, missing masks, and mismatched image-mask pairs.
- Preserve the mapping between each scan and its segmentation mask.

## Image and mask alignment
- Verify that image and mask shapes are compatible.
- Confirm that spatial orientation and voxel spacing are handled consistently.
- Use nearest-neighbour interpolation for categorical masks when resizing.
- Check that mask labels remain valid after every transformation.

## Normalization
- Select an intensity normalization method appropriate to the MRI sequence.
- Fit any data-dependent normalization parameters using training data only.
- Apply the same fitted transformation to validation and test data.

## Leakage prevention
- Split by patient, not by individual slice, when multiple slices belong to one patient.
- Keep all derived slices from a patient in the same partition.
- Do not use test data to tune preprocessing or model thresholds.

## Final validation
Create a small visual audit showing original images, masks, and processed outputs before starting a full training run.
