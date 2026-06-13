# LISA Challenge Medical Image Segmentation

## Overview

This project was developed as part of the **LISA Challenge 2025** and focuses on automatic segmentation of brain structures from low-field MRI scans using deep learning techniques.

The system leverages an Attention U-Net architecture implemented with MONAI and PyTorch to perform accurate volumetric segmentation of anatomical structures including:

* Hippocampus
* Basal Ganglia

The pipeline covers the complete workflow from dataset preparation and preprocessing to model training, evaluation, and visualization.

---

## Features

* 3D MRI volume processing
* Attention U-Net architecture
* MONAI-based medical imaging workflow
* Automated preprocessing and normalization
* Data augmentation support
* Dice-based segmentation optimization
* Early stopping and checkpoint saving
* Validation and testing pipelines
* Segmentation performance visualization
* Confusion matrix and classification metrics generation

---

## Dataset

This project uses the dataset provided during the **LISA Challenge 2025**.

The dataset contains:

* Low-field MRI volumes (.nii/.nii.gz)
* Hippocampus segmentation masks
* Basal ganglia segmentation masks

---

## Model Architecture

The primary model used in this project is:

### Attention U-Net

Key characteristics:

* 3D Convolutional Neural Network
* Encoder-decoder architecture
* Attention gates for enhanced feature selection
* Multi-scale feature extraction
* Skip connections for precise localization

---

## Training Configuration

| Parameter             | Value           |
| --------------------- | --------------- |
| Architecture          | Attention U-Net |
| Input Channels        | 1               |
| Spatial Dimensions    | 3D              |
| Optimizer             | AdamW           |
| Learning Rate         | 1e-4            |
| Weight Decay          | 1e-5            |
| Epochs                | 100             |
| Batch Size            | 2               |
| Validation Batch Size | 1               |

### Loss Functions

* Dice Cross Entropy Loss
* Focal Dice Loss (experimental)

### Evaluation Metrics

* Dice Score
* Hausdorff Distance
* Precision
* Recall
* F1 Score
* Accuracy

---

## Installation

```bash
pip install nibabel matplotlib pandas numpy scikit-learn torch torchvision tqdm monai scipy
```

---

## Project Structure

```text
project/
│
├── data/
│   ├── Low Field Images/
│   ├── Hippocampus Segmentations/
│   └── Basal Ganglia Segmentations/
│
├── notebooks/
│   └── LisaChallenge.ipynb
│
├── models/
│   └── best_attention_unet.pth
│
├── outputs/
│   ├── plots/
│   ├── predictions/
│   └── metrics/
│
└── README.md
```

---

## Results

The model was evaluated using segmentation-specific metrics including Dice Score and Hausdorff Distance. Training and validation performance were monitored throughout the training process, with the best-performing model automatically saved during training.

---

## Future Improvements

* Transformer-based segmentation models
* SwinUNETR implementation
* Cross-validation experiments
* Multi-organ segmentation support
* Hyperparameter optimization
* Deployment as a clinical decision-support tool

---

## Acknowledgements

This work was developed for the **LISA Challenge 2025** and utilizes the MONAI framework and PyTorch ecosystem for medical image analysis.
