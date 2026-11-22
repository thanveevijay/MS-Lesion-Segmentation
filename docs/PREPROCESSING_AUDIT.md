# Preprocessing audit checklist

Before running a segmentation experiment, verify that preprocessing is consistent and traceable.

- Confirm image and mask files are paired using stable identifiers, not directory ordering.
- Check image-mask dimensions and spatial alignment before resizing.
- Apply identical geometric transforms to each image and its mask.
- Use interpolation suitable for the data type: continuous interpolation for images and label-preserving interpolation for categorical masks.
- Document intensity normalization and any clipping or rescaling.
- Fit any data-dependent normalization parameters using training data only.
- Preserve patient-level grouping throughout splitting and evaluation.
- Visualize samples before and after preprocessing, including edge cases.
- Record excluded cases and the reason for exclusion.

Do not silently discard difficult scans. Report preprocessing failures and their impact on the final evaluation cohort.
