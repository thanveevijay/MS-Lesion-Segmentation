Multi-Scale Temporal Modeling for MS Disease Progression

This project presents a multi-scale deep learning framework to model lesion dynamics and predict disease progression in Multiple Sclerosis (MS) using longitudinal MRI data. The approach captures temporal patterns at voxel, lesion, and patient levels, enabling more accurate and clinically meaningful predictions.

🔍 Problem Statement
Traditional MS lesion analysis methods focus on lesion volume or count at individual timepoints and fail to capture temporal evolution across multiple scales. This limits early prediction of disease progression and treatment response.

🎯 Objectives
Model temporal lesion dynamics across multiple scales
Detect early voxel-level changes before visible lesion formation
Track lesion growth, shrinkage, and interactions over time
Predict patient-level disease progression (EDSS trend)

🧠 Methodology Overview
1. Data Acquisition
Longitudinal multi-modal MRI scans: T1, T2, FLAIR
Clinical data including EDSS scores

3. Preprocessing
Skull stripping
Bias field correction
Registration across timepoints
Intensity normalization

3. Lesion Segmentation
3D U-Net used to segment MS lesions from MRI volumes
Generates temporal lesion masks for each patient

4. Multi-Scale Temporal Modeling
Voxel-Level: CNN + LSTM
Captures fine-grained voxel intensity changes over time
Lesion-Level: Attention-based model
Learns lesion evolution patterns (growth, merging, regression)
Patient-Level: Gradient Descent–based sequence model
Integrates lesion features and clinical data

5. Fusion & Prediction
Multi-scale features are fused into a unified representation

Predicts:
Future lesion activity
Disease progression trends (EDSS)

🧪 Evaluation Metrics
Dice Coefficient (lesion segmentation accuracy)
Precision & Recall
EDSS correlation
MAE / RMSE for progression prediction

🛠️ Tech Stack
Python
PyTorch
MONAI
NumPy, SciPy
Medical imaging formats: NIfTI

📁 Project Structure (example)
├── data/
│   ├── raw/
│   └── processed/
├── preprocessing/
├── segmentation/
│   └── unet_3d.py
├── models/
│   ├── voxel_cnn_lstm.py
│   ├── lesion_attention.py
│   └── patient_gd_model.py
├── evaluation/
├── results/
├── README.md

🚀 Key Contributions
Unified multi-scale temporal framework for MS analysis
Early detection using voxel-level temporal modeling
Attention-driven lesion evolution tracking
Patient-level progression prediction using deep learning

📌 Future Work
Incorporate transformer-based temporal models
Extend framework to other neurodegenerative diseases
Improve interpretability with attention visualization
