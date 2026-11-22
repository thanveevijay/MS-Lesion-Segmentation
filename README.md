# Multiple Sclerosis Lesion Segmentation and Progression Modelling

This repository contains a Google Colab notebook exploring MRI preprocessing, lesion segmentation, temporal modelling, and patient-level progression analysis for Multiple Sclerosis (MS).

> **Research prototype only:** this notebook is not a clinically validated diagnostic or treatment tool. Do not use its outputs to make patient-care decisions.

## Repository contents

- `MS_Lesion_Segmetation.ipynb` — end-to-end experimental notebook.
- The notebook currently contains MRI preprocessing, a U-Net-style segmentation experiment, evaluation utilities, temporal modelling experiments, graph-based modelling, and feature-fusion experiments.

## Runtime and dependencies

The notebook was authored for Google Colab and expects the dataset to be mounted from Google Drive. It currently contains paths under:

```text
/content/drive/MyDrive/MS_Project/
```

Update those paths to match your own dataset layout before running the relevant cells. The raw MRI dataset is not included in this repository.

The experiments use a mixture of TensorFlow/Keras and PyTorch, along with NumPy, pandas, nibabel, SciPy, scikit-learn, Matplotlib, and Seaborn. The graph experiment additionally uses PyTorch Geometric.

A starting environment can be installed with:

```bash
python -m pip install -r requirements.txt
```

Install a PyTorch build that matches your runtime (CPU/CUDA) before installing PyTorch Geometric. See the official installation guidance for the matching wheel instructions: https://pytorch-geometric.readthedocs.io/en/latest/install/installation.html

## Suggested execution order

1. Open the notebook in Google Colab or a compatible GPU-enabled environment.
2. Mount Google Drive and update the dataset paths in the preprocessing cells.
3. Run preprocessing and patient-level data splitting.
4. Run the segmentation model cells and inspect the segmentation metrics.
5. Run the temporal/graph experiments only after the expected intermediate arrays have been created.
6. Review the evaluation cells and verify that test data is held out by patient, not by slice.

## Reproducibility and interpretation

- Record the dataset version, patient split, random seed, and runtime/library versions for every experiment.
- Keep all slices and timepoints from a patient in the same data split to reduce leakage.
- Report segmentation metrics (such as Dice, precision, and recall) separately from progression-regression metrics (such as MAE, RMSE, and correlation).
- Do not describe estimated or illustrative metrics as measured results. Re-run evaluation on a genuinely held-out cohort before reporting performance.
- MRI preprocessing and model outputs require domain-expert review.

## Scope

The notebook is exploratory and contains multiple experimental model approaches. It is not yet packaged as a reusable training/inference library or a production clinical application.
