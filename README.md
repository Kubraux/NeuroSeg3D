# NeuroSeg3D
**Deep Learning-Based 3D Brain Tumor Segmentation and Visualization**

NeuroSeg3D is a deep learning-based project for automated 3D brain tumor segmentation from multimodal MRI scans. Developed using PyTorch and the BraTS 2021 dataset, the system combines volumetric segmentation with an interactive desktop visualization interface.

## Key Features

- **Multimodal MRI Processing:** T1, T1ce, T2, and FLAIR sequences.
- **3D Deep Learning:** Standard 3D U-Net and Advanced Residual UNet3D architectures.
- **Tumor Subregion Segmentation:** Necrotic Core (NCR), Peritumoral Edema (ED), and Enhancing Tumor (ET).
- **Multi-Planar Visualization:** Axial, sagittal, and coronal MRI views.
- **Interactive 3D Visualization:** Tumor structure visualization using PyVista.
- **Volumetric Analysis:** Calculation of tumor subregion volumes.
- **Desktop GUI:** Developed using PyQt6 and PyVista.

## Methodology

Three model configurations were evaluated:

1. **Model-1:** Baseline 3D U-Net.
2. **Model-2:** 3D U-Net with class-weighted cross-entropy loss.
3. **Model-3:** Advanced Residual UNet3D incorporating residual connections.

The training pipeline includes intensity normalization, label remapping, AdamW optimization, automatic mixed precision (AMP), and early stopping.

## Experimental Results

The following results were obtained on the BraTS 2021 test split.

| Model | Mean Dice (%) | Mean HD95 (mm) | mIoU (%) |
|---|---:|---:|---:|
| Model-1 | 71.92 | 13.15 | 59.62 |
| Model-2 | 82.47 | **9.35** | 73.30 |
| Model-3 | **83.42** | 11.77 | **74.62** |

Model-3 achieved the highest mean Dice and mIoU scores, while Model-2 achieved the lowest mean HD95.

**Advanced Residual UNet3D Dice Scores:**

- Whole Tumor (WT): **85.07%**
- Tumor Core (TC): **84.55%**
- Enhancing Tumor (ET): **81.18%**

## Graphical User Interface

The PyQt6 and PyVista-based desktop application enables users to load multimodal MRI scans, run segmentation inference, examine the results across three anatomical planes, and interactively visualize the predicted tumor structure in 3D.

The interface also provides tumor volume calculations and PNG screenshot export.

*GUI screenshots and a demonstration will be added.*

## Technologies

Python · PyTorch · 3D CNN · NumPy · NiBabel · PyQt6 · PyVista · BraTS 2021

## Project Status

The research results and project documentation are available. Source code, installation instructions, and model deployment assets will be added following repository preparation.

## Contributors

- Kübra Yiğit
- Begüm Beraye Atalay

**Academic Supervisor:** Dr. Öğr. Üyesi Gürkan Aydemir

**Institution:** Bursa Technical University, Department of Electrical and Electronics Engineering

## Disclaimer

This project was developed for academic research and educational purposes. It is not a clinically validated medical device and should not be used independently for medical diagnosis or treatment decisions.

