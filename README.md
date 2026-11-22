# Multiple Sclerosis Lesion Segmentation and Progression Modelling

This repository contains an experimental notebook for MRI preprocessing, lesion segmentation, and exploratory progression modelling in Multiple Sclerosis (MS).

> **Research prototype only:** this project is not a clinically validated diagnostic or treatment tool. Do not use its outputs for patient-care decisions.

## Repository contents

- `MS_Lesion_Segmetation.ipynb` — end-to-end experimental notebook.
- `requirements.txt` — Python dependencies used by the notebook.

The raw MRI dataset is not included. The notebook was authored for Google Colab and currently expects data under `/content/drive/MyDrive/MS_Project/`. Update the paths in the notebook to match your own dataset before running it.

## Setup

Create an isolated environment and install the listed dependencies:

```bash
python -m venv .venv
# Windows: .venv\Scripts\activate
# macOS/Linux: source .venv/bin/activate
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

The notebook uses a mixture of TensorFlow/Keras and PyTorch. Install a PyTorch build compatible with your CPU/CUDA runtime. If running the graph-model sections, install the matching PyTorch Geometric packages using its official compatibility guide: https://pytorch-geometric.readthedocs.io/en/latest/install/installation.html

## Suggested workflow

1. Open the notebook in Google Colab or a compatible GPU-enabled environment.
2. Mount Google Drive and update dataset paths.
3. Run preprocessing and create patient-level train/validation/test splits.
4. Run segmentation experiments and inspect the generated masks.
5. Run temporal or graph-based experiments only after their required intermediate data has been generated.
6. Evaluate on held-out patients and record the exact split and random seed.

## Reproducibility and evaluation

- Keep every scan and timepoint from one patient in a single split to reduce data leakage.
- Fit normalization and other learned preprocessing only on training data.
- Report segmentation metrics (for example, Dice, precision, and recall) separately from progression metrics (for example, MAE and RMSE).
- Record dataset provenance, library versions, hardware, and random seeds.
- Do not report illustrative or placeholder values as measured model performance.
- Have MRI preprocessing and model outputs reviewed by qualified domain experts.

## Current scope

The notebook is an exploratory research workflow. It is not yet packaged as a reusable training/inference library or a production clinical application.
